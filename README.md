
# LogWarp Windows Event Log Export Script

## Overview

This PowerShell script exports specified Windows event logs to CSV files. The exported event log types include Application, Security, Setup, System, and ForwardedEvents. 

The CSV files are saved to a specified output folder with filenames containing the event log type and timestamp.

## Usage

To use the script, update the following parameters:

- `$LogOutputDirectory` - Folder path to save the exported CSV files
- `$EventTypesToExport` - Array of event log types to export 

Then run the script in a PowerShell ( Administrator ) session using the below line.

```
 Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; .\export_log.ps1
```
By default, it will export the Application, Security, Setup, System, and ForwardedEvents logs.

## What it does

The script performs the following:

1. Captures start time for script execution timestamp

2. Sets output folder path for saving CSV files 

3. Defines array of event log types to export

4. Loops through each event log type
   - Builds filename with event log type and timestamp
   - Exports event log to a CSV file in the output folder

5. Calculates total script execution time

6. Prints messages showing file export status and times

The resulting CSV files contain the exported Windows event log data for each specified log type.

## Example Output

```
Creating CSV version of Windows event log of type Application.
Target CSV file path:
C:\data\Windows Event Log Export\2023-01-09T14-22-35Z - Windows Event Log - Application.csv
Finished creating CSV file.

Creating CSV version of Windows event log of type Security.  
Target CSV file path:
C:\data\Windows Event Log Export\2023-01-09T14-22-35Z - Windows Event Log - Security.csv
Finished creating CSV file.

...

Log export process execution time: 00:00:14.123456
```
