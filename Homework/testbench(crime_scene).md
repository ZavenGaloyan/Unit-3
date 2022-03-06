# Code 
'''sql
--query the database to know what is inside
select * from person limit 1;

--find all names starting with C
select name, id from person where name like 'C%';
select count(name)from person where name like 'C%';
select name, ssn from person where name like 'Waldo Oleksa%';
--find the highest income
select max(annual_income), ssn from income;
select * from person where ssn = 361660921;
select ssn, annual_income from income order by annual_income desc limit 5;
select name from person  where  ssn= 541217354;
--income above 35k
select  count(annual_income) from income where annual_income >100000;
select  count(annual_income) from income where annual_income <35000;
select  count(annual_income) from income where annual_income =35000;

'''
'''sql
# HW: code to find number of crime related to nudism/nudist
--how many murder cases related to nudism
select * from  facebook_event_checkin where event_name like '%nudi%';
select count() from  facebook_event_checkin where event_name like '%nudi%';
select count() from  crime_scene_report where crime_scene_report.description like '%nudist%';
select count() from  crime_scene_report where crime_scene_report.description like '%nudism%';
'''


# Test for homework

## Test for all facebook event name include the word nudi and its count

<img width="1440" alt="count" src="https://user-images.githubusercontent.com/82266864/156921634-450cde04-1702-4332-972f-a7d05e186cb4.png">

<img width="1440" alt="count2" src="https://user-images.githubusercontent.com/82266864/156921648-b30bcf69-de36-4602-95e6-2b9e913c731f.png">

## Test for number of crime description that include the work nudism or nudist

<img width="1440" alt="count3" src="https://user-images.githubusercontent.com/82266864/156921666-8ca343f2-c14e-4a0e-8ace-a866b9f0260e.png">
<img width="1440" alt="count4" src="https://user-images.githubusercontent.com/82266864/156921668-a58f373e-5745-4c2c-8020-67382e74b830.png">



