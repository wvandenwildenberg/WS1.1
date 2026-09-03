# Branching and merge conflicts

Let's practice branching, merging, pull requests and conflicts with a crossword puzzle. This exercise is not about solving the crossword, but about practicing with GitHub features. Most of this could be done locally too, but we will practice with GitHub to mimic a real-world scenario where you collaborate with others and use pull requests to propose changes and give feedback. Locally, the notion of a pull request doesn't exist, but you can still merge branches into each other directly.

## Task 1 Open crossword file on GitHub
1. Go to the repository of this workshop assignment on GitHub
2. Click on the file `crossword.md` to open it
3. Click on the pencil icon in the top right corner to edit the file
4. Click on 'soft wrap' in the top right corner to disable and select 'no wrap' to disable word wrap
5. Click on 'Preview changes' to see the rendered version of the markdown file

## Task 2 Edit crossword

Fill in horizontal word 24 replacing some of the `-` in the table in `crossword.md`.

## Task 3 Commit your changes to a separate branch

Click the green `Commit changes`, but instead of the default branch, create a new branch (e.g. 'word1') for this commit and start a pull request.

Your commit history now should look like this:

![Git history](https://github.com/TUDelft-MUDE/source-files/raw/main/file/mermaid-diagram-WS1_1_2.png)

Check your visualization of this commit history in VS code. To see all the branches, make sure to select 'all' as history item reference:

![Git history](https://github.com/TUDelft-MUDE/source-files/raw/main/file/git_history_vs_code_all.jpg)

## Task 4 Create pull request

Now you're automatically send to the screen 'open a pull request'. Here you can give some description (for other to see what you've done) and the changes are shown. Click the green 'Create pull request' 

Note that this pull request only contains one commit now, but we can add more commits to this branch which are all added to this pull request too. Furthermore, when doing this locally, there's no option for a pull request (because there's no one else on your local computer to give you feedback). In that case, you can still merge one branch into another directly and push those changes to the remote.

## Task 5 Edit the crossword again

Now let's edit the crossword again, with horizontal word (25). Therefore make sure to open the file again on 'main' branch. This word is on another line, so it won't cause a merge conflict with the previous word.

## Task 6 Commit your changes to a separate branch

Again, click the green `Commit changes`, create a new branch (e.g. 'word2') for this commit and start a new pull request.

Your commit history now should look like this:

![Git history](https://github.com/TUDelft-MUDE/source-files/raw/main/file/mermaid-diagram-WS1_1_3.png)

## Task 7 Merge 'word1' into 'main'

Now, let's merge the first pull request (word1) into main. Open the pull request for word1. Under 'Files changes' you can see the changes you made. You can also add comments here if you want to give feedback to yourself or others. If you're happy with the changes, scroll down and click 'Merge pull request' to merge it into main.

Your commit history now should look like this:

![Git history](https://github.com/TUDelft-MUDE/source-files/raw/main/file/mermaid-diagram-WS1_1_4.png)

## Task 8 Add a conflicting change

Now, let's add a conflicting change, which will cause a merge conflict later on. Open the file again on 'main' branch and edit the vertical word 19 which intersects with the horizontal word 25. Note that you should see word 24 already in the file, because you merged that change into main. Commit this change to a new branch (e.g. 'word3') and start a pull request.

Your commit history now should look like this:

![Git history](https://github.com/TUDelft-MUDE/source-files/raw/main/file/mermaid-diagram-WS1_1_5.png)

## Task 9 Merge 'word2' into 'main'

Now, let's open our second pull request (word2) and merge it into main. Because this change doesn't conflict with the previous change, you can merge it without any issues, although it doesn't have all the latest changes from main yet.

Your commit history now should look like this:

![Git history](https://github.com/TUDelft-MUDE/source-files/raw/main/file/mermaid-diagram-WS1_1_6.png)

## Task 10 Try merging 'word3' into 'main'

Now let's try to merge the third pull request (word3) into main. Because this change conflicts with the previous changes, you will see a message that says 'This branch has conflicts that must be resolved'. So it's not possible to merge directly without resolving the conflicts first:

![Git history](https://github.com/TUDelft-MUDE/source-files/raw/main/file/mermaid-diagram-WS1_1_7.png)

Click on 'Resolve conflicts' to open the conflict editor. This will merge 'main' into 'word3' and will allow you to resolve the conflicts in 'word3'. You should see the conflicting lines in the file, which are marked with `<<<<<<<`, `=======` and `>>>>>>>`. The lines between `<<<<<<<` and `=======` are the changes from the current branch (word3), while the lines between `=======` and `>>>>>>>` are the changes from the main branch. You can combine them manually. After resolving the conflicts, you can commit the changes.

Your commit history now should look like this:

![Git history](https://github.com/TUDelft-MUDE/source-files/raw/main/file/mermaid-diagram-WS1_1_8.png)

Now, you can finally merge the third pull request (word3) into main, because it now contains all the latest changes from main and there are no more conflicts.

Your commit history now should look like this:

![Git history](https://github.com/TUDelft-MUDE/source-files/raw/main/file/mermaid-diagram-WS1_1_9.png)

Does it actually look like this in the VS code history graph? Check it out and make sure to select 'all' as history item reference.

> By Tom van Woudenberg, Delft University of Technology. CC BY 4.0, more info [on the Credits page of Workbook](https://mude.citg.tudelft.nl/workbook-2025/credits.html).
