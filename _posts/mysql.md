 ## MySQL杂记
 ###  查看mysql版本号
   >windows下三种方式  
   >命令行中 mysql --help  
   > mysql命令状态下 status;  
   > mysql命令状态下 select version();  
   > linux下三种方式
   > mysql --help |grep Distrib  
   > 其余两种和windos mysql命令状态下相同
 ###  查看当前服务器支持的存储引擎
   > SHOW ENGINES;
 ###  创建表时指定存储引擎 
   > CREATE TABLE 表名(  
   >     建表语句;  
   >) ENGINE = 存储引擎名称;
 ###  修改表的存储引擎
   > ALTER TABLE 表名 ENGINE = 存储引擎名称;
 ###  查看表结构
   > SHOW CREATE TABLE 表名\G
 ###  InnoDB行格式
   > 四种：Compact,Redundant,Dynamic,Compressed
 ###  指定行格式语法
   > CREATE TABLE 表名 (列的信息) ROW_FORMAT=行格式名称  
   > ALTER TABLE 表名 ROW_FORMAT=行格式名称
 
   