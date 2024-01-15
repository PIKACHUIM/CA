# 皮卡丘虚假证书颁发机构在线验证点

# Pikachu Fake Certification Authority

## CA证书信息 / CA Certificates Details

`Pikachu Fake CA RSA`是皮卡丘自建的PKI证书系统，该系统只用于<u>测试签名</u>和<u>测试驱动程序</u>等

***本证书及其签署内容不建议安装在生产环境，如果是内部生产环境，请安装***[`Pikachu Root CA`](https://cert.pika.net.cn)

> - **CN =  Pikachu Fake CA RSA**
> - **O = Pikachu Faker Network CA**
> - **OU = Only for Crack & Testing,  C  =  CN**
> - **Description = Do not trust this CA certificate, it is only for forgery and crack testing**
> - **Description = 请勿信任该CA证书，仅供伪造和破解测试，请勿用于生产环境**

## 安装CA证书 / Import CA Certificates

> ### Win32 - [点击下载 / Download File](https://github.com/PIKACHUIM/CA/blob/main/fake/FakeCACert.zip?raw=true)
>
> [Github海外](https://github.com/PIKACHUIM/CA/blob/main/fake/FakeCACert.zip?raw=true)  [Gitee国内](https://gitee.com/pikachuim/CA/raw/main/fake/FakeCACert.zip)  [CDN服务器](https://cdn-tx1.pika.net.cn/Cert/fake/FakeCACert.zip)  [直链服务](https://cert.pika.net.cn/fake/FakeCACert.zip)
>
> ```
> certutil.exe -urlcache -split -f "https://gitee.com/pikachuim/CA/raw/main/fake/CA-RSA4096.zip" CA-RSA4096.zip
> 7z x -tzip -y CA-RSA4096.zip
> forfiles /p .\ /s /c "cmd /c ..\certmgr.exe -add /all @path -s -r localMachine AuthRoot"
> forfiles /p .\ /s /c "cmd /c echo @path"
> ```
>
> ### Linux - 导入方法 / Import Tutorial
>
> ```
> wget https://github.com/PIKACHUIM/CA/raw/main/fake/CA-RSA4096.zip
> unzip CA-RSA4096.zip
> sudo cp -r ./*.crt /usr/local/share/ca-certificates
> sudo update-ca-certificates
> sudo cp -r ./*/*.crt /usr/local/share/ca-certificates
> sudo update-ca-certificates
> ```
>
> ### MacOS  - 导入方法 / Import Tutorial
>
> ```
> curl -L -o CA.zip -k "https://github.com/PIKACHUIM/CA/raw/main/fake/CA-RSA4096.zip"
> unzip CA-RSA4096.zip
> for i in ./*.cer; do
> echo "$i" && sudo security add-trusted-cert -d -r trustRoot "$i";
> done
> for i in ./*/*.cer; do
> echo "$i" && sudo security add-trusted-cert -d -r trustRoot "$i";
> done
> ```

## CA根证书 / Root CA - RSA-4096-SHA

> - ### **[证书信息 / Certificate Info](fake/CA-RSA4096.cer)**
>
>   - **证书算法(Signer Algorithm)：**`RSA4096(05 00) sha512RSA`
>
>   - **CA序列号(Certificate  SerN.)：**`00915b84a17240391d58dd3597`
>
>   - **证书指纹(Certificate  SHA1)：**`d5585407f4d02b94e8ba54440dbb9ebd9a2a72b0`
>   
>- ### [下载证书 / Download Cert](fake/CA-RSA4096.cer)
> 
>  - **[CER](fake/CA-RSA4096.cer)**   /  **[CRT](fake/CA-RSA4096.crt)**   /  **[DER](fake/CA-RSA4096.der)**   /  **[P7B](fake/CA-RSA4096.p7b)**
> 
>- ### **[吊销列表 / Revocation List](fake/CA-RSA4096.crl)**
> 
>  - [2020/01/01 - 2030/01/01](fake/CA-RSA4096.crl)
