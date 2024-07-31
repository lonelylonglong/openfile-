
# DIR-860L_REVA_FIRMWARE_hardcode_password

# Firmware:
[DIR-860L_REVA_FIRMWARE_1.08B02.ZIP](https://support.dlink.com/resource/products/DIR-860L/REVA/DIR-860L_REVA_FIRMWARE_1.08B02.ZIP)

# Description:

After the device's system initialization starts, the telnet service is a default startup item. The login account and password for this service are hard-coded and can be directly obtained from the device files. This vulnerability can be exploited by attackers for malicious command execution. Note: This device is a decommissioned device.

# Analyse：

Firstly, we can see that the login account is Alphanetworks, and the password is a parameter: image_sign.
![389843926528302](vx_images/412207692970518.png)

Password: "image_sign" is obtained by running the command: cat /etc/config/image_sign. As shown in the figure below.

![38234044756609](vx_images/247026129619054.png)
After executing the command, go to telnet hard code: wrgac03_dlob.hans_dir860

![55553997844254](vx_images/403348452579194.png)




Simulate the launch of the website

![443642910798891](vx_images/4858349149013.png)



Then connect to the website via telnet

![17284674082694](vx_images/154749842324546.png)
