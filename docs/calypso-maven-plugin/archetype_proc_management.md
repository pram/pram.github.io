---
layout: docs
title: Process Management
prev_section: calypso-maven-plugin/archetype_project_deployment
next_section: calypso-maven-plugin/archetype_structure
permalink: /docs/calypso-maven-plugin/archetype_process_management/
documentation: true
project: cmp
---

##Calypso Process Status Check

To see the currently active Calypso processes run

{% highlight bash %}
$ mvn calypso:status
{% endhighlight %}
    

You should see output of the following form

{% highlight bash %}
+==========+======================================================================+==============================+==============================+
|   PID    |                              Class Name                              |   ENV (expected[/running])   |            Config            |
+==========+======================================================================+==============================+==============================+
| Inactive |              com.calypso.apps.startup.StartEventServer               |              -               |                              |
| Inactive |              com.calypso.apps.startup.StartAuthService               |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartDataServer               |              -               |                              |
| Inactive |            com.calypso.apps.startup.StartAccountingEngine            |              -               |                              |
| Inactive |             com.calypso.apps.startup.StartBalanceEngine              |              -               |                              |
| Inactive |          com.calypso.apps.startup.StartImportMessageEngine           |              -               |                              |
| Inactive |         com.calypso.apps.startup.StartIncomingMessageEngine          |              -               |                              |
| Inactive |            com.calypso.apps.startup.StartInventoryEngine             |              -               |                              |
| Inactive |              com.calypso.apps.startup.StartLimitEngine               |              -               |                              |
| Inactive |           com.calypso.apps.startup.StartLiquidationEngine            |              -               |                              |
| Inactive |         com.calypso.apps.startup.StartMatchableBuilderEngine         |              -               |                              |
| Inactive |             com.calypso.apps.startup.StartMatchingEngine             |              -               |                              |
| Inactive |             com.calypso.apps.startup.StartMessageEngine              |              -               |                              |
| Inactive |              com.calypso.apps.startup.StartSenderEngine              |              -               |                              |
| Inactive |             com.calypso.apps.startup.StartTransferEngine             |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartTaskEngine               |              -               |                              |
| Inactive |            com.calypso.apps.startup.StartSchedulingEngine            |              -               |                              |
| Inactive |             com.calypso.apps.startup.StartMutationEngine             |              -               |                              |
| Inactive |             com.calypso.apps.startup.StartBillingEngine              |              -               |                              |
| Inactive |              com.calypso.apps.startup.StartDiaryEngine               |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartMainEntry                |              -               |                              |
| Inactive |                 com.calypso.apps.startup.StartAdmin                  |              -               |                              |
| Inactive |                com.calypso.apps.startup.StartUserEnv                 |              -               |                              |
| Inactive |           com.calypso.apps.startup.StartCalculationServer            |              -               |                              |
| Inactive |           com.calypso.apps.startup.StartPresentationServer           |              -               |                              |
| Inactive |             com.calypso.apps.startup.StartMktDataServer              |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartDispatcher               |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartCalculator               |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartExecuteSQL               |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartExecuteSQL               |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartExportData               |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartDBBrowser                |              -               |                              |
| Inactive |                com.calypso.apps.startup.StartAutoTest                |              -               |                              |
| Inactive |             com.calypso.apps.startup.StartBenchMarkTools             |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartAccessPerm               |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartSystemEnv                |              -               |                              |
| Inactive |                com.calypso.web.server.LocalWebServer                 |              -               |                              |
| Inactive |              com.calypso.apps.startup.StartQuoteServer               |              -               |                              |
| Inactive |          com.calypso.apps.startup.StartCustomerQuoteServer           |              -               |                              |
| Inactive |          com.calypso.apps.startup.StartFXManualQuoteServer           |              -               |                              |
| Inactive |            com.calypso.apps.startup.StartMarginCallEngine            |              -               |                              |
| Inactive |             com.calypso.apps.startup.StartPositionEngine             |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartCreEngine                |              -               |                              |
| Inactive |            com.calypso.apps.startup.StartCreSenderEngine             |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartISDAServer               |              -               |                              |
| Inactive |              com.calypso.apps.datamigration.MigratorGUI              |              -               |                              |
| Inactive |             com.calypso.apps.datamigration.MigratorCMGUI             |              -               |                              |
+==========+======================================================================+==============================+==============================+
{% endhighlight %}

<div class="note info">
  <h5>Process Catalog</h5>
  <p>The purpose of the Process Catalog is to allow you to define a discrete set of components that you can manage as a single unit. You can also define the relationship between the components in order to construct a dependency hierarchy</p>
</div>

To see the processes in the other process catalog included in the release either modify the `processCatalog` in the parent pom (currently set to `<processCatalog>FULL</processCatalog>`) or run `mvn calypso:status` setting the `processCatalog` variable to the name of the alternative catalog. For example to see the catalog of the other bundled catalog (named ALL) you would run the following command

{% highlight bash %}
mvn calypso:status -DprocessCatalog=ALL
{% endhighlight %}

The output of which looks like

{% highlight bash %}
+==========+======================================================================+==============================+==============================+
|   PID    |                              Class Name                              |   ENV (expected[/running])   |            Config            |
+==========+======================================================================+==============================+==============================+
| Inactive |              com.calypso.apps.startup.StartAuthService               |              -               |                              |
| Inactive |               com.calypso.apps.startup.StartDataServer               |              -               |                              |
| Inactive |              com.calypso.apps.startup.StartEventServer               |              -               |                              |
| Inactive |           com.calypso.apps.startup.StartCalculationServer            |              -               |           CS_AdHoc           |
| Inactive |           com.calypso.apps.startup.StartCalculationServer            |              -               |         CS_Official          |
| Inactive |           com.calypso.apps.startup.StartPresentationServer           |              -               |           PS_AdHoc           |
| Inactive |           com.calypso.apps.startup.StartPresentationServer           |              -               |         PS_Official          |
+==========+======================================================================+==============================+==============================+
{% endhighlight %}

You can define your own catalogs in the `config` module. They must be named `calypso-catalog-env.xml` or `calypso-catalog-xxx.xml` where xxx corresponds to the calypso.env.name property ie

{% highlight bash %}
mvn calypso:status -DprocessCatalog=env -Dcalypso.env.name=DEV1
{% endhighlight %}

##Displaying the Calypso Dependency Tree

In order to see the dependency graph defined in the process catalog you can run the `tree` goal. So running

{% highlight bash %}
mvn calypso:tree
{% endhighlight %}

Will show

{% highlight bash %}
-- EventServer'{ className='com.calypso.apps.startup.StartEventServer'}
   `-- AuthService'{ className='com.calypso.apps.startup.StartAuthService'}
      `-- DataServer'{ className='com.calypso.apps.startup.StartDataServer'}
         |-- AccountingEngine'{ className='com.calypso.apps.startup.StartAccountingEngine'}
         |-- BalanceEngine'{ className='com.calypso.apps.startup.StartBalanceEngine'}
         |-- ImportMessageEngine'{ className='com.calypso.apps.startup.StartImportMessageEngine'}
         |-- IncomingMessageEngine'{ className='com.calypso.apps.startup.StartIncomingMessageEngine'}
         |-- InventoryEngine'{ className='com.calypso.apps.startup.StartInventoryEngine'}
         |-- LimitEngine'{ className='com.calypso.apps.startup.StartLimitEngine'}
         |-- LiquidationEngine'{ className='com.calypso.apps.startup.StartLiquidationEngine'}
         |-- MatchableBuilderEngine'{ className='com.calypso.apps.startup.StartMatchableBuilderEngine'}
         |-- MatchingEngine'{ className='com.calypso.apps.startup.StartMatchingEngine'}
         |-- MessageEngine'{ className='com.calypso.apps.startup.StartMessageEngine'}
         |-- SenderEngine'{ className='com.calypso.apps.startup.StartSenderEngine'}
         |-- TransferEngine'{ className='com.calypso.apps.startup.StartTransferEngine'}
         |-- TaskEngine'{ className='com.calypso.apps.startup.StartTaskEngine'}
         |-- SchedulingEngine'{ className='com.calypso.apps.startup.StartSchedulingEngine'}
         |-- MutationEngine'{ className='com.calypso.apps.startup.StartMutationEngine'}
         |-- BillingEngine'{ className='com.calypso.apps.startup.StartBillingEngine'}
         |-- DiaryEngine'{ className='com.calypso.apps.startup.StartDiaryEngine'}
         |-- MainEntry'{ className='com.calypso.apps.startup.StartMainEntry'}
         |-- Admin'{ className='com.calypso.apps.startup.StartAdmin'}
         |-- UserEnv'{ className='com.calypso.apps.startup.StartUserEnv'}
         |-- CalculationServer'{ className='com.calypso.apps.startup.StartCalculationServer'}
         |-- PresentationServer'{ className='com.calypso.apps.startup.StartPresentationServer'}
         |-- MktDataServer'{ className='com.calypso.apps.startup.StartMktDataServer'}
         |-- Dispatcher'{ className='com.calypso.apps.startup.StartDispatcher'}
         |-- Calculator'{ className='com.calypso.apps.startup.StartCalculator'}
         |-- ExecuteSQL'{ className='com.calypso.apps.startup.StartExecuteSQL'}
         |-- MiddleTierExecuteSQL'{ className='com.calypso.apps.startup.StartExecuteSQL'}
         |-- ExportData'{ className='com.calypso.apps.startup.StartExportData'}
         |-- DBBrowser'{ className='com.calypso.apps.startup.StartDBBrowser'}
         |-- AutoTest'{ className='com.calypso.apps.startup.StartAutoTest'}
         |-- BenchMarkTools'{ className='com.calypso.apps.startup.StartBenchMarkTools'}
         |-- AccessPerm'{ className='com.calypso.apps.startup.StartAccessPerm'}
         |-- SystemEnv'{ className='com.calypso.apps.startup.StartSystemEnv'}
         |-- LocalWebServer'{ className='com.calypso.web.server.LocalWebServer'}
         |-- QuoteServer'{ className='com.calypso.apps.startup.StartQuoteServer'}
         |-- CustomerQuoteServer'{ className='com.calypso.apps.startup.StartCustomerQuoteServer'}
         |-- FXManualQuoteServer'{ className='com.calypso.apps.startup.StartFXManualQuoteServer'}
         |-- MarginCallEngine'{ className='com.calypso.apps.startup.StartMarginCallEngine'}
         |-- PositionEngine'{ className='com.calypso.apps.startup.StartPositionEngine'}
         |-- CreEngine'{ className='com.calypso.apps.startup.StartCreEngine'}
         |-- CreSenderEngine'{ className='com.calypso.apps.startup.StartCreSenderEngine'}
         |-- ISDAServer'{ className='com.calypso.apps.startup.StartISDAServer'}
         |-- CAM'{ className='com.calypso.apps.datamigration.MigratorGUI'}
         `-- ConfigurationManagement'{ className='com.calypso.apps.datamigration.MigratorCMGUI'}
{% endhighlight %}

Alternatively running for the other bundled catalog

{% highlight bash %}
mvn calypso:tree -DprocessCatalog=ALL
{% endhighlight %}

Will show

{% highlight bash %}
-- EventServer'{ className='com.calypso.apps.startup.StartEventServer'}
   `-- AuthService'{ className='com.calypso.apps.startup.StartAuthService'}
      `-- DataServer'{ className='com.calypso.apps.startup.StartDataServer'}
         |-- CalculationServer'{ className='com.calypso.apps.startup.StartCalculationServer', id='CS_AdHoc'}
         |   `-- PresentationServer'{ className='com.calypso.apps.startup.StartPresentationServer', id='PS_AdHoc'}
         `-- CalculationServer'{ className='com.calypso.apps.startup.StartCalculationServer', id='CS_Official'}
            `-- PresentationServer'{ className='com.calypso.apps.startup.StartPresentationServer', id='PS_Official'}
{% endhighlight %}

If you want to see the process catalog for the sample catalog included in the config module then type the following

{% highlight bash %}
mvn calypso:tree -DprocessCatalog=env -Dcalypso.env.name=DEV1
{% endhighlight %}

This will display

{% highlight bash %}
-- EventServer'{ className='com.calypso.apps.startup.StartEventServer'}
   `-- AuthService'{ className='com.calypso.apps.startup.StartAuthService'}
      `-- DataServer'{ className='com.calypso.apps.startup.StartDataServer'}
         |-- CalculationServer'{ className='com.calypso.apps.startup.StartCalculationServer', id='CS_AdHoc'}
         |   `-- PresentationServer'{ className='com.calypso.apps.startup.StartPresentationServer', id='PS_AdHoc'}
         |-- CalculationServer'{ className='com.calypso.apps.startup.StartCalculationServer', id='CS_Official'}
         |   `-- PresentationServer'{ className='com.calypso.apps.startup.StartPresentationServer', id='PS_Official'}
         |-- TransferEngine'{ className='com.calypso.apps.startup.StartTransferEngine'}
         `-- TaskEngine'{ className='com.calypso.apps.startup.StartTaskEngine'}
{% endhighlight %}            

To see output for a custom process catalog, then replace `DEV1` above with the desired catalog name. Ensure that the file `calypso-catalog-<env>.xml` exists on the classpath.


