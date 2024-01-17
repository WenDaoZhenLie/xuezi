## 存储引擎
* InnoDB
* MyISAM

## 索引


## 锁
* 全局锁
* 表级锁
* 行级锁

## 事务
### 事务隔离
* Read uncommitted 
* Read committed 
* Repeatable read 
* Serializable 

## **序列**
```sql
create table if not exists sequence
(
    seq_name      varchar(32) not null,
    current_val   integer     not null,
    increment_val integer     not null default 1,
    primary key (seq_name)
);

create function curr_val(v_seq_name varchar(32))
    returns integer
    deterministic
begin
    declare value integer;
    set value = 0;
    select current_val into value from sequence where seq_name = v_seq_name;
    return value;
end;

create function next_val(v_seq_name varchar(50))
    returns integer
    deterministic
begin
    update sequence set current_val = current_val + increment_val where seq_name = v_seq_name;
    return curr_val(v_seq_name);
end;
```