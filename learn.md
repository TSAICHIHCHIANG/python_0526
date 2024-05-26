git init
git status
git add .
git commit -m
git log
CI\CD
    要建立一個.github資料夾  裡面要在建立一個workflows資料夾 之後再workflows底下 建立一下main.yml
    yml是一種資料格式 (yaml)
    name: Run Python Test
on: 
  push: # do this every push
  schedule:
  - cron: "0 8 * * *"  每天早上八點執行 https://crontab.guru/#0_0_*_*_1
    jobs:
         build:   
            name: run python
            runs-on: ubuntu-latest  執行在linux上
            steps:
            - uses: actions/checkout@v2
            - name: Run python
           run: |
              python3 test.py  啟動pythob3  執行檔案