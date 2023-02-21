# Simple SQL queries

View a full table and sort

    SELECT *             # all columns
    FROM SamplePlan      # table name
    ORDER BY Year DESC   # column name
    
View the most recent API queries

    SELECT * FROM [api].[DataApi_Audit]
    order by ExecutionTime desc

Join two tables and filter

    SELECT *
    FROM TransectVisit
    LEFT JOIN Transect
        ON TransectVisit.TransectID = Transect.TransectID
        WHERE TransectNum LIKE 'PLJV-GMKS-AG%'
