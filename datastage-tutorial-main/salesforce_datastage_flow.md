# Salesforce (to Snowflake) DataStage Flow 

In this exercise, you are going to build a DataStage flow to read contents from Salesforce table `ACCOUNT`. You filter the contents as a sample data transformation. Then, you create a table in Snowflake system and store your transformed data there.


## 1. Pre-requisites

### 1.1 Explore Salesforce

1. Create a Salesforce Free Tier account from [this](https://www.salesforce.com/ap/form/signup/freetrial-sales/) link.

1. Login with your Username and Password

    ![img](doc/images/sf_ui01.png)

1. In the left pane, select `Schema Builder` under `Build` section.

1. Tables in the default schema `SFORCE` appears.

    ![img](doc/images/sf_ui02.png)

1. You'll use table `ACCOUNT` as the data source later in the exercise when you build DataStage flow.


### 1.2 Create a Watson Project

Create a new Watson Project or use an existing one.

1. Login to CP4D console.

1. Navigate to `Projects` --> `All projects` tab from the left pane. 

1. Click `New project +` to create new project. 

1. `Create an empty project`.

1. Enter a project name.

1. `Create`.


## 2. Create Salesforce Connection 

1. In the left of CP4D console, select `main menu` -> `Data` -> `Platform connections`.

    ![image](doc/images/sf_cp4d_menu01.png)

1. Enter a connection name. For example, `salesforce-platform-connection`.

1. Enter `login.salesforce.com` in the `Server name` field.

1. Select `Shared` option under `Credential setting`.

1. Select `Enter credential manually` option in the `Input method` field.

1. Enter username.

1. Enter password.

1. Append your `Salesforce Security Token` at the end of your password, if your account has not enabled two-steps authentication. Otherwise, you won't be able to connect to your Salesforce system.

    > Note, if you forgot your security token, you can request to reset your password. After your set your new password, you should receive an email with new security token.

    ![image](doc/images/sf_platform_connection01.png)

1. Now test the connection by clicking on `Test connection`. 

1. Click `Create` after the connection is successfully tested.


## 3. Build DataStage Flow

### 3.1 Add Data Source Connection

To connect to your data sources and/or targets, you have options to 
- create data connection in individual project
- create `Platform connection` and add/use it to individual project

The benefits of `Platform connection` allow you to create a connection once and use it in multiple projects. 

You created a `Platform connection` for your `Salesforce` system in the early session. In this exercise, a `Platform connection` for `Snowflake` is used as the target in the DataStage flow. If you don't have one, you need to build one by following the procedure in `Snowflake DataStage Flow`.

1. In the left of CP4D console, select `main menu` -> `Projects` -> `All projects`.

    ![image](doc/images/sf_cp4d_menu02.png)

1. Open your project.

1. Navigate to `Asset` tab of your project. 

1. Then click on `New asset +`.

    ![image](doc/images/new_asset.png)

1. Select `Connection`.

    ![image](doc/images/sf_connection01.png)

1. Go to `From platform connections` tab.

    ![image](doc/images/sf_connection02.png)

1. Select your `Salesforce` connection.

1. `Select`.

1. Repeat the steps to add your `Snowflake` connection.

1. Now, you have both `Salesforce` and `Snowflake` connections in your project.

    ![image](doc/images/sf_connection03.png)


### 3.2 Create DataStage Flow

1. In the left of CP4D console, select `main menu` -> `Projects` -> `All projects`.

    ![image](doc/images/sf_cp4d_menu02.png)

1. Open your project.

1. Navigate to `Asset` tab of your project. 

1. Then click on `New asset +`.

    ![image](doc/images/new_asset.png)

1. Scroll down to "Graphical Builders" in the left menu and choose `DataStage Flow` for the new asset.

    ![image](doc/images/new_datastage_asset.png)

1. Name your asset. For example, `my-salesforce-flow`.
    
    ![image](doc/images/name_datastage_asset.png)

1. Optionally enter a description.

1. `Create`.


### 3.3 Build DataStage Flow

In this exercise, you are going to read contents from Salesforce table `ACCOUNT`. You filter the contents as a sample data transformation. Then, you create a table in Snowflake system and store your transformed data there.

1. Open up the DataStage asset that you just created. You should have a blank canvas.

1. In the `filter` field of the left pane, enter `sales`. 

    ![image](doc/images/sf_sfconnector01.png)

1. Drag and drop `Salesforce.com` connector to the canvas on the right to add a connector for your input data. 

    ![image](doc/images/sf_canvas01.png)

1. Clear the `filter` and enter `snow` to narrow down the items in the pallett. 

1. Drag and drop `Snowflake` connector to the canvas on the right to add a connector for your output data. 

    ![image](doc/images/sf_canvas02.png)

1. Clear the `filter` and enter `filter` to narrow down the items in the pallett. 

1. Drag and drop `Filter` stage to the canvas on the right to add a connector for your output data. 

    ![image](doc/images/sf_canvas03.png)

1. Link up your pipeline. First, hover over `Salesforce_1` and drag the arrow that shows up to the right of it until it is linked with `Filter_1`. 

1. Repeat the connection between `Filter_1` and `Snowflake_1`.

1. Your overall flow should now look like this.

   ![image](doc/images/sf_canvas04.png)


### 3.4 Configure Salesforce Connector in DataStage Flow

Now it's time to edit the settings for each step of the flow. These settings make sure you are connected to the correct data instances, and allow you to customize transformations, choose columns to be passed along, name inputs/outputs, and even customize advanced processing settings when needed for ETL optimization. 

1. Double click on first `Salesforce` connector, i.e. `Salesforce.com_1`. Table `SFORCE.ACCOUNT` in `Salesforce` is used as the data source of the flow.

1. Select the `Stage` tab of the property window on the right.

    ![image](doc/images/sf_salesforce01.png)

1. Expand the `Properties` section.

1. Select your `Salesforce` connection under the `Connection` section.

    ![image](doc/images/sf_salesforce02.png)

1. Make sure `General` option is selected as the `Read method`.

1. Enter `SFORCE` in the `Schema name` field.

1. Enter `ACCOUNT` in the `Table name` field.

1. Navigate to the `Output` tab.

    ![image](doc/images/sf_salesforce03.png)

1. Click `Edit` link under `Columns` section to open the `Edit columns` window.

1. Click on `Import existing data definition` icon near top-right to import the columns.
    ![image](doc/images/sf_salesforce04.png)

    >Note, this is a very smallicon near top-right.

1. Select `Choose asset` -> `Connection` -> `Salesforce connection` -> `SFORCE` -> `ACCOUNT`.

    ![image](doc/images/sf_salesforce05.png)

1. `Next`.

    ![image](doc/images/sf_salesforce06.png)

1. `Import`.

1. Select all columns.

    ![image](doc/images/sf_salesforce07.png)

1. `Apply and return`.

    ![image](doc/images/sf_salesforce08.png)

1. Save.

1. To verify your configuration, right-click the `Salesforce` connector and select `Preview data`.

1. You should see data in table `SFORCE.ACCOUNT`.

1. `Close` after reviewing data.


### 3.5 Configure Filter Stage

1. Double click on `Filter_1` stage to open its properties window on the right.

1. In the `Stage` tab, under the `Properties` section, select `Edit` link.

   ![image](doc/images/s3_filter_ds_1.png)

1. Click the `pencil` icon under `Where clause` to enable its editing.

   ![image](doc/images/sf_salesforce09.png)

1. Optionally, you can edit `Output` or `Input` columns to remove unwanted columns. For example, you can delete the `address` column, and apply an alias of "email_address" to what was originally the `email` column.
    
1. `Apply and return`.

1. `Save`.


### 3.6 Configure Snowflake Connector in DataStage Flow

Now, you configure `Snowflake` connection. `Snowflake` acts as the target in this exercise. 

1. Double click `Snowflake_1` to open its properties window on the right.

   ![image](doc/images/sf_salesforce10.png)

1. In the `Stage` tab, expand the `Properties' section.

1. Under `Connection` section, select your `Snowflake` connection that you added earlier.

   ![image](doc/images/sf_salesforce11.png)

1. Navigate to `Input` tab.

   ![image](doc/images/sf_salesforce12.png)

1. Expand `Usage` section.

   ![image](doc/images/sf_salesforce13.png)

1. Unselect the `Use DataStage properties` checkbox.

1. Select `Merge` as the `Writing mode`.

1. Enter `PUBLIC` in the `Schema name` field.

1. Enter `ACCOUNT_SF` in the `Table name` field.

1. Select `Replace` for the `Table action`.

1. `Save`.


## 4. Execute DataStage Flow

1. Save the flow, by clicking on `Save` from the top bar.

1. Compile the DataStage job by clicking on `Compile`. 

    >Note: if any steps were missed, you can check the error log to find what went wrong and correct it. You can also choose `Run` without `Compile`.

   ![image](doc/images/sf_execute01.png)

1. After successful compilation, `Run` the DataStage job. 

    >Note, if some of the job setup is incomplete you will see a `Failure` message, and you can check the error log to correct the issue. 

1. If everything works as expected, you should receive a `Run successful` message.

   ![image](doc/images/sf_execute02.png)

1. The execution also displays the count of records retrieved from data source and records stored to the data target under the connection links of the flow.

1. To verify that the table `ACCOUNT_SF` was created successfully in `Snowflake` system and correct data was stored, right-click the `Snowflake_1` node and select `Preview data`.

1. You should have one data record for company `GenePoint`.

1. `Close` after reviewing data.



**End of Exercise**

