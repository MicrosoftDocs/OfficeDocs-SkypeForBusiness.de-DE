---
title: Führen Sie Microsoft-Teams in einer virtuellen Umgebung
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/28/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jaym
description: Erfahren Sie, wie Microsoft-Teams in einer virtualisierten Umgebung ausführen.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a55dba95ee57738a708db1167288cc6bd210fc6
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858465"
---
<a name="run-microsoft-teams-in-a-virtual-environment"></a>Führen Sie Microsoft-Teams in einer virtuellen Umgebung
============================================

Dieser Artikel beschreibt die Anforderungen und Einschränkungen für die Verwendung von Teams in einer virtualisierten Umgebung.

Eine VDI-Umgebung (Virtual Desktop Infrastructure) wird in einigen Organisationen verwendet, in denen Sicherheit und Complianceprobleme besonders sensibel sind. Die Benutzer führen Sie ihre Arbeit auf einem virtuellen Desktop alle desktopanwendungen und Dateien mithilfe von Remote Desktop Services oder einer ähnlichen Remoteverbindung enthält. Da Teams auf dem virtuellen Desktop wurde nicht optimiert zugreifen oder die Geräte Audio- oder Videodatei auf dem Gerät des Benutzers lokale (ohne zusätzliche Software) verwenden, wird in einer VDI-Umgebung arbeiten in der Regel Probleme im Zusammenhang mit multimedia Szenarien wie der Aufruf von verfügen, Video-Anruf, Bildschirmfreigabe, Anwendungsfreigabe, gemeinsame dokumenterstellung und vieles mehr. 

> [!NOTE]
> Organisationen können auswählen, Teams vollständig in VDI ausgeführt (mit dem Web App oder dem Desktopclient), aber es wird empfohlen, die folgenden Richtlinien deaktiviert werden, sodass Benutzer eine schlechte Erfahrung in einer virtualisierten Umgebung nicht. Beachten Sie, dass es eine Weile dauern für diese Richtlinie Änderungen verteilen kann. Wenn Sie Änderungen für ein bestimmtes Konto sofort nicht angezeigt wird, versuchen Sie es erneut nach einigen Stunden. 

## <a name="calling"></a>Anrufe

Die Cmdlets *CsTeamsCallingPolicy* aktivieren Websiteadministratoren steuern, ob aufrufen und Optionen in privaten aufrufen und Gruppe Chats aktiviert sind, oder nicht. 


|Richtlinienname |Beschreibung  |Empfohlener Wert  |
|---------|---------|---------|
|AllowPrivateCalling   |Steuert, ob die app Aufrufen in der linken Rail des Teams-Clients verfügbar oder nicht ist. Außerdem steuert, ob Benutzer Anruf- und Videoanruf Optionen im privaten Chat angezeigt. |Legen Sie den **False** die aufrufenden app von der linken Rail entfernen und die Optionen für Anrufe und Videoanruf im privaten Chat zu entfernen. |

### <a name="powershell-instructions"></a>PowerShell-Anweisungen

1.  Starten Sie PowerShell als Administrator an.
2.  Verbinden Sie mit Skype Online Connector:<br>
\>> *-Legen Sie die Office 365-Benutzernamen und das Kennwort*<br>
\>> *$username = "Admin-e-Mail-Adresse"*<br>
\>> *$password = "Password" ConvertTo-SecureString - AsPlainText-Force*<br>
\>> *$LiveCred = neues Objekt - Typename System.Management.Automation.PSCredential - Argumentliste $username $password*<br><br>
\>> *# Verknüpfen und Skype Online*<br>
\>> *Import-Module SkypeOnlineConnector*<br>
\>> *$sfboSession = New CsOnlineSession-Anmeldeinformationen $LiveCred*<br>
\>> *Import-PSSession $sfboSession*<br>
3.  Liste der Anrufoptionen Richtlinie anzeigen:<br>
\>> *Get-CsTeamsCallingPolicy*
4.  Suchen Sie nach die Option vor dem programmierte, bei denen alle Richtlinien für die aufrufende deaktiviert sind:<br>
![Screenshot der Option von Besprechungen mit alle Besprechungsrichtlinien deaktiviert.](media/virtual-environment-image2.png)
5.  Alle Benutzer, die in einer virtualisierten Umgebung Teams verwenden sollen zuweisen Sie die Option "DisallowCalling" vor dem programmierte Richtlinie:<br>
\>> *GRANT-CsTeamsCallingPolicy - PolicyName DisallowCalling-Identity "Benutzer-e-Mail-Id"*

## <a name="meetings"></a>Besprechungen

Die *CsTeamsMeetingPolicy* -Cmdlets können Administratoren steuern, welche Art von Besprechungen, die Benutzer erstellen können oder die Features, die sie während einer Besprechung zugreifen können. Außerdem können die Behandlung von Besprechungen mit anonymen oder externe Benutzer bestimmen.

|Richtlinienname |Beschreibung  |Empfohlener Wert  |
|---------|---------|---------|
|AllowPrivateMeetingScheduling    |Bestimmt, ob ein Benutzer das Planen von privaten Besprechungen zulässig sind.         |Festlegen Sie diese Eigenschaft auf **False** Benutzer an der Freigabefunktion für private Besprechungstermine.         |
|AllowChannelMeetingScheduling     |Bestimmt, ob ein Benutzer das Planen von Besprechungen Kanal zulässig sind.         |Festlegen Sie diese Eigenschaft auf **False,** um zu verhindern, dass den Benutzer, Anwendungen oder Bildschirme Channel Besprechungen planen.         |
|AllowMeetNow     |Bestimmt, ob ein Benutzer zu erstellen, oder starten Sie Ad-hoc-Besprechungen zulässig sind.         |Festlegen Sie diese Eigenschaft auf **False,** um zu verhindern, dass den Benutzer, dass mehr Ad-hoc-Besprechungen gestartet.         |
|ScreenSharingMode     |Bestimmt den Modus, in dem ein Benutzer freigeben Bildschirm in Anrufe oder Besprechungen zulässig sind.         |Legen Sie den **deaktivierten** zu verhindern, dass den Benutzer ihre Bildschirme freigeben.         |
|AllowIPVideo     |Bestimmt, ob das Video in Besprechungen oder Anrufe des Benutzers aktiviert ist.         |Festlegen Sie diese Eigenschaft auf **False,** um zu verhindern, dass den Benutzer seine Videowiedergabe Freigabe.         |
|AllowAnonymousUsersToDialOut     |Bestimmt, ob anonyme Benutzer anwählen eine PSTN-Nummer zulässig sind.         |Festlegen Sie diese Eigenschaft auf **False,** um zu verhindern, dass anonyme Benutzer Telefonverbindung.         |
|AllowAnonymousUsersToStartMeeting     |Bestimmt, ob anonyme Benutzer eine Besprechung initiieren können.         |Festlegen Sie diese Eigenschaft auf **False** , wenn sie verhindern, dass Initiieren einer Besprechung.         |
|AllowOutlookAddIn     |Bestimmt, ob ein Benutzer in Outlook-Desktopclient Teams Besprechungen planen zu kann.         |Festlegen Sie diese Eigenschaft auf **False,** um zu verhindern, dass einen Benutzer planen Teams Besprechung im Outlook-Client.         |
|AllowParticipantGiveRequestControl     |Bestimmt, ob Teilnehmer übergeben der Steuerung Bildschirmfreigabe oder anfordern können.         |Legen Sie dies auf **False** , wenn den Benutzer dazu führte, verbieten Anfordern der Steuerung in einer Besprechung.         |
|AllowExternalParticipantGiveRequestControl     |Bestimmt, ob externe Teilnehmer übergeben der Steuerung Bildschirmfreigabe oder anfordern können.         |Legen Sie dies auf **False** , wenn einen externen Benutzer dazu führte, verbieten Anfordern der Steuerung in einer Besprechung.         |
|AllowPowerPointSharing     |Bestimmt, ob PowerPoint-Freigabe in einem Benutzer Besprechungen zulässig ist.         |Legen Sie dies auf **true fest,** um zu ermöglichen.<br>Festlegen Sie diese Eigenschaft auf **False,** um zu verhindern, dass Benutzer freigeben von PowerPoint-Dateien in einer Besprechung.         |
|AllowWhiteboard     |Bestimmt, ob Whiteboard in einem Benutzer Besprechungen zulässig ist.         |Festlegen Sie diese Eigenschaft auf **False** , Whiteboardanwendung in einer Besprechung zu untersagen.         |
|AllowTranscription     |Bestimmt, ob in Echtzeit und/oder nach dem meeting Beschriftungen und Abschriften an einen Benutzer Besprechungen zulässig sind.         |Festlegen Sie diese Eigenschaft auf **False** Umsetzung und Untertitel in einer Besprechung zu untersagen.         |

### <a name="powershell-instructions"></a>PowerShell-Anweisungen

1.  Starten Sie PowerShell als Administrator an.
2.  Verbinden Sie mit Skype Online Connector:<br>
\>> *-Legen Sie die Office 365-Benutzernamen und das Kennwort*<br>
\>> *$username = "Admin-e-Mail-Adresse"*<br>
\>> *$password = "Password" ConvertTo-SecureString - AsPlainText-Force*<br>
\>> *$LiveCred = neues Objekt - Typename System.Management.Automation.PSCredential - Argumentliste $username $password*<br><br>
\>> *# Verknüpfen und Skype Online*<br>
\>> *Import-Module SkypeOnlineConnector*<br>
\>> *$sfboSession = New CsOnlineSession-Anmeldeinformationen $LiveCred*<br>
\>> *Import-PSSession $sfboSession*
3.  Liste der Richtlinie Besprechungsoptionen anzeigen:<br>
\>> *Get-CsTeamsMeetingPolicy*
4.  Suchen Sie nach der Überprüfung vor dem programmierte Option, bei denen alle Besprechungsrichtlinien deaktiviert sind:<br>
![Screenshot des durch den Aufruf von Option alle Besprechungsrichtlinien deaktiviert.](media/virtual-environment-image1.png)
5.  Alle Benutzer, die in einer virtualisierten Umgebung Teams verwenden sollen zuweisen Sie die Option "AllOff" vor dem programmierte Richtlinie:<br>
\>> *GRANT-CsTeamsMeetingPolicy - PolicyName AllOff-Identity "Benutzer-e-Mail-Id"*

##<a name="known-limitations"></a>Bekannte Einschränkungen

Zusätzlich zu den Audio- und Videodaten Einschränkungen Previosly erwähnt stehen Ihnen einige zusätzlichen Einschränkungen, die Benutzern in virtualisierten Umgebungen mit der Vorderseite nach möglicherweise:

- **Teilnehmen an Besprechungen, die von anderen Benutzern erstellt.** Obwohl die oben genannten Richtlinien Benutzer beschränken von Besprechungen erstellen, werden sie weiterhin können zur Teilnahme an Besprechungen, die von anderen Benutzern gesendet. Innerhalb dieser treffen ihre Möglichkeit zur Freigabe von Video, verwenden Sie das WhiteBoard, und andere Features, hängt gibt an, ob der Administrator diese deaktiviert oder nicht.

- **Probleme im Zusammenhang mit zwischengespeicherten Inhalt.** Wenn die virtuelle Umgebung, die Teams ausgeführt wird nicht beibehalten wird (Daten werden bereinigt am Ende jeder Sitzung des Benutzers), Benutzer Umständen Leistungseinbußen aufgrund des Clients, um alle Inhalte erneut, unabhängig davon, ob erneut herunterzuladen, dass der Benutzer Zugriff auf den gleichen Inhalt in einer vorherigen Sitzung. Diese Leistungseinbußen kann mithilfe von servergespeicherten Cache Lösungen, beispielsweise von FSLogix bereitgestellte behoben werden.

Nachdem Teams zur Verwendung in virtuellen Desktop Umgebungen optimiert wurde, können Administratoren diese Richtlinien zurücksetzen und ermöglichen Benutzern die Verwendung von Teams, wie üblich.

         
        
        
        
        
        
        
        
        
        
        


