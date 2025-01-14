---
external help file: MsftSil_UalAccess.cdxml-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/softwareinventorylogging/get-silualaccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SilUalAccess
---

# Get-SilUalAccess

## SYNOPSIS
Displays the total number of unique client device requests and client user requests of the server from two days prior.
Windows Server 2012 R2 with KB3000850 applied.
For more information, see https://support.microsoft.com/kb/3000850.

## SYNTAX

```
Get-SilUalAccess [[-RoleGuid] <String[]>] [-RoleName <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SilUalAccess** cmdlet displays the total number of unique client device requests and the total number of client user requests for server roles or software products.
You can specify the **RoleName** parameter and **RoleGuid** parameter to filter the client device requests and client user requests of the server that the cmdlet displays.

The cmdlet returns totals of client requests for a server role or software product that uses the User Access Logging framework to capture client requests.
The cmdlet returns totals for one calendar day, two days prior to when the cmdlet is run.

## EXAMPLES

### Example 1: Display the total number of client requests of the server
```
PS C:\> Get-SilUalAccess


ProductName             : Windows Server 2012 R2 Datacenter
RoleGuid                : 10a9226f-50ee-49d8-a393-9a501d47ce04
RoleName                : File Server
SampleDate              : 3/30/2013 11:59:59 PM
UniqueDeviceAccessCount : 45
UniqueUserAccessCount   : 45


ProductName             : Windows Server 2012 R2 Datacenter
RoleGuid                : 7fb09bd3-7fe6-435e-8348-7d8aefb6cea3
RoleName                : Print and Document Services
SampleDate              : 3/30/2013 11:59:59 PM
UniqueDeviceAccessCount : 15
UniqueUserAccessCount   : 9
```

This command displays the total number of unique client requests of the server for the day, two days prior from when the cmdlet is run.

### Example 2: Display UAL data for a specified server role
```
PS C:\>Get-SilUalAccess -RoleName "Print and Document Services"
ProductName             : Windows Server 2012 R2 Datacenter
RoleGuid                : 7fb09bd3-7fe6-435e-8348-7d8aefb6cea3
RoleName                : Print and Document Services
SampleDate              : 7/24/2013
UniqueDeviceAccessCount : 0
UniqueUserAccessCount   : 0
```

This command displays a filtered list of UAL data for only the server role specified.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSession https://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSession https://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleGuid
Specifies an array of GUIDs of server roles or software products installed on the server.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoleName
Specifies an array of names of server roles or software products installed on the server.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/InventoryLogging/MsftSil_UalAccess
This cmdlet returns an object that encapsulates the unique role access information for a device or user.
That object includes the following properties: 

- **ProductName** (**System.String**)
- **RoleGuid** (**System.String**)
- **RoleName** (**System.String**)
- **SampleDate** (**System.DateTime**)
- **UniqueDeviceAccessCount** (**System.UInt32**)
- **UniqueUserAccessCount** (**System.UInt32**)

## NOTES

## RELATED LINKS

[Get-SilSoftware](./Get-SilSoftware.md)

[Get-SilComputer](./Get-SilComputer.md)

[Get-SilData](./Get-SilData.md)

[Get-SilLogging](./Get-SilLogging.md)

[Get-SilWindowsUpdate](./Get-SilWindowsUpdate.md)

