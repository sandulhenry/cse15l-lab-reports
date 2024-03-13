# Lab Report 4 - VIM
## CSE 15L W24 - Sandul Henry

### Step 4:
![4](/lab4_photos/Screenshot 2024-02-23 171220.png)
* Type `ssh s7henry@ieng6.ucsd.edu`. Then hit `<enter>`. You should be logged in automatically.

### Step 5:
![5](/lab4_photos/Screenshot 2024-02-23 172144.png)
* Natigate to github and copy the ssh address of the repository, and copy it with `<Ctrl> + <C>`. 
* Type `git clone <Ctrl + V>` and then hit `<enter>`. This clones the repository, after you paste your ssh. 
* Change into the cloned directory with `cd lab7` and `<enter>`.

### Step 6. 
![6](/lab4_photos/Screenshot 2024-02-27 112334.png)
* Run the tests with `bash test.sh` and hit `<enter>`. See how they initially fail.

### Step 7.
![7](/lab4_photos/Screenshot 2024-02-27 112447.png)
* fix the code by entering the text editor with `vim ListExamples.java <enter>`. You can use tab to autocomplete.
* Jumpt to the line with the mistake with by typing `:44 <enter>` in normal mode. Move the cursor over by typing `<l><l><l><l><l>` and delete the character with `<x>`. Now type `<i> 2 <ESC>` to make the correction.
* Save and exit vim with `:wq <enter>`

### Step 8.
![8](/lab4_photos/Screenshot 2024-02-27 111051.png)
* Rerun the tests with `bash test.sh <enter>`. They should now pass without a 2 successes.

### Step 9. 
![9](/lab4_photos/Screenshot 2024-02-27 111515.png)
* To commit and push, begin by typing `git add ListExamples.java <enter>`.
* Now type `git commit <enter>` and then type a commit message. This should open vim to type a message. I wrote `<i> fixed ListExamples.java code <ESC>` and saved by typing `:wq <enter>`
* Now type `git push <enter>` to update the repository on github.com. You can check the website to see the changes!

