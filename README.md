# NmapToXLSX
nmap scan and report to xlsx file

（1）实现nmap扫描并将扫描结果直接导出到xlsx文件

（2）支持批量扫描，批量时每个txt文件导出一个xlsx

（3）支持nmap扫描结果xml直接转xlsx

需要：先在本地安装nmap,并添加环境变量/在nmapToxlsx.py将nmap改为物理路径\n
```
usage:
python nmapToxlsx.py -h

usage: nmapToxlsx.py [-h] [-t TARGET] [-p PORT] [-f FILE] [-td TARGETDIR] [-nP PARAMATE] [-o XLS] [-r XML [XML ...]]

optional arguments:
  -h, --help            show this help message and exit
  -t TARGET, --target TARGET
                        Nmap input host/network
  -p PORT, --port PORT  Nmap only scan specified ports,default:1-65535
  -f FILE, --file FILE  Nmap input from list of hosts/networks
  -td TARGETDIR, --targetdir TARGETDIR
                        Nmap input from list of target file
  -nP PARAMATE, --paramate PARAMATE
                        Nmap paramate with scanner,default:-Pn -sS
  -o XLS, --output XLS  Path to xlsx output
  -r XML [XML ...], --reports XML [XML ...]
                        Path to nmap xml file
                        
```
单个目标：
python nmapToxlsx.py -t 127.0.0.1 -p 80 -nP "-Pn -sV" -o test.xlsx -r test.xml

批量扫描：
python nmapToxlsx.py -f url.txt -p 80 -nP "-Pn -sV" -o test.xlsx -r test.xml

多个url.txt:
python nmapToxlsx.py -td C:\test\nmapToxlsx\Targets -p 80 -nP "-Pn -sV"
