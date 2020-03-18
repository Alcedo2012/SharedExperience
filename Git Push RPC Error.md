
# 问题：Git在push的时候发生 RPC failed 错误。

```java
Push failed
Enumerating objects: 521, done.
Delta compression using up to 4 threads
RPC failed; HTTP 500 curl 22 The requested URL returned error: 500
the remote end hung up unexpectedly
Total 493 (delta 97), reused 0 (delta 0)
the remote end hung up unexpectedly
 ```
 
## 解决


1. 进入Git


2. 运行

    ```java
   git config --global http.postBuffer 1048576000

    ```
