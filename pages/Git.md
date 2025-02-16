level:: 2
comment:: version control system
type:: language

-
- [[Intro]]
  collapsed:: true
	- Version control system
		- centralized
		- distributed
			- copy of the project
			- no need to central server
	- DB: repositories
	- Revert back to prev version
	- track history, work togather
	- Branching and merging
- Use git
  collapsed:: true
	- cmd line
	- code editor and IDE
	- GUI
		- GitKraken
		- with limitations
- [[Architecture]]
  collapsed:: true
	- Working directory/ Local repository
	- Staging area
	- Remote Repository (GitHub)
- [[CMD]]
  collapsed:: true
	- Initialization
		- git --version
		- git config
		  collapsed:: true
			- level
			  collapsed:: true
				- system
				- global
				- local
			- setting
			  collapsed:: true
				- user.name
				- user.email
				- git config --global core.editor "notepad"
				- git config --global -e // edit config file
				- core.autocrlf //for CR LF
				- diff.tool vscode
				- diff.too.vscode.cmd
		- git --help
		  collapsed:: true
			- big help
		- git -h
		  collapsed:: true
			- Short help
		- git init
		  collapsed:: true
			- master/main branch
		- git clone
		  collapsed:: true
			- git clone https://github.com/account/repo.git // create clone of the public repo in local machine
			- git clone http https://token@github.com/account/repo.git // create clone of the private repo in local machine
		- git add // staging area, index
		  collapsed:: true
			- git add . // all files recursively
		- git commit // snapshot
		  collapsed:: true
			- id, message, date time, author, data
			- compress, don't store duplicate data
			- git commit -m "message" // one line message
			- git commit // a descriptive message
			- Best practices
			  collapsed:: true
				- no too big, too small
				- record checkpoints
				- Logically separate works
				- meaningfull commit messages
				- wording: tense
			- git commit -a -m  // Skip staging area, not recommended, -a: all without staging
		- git status // staging area and local repo diff
		  collapsed:: true
			- git status -s // short status
			  collapsed:: true
				- M // modified
				- A // added
				- ? // not added
		- git push // push from local repo to github
		  collapsed:: true
			- git push -u origin main // push to main branch
		- git pull // pull from github to local repo
		- git remote -v // view remote branch
		  collapsed:: true
			- git remote add origin https://tokenurl.git // origin branch
			- git remote remove origin // remove connection
			- git branch -M main // change name of the branch to "main" from master
		- git pull // pull from github to working dir
		- git fetch origin main // pull from github to local repo
	- branches
		- info
		  collapsed:: true
			- Independent line of development
			- Pointers to commits
			- main // github root branch
			- master // git root branch
			- HEAD // pointing to the name of the branch // ref to commit
		- git checkout origin/main // check to other branches
		- git switch branchName // switch branches
		- git merge // pull from local repo to working dir, merge branches
		  collapsed:: true
			- git merge branchName // should be in diff branch
			  collapsed:: true
				- Fast forward merge // Auto commit, auto merge
				- no conflict // auto merge, auto commit
				- merge conflict // error, fix conflicts, manual commit
		- git branch // return branch names
		  collapsed:: true
			- git branch branchName // create new branch
		- git branch -m newName // rename the current branch, should be in the branch
		- git branch -d branchName // Delete branch, should be in other branch
	- basic 01
		- git ls-files // git ls in staging area
		- git rm // rm files from staging area and working dir
		- git rm --cached // rm files from staging area
		- git mv // mv files from staging area and working dir
		- .gitignore // ignore files/dir
		  collapsed:: true
			- logs/
			- main.log
			- *.log
	- basic 02
		- git diff --staged // diff prev commit and staging area
		  collapsed:: true
			- git diff // diff staging area and working dir
			- git difftool // diff in gui
		- git log // commit history
		  collapsed:: true
			- git log --oneline // short description
			- git log --oneline --reverse //
		- git show
		  collapsed:: true
			- git show <comitId> // git diff
			- git show <fileId> // file contents
			- git show HEAD // git diff
			- git show <>:<fileName> // complete snapshot of the files
		- git ls-tree HEAD
		  collapsed:: true
			- file: blob
			- dir: tree
		- git clean // remove untracked files(files not in staging area) from local dir
	- Undo changes
		- git restore // Restoring working dir to last commit in local repo
		  collapsed:: true
			- git restore --staged <fileName> // put last commit in local repo in staging area
			- git restore <fileName> // put staging area to working dir
			- git restore --source=HEAD~1 fileName // restore file(working dir) to previous version commit
		- git reset (not recommended)
		  collapsed:: true
			- git reset <commitId> // remove commit upto commitId from local repo, working dir remain untouched, commit id not remain in git log
			- git reset <commitId> --hard // remove commit upto commitId from local repo, working dir also reset to commitId, not recoverable,  commit id not remain in git log
		- git revert
		  collapsed:: true
			- git revert <commitId> // working dir and local repo to commitId-1, commit id remain in the git log
	- Intermidiate 01
	  collapsed:: true
		- git stash // Preserve changes without commit
		  collapsed:: true
			- git stash pop // getting preserved changes back
			- git stash apply
		- .gitignore // List of files or dir to ignore by git
		- Pull request // Merging one branch to main branch
		  collapsed:: true
			- with multiple users
			- git hub feature
			- all branches on one user
			- needs permission
		- fork // Create copy of repo on own github account
		  collapsed:: true
			- with multiple users
			- git hub feature
			- no need permission
		- Github Actions // Automate Build, test, and deployment pipeline
		  collapsed:: true
			- CI/CD
			- Triggering event, Runner, Jobs
			- YAML file
	- git tree
	  collapsed:: true
		- git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)' --all
		- git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(auto)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)'
	- Common workflow patterns
	  collapsed:: true
		- Single branch workflow
		- Branch based development
	-
	- [[Question]]
	  collapsed:: true
		- git checkout vs git switch
- Common cmd list
	- Delete a file from previous commits
		- git filter-branch -f --index-filter 'git rm --cached --ignore-unmatch <file_name>' -- --all
			- git filter-branch -f --index-filter 'git rm --cached --ignore-unmatch pages/Cloudflare.md' -- --all
			- Rewrite the entire commit history of the repository.
			- Remove the specified file from each commit in the repository, but keep the file working directory
			- Apply the changes to all branches in the repository.
		- pages/Cloudflare.md
		- git push
		- git push --force --all
			- update the remote repository with the rewritten commit history
- Credentials
  collapsed:: true
	- github token
	  id:: 672df2e5-7ff2-441c-addd-ae59c5769ef9
	- github logseq
		- https://github.com/saptarshibhosale604/Logseq.git
		- git remote add origin https://token@github.com/saptarshibhosale604/Logseq.git
		- Token03 #Encrypted
			- expiry 60 days
			- admin repo
			- 101105116094120052114085105119078119075108126117120052115083080068112120110070106064058054103107051049052123096106119049
		- branch
			- main // operate from home
			- companyMain // operate from company
				- git push -u origin companyMain
	- github project02
		- token01
			- 101105116094050069051088052072048109052089069089067074074066049052125066116071097070106082053085087112054081113091083107 #Encrypted
			- Admin permissions
		- https://github.com/saptarshibhosale604/project02
		- git config --global user.email "saptarshibhosale604@gmail.com"
		- git config --global user.name "saptarshibhosale604"
		- git remote add origin https://<token01>@github.com/saptarshibhosale604/project02.gi
		- git branch -M main
		- branch
			- main // operates from company pc