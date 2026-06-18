# Scott - schema ( PostgreSQL )

```sql
-- postgreSQL
CREATE SCHEMA scott;
SET search_path TO scott;

CREATE TABLE dept (
    deptno INTEGER PRIMARY KEY,
    dname  VARCHAR(14),
    loc    VARCHAR(13)
);
CREATE TABLE emp (
    empno    INTEGER PRIMARY KEY,
    ename    VARCHAR(10),
    job      VARCHAR(9),
    mgr      INTEGER,
    hiredate DATE,
    sal      NUMERIC(7,2),
    comm     NUMERIC(7,2),
    deptno   INTEGER,
    CONSTRAINT fk_emp_dept
        FOREIGN KEY (deptno)
        REFERENCES dept(deptno),
    CONSTRAINT fk_emp_mgr
        FOREIGN KEY (mgr)
        REFERENCES emp(empno)
);
CREATE TABLE salgrade (
    grade INTEGER PRIMARY KEY,
    losal NUMERIC,
    hisal NUMERIC
);
CREATE TABLE bonus (
    ename VARCHAR(10),
    job   VARCHAR(9),
    sal   NUMERIC,
    comm  NUMERIC
);

INSERT INTO dept (deptno, dname, loc) VALUES
(10, 'ACCOUNTING', 'NEW YORK'),
(20, 'RESEARCH',   'DALLAS'),
(30, 'SALES',      'CHICAGO'),
(40, 'OPERATIONS', 'BOSTON');

INSERT INTO emp (empno, ename, job, mgr, hiredate, sal, comm, deptno) VALUES
(7369, 'SMITH',  'CLERK',     7902, DATE '1980-12-17',  800, NULL, 20),
(7499, 'ALLEN',  'SALESMAN',  7698, DATE '1981-02-20', 1600,  300, 30),
(7521, 'WARD',   'SALESMAN',  7698, DATE '1981-02-22', 1250,  500, 30),
(7566, 'JONES',  'MANAGER',   7839, DATE '1981-04-02', 2975, NULL, 20),
(7654, 'MARTIN', 'SALESMAN',  7698, DATE '1981-09-28', 1250, 1400, 30),
(7698, 'BLAKE',  'MANAGER',   7839, DATE '1981-05-01', 2850, NULL, 30),
(7782, 'CLARK',  'MANAGER',   7839, DATE '1981-06-09', 2450, NULL, 10),
(7788, 'SCOTT',  'ANALYST',   7566, DATE '1987-04-19', 3000, NULL, 20),
(7839, 'KING',   'PRESIDENT', NULL, DATE '1981-11-17', 5000, NULL, 10),
(7844, 'TURNER', 'SALESMAN',  7698, DATE '1981-09-08', 1500,    0, 30),
(7876, 'ADAMS',  'CLERK',     7788, DATE '1987-05-23', 1100, NULL, 20),
(7900, 'JAMES',  'CLERK',     7698, DATE '1981-12-03',  950, NULL, 30),
(7902, 'FORD',   'ANALYST',   7566, DATE '1981-12-03', 3000, NULL, 20),
(7934, 'MILLER', 'CLERK',     7782, DATE '1982-01-23', 1300, NULL, 10);

INSERT INTO salgrade (grade, losal, hisal) VALUES
(1,  700, 1200),
(2, 1201, 1400),
(3, 1401, 2000),
(4, 2001, 3000),
(5, 3001, 9999);
```

```sql
-- mySQL 
CREATE DATABASE SCOTT ;
USE SCOTT;
DROP TABLE IF EXISTS emp;
CREATE TABLE emp
(
 empno decimal(4,0) NOT NULL,
 ename varchar(10) default NULL,
 job varchar(9) default NULL,
 mgr decimal(4,0) default NULL,
 hiredate date default NULL,
 sal decimal(7,2) default NULL,
 comm decimal(7,2) default NULL,
 deptno decimal(2,0) default NULL
);
DROP TABLE IF EXISTS dept;
CREATE TABLE dept (
 deptno decimal(2,0) default NULL,
 dname varchar(14) default NULL,
 loc varchar(13) default NULL
);

INSERT INTO emp VALUES
('7369','SMITH','CLERK','7902','1980-12-17','800.00',NULL,'20'),
('7499','ALLEN','SALESMAN','7698','1981-02-20','1600.00','300.00','30'),
('7521','WARD','SALESMAN','7698','1981-02-22','1250.00','500.00','30'),
('7566','JONES','MANAGER','7839','1981-04-02','2975.00',NULL,'20'),
('7654','MARTIN','SALESMAN','7698','1981-09-28','1250.00','1400.00','30'),
('7521','WARD','SALESMAN','7698','1981-02-22','1250.00','500.00','30'),
('7566','JONES','MANAGER','7839','1981-04-02','2975.00',NULL,'20'),
('7654','MARTIN','SALESMAN','7698','1981-09-28','1250.00','1400.00','30'),
('7698','BLAKE','MANAGER','7839','1981-05-01','2850.00',NULL,'30'),
('7782','CLARK','MANAGER','7839','1981-06-09','2450.00',NULL,'10'),
('7788','SCOTT','ANALYST','7566','1982-12-09','3000.00',NULL,'20'),
('7839','KING','PRESIDENT',NULL,'1981-11-17','5000.00',NULL,'10'),
('7844','TURNER','SALESMAN','7698','1981-09-08','1500.00','0.00','30'),
('7876','ADAMS','CLERK','7788','1983-01-12','1100.00',NULL,'20'),
('7900','JAMES','CLERK','7698','1981-12-03','950.00',NULL,'30'),
('7902','FORD','ANALYST','7566','1981-12-03','3000.00',NULL,'20'),
('7934','MILLER','CLERK','7782','1982-01-23','1300.00',NULL,'10');

INSERT INTO dept VALUES 
('10','ACCOUNTING','NEW YORK'),
('20','RESEARCH','DALLAS'),
('30','SALES','CHICAGO'),
('40','OPERATIONS','BOSTON');
```