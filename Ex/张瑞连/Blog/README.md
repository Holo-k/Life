### 转义后域名:
xn--e1Tu68Bp7T.xn--6qQ986B3xL


### Nginx开启SSL
- https://blog.csdn.net/re_xue/article/details/138003534
- https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-22-04
- https://linuxbeast.com/blog/how-to-secure-nginx-with-lets-encrypt-on-ubuntu-22-04/
- https://segmentfault.com/a/1190000042608121

命令
``` bash
sudo certbot --nginx -d xn--e1Tu68Bp7T.xn--6qQ986B3xL -d www.xn--e1Tu68Bp7T.xn--6qQ986B3xL --email tianki.tsai@outlook.com
```

### Hexo 显示IPC或者NPC
在layout/includes/footer.pug 添加如下代码
``` pug
  if theme.ICP.enable
    .icp
      a(href=theme.ICP.url)
        if theme.ICP.icon
          img.icp-icon(src=url_for(theme.ICP.icon))
        span=theme.ICP.text
  if theme.NSP.enable
    .icp
      a(href=theme.NSP.url)
        if theme.NSP.icon
          img.icp-icon(src=url_for(theme.NSP.icon))
        span=theme.NSP.text
```
_config 添加如下配置
``` yaml
# --------------------------------------
# Footer Settings
# --------------------------------------
footer:
  owner:
    enable: true
    since: 2024
  custom_text:
  # Copyright of theme and framework
  copyright: true

ICP:
  enable: true  # 是否启用ICP
  url: https://beian.miit.gov.cn  # 点击后的链接地址
  text: 粤ICP备2024326460号  # 备案号
  icon:    # 图标

NSP:
  enable: true   # 是否启用NSP
  url: http://www.beian.gov.cn/  # 点击后的链接地址
  text: 京公网安备 xxxxx号    # 公安备案号
  icon: http://www.beian.gov.cn/img/new/gongan.png  # 图标

```

### 更改源

- cdn.jsdelivr.net-->fastly.jsdelivr.net