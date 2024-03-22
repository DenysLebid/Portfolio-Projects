### My First project

# SQL query

SELECT 
  rent_tbl.city, 
  ROUND(AVG(rent_tbl.price), 2) AS avg_rent_price,
  ROUND(AVG(apart_tbl.price), 2) AS avg_apartment_price,
  ROUND(AVG(apart_tbl.price) / (12 * AVG(rent_tbl.price)), 1) AS approx_years_to_cover_cost
FROM 
  `my-data-project-1054.Apartments_data_Pl.apartments_rent_pl_2024_02` AS rent_tbl
INNER JOIN 
  `my-data-project-1054.Apartments_data_Pl.apartments_pl_2024_02` AS apart_tbl
  ON rent_tbl.city = apart_tbl.city
GROUP BY 
  rent_tbl.city
ORDER BY 
  avg_rent_price ASC;
