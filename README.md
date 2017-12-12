# falcon_install

安装说明
========

- 此项目主要是通过ansible+docker安装open-falcon_0.2.1版本
- falcon_0.2.1.tar和mysql_5.5.tar需要手动上传
- ansible版本为2.4


第一步: 修改变量文件
--------------
* 修改groups_vars/all里面的变量
* 修改hosts主机变量: open-falcon主机

第二步: 安装mysql
--------------
* 执行脚本:ansible-playbook -i hosts falcon_install.yml --tags mysql_install

第三步: 安装falcon
--------------
* 执行脚本:ansible-playbook -i hosts falcon_install.yml --tags falcon_install
