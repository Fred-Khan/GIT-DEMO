Hello world.
Added a new file.
Last line in the file.

<h2>GIT Commands:</h2>
git config --global user.name "Your Name" // Configure Name<br>
git config --global user.email youremail@domain.com // Configure email<br>
<br>
git init // start tracking current directory<br>
git add . // add all files in current directory to staging area, making them available for commit<br>
git commit -m "commit message" // commit your changes<br>
git branch -M master // specifiy the branch<br>
git remote add origin https://github.com/username/repo-name.git // add remote repository URL which contains the required details<br>
git pull origin master // always pull from remote before pushing<br>
git push -u origin master // publish changes to your remote repository<br>
<br>
<br>
<h2>How to Delete LOCAL Git repository:</h2>
Change to the project's root folder first.<br>
<h5> For Linux/MacOSX use:</h5>
rm -fr .git<br>
<br>
<h5>For Windows use:</h5>
rmdir /s .git<br>
<br>
To ensure the local git repo was deleted successfully, run:<br>
git status<br>
<em>You should get a  fatal: not a git repository error</em><br>
<br>
You can now run git init to intitialise a new git local repo.<br>
<br>
<br>
<h2>How to Delete REMOTE Git repository:</h2>
https://docs.github.com/en/repositories/creating-and-managing-repositories/deleting-a-repository<br>
1. On GitHub.com, navigate to the main page of the repository.<br>
<br>
2. Under your repository name, click Settings.<br>
<em>If you cannot see the "Settings" tab, select the dropdown menu, then click Settings.</em><br>
<br>
3. In the "Danger Zone" section, click Delete this repository.<br>
<br>
4. Read the warnings.<br>
<br>
5. To verify that you're deleting the correct repository, in the text box, type the name of the repository you want to delete.<br>
<br>
6. Click I understand the consequences, delete this repository.<br>
<br>
