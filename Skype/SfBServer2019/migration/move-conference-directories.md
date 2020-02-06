---
title: Verschieben von Konferenzverzeichnissen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vor der Außerbetriebnahme eines Pools müssen Sie die folgenden Schritte für jedes Konferenzverzeichnis in Ihrem Legacy Pool durchführen.
ms.openlocfilehash: bdcb816a91f6bc4a4372141595e46ba2369618a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813283"
---
# <a name="move-conference-directories"></a>Verschieben von Konferenzverzeichnissen

Bevor Sie einen Pool außer Betrieb nehmen, müssen Sie für jedes Konferenzverzeichnis in Ihrem Legacy Pool die folgenden Schritte ausführen.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>So verschieben Sie ein Konferenzverzeichnis in Skype for Business Server 2019

1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie den folgenden Befehl aus, um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu ermitteln:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    Der vorhergehende Befehl gibt alle Konferenzverzeichnisse in Ihrer Organisation zurück. Aus diesem Grund sollten Sie die Ergebnisse auf den Pool beschränken, der außer Betrieb genommen wird. Wenn Sie beispielsweise den Pool mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) pool01.contoso.net, verwenden Sie diesen Befehl, um die zurückgegebenen Daten auf Konferenzverzeichnisse aus diesem Pool zu begrenzen:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Dieser Befehl gibt nur die Konferenzverzeichnisse zurück, in denen die Service-Eigenschaft den FQDN-pool01.contoso.NET enthält.
    
3. Führen Sie zum Verschieben von Konferenz Verzeichnissen den folgenden Befehl für jedes Konferenzverzeichnis im Pool aus:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Wenn Sie beispielsweise das Konferenzverzeichnis 3 verschieben möchten, verwenden Sie diesen Befehl, und geben Sie einen Skype for Business Server 2019-Pool als TargetPool an:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Wenn Sie alle Konferenzverzeichnisse in einem Pool verschieben möchten, verwenden Sie einen Befehl wie den folgenden:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Laden Sie die [Deinstallation von Microsoft Legacy herunter, und entfernen Sie die Server Rollen](https://go.microsoft.com/fwlink/p/?linkId=246227) , um umfassende, schrittweise Anleitungen zur Außerbetriebnahme von Legacy Pools zu erhalten.
  
Beim Verschieben von Konferenz Verzeichnissen kann die folgende Fehlermeldung auftreten:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Dieser Fehler tritt in der Regel auf, wenn die Skype for Business Server-Verwaltungsshell eine aktualisierte Gruppe von Active Directory-Berechtigungen erfordert, um eine Aufgabe abzuschließen. Um das Problem zu beheben, schließen Sie die aktuelle Instanz der Verwaltungsshell, öffnen Sie dann eine neue Instanz der Shell, und führen Sie den Befehl erneut aus, um das Konferenzverzeichnis zu verschieben.
  

