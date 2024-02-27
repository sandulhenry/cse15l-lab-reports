# Lab Report 4 - VIM
## CSE 15L W24 - Sandul Henry

### Step 4:
![4](/lab4_photos/Screenshot 2024-02-23 171220.png)
* Type `ssh user@ieng6.ucsd.edu`. Then hit `<enter>`. You should be logged in automatically.

### Step 5:
![5](/lab4_photos/
* Type `git clone [repository ssh]` and then hit `<enter>`. This clones the repository.
* Change into the cloned directory with `cd lab7` and `<enter>`.

### Step 6. 
* Run the tests with `bash test.sh` and hit `<enter>`. See how they initially fail.

### Step 7.
* fix the code by entering the text editor with `vim ListExamples.java <enter>`. You can use tab to autocomplete.
* Jumpt to the line with the mistake with by typing `:44 <enter>` in normal mode. Move the cursor over by typing `<l><l><l><l><l>` and delete the character with `x`. Now type `<i> 2 <ESC>` to make the correction.
* Save and exit vim with `:wq <enter>`

### Step 8.
* Rerun the tests with `bash test.sh <enter>`. They should no pass without a 2 successes.

### Step 9. 
* To commit and push, begin by typing `git add ListExamples.java <enter>`.
* Now type `git commit <enter>` and then type a commit message. This should open vim to type a message. I wrote `<i> fixed ListExamples.java code <ESC>` and saved by typing `:wq <enter>`
* Now type `git push` to update the repository on github.com. You can check the website to see the changes!

