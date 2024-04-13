# EVERYTHING-DATA--PAIR-PROJECT
**Project Overview**

An analysis of world statistics to gain insights on population distribution.

**Data Analysis**

	The human resource data was obtained from Kaggle website.

	The data was clean and did not require any cleaning.

	Used SQL to write queries which provide the needed data.

	Used power BI for visualization

**Analysis Questions**

1.	What is the size of each continent?
2.	What is the 2023 population of each continent?
3.	What is the population growth over the periods?
4.	Total population per census period
5.	2023 top 10 populous countries
6.	2023 top 10 populous cities
7.	Largest continent
8.	Largest city by size
9.	Largest city by population
10.	Smallest continent
11.	Smallest city by size
12.	Smallest city by population

  **  SQL Queries**

**  ----1.	What is the size of each continent?**

select Continent, sum(Area_km) as Total_Area from [World Population]
group by Continent
order by Total_Area Desc
 
**----2.	What is the 2023 population of each continent?**

select Continent, sum(Yr_2023) as Total_Population from [World Population]
group by Continent
order by Total_Population Desc
 

----3.	What is the 2023 global population? 

select sum(Yr_2023) as '2023 Global Population' from [World Population]

 
----4.	Total population per census period

select Continent, sum(Yr_1950) as Population_1950, sum(Yr_1960) as Population_1960, sum(Yr_1970) as Population_1970,
sum(Yr_1980) as Population_1980, sum(Yr_1990) as Population_1990, sum(Yr_2000) as Population_2000, 
sum(Yr_2010) as Population_2010, sum(Yr_2020) as Population_2020, sum(Yr_2023) as Population_2023 from [World Population]
group by Continent
order by Population_1950 Desc

 
----5.	2023 top 10 populous countries

select top 10 country, sum(Yr_2023) as Population_2023 from [World Population]
group by country
order by Population_2023 desc 

 
--6.	2023 top 10 populous cities

select top 10 Capital, sum(Yr_2023) as Population_2023 from [World Population]
group by Capital
order by Population_2023 desc
 
--7.	Largest continent
select top 1 Continent as Largest_Continent_By_Size

FROM ( SELECT Continent, SUM(Area_km) AS Total_Area from [World Population] group by Continent) as Largest 
order by largest.Total_Area desc ;
 
--8.	Largest city by size

select top 1 Capital as Largest_City_By_Size

FROM ( SELECT Capital, SUM(Area_km) AS Total_Area from [World Population] group by Capital) as Largest 
order by largest.Total_Area desc ;
 
--9.	Largest city by population

select top 1 Capital as Largest_City_By_Population

FROM ( SELECT Capital, SUM(Yr_2023) AS Total_Population from [World Population] group by Capital) as Largest 
order by largest.Total_Population desc ;
 
--10.	Smallest continent

select top 1 Continent as Smallest_Continent_By_Size

FROM ( SELECT Continent, SUM(Area_km) AS Total_Area from [World Population] group by Continent) as Largest 
order by largest.Total_Area asc ;
 
--11.	Smallest city by size

select top 1 Capital as Smallest_City_By_Size

FROM ( SELECT Capital, SUM(Area_km) AS Total_Area from [World Population] group by Capital) as Largest 
order by largest.Total_Area asc ;

 
--12.	Small city by population

select top 1 Capital as Smallest_City_By_Population

FROM ( SELECT Capital, SUM(Yr_2023) AS Total_Population from [World Population] group by Capital) as Largest 
order by largest.Total_Population asc ;

**Analysis Findings**

	Asia is the largest continent in size while Oceania is the smallest.

	Asia is the most populous Continent as per 2023 statistics.

	India has the highest population followed by China

	Moscow is the largest City in Size While New Delhi is the largest in population.

	Monaco City is the smallest in size while Nukonunu is smallest by population

	As per 2023 statistics, global population is 8B

 

