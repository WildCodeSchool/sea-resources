# Merge a SEA Resource Repo

    As a participant of SEA, I want to add new resources to the existing GitHub Repo.

## Dojo

![](img/dojo_git_1.png)

### Setup

(Co) Step 1a: Create a local git repository  
(Co) Step 1b: Add a new file with at least one line to the repo  
(Co) Step 1c: Commit the new file  
(Co) Step 1d: Create a new repository on GitHub  
(Co) Step 1e: Push local changes to GitHub

(Mo) Step 2: Clone Repo (...) to local Repo  
(Mo) Step 4: Change first line of newfile.txt and commit  

(Ch) Step 3: Clone Repo (...) to new local Repo  
(Ch) Step 5: Change first line of newfile.txt and commit

(Mo) Step 6: Push changes to GitHub

(Ch) Step 7a: Push changes to GitHub  
(Ch) Step 7b: Resolve Merge Conflict  
(Ch) Step 7c: Push changes to GitHub

(RR) Step 8a: Clone repo to local repo  
(RR) Step 8b: Watch changes in file newfile.txt

### Known Issues

Q: After creating a README, I cannot connect my local Repo to the GitHub one (unrelated histories)  
A: "git pull origin main --allow-unrelated-histories"