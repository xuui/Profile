# gitlab修改root用户密码

1.使用root权限登录到服务器。
2.使用以下命令启动控制台:
   gitlab-rails console production
3.有多种方法可以查找您的用户。您可以搜索电子邮件或用户名。
   user = User.where(id: 1).first
或者
   user = User.find_by(email: 'admin@local.host')
4.现在, 您可以更改密码:
   user.password = 'secret_pass'
   user.password_confirmation = 'secret_pass'
5.不要忘记保存：
   user.save!
6.退出控制台, 然后尝试使用新密码登录。