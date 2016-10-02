# First commit

To contribute to this repo first click Fork at the right top of the projects Github page. This adds a copy of the repo to your own account. You can then clone your copy to your computer with
````
git clone https://github.com/ (your github username) /mu-cs424-f2016
````
then
````
cd mu-cs424-f2016
````
This moves you into the folder where all the Github files are held. Add your new files here, if you're not experienced with markdown you can use the Atom editor by github which has the option to add a markdown preview view under Packages>Markdown Preview.  

Make changes locally to the files/add new files then run  
````
git add -A
````
to add all files to git. Then run  
````
git commit -m "commit message"
````
to give a brief summary of what you changed. Finally run  
````
git push
````
to take the changes made locally and publish them on Github.  

Now go back to the repo on your Github and click on new pull request near the top. You should see a page detailing the changes made to current files and the new files you added locally compared to the current class repo.

# Setting up commits after the upstream has changed
If you wish to commit again and Barak's repo has changed since your fork you need to go a few extra steps

````
git remote -v
````
This should list the remote repositories linked to your local copy. Initially you should just see



````
origin	https://github.com/robertmccraith/mu-cs401-f2016 (fetch)
origin	https://github.com/robertmccraith/mu-cs401-f2016 (push)
````

We need to add Barak's copy to this list so we can merge the changes.

````
git remote add upstream https://github.com/barak/mu-cs401-f2016
````
Will add Barak's repo as a new remote called upstream.  
Running ````git remote -v```` again should result in  
````
origin	https://github.com/robertmccraith/mu-cs401-f2016 (fetch)
origin	https://github.com/robertmccraith/mu-cs401-f2016 (push)
upstream	https://github.com/barak/mu-cs401-f2016 (fetch)
upstream	https://github.com/barak/mu-cs401-f2016 (push)
````

Now we need to download a copy of Barak's repo
````
git fetch upstream
````
Then we checkout our own
````
git checkout master
````
Then we merge the changes
````
git checkout master
````

If this is successful we can run the last three steps in the first part of this tutorial to push a new commit with our local changes  
