# Apache_Impala
## Link to the repo: 
https://github.com/JyoshnaBoppidi/Apache_Impala
## Link to Slides:
[Impala Slides](https://docs.google.com/presentation/d/1j797ysLV1gGasFlRr8NAfWPal49MVNxaaPqGIWR9gJg/edit?usp=sharing)

![](https://github.com/JyoshnaBoppidi/Apache_Impala/blob/master/teammembers.PNG)

## To start Impala:
- Open the clodera VM and type the command impala-shell.
- You can also communicate through Hue Query editor.Once you enter the VM, open the web browser where you can find Hue. Click on that.
## To see the databases present in Impala:
show databases;

## creating a database

create database bigdata_demo;

## creating a table

create table my_list(Name String);

## loading data into hive warehouse

hadoop fs -put impala_input.txt /user/hive/warehouse

load data inpath '/user/hive/warehouse/impala_input.txt' into table my_list;

## Spliting the data into mulitple rows

create table wordCount as select regexp_replace(Name,' ','\n') as word from my_list;

## counting wordcount for each word

select word, count(*) from wordCount group by word order by word; 

## Reference

https://www.tutorialspoint.com/impala/index.htm

https://www.simplilearn.com/working-with-hive-and-impala-tutorial

https://www.youtube.com/watch?v=3PgpOZ8SpLA

https://www.educba.com/hive-vs-impala/

