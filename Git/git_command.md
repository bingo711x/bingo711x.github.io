#Git Command 
mkdir my-repo
cd my-repo
git init 
git --bare init		this is a repo only


if you git add file it's ok, if you add a filefolder if occur a error!
did not match any files known to git; you must add a file to this filefoder
then git add filefolder/
then git commit -m "mesg" filefolder/
git commit -a -m "mmm"

git branch :output the current branch name
git remote add origin ssh://totemdb@totemdb.whu.edu.cn/bingo711x/xxx/.git
here ssh address is local address

git push origin master

git clone git@github.com:bingo711x/repo
git pull origin master
git status
git add filename/.
git rm filename/.
git commit -m "mesg"
git push origin master