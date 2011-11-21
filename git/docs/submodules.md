## submodules

----------------

### Set up the submodule for the first time:
	[~]$  cd ~/main/
	[main]$  git submodule add git://github.com/my/submodule.git ./subm
	[main]$  git submodule update --init
	[main]$  git commit ./submodule -m "Added submodule as ./subm"

### Fetch submodules after cloning a repository:
	[~]$  git clone git://github.com/my/main.git ~/main
	[~]$  cd ~/main/
	[main]$  git submodule update --init

### Pull upstream main repo changes and update submodule contents:
	[main]$  git pull origin/master
	[main]$  git submodule update

### Pull upstream changes to the submodule:
	[main]$  cd ./subm
	[subm]$  git pull origin/master   # or fetch then merge
	[subm]$  cd ..
	[main]$  git commit ./subm -m "Updated submodule reference"

### Edit and commit files in your submodule:
	[main]$  cd ./subm
	[subm]$  edit whatever.rb
	[subm]$  git commit whatever.rb -m "Updated whatever.rb"
	[subm]$  cd ..
	[main]$  git commit ./subm -m "Updated submodule reference"

### Push your submodule changes to the submodule upstream:
	[main]$  cd ./subm
	[subm]$  git push origin master