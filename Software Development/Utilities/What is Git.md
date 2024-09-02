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

## References
- Git - https://git-scm.com/
- GitHub - https://github.com/
- Atlassian Git - https://www.atlassian.com/git/tutorials