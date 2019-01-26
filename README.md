1.拉取代码，编译

cd BootImgTool
chmod 755 build.sh
./build.sh


2.使用tmp下的boot.img练手，解包：
./bin/unpack-bootimg.sh .tmp/boot.img

此时tmp如下：
ll tmp
total 34944
-rw-r--r--   1 andr0day  staff   8.5M  4 16 19:14 boot.img
-rw-r--r--   1 andr0day  staff   8.0M  4 16 19:30 boot.img-kernel.gz //替换kernel时，覆盖此文件
drwxr-xr-x  25 andr0day  staff   800B  4 16 19:30 boot.img-ramdisk //进入此目录修改配置
-rw-r--r--   1 andr0day  staff   488K  4 16 19:30 boot.img-ramdisk.cpio.gz


3.修改内容略....

4.重新打包：
./bin/repack-bootimg.sh ./tmp/boot.img-kernel.gz ./tmp/boot.img-ramdisk ./myboot.img
