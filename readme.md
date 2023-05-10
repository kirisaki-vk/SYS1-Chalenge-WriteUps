# **Write Ups on the Root Me Network Chalenge**

> **Notes:** To complete those chalenge, I will mainly use Wireshark to analize all the capture given to complete the level.

-----------------------------------

## **1.FTP Authentification**
- To Complete this chalenge, open the FTP capture and then right click on any FTP trafic then go to **Follow > TCP Stream**, the password would be after the `PASS` keyword.

-------------------

## **2.TELNET Authentification**
- To complete this, open the TELNET capture in Wireshark, then right click on any TELNET packet then go to **Follow > TCP Stream**, the password would be after the `Password: ` keyword

------------------

## **3.ETHERNET Frame**
- To complete it, you would need first decode that hex frame to any tool who can do it, I've used [ConvertString](https://www.convertstring.com/fr/EncodeDecode/HexDecode)

- After decoding it, you should get:

```
�s ��àiØZÝ`����@&S��`*¼����ºÞÀÞ AÐ�B3�������t�P¼ê}¸�Á×�áÏ ��
	>i¹¡~ÓGET / HTTP/1.1
Authorization: Basic Y29uZmk6ZGVudGlhbA==
User-Agent: InsaneBrowser
Host: www.myipv6.org
Accept: */*

```

- The password is encoded in **base64** after that `Basic` keyword, decode it and you should get the password

-------------------

## **4.Twitter Authentification**
- To pass it, open the capture in Wireshark then right cilck on the packet then go to **Follow > TCP Stream**
- The password is encoded in **base64** after that `Basic` keyword, decode it and you should get the password

-----------------

## **5.Bluetooth - Unknown File**
- You can open the `.bin` file with Wireshark then go to `wireless` menu then go to `Bluetooth Devices`, you will find there the MAC Adress of the device and his name
- Then you can concatenate them and make it's `sha1sum` to get the password