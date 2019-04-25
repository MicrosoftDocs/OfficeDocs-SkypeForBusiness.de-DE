---
title: Teams für Virtualized Desktop Infrastructure
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Erfahren Sie, wie Microsoft-Teams in einer virtualisierten Desktop Infrastructure (VDI)-Umgebung ausführen.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c351e0cefc5e4de4ff74a175af4dee064bf96f3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223424"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams für Virtualized Desktop Infrastructure

Dieser Artikel beschreibt die Anforderungen und Einschränkungen für die Verwendung von Microsoft-Teams in einer virtualisierten Umgebung.

## <a name="what-is-vdi"></a>Was ist VDI?

Virtual Desktop Infrastructure (VDI) ist Virtualisierungstechnologie, die ein desktop-Betriebssystem und Anwendungen auf einem zentralen Server in einem Rechenzentrum gehostet wird. Dies ermöglicht eine vollständig personalisierte desktop Umgebung für Benutzer mit eine zentrale Quelle vollständig gesicherte und kompatibel. 
 
Derzeit Teams in einer virtualisierten Umgebung mit Unterstützung für die Zusammenarbeit und Chat Funktionalität mit einem dedizierten persistent virtualisierte Computer (VM) verfügbar ist. Um eine optimale Umgebung sicherzustellen, befolgen Sie die Anweisungen in diesem Artikel. 

## <a name="teams-requirements"></a>Anforderungen für Teams

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>Festlegen von Richtlinien zum Deaktivieren von aufrufen und meeting-Funktionalität in Teams

Die Teams aufrufen und meeting Erfahrung ist nicht für eine VDI-Umgebung (bald verfügbar) optimiert. Es wird empfohlen, dass Festlegen von Richtlinien auf Benutzerebene, um zu deaktivieren aufrufen und meeting-Funktionalität in Teams.

Sie können dennoch wählen, Teams vollständig in VDI führen über die Teams-desktop-app oder Web app. Jedoch wird empfohlen, dass Sie die Richtlinien nicht beeinträchtigt die Benutzeroberfläche festgelegt.  

Es kann einige Zeit (ein paar Stunden) für die Richtlinie ändert weitergegeben dauern. Wenn Sie Änderungen für ein bestimmtes Konto sofort nicht angezeigt wird, versuchen Sie erneut in ein paar Stunden.

> [!NOTE]
> Beim Aufruf von Teams und Besprechungen für die Verwendung in virtuellen Umgebungen desktop optimiert sind, können Sie diese Richtlinien zurücksetzen und ermöglichen Benutzern die Verwendung von Teams, wie üblich. 

#### <a name="calling"></a>Anrufe

Verwenden Sie die **CSTeamsCallingPolicy** -Cmdlets zum Steuerelement, ob Benutzer dürfen verwenden aufrufen und Optionen in privaten aufrufen und Gruppe chats. Hier wird die Liste der Einstellungen für Gruppenrichtlinien und die empfohlenen Werte.

|Richtlinienname  |Beschreibung |Empfohlener Wert  |
|---------|---------|---------|
|AllowCalling    |Steuerelemente Interop Funktionen aufrufen. Aktivieren Sie dies ermöglicht Skype für Unternehmensbenutzer Angebot Anrufe mit Benutzern von Teams und umgekehrt werden.         |Um zu verhindern, dass Anrufe von Skype für Unternehmensbenutzer Zielseite in Teams auf False festgelegt.          |
|AllowPrivateCalling     | Steuert, ob die Aufruf von app in der app-Leiste auf der linken Seite des Teams-Clients verfügbar ist, und gibt an, ob Benutzer Anrufe und Optionen in privaten Chat aufrufen Video finden Sie unter         |So entfernen Sie die app Aufrufen aus der app-Leiste auf der linken Seite des Teams und Anrufoptionen Anruf- und Video im privaten Chat entfernen auf False festgelegt.          |

#### <a name="create-and-assign-a-calling-policy"></a>Erstellen und Zuweisen einer Richtlinie auf aufrufenden

1. Starten Sie eine Windows PowerShell-Sitzung als Administrator an.
2. Verbinden Sie mit der Online Skype-Connector.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Anzeigen einer Liste der Anrufoptionen Richtlinie anzuzeigen.

       Get-CsTeamsCallingPolicy
 
4. Suchen Sie nach die Option integrierte Richtlinie, bei denen alle Richtlinien für die aufrufende deaktiviert werden. Es sieht folgendermaßen aus.
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. Gelten Sie die Option DisallowCalling integrierten Richtlinie für alle Benutzer, die Teams in einer virtualisierten Umgebung verwendet werden soll.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Weitere Informationen zu Teams aufrufende Richtlinien finden Sie unter [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

#### <a name="meetings"></a>Besprechungen

Verwenden Sie die **CsTeamsMeetingPolicy** -Cmdlets um zu steuern, welche Art von Besprechungen, die Benutzer erstellen können, die Features, die sie während einer Besprechung zugreifen können und die Meeting-Features, die für anonyme als auch externe Benutzer verfügbar sind. Hier wird die Liste der Einstellungen für Gruppenrichtlinien und die empfohlenen Werte.

|Richtlinienname |Beschreibung|Empfohlene Wert                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | Bestimmt, ob ein Benutzer das Planen von privaten Besprechungen zulässig ist.| Benutzer an der Freigabefunktion für private Konferenzen planen auf False festgelegt.  |
|AllowChannelMeetingScheduling  | Bestimmt, ob ein Benutzer das Planen von Besprechungen DDE-Kanal zulässig ist. | Um zu verhindern, dass den Benutzer, Anwendungen oder Bildschirme Channel Besprechungen planen auf False festgelegt.                       |
|AllowMeetNow |Bestimmt, ob ein Benutzer berechtigt ist, erstellen oder Ad-hoc-Besprechungen starten.              |  Legen Sie dies auf false fest, um zu verhindern, dass den Benutzer, dass mehr Ad-hoc-Besprechungen gestartet.                     |
|ScreenSharingMode | Bestimmt den Modus, in dem ein Benutzer freigeben seines Bildschirms in Anrufe oder Besprechungen zulässig ist. | Um zu verhindern, dass den Benutzer ihre Bildschirme Freigabe auf deaktiviert festgelegt                          |
|AllowIPVideo |Bestimmt, ob das Video in Besprechungen oder Anrufe des Benutzers aktiviert ist.                  |    Auf False festgelegt, um zu verhindern, dass den Benutzer seine Videowiedergabe Freigabe                                         |
| AllowAnonymousUsersToDialOut | Bestimmt, ob anonyme Benutzer anwählen eine PSTN-Nummer zulässig sind. | Auf False festgelegt, um zu verhindern, dass anonyme Benutzer Telefonverbindung                                  |
| AllowAnonymousUsersToStartMeeting | Bestimmt, ob anonyme Benutzer eine Besprechung starten können.     |  Auf False festgelegt, um zu verhindern, dass Benutzer beginnen einer Besprechung                                            |
| AllowOutlookAddIn |Bestimmt, ob ein Benutzer Besprechungen im Outlook-Desktopclient Teams planen kann.| Auf False festgelegt, um zu verhindern, dass einen Benutzer Planen von Besprechungen im Outlook-Desktopclient Teams|
| AllowParticipantGiveRequestControl|Bestimmt, ob Teilnehmer übergeben der Steuerung Bildschirmfreigabe oder anfordern können.| Auf False festgelegt ist, an den Benutzer zu hindern vermitteln und Anfordern der Steuerung in einer Besprechung    |
| AllowExternalParticipantGiveRequestControl | Bestimmt, ob externe Teilnehmer übergeben der Steuerung Bildschirmfreigabe oder anfordern können.| Auf False festgelegt, um einen externen Benutzer dazu führte, zu untersagen Anfordern der Steuerung in einer Besprechung|
|AllowPowerPointSharing|Bestimmt, ob PowerPoint-Freigabe in einem Benutzer Besprechungen zulässig ist. |Auf False festgelegt, um zu verhindern, dass einen Benutzer freigeben von PowerPoint-Dateien in einer Besprechung  |
|AllowWhiteboard | Bestimmt, ob Whiteboard in einem Benutzer Besprechungen zulässig ist. |   Auf False festgelegt, Whiteboard in einer Besprechung nicht zulassen |
| AllowTranscription |Bestimmt, ob in Echtzeit und/oder nach dem meeting Beschriftungen und Abschriften an einen Benutzer Besprechungen zulässig sind.|    Auf False festgelegt, Umsetzung und Beschriftungen in einer Besprechung nicht zulassen  |  
| AllowSharedNotes | Bestimmt, ob Benutzer freigegebene Notizen zulässig sind. | Auf False festgelegt, um zu verhindern, dass Benutzer freigegebene Notizen |
|MediaBitRateKB |Bestimmt die Medien Bitrate für Audio/Video/Anwendungsfreigabe Übertragungen an Besprechungen  | Vorgeschlagener Wert ist 5000 (5 MB). Sie können ihn auf Basis der Anforderungen Ihrer Organisation ändern.| 

#### <a name="create-and-assign-a-meeting-policy"></a>Erstellen und Zuweisen einer besprechungsrichtlinie

1. Starten Sie eine Windows PowerShell-Sitzung als Administrator an.
2. Verbinden Sie mit der Online Skype-Connector.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Anzeigen einer Liste der Richtlinie Besprechungsoptionen.

       Get-CsTeamsMeetingPolicy
 
4. Suchen Sie nach die Option integrierte Richtlinie, bei denen alle Besprechungsrichtlinien deaktiviert werden. Es sieht folgendermaßen aus.
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. Gelten Sie die Option AllOff integrierten Richtlinie für alle Benutzer, die Teams in einer virtualisierten Umgebung verwendet werden soll. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Weitere Informationen zu Besprechungsrichtlinien Teams finden Sie unter [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

### <a name="virtualization-provider-requirements"></a>Anforderungen für die Virtualisierung-Anbieter

Die app Teams wurde auf führende Virtualisierung Lösungsanbieter validiert. Wenden Sie mit mehreren Anbietern für Land/Ihrer Region sich an Ihrer Lösungsanbieter Virtualisierung, um sicherzustellen, dass die Mindestanforderungen erfüllt sind.

### <a name="virtual-machine-requirements"></a>Anforderungen für die virtuellen Computer

Mit den unterschiedlichen Arbeitslasten und der benutzeranforderungen in einer virtualisierten Umgebung ist die folgenden mindestens VM-Konfiguration empfohlen.

|Parameter  |Measure  |
|---------|---------|
|vCPU mit    |  2 Kerne       |
|RAM     |  4 GB      |
|Speicher     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>Betriebssystemanforderungen für die virtuellen Computer

Die unterstützten Betriebssysteme für VM sind:

- Windows 10 und höher
- Windows Server 2012 R2 und höher

## <a name="install-teams-on-vdi"></a>Installieren von Teams auf VDI

Hier wird der Prozess und die Tools zum Bereitstellen von Teams-desktop-app. 

1. Herunterladen Sie Teams MSI-Paket mit einer der folgenden Links je nach der Umgebung. Wir empfehlen die 64-Bit-Version für eine VDI VM mit einem 64-Bit-Betriebssystem.

    - [32-Bit-version](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64-Bit-version](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Führen Sie den folgenden Befehl zum Installieren der MSI-Datei für die VDI-VM (oder Abschließen der Aktualisierung).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Dies installiert Teams Program Files. Zu diesem Zeitpunkt ist das goldene Bild Setup abgeschlossen.
 
    Die nächste interaktive Sitzung beginnt Teams und fordert die Anmeldeinformationen. Beachten Sie, dass es nicht möglich, automatisch gestartet Teams bei der Installation von Teams auf VDI mithilfe der ALLUSER-Eigenschaft zu deaktivieren. 

3. Führen Sie den folgenden Befehl zum Deinstallieren der MSI-Datei aus der VDI VM (oder Vorbereiten der Aktualisierung).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Dies deinstalliert Teams aus Program Files.

## <a name="known-issues-and-limitations"></a>Bekannte Probleme und Einschränkungen

Die folgenden sind Probleme und Einschränkungen für VDI-Teams bekannt.

- **Shared Session Host Typ Bereitstellungen**: Shared Session Host Typ Bereitstellungen (beispielsweise freigegebene nicht beständige VM-Konfiguration) werden nicht im Bereich.
- **Anruf- und Besprechungen**:

    - Anruf- und meeting-Szenarien sind nicht für VDI optimiert. Diese Szenarien führt schlecht. Es wird empfohlen, mithilfe von Richtlinien auf Benutzerebene, wie im Abschnitt [Festlegen von Richtlinien zum Deaktivieren der aufrufen und Funktionalität in Teams meeting](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) beschrieben.  
    - Die in diesem Artikel beschriebenen Richtlinien anwenden und wirkt sich auf die Möglichkeit, verwenden Sie aufrufende und Besprechungen-Funktion, die je nach den anderen Richtlinien, anderen Benutzern in Ihrer Organisation beeinträchtigen können. Wenn Benutzer in Ihrer Organisation nicht VDI-Clients verwenden, können Sie nicht die Richtlinien gelten.  

- **Teilnehmen an Anrufe und Besprechungen, die von anderen Benutzern erstellte**: zwar Richtlinien für die Benutzer beschränken von Besprechungen erstellen, sie können immer noch an Besprechungen teilnehmen, wenn ein anderer Benutzer aus der Besprechung, Ihnen wählt. An diesen Besprechungen, die Möglichkeit eines Benutzers zum Freigeben von Video, hängen Whiteboard verwenden und andere Features, ob Sie diese Features verwenden TeamsMeetingPolicy deaktiviert.  
- **Cache-Inhalten**: ist die virtuelle Umgebung, in welche Teams ausgeführt wird, nicht persistent (und Daten werden am Ende jeder Sitzung des Benutzers bereinigt), Benutzer möglicherweise Leistungseinbußen aufgrund von aktualisieren, unabhängig davon, ob der Benutzer die gleiche zugegriffen fest Inhalte in einer vorherigen Sitzung.
- **Clientupdates**: Teams auf VDI ist nicht vergleichbar, die nicht - VDI-Teams Clients werden automatisch aktualisiert.  Sie müssen das Bild VM aktualisieren, indem Sie eine neue MSI-Datei installieren, wie im Abschnitt [Installieren Teams auf VDI](#install-teams-on-vdi) beschrieben. Sie müssen die aktuelle Version auf eine neuere Version aktualisieren deinstallieren.
- **Benutzerinteraktion**: Benutzeroberfläche für die Teams in einer VDI-Umgebung kann von einer nicht-VDI-Umgebung abweichen. Die Unterschiede können aufgrund von Richtlinieneinstellungen werden und/oder feature Support in der Umgebung.

Teams bekannte Probleme, die nicht mit VDI verknüpft sind, finden Sie unter [bekannte Probleme mit Microsoft-Teams](Known-issues.md).

## <a name="related-topics"></a>Verwandte Themen

- [Installieren von Microsoft Teams mithilfe eines MSI-Pakets](msi-deployment.md)