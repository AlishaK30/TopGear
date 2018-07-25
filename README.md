# TopGear
1. What will be the output of 'seclist' in print commands of below code?
mylist = range(4)
seclist = mylist
print seclist
mylist.append(4)
print seclist
seclist = mylist[:]
print seclist
mylist.append(5)
print seclist

Ans:[0,1,2,3,4]

2. What is the output of following code:
def f(n):
  for x in range(n):
    yield x**3

for x in f(6):
  print x

Ans: 0
1
8
27
64
125

3. Write a program to receive a string from keybord and check if the string has two 'e' in the characters. 
   If yes return True else False.



def Check():
    str=input("Enter the string");
    count=0;
    for c in str:
       if c=='e':
            count=count+1
    if count==2:
        return True
    else:
        return False

res=Check();
print(res);


4. What is the output of following code:
counter = 1
def dolots(count):
  global counter
  for i in (1, 2, 3):
    counter = count + i

print dolots(4)
print counter

Ans:7

5.	Write a code to read  the data from  input file called input.txt and count the number of characters per line,
number of words per line and write these into output file called as output.txt 

file=open('input.txt',"r");
lines=file.readlines()
count=0;
for line in lines:
    str=line;
    count=count+1;
    word=1;
    chara=0;
    print("Line %d :"%(count))
    for c in str:
        if c==' ':
            word=word+1;
        if (c<='z' and c>='a')or(c<='Z' and c>='A'):
             chara=chara+1;
    
    print("No of words:%d No of char:%d"%(word,chara))
   
    
file.close()

6.	Create 3 Lists ( list1,list2,list3) with numbers and perform following operations
         a) Create Maxlist by taking 2 maximum elements from each list.
         b) Find average value from all the elements of Maxlist.
         c) Create a MinlIst by taking 2 minimum elements from each list 
         d) Find the average value from all the elements of Minlist

list1=[1,9,4,7,2]
list2=[8,3,0,5,7]
list3=[7,90,3,8,1,9]

n=len(list1);
maxList=[]
minList=[]
i=0;
for i in range(n):
    j=0;
    for j in range(n-i-1):
        if list1[j+1]<list1[j]:
            list1[j],list1[j+1]=list1[j+1],list1[j];
    if i==0:
        maxList.append(list1[n-1])
    if i==1:
        maxList.append(list1[n-2])
minList.append(list1[0]);
minList.append(list1[1]);
i=0;
n=len(list2)
for i in range(n):
    j=0;
    for j in range(n-i-1):
        if list2[j+1]<list2[j]:
            list2[j],list2[j+1]=list2[j+1],list2[j];
    if i==0:
        maxList.append(list2[n-1])
    if i==1:
        maxList.append(list2[n-2])
minList.append(list2[0]);
minList.append(list2[1]);

i=0;
n-len(list3);
for i in range(n):
    j=0;
    for j in range(n-i-1):
        if list3[j+1]<list3[j]:
            list3[j],list3[j+1]=list3[j+1],list3[j];
    if i==0:
        maxList.append(list3[n-1])
    if i==1:
        maxList.append(list3[n-2])
minList.append(list3[0]);
minList.append(list3[1]);
#a
print(maxList);
#b
sum=0;
c=0;
for i in maxList:
    c=c+1;
    sum=sum+i;
avg=sum/c;
print("Average is %f"%(avg))
#c
print(minList);
#d
sum=0;
c=0;
for i in minList:
    c=c+1;
    sum=sum+i;
avg1=sum/c;

print("Average is %f"%(avg1))
 



 8.	Create a suitable data construct to read the data from an xml document as shown below:
<bookstore shelf="New Arrivals">
  <book category="COOKING">
    <title lang="en">Everyday Italian</title>
    <author>Giada De Laurentiis</author>
    <year>2005</year>
    <price>30.00</price>
  </book>
  <book category="CHILDREN">
    <title lang="en">Harry Potter</title>
    <author>J K. Rowling</author>
    <year>2005</year>
    <price>29.99</price>
  </book>
  <book category="WEB">
    <title lang="en">Learning XML</title>
    <author>Erik T. Ray</author>
    <year>2003</year>
    <price>39.95</price>
  </book>
</bookstore>

from xml.dom import minidom

doc = minidom.parse("xmlq.xml")

books = doc.getElementsByTagName("book")
for book in books:
        categ=book.getAttribute("category")
        nameOfAuth = book.getElementsByTagName("author")[0]
        title=book.getElementsByTagName("title")[0]
        price=book.getElementsByTagName("price")[0]
        print("Title:%s , Category:%s ,Author:%s ,Price:%s" %(title.firstChild.data,categ,nameOfAuth.firstChild.data,price.firstChild.data))

9.	Create a suitable object type and  check for file size of 0 bytes of the directory contents as shown below
02/15/2016              10:49 PM               962                     switchfinal.py
02/15/2016             10:49 PM               943                       switchfinal.py.bak
01/27/2016             11:46 AM                15                        t.py
03/31/2016            12:39 PM               840                        t1.py
01/25/2016            10:34 AM             2,407                      tc1.py
02/14/2017           09:13 AM                 0                           teat.py
03/15/2016          05:52 PM                 5                             tes.py

class File(object):
    name=""
    date=""
    time=""
    file_size=0

    def __init__(self,name,date,time,file_size):
        self.name=name
        self.date=date
        self.time=time
        self.file_size=file_size
        
    def displayFile(obj):
        print("Name : %s"%(obj.name))
        print("Date : %s"%(obj.date))
        print("Time : %s"%(obj.time))
        print("Size : %d"%(obj.file_size))

    def checkZero(obj):
        if obj.file_size==0:
            print("File size is zero")
        else:
            print("File size is not zero")

f1=File("als","12/12/12","12:12:12",90)
f1.displayFile()
f1.checkZero()

10.Create a suitable object type to eliminate the duplicate elements
def RemDup(duplicate):
    finalList=[]
    for i in duplicate:
        if i not in finalList:
            finalList.append(i)
    return finalList

List=[2,45,6,1,7,2,9,3,45,9,7,4]
New=RemDup(List)
print("New list is ",New)
