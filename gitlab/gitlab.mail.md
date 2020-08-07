# gitlab mail send.

'hosts' need to be configured for local services

gitlab_rails['smtp_enable'] = true

## mail 配置

No ssl tls
```
gitlab_rails['smtp_enable'] = true
gitlab_rails['smtp_address'] = "xxx"
gitlab_rails['smtp_port'] = 25
gitlab_rails['smtp_user_name'] = "gitlab@xxx.com"
gitlab_rails['smtp_password'] = 123456
gitlab_rails['smtp_authentication'] = "login"
gitlab_rails['smtp_enable_starttls_auto'] = false
gitlab_rails['smtp_tls'] = false
gitlab_rails['gitlab_email_from'] = 'gitlab@xxx.com'
```

Office 365 
```
gitlab_rails['smtp_enable'] = true
gitlab_rails['smtp_address'] = "smtp.office365.com"
gitlab_rails['smtp_port'] = 25
gitlab_rails['smtp_user_name'] = "user.name@company.com"
gitlab_rails['smtp_password'] = "secret"
gitlab_rails['smtp_domain'] = "company.com"
gitlab_rails['smtp_authentication'] = "login"
gitlab_rails['smtp_enable_starttls_auto'] = true
gitlab_rails['smtp_tls'] = false
```

QQ exmail (腾讯企业邮箱) 
```
gitlab_rails['smtp_enable'] = true
gitlab_rails['smtp_address'] = "smtp.exmail.qq.com"
gitlab_rails['smtp_port'] = 465
gitlab_rails['smtp_user_name'] = "xxxx@xx.com"
gitlab_rails['smtp_password'] = "password"
gitlab_rails['smtp_authentication'] = "login"
gitlab_rails['smtp_enable_starttls_auto'] = true
gitlab_rails['smtp_tls'] = true
gitlab_rails['gitlab_email_from'] = 'xxxx@xx.com'
```

## mail 测试

在GitLab服务器上，执行 gitlab-rails console 进入控制台。 然后在控制台提示符后输入下面的命令 发送一封测试邮件：

```
Notify.test_email('xxx@xxx.com','Message Subject','Message Body').deliver_now
```

or 示例
```
Notify.test_email('收件人邮箱', '邮件标题', '邮件正文').deliver_now
```
