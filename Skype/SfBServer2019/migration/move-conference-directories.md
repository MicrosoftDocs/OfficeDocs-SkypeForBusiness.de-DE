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
description: Vor der Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis in Ihrem Legacypool ausführen.
ms.openlocfilehash: 7e124a81b8aed561419e5965c930ad64988c122540df6660ae68006fe6af9a55
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313853"
---
# <a name="move-conference-directories"></a>Verschieben von Konferenzverzeichnissen

Vor der Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis in Ihrem Legacypool ausführen.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>So verschieben Sie ein Konferenzverzeichnis in Skype for Business Server 2019

1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie den folgenden Befehl aus, um die Identität der Konferenzverzeichnisse in Ihrer Organisation abzurufen:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    Der vorstehende Befehl gibt alle Konferenzverzeichnisse in Ihrer Organisation zurück. Aus diesem Grund sollten Sie die Ergebnisse auf den außer Betrieb genommenen Pool beschränken. Wenn Sie den Pool beispielsweise mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) pool01.contoso.net außer Betrieb nehmen, verwenden Sie diesen Befehl, um die zurückgegebenen Daten auf Konferenzverzeichnisse aus diesem Pool zu beschränken:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Dieser Befehl gibt nur die Konferenzverzeichnisse zurück, in denen die ServiceID-Eigenschaft den FQDN-pool01.contoso.net enthält.
    
3. Führen Sie den folgenden Befehl für jedes Konferenzverzeichnis im Pool aus, um Konferenzverzeichnisse zu verschieben:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Verwenden Sie zum Verschieben von Konferenzverzeichnis 3 beispielsweise diesen Befehl, um einen Skype for Business Server 2019-Pool als TargetPool anzugeben:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Wenn Sie alle Konferenzverzeichnisse in einem Pool verschieben möchten, verwenden Sie einen Befehl ähnlich dem folgenden:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Laden Sie die [Deinstallation der Vorgängerversion](https://go.microsoft.com/fwlink/p/?linkId=246227) von Microsoft und das Entfernen von Serverrollen herunter, um umfassende schrittweise Anweisungen zur Außerbetriebnahme von Legacypools zu erhalten.
  
Beim Verschieben von Konferenzverzeichnissen tritt möglicherweise der folgende Fehler auf:
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Dieser Fehler tritt in der Regel auf, wenn die Skype for Business Server-Verwaltungsshell einen aktualisierten Satz von Active Directory-Berechtigungen benötigt, um eine Aufgabe abzuschließen. Um das Problem zu beheben, schließen Sie die aktuelle Instanz der Verwaltungsshell, öffnen Sie dann eine neue Instanz der Shell, und führen Sie den Befehl erneut aus, um das Konferenzverzeichnis zu verschieben.
  

