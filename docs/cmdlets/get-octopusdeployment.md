﻿
### Summary

Gets information about Octopus deployments
### Parameters
| Name | DataType          | Description |
| ------------- | ----------- | ----------- |
| ReleaseVersion | String[] |  Release version to filter by. The cmdlet will only return deployments that belong to these releases     |
| LatestReleases |  |  Gets deployments by latest X releases     |
| ResourceOnly | Switch |  If set to TRUE the cmdlet will return the basic Octopur resource. If not set or set to FALSE, the cmdlet will return a human friendly Octoposh output object     |
| EnvironmentName | String[] |  Name of the Environment to filter by     |
| ProjectName | String[] |  Name of the Project to filter by     |
| Before |  |  Target communication style to filter by     |
| After |  |  Target communication style to filter by     |

### Syntax
``` powershell

Get-OctopusDeployment [-After <DateTimeOffset>] [-Before <DateTimeOffset>] [-EnvironmentName <string[]>] [-ProjectName <string[]>] [-ReleaseVersion <string[]>] [-ResourceOnly <SwitchParameter>] [<CommonParameters>]

Get-OctopusDeployment [-After <DateTimeOffset>] [-Before <DateTimeOffset>] [-EnvironmentName <string[]>] [-LatestReleases <int>] [-ProjectName <string[]>] [-ResourceOnly <SwitchParameter>] [<CommonParameters>]




``` 

### Examples 

**EXAMPLE 1**

Get all the deployments that were done on the Octopus Instance. You might wanna go grab a coffee after hitting [enter] on this one, its gonna take a while.

``` powershell 
 Get-OctopusDeployment
``` 

**EXAMPLE 2**

Get all the deployments that were done for the release 1.0.0 of the project "MyProject"

``` powershell 
 Get-OctopusDeployment -Project "MyProject" -ReleaseVersion 1.0.0
``` 

**EXAMPLE 3**

Get all the deployents that were done to the environments Staging and UAT on the project "MyService"

``` powershell 
 Get-OctopusDeployment -EnvironmentName "Staging","UAT" -ProjectName "MyService"
``` 

**EXAMPLE 4**

Get all the deployments that were done to the environment "Production" on the projects "MyProduct.webapp" and "MyProduct.service"

``` powershell 
 Get-OctopusDeployment -project "MyProduct.Webapp","MyProduct.service" -Environment "Production"
``` 

**EXAMPLE 5**

Gets all the deployments for the project "MyProduct.WebApp" for the environment "Production" between 2/20/2017 and 2/21/2017

``` powershell 
 PS Get-OctopusDeployment -project "MyProduct.Webapp" -Environment "Production" -After 2/20/2017 -Before 2/21/2017
``` 

