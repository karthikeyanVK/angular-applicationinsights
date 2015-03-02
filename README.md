# angular-applicationinsights

An implementation of Microsoft Application Insights as an AngularJS module.

## Installation

##### Prerequisites

- A Microsoft Application Insights Instrumentation Key:
    - This can be obtained from https://portal.azure.com, and registering an Application Insights resource.
    - A tutorial on how to do this can be found @ http://azure.microsoft.com/en-us/documentation/articles/app-insights-web-track-usage/ . Depending on the version of the documentation the Instrumentation Key may also be referred to as 'iKey'. 

##### Via NPM

     npm i angular-applicationinsights

1. Run the above command from within your root project folder
2. Add a reference to the application insights script in your main app view, after the angularJS reference:
    
    ```HTML
    <!--Dependency on the Angular Local Storage Module-->
    <script src="/node_modules/angular-applicationinsights/node_modules/angular-local-storage/dist/angular-local-storage.min.js" />
    <!--Application Insights Module-->
    <script src="/node_modules/angular-applicationinsights/build/angular-applicationinsights.min.js" />
    ```
3. Add 'ApplicationInsightsModule' to the list of modules required by your application.
4. Configure the provider during your application module's config phase:
    
    ```Javascript
    myAmazingApp.config(function(applicationInsightsServiceProvider){
        applicationInsightsServiceProvider.configure('<PUT YOUR APPLICATION INSIGHTS KEY HERE', 'myAmazingApp');
    })
    ```
5. Start using your application. In the default configuration the Application Insights module will automatically track view changes and $log events, sending the telemetry to Microsoft Application Insights.
