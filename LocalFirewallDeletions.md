
DeviceProcessEvents
| where ProcessCommandLine contains "firewall delete"
| where InitiatingProcessFileName != "Microsoft.Tri.Sensor.Updater.exe" // DFI sensor
| project-reorder
     Timestamp,
     DeviceName,
     AccountName,
     ProcessCommandLine,
     InitiatingProcessCommandLine

