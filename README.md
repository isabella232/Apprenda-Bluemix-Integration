# Bluemix Service Integration

The Apprenda Bluemix Service Integration allows developers to provision IBM Bluemix Services from within Apprenda. 

### Release Notes

#### v1.0
  * Initial Release
  * Provision any Bluemix service that returns a connection string

## Installation
1. Clone the repository.
2. Build the Apprenda Bluemix Add-On.
3. Package your Add-On by simply zipping up your AddOnManifest.xml, icon.png and compiled assemblies. 
4. Upload to your System Operations Center (SOC). -> http://docs.apprenda.com/current/addons

### Developer Parameters.

These are the properties that the developer will specify. The below table outlines the developer parameters that can be used to provision an instance of the addon. This version of the integration only supports developer parameters as it was intended to be used by consumers of the Apprenda Cloud Platform (public alpha) running on Bluemix. 

| Name (Alias) | Description | Example | 
| ------------ | ----------- | ------- |
| Bluemix Username | Your IBM Bluemix Username | user@gmail.com | 
| Bluemix Password | Your IBM Bluemix Password | password |
| Bluemix Service Name | The Bluemix Service name as defined within Bluemix itself. This can be found with a "Services" API call to Bluemix | "conversation" for Watson Conversation Service or "watson_vision_combined" for Watson Vision Service|
| Bluemix Space | Your IBM Bluemix Space | dev/qa/prod - however you divide up your Bluemix Spaces |
| Bluemix API URL | The Bluemix API Endpoint | http://api.ng.bluemix.net |
| Bluemix API Version | The Bluemix API Version | v2 |


### Programmatic way to get Bluemix Service Name

```cs
//Example C# API call for services
var client = new RestClient("https://api.ng.bluemix.net/v2/services");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "bearer YOURTOKENHERE");
IRestResponse response = client.Execute(request);
```