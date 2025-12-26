

bug:

1. 配置通知的时候，第一次保存不成功，需要重新配置

2. 定时任务没生效，可以配合脚本更新，见文档下方



## 一键部署脚本

```
curl -sS -O https://raw.githubusercontent.com/woniu336/open_shell/main/save_kua.sh && chmod +x save_kua.sh && ./save_kua.sh install
```



常用命令

```

## 启动

./save_kua.sh start

## 停止

./save_kua.sh stop


## 帮助

./save_kua.sh -h
```


## 定时任务

追更：

```
(crontab -l 2>/dev/null; echo "0 8,12,20 * * * cd /root/auto-save-kua && /usr/bin/python3 quark_auto_save.py >> /root/auto-save-kua/simple_admin/cron.log 2>&1") | crontab -
```

查看日志
```
tail  /root/auto-save-kua/simple_admin/cron.log
```

定时清理追更日志：

```
(crontab -l 2>/dev/null; echo "0 3 * * * cd $HOME/auto-save-kua && /usr/bin/python3 clean_log_simple.py 2>&1 | logger -t save_kua") | crontab -
```

验证是否添加成功

```
crontab -l
```

<br>