Git 学习
============

### **`git remote -v`** 获取版本库地址信息

代表的是源, 提交与拉取都是从这个地址

当然我们也可以从设置修改它, 以便决定我们以什么样的方式提交

```git
    git remote -v   // 获取版本库地址信息

    // 输出
    origin https://github.com/sursir/Note.git (fetch)
    origin https://github.com/sursir/Note.git (push)
    ...
```
### **`git remote rm origin` | `git remote add origin GIT_ADDR`** 修改源

先删除, 然后添加新源

```git
    git remote rm origin
    // 删除源
    git remote add origin git@github.com:sursir/YSL.js.git
    // 添加 `以SSH方式提交的` 源
```

### **`git push origin master`** 提交, [指定*源*与*分支*]

指定新的源之后需要重新建立一个上传流 **`--set-upstream`**才可再次进行 `push/pull`

```git
    git push --set-upstream origin master
    // 提交到源的master分支
```

