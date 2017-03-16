# Apprenda Bluemix Add-on

The Apprenda Bluemix Add-on allows developers to provision IBM Bluemix Services from within Apprenda. 

## Installation

1. Clone the repository.
2. Build the Apprenda Bluemix Add-On.
3. Package your Add-On by simply zipping up your AddOnManifest.xml, icon.png and compiled assemblies. 
4. Upload to your System Operations Center (SOC). -> http://docs.apprenda.com/current/addons


## Usage
1. In the SOC, go to "Configuration->Platform Addons->Edit"
2. Enter your IBM Bluemix credentials on the general page.       


![](/readme_images/bluemixaddon_general.png)


3. On the configuration tab, enter your Bluemix "space" that defines where your app will be deployed within Bluemix. 
4. Add the current "Bluemix API URL"(ie. "http://api.ng.bluemix.net") and the API Version (ie. "v2")  


![](/readme_images/bluemixaddon_config.png)


5. Next, go to the Apprenda Developer Portal and click Addons on the left side.
6. Click on the Bluemix Add-on and click the "+" symbol to provision an instance of the Add-on
    1. Enter in the "Instance Alias" (how Apprenda will identify your add-on instance)
    2. Enter the "Bluemix Service Name" as defined by Bluemix. This can be found by calling the "https://api.ng.bluemix.net/v2/services" endpoint for a complete list.
    3. Enter the "Service Name". This is the name of your service within Bluemix itself. 

```cs
//Example C# API call for services
var client = new RestClient("https://api.ng.bluemix.net/v2/services");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "bearer YOURTOKENHERE");
IRestResponse response = client.Execute(request);
```
    
7. If you'd like to check if your "Bluemix Service Name" is correct, go back to the Add-ons section in the SOC and click the test button (only enter the "Bluemix Service Name"). 


![](/readme_images/bluemixaddon_provision.png)
