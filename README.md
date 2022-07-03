

手動部署 K8s 叢集是件重複又繁瑣的事情，除了要先準備好基礎機器環境之外，還要每一台機器安裝依賴套件後，並一個一個加入叢集內，透過 Terraform + Ansible Iac 最佳組合自動化完成一整個系列從無到有創建。

<!-- more -->

## 1. DEMO 執行範例


![](https://i.imgur.com/Rows9UK.png "初始化")

![](https://i.imgur.com/Q5HMaRn.png "Terraform 自動創建 EC2")

![](https://i.imgur.com/dzoepIC.png "Ansible 自動部署 K8s")

![](https://i.imgur.com/spP2gnu.png "K8s 狀態")

---

## 2. Quick Start  
>透過 Docker 快速創建 Terraform & Ansible 環境及 Iac Code。


1. 啟動建立好的環境。

```bash
docker run --rm -it jeffwen0105/iac-ec2-k8s bash
```

2.  使用 vi 編輯 credentials ，將 AWS 具備創建 VPC 及 EC2 的 credentials 貼上。

```ini
[default]
aws_access_key_id=<YOUR aws_access_key_id>
aws_secret_access_key=<YOUR aws_secret_access_key>
```



3.  執行自動部屬腳本。

> *該環境會使用既有的金鑰遠端連線執行 Ansible 操作，如果擔心金鑰重複的安全性，可以先執行 `bash regenerateKey.sh` 來重新產生一組公私鑰。*


```bash
bash run.sh
```


更多內容請至 HowHow 官網查閱，[AWS - Terraform & Ansible 在 AWS 上自動部署 K8S 叢集請點我](https://how64bit.com/posts/aws/2022/aws-iac_k8s/)