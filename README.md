# portscan
批量扫描IP端口程序 （适用于window&amp;linux）


批量扫描IP端口，根据扫描IP导出IP命名的文件的结果。  
假设1.txt文件内容为  
127.0.0.1  
192.168.1.1  
然后我们获取文件内容IP进行扫描  

## window .bat版本  
```
:1.txt为文件名,根据需求进行修改
:C:\nmap\nmap-6.46\nmap.exe 为namp的路径,根据需求进行修改
:把1.txt与该扫描脚本放一起
@echo off
for /f "delims=、" %%i in (1.txt) do C:\nmap\nmap-6.46\nmap.exe -T3 -A
-v -p- %%i >%%i.txt
```  

## linux shell版本  

```  
echo ‘start scan ip port!‘
cat 1.txt|while read line
do
        nmap -T3 -A -v -p- $line > $line.txt
        echo "scan $line port ok!"
done
echo "scan all ip port ok!"
```  
附上linux扫描结果图  

我然后利用扫描出来的文件，进行批量筛选出IP、Port、状态、服务 合成一个文件，然后统计excel文档就很快速了:)  

Ref: https://www.yuanmas.com/info/x5aYJ90ByD.html  
