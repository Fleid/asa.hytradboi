# Demo

## Testing

Creating a new test case:

```PowerShell
# to be run in the project folder
$projectPath = ".\"

azure-streamanalytics-cicd addtestcase -project ($projectPath + "asaproj.json") 
```

Running a test:

```PowerShell
$projectFullPath = ".\"

azure-streamanalytics-cicd test `
	-project ($projectPath + "asaproj.json") `
	-testConfigPath ($projectPath + "test\testConfig.json") `
	-outputPath ($projectPath + "test\testRuns\$(Get-Date -Format "yyyyMMddHHmmss")\")
```