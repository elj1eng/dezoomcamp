# Data Engineering Zoomcamp - Homework 1

**Author:** elj1eng  
**Submission Date:** April 21, 2026

## Question 1
**Answer:** 25.3

## Question 2
**Answer:** db:5433

## Question 3
**Answer:** 8007

**Query:**
```sql
SELECT COUNT(*) FROM green_trip_data 
WHERE "lpep_pickup_datetime" BETWEEN '2025-11-01' AND '2025-12-01' 
AND "trip_distance" <= 1;
```

## Question 4
**Answer:** 2025-11-14

**Query:**
```sql
SELECT "lpep_pickup_datetime" FROM green_trip_data 
WHERE "trip_distance" <= 100 
ORDER BY "trip_distance" DESC 
LIMIT 1;
```

## Question 5
**Answer:** East Harlem North

**Query:**
```sql
SELECT "Zone" FROM green_trip_data g 
JOIN taxi_zone_lookup t ON g."PULocationID" = t."LocationID" 
GROUP BY "Zone" 
ORDER BY COUNT(*) DESC 
LIMIT 1;
```

## Question 6
**Answer:** Yorkville West

**Query:**
```sql
SELECT t_do."Zone" FROM green_trip_data g 
JOIN taxi_zone_lookup t_pu ON g."PULocationID" = t_pu."LocationID" 
JOIN taxi_zone_lookup t_do ON g."DOLocationID" = t_do."LocationID" 
WHERE "lpep_pickup_datetime" BETWEEN '2025-11-01' AND '2025-12-01' 
AND t_pu."Zone" = 'East Harlem North' 
ORDER BY "tip_amount" DESC 
LIMIT 1;
```

## Question 7
**Commands:**
```bash
terraform init
terraform apply -auto-approve
terraform destroy
```