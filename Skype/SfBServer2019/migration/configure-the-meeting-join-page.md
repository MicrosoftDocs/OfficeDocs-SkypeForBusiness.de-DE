---
title: Konfigurieren der Seite für den Besprechungsbeitritt
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Benutzer klickt einen Link zur Besprechung in eine Besprechungsanfrage an der Besprechung teilnehmen Seite erkennt der Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird dieser Client wird geöffnet und der Besprechung teilnimmt. Wenn ein Client nicht installiert ist, wird standardmäßig geöffnet Web-App.
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238716"
---
# <a name="configure-the-meeting-join-page"></a>Konfigurieren der Seite für den Besprechungsbeitritt

Wenn ein Benutzer klickt einen Link zur Besprechung in eine Besprechungsanfrage an der Besprechung teilnehmen Seite erkennt der Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird dieser Client wird geöffnet und der Besprechung teilnimmt. Wenn ein Client nicht installiert ist, wird standardmäßig geöffnet Web-App.
  
Sie können das Verhalten der Teilnahme an einer Besprechung ändern Seite, wenn Sie Benutzer zur Teilnahme an Besprechungen zulassen möchten. Diese Konfigurationsoptionen in der Systemsteuerung entfernt wurden, aber Sie mithilfe des Cmdlets "cswebserviceconfiguration" konfigurieren.
  
**Parameter für den Besprechungsbeitritt Besprechungsbeitrittsseite**

|**CsWebServiceConfiguration-Parameter**|**Beschreibung**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Wenn auf True festgelegt, teilnehmen an einer Besprechung mithilfe einer anderen Clientanwendung als Lync Benutzer die Möglichkeit, an der Besprechung teilzunehmen gewährt werden. Der Standardwert lautet "False".  <br/> |
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


