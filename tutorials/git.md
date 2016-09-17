#Tutorial for Git&Github workshop

###Life of a file in Git
![Life of a file in Git](http://wiki.eclipse.org/images/0/03/Egit-0.9-lifecycle-file.png)

###Local Repository
A local repository holds the data and the whole history of the tracked files, along with the commits and log files.

* Creating a local repository
    * $ **cd \<folder that you want\>**
    * $ **mkdir \<name-of-the-repository\>**
    * $ **cd \<name-of-the-repository\>**
    * $ **git init** *initialized git repository (.git hidden folder)*

* Use **git status** to enquire the state of the repository

* Adding files to repository and saving their history
    * $ **git add \<name-of-the-file\>** *tells git to track the history of that file*   
    * $ **git commit -m "comment-on-the-changes"** *saves an history log for the tracked files*
    * ** To commit all the files ** use flag -am instead of -m. This flag "adds" all tracked file to the commit.

*MinhoTeam 2016/2017*
