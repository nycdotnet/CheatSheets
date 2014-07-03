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


