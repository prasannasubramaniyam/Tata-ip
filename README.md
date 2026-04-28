# Tata-ip
Csk_analysis
Create table  cskans (
player_name varchar (10),
player_num int,
player_runs int,
strike_rate int,
player_ground varchar(15) 
);
insert into cskans ( Player_Name, Player_Num, Player_Runs, Strike_Rate,Player_Ground) 
values
('Rutu',31,2000,100,'csk'),
('Dhoni',7,5000,135,'csk'),
('Jadeja',8,2500,130,'csk'),
('Conway',88,1800,145,'sk'),
('Dube',25,1500,150,'csk');

--- Top Scorer In Csk ---
select	player_name,player_runs
from cskans where player_ground ="csk"
order by player_runs desc
limit 2;

--- Highest Strike Rate ---
select player_name, strike_rate
from cskans 
where player_ground="csk"
order by strike_rate desc
limit 1;

--- Top 4 Runs Scorers ---
select player_name, player_runs
from cskans
where player_ground="csk"
order by player_runs desc
limit 4;

--- Average Runs Of Csk Players ---
select player_name, player_runs
from cskans
where player_ground="csk"
order by player_runs desc
limit 5;

--- Player With Lowest Strike Rate ---
select player_name, strike_rate
from cskans
where player_ground="csk"
order by strike_rate asc
limit 2;

--- Total Runs By CSK Team ---
select sum (player_runs) as total_runs
from cskans
where player_ground="csk"
;

--- Count Of Players In csk
Select Count As total_players
from cskans 
where player_ground="csk"
;

--- Players With Strike Rate Above 140 ---
select player_name, strike_rate
from cskans
where player_ground= "csk"
and strike_rate>140;

--- Second Highest Run Scorer ---
--- Interview Question ---
select player_name,player_runs
from cskans
where player_ground="csk"
order by player_runs desc
limit 2 offset 2;

--- Rank Players By Runs ---
select player_name,player_runs,
rank() over (order by player_runs desc) as
rank_position
from cskans
where player_ground = "csk"





