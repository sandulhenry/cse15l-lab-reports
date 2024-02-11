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


  
