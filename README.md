# Azure_Kubelogin_tool_installer.ado
Use this template for installing kubelogin and adding it to the PATH of your agent in Azure Devops Pipeline.

## Parameters:

The pipeline requires the following parameters to be defined:


| Name  | Displayname | type | Default | Values | Opional/Required | Comments |
| ------------- | ------------- | :-------------: | :-------------: | ------------- | :-------------: | ------------- |
| kubeloginVersion | kubelogin version | string | latest | | Required | The version of kubelogin to use, for example 0.0.30, or latest to use the latest version |


--------------------------------------------------------------------------------------------------------------------------------------------------

These parameters provide multiple use case options for the template, enable/disable flags for the utilization of different templates as per the requirements.


## Use Cases

You can directly call a particular template as per the requirement. for example: 

  ```yaml
  # azure-pipeline.yml
  resources:
  repositories:
    - repository: Template
      type: github
      name: your_username/Azure_Kubelogin_tool_installer.ado
      ref: <respective branch name>
      endpoint: 'githubServiceConnectioNname'

  steps:
  # passing the parameters
  - template: Azure_Kubelogin_tool_installer.yml
    parameters:
      kubeloginVersion: '${{parameters.kubeloginVersion}}'   
  ```
  
Make sure to adjust the repository name, branch name, and parameter values according to your project's requirements.
