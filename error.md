####安装过程中遇到的问题：
###报错：Cannot find module './build/default/DTraceProviderBindings'
解决办法：npm install dtrace-provider

###hexo d 
You should configure deployment settings in _config.yml first!
解决办法：_config.yml里面的格式很重要

参考文献：
https://hexo.io/zh-cn/docs/
http://theme-next.iissnan.com/getting-started.html
http://gonghonglou.com/2016/02/03/firstblog/

http://ijiaober.github.io/2014/08/06/hexo/hexo-07/


…or push an existing repository from the command line

git remote add origin https://github.com/wxnsmile/wxnsmile.github.io.git
git push -u origin master


…or create a new repository on the command line

echo "# hello" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/wxnsmile/wxnsmile.git
git push -u origin master