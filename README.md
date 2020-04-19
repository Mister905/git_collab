# git_collab

Common Pitfalls

** Pulling with Untracked Changes **
user 1 pushes local changes to remote
user 2 also makes local changes and tries to pull from remote
error: Your local changes to the following files would be overwritten by merge: 
git commit -am "user 2 changes"
git pull origin master - this creates conflicts
open the file that you modified - meta data has been inserted you assist in resolving the conflicts
git commit -am "Resolved conflict"
git push origin master

** Forced Pushes **
push command with a force flag
git push origin master --force  (Danger)
user 1 pushes local changes to remote
user 2 also makes local changes and tries to push to remote
failed to push some refs...the remote contains work that you do not have locally
This could have been avoided with the first tip:

TIP: Always Pull Before a Push
This is a bedrock rule. Before you try to push code out to the repository, you should 
always pull all the current changes from the remote repository to your local machine. 
Doing so will ensure that your local copy is in sync with the remote repository. Remember, other 
people have been pushing to the remote copy, and if you push before syncing up, you could end up 
with multiple heads or merge conflicts when you push.

TIP: Pull Frequently
On large teams, the central repository will continuously be changing. You should endeavor to keep 
your local machine as close to the remote repository as possible. The way to do that is to pull all 
the changes on the remote server to your local copy. You can do this as often as you like, and should 
do it frequently — at least once a day if not more.

TIP: Push infrequently
When you push, you are inflicting your changes on others. You should only do this when you know you won’t 
break the build, when you have carefully reviewed what it is that you are pushing, and when you feel that 
your local code is in a state that will be useful to others.

TIP: Commit Frequently
Many developers don’t commit often enough. They end up committing after making many changes, and their comment 
is, as a result, inadequate to describe all the changes made. Trying to review large, ponderous commits is 
irritating and counter-productive.

TIP: Create Pull Requests Infrequently
While you can merge “forward” as much as you want, you should be far more cautious in creating pull requests to 
merge your code back into the develop branch. Your organization will likely have a policy on pull requests, but 
you should take care in creating them. A pull request is asking people to look your code over with a fine-toothed 
comb, so do them with care. You should make a pull request only after your code is in a state that will result in 
a clear, discrete, and complete addition to the code base. Again, if you feel the need to use the word “and” in 
describing your pull request, it’s likely too big.

TIP: Branch Infrequently
Branch for clear reasons: features, hotfixes, etc...
