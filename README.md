# Purpose

# EC2 Instance Setup Procedure

## Step 1 VPC Dashboard ---> Lauch EC Instance
![alt tag](https://i.imgur.com/6dKEh7Y.jpg)

## Step 2 Choose an Amazon Machine Image
![alt tag](https://i.imgur.com/d5ec93W.jpg)

## Step 3 Click Connect Button
![alt tag](https://i.imgur.com/6iv5JUq.jpg)

## Step 4 Download PEM file


# Troubleshooting


# Reference
* [（二）EC2（Elastic Compute Cloud）－－AWS經驗教學 Jan 23 Mon 2017](http://akuma1.pixnet.net/blog/post/291725322-%ef%bc%88%e4%ba%8c%ef%bc%89ec2%ef%bc%88elastic-compute-cloud%ef%bc%89%ef%bc%8d%ef%bc%8daws%e7%b6%93%e9%a9%97%e6%95%99%e5%ad%b8)

* [Amazon EC2使用心得 Jan 29, 2016](http://carlislebear.blogspot.com/2016/01/amazon-ec2-tips.html)
```
使用PuTTY連線 Amazon EC2
Rellik：建議你機器不要開密碼登入，開 key登入比較保險（實務上不是掛vpn就是用key登陸，不讓外面的ip直接ssh來try帳號密碼），外面 ssh 通常很容易掃得到，都會有無聊人士，所以不建議用密碼登入。
http://unix.stackexchange.com/questions/116303/convert-amazon-pem-key-to-putty-ppk-key-linux
因為AWS下載的.pem檔，不能直接相容於PuTTY
1. 在AWS上下載你的.pem檔（上面步驟的key.pem）
2. 到 http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html 下載PuTTYgen，並打開他，選擇Type of key to generate為SSH-2 RSA
3. 點擊Load按鈕
4. 設定檔案類型為 *.*
5. 打開你的.pem檔
6. 點擊 Save private key ，把它存為 ppk檔
7. 打開PuTTY。Connection -> SSH -> Auth -> Private key file for authentication選擇你產生的ppk檔
8. PuTTY  Session的連線地址設。AWS Instances列表，你的機器的Public DNS
9. 連線後使用者名稱輸入admin（不能輸入root）
10. 連進去後直接 sudo su - 切換成root
```

* [Convert Amazon .pem key to Putty .ppk key Linux ](https://unix.stackexchange.com/questions/116303/convert-amazon-pem-key-to-putty-ppk-key-linux)
```
Using the GUI

See this SO Q&A on how to do exactly what you want, titled: Convert PEM to PPK file format.
https://stackoverflow.com/questions/3190667/convert-pem-to-ppk-file-format

excerpt

    Download your .pem from AWS
    Open PuTTYgen, select Type of key to generate as: SSH-2 RSA
    Click "Load" on the right side about 3/4 down
    Set the file type to *.*
    Browse to, and Open your .pem file
    PuTTY will auto-detect everything it needs, and you just need to click "Save private key" and you can save your ppk key for use with PuTTY
```

* [[ AWS ] Windows 登入 AWS EC2 教學 23 April 2018](https://oranwind.org/-aws-windows-deng-ru-aws-ec2-jiao-xue/)

* [AWS 設定Load Balancer 教學(含SSL憑證) 2018-10-17](https://liangdaddy.com/2018/10/17/aws-%e8%a8%ad%e5%ae%9aload-balancer-%e6%95%99%e5%ad%b8%e5%90%abssl%e6%86%91%e8%ad%89/)
* [AWS 免費SSL憑證申請教學(有條件的) 2018-10-17](https://liangdaddy.com/2018/10/17/aws-%e5%85%8d%e8%b2%bbssl%e6%86%91%e8%ad%89%e7%94%b3%e8%ab%8b%e6%95%99%e5%ad%b8%e6%9c%89%e6%a2%9d%e4%bb%b6%e7%9a%84/)

* [[教學] 快速註冊 AWS 帳號 (含電話驗證技巧) 2017-04-13](https://jerrynest.io/signup-aws/)

* []()
![alt tag]()

# h1 size

## h2 size

### h3 size

#### h4 size

##### h5 size

*strong*strong  
**strong**strong  

> quote  
> quote

- [ ] checklist1
- [x] checklist2

* 1
* 2
* 3

- 1
- 2
- 3
