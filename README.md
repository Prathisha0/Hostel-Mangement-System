# Hostel-Mangement-System
import mysql.connector as sql
conn=sql.connect(host=&#39;localhost&#39;,user=&#39;root&#39;,p
asswd=&#39;admin@123&#39;,database=&#39;hostel_management&#39;)
conn.autocommit=True
if conn.is_connected():
    print(&#39;connected succesfully&#39;)
else:
    print(&#39;not connected&#39;)

c1=conn.cursor()
#c1.execute(&quot;create table
hostel_management(roll_no int primary key,name
varchar(20),address varchar(100),room_no
int,dept varchar(15),fees int,bal int)

print(&quot;WELCOME TO HOSTEL MANAGEMENT&quot;)
print(&quot;1.ADMISSION FORM&quot;)
print(&quot;2.FEE CHECKING&quot;)
print(&quot;3.MODIFY DATA&quot;)
print(&quot;4.EXIT&quot;)
choice=int(input(&#39;ENTER YOUR CHOICE&#39;))
if choice==1:
    v_roll=input(&quot;ENTER YOUR ROLL NUMBER&quot;)
    v_name=input(&quot;ENTER YOUR NAME&quot;)
    v_add=input(&quot;ENTER YOUR ADDRESS&quot;)
    v_room_no=input(&quot;ENTER YOUR ROOM NUMBER&quot;)
    v_dept=input(&quot;ENTER YOUR DEPARTMENT&quot;)
    v_fees=input(&quot;ENTER YOUR FEES&quot;)
    v_bal=input(&quot;ENTER YOUR BALANCE&quot;)
    
    abc=(&quot;insert into hostel_management values
(&quot;+v_roll+&quot;,&#39;&quot;+v_name+&quot;&#39;,&#39;&quot;+v_add+&quot;&#39;,&quot;+v_room_n
o+&quot;,&#39;&quot;+v_dept+&quot;&#39;,&quot;+v_fees+&quot;,&quot;+v_bal+&quot;)&quot;)
    print(abc)
    c1.execute(abc)
    conn.commit()
elif choice==3:
    roll_no=int(input(&quot;enter your roll
number&quot;))
    mysql=&quot;select*from hostel_management where
roll_no={}&quot;.format(roll_no)
    c1.execute(mysql)
data=c1.fetchall()
    print(&quot;roll_no:&quot;,data[0][0])
    print(&quot;name:&quot;,data[0][1])
    print(&quot;address:&quot;,data[0][2])           
    print(&quot;room_no:&quot;,data[0][3])
    print(&quot;dept:&quot;,data[0][4])
    print(&quot;fees:&quot;,data[0][5])           
    print(&quot;bal:&quot;,data[0][6])
elif choice==2:
    print(&quot;AVAILABLE DEPARTMENTS AS FOLLOWS&quot;)
    print(&quot;1.COMPUTER&quot;)
    print(&quot;2.BIO&quot;)
    print(&quot;3.TECH&quot;)
    print(&quot;4.PHYSICS&quot;)
    print(&quot;5.ECO&quot;)
    print(&quot;6.ENG&quot;)
    department=input(&quot;ENTER YOUR DEPARTMENT&quot;)
    mysql=&quot;select*from fees where
department=&#39;{}&#39;&quot;.format(department)
    c1.execute(mysql)
    data=c1.fetchall()
    print(&quot;your fees is:&quot;,data[0][1])

else:
     print(&quot;QUITTING!!!!!!!!!&quot;)
