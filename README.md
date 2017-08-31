# testFork

git clone 之后才想要提交代码怎么办？

使用这个：git clone git@github.com:yhding/testFork.git 我们可以down

现在问题来了，接下来我们该如何提交代码？
  使用“git remote add origin git@github.com:yhding/testFork.git” 
  还是使用“git push origin master”。

发现都不能使用。原因来了：
  我们是通过 git clone命令来将该仓库下载到本地的，这个时候的remote其实是原项目地址，我们当然是不能直接git push的，因为我们并没有这样的权限。

我们怎么做呢？
  git remote remove origin 切断当前的连接
  添加新的连接
  git remote add origin git@github.com:yhding/testFork.git
  然后就发现可以使用add和commit了

期间可能出现的问题：
1、“Please tell me who you are”？
  你需要设置你的name和email
  git config user.name yourname
  git config user.email youremail@example.com
2、需要ssh连接
   ssh-keygen -t rsa -C "youremail@example.com"
   具体可以参考这里：
   https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001374385852170d9c7adf13c30429b9660d0eb689dd43a000
