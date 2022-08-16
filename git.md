# fork后的repo 与upstream有冲突 必须用pull request才能merge
a workaround:  
```
git branch newbranchname upstream/main
git checkout newbranchname
git checkout -b newbranchname upstaream/main
```
* withdraw a modification if there is no stash  

git checkout [--] <paths>
* restore commit stage  
git checkout [commit id] [--] <paths>


# rebase and merge
main m1 m2 m3  
feature m2 f1 f2
# commits 和 command 上的区分
```git
git merge feature
```
在main上merge分支feature

得到
main：m1 m2 m3 mergecommit   
  
feature: 应该不变

```git
git rebase main
```
在feature 上 rebase main  
得到  m1 m2 m3 f1 f2  
stash
## rabase 
```git
git rebase -i HEAD~某个整数
```
pick  
squash  
  
此时 squash的commit 会与前一个合二为一

rebase成功后记得push保证上下游的commits一致  
  
# stash
  git stash
  储存更改 回到最后一次一次commit后的状态
  git stash apply 
``` 
  git push -f origin HEAD^:master
```
  this will withdraw a push to the origin
