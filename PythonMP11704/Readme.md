### Python也可以這樣學

PythonMP11704  [Python也可以這樣學](http://www.drmaster.com.tw/Bookinfo.asp?BookID=MP11704)

02_Python 序列  
04_物件導向程式設計  
05_字串與規則運算式  
06_檔案與資料夾操作  



import this  

package list  
https://pypi.org/  

安裝C++ 編譯器  
https://www.lfd.uci.edu/~gohlke/pythonlibs/  
pip install pygame-1.9.2a0-cp35-none-win_amd64.whl  

### 02_Python 序列
list({"a":3, "b":9, "c":72}.items())  
[("b",9), ("c",72), ("a",3)]

建立值為空的字典  
adict = dict.fromkeys(["name","age","sex"])  
設定預設值  
adict.setdefault("adress","NotHere") 

列印區域、全域變數  
print("locals",locals())  
print("globals",globals())  

建立一個有序的字典  
import collections  
x = collections.OrderedDict()  
x["a"] = 3, x["b"] = 4, x["c"] = 5  
x >>> OrderedDict([("a",3),("b",4),("c",5)])  

### 04_物件導向程式設計
import datetime  
Today = datetime.date.today()  
<<< Today  
datatime.date(2015,12,6)  
now = datetime.datetime.now()  
<<< now  
datetime.datetime(2015,12,6,16,1,30,313898)  

__new__在__init__之前執行  
total =  0  
def _ _ new _ _ (cls, *args, **kwargs):  
&emsp;if cls.total >= 3:  
&emsp;&emsp;raise Exception("MAX 3")  
&emsp;else:  
&emsp;&emsp;return object. _ _ new _ _ (cls)          
def _ _ init _ _ (self):  
&emsp;ClassName.total = ClassName.total + 1  
  
可讀、可寫、可刪除的屬性  
def get(self):  
&emsp;return self.__value  
def set(self, v):  
&emsp;self.__value = v  
def del(self):  
&emsp;del self.__value  
value = property(__get,__set,__del)

### 05_字串與規則運算式
print(ord("測"))  
print(ord("試"))  
28204 # 測 utf8編碼數字  
35430 # 試 utf8編碼數字

<<< type("測試")  
<class "str">  
<<< type("測試".encode("unt-8"))  
<class "bytes">

%格式字串方法  
%s # 用str()顯示  
%r # 用repr()顯示  
%d # 十進位整數    
%f # 浮點數  
%% # 字元%  

尋找字串方法  
find() rfind()  # 不存在返回-1  
index() rindex() # 不存在拋出異常  
count() # 不存在返回 0  

映射字串內位置相對的字元  
table = "".maketrans("字串A","字串B")
字串C.trainslate(table) # 字串C內 符合映射表字串A的字元會被字串B取代  

產生隨機密碼  
ascii = string.ascii_letters  # 英文字母 a-Z  
dight = string.digits  # 數字 0-9  
punct = string.punctuation  # 標點符號 !"#$%&\'()*+,  
x = ascii + digit + punct  
"".join([random.choice(x) for i in range(8)])
隨機產生8字元密碼

startswith(字串A) # 以 字串A 為開頭  
endswith(字串A) # 以 字串A 為結尾  

字串.center(數字) # 長度數字的字串,居中對齊,左右以空白填充  
字串.ljust(數字,字元) # 靠左對齊,右邊以字元填充  
字串.rjust(數字) # 靠右對齊  
字串.zfill(數字) # 長度數字的字串,空白處以0填充  

import textwrap  
textwrap.fill(doc, width=80) # 以字串長度80排版 doc  

另一種中文斷詞套件  
import snownlp  
snownlp.SnowNLP(字串).words  

規則運算式  
_. 比對除分行符號之外的任意單個字元  
_* 出現0或多次  
_+ 出現1或多次  
_? 出現0或1次  
_- 在[]內表示範圍  
^ 從行頭比對  
$ 從行尾比對  
\num 比對num次數的連續字元  
\d 比對數字  [0-9]  
\D 比對非數字 [^0-9]  
\s 比對空白字元 [\f\n\r\t\v]  
\S 比對非空白字元  
\w 比對任何字母、數字、底線 [a-zA-Z0-9_]  
\W 比對任何非....  
() 將()視為一個整體對待  
{} 按照{}內次數進行比對    
[] 比對[]內任何字元  
[^] 比對非[]內任何字元  

re.compile()  
re.search()  
re.match()  
re.findall()  
re.sub()  以repl替換  

### 06_檔案與資料夾操作
