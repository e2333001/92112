# Welcome

## Install

### Step 1

下載後直接執行 script 腳本

[主程式安裝腳本](https://gist.github.com/yagami-cerberus/325978e357dbab5be7b4c1f37f8ec9f7)

### Step 2

[ukumpcore 設定檔範例](https://gist.github.com/yagami-cerberus/2739b5e855b49222d8d9fa303038328d)

Note: 100行以前不需要編輯，100行之後需逐行確認包含 資料庫設定，linebot 設定, crm 設定與 google doc 設定

請將設定檔放在 `/var/repository/ukumpcore/ukumpcore/settings.py`

### Step 3

準備資料庫

```
#!sh
# 切換到 ukumpcore 工作目錄
cd /var/repository/ukumpcore

# 建立快取資料庫 (只有在第一次安裝時需要)
./manage.py createcachetable

# 同步資料庫 schema
./manage.py migrate
```

### Step 4

[複製 uwsgi 設定檔](https://gist.github.com/yagami-cerberus/0fa6217215d33ab805c7c6a4bad96999)

複製到 `/etc/uwsgi/apps-enabled/ukumpcore.xml`