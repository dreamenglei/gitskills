# merge 和 rebase  

`$ git merge <branchname>`  
合并branchname到当前分支  
所以运行前要用checkout 切换到要被并入的分支   
***
`$ git rebase <branchname>`  
branchname为变基操作的目标基底分支  
将当前分支中的修改变基到branchname分支上  
变基后历史记录中先是branchname分支,后是当前分支  
[看图37的名字](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%8F%98%E5%9F%BA)  
[另一个例子](https://www.jianshu.com/p/f23f72251abc)
___
`$ git rebase [basebranch] [topicbranch]`  
可以直接将特性分支变基到目标分支上,即  
`$ git rebase master server` 等价于下面两条   
`$ git checkout server`  
`$ git rebase master`  
这样执行下来，将server中的修改变基到master上,  
server中的代码被放到了master后面  
[图42](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%8F%98%E5%9F%BA#rrbdiag_h)  
说法有：当前分支(server)变基到目标分支(master)  
历史记录中目标分支在前，当前分支在后  

# 综述  
`$ git rebase <目标分支>  <当前分支>`等价于  
`$ git checkout <当前分支>`  
`$ git rebase <目标分支>`  
**历史记录中目标分支在前，当前分支在后**
![图片示例](https://git-scm.com/book/en/v2/images/interesting-rebase-4.png)  
上面这个例子就是`$ git rebase master server`的结果
       
