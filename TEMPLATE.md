### 该仓库作为ansible-playbook模板使用

Playbook 主体结构
  - group_vars:组变量
  - roles:角色
  - main.yml : playbook入口文件

group_vars 结构
 - all.yml: 组变量

变量注意事项:
  1. 变量优先级 -e 选项指定的变量 > group_vars > inventory 主机清单中定义的变量 > play剧本中vars
  2. roles中的变量修改使用优先级覆盖,使用-e参数以及group_vars,保持roles变量默认
  3. remote_user 变量 默认root,为了适应aws和azure,使用-e覆盖[-e remote_user=ubuntu]

common 和 final 默认是空文件夹 运行是会从GitHub上clone下来,common 和 final 已经clone 则会更新,以保持最新

**play编写尽量使用模块,少用shell,command等模块**

*目录结构说明:*

.github 用于存放 GitHub Actions 配置
   
docs 用于存放文档
   
  
roles 用于存放role目录
   
vars 存放变量

   
ansible.cfg 项目配置
 > 注意: 由于在Centos7中YUM/Dnf 等包管理工具没有获得python3模块的支持 interpreter_python需要指定python2为解析器;Ubuntu18.04/Centos8指定使用Python3作为解析器,如果项目需要考虑Ubuntu18.04和Centos7,优先将解析器设置为python2;目前发现 docker_compose modules 需要python3,如果多系统支持 docker_compose modules 考虑使用 shell modules实现
    
main.yml Playbook入口
   
requirements.yml  依赖文件,存放所需role仓库地址
 > 将项目需要的 role 仓库地址写入该文件



*注意:*

roles 目录内模块化的role保持默认 role_xxx的命名,该项目所需要的编写的role 直接以项目名称命名以示区分
