create table person ( driver_id varchar2(10), name varchar2(20), address varchar2(15), PRIMARY KEY(driver_id) );

create table car ( regno varchar2(10), model varchar2(10), year number(4), PRIMARY KEY(regno) );

create table accident ( report_no number(5), adate date, location varchar2(15), PRIMARY KEY(report_no));

create table owns ( driver_id varchar2(10), regno varchar2(10), PRIMARY KEY(driver_id, regno), FOREIGN KEY(driver_id)REFERENCES person(driver_id), FOREIGN KEY(regno) REFERENCES car(regno));

create table participated ( driver_id varchar2(10), regno varchar2(10), report_no number(5), damage_amt number(7,2), PRIMARY KEY(driver_id, regno, report_no), FOREIGN KEY(driver_id, regno) REFERENCES owns(driver_id, regno) on delete cascade, FOREIGN KEY(report_no) REFERENCES accident(report_no) on delete cascade);

desc person;
desc car;
desc accident;
desc owns;
desc participated;

insert into person values('1111','ramu','k.s.layout');
insert into person values('2222','john','indiranagar');
insert into person values('3333','priya','jayanagar');
insert into person values('4444','gopal','whitefield');
insert into person values('5555','latha','vijayanagar');

insert into car values('ka04q2301','maruthi-dx',2000);
insert into car values('ka05p1000','fordicon',2000);
insert into car values('ka03l1234','zen-vxi',1999);
insert into car values('ka03l9999','maruth-dx',2002);
insert into car values('ka01p4020','indica-vx',2002);

insert into accident values(12,'01-jun-02','mg road');
insert into accident values(200,'10-dec-02','doubleroad');
insert into accident values(300,'23-jul-99','mg road');
insert into accident values(25000,'11-jun-00','residency road');
insert into accident values(26500,'16-oct-01','richmond road');

insert into owns values('1111','ka04q2301');
insert into owns values('1111','ka05p1000');
insert into owns values('2222','ka03l1234');
insert into owns values('3333','ka03l9999');
insert into owns values('4444','ka01p4020');

insert into participated values('1111','ka04q2301',12,20000);
insert into participated values('2222','ka03l1234',200,500);
insert into participated values('3333','ka03l9999',300,10000);
insert into participated values('4444','ka01p4020',25000,2375);
insert into participated values('1111','ka05p1000',26500,70000);
insert into participated values('2222','ka03l9999',12,10000);

desc person;
select * from person;
select * from car;
select * from accident;
select * from owns;
select * from participated;

update participated set damage_amt=25000 where report_no=12 and regno='ka04q2301';

select * from participated;

insert into accident values( 500, '25-oct-99','basavanagudi');
select * from accident;

SELECT COUNT(*) FROM ACCIDENT
WHERE ADATE LIKE '__-___-02';

SELECT COUNT(A.REPORT_NO)

FROM ACCIDENT A, PARTICIPATED P, CAR C

WHERE A.REPORT_NO=P.REPORT_NO

AND

P.REGNO=C.REGNO

AND

C.MODEL='MARUTHI-DX';
