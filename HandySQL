--XML 
use Intelligence_FO
select top 100 b.*,o.h.value('.','varchar(100)') 
from dm.errorlog b
cross apply  Data.nodes('/Error[1]/ErrorMessage[1]') as o(h)
where b.[ERROR_MESSAGE] ='MesageForwarder'
and o.h.value('.','varchar(100)') like 'Transaction count after EXECUTE%'
order by 1 desc

--进制转换
select CONVERT(bigint, CONVERT(varbinary, CAST(N'0x0000000000000400'  AS char), 1))
set @num2=convert(varbinary(8),123)--直接转换为二进制 
set @r= dbo.varbin2hexstr(@num2)--

select dbo.varbin2hexstr(convert(varbinary(8),123))--

--查看进程命令text
 select text from sys.dm_exec_connections ec1
  CROSS APPLY sys.dm_exec_sql_text(ec1.most_recent_sql_handle) AS h1
 where session_id=235
