# Intro to Git
+ Distribute Version Control System (DVCS)
![[Pasted image 20241024152834.png]]
+ Started in 2005
+ **Main features**: Fully distributed, Strong support for non-linear development (multiple parallel branches)

## Difference between others VCSs 

Git is no delta based VCS, instead it saves a stream of snapshots:
+ **Other VCSs**: delta based
![[Pasted image 20241024153614.png]]
	
+ **Git**: stream of snapshots, every time you commit or save the state of your project, git takes an snapshot of what all your files look like at the moment and sstores a reference to that snapshot. If files have no changed git doesn't store the file again, just a link to the previous identical file it has already stored
![[Pasted image 20241024155356.png]]

**Checksumming and Data Integrity**: almost everything is checksummed before it is stored SHA-1 calculated based on the content of a file or directory, git uses it to ensure data integrity in its db
+ thanks to this, every operations is undoable

## The Three States
+ Git has 3 main states for files: ==modified, staged, committed==, this is representend in  ==working directory (working tree), staging area, .git directory (repository)==
+ **Modified**: you have chenged the filed but you have not staged yet
+ **Staged**: you have marked a modified file in its current version to go into your next commit snapshot.
+ **Committed**: data is safely stored in your .git database
![[Pasted image 20241024160905.png]]
+ **Working Tree**: Is a single checkout of the projectm, files are pull out of the compressed .git db and placed on disk for you to use of modify
+ **Staging area (a.k.a. index area)**: file in .git dir, stores data about what will go into your next commit 

### Workflow
1. modify files in your working tree
2. selectively stage just those changes you want to be part of your next commit
3. Do a commit, which takes the files in staging area and stores that snapshot permanentely to your git directory
