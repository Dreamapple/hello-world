
使用pcap库提取网卡信息，实现tcp html协议，最后提取信息

### 使用的外部库有：
1. zlib 用于网站的解压缩，编译需要-lz或者在需要链接的地方加z;
2. libchardet 用于网站的字符编码打确定，编译需要-lchardet或者在需要链接的地方加chardet;
3. libconfig 用于读取配置文件，编译需要-lconfig++
4. libpcap,-lpcap
```
sudo ldconfig -v
```

### 还未完成的：
1. 乱序的tcp包会导致整个流解码出现错误，丢包/重复同上。  -> 已经实现简单的了
2. 状态转换不完整，遇到没有必要处理的图片等包也必需处理，浪费时间。 -> easy
3. string 处理不熟练，可能会无畏拷贝，释放很多次，尽管已经极力避免。
4. ctrl+c处理    -> ok

- 修复了一个*** stack smashing detected ***崩溃的错误（原因是网址太长，分配的内存char url[30]不够）
