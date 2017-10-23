# git 
## .gitignore
> gitignore - Specifies intentionally untracked files to ignore

### 生成
```
vim .gitignore
/// 要忽略的文件路径
：wq

```

### 删除已经提交了的文件
```
git rm -r --cached node_modules（要删除的文件名）
```