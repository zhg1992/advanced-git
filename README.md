# Git高级命令实战

本仓库用于练习各种Git的高级命令：

请fork本仓库，并在你的fork中完成如下操作：

## git三种merge方式练习

我们有如下状态的三对分支：

```
	  A---B---C test-my-feature-1
	 /
    D---E---F test-master-1
    
	  A---B---C test-my-feature-2
	 /
    D---E---F test-master-2

	  A---B---C test-my-feature-3
	 /
    D---E---F test-master-3 
```

### merge

请在`test-master-1`分支上合并`test-my-feature-1`分支，并产生一个合并提交，如图所示：

```
	  A---B---C test-my-feature-1
	 /         \
    D---E---F---G test-master-1
```

### rebase

请在`test-my-feature-2`分支上rebase `test-master-2`分支，如图所示：

```
D---E---F---A'---B'---C' test-my-feature-2
        |
        test-master-2
```

### merge --squash练习

请将`test-my-feature-3`分支上的3个提交使用`merge --squash`方式，使得这三个提交被合并成一个提交进入`test-master-3`分支

```
	  A---B---C test-my-feature-3
	 /
    D---E---F---G test-master-3 
                |
               压扁后的提交
```

## checkout练习

请基于`v6.0`这个tag创建一个新的名为`release-6x`的分支，并将其中的bug修复掉（即删除`Product.java`中的`System.out.println("I have a bug!");`语句）

```
	      release-6x
	     /
    v5.0---v6.0---v7.0---...--- master 
```

## reset练习

请在`test-my-feature`分支上将最新的三个提交压扁成一个提交：

压扁前：

```
    D---E---F---G test-my-feature
```

压扁后：


```
    D---H test-my-feature
        |
        压扁后的提交
```

## cherry-pick练习

请在`master`分支上修复`Product.java`中的bug（即删除其中的`System.out.println("I have a bug!");`语句），并将修复bug的提交cherry-pick到`release-9x`分支上。

## revert练习

- 请在`master`分支上revert `9dfb38fc7f9a33299801c695092de3e2e8b67607` 这个提交。
- 然后再次将你刚刚revert的提交revert掉。

## bisect练习

请在`v1.0`和`v10.0`这两个代码版本之间，使用`git bisect`命令找到第一个引入bug（即引入`System.out.println("I have a bug!");`语句）的提交。
