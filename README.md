# Action-Movies
Are Action movies profitable? 
If they are - what type is the most profitable?

For Action movies Data Analysis, I used the IMDB website and report builder. Also, data was scraped from the Numbers and Mediaversity website.
When data was collected and imported into Excel, I inserted two additional rows and created formulas for ROI and PROI (for more appealing visual effects).
After that, it was imported into SQL and joined with the following SQL query:

SELECT basics.tconst, basics.startYear, basics.primaryTitle, rois.CreativeType, actionm.ActionType,
rian05.GenderLead, rian05.Profitable, rian05.InflAdjDomBO, rian05.BreakevenPoint, rian05.DiverseCast, rian05.ProductionMethod,
rois.ProductionBudget, rois.DomesticBoxOffice, rois.WorldwideBoxOffice, 
ratings.averageRating, rois.ROI, rois.PROI, opweek.TheatricalEngagements, opweek.OpeningWeekend
 
FROM basics

JOIN ratings on basics.tconst =	ratings.tconst

JOIN rois on basics.primaryTitle = rois.primaryTitle

JOIN rian05 on basics.primaryTitle = rian05.primaryTitle

JOIN opweek on basics.primaryTitle = opweek.primaryTitle

JOIN actionm on basics.startYear = actionm.startYear!

With this query, I was able to extract and create a new report and use the same in Orange and Power Bi.
In Orange, I used K-Means and Linear Projection as Machine Learning methods for statistical analysis.
Based on the K-Means method analysis - Action movies are high-earning movie genres Domestic and Worldwide, and Super Hero movies are the highest-earning type of Action movies.
To confirm the previous Analysis, I used Linear Projection and incorporated additional factors: PROI, Inflation Adjustment, Average Ratings, Theatrical Engagements, Open Week, Breakeven Point, and Start Year. 
When all incorporated and based on Linear Projection, Action movies were still showing as profitable, and the only loss was in the Theatrical Engagement area.
To get a better visual perspective, I used PowerBi, which clearly identifies profit in Super Hero movies. 

Attach is also a PowerPoint presentation of this project for better visual and story flow comprehension. 
