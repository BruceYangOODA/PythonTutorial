### Python也可以這樣學

PythonMP11704  [Python也可以這樣學](http://www.drmaster.com.tw/Bookinfo.asp?BookID=MP11704)

02_Python 序列  
04_物件導向程式設計  
05_字串與規則運算式  



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

print(ord("測"))  
print(ord("試"))  
28204 # 測 utf8編碼數字  
35430 # 試 utf8編碼數字  

string.ascii_letters  a-Z  
string.digits  0-9  
string.punctuation  !"#$%&\'()*+,  

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
<<< type("測試")  
<class "str">  
<<< type("測試".encode("unt-8"))  
<class "bytes">

%格式字串方法  
%s # 用str()顯示  
%r # 用repr()顯示  




