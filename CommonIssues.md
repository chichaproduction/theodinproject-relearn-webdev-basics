# Common Issues
A website with all my TOP learning and experiences while refreshing and relearning Website Development




## 🚀 GIT
###  Changing folder location:
We need to check if folder still has .git which is the git init used. 
Use ls -a to see even hidden folders. 

#### If no .git found
1. Initialize the project
git init 

2. Connect to the Repository
git remote add origin [YOUR_REPO_URL]

3. Pull the repository to update or check for conflicts
If pull is being refused, it's because your history does not match witch the history recorded. 
You need to forcefully pull repository files to your local by:

git pull origin [branch] --allow-unrelated-histories

4. Clean and Merge online and local
Update the files to its most latest updates,
and finally check for conflicts to every file. 

5. Push a Merged and Updated files.
git push origin [branch]


#### If .git is found
1. Verify connection
git remote -v

Some lines will show if its connected
Nothing will show if its not

2. If not connected use 
git remote add origin [YOUR_REPO_URL]

3. IF connected just use 
git pull origin [branch]




# 🛠️ Tools to use
* Check if local is connected to remote
git remote -v

* CSS
* JS
