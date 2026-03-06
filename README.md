# 🎯 Master SQL Server From A to Z

## A Comprehensive Guide from Beginner to Advanced Level

---

## 📖 Table of Contents

1. [Introduction](#1-introduction)
2. [Prerequisites](#2-prerequisites)
3. [Chapter 1: SQL Server Architecture](#3-chapter-1-sql-server-architecture)
4. [Chapter 2: Installation and Configuration](#4-chapter-2-installation-and-configuration)
5. [Chapter 3: Database Fundamentals](#5-chapter-3-database-fundamentals)
6. [Chapter 4: SQL Server Data Types](#6-chapter-4-sql-server-data-types)
7. [Chapter 5: Creating and Managing Tables](#7-chapter-5-creating-and-managing-tables)
8. [Chapter 6: Constraints](#8-chapter-6-constraints)
9. [Chapter 7: Basic Queries - SELECT Statement](#9-chapter-7-basic-queries---select-statement)
10. [Chapter 8: Filtering and Sorting Data](#10-chapter-8-filtering-and-sorting-data)
11. [Chapter 9: JOINs - Combining Tables](#11-chapter-9-joins---combining-tables)
12. [Chapter 10: Aggregate Functions and GROUP BY](#12-chapter-10-aggregate-functions-and-group-by)
13. [Chapter 11: Subqueries and CTEs](#13-chapter-11-subqueries-and-ctes)
14. [Chapter 12: Data Modification - INSERT, UPDATE, DELETE, MERGE](#14-chapter-12-data-modification---insert-update-delete-merge)
15. [Chapter 13: Indexes - Performance Foundation](#15-chapter-13-indexes---performance-foundation)
16. [Chapter 14: Views](#16-chapter-14-views)
17. [Chapter 15: Stored Procedures](#17-chapter-15-stored-procedures)
18. [Chapter 16: User-Defined Functions](#18-chapter-16-user-defined-functions)
19. [Chapter 17: Triggers](#19-chapter-17-triggers)
20. [Chapter 18: Transactions and Locking](#20-chapter-18-transactions-and-locking)
21. [Chapter 19: Error Handling](#21-chapter-19-error-handling)
22. [Chapter 20: Performance Tuning](#22-chapter-20-performance-tuning)
23. [Chapter 21: Security](#23-chapter-21-security)
24. [Chapter 22: Backup and Recovery](#24-chapter-22-backup-and-recovery)
25. [Chapter 23: High Availability and Disaster Recovery](#25-chapter-23-high-availability-and-disaster-recovery)
26. [Chapter 24: SQL Server Administration](#26-chapter-24-sql-server-administration)
27. [Chapter 25: Advanced T-SQL Features](#27-chapter-25-advanced-t-sql-features)
28. [Best Practices](#28-best-practices)
29. [Common Mistakes](#29-common-mistakes)
30. [Quick Reference Cheatsheet](#30-quick-reference-cheatsheet)
31. [Additional Resources](#31-additional-resources)

---

## 1. Introduction

### What is SQL Server?

Microsoft SQL Server is a relational database management system (RDBMS) developed by Microsoft. As a database server, it is a software product with the primary function of storing and retrieving data as requested by other software applications—which may run either on the same computer or on another computer across a network (including the Internet). SQL Server supports a wide variety of transaction processing, business intelligence, and analytics applications in corporate IT environments.

SQL Server has been a cornerstone of enterprise data management since its initial release in 1989. Over the decades, it has evolved from a basic relational database to a comprehensive data platform that supports structured and semi-structured data, advanced analytics, machine learning integration, and cloud-native deployments. The product combines enterprise-grade reliability with developer-friendly features, making it suitable for organizations of all sizes.

### Why Learn SQL Server?

SQL Server remains one of the most widely used database platforms globally, powering critical applications across virtually every industry. Financial institutions rely on SQL Server for transaction processing and regulatory compliance. Healthcare organizations use it for patient record management and analytics. Retail companies leverage its capabilities for inventory management and customer insights. Government agencies depend on its security features for sensitive data management.

Learning SQL Server opens doors to multiple career paths. Database administrators (DBAs) manage and optimize SQL Server installations. Database developers design and implement database solutions. Data engineers build data pipelines and transformation processes. Business intelligence developers create reports and analytics solutions. Data scientists use SQL Server for data preparation and machine learning. Even application developers benefit from deep SQL Server knowledge when building data-driven applications.

### What You Will Learn

This comprehensive guide takes you from SQL Server fundamentals through advanced administration and optimization. You will start by understanding SQL Server architecture and installation. You will learn to design databases, write efficient queries, create stored procedures, and implement business logic. Advanced sections cover performance tuning, security, backup strategies, high availability, and administration. By completing this guide, you will have the knowledge to design, develop, and administer SQL Server solutions at a professional level.

### SQL Server Editions

Microsoft offers several SQL Server editions to meet different needs. The Enterprise edition provides the full feature set for mission-critical workloads and data warehouses. The Standard edition offers core database functionality for departments and small organizations. The Express edition is free and ideal for learning, development, and small applications. The Developer edition provides all Enterprise features for development and testing at no cost. Azure SQL Database offers SQL Server capabilities as a fully managed cloud service.

---

## 2. Prerequisites

### Required Knowledge

Before diving into SQL Server, you should have a basic understanding of relational database concepts. Know what tables, rows, and columns represent. Understand the concept of primary keys and foreign keys. Familiarity with basic set theory helps with understanding SQL operations. No prior SQL knowledge is required—we'll start from the fundamentals.

Basic computer literacy is essential. You should be comfortable using Windows or Linux operating systems. Understanding of file systems, directories, and basic networking concepts (like IP addresses and ports) will help with administration tasks. For performance tuning sections, understanding of computer memory, storage, and CPU concepts is beneficial.

### System Requirements

SQL Server runs on Windows and Linux operating systems. For learning purposes, any modern development machine can run SQL Server Express or Developer edition. Minimum requirements include a 1.4 GHz or faster processor, 1 GB of RAM (4 GB recommended), and 6 GB of available disk space. Production requirements vary significantly based on workload.

### Installation Options

You have several options for practicing SQL Server. Install SQL Server Developer Edition on your local machine for a full-featured learning environment. Use Docker containers for quick, isolated SQL Server instances. Create a virtual machine with SQL Server pre-installed. Use Azure SQL Database for a managed cloud experience. SQL Server Management Studio (SSMS) provides the primary development environment for Windows users, while Azure Data Studio works cross-platform.

---

## 3. Chapter 1: SQL Server Architecture

### Database Engine Architecture

SQL Server's architecture consists of multiple components working together to provide reliable, efficient data storage and retrieval. At its core, the Database Engine handles data storage, processing, and security. The engine comprises two main components: the Relational Engine (also called the Query Processor) and the Storage Engine.

The Relational Engine processes SQL queries and determines the most efficient method to execute each request. It parses the SQL statement, creates an execution plan, and coordinates query execution. The optimizer, a crucial component of the Relational Engine, evaluates multiple execution strategies and selects the most efficient one based on available indexes, data distribution statistics, and system resources.

The Storage Engine manages all data storage and retrieval operations. It handles database files, manages memory buffers, implements locking and concurrency controls, and ensures transaction durability through the transaction log. The Storage Engine works closely with the operating system to optimize I/O operations and manage system resources efficiently.

### Key Components

**Protocol Layer**: Handles network communication between clients and SQL Server. It supports multiple protocols including TCP/IP, Named Pipes, and Shared Memory. The protocol layer translates client requests into commands for the relational engine and returns results to clients.

**Query Processor**: The query processor receives SQL statements, parses them for syntax errors, binds them to database objects, and optimizes them for efficient execution. The query optimizer evaluates multiple execution plans and selects the most efficient one. The query executor then runs the selected plan.

**Buffer Pool**: The buffer pool is SQL Server's main memory area. It caches data pages read from disk, reducing physical I/O operations. The buffer pool also stores execution plans, locks, and other internal structures. Proper buffer pool sizing is crucial for performance.

**Transaction Manager**: Ensures transaction atomicity, consistency, isolation, and durability (ACID properties). It coordinates with the lock manager for concurrency control and the log manager for durability. The transaction manager implements isolation levels and handles deadlock detection.

**Lock Manager**: Implements concurrency control through locking. It manages various lock types (shared, exclusive, update, intent) at different granularities (row, page, table). The lock manager detects and resolves deadlocks automatically.

**Log Manager**: Writes transaction log records to disk, ensuring durability. It implements the Write-Ahead Logging (WAL) protocol, guaranteeing that log records are written before data pages are modified. The log manager supports point-in-time recovery and transaction rollback.

### Database Files

SQL Server databases consist of at least two files: a primary data file (.mdf) and a transaction log file (.ldf). Secondary data files (.ndf) can be added to distribute data across multiple storage devices. Understanding file organization helps with capacity planning and performance optimization.

**Primary Data File (.mdf)**: Contains database startup information and points to other files. Every database has one primary data file. User data and objects can be stored in this file, though best practice often separates them.

**Secondary Data Files (.ndf)**: Optional files for storing user data. Use secondary files to spread data across multiple drives for performance or to exceed size limits on individual drives. A database can have zero or many secondary data files.

**Transaction Log File (.ldf)**: Stores all transactions and database modifications. Essential for recovery, the log enables rollback of failed transactions and point-in-time recovery. The log file is written sequentially, which impacts recovery performance.

### Filegroups

Filegroups provide a logical grouping of database files. The primary filegroup contains the primary data file and any files not assigned to other filegroups. User-defined filegroups can group secondary files for administrative and performance purposes. Objects like tables and indexes can be placed on specific filegroups.

```sql
-- Creating database with multiple filegroups
CREATE DATABASE SalesDB
ON PRIMARY 
(
    NAME = 'SalesDB_Primary',
    FILENAME = 'C:\SQLData\SalesDB.mdf',
    SIZE = 100MB,
    MAXSIZE = UNLIMITED,
    FILEGROWTH = 10MB
),
FILEGROUP FG_Sales
(
    NAME = 'SalesDB_Sales',
    FILENAME = 'D:\SQLData\SalesDB_Sales.ndf',
    SIZE = 500MB,
    MAXSIZE = UNLIMITED,
    FILEGROWTH = 50MB
),
FILEGROUP FG_Index
(
    NAME = 'SalesDB_Index',
    FILENAME = 'E:\SQLData\SalesDB_Index.ndf',
    SIZE = 200MB,
    MAXSIZE = UNLIMITED,
    FILEGROWTH = 20MB
)
LOG ON
(
    NAME = 'SalesDB_Log',
    FILENAME = 'F:\SQLLog\SalesDB.ldf',
    SIZE = 100MB,
    MAXSIZE = UNLIMITED,
    FILEGROWTH = 10MB
);

-- Create table on specific filegroup
CREATE TABLE SalesDB.dbo.Orders
(
    OrderID INT IDENTITY(1,1) PRIMARY KEY,
    OrderDate DATETIME2 NOT NULL,
    CustomerID INT NOT NULL,
    TotalAmount DECIMAL(18,2)
) ON FG_Sales;
```

### Pages and Extents

SQL Server stores data in 8KB pages. Pages are the fundamental unit of storage and I/O. Each page contains a 96-byte header, data rows, and row offset entries. Different page types store different data: data pages, index pages, text/image pages, and various system pages.

Extents are the basic unit of space allocation. An extent consists of eight contiguous pages (64KB). Uniform extents are owned by a single object, while mixed extents can be shared by up to eight objects. New objects initially use mixed extents, then switch to uniform extents after eight pages.

### System Databases

SQL Server includes several system databases that support operations:

**master**: Records all system-level information for a SQL Server instance. Contains login accounts, linked servers, and system configuration settings. Critical for server operation—must be backed up regularly.

**model**: Template database for new database creation. Any object or setting placed in model appears in newly created databases. Customize model to establish standard database configurations.

**msdb**: Stores SQL Server Agent job definitions, schedules, operators, and history. Also stores database backup and restore history, maintenance plans, and log shipping configuration.

**tempdb**: Workspace for temporary operations. Stores temporary tables, table variables, work tables for sorting, and row versioning data. Recreated on each SQL Server restart. Critical for performance—typically placed on fast storage.

**Resource (hidden)**: Read-only database containing system objects. System stored procedures and system views are stored here. Not visible in SSMS but can be accessed through DAC (Dedicated Administrator Connection).

---

## 4. Chapter 2: Installation and Configuration

### Installation Process

SQL Server installation involves several steps. Download the installation media from Microsoft's website or your volume licensing portal. Run the setup program and select the installation type. Choose between a basic installation with default settings or a custom installation with detailed configuration options.

The feature selection page lets you choose which components to install. Database Engine Services is the core component, required for database functionality. SQL Server Agent enables job scheduling and automation. Analysis Services provides OLAP and data mining. Reporting Services offers reporting capabilities. Integration Services supports ETL operations. Select features based on your needs.

### Instance Configuration

SQL Server supports multiple instances on a single server. The default instance is accessed by the server name only. Named instances are accessed as ServerName\InstanceName. Each instance has its own set of services, security settings, and databases. Multiple instances are useful for consolidating servers while maintaining isolation.

During installation, you configure service accounts for each SQL Server service. Use domain accounts for production environments requiring network access. Use managed service accounts (MSA) or virtual accounts when possible. The Database Engine service account needs appropriate permissions on data and log directories.

### Server Configuration

Server configuration options control SQL Server behavior at the instance level. These settings affect memory usage, processor utilization, security, and connectivity. Configure server settings through sp_configure system stored procedure or SQL Server Management Studio.

```sql
-- View current configuration
EXEC sp_configure;

-- Show advanced options
EXEC sp_configure 'show advanced options', 1;
RECONFIGURE;

-- Configure max server memory (in MB)
EXEC sp_configure 'max server memory', 4096;
RECONFIGURE;

-- Configure max degree of parallelism
EXEC sp_configure 'max degree of parallelism', 4;
RECONFIGURE;

-- Configure backup compression default
EXEC sp_configure 'backup compression default', 1;
RECONFIGURE;
```

### Authentication Modes

SQL Server supports two authentication modes. Windows Authentication uses Windows accounts for login validation. It leverages Active Directory for centralized security management and supports password policies. Mixed Mode allows both Windows and SQL Server authentication. SQL Server logins store passwords in SQL Server, useful when Windows authentication isn't available.

```sql
-- Create SQL Server login
CREATE LOGIN AppUser WITH PASSWORD = 'Str0ngP@ssw0rd!';

-- Create Windows login
CREATE LOGIN [DOMAIN\UserName] FROM WINDOWS;

-- Grant server role
ALTER SERVER ROLE sysadmin ADD MEMBER [DOMAIN\DBA];

-- Create database user
USE MyDatabase;
CREATE USER AppUser FOR LOGIN AppUser;

-- Grant database permissions
ALTER ROLE db_datareader ADD MEMBER AppUser;
ALTER ROLE db_datawriter ADD MEMBER AppUser;
```

### SQL Server Management Studio

SSMS is the primary tool for SQL Server development and administration. It provides a graphical interface for database management, query writing, and server administration. Key features include Object Explorer for browsing database objects, Query Editor with IntelliSense for writing T-SQL, and graphical tools for managing indexes, security, and maintenance.

Download SSMS separately from SQL Server installation. It's updated frequently with new features and bug fixes. SSMS supports connecting to multiple SQL Server instances and versions from a single interface. Use Registered Servers to organize frequently accessed servers.

### Azure Data Studio

Azure Data Studio is a cross-platform database tool for data professionals. It runs on Windows, macOS, and Linux. Key features include a modern query editor with IntelliSense, integrated terminal, Git integration, and notebook functionality for documentation and code sharing. Azure Data Studio is particularly useful for working with Azure SQL Database and SQL Server on Linux.

---

## 5. Chapter 3: Database Fundamentals

### Creating Databases

Creating a database involves defining its name, file locations, and initial configuration. SQL Server provides defaults for most settings, but understanding and customizing these settings is important for production databases.

```sql
-- Simple database creation with defaults
CREATE DATABASE MyDatabase;

-- Database creation with full specification
CREATE DATABASE SalesDB
ON PRIMARY 
(
    NAME = 'SalesDB_Data',
    FILENAME = 'C:\SQLData\SalesDB.mdf',
    SIZE = 100MB,
    MAXSIZE = 10GB,
    FILEGROWTH = 10MB
)
LOG ON
(
    NAME = 'SalesDB_Log',
    FILENAME = 'D:\SQLLog\SalesDB.ldf',
    SIZE = 50MB,
    MAXSIZE = 2GB,
    FILEGROWTH = 10%
)
COLLATE SQL_Latin1_General_CP1_CI_AS;

-- Create database with specific options
CREATE DATABASE ArchiveDB
ON PRIMARY
(
    NAME = 'ArchiveDB_Data',
    FILENAME = 'C:\SQLData\ArchiveDB.mdf',
    SIZE = 500MB
)
LOG ON
(
    NAME = 'ArchiveDB_Log',
    FILENAME = 'D:\SQLLog\ArchiveDB.ldf',
    SIZE = 100MB
)
WITH
(
    COMPATIBILITY_LEVEL = 160,
    RECOVERY FULL,
    PAGE_VERIFY CHECKSUM
);
```

### Database Options

SQL Server databases have numerous configurable options affecting behavior, performance, and recovery. Understanding these options helps optimize databases for specific workloads.

```sql
-- Set database options
ALTER DATABASE SalesDB SET RECOVERY FULL;
ALTER DATABASE SalesDB SET PAGE_VERIFY CHECKSUM;
ALTER DATABASE SalesDB SET AUTO_CREATE_STATISTICS ON;
ALTER DATABASE SalesDB SET AUTO_UPDATE_STATISTICS ON;
ALTER DATABASE SalesDB SET COMPATIBILITY_LEVEL = 160;

-- Set database to read-only
ALTER DATABASE ArchiveDB SET READ_ONLY;

-- Set database to single-user mode
ALTER DATABASE MaintenanceDB SET SINGLE_USER WITH ROLLBACK IMMEDIATE;

-- Set database back to multi-user
ALTER DATABASE MaintenanceDB SET MULTI_USER;

-- Enable change tracking
ALTER DATABASE SalesDB SET CHANGE_TRACKING = ON
(
    AUTO_CLEANUP = ON,
    CHANGE_RETENTION = 2 DAYS
);

-- Enable snapshot isolation
ALTER DATABASE SalesDB SET ALLOW_SNAPSHOT_ISOLATION ON;
ALTER DATABASE SalesDB SET READ_COMMITTED_SNAPSHOT ON;
```

### Collation

Collation determines how string data is stored, compared, and sorted. It affects character set support, case sensitivity, accent sensitivity, and sort order. Choose collation carefully during database creation—it's difficult to change later.

```sql
-- View server collation
SELECT SERVERPROPERTY('Collation') AS ServerCollation;

-- View database collations
SELECT name, collation_name 
FROM sys.databases;

-- Create database with specific collation
CREATE DATABASE InternationalDB
COLLATE Latin1_General_100_CI_AS_SC_UTF8;

-- Common collations explained:
-- Latin1_General_CI_AS: Case-insensitive, accent-sensitive, Western European
-- SQL_Latin1_General_CP1_CI_AS: Legacy SQL collation, widely used
-- Latin1_General_100_BIN2: Binary sort, fastest comparisons
-- Latin1_General_100_CI_AS_SC: Supports supplementary characters
-- Japanese_CI_AS: Japanese collation
-- Hebrew_100_CI_AS: Hebrew collation
```

### Database Properties

Query system views and functions to retrieve database information. Understanding database metadata helps with administration and monitoring.

```sql
-- Database information
SELECT 
    name,
    database_id,
    create_date,
    compatibility_level,
    collation_name,
    user_access_desc,
    state_desc,
    recovery_model_desc,
    page_verify_option_desc
FROM sys.databases;

-- Database file information
SELECT 
    DB_NAME(database_id) AS DatabaseName,
    name AS LogicalName,
    physical_name AS PhysicalPath,
    type_desc AS FileType,
    size * 8 / 1024 AS SizeMB,
    max_size,
    growth
FROM sys.master_files
WHERE DB_NAME(database_id) = 'SalesDB';

-- Database size information
EXEC sp_spaceused;

-- Database space usage by file
SELECT 
    DB_NAME() AS DatabaseName,
    name AS FileName,
    size/128.0 AS CurrentSizeMB,
    size/128.0 - CAST(FILEPROPERTY(name, 'SpaceUsed') AS INT)/128.0 AS FreeSpaceMB
FROM sys.database_files;
```

### Dropping Databases

Dropping a database permanently deletes all data and files. This operation cannot be undone without a backup. Always ensure you have a backup before dropping a production database.

```sql
-- Drop database
DROP DATABASE IF EXISTS OldDatabase;

-- Drop database with checking connections
ALTER DATABASE OldDatabase SET SINGLE_USER WITH ROLLBACK IMMEDIATE;
DROP DATABASE OldDatabase;
```

---

## 6. Chapter 4: SQL Server Data Types

### Numeric Data Types

SQL Server provides various numeric types for different precision and range requirements. Choose the appropriate type based on the data's nature and range to optimize storage and prevent overflow errors.

```sql
-- Integer types
-- TINYINT: 0 to 255 (1 byte)
CREATE TABLE ExampleNumbers (
    TinyIntColumn TINYINT,        -- 0 to 255
    SmallIntColumn SMALLINT,      -- -32,768 to 32,767 (2 bytes)
    IntColumn INT,                -- -2^31 to 2^31-1 (4 bytes)
    BigIntColumn BIGINT,          -- -2^63 to 2^63-1 (8 bytes)
    
    -- Exact numeric types
    DecimalColumn DECIMAL(18,4),  -- Precision 18, Scale 4 (5-17 bytes)
    NumericColumn NUMERIC(10,2),  -- Same as DECIMAL
    
    -- Approximate numeric types
    FloatColumn FLOAT(53),        -- Double precision (8 bytes)
    RealColumn REAL,              -- Single precision (4 bytes)
    
    -- Money types
    MoneyColumn MONEY,            -- -922B to 922B (8 bytes)
    SmallMoneyColumn SMALLMONEY   -- -214,748 to 214,748 (4 bytes)
);

-- Example values
INSERT INTO ExampleNumbers 
(TinyIntColumn, SmallIntColumn, IntColumn, BigIntColumn, DecimalColumn, NumericColumn, FloatColumn, RealColumn, MoneyColumn, SmallMoneyColumn)
VALUES 
(255, -32000, 2147483647, 9223372036854775807, 12345678.9012, 99999999.99, 1.79E+308, 3.4E+38, 922337203685477.58, 214748.3647);
```

### Character Data Types

Character types store text data. Choose between fixed-length (CHAR) and variable-length (VARCHAR) based on data consistency. Use NVARCHAR for Unicode support when storing international characters.

```sql
-- Character types
CREATE TABLE ExampleStrings (
    -- Non-Unicode (1 byte per character)
    CharColumn CHAR(10),          -- Fixed length, padded with spaces
    VarcharColumn VARCHAR(100),   -- Variable length up to 100 chars
    VarcharMaxColumn VARCHAR(MAX), -- Variable length, up to 2GB
    
    -- Unicode (2 bytes per character)
    NcharColumn NCHAR(10),        -- Fixed Unicode, padded
    NvarcharColumn NVARCHAR(100), -- Variable Unicode
    NvarcharMaxColumn NVARCHAR(MAX), -- Variable Unicode, up to 2GB
    
    -- Text types (deprecated, use VARCHAR(MAX) instead)
    TextColumn TEXT,
    NtextColumn NTEXT
);

-- Example with different string data
INSERT INTO ExampleStrings 
(CharColumn, VarcharColumn, VarcharMaxColumn, NcharColumn, NvarcharColumn, NvarcharMaxColumn)
VALUES 
('Fixed     ', 'Variable', 'Long text...', N'Unicode  ', N'国际字符', N'日本語テキスト');

-- String functions
SELECT 
    LEN('Hello World') AS Length,           -- 11
    DATALENGTH('Hello World') AS DataLength, -- 11 bytes
    DATALENGTH(N'Hello World') AS UnicodeLength, -- 22 bytes
    LEFT('Hello World', 5) AS LeftPart,     -- Hello
    RIGHT('Hello World', 5) AS RightPart,   -- World
    SUBSTRING('Hello World', 7, 5) AS Substring, -- World
    UPPER('hello') AS UpperCase,            -- HELLO
    LOWER('HELLO') AS LowerCase,            -- hello
    LTRIM('  hello  ') AS LeftTrimmed,      -- 'hello  '
    RTRIM('  hello  ') AS RightTrimmed,     -- '  hello'
    REPLACE('Hello World', 'World', 'SQL') AS Replaced, -- Hello SQL
    STUFF('Hello World', 7, 5, 'SQL') AS Stuffed, -- Hello SQL
    CONCAT('Hello', ' ', 'World') AS Concatenated, -- Hello World
    REVERSE('Hello') AS Reversed;           -- olleH
```

### Date and Time Data Types

SQL Server provides multiple date/time types with different precision and storage requirements. Choose based on the accuracy needed and compatibility requirements.

```sql
-- Date and time types
CREATE TABLE ExampleDates (
    -- Date only
    DateColumn DATE,              -- 0001-01-01 to 9999-12-31 (3 bytes)
    
    -- Time only
    TimeColumn TIME(7),           -- 00:00:00 to 23:59:59.9999999 (3-5 bytes)
    
    -- Date and time combinations
    DateTimeColumn DATETIME,      -- 1753-01-01 to 9999-12-31 (8 bytes)
    SmallDateTimeColumn SMALLDATETIME, -- 1900-01-01 to 2079-06-06 (4 bytes)
    DateTime2Column DATETIME2(7), -- Higher precision (6-8 bytes)
    DateTimeOffsetColumn DATETIMEOFFSET(7) -- With timezone (8-10 bytes)
);

-- Example date values
INSERT INTO ExampleDates 
(DateColumn, TimeColumn, DateTimeColumn, SmallDateTimeColumn, DateTime2Column, DateTimeOffsetColumn)
VALUES 
('2024-12-25', '14:30:45.1234567', '2024-12-25 14:30:45', '2024-12-25 14:30:00', 
 '2024-12-25 14:30:45.1234567', '2024-12-25 14:30:45.1234567 +05:30');

-- Current date/time functions
SELECT 
    GETDATE() AS CurrentDateTime,           -- DATETIME
    SYSDATETIME() AS CurrentDateTime2,      -- DATETIME2
    SYSUTCDATETIME() AS CurrentUTC,         -- DATETIME2 UTC
    CURRENT_TIMESTAMP AS CurrentTimestamp,  -- Same as GETDATE()
    GETUTCDATE() AS CurrentUTCDate,         -- DATETIME UTC
    CAST(GETDATE() AS DATE) AS CurrentDate, -- DATE only
    CAST(GETDATE() AS TIME) AS CurrentTime; -- TIME only

-- Date functions
DECLARE @Date DATETIME = '2024-12-25 14:30:45';
SELECT 
    YEAR(@Date) AS YearValue,           -- 2024
    MONTH(@Date) AS MonthValue,         -- 12
    DAY(@Date) AS DayValue,             -- 25
    DATEPART(YEAR, @Date) AS YearPart,  -- 2024
    DATEPART(WEEKDAY, @Date) AS WeekDay,-- 4 (Wednesday)
    DATEPART(QUARTER, @Date) AS Quarter,-- 4
    DATENAME(MONTH, @Date) AS MonthName,-- December
    DATENAME(WEEKDAY, @Date) AS DayName,-- Wednesday
    DATEDIFF(DAY, '2024-01-01', @Date) AS DaysDiff, -- 359
    DATEDIFF(MONTH, '2024-01-01', @Date) AS MonthsDiff, -- 11
    DATEADD(DAY, 7, @Date) AS WeekLater, -- 2025-01-01
    DATEADD(MONTH, -1, @Date) AS MonthEarlier, -- 2024-11-25
    EOMONTH(@Date) AS EndOfMonth,       -- 2024-12-31
    EOMONTH(@Date, 1) AS EndNextMonth;  -- 2025-01-31
```

### Binary Data Types

Binary types store binary data such as images, files, and encrypted data. Choose between fixed-length and variable-length based on data characteristics.

```sql
-- Binary types
CREATE TABLE ExampleBinary (
    BinaryColumn BINARY(16),      -- Fixed length (16 bytes)
    VarbinaryColumn VARBINARY(100), -- Variable length
    VarbinaryMaxColumn VARBINARY(MAX), -- Variable length, up to 2GB
    ImageColumn IMAGE,            -- Deprecated, use VARBINARY(MAX)
    RowversionColumn ROWVERSION   -- Auto-updating binary(8)
);

-- Converting to/from binary
SELECT 
    CAST('Hello' AS VARBINARY(100)) AS TextToBinary,
    CAST(CAST('Hello' AS VARBINARY(100)) AS VARCHAR(100)) AS BinaryToText;

-- UniqueIdentifier (GUID)
DECLARE @GUID UNIQUEIDENTIFIER = NEWID();
SELECT @GUID AS NewGUID, NEWSEQUENTIALID() AS SequentialGUID;

-- Store hash
DECLARE @Password NVARCHAR(100) = 'MyPassword123';
SELECT HASHBYTES('SHA2_256', @Password) AS PasswordHash;
```

### Other Data Types

SQL Server provides additional specialized data types for specific use cases.

```sql
-- Additional data types
CREATE TABLE ExampleOther (
    -- Boolean equivalent
    BitColumn BIT,                -- 0, 1, or NULL
    
    -- Unique identifier
    GUIDColumn UNIQUEIDENTIFIER,  -- 16-byte GUID
    
    -- XML data
    XMLColumn XML,                -- XML data with validation
    
    -- JSON (stored as NVARCHAR)
    JSONColumn NVARCHAR(MAX),     -- JSON data
    
    -- Spatial data
    GeometryColumn GEOMETRY,      -- Planar spatial data
    GeographyColumn GEOGRAPHY,    -- Earth-based spatial data
    
    -- Hierarchy
    HierarchyColumn HIERARCHYID,  -- Position in hierarchy
    
    -- SQL Variant
    VariantColumn SQL_VARIANT     -- Any data type
);

-- Bit examples
INSERT INTO ExampleOther (BitColumn) VALUES (0), (1), (NULL);
SELECT BitColumn, 
       CASE WHEN BitColumn = 1 THEN 'True' 
            WHEN BitColumn = 0 THEN 'False' 
            ELSE 'Unknown' END AS BitDescription
FROM ExampleOther;

-- XML example
INSERT INTO ExampleOther (XMLColumn)
VALUES ('<Customer><Name>John</Name><City>New York</City></Customer>');

SELECT XMLColumn.query('/Customer/Name') AS CustomerName,
       XMLColumn.value('(/Customer/Name)[1]', 'VARCHAR(50)') AS NameValue,
       XMLColumn.exist('/Customer/City') AS CityExists
FROM ExampleOther
WHERE XMLColumn IS NOT NULL;

-- JSON example
INSERT INTO ExampleOther (JSONColumn)
VALUES ('{"name": "John", "age": 30, "city": "New York"}');

SELECT JSON_VALUE(JSONColumn, '$.name') AS Name,
       JSON_VALUE(JSONColumn, '$.age') AS Age,
       JSON_QUERY(JSONColumn, '$') AS FullJSON,
       ISJSON(JSONColumn) AS IsValidJSON
FROM ExampleOther
WHERE JSONColumn IS NOT NULL;

-- Parse JSON into rows
SELECT *
FROM OPENJSON('{"orders": [{"id": 1, "amount": 100}, {"id": 2, "amount": 200}]}')
WITH (
    id INT '$.id',
    amount DECIMAL(10,2) '$.amount'
);
```

---

## 7. Chapter 5: Creating and Managing Tables

### CREATE TABLE Syntax

Tables are the fundamental database objects that store data. A well-designed table has appropriate columns, data types, and constraints. The CREATE TABLE statement defines the table structure.

```sql
-- Basic table creation
CREATE TABLE Customers (
    CustomerID INT IDENTITY(1,1),
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    Email VARCHAR(100),
    Phone VARCHAR(20),
    DateOfBirth DATE,
    CreatedAt DATETIME2 DEFAULT SYSDATETIME(),
    IsActive BIT DEFAULT 1
);

-- Table with all constraints
CREATE TABLE Orders (
    OrderID INT IDENTITY(1,1) PRIMARY KEY,
    OrderNumber AS 'ORD-' + RIGHT('000000' + CAST(OrderID AS VARCHAR(10)), 6) PERSISTED,
    CustomerID INT NOT NULL,
    OrderDate DATETIME2 DEFAULT SYSDATETIME(),
    RequiredDate DATETIME2,
    ShippedDate DATETIME2,
    Status VARCHAR(20) DEFAULT 'Pending',
    TotalAmount DECIMAL(18,2) DEFAULT 0,
    Notes NVARCHAR(MAX),
    
    CONSTRAINT PK_Orders PRIMARY KEY (OrderID),
    CONSTRAINT FK_Orders_Customers FOREIGN KEY (CustomerID)
        REFERENCES Customers(CustomerID)
        ON DELETE NO ACTION
        ON UPDATE CASCADE,
    CONSTRAINT CK_Orders_OrderDate CHECK (OrderDate <= ShippedDate OR ShippedDate IS NULL),
    CONSTRAINT CK_Orders_Status CHECK (Status IN ('Pending', 'Processing', 'Shipped', 'Delivered', 'Cancelled'))
);

-- Create table with computed columns
CREATE TABLE Products (
    ProductID INT IDENTITY(1,1) PRIMARY KEY,
    ProductName VARCHAR(100) NOT NULL,
    UnitPrice DECIMAL(18,2) NOT NULL,
    Quantity INT NOT NULL DEFAULT 0,
    DiscountPercent DECIMAL(5,2) DEFAULT 0,
    
    -- Computed column (not stored)
    TotalValue AS (UnitPrice * Quantity),
    
    -- Persisted computed column (stored on disk)
    DiscountedPrice AS (UnitPrice * (1 - DiscountPercent/100)) PERSISTED
);
```

### Identity and Sequences

Identity columns auto-generate sequential numbers. Sequences provide more flexible number generation outside of tables.

```sql
-- Identity column
CREATE TABLE Employees (
    EmployeeID INT IDENTITY(1000, 1) PRIMARY KEY, -- Start at 1000, increment by 1
    FirstName VARCHAR(50),
    LastName VARCHAR(50)
);

-- Reset identity seed
DBCC CHECKIDENT('Employees', RESEED, 2000);

-- Get current identity value
SELECT IDENT_CURRENT('Employees') AS CurrentIdentity;

-- Get last identity value inserted in current session
SELECT SCOPE_IDENTITY() AS LastIdentity;

-- Create sequence
CREATE SEQUENCE seq_InvoiceNumber
    AS INT
    START WITH 10000
    INCREMENT BY 1
    MINVALUE 10000
    MAXVALUE 999999
    CYCLE
    CACHE 20;

-- Use sequence
DECLARE @InvoiceNumber INT = NEXT VALUE FOR seq_InvoiceNumber;
SELECT @InvoiceNumber AS InvoiceNumber;

-- Use sequence in table
CREATE TABLE Invoices (
    InvoiceID INT PRIMARY KEY DEFAULT (NEXT VALUE FOR seq_InvoiceNumber),
    CustomerID INT,
    InvoiceDate DATETIME2 DEFAULT SYSDATETIME()
);
```

### Altering Tables

Modify existing tables using ALTER TABLE statements. Be careful with changes that affect existing data.

```sql
-- Add column
ALTER TABLE Customers ADD MiddleName VARCHAR(50) NULL;

-- Add column with default
ALTER TABLE Customers ADD Country VARCHAR(50) NOT NULL DEFAULT 'USA';

-- Modify column
ALTER TABLE Customers ALTER COLUMN Email VARCHAR(200);

-- Drop column
ALTER TABLE Customers DROP COLUMN MiddleName;

-- Add constraint
ALTER TABLE Customers ADD CONSTRAINT PK_Customers PRIMARY KEY (CustomerID);
ALTER TABLE Customers ADD CONSTRAINT UQ_Customers_Email UNIQUE (Email);
ALTER TABLE Customers ADD CONSTRAINT CK_Customers_Email CHECK (Email LIKE '%@%.%');

-- Drop constraint
ALTER TABLE Customers DROP CONSTRAINT UQ_Customers_Email;

-- Disable constraint
ALTER TABLE Customers NOCHECK CONSTRAINT CK_Customers_Email;

-- Enable constraint
ALTER TABLE Customers CHECK CONSTRAINT CK_Customers_Email;

-- Rename table
EXEC sp_rename 'Customers', 'Clients';

-- Rename column
EXEC sp_rename 'Clients.FirstName', 'GivenName', 'COLUMN';
```

### Dropping Tables

Remove tables and their data permanently. Always check for dependencies before dropping.

```sql
-- Check for dependencies
SELECT OBJECT_NAME(parent_object_id) AS TableName
FROM sys.foreign_keys
WHERE referenced_object_id = OBJECT_ID('Customers');

-- Drop table if exists
DROP TABLE IF EXISTS Customers;

-- Drop multiple tables
DROP TABLE IF EXISTS Customers, Orders, OrderItems;
```

### Temporary Tables

Temporary tables are useful for intermediate results in complex operations. They're automatically cleaned up when no longer needed.

```sql
-- Local temporary table (#) - visible only to current session
CREATE TABLE #TempResults (
    ID INT,
    Name VARCHAR(100),
    Value DECIMAL(18,2)
);

-- Insert into temp table
INSERT INTO #TempResults
SELECT CustomerID, CustomerName, TotalPurchases
FROM Customers
WHERE TotalPurchases > 1000;

-- Global temporary table (##) - visible to all sessions
CREATE TABLE ##SharedResults (
    Category VARCHAR(50),
    TotalCount INT
);

-- Table variable (in memory, scoped to batch)
DECLARE @TableVar TABLE (
    ID INT,
    Name VARCHAR(100)
);

INSERT INTO @TableVar VALUES (1, 'Test');

-- Temp table vs table variable
-- Temp tables: support indexes, constraints, statistics
-- Table variables: faster for small datasets, no statistics

-- Drop temp tables explicitly (optional)
DROP TABLE #TempResults;
DROP TABLE ##SharedResults;
```

---

## 8. Chapter 6: Constraints

### Primary Key Constraints

Primary keys uniquely identify each row in a table. A table can have only one primary key, which can consist of one or more columns.

```sql
-- Single-column primary key
CREATE TABLE Departments (
    DepartmentID INT PRIMARY KEY,
    DepartmentName VARCHAR(50) NOT NULL
);

-- Primary key with identity
CREATE TABLE Employees (
    EmployeeID INT IDENTITY(1,1) PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL
);

-- Composite primary key
CREATE TABLE OrderDetails (
    OrderID INT NOT NULL,
    ProductID INT NOT NULL,
    Quantity INT NOT NULL,
    UnitPrice DECIMAL(18,2) NOT NULL,
    
    CONSTRAINT PK_OrderDetails PRIMARY KEY (OrderID, ProductID)
);

-- Add primary key to existing table
ALTER TABLE Customers ADD CONSTRAINT PK_Customers PRIMARY KEY (CustomerID);

-- Named primary key constraint
CREATE TABLE Suppliers (
    SupplierID INT,
    SupplierName VARCHAR(100),
    
    CONSTRAINT PK_Suppliers PRIMARY KEY CLUSTERED (SupplierID)
);

-- Non-clustered primary key
CREATE TABLE AuditLog (
    LogID BIGINT IDENTITY(1,1),
    LogDate DATETIME2 DEFAULT SYSDATETIME(),
    LogMessage NVARCHAR(MAX),
    
    CONSTRAINT PK_AuditLog PRIMARY KEY NONCLUSTERED (LogID)
);
```

### Foreign Key Constraints

Foreign keys enforce referential integrity between tables. They ensure that relationships between tables remain consistent.

```sql
-- Foreign key reference
CREATE TABLE Orders (
    OrderID INT IDENTITY(1,1) PRIMARY KEY,
    CustomerID INT NOT NULL,
    OrderDate DATETIME2 DEFAULT SYSDATETIME(),
    
    CONSTRAINT FK_Orders_Customers FOREIGN KEY (CustomerID)
        REFERENCES Customers(CustomerID)
);

-- Foreign key with cascade actions
CREATE TABLE OrderDetails (
    OrderDetailID INT IDENTITY(1,1) PRIMARY KEY,
    OrderID INT NOT NULL,
    ProductID INT NOT NULL,
    Quantity INT NOT NULL,
    
    CONSTRAINT FK_OrderDetails_Orders FOREIGN KEY (OrderID)
        REFERENCES Orders(OrderID)
        ON DELETE CASCADE     -- Delete details when order is deleted
        ON UPDATE CASCADE,    -- Update OrderID when Orders.OrderID changes
    
    CONSTRAINT FK_OrderDetails_Products FOREIGN KEY (ProductID)
        REFERENCES Products(ProductID)
        ON DELETE NO ACTION   -- Prevent product deletion if referenced
        ON UPDATE NO ACTION
);

-- Self-referencing foreign key
CREATE TABLE Employees (
    EmployeeID INT IDENTITY(1,1) PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    ManagerID INT NULL,
    
    CONSTRAINT FK_Employees_Manager FOREIGN KEY (ManagerID)
        REFERENCES Employees(EmployeeID)
);

-- Foreign key with multiple columns
CREATE TABLE OrderItemLocations (
    OrderID INT,
    ProductID INT,
    LocationID INT,
    
    CONSTRAINT FK_OrderItemLocations_OrderDetails 
        FOREIGN KEY (OrderID, ProductID)
        REFERENCES OrderDetails(OrderID, ProductID)
);

-- Add foreign key to existing table
ALTER TABLE Orders
ADD CONSTRAINT FK_Orders_Customers 
FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID);

-- Disable foreign key constraint
ALTER TABLE Orders NOCHECK CONSTRAINT FK_Orders_Customers;

-- Enable foreign key constraint
ALTER TABLE Orders CHECK CONSTRAINT FK_Orders_Customers;

-- Check existing data when enabling
ALTER TABLE Orders WITH CHECK CHECK CONSTRAINT FK_Orders_Customers;
```

### Unique Constraints

Unique constraints ensure that no duplicate values exist in specified columns. Unlike primary keys, a table can have multiple unique constraints, and they can allow NULL values.

```sql
-- Unique constraint on single column
CREATE TABLE Users (
    UserID INT IDENTITY(1,1) PRIMARY KEY,
    Username VARCHAR(50) NOT NULL,
    Email VARCHAR(100),
    
    CONSTRAINT UQ_Users_Username UNIQUE (Username),
    CONSTRAINT UQ_Users_Email UNIQUE (Email)
);

-- Composite unique constraint
CREATE TABLE ProductPrices (
    ProductID INT,
    EffectiveDate DATE,
    Price DECIMAL(18,2),
    
    CONSTRAINT UQ_ProductPrices_Product_Date UNIQUE (ProductID, EffectiveDate)
);

-- Add unique constraint to existing table
ALTER TABLE Customers ADD CONSTRAINT UQ_Customers_Email UNIQUE (Email);

-- Unique constraint with index options
CREATE UNIQUE NONCLUSTERED INDEX IX_Customers_Email 
ON Customers(Email)
WHERE Email IS NOT NULL;  -- Filtered unique index
```

### Check Constraints

Check constraints enforce domain integrity by limiting acceptable values. They evaluate to TRUE, FALSE, or UNKNOWN.

```sql
-- Check constraint on single column
CREATE TABLE Products (
    ProductID INT IDENTITY(1,1) PRIMARY KEY,
    ProductName VARCHAR(100) NOT NULL,
    UnitPrice DECIMAL(18,2) NOT NULL,
    StockQuantity INT NOT NULL DEFAULT 0,
    
    CONSTRAINT CK_Products_UnitPrice CHECK (UnitPrice > 0),
    CONSTRAINT CK_Products_StockQuantity CHECK (StockQuantity >= 0)
);

-- Check constraint with multiple columns
CREATE TABLE Events (
    EventID INT IDENTITY(1,1) PRIMARY KEY,
    EventName VARCHAR(100),
    StartDate DATETIME2 NOT NULL,
    EndDate DATETIME2 NOT NULL,
    
    CONSTRAINT CK_Events_Dates CHECK (EndDate > StartDate)
);

-- Check constraint with list of values
CREATE TABLE Orders (
    OrderID INT IDENTITY(1,1) PRIMARY KEY,
    Status VARCHAR(20),
    
    CONSTRAINT CK_Orders_Status CHECK (Status IN ('Pending', 'Processing', 'Shipped', 'Delivered', 'Cancelled'))
);

-- Check constraint with pattern matching
CREATE TABLE Customers (
    CustomerID INT IDENTITY(1,1) PRIMARY KEY,
    Email VARCHAR(100),
    Phone VARCHAR(20),
    
    CONSTRAINT CK_Customers_Email CHECK (Email LIKE '%@%.%'),
    CONSTRAINT CK_Customers_Phone CHECK (Phone LIKE '+[0-9][0-9][0-9]-[0-9][0-9][0-9]-[0-9][0-9][0-9][0-9]')
);

-- Add check constraint to existing table
ALTER TABLE Products ADD CONSTRAINT CK_Products_Discount CHECK (Discount BETWEEN 0 AND 100);

-- Disable check constraint
ALTER TABLE Products NOCHECK CONSTRAINT CK_Products_UnitPrice;

-- Enable check constraint
ALTER TABLE Products CHECK CONSTRAINT CK_Products_UnitPrice;
```

### Default Constraints

Default constraints provide values when none is specified during INSERT. They ensure columns have valid values without requiring explicit specification.

```sql
-- Default constraint in CREATE TABLE
CREATE TABLE Orders (
    OrderID INT IDENTITY(1,1) PRIMARY KEY,
    OrderDate DATETIME2 DEFAULT SYSDATETIME(),
    Status VARCHAR(20) DEFAULT 'Pending',
    TotalAmount DECIMAL(18,2) DEFAULT 0,
    CreatedBy VARCHAR(100) DEFAULT SUSER_NAME()
);

-- Add default constraint to existing table
ALTER TABLE Customers ADD CONSTRAINT DF_Customers_Country DEFAULT 'USA' FOR Country;

-- Default with function
ALTER TABLE Orders ADD CONSTRAINT DF_Orders_OrderNumber DEFAULT (NEXT VALUE FOR seq_OrderNumber) FOR OrderNumber;

-- Drop default constraint
ALTER TABLE Orders DROP CONSTRAINT DF_Orders_Status;
```

### Viewing Constraint Information

Query system views to examine constraint definitions and properties.

```sql
-- View all constraints in a database
SELECT 
    OBJECT_NAME(parent_object_id) AS TableName,
    name AS ConstraintName,
    type_desc AS ConstraintType
FROM sys.objects
WHERE type IN ('PK', 'FK', 'UQ', 'C', 'D')
ORDER BY TableName, ConstraintType;

-- View foreign key details
SELECT 
    OBJECT_NAME(f.parent_object_id) AS TableName,
    COL_NAME(fc.parent_object_id, fc.parent_column_id) AS ColumnName,
    OBJECT_NAME(f.referenced_object_id) AS ReferencedTable,
    COL_NAME(fc.referenced_object_id, fc.referenced_column_id) AS ReferencedColumn,
    f.name AS ConstraintName,
    f.delete_referential_action_desc AS OnDelete,
    f.update_referential_action_desc AS OnUpdate
FROM sys.foreign_keys f
INNER JOIN sys.foreign_key_columns fc ON f.object_id = fc.constraint_object_id
ORDER BY TableName, ColumnName;

-- View check constraints
SELECT 
    OBJECT_NAME(parent_object_id) AS TableName,
    name AS ConstraintName,
    definition AS CheckDefinition
FROM sys.check_constraints
WHERE OBJECT_NAME(parent_object_id) = 'Products';
```

---

## 9. Chapter 7: Basic Queries - SELECT Statement

### Basic SELECT Syntax

The SELECT statement retrieves data from tables. Master SELECT before moving to more complex queries.

```sql
-- Select all columns
SELECT * FROM Customers;

-- Select specific columns
SELECT CustomerID, FirstName, LastName FROM Customers;

-- Select with column aliases
SELECT 
    CustomerID AS ID,
    FirstName + ' ' + LastName AS FullName,
    Email AS EmailAddress
FROM Customers;

-- Select distinct values
SELECT DISTINCT Country FROM Customers;

-- Select top rows
SELECT TOP 10 * FROM Orders ORDER BY OrderDate DESC;

-- Top with percent
SELECT TOP 10 PERCENT * FROM Products ORDER BY UnitPrice DESC;

-- Top with ties (include rows with equal values)
SELECT TOP 10 WITH TIES * FROM Products ORDER BY UnitPrice DESC;
```

### Using Expressions

Expressions calculate values or transform data in SELECT statements.

```sql
-- Arithmetic expressions
SELECT 
    ProductName,
    UnitPrice,
    Quantity,
    UnitPrice * Quantity AS TotalValue,
    UnitPrice * 1.1 AS PriceWithTax,
    (UnitPrice * Quantity) - (UnitPrice * Quantity * 0.1) AS DiscountedTotal
FROM OrderDetails;

-- String expressions
SELECT 
    FirstName + ' ' + LastName AS FullName,
    UPPER(LEFT(FirstName, 1)) + LOWER(SUBSTRING(FirstName, 2, LEN(FirstName) - 1)) AS FormattedName,
    COALESCE(Email, 'No email') AS EmailOrPlaceholder
FROM Customers;

-- Date expressions
SELECT 
    OrderDate,
    DATEADD(DAY, 7, OrderDate) AS ExpectedDelivery,
    DATEDIFF(DAY, OrderDate, GETDATE()) AS DaysSinceOrder,
    DATENAME(WEEKDAY, OrderDate) AS OrderDay
FROM Orders;

-- CASE expressions
SELECT 
    ProductName,
    UnitPrice,
    CASE 
        WHEN UnitPrice < 10 THEN 'Low'
        WHEN UnitPrice BETWEEN 10 AND 50 THEN 'Medium'
        WHEN UnitPrice > 50 THEN 'High'
        ELSE 'Unknown'
    END AS PriceCategory,
    CASE UnitPrice
        WHEN 0 THEN 'Free'
        ELSE 'Paid'
    END AS PriceType
FROM Products;

-- IIF function (simplified CASE)
SELECT 
    ProductName,
    UnitPrice,
    IIF(UnitPrice > 50, 'Premium', 'Standard') AS PriceLevel
FROM Products;
```

### NULL Handling

NULL represents unknown or missing values. Handle NULLs carefully because they behave differently from other values.

```sql
-- IS NULL and IS NOT NULL
SELECT * FROM Customers WHERE Email IS NULL;
SELECT * FROM Customers WHERE Phone IS NOT NULL;

-- COALESCE - return first non-NULL value
SELECT 
    CustomerID,
    COALESCE(Phone, Mobile, Email, 'No contact info') AS ContactInfo
FROM Customers;

-- ISNULL - replace NULL with default
SELECT 
    ProductName,
    ISNULL(Description, 'No description available') AS Description
FROM Products;

-- NULLIF - return NULL if values match
SELECT 
    ProductName,
    NULLIF(UnitPrice, 0) AS NonZeroPrice  -- Returns NULL if price is 0
FROM Products;

-- Handling NULL in calculations
SELECT 
    ProductName,
    UnitPrice,
    Discount,
    UnitPrice - ISNULL(Discount, 0) AS FinalPrice
FROM Products;

-- NULL in comparisons
SELECT 
    ProductName,
    UnitPrice
FROM Products
WHERE UnitPrice > 50 OR UnitPrice IS NULL;  -- NULL comparisons need special handling
```

### SELECT INTO

Create a new table from query results using SELECT INTO.

```sql
-- Create new table from query
SELECT 
    CustomerID,
    FirstName,
    LastName,
    Email
INTO CustomerBackup
FROM Customers;

-- Create table from joined data
SELECT 
    c.CustomerID,
    c.FirstName,
    c.LastName,
    o.OrderID,
    o.OrderDate,
    o.TotalAmount
INTO CustomerOrdersReport
FROM Customers c
INNER JOIN Orders o ON c.CustomerID = o.CustomerID;

-- Create empty table structure
SELECT * INTO Products_NewStructure
FROM Products
WHERE 1 = 0;  -- No rows copied, just structure
```

---

## 10. Chapter 8: Filtering and Sorting Data

### WHERE Clause Basics

The WHERE clause filters rows based on conditions. Only rows that satisfy the conditions are returned.

```sql
-- Basic comparison operators
SELECT * FROM Products WHERE UnitPrice > 50;
SELECT * FROM Products WHERE UnitPrice <= 100;
SELECT * FROM Products WHERE ProductName = 'Chai';
SELECT * FROM Products WHERE ProductName != 'Chai';
SELECT * FROM Products WHERE ProductName <> 'Chai';  -- Same as !=

-- Range conditions
SELECT * FROM Products WHERE UnitPrice BETWEEN 10 AND 50;
SELECT * FROM Orders WHERE OrderDate BETWEEN '2024-01-01' AND '2024-12-31';
SELECT * FROM Products WHERE UnitPrice NOT BETWEEN 10 AND 50;

-- List conditions
SELECT * FROM Products WHERE CategoryID IN (1, 3, 5);
SELECT * FROM Products WHERE CategoryID NOT IN (1, 3, 5);
SELECT * FROM Customers WHERE Country IN ('USA', 'Canada', 'Mexico');

-- Pattern matching with LIKE
SELECT * FROM Customers WHERE LastName LIKE 'Smith%';     -- Starts with Smith
SELECT * FROM Customers WHERE LastName LIKE '%son';       -- Ends with son
SELECT * FROM Customers WHERE LastName LIKE '%ith%';      -- Contains ith
SELECT * FROM Customers WHERE Email LIKE '%@gmail.com';   -- Gmail addresses
SELECT * FROM Products WHERE ProductName LIKE '_h%';      -- Second letter is h
SELECT * FROM Customers WHERE Phone LIKE '[0-9][0-9][0-9]-______'; -- Pattern

-- ESCAPE character for special characters
SELECT * FROM Products WHERE ProductName LIKE '%\%%' ESCAPE '\'; -- Contains %

-- Multiple conditions with AND, OR
SELECT * FROM Products 
WHERE CategoryID = 1 AND UnitPrice > 20;

SELECT * FROM Products 
WHERE CategoryID = 1 OR CategoryID = 3;

SELECT * FROM Products 
WHERE (CategoryID = 1 OR CategoryID = 3) AND UnitPrice > 20;

-- NOT operator
SELECT * FROM Products WHERE NOT CategoryID = 1;
SELECT * FROM Products WHERE NOT (UnitPrice > 50 OR UnitPrice < 10);
```

### ORDER BY Clause

Sort query results by one or more columns. ASC (ascending) is default; use DESC for descending.

```sql
-- Sort by single column
SELECT * FROM Products ORDER BY ProductName;
SELECT * FROM Products ORDER BY UnitPrice DESC;

-- Sort by multiple columns
SELECT * FROM Products 
ORDER BY CategoryID ASC, UnitPrice DESC;

-- Sort by expression
SELECT * FROM Products 
ORDER BY UnitPrice * Quantity DESC;

-- Sort by column position
SELECT ProductName, UnitPrice, CategoryID
FROM Products
ORDER BY 2 DESC;  -- Sort by second column (UnitPrice)

-- Sort with CASE
SELECT * FROM Products
ORDER BY 
    CASE WHEN CategoryID = 1 THEN 1
         WHEN CategoryID = 2 THEN 2
         ELSE 3
    END,
    ProductName;

-- NULL ordering
SELECT * FROM Customers
ORDER BY Email DESC;  -- NULLs appear first in DESC, last in ASC

-- Control NULL position
SELECT * FROM Customers
ORDER BY 
    CASE WHEN Email IS NULL THEN 1 ELSE 0 END,
    Email;
```

### OFFSET-FETCH Pagination

Implement pagination using OFFSET-FETCH clause, which is ANSI SQL standard.

```sql
-- Skip first 10 rows, take next 10
SELECT * FROM Products
ORDER BY ProductName
OFFSET 10 ROWS
FETCH NEXT 10 ROWS ONLY;

-- First page (rows 1-10)
SELECT * FROM Products
ORDER BY ProductName
OFFSET 0 ROWS
FETCH NEXT 10 ROWS ONLY;

-- Second page (rows 11-20)
SELECT * FROM Products
ORDER BY ProductName
OFFSET 10 ROWS
FETCH NEXT 10 ROWS ONLY;

-- Dynamic pagination
DECLARE @PageNumber INT = 3;
DECLARE @PageSize INT = 20;
DECLARE @Offset INT = (@PageNumber - 1) * @PageSize;

SELECT * FROM Products
ORDER BY ProductName
OFFSET @Offset ROWS
FETCH NEXT @PageSize ROWS ONLY;
```

### Advanced Filtering Techniques

Combine multiple filtering techniques for complex queries.

```sql
-- Subquery in WHERE
SELECT * FROM Products
WHERE UnitPrice > (SELECT AVG(UnitPrice) FROM Products);

-- EXISTS
SELECT * FROM Customers c
WHERE EXISTS (SELECT 1 FROM Orders o WHERE o.CustomerID = c.CustomerID);

-- NOT EXISTS
SELECT * FROM Customers c
WHERE NOT EXISTS (SELECT 1 FROM Orders o WHERE o.CustomerID = c.CustomerID);

-- ANY and ALL
SELECT * FROM Products
WHERE UnitPrice > ANY (SELECT UnitPrice FROM Products WHERE CategoryID = 1);

SELECT * FROM Products
WHERE UnitPrice > ALL (SELECT UnitPrice FROM Products WHERE CategoryID = 2);

-- Using variables
DECLARE @MinPrice DECIMAL(18,2) = 20;
DECLARE @MaxPrice DECIMAL(18,2) = 50;
DECLARE @CategoryID INT = 1;

SELECT * FROM Products
WHERE UnitPrice BETWEEN @MinPrice AND @MaxPrice
  AND CategoryID = @CategoryID;

-- Dynamic filtering with optional parameters
CREATE PROCEDURE SearchProducts
    @ProductName VARCHAR(100) = NULL,
    @CategoryID INT = NULL,
    @MinPrice DECIMAL(18,2) = NULL,
    @MaxPrice DECIMAL(18,2) = NULL
AS
BEGIN
    SELECT * FROM Products
    WHERE (@ProductName IS NULL OR ProductName LIKE '%' + @ProductName + '%')
      AND (@CategoryID IS NULL OR CategoryID = @CategoryID)
      AND (@MinPrice IS NULL OR UnitPrice >= @MinPrice)
      AND (@MaxPrice IS NULL OR UnitPrice <= @MaxPrice);
END
```

---

## 11. Chapter 9: JOINs - Combining Tables

### INNER JOIN

INNER JOIN returns rows when there's a match in both tables. Rows without matches are excluded.

```sql
-- Basic INNER JOIN
SELECT 
    c.CustomerID,
    c.FirstName,
    c.LastName,
    o.OrderID,
    o.OrderDate,
    o.TotalAmount
FROM Customers c
INNER JOIN Orders o ON c.CustomerID = o.CustomerID;

-- Multiple INNER JOINs
SELECT 
    c.CustomerID,
    c.FirstName,
    o.OrderID,
    o.OrderDate,
    p.ProductName,
    od.Quantity,
    od.UnitPrice
FROM Customers c
INNER JOIN Orders o ON c.CustomerID = o.CustomerID
INNER JOIN OrderDetails od ON o.OrderID = od.OrderID
INNER JOIN Products p ON od.ProductID = p.ProductID;

-- JOIN with table alias
SELECT 
    e.EmployeeID,
    e.FirstName AS EmployeeName,
    m.FirstName AS ManagerName
FROM Employees e
INNER JOIN Employees m ON e.ManagerID = m.EmployeeID;

-- JOIN with additional conditions
SELECT 
    o.OrderID,
    o.OrderDate,
    c.FirstName,
    c.LastName
FROM Orders o
INNER JOIN Customers c ON o.CustomerID = c.CustomerID
    AND o.OrderDate >= '2024-01-01';
```

### LEFT OUTER JOIN

LEFT JOIN returns all rows from the left table and matching rows from the right table. NULL values appear for non-matching rows.

```sql
-- Basic LEFT JOIN
SELECT 
    c.CustomerID,
    c.FirstName,
    c.LastName,
    o.OrderID,
    o.OrderDate
FROM Customers c
LEFT JOIN Orders o ON c.CustomerID = o.CustomerID;

-- Find customers without orders
SELECT 
    c.CustomerID,
    c.FirstName,
    c.LastName
FROM Customers c
LEFT JOIN Orders o ON c.CustomerID = o.CustomerID
WHERE o.OrderID IS NULL;

-- Multiple LEFT JOINs
SELECT 
    c.CustomerID,
    c.FirstName,
    o.OrderID,
    od.ProductID
FROM Customers c
LEFT JOIN Orders o ON c.CustomerID = o.CustomerID
LEFT JOIN OrderDetails od ON o.OrderID = od.OrderID;

-- LEFT JOIN with aggregation
SELECT 
    c.CustomerID,
    c.FirstName,
    COUNT(o.OrderID) AS OrderCount,
    ISNULL(SUM(o.TotalAmount), 0) AS TotalSpent
FROM Customers c
LEFT JOIN Orders o ON c.CustomerID = o.CustomerID
GROUP BY c.CustomerID, c.FirstName;
```

### RIGHT OUTER JOIN

RIGHT JOIN returns all rows from the right table and matching rows from the left table. It's the reverse of LEFT JOIN and less commonly used.

```sql
-- Basic RIGHT JOIN
SELECT 
    c.CustomerID,
    c.FirstName,
    o.OrderID,
    o.OrderDate
FROM Customers c
RIGHT JOIN Orders o ON c.CustomerID = o.CustomerID;

-- Find orders without valid customer (data integrity issue)
SELECT 
    o.OrderID,
    o.OrderDate,
    o.TotalAmount
FROM Customers c
RIGHT JOIN Orders o ON c.CustomerID = o.CustomerID
WHERE c.CustomerID IS NULL;
```

### FULL OUTER JOIN

FULL JOIN returns all rows from both tables, matching where possible and showing NULLs where no match exists.

```sql
-- Basic FULL JOIN
SELECT 
    c.CustomerID,
    c.FirstName,
    o.OrderID,
    o.OrderDate
FROM Customers c
FULL OUTER JOIN Orders o ON c.CustomerID = o.CustomerID;

-- Find unmatched rows in either table
SELECT 
    c.CustomerID,
    c.FirstName,
    o.OrderID,
    o.OrderDate
FROM Customers c
FULL OUTER JOIN Orders o ON c.CustomerID = o.CustomerID
WHERE c.CustomerID IS NULL OR o.OrderID IS NULL;
```

### CROSS JOIN

CROSS JOIN produces a Cartesian product—all combinations of rows from both tables. Use carefully as results can be large.

```sql
-- CROSS JOIN - all combinations
SELECT 
    c.FirstName,
    c.LastName,
    p.ProductName
FROM Customers c
CROSS JOIN Products p;

-- Use case: generate all possible date/product combinations
SELECT 
    d.DateValue,
    p.ProductID,
    p.ProductName
FROM (SELECT DISTINCT OrderDate AS DateValue FROM Orders) d
CROSS JOIN Products p;

-- Self CROSS JOIN for comparison
SELECT 
    p1.ProductName AS Product1,
    p2.ProductName AS Product2,
    p1.UnitPrice - p2.UnitPrice AS PriceDifference
FROM Products p1
CROSS JOIN Products p2
WHERE p1.ProductID < p2.ProductID
  AND ABS(p1.UnitPrice - p2.UnitPrice) < 5;
```

### Join Best Practices

```sql
-- Use meaningful aliases
-- Good
SELECT 
    cust.FirstName,
    ord.OrderDate
FROM Customers cust
INNER JOIN Orders ord ON cust.CustomerID = ord.CustomerID;

-- Avoid ambiguous column references
-- Bad
SELECT FirstName, OrderID
FROM Customers
INNER JOIN Orders ON CustomerID = CustomerID;  -- Ambiguous!

-- Good
SELECT c.FirstName, o.OrderID
FROM Customers c
INNER JOIN Orders o ON c.CustomerID = o.CustomerID;

-- Consider performance
-- Join on indexed columns
-- Filter early in WHERE clause
-- Use appropriate join types
```

---

## 12. Chapter 10: Aggregate Functions and GROUP BY

### Aggregate Functions

Aggregate functions perform calculations on sets of values and return a single value.

```sql
-- Basic aggregate functions
SELECT 
    COUNT(*) AS TotalRows,
    COUNT(ProductID) AS CountProductID,
    COUNT(DISTINCT CategoryID) AS UniqueCategories,
    SUM(UnitPrice * Quantity) AS TotalValue,
    AVG(UnitPrice) AS AveragePrice,
    MIN(UnitPrice) AS MinPrice,
    MAX(UnitPrice) AS MaxPrice,
    STDEV(UnitPrice) AS PriceStdDev,
    VAR(UnitPrice) AS PriceVariance
FROM Products;

-- Aggregates with filtering
SELECT 
    COUNT(*) AS ProductCount,
    SUM(UnitPrice) AS TotalPrice,
    AVG(UnitPrice) AS AveragePrice
FROM Products
WHERE CategoryID = 1;

-- Aggregates with NULL handling
SELECT 
    COUNT(*) AS TotalRows,
    COUNT(Email) AS EmailCount,        -- Excludes NULLs
    COUNT(DISTINCT Email) AS UniqueEmails,
    AVG(UnitPrice) AS AvgPrice,         -- Excludes NULLs
    SUM(ISNULL(Discount, 0)) AS TotalDiscount
FROM Products;

-- String aggregation (SQL Server 2017+)
SELECT 
    STRING_AGG(FirstName, ', ') AS AllNames,
    STRING_AGG(FirstName, ', ') WITHIN GROUP (ORDER BY FirstName) AS SortedNames
FROM Customers;

-- Statistical functions
SELECT 
    ProductName,
    UnitPrice,
    PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY UnitPrice) OVER () AS MedianPrice,
    PERCENT_RANK() OVER (ORDER BY UnitPrice) AS PricePercentile
FROM Products;
```

### GROUP BY Clause

GROUP BY groups rows that have the same values in specified columns and applies aggregate functions to each group.

```sql
-- Simple GROUP BY
SELECT 
    CategoryID,
    COUNT(*) AS ProductCount,
    AVG(UnitPrice) AS AveragePrice,
    SUM(UnitsInStock) AS TotalStock
FROM Products
GROUP BY CategoryID;

-- GROUP BY with JOIN
SELECT 
    c.CategoryName,
    COUNT(p.ProductID) AS ProductCount,
    AVG(p.UnitPrice) AS AveragePrice
FROM Categories c
LEFT JOIN Products p ON c.CategoryID = p.CategoryID
GROUP BY c.CategoryID, c.CategoryName;

-- GROUP BY with WHERE
SELECT 
    CategoryID,
    COUNT(*) AS ProductCount,
    AVG(UnitPrice) AS AveragePrice
FROM Products
WHERE Discontinued = 0
GROUP BY CategoryID;

-- GROUP BY with ORDER BY
SELECT 
    CategoryID,
    COUNT(*) AS ProductCount,
    SUM(UnitPrice * UnitsInStock) AS InventoryValue
FROM Products
GROUP BY CategoryID
ORDER BY InventoryValue DESC;

-- GROUP BY with expressions
SELECT 
    YEAR(OrderDate) AS OrderYear,
    MONTH(OrderDate) AS OrderMonth,
    COUNT(*) AS OrderCount,
    SUM(TotalAmount) AS TotalSales
FROM Orders
GROUP BY YEAR(OrderDate), MONTH(OrderDate)
ORDER BY OrderYear, OrderMonth;

-- GROUP BY with CASE
SELECT 
    CASE 
        WHEN UnitPrice < 10 THEN 'Budget'
        WHEN UnitPrice BETWEEN 10 AND 50 THEN 'Regular'
        ELSE 'Premium'
    END AS PriceRange,
    COUNT(*) AS ProductCount,
    AVG(UnitPrice) AS AveragePrice
FROM Products
GROUP BY 
    CASE 
        WHEN UnitPrice < 10 THEN 'Budget'
        WHEN UnitPrice BETWEEN 10 AND 50 THEN 'Regular'
        ELSE 'Premium'
    END;
```

### HAVING Clause

HAVING filters groups after aggregation, similar to WHERE filtering rows before aggregation.

```sql
-- HAVING with aggregate condition
SELECT 
    CategoryID,
    COUNT(*) AS ProductCount,
    AVG(UnitPrice) AS AveragePrice
FROM Products
GROUP BY CategoryID
HAVING COUNT(*) > 5;

-- HAVING with multiple conditions
SELECT 
    CategoryID,
    COUNT(*) AS ProductCount,
    AVG(UnitPrice) AS AveragePrice,
    SUM(UnitsInStock) AS TotalStock
FROM Products
GROUP BY CategoryID
HAVING COUNT(*) > 3 
   AND AVG(UnitPrice) > 20
   AND SUM(UnitsInStock) > 100;

-- HAVING vs WHERE
SELECT 
    CategoryID,
    COUNT(*) AS ProductCount,
    AVG(UnitPrice) AS AveragePrice
FROM Products
WHERE Discontinued = 0          -- Filter rows before grouping
GROUP BY CategoryID
HAVING AVG(UnitPrice) > 25;    -- Filter groups after aggregation

-- HAVING with subquery
SELECT 
    CategoryID,
    COUNT(*) AS ProductCount
FROM Products
GROUP BY CategoryID
HAVING COUNT(*) > (SELECT AVG(ProductCount) FROM 
    (SELECT CategoryID, COUNT(*) AS ProductCount 
     FROM Products GROUP BY CategoryID) AS Counts);
```

### GROUPING SETS

GROUPING SETS allow multiple grouping combinations in a single query.

```sql
-- Multiple grouping sets
SELECT 
    CategoryID,
    SupplierID,
    COUNT(*) AS ProductCount,
    SUM(UnitPrice) AS TotalPrice
FROM Products
GROUP BY GROUPING SETS (
    (CategoryID),
    (SupplierID),
    (CategoryID, SupplierID),
    ()
);

-- Equivalent to UNION ALL of:
-- SELECT CategoryID, NULL, COUNT(*), SUM(UnitPrice) FROM Products GROUP BY CategoryID
-- SELECT NULL, SupplierID, COUNT(*), SUM(UnitPrice) FROM Products GROUP BY SupplierID
-- SELECT CategoryID, SupplierID, COUNT(*), SUM(UnitPrice) FROM Products GROUP BY CategoryID, SupplierID
-- SELECT NULL, NULL, COUNT(*), SUM(UnitPrice) FROM Products

-- ROLLUP - hierarchical grouping
SELECT 
    YEAR(OrderDate) AS OrderYear,
    MONTH(OrderDate) AS OrderMonth,
    SUM(TotalAmount) AS TotalSales
FROM Orders
GROUP BY ROLLUP (YEAR(OrderDate), MONTH(OrderDate));

-- CUBE - all combinations
SELECT 
    CategoryID,
    SupplierID,
    COUNT(*) AS ProductCount
FROM Products
GROUP BY CUBE (CategoryID, SupplierID);

-- GROUPING_ID to identify grouping level
SELECT 
    YEAR(OrderDate) AS OrderYear,
    MONTH(OrderDate) AS OrderMonth,
    GROUPING_ID(YEAR(OrderDate), MONTH(OrderDate)) AS GroupingLevel,
    SUM(TotalAmount) AS TotalSales
FROM Orders
GROUP BY ROLLUP (YEAR(OrderDate), MONTH(OrderDate));
```

---

## 13. Chapter 11: Subqueries and CTEs

### Scalar Subqueries

Scalar subqueries return a single value and can be used anywhere a single value is expected.

```sql
-- Subquery in SELECT
SELECT 
    ProductName,
    UnitPrice,
    (SELECT AVG(UnitPrice) FROM Products) AS AveragePrice,
    UnitPrice - (SELECT AVG(UnitPrice) FROM Products) AS DifferenceFromAverage
FROM Products;

-- Subquery in WHERE
SELECT * FROM Products
WHERE UnitPrice > (SELECT AVG(UnitPrice) FROM Products);

-- Subquery for comparison
SELECT * FROM Products
WHERE CategoryID = (SELECT CategoryID FROM Products WHERE ProductName = 'Chai');

-- Correlated scalar subquery
SELECT 
    p.ProductName,
    p.UnitPrice,
    (SELECT AVG(p2.UnitPrice) FROM Products p2 WHERE p2.CategoryID = p.CategoryID) AS CategoryAverage
FROM Products p;
```

### Table Subqueries

Table subqueries (derived tables) return a result set that can be used like a table.

```sql
-- Derived table in FROM
SELECT 
    CategoryName,
    ProductCount
FROM (
    SELECT 
        c.CategoryName,
        COUNT(p.ProductID) AS ProductCount
    FROM Categories c
    LEFT JOIN Products p ON c.CategoryID = p.CategoryID
    GROUP BY c.CategoryName
) AS CategoryStats
WHERE ProductCount > 5;

-- Derived table with JOIN
SELECT 
    cs.CategoryName,
    cs.ProductCount,
    ps.OverallAverage
FROM (
    SELECT CategoryName, COUNT(*) AS ProductCount
    FROM Products p JOIN Categories c ON p.CategoryID = c.CategoryID
    GROUP BY CategoryName
) AS cs
CROSS JOIN (
    SELECT AVG(ProductCount) AS OverallAverage
    FROM (SELECT CategoryID, COUNT(*) AS ProductCount FROM Products GROUP BY CategoryID) AS counts
) AS ps;

-- Subquery in IN clause
SELECT * FROM Products
WHERE CategoryID IN (SELECT CategoryID FROM Categories WHERE CategoryName LIKE '%food%');

-- Subquery in EXISTS
SELECT * FROM Customers c
WHERE EXISTS (
    SELECT 1 FROM Orders o 
    WHERE o.CustomerID = c.CustomerID 
    AND o.OrderDate >= DATEADD(YEAR, -1, GETDATE())
);
```

### Common Table Expressions (CTEs)

CTEs provide a way to define temporary result sets that can be referenced within a query. They improve readability and enable recursive queries.

```sql
-- Basic CTE
WITH CategorySales AS (
    SELECT 
        c.CategoryName,
        COUNT(o.OrderID) AS OrderCount,
        SUM(od.Quantity * od.UnitPrice) AS TotalSales
    FROM Categories c
    JOIN Products p ON c.CategoryID = p.CategoryID
    JOIN OrderDetails od ON p.ProductID = od.ProductID
    JOIN Orders o ON od.OrderID = o.OrderID
    GROUP BY c.CategoryName
)
SELECT * FROM CategorySales
WHERE TotalSales > 10000
ORDER BY TotalSales DESC;

-- Multiple CTEs
WITH 
TopCustomers AS (
    SELECT TOP 10 CustomerID, SUM(TotalAmount) AS TotalSpent
    FROM Orders
    GROUP BY CustomerID
    ORDER BY TotalSpent DESC
),
CustomerOrders AS (
    SELECT CustomerID, COUNT(*) AS OrderCount
    FROM Orders
    GROUP BY CustomerID
)
SELECT 
    c.FirstName,
    c.LastName,
    tc.TotalSpent,
    co.OrderCount
FROM TopCustomers tc
JOIN Customers c ON tc.CustomerID = c.CustomerID
JOIN CustomerOrders co ON tc.CustomerID = co.CustomerID;

-- CTE for data modification
WITH DuplicateProducts AS (
    SELECT ProductID,
           ROW_NUMBER() OVER (PARTITION BY ProductName ORDER BY ProductID) AS RowNum
    FROM Products
)
DELETE FROM Products
WHERE ProductID IN (SELECT ProductID FROM DuplicateProducts WHERE RowNum > 1);
```

### Recursive CTEs

Recursive CTEs reference themselves, enabling hierarchical queries.

```sql
-- Employee hierarchy
WITH EmployeeHierarchy AS (
    -- Anchor member
    SELECT 
        EmployeeID,
        FirstName,
        LastName,
        ManagerID,
        0 AS Level,
        CAST(FirstName AS VARCHAR(1000)) AS Path
    FROM Employees
    WHERE ManagerID IS NULL
    
    UNION ALL
    
    -- Recursive member
    SELECT 
        e.EmployeeID,
        e.FirstName,
        e.LastName,
        e.ManagerID,
        eh.Level + 1,
        CAST(eh.Path + ' -> ' + e.FirstName AS VARCHAR(1000))
    FROM Employees e
    INNER JOIN EmployeeHierarchy eh ON e.ManagerID = eh.EmployeeID
)
SELECT * FROM EmployeeHierarchy
ORDER BY Level, Path;

-- Bill of materials
WITH BillOfMaterials AS (
    -- Anchor - final products
    SELECT 
        ProductID,
        ComponentID,
        Quantity,
        0 AS Level
    FROM ProductComponents
    WHERE ProductID = 1
    
    UNION ALL
    
    -- Recursive - components of components
    SELECT 
        bom.ProductID,
        pc.ComponentID,
        bom.Quantity * pc.Quantity,
        bom.Level + 1
    FROM BillOfMaterials bom
    JOIN ProductComponents pc ON bom.ComponentID = pc.ProductID
)
SELECT * FROM BillOfMaterials;

-- Generate date series
WITH DateSeries AS (
    SELECT CAST('2024-01-01' AS DATE) AS DateValue
    
    UNION ALL
    
    SELECT DATEADD(DAY, 1, DateValue)
    FROM DateSeries
    WHERE DateValue < '2024-12-31'
)
SELECT DateValue FROM DateSeries
OPTION (MAXRECURSION 366);  -- Increase limit if needed
```

### Window Functions

Window functions perform calculations across a set of rows related to the current row.

```sql
-- ROW_NUMBER
SELECT 
    ProductName,
    UnitPrice,
    ROW_NUMBER() OVER (ORDER BY UnitPrice DESC) AS RowNum,
    ROW_NUMBER() OVER (PARTITION BY CategoryID ORDER BY UnitPrice DESC) AS CategoryRank
FROM Products;

-- RANK and DENSE_RANK
SELECT 
    ProductName,
    UnitPrice,
    RANK() OVER (ORDER BY UnitPrice DESC) AS Rank,        -- Gaps for ties
    DENSE_RANK() OVER (ORDER BY UnitPrice DESC) AS DenseRank,  -- No gaps
    ROW_NUMBER() OVER (ORDER BY UnitPrice DESC) AS RowNum
FROM Products;

-- NTILE - divide into groups
SELECT 
    ProductName,
    UnitPrice,
    NTILE(4) OVER (ORDER BY UnitPrice) AS Quartile
FROM Products;

-- Aggregate window functions
SELECT 
    OrderID,
    OrderDate,
    TotalAmount,
    SUM(TotalAmount) OVER (ORDER BY OrderDate) AS RunningTotal,
    AVG(TotalAmount) OVER (ORDER BY OrderDate ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS MovingAverage,
    SUM(TotalAmount) OVER (PARTITION BY CustomerID ORDER BY OrderDate) AS CustomerRunningTotal,
    MAX(TotalAmount) OVER (PARTITION BY CustomerID) AS CustomerMaxOrder,
    COUNT(*) OVER (PARTITION BY CustomerID) AS CustomerOrderCount
FROM Orders;

-- LAG and LEAD
SELECT 
    OrderDate,
    TotalAmount,
    LAG(TotalAmount, 1, 0) OVER (ORDER BY OrderDate) AS PreviousOrder,
    LEAD(TotalAmount, 1, 0) OVER (ORDER BY OrderDate) AS NextOrder,
    TotalAmount - LAG(TotalAmount, 1, 0) OVER (ORDER BY OrderDate) AS ChangeFromPrevious
FROM Orders;

-- FIRST_VALUE and LAST_VALUE
SELECT 
    ProductName,
    CategoryID,
    UnitPrice,
    FIRST_VALUE(UnitPrice) OVER (PARTITION BY CategoryID ORDER BY UnitPrice) AS MinInCategory,
    LAST_VALUE(UnitPrice) OVER (PARTITION BY CategoryID ORDER BY UnitPrice 
        ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING) AS MaxInCategory
FROM Products;
```

---

## 14. Chapter 12: Data Modification - INSERT, UPDATE, DELETE, MERGE

### INSERT Statement

Insert new rows into tables using INSERT. You can insert single rows, multiple rows, or results from a query.

```sql
-- Single row insert
INSERT INTO Customers (FirstName, LastName, Email, Phone)
VALUES ('John', 'Smith', 'john.smith@email.com', '555-1234');

-- Insert with all columns
INSERT INTO Customers
VALUES (DEFAULT, 'Jane', 'Doe', 'jane.doe@email.com', '555-5678', DEFAULT, DEFAULT);

-- Multiple rows insert
INSERT INTO Customers (FirstName, LastName, Email)
VALUES 
    ('Alice', 'Johnson', 'alice@email.com'),
    ('Bob', 'Williams', 'bob@email.com'),
    ('Carol', 'Brown', 'carol@email.com');

-- Insert from SELECT
INSERT INTO CustomerArchive (CustomerID, FirstName, LastName, Email)
SELECT CustomerID, FirstName, LastName, Email
FROM Customers
WHERE CreatedDate < DATEADD(YEAR, -5, GETDATE());

-- Insert with DEFAULT values
INSERT INTO Orders DEFAULT VALUES;

-- Insert with OUTPUT clause
INSERT INTO Customers (FirstName, LastName, Email)
OUTPUT INSERTED.CustomerID, INSERTED.FirstName, INSERTED.LastName
VALUES ('David', 'Miller', 'david@email.com');

-- Insert into table with IDENTITY
SET IDENTITY_INSERT Customers ON;
INSERT INTO Customers (CustomerID, FirstName, LastName)
VALUES (1000, 'Test', 'User');
SET IDENTITY_INSERT Customers OFF;
```

### UPDATE Statement

Modify existing data in tables. Always include a WHERE clause to avoid updating all rows unintentionally.

```sql
-- Simple update
UPDATE Products
SET UnitPrice = 25.00
WHERE ProductID = 1;

-- Update multiple columns
UPDATE Products
SET UnitPrice = 25.00,
    Discontinued = 0,
    LastModified = GETDATE()
WHERE ProductID = 1;

-- Update with calculation
UPDATE Products
SET UnitPrice = UnitPrice * 1.10
WHERE CategoryID = 1;

-- Update with FROM clause
UPDATE p
SET p.UnitPrice = p.UnitPrice * 1.05
FROM Products p
JOIN Categories c ON p.CategoryID = c.CategoryID
WHERE c.CategoryName = 'Beverages';

-- Update with subquery
UPDATE Products
SET UnitPrice = (SELECT AVG(UnitPrice) FROM Products WHERE CategoryID = 1)
WHERE ProductID = 1;

-- Update with CASE
UPDATE Products
SET UnitPrice = CASE 
    WHEN CategoryID = 1 THEN UnitPrice * 1.10
    WHEN CategoryID = 2 THEN UnitPrice * 1.05
    ELSE UnitPrice
END;

-- Update with OUTPUT
UPDATE Products
SET UnitPrice = UnitPrice * 1.10
OUTPUT 
    INSERTED.ProductID,
    DELETED.UnitPrice AS OldPrice,
    INSERTED.UnitPrice AS NewPrice
WHERE CategoryID = 1;

-- Update with TOP
UPDATE TOP (10) Products
SET UnitPrice = UnitPrice * 1.05
WHERE Discontinued = 0;
```

### DELETE Statement

Remove rows from tables. Always include a WHERE clause to avoid deleting all rows.

```sql
-- Simple delete
DELETE FROM Customers WHERE CustomerID = 100;

-- Delete with condition
DELETE FROM Orders 
WHERE OrderDate < DATEADD(YEAR, -5, GETDATE());

-- Delete with JOIN
DELETE od
FROM OrderDetails od
JOIN Orders o ON od.OrderID = o.OrderID
WHERE o.Status = 'Cancelled';

-- Delete with subquery
DELETE FROM Products
WHERE CategoryID IN (SELECT CategoryID FROM Categories WHERE CategoryName = 'Discontinued');

-- Delete with OUTPUT
DELETE FROM Customers
OUTPUT DELETED.CustomerID, DELETED.FirstName, DELETED.LastName
WHERE IsActive = 0;

-- Delete with TOP
DELETE TOP (1000) FROM AuditLog
WHERE LogDate < DATEADD(YEAR, -1, GETDATE());

-- Truncate table (faster, cannot be rolled back in same transaction)
TRUNCATE TABLE TempData;

-- TRUNCATE vs DELETE
-- TRUNCATE: Faster, resets identity, minimal logging, no WHERE clause
-- DELETE: Slower, WHERE clause allowed, can be rolled back, triggers fire
```

### MERGE Statement

MERGE performs INSERT, UPDATE, or DELETE operations based on conditions in a single statement.

```sql
-- Basic MERGE
MERGE INTO Products AS target
USING ProductUpdates AS source
ON target.ProductID = source.ProductID
WHEN MATCHED THEN
    UPDATE SET 
        target.ProductName = source.ProductName,
        target.UnitPrice = source.UnitPrice
WHEN NOT MATCHED THEN
    INSERT (ProductName, UnitPrice, CategoryID)
    VALUES (source.ProductName, source.UnitPrice, source.CategoryID)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;

-- MERGE with OUTPUT
MERGE INTO Customers AS target
USING CustomerStaging AS source
ON target.Email = source.Email
WHEN MATCHED THEN
    UPDATE SET 
        target.FirstName = source.FirstName,
        target.LastName = source.LastName
WHEN NOT MATCHED THEN
    INSERT (FirstName, LastName, Email)
    VALUES (source.FirstName, source.LastName, source.Email)
OUTPUT 
    $action AS ActionType,
    INSERTED.CustomerID,
    INSERTED.Email;

-- MERGE with conditions
MERGE INTO Products AS target
USING NewProducts AS source
ON target.SKU = source.SKU
WHEN MATCHED AND target.LastModified < source.LastModified THEN
    UPDATE SET 
        target.ProductName = source.ProductName,
        target.UnitPrice = source.UnitPrice,
        target.LastModified = source.LastModified
WHEN NOT MATCHED THEN
    INSERT (SKU, ProductName, UnitPrice, LastModified)
    VALUES (source.SKU, source.ProductName, source.UnitPrice, source.LastModified);
```

---

## 15. Chapter 13: Indexes - Performance Foundation

### Understanding Indexes

Indexes are database objects that improve query performance by providing fast access paths to data. Like a book index helps find topics quickly, database indexes help find rows quickly. However, indexes incur overhead during data modification and consume storage space.

SQL Server supports two main index types: clustered and nonclustered. A clustered index determines the physical order of data in a table—there can be only one per table. Nonclustered indexes are separate structures that point to data rows. Understanding when to create each type is crucial for performance optimization.

### Clustered Indexes

The clustered index organizes data physically in the order of the index key. The leaf level of a clustered index is the actual data pages. This makes clustered indexes ideal for range queries and ordered retrieval. Choose the clustered index key carefully—it affects all nonclustered indexes.

```sql
-- Create clustered index on primary key (default for PRIMARY KEY)
CREATE TABLE Orders (
    OrderID INT IDENTITY(1,1) PRIMARY KEY CLUSTERED,
    CustomerID INT,
    OrderDate DATETIME2,
    TotalAmount DECIMAL(18,2)
);

-- Create clustered index separately
CREATE CLUSTERED INDEX IX_Orders_OrderDate 
ON Orders(OrderDate);

-- Create clustered index with options
CREATE CLUSTERED INDEX IX_Orders_OrderDate
ON Orders(OrderDate)
WITH (
    PAD_INDEX = ON,
    FILLFACTOR = 80,
    SORT_IN_TEMPDB = ON,
    STATISTICS_NORECOMPUTE = OFF,
    DROP_EXISTING = OFF,
    ONLINE = ON
);

-- Drop clustered index
DROP INDEX IX_Orders_OrderDate ON Orders;
```

### Nonclustered Indexes

Nonclustered indexes are separate structures that contain index keys and pointers to data rows (row locators). They're useful for queries that filter or sort on non-key columns. A table can have up to 999 nonclustered indexes.

```sql
-- Create basic nonclustered index
CREATE NONCLUSTERED INDEX IX_Products_CategoryID
ON Products(CategoryID);

-- Create composite index
CREATE NONCLUSTERED INDEX IX_Products_Category_Price
ON Products(CategoryID, UnitPrice);

-- Create index with included columns
CREATE NONCLUSTERED INDEX IX_Products_CategoryID_Include
ON Products(CategoryID)
INCLUDE (ProductName, UnitPrice, UnitsInStock);

-- Create filtered index
CREATE NONCLUSTERED INDEX IX_Products_ActiveProducts
ON Products(CategoryID)
WHERE Discontinued = 0;

-- Create unique index
CREATE UNIQUE NONCLUSTERED INDEX IX_Customers_Email
ON Customers(Email)
WHERE Email IS NOT NULL;

-- Create index with column order (descending)
CREATE NONCLUSTERED INDEX IX_Orders_Date_Desc
ON Orders(OrderDate DESC);

-- Create covering index
CREATE NONCLUSTERED INDEX IX_Orders_Covering
ON Orders(CustomerID, OrderDate)
INCLUDE (TotalAmount, Status);

-- Index with compression
CREATE NONCLUSTERED INDEX IX_Products_Compressed
ON Products(CategoryID)
WITH (DATA_COMPRESSION = PAGE);
```

### Index Design Guidelines

Design indexes based on query patterns, not just on all columns. Focus on columns used in WHERE clauses, JOIN conditions, ORDER BY, and GROUP BY. Consider the selectivity of columns—high selectivity (many unique values) makes better indexes.

```sql
-- Analyze index usage
SELECT 
    OBJECT_NAME(i.object_id) AS TableName,
    i.name AS IndexName,
    i.type_desc,
    s.user_seeks,
    s.user_scans,
    s.user_lookups,
    s.user_updates,
    s.last_user_seek,
    s.last_user_scan
FROM sys.indexes i
LEFT JOIN sys.dm_db_index_usage_stats s 
    ON i.object_id = s.object_id AND i.index_id = s.index_id
WHERE OBJECT_NAME(i.object_id) = 'Products'
ORDER BY s.user_seeks + s.user_scans DESC;

-- Find missing indexes
SELECT 
    migs.avg_total_user_cost * migs.avg_user_impact * migs.user_seeks AS ImprovementScore,
    mid.statement AS TableName,
    mid.equality_columns,
    mid.inequality_columns,
    mid.included_columns
FROM sys.dm_db_missing_index_details mid
JOIN sys.dm_db_missing_index_groups mig ON mid.index_handle = mig.index_handle
JOIN sys.dm_db_missing_index_group_stats migs ON mig.index_group_handle = migs.group_handle
ORDER BY ImprovementScore DESC;

-- Find unused indexes
SELECT 
    OBJECT_NAME(i.object_id) AS TableName,
    i.name AS IndexName,
    i.type_desc,
    s.user_seeks,
    s.user_scans,
    s.user_lookups,
    s.user_updates,
    p.rows
FROM sys.indexes i
LEFT JOIN sys.dm_db_index_usage_stats s 
    ON i.object_id = s.object_id AND i.index_id = s.index_id
JOIN sys.partitions p ON i.object_id = p.object_id AND i.index_id = p.index_id
WHERE OBJECT_NAME(i.object_id) NOT LIKE 'sys%'
  AND i.type_desc <> 'HEAP'
  AND (s.user_seeks = 0 OR s.user_seeks IS NULL)
  AND (s.user_scans = 0 OR s.user_scans IS NULL)
  AND (s.user_lookups = 0 OR s.user_lookups IS NULL)
ORDER BY p.rows DESC;
```

### Index Maintenance

Indexes become fragmented over time as data is modified. Regular maintenance ensures optimal performance.

```sql
-- Check index fragmentation
SELECT 
    OBJECT_NAME(ips.object_id) AS TableName,
    i.name AS IndexName,
    ips.avg_fragmentation_in_percent,
    ips.fragment_count,
    ips.page_count
FROM sys.dm_db_index_physical_stats(DB_ID(), NULL, NULL, NULL, 'LIMITED') ips
JOIN sys.indexes i ON ips.object_id = i.object_id AND ips.index_id = i.index_id
WHERE ips.avg_fragmentation_in_percent > 10
ORDER BY ips.avg_fragmentation_in_percent DESC;

-- Reorganize index (online, for 5-30% fragmentation)
ALTER INDEX IX_Products_CategoryID ON Products REORGANIZE;

-- Rebuild index (for >30% fragmentation)
ALTER INDEX IX_Products_CategoryID ON Products REBUILD;

-- Rebuild all indexes on a table
ALTER INDEX ALL ON Products REBUILD
WITH (FILLFACTOR = 80, SORT_IN_TEMPDB = ON);

-- Rebuild index online (Enterprise edition)
ALTER INDEX IX_Products_CategoryID ON Products REBUILD
WITH (ONLINE = ON);

-- Disable index (for bulk imports)
ALTER INDEX IX_Products_CategoryID ON Products DISABLE;

-- Enable index
ALTER INDEX IX_Products_CategoryID ON Products REBUILD;
```

---

## 16. Chapter 14: Views

### Creating Views

Views are virtual tables defined by SELECT statements. They simplify complex queries, provide security abstraction, and present data in customized formats.

```sql
-- Basic view
CREATE VIEW vw_CustomerOrders AS
SELECT 
    c.CustomerID,
    c.FirstName,
    c.LastName,
    o.OrderID,
    o.OrderDate,
    o.TotalAmount
FROM Customers c
INNER JOIN Orders o ON c.CustomerID = o.CustomerID;

-- Use the view
SELECT * FROM vw_CustomerOrders WHERE CustomerID = 1;

-- View with schema binding
CREATE VIEW vw_ActiveProducts WITH SCHEMABINDING AS
SELECT 
    ProductID,
    ProductName,
    UnitPrice,
    CategoryID
FROM dbo.Products
WHERE Discontinued = 0;

-- View with encryption
CREATE VIEW vw_SensitiveData WITH ENCRYPTION AS
SELECT CustomerID, Email FROM Customers;

-- View with CHECK OPTION
CREATE VIEW vw_USCustomers AS
SELECT CustomerID, FirstName, LastName, Country
FROM Customers
WHERE Country = 'USA'
WITH CHECK OPTION;

-- Insert through view (must satisfy view definition)
INSERT INTO vw_USCustomers (FirstName, LastName, Country)
VALUES ('John', 'Doe', 'USA');  -- Works

INSERT INTO vw_USCustomers (FirstName, LastName, Country)
VALUES ('Jane', 'Smith', 'Canada');  -- Fails due to CHECK OPTION
```

### Indexed Views (Materialized Views)

Indexed views store results physically, improving performance for complex aggregations. Available in Enterprise edition or with NOEXPAND hint.

```sql
-- Create indexed view
CREATE VIEW vw_CategorySales WITH SCHEMABINDING AS
SELECT 
    c.CategoryID,
    c.CategoryName,
    COUNT_BIG(*) AS ProductCount,
    SUM(ISNULL(p.UnitPrice * p.UnitsInStock, 0)) AS InventoryValue
FROM dbo.Categories c
LEFT JOIN dbo.Products p ON c.CategoryID = p.CategoryID
GROUP BY c.CategoryID, c.CategoryName;

-- Create unique clustered index on the view
CREATE UNIQUE CLUSTERED INDEX IX_vw_CategorySales
ON vw_CategorySales(CategoryID);

-- Create additional nonclustered index
CREATE NONCLUSTERED INDEX IX_vw_CategorySales_Name
ON vw_CategorySales(CategoryName);

-- Query the indexed view
SELECT * FROM vw_CategorySales;

-- Force use of indexed view
SELECT * FROM vw_CategorySales WITH (NOEXPAND);
```

### Modifying and Dropping Views

```sql
-- Alter view
ALTER VIEW vw_CustomerOrders AS
SELECT 
    c.CustomerID,
    c.FirstName + ' ' + c.LastName AS FullName,
    o.OrderID,
    o.OrderDate,
    o.TotalAmount,
    o.Status
FROM Customers c
INNER JOIN Orders o ON c.CustomerID = o.CustomerID
WHERE o.Status != 'Cancelled';

-- Drop view
DROP VIEW IF EXISTS vw_CustomerOrders;

-- Drop multiple views
DROP VIEW IF EXISTS vw_CustomerOrders, vw_ProductSales, vw_MonthlyReport;

-- Refresh view metadata
EXEC sp_refreshview 'vw_CustomerOrders';

-- View definition
SELECT definition FROM sys.sql_modules
WHERE object_id = OBJECT_ID('vw_CustomerOrders');
```

---

## 17. Chapter 15: Stored Procedures

### Creating Stored Procedures

Stored procedures are compiled T-SQL code stored in the database. They provide code reuse, security, performance benefits, and reduced network traffic.

```sql
-- Basic stored procedure
CREATE PROCEDURE usp_GetCustomerOrders
    @CustomerID INT
AS
BEGIN
    SELECT 
        o.OrderID,
        o.OrderDate,
        o.TotalAmount,
        o.Status
    FROM Orders o
    WHERE o.CustomerID = @CustomerID
    ORDER BY o.OrderDate DESC;
END;

-- Execute stored procedure
EXEC usp_GetCustomerOrders @CustomerID = 1;
EXEC usp_GetCustomerOrders 1;  -- Parameter by position

-- Procedure with multiple parameters
CREATE PROCEDURE usp_SearchProducts
    @ProductName VARCHAR(100) = NULL,
    @CategoryID INT = NULL,
    @MinPrice DECIMAL(18,2) = NULL,
    @MaxPrice DECIMAL(18,2) = NULL
AS
BEGIN
    SELECT 
        ProductID,
        ProductName,
        UnitPrice,
        CategoryID
    FROM Products
    WHERE (@ProductName IS NULL OR ProductName LIKE '%' + @ProductName + '%')
      AND (@CategoryID IS NULL OR CategoryID = @CategoryID)
      AND (@MinPrice IS NULL OR UnitPrice >= @MinPrice)
      AND (@MaxPrice IS NULL OR UnitPrice <= @MaxPrice);
END;

-- Execute with named parameters
EXEC usp_SearchProducts 
    @ProductName = 'Ch',
    @MinPrice = 10;

-- Execute with default values
EXEC usp_SearchProducts;
```

### Output Parameters

Return values through output parameters for additional information beyond the result set.

```sql
-- Procedure with output parameter
CREATE PROCEDURE usp_GetCustomerStats
    @CustomerID INT,
    @TotalOrders INT OUTPUT,
    @TotalSpent DECIMAL(18,2) OUTPUT,
    @AverageOrder DECIMAL(18,2) OUTPUT
AS
BEGIN
    SELECT 
        @TotalOrders = COUNT(*),
        @TotalSpent = ISNULL(SUM(TotalAmount), 0),
        @AverageOrder = ISNULL(AVG(TotalAmount), 0)
    FROM Orders
    WHERE CustomerID = @CustomerID;
END;

-- Execute and capture output
DECLARE @Orders INT, @Spent DECIMAL(18,2), @Avg DECIMAL(18,2);
EXEC usp_GetCustomerStats 
    @CustomerID = 1,
    @TotalOrders = @Orders OUTPUT,
    @TotalSpent = @Spent OUTPUT,
    @AverageOrder = @Avg OUTPUT;

SELECT @Orders AS TotalOrders, @Spent AS TotalSpent, @Avg AS AverageOrder;
```

### Return Values

Use RETURN to indicate success/failure or return a status code.

```sql
-- Procedure with return value
CREATE PROCEDURE usp_DeleteCustomer
    @CustomerID INT
AS
BEGIN
    SET NOCOUNT ON;
    
    -- Check if customer has orders
    IF EXISTS (SELECT 1 FROM Orders WHERE CustomerID = @CustomerID)
    BEGIN
        RETURN -1;  -- Cannot delete, has orders
    END
    
    -- Delete customer
    DELETE FROM Customers WHERE CustomerID = @CustomerID;
    
    IF @@ROWCOUNT = 0
        RETURN -2;  -- Customer not found
    
    RETURN 0;  -- Success
END;

-- Execute and capture return value
DECLARE @Result INT;
EXEC @Result = usp_DeleteCustomer @CustomerID = 100;

IF @Result = 0
    PRINT 'Customer deleted successfully';
ELSE IF @Result = -1
    PRINT 'Cannot delete customer with existing orders';
ELSE IF @Result = -2
    PRINT 'Customer not found';
```

### Table-Valued Parameters

Pass tables as parameters to procedures for bulk operations.

```sql
-- Create table type
CREATE TYPE dbo.ProductTableType AS TABLE
(
    ProductName VARCHAR(100),
    UnitPrice DECIMAL(18,2),
    CategoryID INT
);

-- Procedure with table parameter
CREATE PROCEDURE usp_InsertProducts
    @Products dbo.ProductTableType READONLY
AS
BEGIN
    INSERT INTO Products (ProductName, UnitPrice, CategoryID)
    SELECT ProductName, UnitPrice, CategoryID
    FROM @Products;
END;

-- Execute with table variable
DECLARE @NewProducts AS dbo.ProductTableType;
INSERT INTO @NewProducts (ProductName, UnitPrice, CategoryID)
VALUES 
    ('Product A', 19.99, 1),
    ('Product B', 29.99, 2),
    ('Product C', 39.99, 1);

EXEC usp_InsertProducts @Products = @NewProducts;
```

### Error Handling in Procedures

Implement robust error handling with TRY-CATCH blocks.

```sql
CREATE PROCEDURE usp_ProcessOrder
    @CustomerID INT,
    @ProductList dbo.ProductTableType READONLY,
    @OrderID INT OUTPUT
AS
BEGIN
    SET NOCOUNT ON;
    
    BEGIN TRY
        BEGIN TRANSACTION;
        
        -- Create order
        INSERT INTO Orders (CustomerID, OrderDate, Status, TotalAmount)
        VALUES (@CustomerID, GETDATE(), 'Pending', 0);
        
        SET @OrderID = SCOPE_IDENTITY();
        
        -- Add order details
        INSERT INTO OrderDetails (OrderID, ProductID, Quantity, UnitPrice)
        SELECT @OrderID, p.ProductID, pl.Quantity, p.UnitPrice
        FROM @ProductList pl
        JOIN Products p ON pl.ProductID = p.ProductID;
        
        -- Update total
        UPDATE o
        SET TotalAmount = (
            SELECT SUM(od.Quantity * od.UnitPrice)
            FROM OrderDetails od
            WHERE od.OrderID = @OrderID
        )
        FROM Orders o
        WHERE o.OrderID = @OrderID;
        
        COMMIT TRANSACTION;
        
        RETURN 0;
    END TRY
    BEGIN CATCH
        IF @@TRANCOUNT > 0
            ROLLBACK TRANSACTION;
        
        -- Log error
        INSERT INTO ErrorLog (ErrorNumber, ErrorSeverity, ErrorState, 
                             ErrorProcedure, ErrorLine, ErrorMessage)
        VALUES (
            ERROR_NUMBER(),
            ERROR_SEVERITY(),
            ERROR_STATE(),
            ERROR_PROCEDURE(),
            ERROR_LINE(),
            ERROR_MESSAGE()
        );
        
        -- Re-throw error
        THROW;
        
        RETURN -1;
    END CATCH
END;
```

---

## 18. Chapter 16: User-Defined Functions

### Scalar Functions

Scalar functions return a single value. Use them for calculations and transformations that need to be reused.

```sql
-- Create scalar function
CREATE FUNCTION dbo.fn_CalculateTax
(
    @Amount DECIMAL(18,2),
    @TaxRate DECIMAL(5,2) = 10.00
)
RETURNS DECIMAL(18,2)
AS
BEGIN
    RETURN @Amount * @TaxRate / 100;
END;

-- Use in query
SELECT 
    OrderID,
    TotalAmount,
    dbo.fn_CalculateTax(TotalAmount, 8.25) AS TaxAmount,
    TotalAmount + dbo.fn_CalculateTax(TotalAmount, 8.25) AS TotalWithTax
FROM Orders;

-- Function with multiple statements
CREATE FUNCTION dbo.fn_GetFullName
(
    @FirstName VARCHAR(50),
    @LastName VARCHAR(50),
    @MiddleName VARCHAR(50) = NULL
)
RETURNS VARCHAR(152)
AS
BEGIN
    DECLARE @FullName VARCHAR(152);
    
    IF @MiddleName IS NULL
        SET @FullName = @FirstName + ' ' + @LastName;
    ELSE
        SET @FullName = @FirstName + ' ' + @MiddleName + ' ' + @LastName;
    
    RETURN @FullName;
END;

-- Drop function
DROP FUNCTION IF EXISTS dbo.fn_CalculateTax;
```

### Inline Table-Valued Functions

Inline table-valued functions return a table result set. They're more efficient than scalar functions because they can be inlined into queries.

```sql
-- Create inline table-valued function
CREATE FUNCTION dbo.fn_GetOrdersByCustomer
(
    @CustomerID INT,
    @StartDate DATETIME2 = NULL,
    @EndDate DATETIME2 = NULL
)
RETURNS TABLE
AS
RETURN
(
    SELECT 
        o.OrderID,
        o.OrderDate,
        o.TotalAmount,
        o.Status,
        COUNT(od.OrderDetailID) AS ItemCount
    FROM Orders o
    LEFT JOIN OrderDetails od ON o.OrderID = od.OrderID
    WHERE o.CustomerID = @CustomerID
      AND (@StartDate IS NULL OR o.OrderDate >= @StartDate)
      AND (@EndDate IS NULL OR o.OrderDate <= @EndDate)
    GROUP BY o.OrderID, o.OrderDate, o.TotalAmount, o.Status
);

-- Use function
SELECT * FROM dbo.fn_GetOrdersByCustomer(1, '2024-01-01', DEFAULT);

-- Use with CROSS APPLY (for each row)
SELECT 
    c.CustomerID,
    c.FirstName,
    o.OrderID,
    o.TotalAmount
FROM Customers c
CROSS APPLY dbo.fn_GetOrdersByCustomer(c.CustomerID) o
WHERE o.TotalAmount > 100;
```

### Multi-Statement Table-Valued Functions

Multi-statement functions allow complex logic but are less efficient than inline functions.

```sql
-- Create multi-statement table-valued function
CREATE FUNCTION dbo.fn_GetCustomerOrderSummary
(
    @CustomerID INT
)
RETURNS @Summary TABLE
(
    CustomerID INT,
    CustomerName VARCHAR(100),
    TotalOrders INT,
    TotalSpent DECIMAL(18,2),
    AverageOrder DECIMAL(18,2),
    FirstOrderDate DATETIME2,
    LastOrderDate DATETIME2,
    FavoriteCategory VARCHAR(100)
)
AS
BEGIN
    -- Get customer info and order stats
    INSERT INTO @Summary (CustomerID, CustomerName, TotalOrders, TotalSpent, 
                          AverageOrder, FirstOrderDate, LastOrderDate)
    SELECT 
        c.CustomerID,
        c.FirstName + ' ' + c.LastName,
        COUNT(o.OrderID),
        ISNULL(SUM(o.TotalAmount), 0),
        ISNULL(AVG(o.TotalAmount), 0),
        MIN(o.OrderDate),
        MAX(o.OrderDate)
    FROM Customers c
    LEFT JOIN Orders o ON c.CustomerID = o.CustomerID
    WHERE c.CustomerID = @CustomerID
    GROUP BY c.CustomerID, c.FirstName, c.LastName;
    
    -- Update favorite category
    UPDATE s
    SET FavoriteCategory = (
        SELECT TOP 1 c.CategoryName
        FROM Orders o
        JOIN OrderDetails od ON o.OrderID = od.OrderID
        JOIN Products p ON od.ProductID = p.ProductID
        JOIN Categories c ON p.CategoryID = c.CategoryID
        WHERE o.CustomerID = @CustomerID
        GROUP BY c.CategoryName
        ORDER BY COUNT(*) DESC
    )
    FROM @Summary s;
    
    RETURN;
END;

-- Use function
SELECT * FROM dbo.fn_GetCustomerOrderSummary(1);
```

---

## 19. Chapter 17: Triggers

### DML Triggers

Triggers are special stored procedures that automatically execute in response to DML events (INSERT, UPDATE, DELETE).

```sql
-- AFTER trigger
CREATE TRIGGER tr_Orders_AfterInsert
ON Orders
AFTER INSERT
AS
BEGIN
    SET NOCOUNT ON;
    
    -- Log new orders
    INSERT INTO OrderLog (OrderID, Action, LogDate, UserName)
    SELECT 
        OrderID, 
        'INSERT', 
        GETDATE(), 
        SUSER_NAME()
    FROM inserted;
END;

-- Trigger for multiple actions
CREATE TRIGGER tr_Products_Audit
ON Products
AFTER INSERT, UPDATE, DELETE
AS
BEGIN
    SET NOCOUNT ON;
    
    -- Handle INSERT
    IF EXISTS (SELECT 1 FROM inserted) AND NOT EXISTS (SELECT 1 FROM deleted)
    BEGIN
        INSERT INTO ProductAudit (ProductID, Action, OldValue, NewValue, ChangedBy, ChangedDate)
        SELECT ProductID, 'INSERT', NULL, ProductName, SUSER_NAME(), GETDATE()
        FROM inserted;
    END
    
    -- Handle UPDATE
    IF EXISTS (SELECT 1 FROM inserted) AND EXISTS (SELECT 1 FROM deleted)
    BEGIN
        INSERT INTO ProductAudit (ProductID, Action, OldValue, NewValue, ChangedBy, ChangedDate)
        SELECT 
            i.ProductID, 
            'UPDATE', 
            d.ProductName, 
            i.ProductName, 
            SUSER_NAME(), 
            GETDATE()
        FROM inserted i
        JOIN deleted d ON i.ProductID = d.ProductID
        WHERE i.ProductName <> d.ProductName;
    END
    
    -- Handle DELETE
    IF NOT EXISTS (SELECT 1 FROM inserted) AND EXISTS (SELECT 1 FROM deleted)
    BEGIN
        INSERT INTO ProductAudit (ProductID, Action, OldValue, NewValue, ChangedBy, ChangedDate)
        SELECT ProductID, 'DELETE', ProductName, NULL, SUSER_NAME(), GETDATE()
        FROM deleted;
    END
END;

-- INSTEAD OF trigger (for views or complex logic)
CREATE TRIGGER tr_Orders_InsteadOfDelete
ON Orders
INSTEAD OF DELETE
AS
BEGIN
    SET NOCOUNT ON;
    
    -- Check for shipped orders
    IF EXISTS (SELECT 1 FROM deleted WHERE Status = 'Shipped')
    BEGIN
        RAISERROR('Cannot delete shipped orders', 16, 1);
        RETURN;
    END
    
    -- Delete order details first
    DELETE FROM OrderDetails
    WHERE OrderID IN (SELECT OrderID FROM deleted);
    
    -- Then delete orders
    DELETE FROM Orders
    WHERE OrderID IN (SELECT OrderID FROM deleted);
END;
```

### DDL Triggers

DDL triggers respond to database or server-level events like CREATE, ALTER, DROP.

```sql
-- Database-level DDL trigger
CREATE TRIGGER tr_PreventTableDrop
ON DATABASE
FOR DROP_TABLE
AS
BEGIN
    RAISERROR('Dropping tables is not allowed in this database.', 16, 1);
    ROLLBACK TRANSACTION;
END;

-- Audit DDL changes
CREATE TRIGGER tr_DDLAudit
ON DATABASE
FOR DDL_DATABASE_LEVEL_EVENTS
AS
BEGIN
    INSERT INTO DDLAuditLog (EventType, ObjectName, ObjectType, SQLCommand, UserName, EventDate)
    SELECT 
        EVENTDATA().value('(/EVENT_INSTANCE/EventType)[1]', 'VARCHAR(100)'),
        EVENTDATA().value('(/EVENT_INSTANCE/ObjectName)[1]', 'VARCHAR(100)'),
        EVENTDATA().value('(/EVENT_INSTANCE/ObjectType)[1]', 'VARCHAR(100)'),
        EVENTDATA().value('(/EVENT_INSTANCE/TSQLCommand/CommandText)[1]', 'NVARCHAR(MAX)'),
        SUSER_NAME(),
        GETDATE();
END;

-- Server-level DDL trigger
CREATE TRIGGER tr_ServerLoginAudit
ON ALL SERVER
FOR LOGIN_EVENTS
AS
BEGIN
    INSERT INTO master.dbo.LoginAudit (EventType, LoginName, EventData, EventDate)
    SELECT 
        EVENTDATA().value('(/EVENT_INSTANCE/EventType)[1]', 'VARCHAR(100)'),
        EVENTDATA().value('(/EVENT_INSTANCE/LoginName)[1]', 'VARCHAR(100)'),
        EVENTDATA(),
        GETDATE();
END;

-- Enable/Disable trigger
DISABLE TRIGGER tr_Orders_AfterInsert ON Orders;
ENABLE TRIGGER tr_Orders_AfterInsert ON Orders;

-- Drop trigger
DROP TRIGGER IF EXISTS tr_Orders_AfterInsert;
```

---

## 20. Chapter 18: Transactions and Locking

### Transaction Basics

Transactions group multiple operations into a single unit of work that follows ACID properties: Atomicity, Consistency, Isolation, and Durability.

```sql
-- Basic transaction
BEGIN TRANSACTION;

BEGIN TRY
    UPDATE Accounts SET Balance = Balance - 100 WHERE AccountID = 1;
    UPDATE Accounts SET Balance = Balance + 100 WHERE AccountID = 2;
    
    COMMIT TRANSACTION;
END TRY
BEGIN CATCH
    IF @@TRANCOUNT > 0
        ROLLBACK TRANSACTION;
    
    THROW;
END CATCH;

-- Transaction with savepoint
BEGIN TRANSACTION;

BEGIN TRY
    UPDATE Products SET UnitsInStock = UnitsInStock - 10 WHERE ProductID = 1;
    
    SAVE TRANSACTION ReduceStock;
    
    BEGIN TRY
        INSERT INTO OrderDetails (OrderID, ProductID, Quantity)
        VALUES (1000, 1, 10);
    END TRY
    BEGIN CATCH
        -- Rollback to savepoint if detail insert fails
        IF @@TRANCOUNT > 0
            ROLLBACK TRANSACTION ReduceStock;
    END CATCH
    
    COMMIT TRANSACTION;
END TRY
BEGIN CATCH
    IF @@TRANCOUNT > 0
        ROLLBACK TRANSACTION;
END CATCH;

-- Nested transactions (use savepoints for partial rollback)
DECLARE @TranCount INT = @@TRANCOUNT;

IF @TranCount = 0
    BEGIN TRANSACTION;
ELSE
    SAVE TRANSACTION MySavePoint;

-- Do work...

IF @TranCount = 0
    COMMIT TRANSACTION;
```

### Isolation Levels

Isolation levels control how transactions interact with each other, balancing consistency and concurrency.

```sql
-- READ UNCOMMITTED (allows dirty reads)
SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED;
SELECT * FROM Products;
-- Can read uncommitted changes from other transactions

-- READ COMMITTED (default, prevents dirty reads)
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
SELECT * FROM Products;
-- Only reads committed data, but can get non-repeatable reads

-- REPEATABLE READ (prevents non-repeatable reads)
SET TRANSACTION ISOLATION LEVEL REPEATABLE READ;
BEGIN TRANSACTION;
SELECT * FROM Products WHERE CategoryID = 1;
-- Other transactions cannot modify these rows until commit
COMMIT TRANSACTION;

-- SERIALIZABLE (highest isolation, prevents phantom reads)
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
BEGIN TRANSACTION;
SELECT * FROM Products WHERE CategoryID = 1;
-- Prevents inserts that would match the WHERE clause
COMMIT TRANSACTION;

-- SNAPSHOT (uses row versioning)
ALTER DATABASE CurrentDB SET ALLOW_SNAPSHOT_ISOLATION ON;
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;
BEGIN TRANSACTION;
SELECT * FROM Products;
-- Sees data as it existed at transaction start
COMMIT TRANSACTION;

-- READ COMMITTED SNAPSHOT (default for Azure SQL Database)
ALTER DATABASE CurrentDB SET READ_COMMITTED_SNAPSHOT ON;
-- READ COMMITTED uses row versioning instead of locking

-- Using table hints
SELECT * FROM Products WITH (NOLOCK);  -- Same as READ UNCOMMITTED
SELECT * FROM Products WITH (READCOMMITTEDLOCK);  -- Force blocking
SELECT * FROM Products WITH (UPDLOCK);  -- Take update lock
SELECT * FROM Products WITH (XLOCK);    -- Take exclusive lock
```

### Lock Types and Monitoring

```sql
-- View current locks
SELECT 
    request_session_id AS SessionID,
    resource_type AS ResourceType,
    resource_database_id AS DatabaseID,
    DB_NAME(resource_database_id) AS DatabaseName,
    resource_associated_entity_id AS ResourceID,
    request_mode AS LockMode,
    request_status AS Status
FROM sys.dm_tran_locks
WHERE resource_type = 'OBJECT';

-- View blocking
SELECT 
    blocking.session_id AS BlockingSessionID,
    blocked.session_id AS BlockedSessionID,
    DB_NAME(blocked.database_id) AS DatabaseName,
    blocked.wait_type,
    blocked.wait_time/1000 AS WaitTimeSeconds,
    blocking_sql.text AS BlockingSQL,
    blocked_sql.text AS BlockedSQL
FROM sys.dm_exec_requests blocked
JOIN sys.dm_exec_sessions blocking ON blocked.blocking_session_id = blocking.session_id
CROSS APPLY sys.dm_exec_sql_text(blocked.sql_handle) blocked_sql
CROSS APPLY sys.dm_exec_sql_text(blocking.most_recent_sql_handle) blocking_sql;

-- Kill blocking session
KILL 53;  -- Replace with session ID

-- Deadlock graph
SELECT 
    XEventData.XEvent.value('(data/value)[1]', 'varchar(max)') AS DeadlockGraph
FROM (
    SELECT CAST(target_data AS XML) AS TargetData
    FROM sys.dm_xe_session_targets st
    JOIN sys.dm_xe_sessions s ON s.address = st.event_session_address
    WHERE s.name = 'system_health'
      AND st.target_name = 'ring_buffer'
) AS Data
CROSS APPLY TargetData.nodes('RingBufferTarget/event[@name="xml_deadlock_report"]/data/value') AS XEventData(XEvent);
```

---

## 21. Chapter 19: Error Handling

### TRY-CATCH

Implement structured error handling with TRY-CATCH blocks.

```sql
-- Basic TRY-CATCH
BEGIN TRY
    SELECT 1/0 AS Result;  -- Division by zero error
END TRY
BEGIN CATCH
    SELECT 
        ERROR_NUMBER() AS ErrorNumber,
        ERROR_SEVERITY() AS ErrorSeverity,
        ERROR_STATE() AS ErrorState,
        ERROR_PROCEDURE() AS ErrorProcedure,
        ERROR_LINE() AS ErrorLine,
        ERROR_MESSAGE() AS ErrorMessage;
END CATCH;

-- THROW (SQL Server 2012+)
BEGIN TRY
    SELECT 1/0;
END TRY
BEGIN CATCH
    THROW;  -- Re-throw the error
END CATCH;

-- THROW with custom message
THROW 50001, 'Custom error message', 1;

-- RAISERROR
RAISERROR('This is an error message', 16, 1);

-- With formatting
RAISERROR('Error in procedure %s at line %d', 16, 1, 
          'MyProcedure', 100);

-- With NOWAIT (send immediately)
RAISERROR('Processing started', 0, 1) WITH NOWAIT;

-- Create custom error message
EXEC sp_addmessage 
    @msgnum = 50001, 
    @severity = 16, 
    @msgtext = 'Customer %s has exceeded credit limit of %d';

-- Use custom message
RAISERROR(50001, 16, 1, 'Acme Corp', 10000);
```

### Custom Error Handling

```sql
-- Comprehensive error handling procedure
CREATE PROCEDURE dbo.usp_LogError
AS
BEGIN
    SET NOCOUNT ON;
    
    DECLARE @ErrorNumber INT = ERROR_NUMBER();
    DECLARE @ErrorSeverity INT = ERROR_SEVERITY();
    DECLARE @ErrorState INT = ERROR_STATE();
    DECLARE @ErrorProcedure NVARCHAR(128) = ERROR_PROCEDURE();
    DECLARE @ErrorLine INT = ERROR_LINE();
    DECLARE @ErrorMessage NVARCHAR(4000) = ERROR_MESSAGE();
    DECLARE @ErrorDateTime DATETIME2 = SYSDATETIME();
    DECLARE @UserName NVARCHAR(128) = SUSER_NAME();
    
    -- Log to error table
    INSERT INTO ErrorLog 
    (ErrorNumber, ErrorSeverity, ErrorState, ErrorProcedure, 
     ErrorLine, ErrorMessage, ErrorDateTime, UserName)
    VALUES
    (@ErrorNumber, @ErrorSeverity, @ErrorState, @ErrorProcedure,
     @ErrorLine, @ErrorMessage, @ErrorDateTime, @UserName);
    
    -- Return error information
    SELECT 
        @ErrorNumber AS ErrorNumber,
        @ErrorSeverity AS ErrorSeverity,
        @ErrorState AS ErrorState,
        @ErrorProcedure AS ErrorProcedure,
        @ErrorLine AS ErrorLine,
        @ErrorMessage AS ErrorMessage;
END;

-- Use in procedures
CREATE PROCEDURE dbo.usp_ProcessOrder
    @OrderID INT
AS
BEGIN
    BEGIN TRY
        BEGIN TRANSACTION;
        
        -- Processing logic here
        UPDATE Orders SET Status = 'Processing' WHERE OrderID = @OrderID;
        
        COMMIT TRANSACTION;
    END TRY
    BEGIN CATCH
        IF @@TRANCOUNT > 0
            ROLLBACK TRANSACTION;
        
        EXEC dbo.usp_LogError;
        THROW;  -- Re-throw to client
    END CATCH
END;
```

---

## 22. Chapter 20: Performance Tuning

### Query Execution Plans

Execution plans show how SQL Server executes queries, revealing performance bottlenecks.

```sql
-- Enable actual execution plan
SET STATISTICS IO ON;
SET STATISTICS TIME ON;

SELECT * FROM Products WHERE CategoryID = 1;

-- Results include:
-- Table 'Products'. Scan count 1, logical reads 5, physical reads 0...
-- SQL Server Execution Times: CPU time = 0 ms, elapsed time = 0 ms.

SET STATISTICS IO OFF;
SET STATISTICS TIME OFF;

-- View estimated execution plan (Ctrl+L in SSMS)
-- View actual execution plan (Ctrl+M in SSMS)

-- Query plan cache
SELECT 
    cp.usecounts,
    cp.size_in_bytes,
    qt.text,
    qp.query_plan
FROM sys.dm_exec_cached_plans cp
CROSS APPLY sys.dm_exec_sql_text(cp.plan_handle) qt
CROSS APPLY sys.dm_exec_query_plan(cp.plan_handle) qp
WHERE qt.text LIKE '%SELECT%Products%';

-- Clear plan cache (use carefully)
DBCC FREEPROCCACHE;
```

### Query Hints

Query hints override optimizer decisions. Use sparingly and document thoroughly.

```sql
-- OPTION hints
SELECT * FROM Products
WHERE CategoryID = 1
OPTION (MAXDOP 1);  -- Use single CPU core

SELECT * FROM Products
OPTION (FAST 100);  -- Optimize for first 100 rows

SELECT * FROM Products
OPTION (RECOMPILE);  -- Recompile each time

-- Join hints
SELECT * FROM Products p
INNER HASH JOIN Categories c ON p.CategoryID = c.CategoryID;

SELECT * FROM Products p
INNER LOOP JOIN Categories c ON p.CategoryID = c.CategoryID;

SELECT * FROM Products p
INNER MERGE JOIN Categories c ON p.CategoryID = c.CategoryID;

-- Index hints
SELECT * FROM Products WITH (INDEX(IX_Products_CategoryID))
WHERE CategoryID = 1;

-- Force specific index
SELECT * FROM Products WITH (INDEX = 1)
WHERE CategoryID = 1;

-- NOLOCK hint (be careful!)
SELECT * FROM Products WITH (NOLOCK);

-- Query trace flag
DBCC TRACEON(4199, -1);  -- Enable query optimizer fixes
```

### Statistics

Statistics help the query optimizer estimate row counts and choose efficient plans.

```sql
-- View statistics
DBCC SHOW_STATISTICS('Products', IX_Products_CategoryID);

-- Update statistics
UPDATE STATISTICS Products;
UPDATE STATISTICS Products IX_Products_CategoryID;

-- Update all statistics in database
EXEC sp_updatestats;

-- Create statistics
CREATE STATISTICS Stats_Products_Name ON Products(ProductName);

-- Auto update statistics settings
ALTER DATABASE MyDB SET AUTO_CREATE_STATISTICS ON;
ALTER DATABASE MyDB SET AUTO_UPDATE_STATISTICS ON;

-- Check statistics age
SELECT 
    OBJECT_NAME(object_id) AS TableName,
    name AS StatisticsName,
    STATS_DATE(object_id, stats_id) AS LastUpdated,
    modification_counter AS RowsModified
FROM sys.stats
CROSS APPLY sys.dm_db_stats_properties(object_id, stats_id)
WHERE OBJECT_NAME(object_id) = 'Products';
```

### Query Store

Query Store tracks query performance over time, enabling troubleshooting and plan forcing.

```sql
-- Enable Query Store
ALTER DATABASE MyDB SET QUERY_STORE = ON;
ALTER DATABASE MyDB SET QUERY_STORE (
    OPERATION_MODE = READ_WRITE,
    MAX_STORAGE_SIZE_MB = 1000,
    QUERY_CAPTURE_MODE = ALL
);

-- View query store data
SELECT 
    qs.query_id,
    qt.query_sql_text,
    rs.avg_duration,
    rs.avg_logical_io_reads,
    rs.count_executions,
    p.query_plan
FROM sys.query_store_query qs
JOIN sys.query_store_query_text qt ON qs.query_text_id = qt.query_text_id
JOIN sys.query_store_plan p ON qs.query_id = p.query_id
JOIN sys.query_store_runtime_stats rs ON p.plan_id = rs.plan_id
ORDER BY rs.avg_duration DESC;

-- Force a specific plan
EXEC sp_query_store_force_plan @query_id = 123, @plan_id = 456;

-- Unforce plan
EXEC sp_query_store_unforce_plan @query_id = 123, @plan_id = 456;
```

---

## 23. Chapter 21: Security

### Logins and Users

```sql
-- Create SQL Server login
CREATE LOGIN AppUser WITH PASSWORD = 'Str0ngP@ssw0rd!';

-- Create login from Windows
CREATE LOGIN [DOMAIN\UserName] FROM WINDOWS;

-- Create database user
CREATE USER AppUser FOR LOGIN AppUser;

-- Create user with default schema
CREATE USER AppUser FOR LOGIN AppUser WITH DEFAULT_SCHEMA = dbo;

-- Create contained database user (SQL Server 2012+)
CREATE USER ContainedUser WITH PASSWORD = 'Str0ngP@ssw0rd!';

-- Drop user and login
DROP USER IF EXISTS AppUser;
DROP LOGIN IF EXISTS AppUser;
```

### Server and Database Roles

```sql
-- Add login to server role
ALTER SERVER ROLE sysadmin ADD MEMBER [DOMAIN\DBA];
ALTER SERVER ROLE securityadmin ADD MEMBER AppUser;

-- Create custom server role
CREATE SERVER ROLE DBA_Auditor;
GRANT VIEW SERVER STATE TO DBA_Auditor;
ALTER SERVER ROLE DBA_Auditor ADD MEMBER AppUser;

-- Add user to database role
ALTER ROLE db_datareader ADD MEMBER AppUser;
ALTER ROLE db_datawriter ADD MEMBER AppUser;

-- Create custom database role
CREATE ROLE OrderProcessor;
GRANT SELECT, INSERT, UPDATE ON Orders TO OrderProcessor;
GRANT SELECT ON Customers TO OrderProcessor;
ALTER ROLE OrderProcessor ADD MEMBER AppUser;

-- View role members
SELECT 
    USER_NAME(member_principal_id) AS MemberName,
    USER_NAME(role_principal_id) AS RoleName
FROM sys.database_role_members;
```

### Permissions

```sql
-- Grant permissions
GRANT SELECT ON Products TO AppUser;
GRANT SELECT, INSERT, UPDATE ON Orders TO AppUser;
GRANT EXECUTE ON usp_ProcessOrder TO AppUser;

-- Grant schema permissions
GRANT SELECT ON SCHEMA::dbo TO AppUser;

-- Grant with GRANT OPTION (can grant to others)
GRANT SELECT ON Products TO AppUser WITH GRANT OPTION;

-- Deny permissions (takes precedence)
DENY DELETE ON Products TO AppUser;

-- Revoke permissions
REVOKE SELECT ON Products FROM AppUser;

-- View permissions
SELECT 
    USER_NAME(grantee_principal_id) AS Grantee,
    USER_NAME(grantor_principal_id) AS Grantor,
    permission_name,
    state_desc
FROM sys.database_permissions
WHERE major_id = OBJECT_ID('Products');
```

### Row-Level Security

```sql
-- Create security predicate function
CREATE FUNCTION dbo.fn_SecurityPredicate(@CustomerID INT)
RETURNS TABLE
WITH SCHEMABINDING
AS
RETURN SELECT 1 AS Result
    WHERE @CustomerID = CAST(SESSION_CONTEXT(N'CustomerID') AS INT)
       OR SESSION_CONTEXT(N'CustomerID') IS NULL;

-- Create security policy
CREATE SECURITY POLICY dbo.CustomerFilter
ADD FILTER PREDICATE dbo.fn_SecurityPredicate(CustomerID)
ON dbo.Orders;

-- Enable/disable policy
ALTER SECURITY POLICY dbo.CustomerFilter WITH (STATE = OFF);
ALTER SECURITY POLICY dbo.CustomerFilter WITH (STATE = ON);

-- Set session context (from application)
EXEC sp_set_session_context N'CustomerID', 123;
```

### Dynamic Data Masking

```sql
-- Create table with masked columns
CREATE TABLE Customers (
    CustomerID INT IDENTITY PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100) MASKED WITH (FUNCTION = 'email()'),
    Phone VARCHAR(20) MASKED WITH (FUNCTION = 'partial(2,"XXX-XXXX",2)'),
    CreditCard VARCHAR(20) MASKED WITH (FUNCTION = 'partial(0,"XXXX-XXXX-XXXX-",4)'),
    Salary DECIMAL(18,2) MASKED WITH (FUNCTION = 'default()')
);

-- Add mask to existing column
ALTER TABLE Customers
ALTER COLUMN Email ADD MASKED WITH (FUNCTION = 'email()');

-- Grant unmask permission
GRANT UNMASK ON Customers TO HRManager;

-- Remove mask
ALTER TABLE Customers
ALTER COLUMN Email DROP MASKED;
```

### Transparent Data Encryption (TDE)

```sql
-- Create database master key
CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'Str0ngM@sterKey!';

-- Create certificate
CREATE CERTIFICATE TDE_Cert WITH SUBJECT = 'TDE Certificate';

-- Create database encryption key
CREATE DATABASE ENCRYPTION KEY
WITH ALGORITHM = AES_256
ENCRYPTION BY SERVER CERTIFICATE TDE_Cert;

-- Enable TDE
ALTER DATABASE MyDB SET ENCRYPTION ON;

-- View encryption status
SELECT 
    db_name(database_id) AS DatabaseName,
    encryption_state,
    encryption_state_desc,
    key_algorithm,
    key_length
FROM sys.dm_database_encryption_keys;

-- Backup certificate
BACKUP CERTIFICATE TDE_Cert TO FILE = 'C:\Backup\TDE_Cert.cer'
WITH PRIVATE KEY (
    FILE = 'C:\Backup\TDE_Cert.pvk',
    ENCRYPTION BY PASSWORD = 'C3rtB@ckup!'
);
```

---

## 24. Chapter 22: Backup and Recovery

### Full Backups

```sql
-- Full backup to disk
BACKUP DATABASE MyDB
TO DISK = 'C:\Backup\MyDB_Full.bak'
WITH 
    FORMAT,
    INIT,
    NAME = 'MyDB-Full Backup',
    SKIP,
    NOREWIND,
    NOUNLOAD,
    STATS = 10,
    COMPRESSION;

-- Backup with checksum
BACKUP DATABASE MyDB
TO DISK = 'C:\Backup\MyDB_Full_Checksum.bak'
WITH 
    CHECKSUM,
    CONTINUE_AFTER_ERROR;

-- Split backup across multiple files
BACKUP DATABASE MyDB
TO 
    DISK = 'C:\Backup\MyDB_1.bak',
    DISK = 'D:\Backup\MyDB_2.bak',
    DISK = 'E:\Backup\MyDB_3.bak'
WITH FORMAT, COMPRESSION;

-- Backup to URL (Azure)
BACKUP DATABASE MyDB
TO URL = 'https://mystorage.blob.core.windows.net/backups/MyDB.bak'
WITH CREDENTIAL = 'AzureCredential';
```

### Differential and Transaction Log Backups

```sql
-- Differential backup
BACKUP DATABASE MyDB
TO DISK = 'C:\Backup\MyDB_Diff.bak'
WITH 
    DIFFERENTIAL,
    INIT,
    COMPRESSION;

-- Transaction log backup
BACKUP LOG MyDB
TO DISK = 'C:\Backup\MyDB_Log.trn'
WITH 
    INIT,
    COMPRESSION;

-- Log backup with NORECOVERY (for restoring to another server)
BACKUP LOG MyDB
TO DISK = 'C:\Backup\MyDB_Log_Norecovery.trn'
WITH NORECOVERY;

-- Tail-log backup (before restore)
BACKUP LOG MyDB
TO DISK = 'C:\Backup\MyDB_TailLog.trn'
WITH 
    NORECOVERY,
    NO_TRUNCATE;
```

### Restore Operations

```sql
-- Full restore
RESTORE DATABASE MyDB
FROM DISK = 'C:\Backup\MyDB_Full.bak'
WITH 
    MOVE 'MyDB_Data' TO 'C:\Data\MyDB.mdf',
    MOVE 'MyDB_Log' TO 'D:\Log\MyDB.ldf',
    REPLACE,
    RECOVERY,
    STATS = 10;

-- Restore with NORECOVERY (for additional restores)
RESTORE DATABASE MyDB
FROM DISK = 'C:\Backup\MyDB_Full.bak'
WITH 
    NORECOVERY,
    REPLACE;

-- Restore differential
RESTORE DATABASE MyDB
FROM DISK = 'C:\Backup\MyDB_Diff.bak'
WITH 
    RECOVERY;

-- Restore transaction logs
RESTORE LOG MyDB
FROM DISK = 'C:\Backup\MyDB_Log_1.trn'
WITH NORECOVERY;

RESTORE LOG MyDB
FROM DISK = 'C:\Backup\MyDB_Log_2.trn'
WITH RECOVERY;

-- Point-in-time restore
RESTORE LOG MyDB
FROM DISK = 'C:\Backup\MyDB_Log.trn'
WITH 
    STOPAT = '2024-06-15 14:30:00',
    RECOVERY;

-- Restore files/filegroups
RESTORE DATABASE MyDB FILE = 'MyDB_Data'
FROM DISK = 'C:\Backup\MyDB_Full.bak'
WITH 
    NORECOVERY,
    REPLACE;

-- View backup history
SELECT 
    database_name,
    backup_start_date,
    backup_finish_date,
    type,
    backup_size/1024/1024 AS SizeMB,
    recovery_model
FROM msdb.dbo.backupset
ORDER BY backup_start_date DESC;
```

---

## 25. Chapter 23: High Availability and Disaster Recovery

### Always On Availability Groups

```sql
-- Create availability group
CREATE AVAILABILITY GROUP AG_MyApp
FOR DATABASE MyDB
REPLICA ON 
    'Server1' WITH (
        ENDPOINT_URL = 'TCP://Server1:5022',
        AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,
        FAILOVER_MODE = AUTOMATIC,
        SEEDING_MODE = AUTOMATIC
    ),
    'Server2' WITH (
        ENDPOINT_URL = 'TCP://Server2:5022',
        AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,
        FAILOVER_MODE = AUTOMATIC,
        SEEDING_MODE = AUTOMATIC
    ),
    'Server3' WITH (
        ENDPOINT_URL = 'TCP://Server3:5022',
        AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,
        FAILOVER_MODE = MANUAL,
        SEEDING_MODE = AUTOMATIC
    );

-- Add database to availability group
ALTER AVAILABILITY GROUP AG_MyApp ADD DATABASE MyDB;

-- Join replica to availability group
ALTER AVAILABILITY GROUP AG_MyApp JOIN;

-- Fail over
ALTER AVAILABILITY GROUP AG_MyApp FAILOVER;

-- View availability group status
SELECT 
    ag.name AS AGName,
    ar.replica_server_name,
    drs.synchronization_state_desc,
    drs.synchronization_health_desc
FROM sys.availability_groups ag
JOIN sys.availability_replicas ar ON ag.group_id = ar.group_id
JOIN sys.dm_hadr_database_replica_states drs ON ar.replica_id = drs.replica_id;
```

### Database Mirroring (Legacy)

```sql
-- Configure mirroring on principal
ALTER DATABASE MyDB SET PARTNER = 'TCP://MirrorServer:5022';

-- Configure mirroring on mirror
ALTER DATABASE MyDB SET PARTNER = 'TCP://PrincipalServer:5022';

-- Add witness
ALTER DATABASE MyDB SET WITNESS = 'TCP://WitnessServer:5022';

-- Fail over
ALTER DATABASE MyDB SET PARTNER FAILOVER;

-- View mirroring status
SELECT 
    database_id,
    mirroring_state_desc,
    mirroring_role_desc,
    mirroring_partner_name
FROM sys.database_mirroring;
```

### Log Shipping

```sql
-- Enable log shipping on primary
EXEC msdb.dbo.sp_add_log_shipping_primary_database 
    @database = N'MyDB',
    @backup_directory = N'C:\LogShip\Backup',
    @backup_share = N'\\PrimaryServer\LogShip\Backup',
    @backup_retention_period = 4320,
    @backup_threshold = 60,
    @threshold_alert_enabled = 1,
    @history_retention_period = 1440;

-- Configure secondary
EXEC msdb.dbo.sp_add_log_shipping_secondary_primary 
    @primary_server = N'PrimaryServer',
    @primary_database = N'MyDB',
    @backup_source_directory = N'\\PrimaryServer\LogShip\Backup',
    @backup_destination_directory = N'C:\LogShip\Copied',
    @copy_retention_period = 4320;

EXEC msdb.dbo.sp_add_log_shipping_secondary_database 
    @secondary_database = N'MyDB',
    @primary_server = N'PrimaryServer',
    @primary_database = N'MyDB',
    @restore_delay = 0,
    @restore_mode = 1,
    @disconnect_users = 1;
```

---

## 26. Chapter 24: SQL Server Administration

### Server Configuration

```sql
-- View server properties
SELECT 
    SERVERPROPERTY('ServerName') AS ServerName,
    SERVERPROPERTY('Edition') AS Edition,
    SERVERPROPERTY('ProductVersion') AS Version,
    SERVERPROPERTY('ProductLevel') AS ProductLevel,
    SERVERPROPERTY('EngineEdition') AS EngineEdition;

-- Configure server settings
EXEC sp_configure 'show advanced options', 1;
RECONFIGURE;

EXEC sp_configure 'max server memory', 8192;  -- MB
RECONFIGURE;

EXEC sp_configure 'max degree of parallelism', 4;
RECONFIGURE;

EXEC sp_configure 'cost threshold for parallelism', 50;
RECONFIGURE;

EXEC sp_configure 'backup compression default', 1;
RECONFIGURE;
```

### Database Maintenance

```sql
-- Check database integrity
DBCC CHECKDB('MyDB');

-- Check with repair options
DBCC CHECKDB('MyDB', REPAIR_REBUILD);
DBCC CHECKDB('MyDB', REPAIR_ALLOW_DATA_LOSS);  -- Use with caution!

-- Update usage
DBCC UPDATEUSAGE('MyDB');

-- Show database size
EXEC sp_spaceused;

-- Shrink database (use carefully)
DBCC SHRINKDATABASE('MyDB', 10);  -- Leave 10% free space

-- Shrink file
DBCC SHRINKFILE('MyDB_Data', 1000);  -- Target size in MB
```

### SQL Server Agent Jobs

```sql
-- Create job
EXEC msdb.dbo.sp_add_job 
    @job_name = N'Daily Backup',
    @enabled = 1,
    @description = N'Performs daily full backup';

-- Add job step
EXEC msdb.dbo.sp_add_jobstep 
    @job_name = N'Daily Backup',
    @step_name = N'Backup Database',
    @subsystem = N'TSQL',
    @command = N'BACKUP DATABASE MyDB TO DISK = ''C:\Backup\MyDB.bak'' WITH COMPRESSION',
    @database_name = N'master';

-- Create schedule
EXEC msdb.dbo.sp_add_jobschedule 
    @job_name = N'Daily Backup',
    @name = N'Daily at 2 AM',
    @freq_type = 4,  -- Daily
    @freq_interval = 1,
    @active_start_time = 20000;  -- 2:00 AM

-- Add job to server
EXEC msdb.dbo.sp_add_jobserver 
    @job_name = N'Daily Backup';

-- Start job
EXEC msdb.dbo.sp_start_job N'Daily Backup';

-- View job history
SELECT 
    j.name AS JobName,
    h.run_date,
    h.run_time,
    h.run_duration,
    CASE h.run_status 
        WHEN 0 THEN 'Failed'
        WHEN 1 THEN 'Succeeded'
        WHEN 2 THEN 'Retry'
        WHEN 3 THEN 'Canceled'
    END AS Status
FROM msdb.dbo.sysjobs j
JOIN msdb.dbo.sysjobhistory h ON j.job_id = h.job_id
WHERE h.step_id = 0  -- Job outcome
ORDER BY h.run_date DESC, h.run_time DESC;
```

### Monitoring and Alerts

```sql
-- View current activity
SELECT 
    session_id,
    status,
    command,
    wait_type,
    wait_time,
    blocking_session_id,
    cpu_time,
    logical_reads
FROM sys.dm_exec_requests;

-- View waiting tasks
SELECT 
    wt.session_id,
    wt.wait_type,
    wt.wait_duration_ms,
    wt.blocking_session_id,
    t.text AS SQLText
FROM sys.dm_os_waiting_tasks wt
OUTER APPLY sys.dm_exec_sql_text(wt.sql_handle) t;

-- Configure alerts
EXEC msdb.dbo.sp_add_alert 
    @name = N'High CPU Usage',
    @message_id = 0,
    @severity = 0,
    @enabled = 1,
    @delay_between_responses = 0,
    @notification_message = N'CPU usage is high',
    @category_name = N'[Uncategorized]',
    @performance_condition = N'SQLServer:CPU|CPU Usage|>|80';

-- Add notification
EXEC msdb.dbo.sp_add_notification 
    @alert_name = N'High CPU Usage',
    @operator_name = N'DBA Team',
    @notification_method = 1;  -- Email
```

---

## 27. Chapter 25: Advanced T-SQL Features

### JSON Support

```sql
-- Query JSON data
DECLARE @json NVARCHAR(MAX) = 
'{"name": "John", "age": 30, "skills": ["SQL", "C#", "Azure"]}';

SELECT 
    JSON_VALUE(@json, '$.name') AS Name,
    JSON_VALUE(@json, '$.age') AS Age,
    JSON_QUERY(@json, '$.skills') AS Skills;

-- Parse JSON into rows
SELECT *
FROM OPENJSON(@json, '$.skills')
WITH (Skill NVARCHAR(100) '$');

-- Convert query results to JSON
SELECT ProductID, ProductName, UnitPrice
FROM Products
FOR JSON AUTO;

SELECT ProductID, ProductName, UnitPrice
FROM Products
FOR JSON PATH, ROOT('Products');

-- Modify JSON
SET @json = JSON_MODIFY(@json, '$.age', 31);
SET @json = JSON_MODIFY(@json, '$.city', 'New York');
SET @json = JSON_MODIFY(@json, 'append $.skills', 'Python');
```

### STRING_SPLIT and STRING_AGG

```sql
-- Split string into rows
SELECT value
FROM STRING_SPLIT('Apple,Banana,Orange', ',');

-- With ordinality
SELECT value, ordinal
FROM STRING_SPLIT('Apple,Banana,Orange', ',', 1);

-- Aggregate strings
SELECT 
    CategoryID,
    STRING_AGG(ProductName, ', ') AS ProductList
FROM Products
GROUP BY CategoryID;

-- With ordering
SELECT 
    CategoryID,
    STRING_AGG(ProductName, ', ') WITHIN GROUP (ORDER BY ProductName) AS ProductList
FROM Products
GROUP BY CategoryID;
```

### Temporal Tables

```sql
-- Create temporal table
CREATE TABLE Products_History (
    ProductID INT,
    ProductName VARCHAR(100),
    UnitPrice DECIMAL(18,2),
    SysStartTime DATETIME2 GENERATED ALWAYS AS ROW START NOT NULL,
    SysEndTime DATETIME2 GENERATED ALWAYS AS ROW END NOT NULL,
    PERIOD FOR SYSTEM_TIME (SysStartTime, SysEndTime)
)
WITH (SYSTEM_VERSIONING = ON);

-- Query history
SELECT * FROM Products_History
FOR SYSTEM_TIME BETWEEN '2024-01-01' AND '2024-12-31';

SELECT * FROM Products_History
FOR SYSTEM_TIME AS OF '2024-06-15 10:00:00';

SELECT * FROM Products_History
FOR SYSTEM_TIME FROM '2024-01-01' TO '2024-12-31';

-- All history including current
SELECT * FROM Products_History
FOR SYSTEM_TIME ALL;
```

### Graph Tables

```sql
-- Create node table
CREATE TABLE Person (
    ID INT PRIMARY KEY,
    Name VARCHAR(100)
) AS NODE;

-- Create edge table
CREATE TABLE FriendOf (
    RelationshipType VARCHAR(50)
) AS EDGE;

-- Insert nodes
INSERT INTO Person (ID, Name) VALUES (1, 'Alice'), (2, 'Bob'), (3, 'Carol');

-- Insert edges
INSERT INTO FriendOf ($from_id, $to_id, RelationshipType)
VALUES (
    (SELECT $node_id FROM Person WHERE ID = 1),
    (SELECT $node_id FROM Person WHERE ID = 2),
    'Friend'
);

-- Query graph
SELECT 
    p1.Name AS Person,
    p2.Name AS Friend,
    f.RelationshipType
FROM Person p1
JOIN FriendOf f ON p1.$node_id = f.$from_id
JOIN Person p2 ON p2.$node_id = f.$to_id;
```

---

## 28. Best Practices

### Database Design

Design databases with proper normalization (typically 3NF) but denormalize when performance requires it. Choose appropriate data types—use the smallest type that can hold your data. Use IDENTITY or sequences for surrogate keys. Create meaningful constraints to enforce data integrity. Document your design decisions and maintain an up-to-date data dictionary.

### Query Development

Write set-based operations instead of cursors when possible. Use appropriate JOIN types and understand their implications. Filter data early in queries to reduce intermediate result sets. Use EXISTS instead of IN for subqueries when checking existence. Avoid SELECT * in production code—specify needed columns explicitly. Parameterize queries to enable plan reuse and prevent SQL injection.

### Index Strategy

Create indexes based on query patterns, not blindly on all columns. Monitor index usage and remove unused indexes. Include all columns needed by a query in covering indexes. Consider filtered indexes for sparse data. Maintain indexes regularly—reorganize for 5-30% fragmentation, rebuild for >30%. Update statistics after significant data changes.

### Security

Follow the principle of least privilege—grant only necessary permissions. Use Windows authentication when possible. Encrypt sensitive data at rest and in transit. Implement row-level security for multi-tenant applications. Audit security-related events and review logs regularly. Keep SQL Server patched with the latest security updates.

### Performance

Monitor wait statistics to identify bottlenecks. Use Query Store to track query performance over time. Test query changes with realistic data volumes. Consider partitioning large tables. Use appropriate isolation levels—don't use higher isolation than necessary. Plan for capacity growth and monitor resource usage trends.

---

## 29. Common Mistakes

### Using SELECT * in Production

SELECT * returns all columns, including those you don't need. This increases network traffic, memory usage, and breaks code when columns are added or removed. Always specify the columns you need.

### Not Using Parameterized Queries

String concatenation for queries leads to SQL injection vulnerabilities and prevents plan caching. Use stored procedures or parameterized queries for all user input.

### Ignoring Index Fragmentation

Fragmented indexes cause more I/O and slower queries. Implement regular index maintenance as part of your database maintenance plan.

### Over-Indexing

Too many indexes slow down INSERT, UPDATE, and DELETE operations. Each index adds overhead. Create indexes based on actual query patterns and monitor their usage.

### Not Having a Backup Strategy

Data loss is catastrophic. Implement a comprehensive backup strategy including full, differential, and transaction log backups. Test your restore process regularly.

### Using Cursors When Set-Based Operations Work

Cursors are often unnecessary and perform poorly. Learn to think in sets and use set-based operations whenever possible.

### Not Understanding Isolation Levels

Default isolation levels can cause blocking or inconsistent reads. Choose the appropriate isolation level for your workload requirements.

### Neglecting Statistics

Outdated statistics lead to poor query plans. Ensure auto-update statistics is enabled and update statistics manually after large data loads.

---

## 30. Quick Reference Cheatsheet

### Data Types

| Category | Types | Storage |
|----------|-------|---------|
| Integer | TINYINT, SMALLINT, INT, BIGINT | 1-8 bytes |
| Decimal | DECIMAL(p,s), NUMERIC(p,s) | 5-17 bytes |
| Approximate | FLOAT, REAL | 4-8 bytes |
| Money | MONEY, SMALLMONEY | 4-8 bytes |
| Character | CHAR, VARCHAR, VARCHAR(MAX) | 1 byte/char |
| Unicode | NCHAR, NVARCHAR, NVARCHAR(MAX) | 2 bytes/char |
| Date | DATE | 3 bytes |
| Time | TIME | 3-5 bytes |
| DateTime | DATETIME, DATETIME2, SMALLDATETIME | 4-8 bytes |
| Binary | BINARY, VARBINARY, VARBINARY(MAX) | Actual size |
| Other | BIT, UNIQUEIDENTIFIER, XML, JSON | Varies |

### Constraints

```sql
PRIMARY KEY (Column)                    -- Unique identifier
FOREIGN KEY (Column) REFERENCES Table   -- Referential integrity
UNIQUE (Column)                         -- No duplicates
CHECK (Condition)                       -- Domain integrity
DEFAULT (Value)                         -- Default value
NOT NULL                                -- Required field
```

### JOIN Types

```sql
INNER JOIN      -- Matching rows only
LEFT JOIN       -- All left, matching right
RIGHT JOIN      -- All right, matching left
FULL JOIN       -- All rows from both
CROSS JOIN      -- Cartesian product
```

### Aggregate Functions

```sql
COUNT(*), COUNT(Column), COUNT(DISTINCT Column)
SUM(Column), AVG(Column)
MIN(Column), MAX(Column)
STDEV(Column), VAR(Column)
STRING_AGG(Column, Separator)
```

### Window Functions

```sql
ROW_NUMBER() OVER (ORDER BY Column)
RANK(), DENSE_RANK() OVER (ORDER BY Column)
NTILE(n) OVER (ORDER BY Column)
LAG(Column, n), LEAD(Column, n) OVER (ORDER BY Column)
SUM(Column) OVER (PARTITION BY Column ORDER BY Column)
```

### Common DBCC Commands

```sql
DBCC CHECKDB('DatabaseName')           -- Check integrity
DBCC CHECKTABLE('TableName')           -- Check table
DBCC SHRINKDATABASE('DatabaseName')    -- Shrink database
DBCC SHRINKFILE('FileName')            -- Shrink file
DBCC FREEPROCCACHE                     -- Clear plan cache
DBCC DROPCLEANBUFFERS                  -- Clear buffer cache
DBCC SQLPERF(LOGSPACE)                 -- Log space usage
```

### System Stored Procedures

```sql
sp_help 'ObjectName'                   -- Object information
sp_helptext 'ProcedureName'            -- View procedure code
sp_configure                           -- Server configuration
sp_who                                 -- Active processes
sp_lock                                -- Lock information
sp_spaceused                           -- Space usage
sp_updatestats                         -- Update all statistics
```

---

## 31. Additional Resources

### Official Documentation
- [SQL Server Documentation](https://docs.microsoft.com/en-us/sql/sql-server/)
- [T-SQL Reference](https://docs.microsoft.com/en-us/sql/t-sql/language-reference)
- [SQL Server Blog](https://cloudblogs.microsoft.com/sqlserver/)

### Learning Resources
- [Microsoft Learn SQL Server](https://learn.microsoft.com/en-us/training/browse/?terms=SQL%20Server)
- [SQL Server Central](https://www.sqlservercentral.com/)
- [Brent Ozar Unlimited](https://www.brentozar.com/)

### Tools
- SQL Server Management Studio (SSMS)
- Azure Data Studio
- SQL Server Data Tools (SSDT)
- sp_whoisactive (community stored procedure)
- First Responder Kit (Brent Ozar)

### Community
- SQL Server subreddit (r/SQLServer)
- Stack Overflow (sql-server tag)
- SQL Server PASS Community

### Recommended Books
- "Microsoft SQL Server 2019: A Beginner's Guide" by Dusan Petkovic
- "T-SQL Fundamentals" by Itzik Ben-Gan
- "SQL Server 2019 Administration Inside Out" by William Assaf
- "Pro SQL Server Internals" by Dmitri Korotkevitch

---

## Summary

Congratulations on completing this comprehensive guide to SQL Server! You've journeyed from understanding SQL Server architecture through advanced administration and performance tuning. This knowledge provides a solid foundation for working with SQL Server in development, database administration, and data engineering roles.

SQL Server is a vast and continually evolving platform. Continue practicing by building projects, experimenting with features, and solving real problems. Stay current with new releases and features. Join the SQL Server community to learn from and contribute to the collective knowledge.

The skills you've developed—relational database design, T-SQL programming, performance optimization, and administration—transfer to other database platforms and data technologies. Whether you're building applications, managing databases, or analyzing data, SQL Server expertise remains valuable in today's data-driven world.

Happy querying!

---

*This guide was created to help developers and database professionals master SQL Server from basics to advanced level. For the most up-to-date information, always refer to the official Microsoft documentation.*
