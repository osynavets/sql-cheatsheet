# sql-cheatsheet

## SQL Server
- finding database by table name

select [name] as [database_name] from sys.databases 
where 
    case when state_desc = 'ONLINE' 
        then object_id(quotename([name]) + '.[dbo].[table_name_we_have]', 'U') 
    end is not null
order by 1
