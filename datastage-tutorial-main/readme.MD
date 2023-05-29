
# DataStage NextGen Tutorial

## April 2023 Edition

## Introduction

IBM DataStage in Cloud Pak for Data is a modernized data integration solution to collect and
deliver trusted data anywhere, at any scale and complexity, on and across multi cloud and hybrid cloud
environments.

IBM DataStage is the data integration tool of choice for customers across industries.

- Design once, run anywhere paradigm allows you to bring data integration to where your data
resides.
- A best in breed parallel engine processes substantial data volumes and built in workload
balancing supports multi cloud scalability and elasticity.
- The DataStage service uses Cloud Pak for Data platform connections and integration points, with
services like Data Virtualization, to simplify the process of connecting to and accessing your
data.

With a fully cloud-native architecture, DataStage can dynamically scale workloads and optimize for large
data sets.

You can import your existing legacy parallel jobs into DataStage through the use of ISX files, use the
DataStage canvas to create, edit, and test flows, and run jobs that are generated from the flows.

In this hands-on-lab you will use DataStage to design transformation flows. The following is a
high-level view of the process steps in this lab:

1. Create a project. Projects are where you can collaborate with others to work with data.
2. Add data to the project. Data can be added from a local project file or from local or remote data
    sources through a connection.
3. Create a DataStage flow.
4. Perform steps using operations to transform the data.
5. Create and run the DataStage job to transform the data..
6. Review the results


## [Pre-requisites and Preparations](prerequisites-preparations.MD)

You must have a DataStage environment, meet all pre-requisites and complete all pre-configurations to start the exercise.


## [Exercise 1. Create a DataStage Flow (DB2 to DB2)](exercise01.MD)

In this exercise, you will:

- Create a project.
- Provision the DataStage service.
- Add a data set to your project from the Gallery.
- Create a DataStage flow.
- Run your Datastage flow and view your asset.

It takes approximately 20 minutes to complete.


## [Exercise 2. DataStage Runtime Environments](exercise02.MD)

***This section is for information only. You don't have any task except review the information.***

You can designate an environment definition as a runtime setting from the DataStage designer canvas or from the Jobs tab.


## [Exercise 3: Create a DataStage flow (file to file)](exercise03.MD)

In this exercise, you will:

- Upload the source files to the project.
- Clone the previous transformation flow.
- Change the source and target for the cloned transformation flow.
- Run your Datastage flow and view your asset in the project and Cloud Object Storage.

This tutorial will approximately 20 minutes to complete.


## [Exercise 4: Parameters and Parameter Sets](exercise04.MD)

Create a DataStage flow using user parameters, parameter sets, and environment variables in your jobs to specify information that your job requires at run time.

In this tutorial, you use paramters and parameter sets instead of hard coding configuration.

- Use parameters
    - Clone the previous transformation flow (file to file)
    - Change the source and target for the cloned transformation flow with parameters
    - Run your DataStage flow and verify your asset in the project and Cloud Object Storage
- Use parameter sets
    - Clone the previous transformation flow (DB2 to DB2)
    - Change the source and target for the cloned transformation flow with parameter sets
    - Run your DataStage flow and verify your asset in the project


## [Exercise 5: Reusable Subflows](exercise05.MD)

You can create a DataStage flow and make part of the flow as a subflow. Reuse the subflow in another flow to simply the development of the new flow.

In this tutorial, you will:

- Create a new subflow
    - Clone the previous transformation flow (file to file)
    - Make the filter stage and sort stage as a local subflow
    - Run your DataStage flow and verify your asset in the project and Cloud Object Storage
    - Create a subflow from the local subflow so it can be shared and reused by other flows
- Reuse a subflow in another flow
    - Clone the previous transformation flow (DB2 to DB2)
    - Reuse the shared subflow in this new flow
    - Run your DataStage flow and verify your asset in the project and DB2


## [Exercise 6: Import and Export DataStage Assets](exercise06.MD)

Use import and export functions to exchange DataStage assets between Classic DataStage and NextGen DataStage, and between NextGen DataStages.

In this exercise, you

- Migrate DataStage jobs from classic DataStage into NextGen DataStage by importing an `isx` file exported from Classic DataStage
- Downloading and importing a DataStage flow and its dependencies


## [Exercise 7: Watson Pipelines](exercise07.MD)

The Watson Pipelines editor provides a graphical interface for orchestrating an end-to-end flow of assets from creation through deployment. Assemble and configure a pipeline to create, train, deploy, and update DataStage flows.

To design a pipeline that you drag nodes onto the canvas, specify DataStage pipeline nodes and parameters, then run and monitor the pipeline.

In this exercise, you

- Run a pipeline that executes a DataStage job
- Develop and run a pipeline that executes a sequence of DataStage jobs


## Advanced Topics

### [Exercise 1(Advanced): Amazon S3 Connector](S3_exercise.md)

Use the Amazon S3 connector to connect to the Amazon Simple Storage Service (S3). In this exercise, you create flow to read data from Amazon S3 storage, transform data and write data back to S3 storage.


### [Exercise 2(Advanced): Snowflake Connector](Snowflake_Exercise.MD)

Use the Snowflake connector in DataStage® to transform data stored in Snowflake. In this exercise, you create jobs that read and write data in Snowflake.


### [Exercise 3(Advanced): HDFS Connector](hdfs_datastage_flow.md)

Use the Apache HDFS connector in DataStage® to transform data stored in Apache Hadoop Distributed File System. In this exercise, you create jobs that read and write data in HDFS.

### [Exercise 4(Advanced): Salesforce Connector](salesforce_datastage_flow.md)

Use the Salesforce connector to in DataStage® to transform data stored in Salesforce. In this exercise, you create flow to read data from Salesforce system, transform data and write data back to Snowflake system.

### [Exercise 5(Advanced): Migrate Legacy DataStage Flows](migrate_datastage_flows.md)

In this exercise, you migrate legacy DataStage flow(s) to DataStage in CP4D. It helps move your on-prem DataStage workflows to a true hyper-cloud environment. With this DataStage modernization, you can run the same DataStage workflows in any public cloud offered by any cloud provider, like IBM, AWS and etc, in your private cloud or on-prem. The same procedure can be used to move DataStage between projects in the same environment or different environment.


## Additional Topics

For experienced DataStage users, listed below are some advanced topics for your exploration.

- DataStage Flow Execution using API — DSaaS and CICD Pipeline
- DataStage command-line tools
- Migrating DataStage jobs
- Sharing DataStage artifacts with all IBM Cloud Object Storage containers
- Partitioning and collecting data


## Important Topics

- Multicloud Data Integration tutorial: Integrate data
- IBM DataStage - IBM Cloud Pak for Data as a Service Documentation
- DataStage NextGen Demo Videos
- DataStage - Data Integration Community Blog
- DataStage as-a-Service Preliminary Sizing Guidance
- DataStage and IS for Cloud Pak for Data - Sizing
- TechZone asset: DataStage DevOps with MettleCI
- Next Generation DataStage Job Review for current customers

