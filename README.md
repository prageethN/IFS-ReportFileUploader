# Report Definition Uploader

Report Definition Uploader is tool used to deploy both report schemas & report layouts to a IFS installation during the development phase. This tool is helpful when the developer requires to deploy developed reports to multiple environments.

## Features

 - Create report layout definitions
 - Upload report schema files
 - Upload report layout files

## Usage

1. Create a new folder called "tools" in the workspace and copy the "ReportFileUploader" folder
   path: /workspace/tools/ReportFileUploader

2. Modify the database connection information in /config/ConnectionInfo.json

```json
{
  "dbConnection": {
    "service": "<server>/<SID>",
    "user": "<db-user>",
    "password": "<password>"
  }
}
```
3. Define report schema information in ReportSchemas.json

```json
{
  "reportSchemas": [
    {
      "reportId": "<report id> Ex: SERVICE_REPAIR_LABEL_REP",
      "schemaPath": "<relative path to the .xsd file in the workspace>"
    }
  ]
}
```
4. Define report layout information in ReportLayouts.json file

```json
{
  "reportLayouts": [
    {
      "reportId": "<report ID>",
      "layoutName": "<layout name>",
      "layoutTitle": "<layout title>",
      "layoutFormat": "<layout format>",
      "layoutType": "<report type>",
      "layoutOrder":"<report order>",
      "layoutVersion": "<report version>",
      "layoutPath": "<relative path to the .rdl file in the workspace>",      
      "overwrite": "<allow installer to override or not>"
    } 
  ]
}
```
5. Run ReportDefinitionUploader-v1.0.bat

6. Check the log
   Log will display all the files that were uploaded. If there are any errors refer to the troubleshoot section

## Troubleshoot

Following is a list of reasons for common errors that could be encountered.

- Database connection issues - Double check database connection information
- Json files are invalid - Use a JSON file validator to validate the JSON files
- File paths are invalid - Check whether relative paths to report files are set properly.
- Refer to attached sample files in the \config\sample-files folder

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
