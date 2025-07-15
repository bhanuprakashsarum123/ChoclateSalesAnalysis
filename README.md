
# Choclate Sales Analysis-Dashboard

### Dashboard Link :[App power BI link] (https://app.powerbi.com/view?r=eyJrIjoiZTE5N2NmNTktN2VmZi00Y2IwLTg3MjMtMjM3YjI2NDkwZjkwIiwidCI6ImFkM2IzZDdjLTliMTAtNDhmZC1hMWFlLWRlZTVhMGJjZmVjNiJ9)

## Problem Statement

This Dashboard helps to understand the full year of choclate sales 
along with KPI's of Total Sales,Total Cost,Total Proft,Total Boxes,Total Shipments

A detailed table highlights salesperson performance — identifying those who met, almost met, or did not meet their targets.
A similar analysis is done for products, showing sales and profit by product and whether they achieved their targets.

A line chart illustrates month-over-month trends in sales, enabling quick identification of seasonal patterns.

Slicers allow users to filter data by Product Category and Country for more focused analysis.

A column chart displays the number of boxes sold alongside total shipments (e.g., shipments of 20 boxes, 40 boxes, etc.), helping visualize product distribution scale.
### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a Excel file.
- Step 2 : Open power query editor & in view tab under Data preview section, Extract year,month,start of month,month name,day name 
- Step 3 : Created a seperate table for measures,i created Total Sales,Total Cost,Total Proft,Total Boxes,Total Shipments and added card visual for all of them. 
- Step 4 : Created profit % and displayed with gauge visual and set the target % = 0.6

        Profit % = DIVIDE([Total Profit],[Total Sales])

- Step 5 : After i created a field parameters for Total Sales,Total Cost,Total Proft,Total Boxes,Total Shipments in modeling tab named as a Measure Selector added to the new slicer.

- Step 6 : Created the line chart with start of month column in x-axis and  Measure selector in y-axis,so we can analyse month on month trends.
- Step 7 : Added a group for boxes bins column in shipments table ,displayed clustered column chart boxes(bins) in x-axis,total shipments in y-axis,it shows no of boxes and their total shipments included zoom slicer for x-axis.
- Step 8 : Added some measures Low box shipments,Lbs % ,set profit target = 0.6,Profit target indicator 

        LowBox Shipments = CALCULATE([Total Shipments],shipments[Boxes]<50) 
        Lbs % = DIVIDE([LowBox Shipments],[Total Shipments]) 
        Profit Target Indicator = IF([Profit %]>[Profit Target],2,IF([Profit %]>0.9*[Profit Target],1,0)) 

- Step 9 :Added a two tables for salesperson,products added name,sales,profit %,Lbs % ,Profit Target indicator to them,applied conditional formating to profit target indicator check marks.
- Step 10 : Added Icons for People,Products,i set bookmarks in view tab when click on People Icon it dispalys People Table and Click on Products Icon it displays products table. 

- Step 11 : Added two slicers,one for product category another one for Country wise by this we filter what we want to analyse.



