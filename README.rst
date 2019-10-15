Learn Packer Notes
==============================================================================

- Q: Packer 解决了什么问题?
- A: Packer 能通过定义一个模板, 生成多个平台的虚拟机镜像 (VM Image).

- Q: 如果不用 Packer, 如何生成虚拟机镜像?
- A:
    - VirtualBox: 很多 Linux 开发者都是从使用 `VirtualBox <https://www.virtualbox.org/>`_ 开始使用虚拟机的. 简单来说你需要从网上下载一个基础镜像, 然后用 VB 建立一个 虚拟机 (VM), 然后在 VM 上安装一些软件之后, 关闭该 VM. 最后将该 VM 打包成一个 ISO Image 发布到网上. 以后你就可以直接用这个镜像启动虚拟机了.
    - AWS EC2: 如果你是 AWS EC2 的用户, 你需要 Launch 一个 EC2, 然后再 EC2 上安装一些软件之后, 停止该 EC2, 然后在 Console 点击 Build Image 生成一个 AMI (Amazon Machine Image).

- Q: 如果用 Packer, 如何生成虚拟机镜像?
- A: 你可以将安装软件的过程写在一个 Shell Script 脚本中, 然后在 Packer Template 中指定 源镜像, 和安装过程脚本. 然后指定 AWS Access Key 之后, 就可以用 ``packer build template.json`` 自动启动 EC2, 执行安装过程脚本, 打包 AMI, 关闭 EC2.
