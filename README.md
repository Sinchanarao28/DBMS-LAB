**Schema(MYSQL v5.7)**

create table PUBLISHER(Name varchar(10) primary key,Address varchar(20),Phone integer);
create table BOOK(Book_id integer primary key,Title varchar(20),Publisher_Name varchar(20),Pub_year integer,foreign key(Publisher_Name) references PUBLISHER(Name));
create table BOOK_AUTHORS(Book_id integer primary key,Author_Name varchar(10),foreign key(Book_id) references BOOK(Book_id));
create table LIBRARY_BRANCH(Branch_id integer primary key,Branch_Name varchar(10),Address varchar(10));
create table BOOK_COPIES(Book_id integer,Branch_id integer,No_of_Copies integer, primary key(Book_id,Branch_id),foreign key(Book_id) references BOOK(Book_id),foreign key(Branch_id) references LIBRARY_BRANCH(Branch_id));
create table BOOK_LENDING(Book_id integer,Branch_id integer,Card_No integer,Date_Out integer,Due_Date integer,primary key(Book_id,Branch_id,Card_No),foreign key(Book_id) references BOOK(Book_id),foreign key(Branch_id) references LIBRARY_BRANCH(Branch_i
