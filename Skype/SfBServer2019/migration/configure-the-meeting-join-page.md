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
localization_priority: Normal
description: Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, wird auf der Seite für den besprechungsbeitritt ermittelt, welcher Client auf dem Computer des Benutzers bereits installiert ist. Ist bereits ein Client installiert, wird dieser Client geöffnet und für den Besprechungsbeitritt verwendet. Wenn ein Client nicht installiert ist, wird die Webanwendung standardmäßig geöffnet.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754025"
---
# <a name="configure-the-meeting-join-page"></a>Konfigurieren der Seite für den Besprechungsbeitritt

Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, wird auf der Seite für den besprechungsbeitritt ermittelt, welcher Client auf dem Computer des Benutzers bereits installiert ist. Ist bereits ein Client installiert, wird dieser Client geöffnet und für den Besprechungsbeitritt verwendet. Wenn ein Client nicht installiert ist, wird die Webanwendung standardmäßig geöffnet.
  
Sie können das Verhalten der Seite für den besprechungsbeitritt ändern, wenn Sie zulassen möchten, dass Benutzer an Besprechungen teilnehmen können. Diese Konfigurationsoptionen wurden aus der Systemsteuerung entfernt, Sie werden jedoch mithilfe des CsWebServiceConfiguration-Cmdlets konfiguriert.
  
**CsWebServiceConfiguration-Parameter der Seite für den Besprechungsbeitritt**

|**CsWebServiceConfiguration-Parameter**|**Beschreibung**|
|:-----|:-----|
|"Showjoinusinglegacyclientlink"  <br/> |Bei Festlegung auf "true" wird Benutzern, die einer Besprechung mit einer anderen Clientanwendung als lync beitreten, die Möglichkeit gegeben, an der Besprechung teilzunehmen. Der Standardwert lautet "False".  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Bei Festlegung auf "true" werden alternative Optionen für die Teilnahme an einer Onlinekonferenz automatisch erweitert und Benutzern angezeigt. Bei Festlegung auf "false" (Standardwert) sind diese Optionen verfügbar, aber der Benutzer muss die Liste der Optionen für sich selbst anzeigen.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>So konfigurieren Sie die Seite für den besprechungsbeitritt mithilfe Skype for Business Server 2019-Verwaltungsshell

1. Starten Sie die Skype for Business Server 2019-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, dann auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Verwaltungskonsole**.
    
2. Führen Sie das folgende Cmdlet aus: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Dieses Cmdlet gibt die Konfigurationseinstellungen für den Webdienst zurück.
    
3. Führen Sie den folgenden Befehl aus, wobei die Parameter abhängig von Ihren Einstellungen auf true oder false festgelegt sind (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur [Skype for Business Server Verwaltungsshell](../../SfbServer/manage/management-shell.md) ):
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


