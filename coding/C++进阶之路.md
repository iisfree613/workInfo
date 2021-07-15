# 神奇的用法：

### #pragma

在所有的预处理指令中，#pragma 指令可能是最复杂的了，它的作用是设定编译器的状态或者是指示编译器完成一些特定的动作。#pragma指令对每个编译器给出了一个方法，在保持与C和C++语言完全兼容的情况下，给出主机或操作系统专有的特征。依据定义，编译指示是机器或操作系统专有的，且对于每个编译器都是不同的。   #pragma once   只要在头文件的最开始加入这条指令就能够保证头文件被编译一次

#ifndef，#define，#endif这个是C++语言相关，这是C++语言中的宏定义，通过宏定义避免文件多次编译。所以在所有支持C++语言的编译器上都是有效的，如果写的程序要跨平台，最好使用这种方式（被称为预处理指令）

#pragma comment

该指令将一个注释记录放入一个对象文件或可执行文件中。
常用的lib关键字，可以帮我们连入一个库文件。



## for(;;)   --> 近似于while(True) 死循环停留



#### include头文件时尖括号<>与双引号""的区别：

* 系统自带的头文件用尖括号；编译器会在系统文件目录查找；
* 用户自定义的头文件用双引号导入；编译器会先在用户目录下查找，然后再到C++安装目录中查找；最后在系统文件中查找



# C++编码安全
*  不使用无长度限制的字符拷贝函数
*  switch中应有default
*  避免函数的声明和实现不同（注意函数名和参数，及返回值类型）
*  不得直接使用刚分配的未初始化的内存-》对新分配的内存赋初值



## C++ 变量默认初始化

1. 全局变量编译器会自动赋初值，局部变量需要自己初始化，否则编译器中报错（MSVC2015测试中会报错，其他编译器未知）
2. 静态变量无论全局还是局部，编译器都会赋初值。

## 类型转换

``` c++
// char * -> string
char * data = "Hello world!";
string str = data;

// string -> char *
string str = "hello world";
char * pstr = (char *) str.data();

// string -> CString
// 方法1
string str1 = "Hello world.";
CString cStr;
cStr.Format(_T("%s"), str1.c_str());
// 方法2 >> 不会打导致乱码显示 (windows系统，MSVC环境下)
string str1 = "Hello world.";
CA2T temp(st1.c_str());
CString cStr = (LPCTSTR)temp;

// CString -> string
CString cstr = _T("Hello world");
string str = CT2A(cstr.GetString());
```

## UDP数据发送接收

``` c++
	CInitSock initSock;
	SOCKET SendSocket = ::socket(AF_INET, SOCK_DGRAM, IPPROTO_UDP);
	if (SendSocket == INVALID_SOCKET) {
		return -1;
	}
	// 设置超时时间
	long secs = 3, u_secs = 0;
	DWORD dw = (secs * 1000) + ((u_secs + 999) / 1000);
	setsockopt(SendSocket, SOL_SOCKET, SO_RCVTIMEO, (char *)&dw, sizeof(dw));

	sockaddr_in addr;
	addr.sin_addr.S_un.S_addr = inet_addr("239.0.0.1");
	addr.sin_family = AF_INET;
	addr.sin_port = htons(28888);
	int len = sizeof(addr);
	
	string temp = "Hello world.";
	char * send_data = (char *)temp.data();
	int send_len = temp.length();

	int ss = sendto(SendSocket, send_data, send_len, 0, (sockaddr*)&addr, len);
	if (ss < 0) {
		std::cout << "send error" << std::endl;
	}
	
	char recv_data[1024];
	memset(recv_data, 0, 1024);
	while (1)
	{
		int n = recvfrom(SendSocket, recv_data, 1024, 0, (sockaddr*)&addr, &len);
		if (n < 0) {
			std::cout << "receive message error" << std::endl;
			break;
		}
        string recv = recv_data;
        std::cout << "接收到数据：" << recv << std::endl;
    }
```

## 获取指定IP的Mac地址

``` C++
string getRemoteMac(char * localIP, char * remoteIP)
{
	string temp;
	unsigned char *pbHexMac;
	WSADATA wsaData;

	int iRet = WSAStartup(MAKEWORD(2, 1), &wsaData);
	if (iRet != 0)
	{
		std::cout << "Error" << endl;
		return "";
	}

	IPAddr nRemoteAddr = inet_addr(remoteIP);
	IPAddr nLocalAddr = inet_addr(localIP);
	unsigned char macAddress[6];
	ULONG macAddrLen = 6;
	memset(&macAddress, 0xff, sizeof(macAddress));
	auto res = SendARP(nRemoteAddr, nLocalAddr, macAddress, &macAddrLen);
	if ((res == NO_ERROR) && (macAddrLen == 6)) {
		pbHexMac = macAddress;
		temp.Format(_T("%02X:%02X:%02X:%02X:%02X:%02X "), pbHexMac[0], pbHexMac[1], pbHexMac[2], pbHexMac[3], pbHexMac[4], pbHexMac[5]);
		return temp;
	}
	else {
		std::cout << "Send arp error" << std::endl;
		return "";
	}
}

```

## 需求：将int类型转化为高,低位两个字节存储
int类型默认为4个字节，32位存储；
首先将int类型转换为`unsigned short`类型，2个字节，16位存储；
然后分别获取高位，低位存储
代码如下：
```C++
	BYTE data[50]; 
    memset(data, 0, sizeof(data));
    int num = 1024;
unsigned short temp = (unsigned short)num;
	data[0] = temp & 0xff; // 获取低位
    data[1] = temp >> 8;  // 右移一个字节，获取高位

```

