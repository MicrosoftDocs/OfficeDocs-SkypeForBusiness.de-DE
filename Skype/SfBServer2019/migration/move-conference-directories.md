---
title: Verschieben von Konferenzverzeichnissen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vor der Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis in Ihrem Legacy Pool ausführen.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752497"
---
# <a name="move-conference-directories"></a>Verschieben von Konferenzverzeichnissen

Vor dem Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis in Ihrem Legacy Pool ausführen.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>So migrieren Sie ein Konferenzverzeichnis in Skype for Business Server 2019

1. Öffnen Sie die Skype for Business Server Management-Shell.
    
2. Um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu erhalten, führen Sie den folgenden Befehl aus:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    Der obige Befehl gibt alle Konferenzverzeichnisse in Ihrer Organisation zurück. Aus diesem Grund möchten Sie möglicherweise die Ergebnisse auf den Pool beschränken, der außer Betrieb genommen wird. Wenn Sie beispielsweise den Pool mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) pool01.contoso.net, verwenden Sie diesen Befehl, um die zurückgegebenen Daten auf Konferenzverzeichnisse aus diesem Pool zu begrenzen:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Dieser Befehl gibt nur die Konferenzverzeichnisse zurück, in denen die Service-Eigenschaft den FQDN pool01.contoso.NET enthält.
    
3. Um Konferenzverzeichnisse zu migrieren, führen Sie den folgenden Befehl für jedes Konferenzverzeichnis im Pool aus:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Um beispielsweise das Konferenzverzeichnis 3 zu verlagern, verwenden Sie diesen Befehl, um einen Skype for Business Server 2019-Pool als TargetPool anzugeben:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Wenn Sie alle Konferenzverzeichnisse in einem Pool verlagern möchten, verwenden Sie einen Befehl wie den folgenden:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Laden Sie das [Deinstallieren von Microsoft Legacy und das Entfernen von Server Rollen](https://go.microsoft.com/fwlink/p/?linkId=246227) für eine umfassende, schrittweise Anleitung zur Außerbetriebnahme von Legacy Pools herunter.
  
Beim Verschieben von Konferenz Verzeichnissen kann der folgende Fehler auftreten:
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Dieser Fehler tritt normalerweise auf, wenn die Skype for Business Server-Verwaltungsshell eine aktualisierte Gruppe von Active Directory Berechtigungen erfordert, um eine Aufgabe abzuschließen. Um das Problem zu beheben, schließen Sie die aktuelle Instanz der Verwaltungsshell, öffnen Sie dann eine neue Instanz der Shell, und führen Sie den Befehl erneut aus, um das Konferenzverzeichnis zu verlagern.
  

