### Protocol packets list
**内容**：DHCP交互报文  
**注意**：使用wireshark打开它  

###说明：  
共有4个报文：  
1.DHCP Discover（在局域网内广播请求信息，寻找DHCP Server）  
请求信息，源MAC地址是请求者，源IP是0.0.0.0；目标MAC地址和IP地址均为局域网广播；  
2.DHCP Offer（DHCP Ser回复消息，携带分配IP信息，询问请求主机是否可以）  
咨询信息，源MAC地址和IP地址为DHCP服务器（一般是网关设备），目标MAC是请求主机，目标IP为请求主机，**请注意**：此时请求主机还未确认，但网关已经将此IP作为主机IP进行信息传递，`Your (client) IP address: 10.1.1.254`  
3.DHCP Request（主机回复信息）  
**请注意**：此时源IP为`Your (client) IP address: 0.0.0.0`,主机回复：我可以，给我吧？  
4.DHCP ACK（网关确认信息）  
OK，给你了，此时，主机才真正拿到IP信息，开始和其他主机通讯。  
所以，常见的问题是：  
**某些时候，为了在办公区域内增加Wi-Fi设备时，会不小心将网线插入到设备WAN，因Wi-Fi设备的DHCP服务是默认启动的，所以，导致局域网内出现了伪造的DHCP服务器，导致无法上网**  


