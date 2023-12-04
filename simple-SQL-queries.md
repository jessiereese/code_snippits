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

Select rows that have more than one distinct value for a given column (here it is PointVisitID, to determine if there are surveys which are duplicated).

    SELECT DISTINCT Point, TransectNum, DATE, TransectVisitObserver, PointVisitID, TransectVisitID, TransectVisitExcludeAnalysis, PointVisitSkippedPointsReason
    FROM api.base
    WHERE PointVisitID IN (SELECT PointVisitID FROM api.base GROUP BY PointVisitID HAVING COUNT(*) > 1)  AND SelectionMethod <> 'PLMX'

Join on multiple criteria

    SELECT DISTINCT(api.bird.TransectNum), api.bird.Point, TransectVisitObserver, api.bird.DATE, isPublic, isPrivate, firstName, lastName, bussinessOwner
    FROM api.bird
    LEFT JOIN LandownerLand ON (LandownerLand.TransectNum = api.bird.TransectNum AND LandownerLand.Point = api.bird.Point)
    LEFT JOIN Landowner ON LandownerLand.landownerID = Landowner.LandownerID
    WHERE TransectVisitObserver = 'AROSH'
    ORDER BY api.bird.TransectNum, api.bird.Point
