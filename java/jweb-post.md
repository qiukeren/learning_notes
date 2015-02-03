#POST数据表单的CheatSheet



####以下代码用于输出POST的全部内容，用于调试
```java
BufferedReader sis; 
sis = request.getReader();
char[] buf = new char[1024];
int len = 0;
StringBuffer sb = new StringBuffer();
while((len = sis.read(buf))!= -1){
sb.append(buf,0,len);
}
System.out.println(sb.toString());
sis.close();
```
输出示例：
>cmd=save-record&recid=0&record[first_name]=%E9%98%BF%E8%90%A8%E5%BE%B7&record[last_name]=%E5%95%8A%E6%B2%99%E5%8F%91%E8%90%A8%E8%BE%BE&record[comments]=%E6%92%92%E6%97%A6%E6%B3%95

注意事项：
1.一旦使用本代码，再用request.getparameter获取参数得到的内容便是null，因此本代码只用于调试。
