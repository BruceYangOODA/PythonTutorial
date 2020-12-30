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
def __get(self):  
&emsp;return self.__value  
def __set(self, v):  
&emsp;self.__value = v  
def __del(self):  
&emsp;del self.__value  
value = property(__get,__set,__del)

### 05_字串與規則運算式
print(ord("測"))  
print(ord("試"))  
28204 # 測 utf8編碼數字  
35430 # 試 utf8編碼數字
chr(28204) # "測"  

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
os.listdir(path) # 返回資料夾,檔案 列表  
os.path.isdir(path) # 是否為資料夾  
os.walk(path) # 返回 root, 資料夾列表, 檔案列表  

CSV讀寫套件  
csv.writer(file, delimiter, quotechar)  
csv.reader(file, delimiter, quotechar)  
csv.DictWriter(file, fieldnames)  
csv.DictReader(file)  

Pickle讀寫二元資料  
pickle.dump(data, file) # 把data寫入檔案  
pickle.load(file) # 從檔案讀出資料  

p = pickle.dumps(data) # 把資料編成pickle形式  
load_data = pickle.loads(p) # 把pickle形式資料轉譯成物件  

檔案與資料夾操作  
OS模組  
chdir(path)  # 把path設為工作目錄  
get_exec_path() # 返回執行檔的搜尋路徑(環境變數)  
getcwd() # 返回目前工作目錄  
listdir(path) # 返回path目錄下的檔案和目錄清單  
mkdir(path) # 建立目錄 
mkdirs(path/path1/path2) # 建立多層目錄  
rmdir(path) # 刪除目錄  
remove(path) # 刪除檔案  
rename(src, dst) # 重新命名檔案或目錄  
startfile(filepath) # 執行檔案  
stat(path # 返回檔案的所有屬性  
walk(path) # 尋訪目錄樹  

PATH模組  
abspath(path)  
basename(path) # 資料夾名稱或檔名與檔案格式  
dirname(path) # path的資料夾名稱  
exists(path) # 檔案或資料夾是否存在  
getcime(filename) # 檔案建立時間  
getatime(filename) # 檔案最後存取時間  
getmtime(filename) # 檔案最後修改時間  
getsize(filename) # 檔案的大小  
isdir(path)  
isfile(path)  
join(path, *paths)  
split(path) # 取得檔案名稱格式 與 前綴path  
splitext(path) # 取得檔案格式與前綴path  
splitdrive(path) # 取得磁碟名稱與後續path  

SHUTIL模組  
copyfile(src, dst)  
move(src, dst)  
make_archive(base_name) # 建立tar或zip格式的壓縮檔  
unpack_archive(filename) # 解壓縮檔案  

EXCEL檔案讀寫  
97版Excel  
from xlwt import *  
book = Workbook()  
sheet = book.add_sheet("First")  
row = sheet.row(0)  
row.write(0,"test")  
book.save(path)  

import xlrd  
l_book = xlrd.open_workbook(path) # 開啟Excel檔案  
l_sheet = l_book.sheet_by_name("First")  
row = l_sheet.row(0)  
print(row[0].value)  

Python與Win32連動  
06-18_1.py  
06-18_2.py  
06-18_3.py  

from openpyxl import Workbook  
2003年版Excel  
wb = Workbook()  
ws = wb.create_sheet(title="First")  
wb.save(path)  
wb = openpyxl.load_workbook(path)	 

將指定資料夾的檔案壓縮至既有壓縮檔  
06-29.py  
