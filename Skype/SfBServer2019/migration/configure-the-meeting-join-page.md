---
title: Konfigurieren die Besprechung teilnehmen-Seite
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Benutzer klickt einen Link zur Besprechung in eine Besprechungsanfrage an der Besprechung teilnehmen Seite erkennt der Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird dieser Client wird geöffnet und der Besprechung teilnimmt. Wenn ein Client nicht installiert ist, wird standardmäßig geöffnet Web-App.
ms.openlocfilehash: 5e56641ce2e19c3194a92cb60bd7291380bc965a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027368"
---
# <a name="configure-the-meeting-join-page"></a>Konfigurieren die Besprechung teilnehmen-Seite

Wenn ein Benutzer klickt einen Link zur Besprechung in eine Besprechungsanfrage an der Besprechung teilnehmen Seite erkennt der Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird dieser Client wird geöffnet und der Besprechung teilnimmt. Wenn ein Client nicht installiert ist, wird standardmäßig geöffnet Web-App.
  
Sie können das Verhalten der Teilnahme an einer Besprechung ändern Seite, wenn Sie Benutzer zur Teilnahme an Besprechungen zulassen möchten. Diese Konfigurationsoptionen in der Systemsteuerung entfernt wurden, aber Sie mithilfe des Cmdlets "cswebserviceconfiguration" konfigurieren.
  
**Parameter für den Besprechungsbeitritt Besprechungsbeitrittsseite**

|**CsWebServiceConfiguration-Parameter**|**Beschreibung**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Wenn auf True festgelegt, teilnehmen an einer Besprechung mithilfe einer anderen Clientanwendung als Lync Benutzer die Möglichkeit, an der Besprechung teilzunehmen gewährt werden. Der Standardwert ist "False".  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Bei Festlegung auf true festgelegt ist, alternative Optionen für die Teilnahme an einer Konferenz online wird automatisch erweitert und anschließend den Benutzern angezeigt. Bei Festlegung auf False (Standardwert), werden diese Optionen zur Verfügung stehen, aber der Benutzer muss die Liste der Optionen für sich selbst anzuzeigen.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>So konfigurieren Sie die Besprechung teilnehmen Seite mithilfe von Skype für Business Server 2019-Verwaltungsshell

1. Starten Sie die Skype für Business Server 2019-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus: 
    
  ```
  Get-CsWebServiceConfiguration
  ```

    Dieses Cmdlet gibt die Konfigurationseinstellungen zurück.
    
3. Führen Sie den folgenden Befehl ein, mit der Parameter auf True oder False, abhängig von Ihrer Präferenz (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation [Skype für Business Server-Verwaltungsshell](../../SfbServer/manage/management-shell.md) ):
    
  ```
  Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
  ```


