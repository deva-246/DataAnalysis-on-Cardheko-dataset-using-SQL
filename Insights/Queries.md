use secondhandcardealer;
select * from secondhandcardealer.car_dekho;

## Total cars
select count(*) from car_dekho;

## Cars available in 2023    
select count(*) from secondhandcardealer.car_dekho where year=2023;

## 2020,2021,2022 cars availability 
select year as 'Year' ,count(*) as 'No.of cars' from secondhandcardealer.car_dekho where year in (2020,2021,2022) group by year;

## Total of all cars by year
select Year,count(*) as 'No.of Cars' from secondhandcardealer.car_dekho group by year; 

## How many diesel cars in 2020 
select count(*) as 'Diesel cars in 2020' from secondhandcardealer.car_dekho where fuel = 'Diesel' and year=2020;

## Petrol car count in 2020 
 select count(*) as 'Petrol cars in 2020' from secondhandcardealer.car_dekho where fuel = 'Petrol' and year=2020;
 
## All cars w.r.t fuels by year 
select distinct(fuel) from secondhandcardealer.car_dekho;

## Fuel Based cars induvidual and group reports

select year, count(*)  as 'Diesel Cars' from secondhandcardealer.car_dekho  where fuel='Diesel' group by year;

select year, count(*) as 'Petrol Cars' from secondhandcardealer.car_dekho  where fuel='Petrol' group by year;

select year, count(*) as 'Electric Cars' from secondhandcardealer.car_dekho  where fuel='Electric' group by year;

select year, count(*) as 'CNG Cars' from secondhandcardealer.car_dekho  where fuel='CNG' group by year;

select year, count(*) as 'LPG Cars' from secondhandcardealer.car_dekho  where fuel='LPG' group by year;

-- common report -- 

select year,fuel,count(*) as 'No.of cars' from secondhandcardealer.car_dekho  group by fuel,year;


## Year which has more than one hundred cars 
with high as
(select year,count(*) as 'c' from secondhandcardealer.car_dekho group by year
having count(*) > 100)

select c,year from high where c = (select max(c) from high);

## Count Details of cars between 2015 and 2023 
select count(*) from secondhandcardealer.car_dekho where year between 2015 and 2023; 

## Details 
select * from secondhandcardealer.car_dekho where year between 2015 and 2023; 








