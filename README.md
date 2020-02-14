# Windows L2TP/IPsec VPN Problems

By default, Windows Vista and the Windows Server 2008 operating system do not support Internet Protocol security (IPsec) network address translation (NAT) Traversal (NAT-T) security associations to servers that are located behind a NAT device. Therefore, if the virtual private network (VPN) server is behind a NAT device, a Windows Vista-based VPN client computer or a Windows Server 2008-based VPN client computer cannot make a Layer Two Tunneling Protocol (L2TP)/IPsec connection to the VPN server. This scenario includes VPN servers that are running Windows Server 2008 and Microsoft Windows Server 2003.

Because of the way in which NAT devices translate network traffic, you may experience unexpected results when you put a server behind a NAT device and then use an IPsec NAT-T environment. Therefore, if you must have IPsec for communication, we recommend that you use public IP addresses for all servers that you can connect to from the Internet. However, if you have to put a server behind a NAT device and then use an IPsec NAT-T environment, you can enable communication by changing a registry value on the VPN client computer and the VPN server.

This affects: Windows Vista, Windows 7, Windows 8, Windows 10 and Windows Server 2008.

Ref:
* [Microsoft Support](https://support.microsoft.com/en-za/help/926179/how-to-configure-an-l2tp-ipsec-server-behind-a-nat-t-device-in-windows)
* [VyprVPN Support](https://www.giganews.com/support/vyprvpn/vpn-setup/windows-10/l2tp.html)
* [hjorter.it](https://hjorter.it/guides/windows-vpn-problems-cant-connect-to-l2tp-english/)

## Simple Installation

Run **AssumeUDPEncapsulationContextOnSendRule.reg**

## Manual Steps

1. Press the **Windows Key** and **R** at the same time to bring up the Run box.
2. Type in: **regedit** and click **OK**. Click **Yes** if asked if you'd like to allow the app to make changes to your PC.
3. In the left pane, locate and click the folder: **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\PolicyAgent**
4. Click the **Edit** menu and hover your cursor over **New**. Click **DWORD Value**. A new registry will appear in the right pane, named **New Value #1**.
5. Rename that file: **AssumeUDPEncapsulationContextOnSendRule** (this is case-sensitive and contains no spaces) and press **ENTER**.
6. Right-click **AssumeUDPEncapsulationContextOnSendRule**, then click **Modify**.
7. In the **Value** data box, type **2** and click **OK**.
8. Reboot the computer.
