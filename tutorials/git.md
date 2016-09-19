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
    * $ **git add .** *this way you all the files and folders in the directory are tracked by git*
    * $ **git commit -m "comment-on-the-changes"** *saves an history log for the tracked files*
    * ** To commit all the files ** use flag -am instead of -m. This flag "adds" all tracked file to the commit.

* Use **git log** to see the commit history and **git show \<commit-id\>** to show the changes done in commit <commit-id>

###Remote Repository
A remote repository holds the repository in an online server so you can easily share your work, work as a team and keep a backup of the data. This remote repository can be in the cloud (like https://github.com) or in a remote machine (server).

####On Github
Github is an online repository server for Git! Git is the technology, Github is just a host/server. If you create an accout you can create repositories going to Your Profile -> Repositories -> New. Entering the repositorie's page, you can see a button of "Clone or Download". If you press it you can see two types of links:
* HTTPS: https://github.com/minhoteam-msl/workshops.git
* SSH : git@github.com:minhoteam-msl/workshops.git
This is the address of the repository in the cloud. To push one of your local repositories into a Github repository you use the push command.

* $ **git push \<remote\_repository\_address> \<branch\>**
Given the example, with master branch:
* $ **git push https://github.com/minhoteam-msl/workshops.git master**
* $ **git push git@github.com:minhoteam-msl/workshops.git**

For convenience, you can store a remote repository address in your local machine and give it an alias. You can also have multiple remotes stored for one local repository. Usually the alias is "origin".
* $ **git remote add \<alias\> \<remote\_repository\_address\>** 

Here are some useful commands for remotes:
* $ **git remote -v** *Displays all the defined remotes*
* $ **git remote remove \<alias\>** *Removes remote defined by alias*
* $ **git remote set-url add \<alias\> \<remote\_repository\_address** *Adds another url to an existing remote*

Now that you have your remotes defined you can send the local repository to the online repository using the push command.
* $ **git push \<alias\> \<branch\>**
If you defined the remote using HTTPS you will be prompted to write your username and password from github. If you used SSH, you must define SSH keys to automatically authenticate the push.   
For that, go to Your Profile -> SSH and GPG Keys -> New SSH Key. First, an SSH key needs to be generated in your local machine.
* $ **ssh-keygen -t rsa** *Press enter in every prompt*   
Your keys have been generated! Back to github!      
* Give it a name under "Title"
* On key paste the content of the key file under ~/.ssh/id_rsa.pub
* Click 'Add SSH Key'

You must be good to go, when making a push to a remote defined with the SSH link, you won't be prompted with any authenticantion procedure.

####On your own server
If you create a server in your home/work network, you must forward network requests for ports 22 to your server's ip. In your server you will have to create a remote repository as well, and you start it by creating a normal folder, adding .git in the end just for identification of the folder:
* $ **sudo apt-get install openssh-server** *Installs ssh server on machine*
* $ **mkdir \<your-repo\>.git**
* $ **cd \<your-repo\>.git**
* $ **git init --bare** *This command actually initializes a git repository in that folder*

Now, you just have to setup your remote server in the same way as for a Github remote, but using just SSH authentication. You can put the SSH keys on your server after you generate them (using ssh-keygen) by doing:
* $ **ssh-copy-id \<user\>@\<server-ip\>**
After correctly configuring the SSH authentication, just add your remote:
* $ **git remote add \<alias\> ssh://\<user\>@\<server-ip\>/path_to_repo/\<repository-name\>.git**

You are now ready to use local repositories, push data to remotes from Github and your own server !!

###Branching
Branching allows to create a bifurcation of a repository and work on that bifurcation without affecting the main branch, the master branch. This is useful when working withing a team, where different developpers can edit **DIFFERENT** files. Once the work is finished, the created branch(1) can be merged into the master branch(0), where collisions (error) might happen if some edition was done in the master branch after the branching happened or if another branch, say branch 2, edited files that were also edited in branch(1), that's why **DIFFERENT** files was said.



*MinhoTeam 2016/2017*
