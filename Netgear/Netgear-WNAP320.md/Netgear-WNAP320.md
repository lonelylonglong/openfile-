# Netgear WNAP 320

# Firmware：

[WNAP320-Firmware-Version-3-7-11-4](https://kb.netgear.com/000060419/WNAP320-Firmware-Version-3-7-11-4)

# Description：

The device has a vulnerability that leads to information leakage, with important data such as account passwords for admin and user privileges displayed in plaintext and in the same format, without encryption protection. Additionally, there is an unauthorized command execution vulnerability, allowing attackers to execute malicious commands. With the information leakage, attackers can gain admin privileges and make malicious changes to the device. Note: This test device is a decommissioned one.

# Analyse：
## 0x1
First, by accessing all the front-end pages of the device, an unauthorized accessible page called boardDataNA.php was found.

![](vx_images/109712883308291.png)
By analyzing, it was found that the page has inadequate filtering of commands, which can lead to the execution of malicious commands.

![](vx_images/254783757085540.png)


## 0x2
![](vx_images/547093239008815.png)
![](vx_images/141925193276885.png)

![](vx_images/419874592252478.png)

By capturing packets from the login verification page and analyzing the code, we learned the storage format of the password and other information. Upon searching, we discovered that sensitive information is stored in the unique file within the tmp directory.
![](vx_images/114033675707504.png)


# exp


![](vx_images/373696112608775.png)



# Modification suggestions:
1. It is recommended to encrypt passwords.
2. Modify the regular expression filtering for the pages.




