# setting up your environment 

## install [atom editor](https://atom.io/)

## install [nvm](https://github.com/creationix/nvm)
This is the node.js version manager, it lets you install different versions of node.  Older libraries only support legacy versions and sometimes there are bugs unless you are running a highly specific release (ex 4.3.1), it's just something you live with.  It's also nice to check out what's going on in future releases.

## install node v4
`nvm install v4`

## git basics 

### initial setup
```bash
# make a new directory 
mdkir my-project
cd my-project

git init
npm init 

# create an empty file that will hold our code
touch index.js

# add the empty file and the file created by npm (package.json)
git add index.js 
git add package.json

# commit the code to the branch (master)
git commit -m 'my first commit'
```
```
# go create a github repository
# do not add a README.md
# get to the point that looks like this
```
![](git setup.png)

```
# take your git remote URL, looks like this - git@github.com:billautomata/my-project.git 
# add the remote URL to your project as the origin
# now when you run "git push" - it sends the data to github, a website

git remote add origin git@github.com:billautomata/my-project.git

git push -u origin master
```

### when you make big updates and want to save them using git

```
git add index.js 
git commit -m 'pushed elements to array'
git push origin master 
```

## npm basics 
npm is the package manager for node.  It is how you install your dependencies and tools.

```
# to install a package 
nvm use 4                       # if you haven't already
npm install --save bignum
# this modifies package.json 
git add package.json
git commit -m 'updated dependencies'
git push origin master 
```

## add some code to your `index.js`
```
echo 'console.log(Date.now()' >> index.js
```

## task runner 
A very useful tool is a task runner called `supervisor`.  It 
```
nvm use 4                       # if you haven't already
npm install -g supervisor
```
The `-g` flag installs the tool as a command line application.

```
cd my-project
supervisor -n exit index.js
```

Now when you save `index.js` the program should restart and run again, very handy!  The `-n exit` flag makes the program not restart on exit.
