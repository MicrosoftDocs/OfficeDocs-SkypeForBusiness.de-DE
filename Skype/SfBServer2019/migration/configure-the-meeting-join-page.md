---
title: Konfigurieren der Seite für den Besprechungsbeitritt
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite für den Besprechungsbeitritt, welcher Client bereits auf dem Computer des Benutzers installiert ist. Ist bereits ein Client installiert, wird dieser Client geöffnet und für den Besprechungsbeitritt verwendet. Wenn kein Client installiert ist, wird standardmäßig die Web-App geöffnet.
ms.openlocfilehash: 8cba2a6ea0bc54eae6c30265c21d33d01ec951c0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617111"
---
# <a name="configure-the-meeting-join-page"></a>Konfigurieren der Seite für den Besprechungsbeitritt

Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite für den Besprechungsbeitritt, welcher Client bereits auf dem Computer des Benutzers installiert ist. Ist bereits ein Client installiert, wird dieser Client geöffnet und für den Besprechungsbeitritt verwendet. Wenn kein Client installiert ist, wird standardmäßig die Web-App geöffnet.
  
Sie können das Verhalten der Besprechungsteilnahmeseite ändern, wenn Sie Benutzern die Teilnahme an Besprechungen gestatten möchten. Diese Konfigurationsoptionen wurden aus der Systemsteuerung entfernt, aber Sie konfigurieren sie mithilfe des Cmdlets "CsWebServiceConfiguration".
  
**CsWebServiceConfiguration-Parameter der Seite für den Besprechungsbeitritt**

|**CsWebServiceConfiguration-Parameter**|**Beschreibung**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Bei Festlegung auf "True" erhalten Benutzer, die mithilfe einer anderen Clientanwendung als Lync an einer Besprechung teilnehmen, die Möglichkeit, an der Besprechung teilzunehmen. Der Standardwert lautet "False".  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Bei Festlegung auf "True" werden alternative Optionen für die Teilnahme an einer Onlinekonferenz automatisch erweitert und Benutzern angezeigt. Bei Festlegung auf "False" (Standardwert) sind diese Optionen verfügbar, aber der Benutzer muss die Liste der Optionen für sich selbst anzeigen.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>So konfigurieren Sie die Besprechungsteilnahmeseite mithilfe Skype for Business Server 2019-Verwaltungsshell

1. Starten Sie die Skype for Business Server 2019-Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Microsoft Skype for Business Server 2019"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Führen Sie das folgende Cmdlet aus: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Dieses Cmdlet gibt die Konfigurationseinstellungen für den Webdienst zurück.
    
3. Führen Sie den folgenden Befehl aus, wobei die Parameter je nach Ihren Wünschen auf "True" oder "False" festgelegt sind (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation [zur Skype for Business Server Verwaltungsshell):](../../SfbServer/manage/management-shell.md)
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


