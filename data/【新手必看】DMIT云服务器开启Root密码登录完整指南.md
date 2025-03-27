
**重要提示**：DMIT云服务器默认禁用Root密码登录是出于安全考虑。若您坚持启用密码登录，请务必设置高强度密码（建议12位以上，包含大小写字母、数字和特殊符号）。

DMIT作为国际知名云服务商，以其高性能网络和稳定服务著称。近期黑五促销期间，许多用户选择了DMIT的云服务器方案，但部分用户对SSH密钥登录方式不太适应。

👉 [【点击查看】2025年最新DMIT优惠码及特价云服务器方案汇总](https://bit.ly/dmit_coupon)

1. **获取登录凭证**：
   - 通过DMIT控制面板的"访问"选项下载密钥压缩包（仅能下载一次，请妥善保管）
   - 解压后获得三个文件，其中`id_rsa.ppk`将用于首次登录

2. **必备工具**：
   - PuTTY客户端（建议从[官网](https://www.putty.org/)下载正版）


1. 打开PuTTY，在"Connection > SSH > Auth"界面加载`id_rsa.ppk`文件
2. 返回Session界面输入服务器IP地址
3. 连接后以root用户名登录（无需密码）

bash
nano /etc/ssh/sshd_config

找到并修改以下参数：
bash
PermitRootLogin yes
PasswordAuthentication yes

保存修改（Ctrl+O）并退出（Ctrl+X）

bash
service ssh restart

bash
passwd

注意：
- Linux系统输入密码时不会显示字符
- 需重复输入两次确认
- 出现"password updated successfully"即表示成功

1. 定期更换密码（建议每90天一次）
2. 启用防火墙限制SSH访问IP
3. 考虑使用Fail2Ban防止暴力破解

DMIT云服务器提供：
- 全球优质网络节点
- 99.9%运行时间保障
- 即时开通服务
- 专业级DDoS防护

[立即获取DMIT最新优惠方案](https://bit.ly/dmit_coupon)

Q：修改后仍无法密码登录？  
A：请检查是否遗漏了`service ssh restart`步骤

Q：忘记root密码怎么办？  
A：可通过控制面板的VNC功能重置

Q：其他Linux系统是否适用？  
A：Ubuntu/CentOS等系统操作类似，仅服务重启命令可能不同
