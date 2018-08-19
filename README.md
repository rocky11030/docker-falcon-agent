# falcon_install

安装说明
========

- 由于使用./open-falcon start agent 用ansible远程执行不成功，估计是go的环境变量问题
- 使用了原来版本的control脚本控制./control start ./control stop ./control restart
  ./control status
- 替换了falcon-agent和cfg.json
- 调整监控网卡的参数，默认为cfg.json的参数为"ifacePrefix": [ ], 可以修改为"ifacePrefix": ["eth", "em", "bond"]过滤输出这几个网卡
- 加了rabbitmq的参数获取脚本和放入到/etc/cron.d/下面的cron自动执行脚本


第一步: 修改变量文件
--------------
* 修改groups_vars/all里面的变量
* 修改hosts主机变量: falcon-agent主机

第二步: 安装falcon
--------------
* 执行脚本:ansible-playbook -i hosts falcon_install_agent.yml
