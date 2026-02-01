# Homework 2: Workflow Orchestration for Data Engineering Zoomcamp 2026


## Question 1. Within the execution for Yellow Taxi data for the year 2020 and month 12: what is the uncompressed file size (i.e. the output file yellow_tripdata_2020-12.csv of the extract task)?

## Answer 1.

<img width="542" height="502" alt="image" src="https://github.com/user-attachments/assets/5fa278f2-fd22-4ffd-97e8-4c6447ac0ff9" />


## Question 2. What is the rendered value of the variable file when the inputs taxi is set to green, year is set to 2020, and month is set to 04 during execution? (1 point)

## Answer 2. 

<img width="1172" height="227" alt="image" src="https://github.com/user-attachments/assets/1ea03e35-1b22-4cb1-82cc-4a76bc4e8d93" />


## Question 3. How many rows are there for the Yellow Taxi data for all CSV files in the year 2020? (1 point)

## Answer 3.

`SELECT COUNT(*) AS total_rows
FROM `zoomcamp.yellow_tripdata`
WHERE EXTRACT(YEAR FROM tpep_pickup_datetime) = 2020;`

<img width="250" height="166" alt="image" src="https://github.com/user-attachments/assets/630ed532-2b69-486d-b5cb-3c4019998b92" />


## Question 4. How many rows are there for the Green Taxi data for all CSV files in the year 2020? (1 point)

## Answer 4.

`SELECT COUNT(*) AS total_rows
FROM `zoomcamp.green_tripdata`
WHERE EXTRACT(YEAR FROM lpep_pickup_datetime) = 2020;`

<img width="252" height="142" alt="image" src="https://github.com/user-attachments/assets/2a7d2222-28d0-4f1b-a0a3-81864ee5eb6c" />

## Question 5. How many rows are there for the Yellow Taxi data for the March 2021 CSV file? (1 point)

## Answer 5. 

`SELECT COUNT(*) AS total_rows
FROM `zoomcamp.yellow_tripdata_2021_03`;`

<img width="238" height="157" alt="image" src="https://github.com/user-attachments/assets/c25f05ba-6814-4aef-b2cd-0b67eef37aa3" />

## Question 6. How would you configure the timezone to New York in a Schedule trigger? (1 point)

## Answer 6.

<img width="828" height="35" alt="image" src="https://github.com/user-attachments/assets/306434f9-b2b3-4087-8c69-db0387dddb45" />













