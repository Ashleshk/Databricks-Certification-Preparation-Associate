# Fundamentals of the Databricks Lakehouse Platform (V2)

- What is a data lakehouse
    
    Data warehouse
    
    ![Untitled](Images/fundamentals/Untitled.png)
    
    Not designed with semi structured or unstructured data in mind
    
    Then comes **Data Lakes**
    
    ![Untitled](Images/fundamentals/Untitled%201.png)
    
    Issues with data lakes
    
    ![Untitled](Images/fundamentals/Untitled%202.png)
    
    Therefore it was required to keep both, stuck in silos
    
    ![Untitled](Images/fundamentals/Untitled%203.png)
    
    To fix these problems new data architecture emerged - data lakehouse - single flexible high performant system
    
    ![Untitled](Images/fundamentals/Untitled%204.png)
    
    provide benefits of both. Built on a data lake, single source of truth for ai and bi together2
    
    Key features of data lakehouse
    
    ![Untitled](Images/fundamentals/Untitled%205.png)
    
- What is databricks Lakehouse Platform
    
    Databricks inventor and pioneer of data lakehouse architecture
    
    ![Untitled](Images/fundamentals/Untitled%206.png)
    
    ![Untitled](Images/fundamentals/Untitled%207.png)
    
    ![Untitled](Images/fundamentals/Untitled%208.png)
    
- Data reliability and performance
    
    **Why Data reliability and performance is important**
    
    bad data in = bad data out
    
    data lake are good to hold large qualities of raw data, but lack reliability and quality features, and end up becoming data swamps
    
    don’t often offer performance as data warehouse
    
    **Issues with data lakes**
    
    Lack of ACID transactions
    
    Lack of schema enforcement
    
    lack of integration with data catalog
    
    data is in immutable format, therefore leads to ineffective partitioning, too many small files
    
    does not have transactional support, appending new data is actually adding new files
    
    small root file leads to query performance degredation
    
    **How Lakehouse solve these issues**
    
    Lakehouse platform solve these issues with the following technologies
    
    - Delta Lake
    - Photon
    
    ![Untitled](Images/fundamentals/Untitled%209.png)
    
    - Data lake runs on top of data lake and compatible with spark
    - Delta Lake uses delta tables which are based on Apache Parquet
    - Delta Lake works on Semi-Structured and Unstructured Data
    - Transaction Log - order of record of every transaction, accommodate multi user environment
        
        ![Untitled](Images/fundamentals/Untitled%2010.png)
        
    - Photon: Execution engine has same performance as data warehouse
    - Photon is the next generation query engine
        
        ![Untitled](Images/fundamentals/Untitled%2011.png)
        
        ![Untitled](Images/fundamentals/Untitled%2012.png)
        
- Unified governance and security
    
    ![Untitled](Images/fundamentals/Untitled%2013.png)
    
    - **Unity Catalog:**
        - Unified governance Solution, for data and models
        - Provides consistent model to discover, access and share data
        
        ![Untitled](Images/fundamentals/Untitled%2014.png)
        
        - Attribute based access control
        - Remove data silos
        - Unity catalog provides automated data lineage charts
        
        ![Untitled](Images/fundamentals/Untitled%2015.png)
        
    - **Delta Sharing-**
        - Open source solution to share live data from your lakehouse, to any computing platform securely
        - Recepients don’t even have to be on the same cloud or on data lakehouse platform
        - Open cross platform sharing tool
        - provides native integration with powerbi, tableau, pandas etc
        - data is shared live
        - centralized administration and governance
        
        ![Untitled](Images/fundamentals/Untitled%2016.png)
        
        - Unity Catalog natively supports delta sharing
            
            ![Untitled](Images/fundamentals/Untitled%2017.png)
            
        - Delta sharing uses rest protocol
        - Control Plane and Data Plane
        
        ![Untitled](Images/fundamentals/Untitled%2018.png)
        
        - Security 3 levels
        
        ![Untitled](Images/fundamentals/Untitled%2019.png)
        
        - User Identity and access
        
        ![Untitled](Images/fundamentals/Untitled%2020.png)
        
        - Data encrypted at rest or in motion
        
        ![Untitled](Images/fundamentals/Untitled%2021.png)
        
        - Compliance
            - SOC 2 Type II
            - ISO 27001
            - ISO 27017
            - ISO 27018
            - FEDRAMP High
            - HITRUST
            - HiPAA
            - PCI
            - GDPR, CCPA Ready
        
- Instant compute and serverless
    
    Classic data plane
    
    ![Untitled](Images/fundamentals/Untitled%2022.png)
    
    Issue with classic data plane - creating clusters
    
    - Cluster creation is complicated
    - Environment startup is slow
    - Clusters hosted in business cloud account, there are limitation on capacity
    - Clusters left running longer
    - Overprovisioning resource
    
    Databricks has released serverless compute option
    
    ![Untitled](Images/fundamentals/Untitled%2023.png)
    
    - Serverless computer runs on databricks coloud account, completely managed by databricks, total cost of ownership is reduced, 30 to 40 %
    
    ![Untitled](Images/fundamentals/Untitled%2024.png)
    
- Introduction to lakehouse data management terminology
    - Understand definitions of common lakehouse terms
        - Metastore
        - catalog
        - schema
        - table
        - view
        - function
    
    Dalta Lake: key architectural component provides a data storage format
    
    ![Untitled](Images/fundamentals/Untitled%2025.png)
    
    ![Untitled](Images/fundamentals/Untitled%2026.png)
    
    - How data management works in databricks
    
    ![Untitled](Images/fundamentals/Untitled%2027.png)
    
    - Metastore: top level logical container, construct that represents metadata,  helps with auditing capabilities
    - Catalog: top most container of data objects, metastore can have multiple catalog
    - Three level namespace to access tables in unity catalaog
    
    ![Untitled](Images/fundamentals/Untitled%2028.png)
    
    - Catalogs can contain as many schemas as desired
    - There are tables, views and functions
    - Table has two things - metadata, and actual data
    - Two types of tables: Managed, External. Metadata
    - Metastore: larger construct of organizing data and its metadata, reference for collection of metadata
- Supported workloads: Data Warehousing
    
    how it supports warehousing workloads using databricks sql
    
    benefits of warehousing with lakehouse platform 
    
    ![Untitled](Images/fundamentals/Untitled%2029.png)
    
    SQL Analytics: BI Tasks, SQL Transformation, querying, ingesting, building dashboards, delivering insights - uses databricks SQL and serverless SQL behind the scenes
    
    Key Benefits for using databricks lakehouse
    
    ![Untitled](Images/fundamentals/Untitled%2030.png)
    
- Supported workloads: Data Engineering
    
    Why data quality is so important
    
    How data lakehouse support data engineerint
    
    Delta Live Tables
    
    Data is a valuable assets to a business
    
    Challenges for de workloads
    
    - Complex ingestion method
    - Support de principals - CI CD, Agile, Version control
    - Third party orchestration system
    - pipeline and architecture performance tuning
    - Inconsistencies between warehouse and lakes providers
    
    Lakehouse Makes DE simple
    
    ![Untitled](Images/fundamentals/Untitled%2031.png)
    
    Lakehouse give de end to end sol for ingestion, transformation, processing, scheduling and delivery of data
    
    Key capabilieits
    
    - Easy data ingestion
    - Automated ETL pipelines
    - Data Quality checks
    - Batch and streaming
    - Automatic recovery
    - data pipeline observability
    - Simplified operation
    - Scheduling and orchestration
    
    ![Untitled](Images/fundamentals/Untitled%2032.png)
    
    Data Transfomration using medallion architecture - bronze silver gold
    
    DLT- Delta Live Tables
    
    ![Untitled](Images/fundamentals/Untitled%2033.png)
    
    ETL framework which is declarative approach to build reliable data pipelines, removing overhead from data engineers in terms of infrastructure management and tooling
    
    DLT autoscales
    
    DLT supports both python and sql
    
    Tailored to work with both streaming and batch workloads
    
    DLT supports both batch and streaming workflows
    
    **Databricks workflows**: fully managed orchestration service
    
    Allows you to orchestrate pipelines written in DLT or DBT
    
    you can use external orchestrator such as airflow 
    
    ![Untitled](Images/fundamentals/Untitled%2034.png)
    
    with databricks workflows
    
- Supported workloads: Data Streaming
    
    ![Untitled](Images/fundamentals/Untitled%2035.png)
    
    ![Untitled](Images/fundamentals/Untitled%2036.png)
    
    ![Untitled](Images/fundamentals/Untitled%2037.png)
    
    ![Untitled](Images/fundamentals/Untitled%2038.png)
    
- Supported workloads: Data Science and ML
    
    Challenges to DS workflows
    
    ![Untitled](Images/fundamentals/Untitled%2039.png)
    
    ![Untitled](Images/fundamentals/Untitled%2040.png)
    
    ![Untitled](Images/fundamentals/Untitled%2041.png)
    
    ![Untitled](Images/fundamentals/Untitled%2042.png)
    
    MLFlow and Automl