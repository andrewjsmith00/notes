## Version Control Systems
Imagine you are working on a large project with a team to deliver a solution to your client. Each team member is working on different components where you might be overlapping elements of work. Every time that you meet, you spend hours discussing what changes were made and how to best merge them together as you all have different versions of the same software. When things go wrong, there's also no solution as everyone then needs to find the problem to keep working.

These exact problems led to the creation of version control systems (VCS). Version Control Systems track changes to files for the purpose of retrieving specific versions later if required. This means you can changes files (or entire projects) back to previous versions, see what changes have been made over time and who made them allowing you to recover from failures easier.

There are many ways to control the versions of your files and you may be working with a version control system without even realising.

The most simple version control system is as simple as saving files multiple times where each file is a different version (*think like `Report_FINAL_V2.docx`*). This is simple but you might not be keeping time for each version to know when it was created meaning you might get confused and edit the wrong version, additionally there is no clear record of changes between versions. 

When you are working in a team, you might struggle as you need to ensure everyone has the same versions and you still need to coordinate your changes together, and if someone loses their work, then everyone is impacted.

To overcome part of this problem, more advanced version control systems were developed. These systems would provide version control systems by tracking files and the difference between versions. When a specific version was required, the system could recreate it by combining all version differences up to that point in time. 

When people needed to collaborate, a single server would exist where all files existed and developers could "check out" files from that central location to work on before putting their changes to the central server.

![[cvs.drawio.png]]

This works better, but there's still a problem. What happens if the server goes down or files on the server are lost? Now we've lost our work without a reliable backup

So then how do we solve this?

This is where Distributed Version Control Systems (DVCS) come into play. Rather than checking out a file from a point in time, DVCS will check out the entire project including all of the history of the files. This means every developer has a full backup of the project in the case that the server dies.

![[dvcs.drawio.png]]


## Git
Git is a distributed version control system created by the Linux community that is efficient at handling large projects with non-linear development.

Git has a few differences to how it stores data compared to other version control systems. As we mentioned before, version control systems will store the difference between files for tracking their history. Git will store a 'snapshot' of your files at a point in time when a change is committed rather than a collection of the differences. Essentially, it takes a picture of what your files look like and stores it.

Since Git is distributed, it works perfectly without a connection to the server as well. Every change that you make is only reflected locally, this makes it fast and efficient for use especially if you aren't able to connect to the version control server. You can make your required changes offline and then upload them to a remote server when required.

For our problem before, Git now handles our version control, ability to roll back and ensures all of our team have a copy in case something gets lost while providing a way for us to share our work.

But how to we use Git?

In order to use Git, we need to create a 'repository'. A repository is the folder where our work is located.

To create a repository run the following command from the command line:
```bash
git init
```

which outputs something like:
> Initialized empty Git repository in /Users/andrew/learning/git-basics/.git/

This command creates the `.git` folder used to track all of our work and store our snapshots. We won't see this when we are working so we don't need to think of it for basics.


With our repository, we can now start adding files. For example, we might have the file:
```python
print('Hello World!')
```

in our repository as `main.py`.

To create a snapshot of this file, we need to add it to Git and them commit the change. We do this by running: 
```shell
git add main.py
```

which now stages the changes. Once all our changes are staged, we can commit the change by running:

```
git commit -m "Added main.py"
```

> \[main (root-commit) 9690928] Added main.py
 1 file changed, 1 insertion(+)
 create mode 100644 main.py

This creates a new commit in our repository that includes the message "Added main.py". Now if someone looks at the history of our files, they can see that the change that added our file has the message "Added main.py" to it.

It is best practice to write meaningful messages when committing changes in Git. These messages should describe what the change you are making does, such as fixing a problem or adding a feature. Meaningful messages mean that others (or yourself) who view your repository are able to get a clear understanding of what a change was and why it was made without having to completely understand the code.

### States in Git
We talked about "stage" and "commit" before but what do these mean?

Files in Git can have 3 different states. These are:
- Modified
- Staged
- Committed

A modified file is a file that has been changed but it is not yet committed into a snapshot in your Git repository.

To prepare a modified file to be committed, you have to "stage" the file first. This means you mark the file as being part of your next commit, typically with the `git add` command.

Once you have staged your files, you commit them to your Git database. This is done by running the `git commit` command. The commit process is what creates the snapshot for the purpose of version control. Without your changes being committed, they cannot be traced back or sent to a remote server.
## References
- Git - https://git-scm.com/
- GitHub - https://github.com/
- Atlassian Git - https://www.atlassian.com/git/tutorials