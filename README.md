


bug:

1. 配置通知的时候，第一次保存不成功，需要重新配置

2. 定时任务没生效，可以配合脚本更新，见文档下方


<br>

需要安装python，开放5006端口



**一键部署脚本**

```
curl -sS -O https://raw.githubusercontent.com/woniu336/open_shell/main/save_kua.sh && chmod +x save_kua.sh
```

**首次安装**

```
./save_kua.sh install
```

其他命令

```

## 启动

./save_kua.sh start

## 停止

./save_kua.sh stop


## 重启

./save_kua.sh restart  
```



访问地址: http://localhost:5006



项目路径: /root/auto-save-kua




日志文件: /root/auto-save-kua/simple_admin/app.log


## 定时追更任务

```
(crontab -l 2>/dev/null; echo "0 8,12,20 * * * cd /root/auto-save-kua && /usr/bin/python3 quark_auto_save.py >> /root/auto-save-kua/simple_admin/cron.log 2>&1") | crontab -
```

查看日志
```
tail  /root/auto-save-kua/simple_admin/cron.log
```

<br>