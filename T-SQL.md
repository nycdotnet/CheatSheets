T-SQL
=====

**Test a bit**

    SELECT 512 & 2
    --Returns INT 0
    
    SELECT 514 & 2
    --Returns INT 2
    
    
**String to DateTime**

DECLARE @Time CHAR(14) = '20141231010203';

SELECT CAST(SUBSTRING(@Time,1,4) + '-' +
       SUBSTRING(@Time,5,2) + '-' +
       SUBSTRING(@Time,7,2) + 'T' +
       SUBSTRING(@Time,9,2) + ':' +
       SUBSTRING(@Time,11,2) + ':' +
       SUBSTRING(@Time,13,2) AS DATETIME2);


**Useful Dates**

    --Thanks to BIT Barbarian: http://www.sqlservercentral.com/blogs/bit-barbarian/2014/08/12/snippet-alert-useful-dates-eom-bom-etc/
    declare @Date date = getdate()
    select  
        previous_month_bom =    dateadd(month, datediff(month, 0, @Date) - 1, 0) --previous_month_bom
        ,previous_month_eom =   dateadd(day, -1, dateadd(month, datediff(month, 0, @Date), 0)) -- previous_month_eom 
        ,bom =                  dateadd(month, datediff(month, 0, @Date), 0) -- bom 
        ,eom =                  dateadd(month, datediff(month, 0, @Date) + 1, -1) -- eom 
        ,next_bom =             dateadd(month, datediff(month, 0, @Date) + 1, 0) -- next_bom 
        ,next_eom =             dateadd(day, -1, dateadd(month, datediff(month, 0, @Date) + 2, 0)) -- next_eom 