Simple SQL queries

    SELECT *             # all columns
    FROM SamplePlan      # table name
    ORDER BY Year DESC   # column name
    
View the most recent API queries

    SELECT * FROM [api].[DataApi_Audit]
    order by ExecutionTime desc
