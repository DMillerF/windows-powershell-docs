---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Grant-ADAuthenticationPolicySiloAccess
ms.reviewer:
ms.assetid: 5127BBE7-39FA-4169-B93C-E567032F6894
---

# Grant-ADAuthenticationPolicySiloAccess

## SYNOPSIS
Grants permission to join an authentication policy silo.

## SYNTAX

```
Grant-ADAuthenticationPolicySiloAccess [-WhatIf] [-Confirm] [-Account] <ADAccount> [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADAuthenticationPolicySilo> [-PassThru] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Grant-ADAuthenticationPolicySiloAccess** cmdlet grants permission to an account to join an authentication policy silo in Active Directory® Domain Services.

## EXAMPLES

### Example 1: Grant access to an authentication policy silo to a user account
```
PS C:\> Grant-ADAuthenticationPolicySiloAccess -Identity AuthenticationPolicySilo01 -Account User01
```

This command grants access to the authentication policy silo named AuthenticationPolicySilo01 to the user account named User01.

### Example 2: grant access to an authentication policy silo for filter matches
```
PS C:\> Get-ADComputer -Filter 'Name -like "NewComputer*"' | Grant-ADAuthenticationPolicySiloAccess -Identity AuthenticationPolicySilo01
```

This example first uses the **Get-ADComputer** cmdlet to get a list of computers that match the filter specified by the Filter parameter.
The output is then passed to the **Grant-ADAuthenticationPolicySiloAccess** cmdlet to grant access to the authentication policy silo named AuthenticationPolicySilo02.

## PARAMETERS

### -Account
Specifies the account to which to grant access to the authentication policy silo.
Specify the account in one of the following formats: 

- A distinguished name
- A GUID 
- A security identifier 
- A SAM account name

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

You can also use this parameter to specify a variable that contains user, computer, and service account objects.

```yaml
Type: ADAccount
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.
A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user account that has permission to perform the task.
The default is the current user.
Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the **Get-Credential** cmdlet.

By default, the cmdlet uses the credentials of the currently logged on user unless the cmdlet is run from an Active Directory Domain Services Windows PowerShell provider drive.
If you run the cmdlet in a provider drive, the account associated with the drive is the default.

If you specify credentials that do not have permission to perform the task, the cmdlet returns an error.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an **ADAuthenticationPolicySilo** object.
Specify the authentication policy silo object in one of the following formats: 

- A distinguished name
- A GUID
- A name

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

The cmdlet searches the default naming context or partition to find the object.
If the cmdlet finds two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAuthenticationPolicySilo
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Server
Specifies the Active Directory Domain Services instance to which to connect, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:  

Domain name values: 
- A Fully qualified domain name
- A NetBIOS name

Directory server values:  
- A Fully qualified directory server name
- A NetBIOS name
- A Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADAccount, Microsoft.ActiveDirectory.Management.ADAuthenticationPolicySilo

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Revoke-ADAuthenticationPolicySiloAccess](./Revoke-ADAuthenticationPolicySiloAccess.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)
