
DeviceProcessEvents
| where ProcessCommandLine contains "firewall add"
| where InitiatingProcessFileName != "Microsoft.Tri.Sensor.Updater.exe" // DFI sensor
| project-reorder
     Timestamp,
     DeviceName,
     AccountName,
     ProcessCommandLine,
     InitiatingProcessCommandLine


