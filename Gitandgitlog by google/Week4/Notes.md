Intro to collaborators: collaborators play very imp role for the GitHub to find out the errors in our code. this will help us and as well as our collegues to more involving into the project.

A simple Pull Request on GitHub:
1. Forking: it is a way of creating a copy of the given repo so that it belongs to our user.
2. Pull request: it is commit or series of commits that you send to the owner of the repository so that they incorporate it into their tree

The typical Pull Request Workflow on GitHub
1. fork is created for rearrange
2. git clone forkedclone address
3. cd rearrange
4. ls -l
5. git log
6. git checkout -b add - README.md addded content
7. git commit -m 'Add a simple README.md file'
8. git push -u origin add-readme
9. creating pull request to merge to the master

Updating an pull request: 
adding some more content to previous and then commit our change it will automatically update the pull request

Squashing changes: 
the project maintainers ask us to create a single commit that includes both changes and a more detailed description than the one we submitted. interactive version called rebase -i
1. git rebase -i master
2. pick --> takes the commit and rebase them against the branch we selected 
3. squash --> the mesgs are added together and an editor 
4. git push -f --> used to push current snapshot into repo

What are code reviews:
code review means going through someone else's code, documentation or configuration and checking that it all makes sense and follows the expected patterns.

Code review Workflow:
there will be reviwers who chcks our code and comments about it. once we are done with changes we can reply to that comment then reviwer will approves for pull request

How to use code reviews in GitHub
FixUp change --> commit replaced completely by new commit ID
git push -f

Managing Collaborations: If you're a project maintainer, it's important that you are reply promptly to pull requests and don't let them stagnate. 
it is imp to understand the changes
a common strategy for active software projects is to use an issue tracker. This is a super useful too
IRC channels, Slack channels, telegram groups

Tracking Issues:
Issue tracker --> tells us the tasks that need to be done, the state they're in and who's working on them. 
Bug Tracker --> Bugzilla
these issues have id using this id we can close automatically and merge to the master
eg: Closes: #id --> this closes that issue if we specify during commiting the changes

Continuous Intrgration: A continuous integration system will build and test our code every time there's a change.
Once we have our code automatically built and tested, the next automation step is continuous deployment which is sometimes called continuous delivery or CD.
Continuous deployment means the new code is deployed often. The goal is to avoid roll outs with a lot of changes between two versions of a project and instead do incremental updates with only a few changes at a time. This allows errors to be caught and fixed early.
Typical configurations include deploying a new version whenever a commit is merged into the main tree or whenever a branch is tagged for release. There's a large world of tools and platforms related to CICD which is what the whole system is usually called. --> jenkins , travis
CICD concepts: 
1. Pipelines specify the steps that need to run to get the result you want. For a simple Python Project, the pipeline could be to just run the automated tests.
2. artifacts. This is the name used to describe any files that are generated as part of the pipeline. This typically includes the compiled versions of the code but can include other generated files like PDFs for the documentation or OS specific packages for easy installation. 
strategies 
1. to do this, like exchanging SSH keys or using application specific API tokens. For some pipelines,
