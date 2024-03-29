# 【HELM 教學】

## 流程

```mermaid
graph TD

S((S:開始)) --> 

a2{網路版本/自訂版本} -- 網路版本--> B1[B1:指定repo位置] -->B2[B2:下載helm chart檔案] --->B3[B3:解壓縮檔案tar] 
---> D[D:helm 的格式]

a2{網路版本/自訂版本} -- 自訂版本--> C1[C1:創建初始樣板]
---> D[D:helm 的格式] --> E((E:結束)) 

```
---

## `B1`指定repo位置
```
$ helm repo add my-repo https://charts.bitnami.com/bitnami
```
---
## `B2`下載helm chart檔案
- 下載redis-cluster
- 檔案為 : redis-cluster-8.3.8.tgz
``` cmd
$ helm pull my-repo/redis-cluster --version 8.3.3
```
---
## `B3`解壓縮檔案tar
- 下載的檔案最新版目前為:redis-cluster-8.3.8.tgz
```
tar xvf redis-cluster-8.3.8.tgz
```
---
## `C1`創建初始樣板
```
helm create helm-demo
```
---
## `D`Chart 的格式
>基本格式
```
.
├── Chart.yaml
├── charts
├── templates
│   ├── deployment.yaml
│   ├── ingress.yaml
│   └── service.yaml
└── values.yaml
```
---
## helm與value產生格式
> 需與 Chart.yam相同目錄
```
helm template .
```
---
