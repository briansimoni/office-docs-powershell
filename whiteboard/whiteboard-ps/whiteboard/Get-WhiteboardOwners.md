---
external help file: Microsoft.Whiteboard.PowerShell.Custom.dll-Help.xml
Module Name: MicrosoftWhiteboard
online version: https://docs.microsoft.com/powershell/module/whiteboard/get-whiteboardowners
applicable: Microsoft Whiteboard
title: Get-WhiteboardOwners
schema: 2.0.0
author: shlevari
ms.author: shlevari
ms.reviewer:
---

# Get-WhiteboardOwners

## SYNOPSIS

Gets all the users in a tenant who own whiteboards in a specified geography.

## SYNTAX

### Get the whiteboard owners in a geography

```powershell
Get-WhiteboardOwners [-Geography] <String> [[-ContinuationToken] <String>] [-ForceAuthPrompt]
 [<CommonParameters>]
```

## DESCRIPTION

Gets all the users in a tenant who own whiteboards in a specified geography. Returns them as an object containing a list of user object, a tenantId and a continuation token. By calling repeatedly passing in the new continuation tokens, all the owners for a tenant can be gathered. The data returned is precalculated and therefore not realtime. Results are precalculated approximately every two weeks.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------

```powershell
PS C:\>Get-WhiteboardOwners -Geography Europe
```

Get the owners in the European geography.

### Output

```output
TenantId:                  tenantId
Geography:                 The geography queried for
Items:                     List of user ids
ContinuationToken:         continuation token
```

## PARAMETERS

### -Geography
Required. The geography to look for board owners in. Accepted values are: Europe, Australia, or Worldwide (all boards not in australia or europe).

```yaml
Type:                        string
Required:                    true
Position:                    1
Default value:               None
Applicable: Microsoft Whiteboard
```

### -ContinuationToken

Optional. The continuation token returned in a previous call.

```yaml
Type:                        string
Required:                    false
Position:                    named
Default value:               $null
Applicable: Microsoft Whiteboard
```

### -ForceAuthPrompt

Optional. Always prompt for auth. Use to ignore cached credentials.

```yaml
Type:                        SwitchParameter
Required:                    false
Position:                    named
Default value:               false
Accept pipeline input:       false
Accept wildcard characters:  false
Applicable: Microsoft Whiteboard
```

## NOTES

For details on user IDs, see the [overview page](../../docs-conceptual/overview.md).
