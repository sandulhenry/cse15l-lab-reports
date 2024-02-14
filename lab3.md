# Lab Report 3
## CSE 15L WI24 - Sandul Henry

---

* A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown):

JUNIT test:
```
  @Test
  public void testReversedFAIL() {
    int[] input1 = {1,2,3,4};
    assertArrayEquals(new int[]{4,3,2,1}, ArrayExamples.reversed(input1));
  }
```

Output:
```
sandu@Sandul_Dell MINGW64 ~/OneDrive/Documents/School/CSE15L/lab3/lab3 (main)
$ java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ArrayTests
JUnit version 4.13.2
..E
Time: 0.022
There was 1 failure:
1) testReversed(ArrayTests)
arrays first differed at element [0]; expected:<4> but was:<0>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReversed(ArrayTests.java:16)
        ... 32 trimmed
Caused by: java.lang.AssertionError: expected:<4> but was:<0>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 38 more

FAILURES!!!
Tests run: 2,  Failures: 1
```


* An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown):

JUNIT test:
```
@Test
  public void testReversed() {
    int[] input1 = {0,0};
    assertArrayEquals(new int[]{0,0}, ArrayExamples.reversed(input1));
  }
```

Output:
```
sandu@Sandul_Dell MINGW64 ~/OneDrive/Documents/School/CSE15L/lab3/lab3 (main)
$ java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ArrayTests
JUnit version 4.13.2
..
Time: 0.018

OK (2 tests)
```


* The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above):

![screenshot](/Screenshot 2024-02-10 190102.png)


* The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

Before:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

After:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

In the original code, the initial array was being modified and returned. However, in the after, the correct array is updated and returned, so that the correct output is returned. 

---

### `grep` command line options

### `-i`, or `--ignore_case`
```
sandu@Sandul_Dell MINGW64 ~/OneDrive/Documents/School/CSE15L/docsearch/technical (main)
$ grep -i "INDEED" */*.txt | head
911report/chapter-1.txt:    The aircraft that spotted the "black smoke" was the same unarmed Air National Guard cargo plane that had seen American 77 crash into the Pentagon 27 minutes earlier. It had resumed its flight to Minnesota and saw the smoke from the crash of United 93, less than two minutes after the plane went down. At 10:17, the Command Center advised headquarters of its conclusion that United 93 had indeed crashed.
911report/chapter-1.txt:    At the White House, the video teleconference was conducted from the Situation Room by Richard Clarke, a special assistant to the president long involved in counterterrorism. Logs indicate that it began at 9:25 and included the CIA; the FBI; the departments of State, Justice, and Defense; the FAA; and the White House shelter. The FAA and CIA joined at 9:40. The first topic addressed in the White House video teleconference-at about 9:40-was the physical security of the President, the White House, and federal agencies. Immediately thereafter it was reported that a plane had hit the Pentagon. We found no evidence that video teleconference participants had any prior information that American 77 had been hijacked and was heading directly toward Washington. Indeed, it is not clear to us that the video teleconference was fully under way before 9:37, when the Pentagon was struck.
911report/chapter-11.txt:                imagine that aircraft could be used as weapons. Indeed, since al Qaeda and other
911report/chapter-11.txt:                needed to be restored across the board. Indeed, the CTC budget had not been cut
911report/chapter-12.txt:            Economic openness is essential. Terrorism is not caused by poverty. Indeed, many
911report/chapter-12.txt:            Throughout government, and indeed in private enterprise, agencies and firms at these
911report/chapter-12.txt:                percent of the critical infrastructure in the nation. Indeed, unless a terrorist's
911report/chapter-13.3.txt:                high-level UAE officials had indeed been at the desert camp. CIA memo, "Recent High
911report/chapter-13.4.txt:                involving himself in al Qaeda's broader terrorist program. Indeed, KSM describes
911report/chapter-13.4.txt:                Indeed, the surviving plot participants have either not mentioned hawala or have
```

* The argument shows results that ignore case, so it searches for strings like "INDEED", "indeed", or "Indeed", of combinations thereof. It is useful to search for many different occurances.

```
sandu@Sandul_Dell MINGW64 ~/Downloads/docsearch/technical (main)
$ grep -i "Bio" */*.txt | head
911report/chapter-11.txt:                as Serbian ethnic cleansing, biological attacks, Iraqi weapons of mass destruction,
911report/chapter-11.txt:                Interest in Biological, Radiological Weapons" (February 2001), "Taliban Holding Firm
911report/chapter-11.txt:                chemical, biological, or nuclear attack-and he downplayed even that, writing several
911report/chapter-11.txt:            With the important exception of analysis of al Qaeda efforts in chemical, biological,
911report/chapter-12.txt:                    nuclear, chemical, radiological, or biological attack;
911report/chapter-12.txt:                than two dozen other terrorist groups are pursuing CBRN [chemical, biological,
911report/chapter-12.txt:            A Biometric Screening System
911report/chapter-12.txt:                information in "feeder" documents used in identifying individuals. Biometric
911report/chapter-12.txt:            Since September 11, the United States has built the first phase of a biometric
911report/chapter-12.txt:                Indicator Technology program). It takes two biometric identifiers-digital
```

* the `-i` arguement ignores the case. This was, it finds anything matching the letters, regardless of uppercase or lowercase. In this case, it searches for case-insensitive occurances of "Bio".

* Source: [thegeekstuff.com](https://www.example.com](https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/ )

### `-c`, or `--count`

```
sandu@Sandul_Dell MINGW64 ~/Downloads/docsearch/technical/biomed (main)
$ grep -c -i "biology"  *.txt | head
1468-6708-3-1.txt:0
1468-6708-3-10.txt:0
1468-6708-3-3.txt:0
1468-6708-3-4.txt:0
1468-6708-3-7.txt:0
1471-2091-2-10.txt:0
1471-2091-2-11.txt:0
1471-2091-2-12.txt:0
1471-2091-2-13.txt:0
1471-2091-2-16.txt:0
```

* the `-c` argument in this case goes file by file and returns the number of occurances. In the short example here, none of the files have an appearence of the word "Biology". This is useful to manually look for files that contain a string.

```
sandu@Sandul_Dell MINGW64 ~/Downloads/docsearch/technical/plos (main)
$ grep -c -i "science" journal.pbio.0020001.txt
21
```

* the `-c` option functions to "count" the number of matches of the argument string. For example, it returned the number of times a case-insensitive "science" appeared in a text file. This is useful to clear, immediate answer on how many times a string appears.

* Source: [thegeekstuff.com](https://www.example.com](https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples )

### `-l`, or `--files-with-matches`

```
sandu@Sandul_Dell MINGW64 ~/Downloads/docsearch/technical/plos (main)
$ grep -r -l "biology" | head
journal.pbio.0020001.txt
journal.pbio.0020012.txt
journal.pbio.0020028.txt
journal.pbio.0020042.txt
journal.pbio.0020043.txt
journal.pbio.0020063.txt
journal.pbio.0020067.txt
journal.pbio.0020071.txt
journal.pbio.0020073.txt
journal.pbio.0020127.txt
```

* the `-l` option lists the files where there is a match. This useful to group those files, if you wanted to redirect it to another command or file to store the output.

```
sandu@Sandul_Dell MINGW64 ~/Downloads/docsearch/technical/government/Media (main)
$ grep -l -i "California" *.txt
Assuring_Underprivileged.txt
Bridging_legal_aid_gap.txt
Coup_Reshapes_Legal_Aid.txt
Farm_workers.txt
Few_who_need.txt
Free_Legal_Assistance.txt
Kiosks_for_court_forms.txt
Legal-aid_chief.txt
Legal_hotline.txt
Lockyer_Warns.txt
Nonprofit_Buys.txt
Understanding.txt
Unusual_Woodburn.txt
Workers_aid_center.txt
Working_for_Free.txt
water_fees.txt
```

* `-l` performance is similar to the previous example. It displays the files that contain a match.

* Source: [man7.org](https://man7.org/linux/man-pages/man1/grep.1.html)

### `--exclude-dir` option

```
sandu@Sandul_Dell MINGW64 ~/Downloads/docsearch/technical (main)
$ grep -i -r "Microbiology" --exclude-dir=biomed
plos/journal.pbio.0020145.txt:        biology, biochemistry, cell development, genetics, microbiology, molecular biology [see
plos/journal.pbio.0020439.txt:          reagents in microbiology may pose security risks in the hands of terrorists. Problems of
```

* the `--exclude-dir=biomed` excludes any results contained in the /biomed/ directory. This is useful to recursively search the contents of a directory while excluding one.

```
sandu@Sandul_Dell MINGW64 ~/Downloads/docsearch/technical (main)
$ grep -i -r "science" --exclude-dir={plos,biomed,government}
911report/chapter-13.1.txt:                all-source analysis, and advanced science and technology.
911report/chapter-13.4.txt:                1987, Sufaat received a bachelor's degree in biological sciences, with a minor in
911report/chapter-13.4.txt:                the National Academy of Sciences, Washington, D.C.), in which he spoke directly to
911report/chapter-13.5.txt:                Needed to Reduce Time Taken to Adjudicate Visas for Science Students and Scholars,"
911report/chapter-2.txt:                satisfy its own conscience and justify its existence."
911report/chapter-2.txt:                humanities and social sciences. Many of these young men, even if able to study
911report/chapter-3.txt:                Academy of Sciences and presented his most somber account yet of what could happen
```

* the `--exclude-dir` option can also be used to exclude multiple directories. In this case, the directories to exclude will be placed inside the brackets `{}`

* Source: [man7.org](https://man7.org/linux/man-pages/man1/grep.1.html) and [baeldung.com](https://www.baeldung.com/linux/grep-exclude-directories )
