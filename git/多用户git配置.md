# 多用户git配置

## 1. 生成不同用户的ssh-gen

```sh
ssh-keygen -t rsa -C "你的邮箱"
```
在之后选择名字的时候修改个不同的名字，默认为id_rsa文件，可根据用户名进行区分，例如为id_rsa_github

## 2.在github上添加对应id_rsa....pub文件的内容

## 3. 编辑~/.ssh/config文件

```sh
添加
Host github.com
    HostName ssh.github.com
    User git
    Port 443
```

其中user根据用户的不同添加不同的用户。

## 4. 验证

```sh
ssh -T git@github.com
看到
# 输出
Enter passphrase for key 'C:\Users\Administrator/.ssh/id_rsa':
Hi happyjava007! You've successfully authenticated, but GitHub does not provide shell access.
即为成功
```

## 5. 为不同项目配置不同的用户与email

```sh
为当前项目配置用户名为work
git config user.name "work"
```

