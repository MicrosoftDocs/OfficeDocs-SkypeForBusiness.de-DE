---
title: Verschieben von Konferenzverzeichnissen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vor der Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis im vorversionspool ausführen.
ms.openlocfilehash: b7526d8c3c032bf8b1f9052dce7da7e8a87b66b5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372805"
---
# <a name="move-conference-directories"></a>Verschieben von Konferenzverzeichnissen

Vor der Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis im vorversionspool ausführen.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>So verschieben Sie ein Konferenzverzeichnis zu Skype für Business Server 2019

1. Öffnen Sie die Skype für Business Server-Verwaltungsshell.
    
2. Um die Identität der konferenzverzeichnisse in Ihrer Organisation zu beziehen, führen Sie den folgenden Befehl aus:
    
   ```
   Get-CsConferenceDirectory
   ```

    Mit dem vorstehende Befehl werden alle konferenzverzeichnisse in Ihrer Organisation zurückgegeben. Aus diesem Grund möchten Sie möglicherweise das Begrenzen der Ergebnisse an den Pool wird außer Betrieb genommen. Wenn Sie den Pool mit den vollqualifizierten Domänennamen (FQDN) Namen pool01.contoso.net außer Betrieb nehmen, verwenden Sie diesen Befehl zum Begrenzen der zurückgegebenen Daten auf konferenzverzeichnisse aus diesem Pool fest:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Dieser Befehl gibt nur die konferenzverzeichnisse zurück, bei denen die ServiceID-Eigenschaft den FQDN pool01.contoso.net enthält.
    
3. Wenn konferenzverzeichnisse verschieben möchten, führen Sie den folgenden Befehl für jedes Konferenzverzeichnis im Pool:
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Beispielsweise wenn Konferenzverzeichnis 3 verschieben möchten, verwenden Sie diesen Befehl: Angeben einer Skype für Business Server 2019 Pool als die TargetPool an:
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Wenn Sie alle konferenzverzeichnisse in einem Pool verschieben möchten, verwenden Sie einen Befehl ähnlich der folgenden:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Laden Sie [Microsoft legacy deinstallieren und Entfernen von Serverrollen](https://go.microsoft.com/fwlink/p/?linkId=246227) umfassende, schrittweisen Anweisungen Außerbetriebnahme von alten Pools.
  
Beim Verschieben von konferenzverzeichnissen, können Sie den folgenden Fehler auftreten:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Dieser Fehler tritt normalerweise auf, wenn die Skype für Business Server-Verwaltungsshell eine aktualisierte Menge von Active Directory-Berechtigungen für die Durchführung eine Aufgabe erforderlich sind. Um das Problem zu beheben, schließen Sie die aktuelle Instanz der-Verwaltungsshell, und klicken Sie dann öffnen Sie eine neue Instanz der Shell, und führen Sie den Befehl aus, um das Konferenzverzeichnis verschieben erneut aus.
  

