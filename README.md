create table PUBLISHER(Name varchar(10) primary key,Address varchar(20),Phone varchar(10));
create table BOOK(Book_id integer primary key,Title varchar(20),Publisher_Name varchar(20),Pub_Year integer,foreign key(Publisher_Name) references PUBLISHER(Name));
create table BOOK_AUTHORS(Book_id integer primary key,Author_Name varchar(10),foreign key(Book_id) references BOOK(Book_id));
create table LIBRARY_BRANCH(Branch_id integer primary key,Branch_Name varchar(30),Address varchar(10));
create table BOOK_COPIES(Book_id integer,Branch_id integer,No_of_Copies integer,primary key(Book_id,Branch_id),foreign key(Book_id) references BOOK(Book_id),foreign key(Branch_id) references LIBRARY_BRANCH(Branch_id));
create table BOOK_LENDING(Book_id integer,Branch_id integer,Card_No integer,Date_Out date,Due_Date date,primary key(Book_id,Branch_id,Card_No),foreign key(Book_id)references BOOK(Book_id),foreign key(Branch_id)references LIBRARY_BRANCH(Branch_id));
insert into PUBLISHER values('Mcgraw','Bangalore','9696500001');
insert into PUBLISHER values('Person','Bangalore','9595950000');
insert into PUBLISHER values('SAM Pub','Mangalore','9494940000');
insert into PUBLISHER values('IOP','Mumbai','9797970000');
insert into PUBLISHER values('IEEE','Delhi','9090900000');
insert into BOOK values(10,'DBMS','Mcgraw',2010);
insert into BOOK values(20,'SE','Person',2008);
insert into BOOK values(30,'FLAT','SAM Pub',2019);
insert into BOOK values(40,'BDA','IOP',2018);
insert into BOOK values(50,'MP','IEEE',2020);
insert into BOOK_AUTHORS values(10,'Andrew');
insert into BOOK_AUTHORS values(20,'Raj Kumar');
insert into BOOK_AUTHORS values(30,'Samual');
insert into BOOK_AUTHORS values(40,'Padma');
insert into BOOK_AUTHORS values(50,'Guru');
insert into LIBRARY_BRANCH values(100,'Main Building','Mangalore');
insert into LIBRARY_BRANCH values(200,'Ground Floor','Bangalore');
insert into LIBRARY_BRANCH values(300,'1st Floor','Bangalore');
insert into LIBRARY_BRANCH values(400,'Research Building','Udupi');
insert into LIBRARY_BRANCH values(500,'OPD Building', 'Manipal');
insert into BOOK_COPIES values(10,100,20);
insert into BOOK_COPIES values(30,100,30);
insert into BOOK_COPIES values(10,200,5);
insert into BOOK_COPIES values(20,300,15);
insert into BOOK_COPIES values(40,500,7);
insert into BOOK_LENDING values(10,100,201,'2020-06-15','2020-06-25');
insert into BOOK_LENDING values(20,200,202,'2020-07-10','2020-07-20');
insert into BOOK_LENDING values(30,300,203,'2020-07-25','2020-07-30');
insert into BOOK_LENDING values(40,400,204,'2020-08-14','2020-08-26');
insert into BOOK_LENDING values(50,500,205,'2020-09-01','2020-09-10');

---

**Query #1**

    select * from PUBLISHER;

| Name    | Address   | Phone      |
| ------- | --------- | ---------- |
| IEEE    | Delhi     | 9090900000 |
| IOP     | Mumbai    | 9797970000 |
| Mcgraw  | Bangalore | 9696500001 |
| Person  | Bangalore | 9595950000 |
| SAM Pub | Mangalore | 9494940000 |

---

[View on DB Fiddle](https://www.db-fiddle.com/f/c1baSsStkJSdnY1aorDVCf/1)
