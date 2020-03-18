
# 问题：Git在push的时候发生 RPC failed 错误。

## 解决


1. 进入Git


2. 运行

    ```java
   git config --global http.postBuffer 1048576000

    ```
