# hytradboi : faster inner dev loop for stream processing

This [Azure Stream Analytics](https://docs.microsoft.com/en-us/azure/stream-analytics/stream-analytics-introduction) local project was used for the **faster inner dev loop for stream processing** talk of the April 2022 edition of [Have You Tried Rubbing A DataBase On It](https://www.hytradboi.com/).

This sample can be used cross platform, offline, without an Azure subscription.

## Prerequisites

- [VS Code](https://code.visualstudio.com/)
- a .NET **SDK** (if [the latest](https://dotnet.microsoft.com/en-us/download) doesn't cut it, [.NET Core 3.1 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/3.1) should do it).
- The [Azure Stream Analytics Tools](https://marketplace.visualstudio.com/items?itemName=ms-bigdatatools.vscode-asa) extension
- The [ASA CICD npm](https://www.npmjs.com/package/azure-streamanalytics-cicd) package
- Optionally : [PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows) (also now cross-platform)

## Local run

Open the `.asaql` file, right click in the script to `ASA: Start Local Run`.

**Documentation**:

- [Local run modes overview](https://docs.microsoft.com/en-us/azure/stream-analytics/visual-studio-code-local-run-all)
- [Step-by-step walkthrough](https://docs.microsoft.com/en-us/azure/stream-analytics/visual-studio-code-local-run)

## Test

Run a test via a terminal (below is PowerShell syntax):

```PowerShell
# Folder where the asaproj.json is located
$projectFullPath = ".\"

azure-streamanalytics-cicd test `
	-project ($projectPath + "asaproj.json") `
	-testConfigPath ($projectPath + "test\testConfig.json") `
	-outputPath ($projectPath + "test\testRuns\$(Get-Date -Format "yyyyMMddHHmmss")\")
```

**Documentation**:

- [Automate builds, tests, and deployments](https://docs.microsoft.com/en-us/azure/stream-analytics/cicd-tools?tabs=visual-studio-code)