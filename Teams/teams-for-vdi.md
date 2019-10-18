---
title: Teams für Virtualized Desktop Infrastructure
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: Erfahren Sie, wie Sie Microsoft Teams in einer VDI-Umgebung (virtualisierte Desktop Infrastruktur) ausführen.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fa560347d7263dafafc4f98e031b3b267f8fb12
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570223"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams für Virtualized Desktop Infrastructure

In diesem Artikel werden die Anforderungen und Einschränkungen für die Verwendung von Microsoft Teams in einer virtualisierten Umgebung beschrieben.

## <a name="what-is-vdi"></a>Was ist VDI?

Virtual Desktop Infrastructure (VDI) ist eine Virtualisierungstechnologie, die ein Desktop Betriebssystem und Anwendungen auf einem zentralen Server in einem Rechenzentrum hostet. Dies ermöglicht Benutzern mit einer vollständig gesicherten und kompatiblen zentralisierten Quelle eine vollständig personalisierte Desktopoberfläche. 
 
Derzeit stehen Teams in einer virtualisierten Umgebung mit Unterstützung für die Zusammenarbeit und Chatfunktionalität mit einem dedizierten beständigen virtualisierten Computer (VM) zur Verfügung. Befolgen Sie die Anleitungen in diesem Artikel, um eine optimale Benutzererfahrung zu gewährleisten. 

## <a name="teams-requirements"></a>Anforderungen für Teams

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>Einrichten von Richtlinien zum Deaktivieren von Anruf-und Besprechungsfunktionen in Teams

Die Anruf-und Besprechungs Erfahrung von Teams ist nicht für eine VDI-Umgebung optimiert (in Kürze verfügbar). Wir empfehlen, Richtlinien auf Benutzerebene zu definieren, um die Anruf-und Besprechungsfunktionen in Teams zu deaktivieren.

Sie können weiterhin Teams mit der Desktop-App "Teams" oder der Web-App in VDI vollständig in VDI ausführen. Es wird jedoch empfohlen, die Richtlinien festzulegen, um eine Gefährdung der Benutzerfreundlichkeit zu vermeiden.  

Es kann einige Zeit dauern (einige Stunden), bis die Richtlinienänderungen übertragen werden. Wenn Änderungen für ein bestimmtes Konto nicht sofort angezeigt werden, versuchen Sie es in ein paar Stunden noch einmal.

> [!NOTE]
> Wenn die Anrufe und Besprechungen von Teams für die Verwendung in virtuellen Desktopumgebungen optimiert sind, können Sie diese Richtlinien wiederherstellen und Benutzern die Verwendung von Teams ermöglichen, wie dies normalerweise der Fall wäre. 

#### <a name="calling"></a>Anrufe

Verwenden Sie die **CSTeamsCallingPolicy** -Cmdlets, um zu steuern, ob Benutzer in privaten und Gruppen-Chats Anruf-und Anrufoptionen verwenden dürfen. Hier sehen Sie die Liste der Richtlinieneinstellungen und empfohlenen Werte.

|Richtlinienname  |Beschreibung |Empfohlener Wert  |
|---------|---------|---------|
|AllowCalling    |Steuert die Interop-Aufruf Funktionen. Wenn Sie diese Option aktivieren, können Skype for Business-Benutzern Einzelgespräche mit Teams und umgekehrt führen.         |Auf "false" festlegen, um zu verhindern, dass Anrufe von Skype for Business-Benutzern in Teams anlanden.          |
|AllowPrivateCalling     | Steuert, ob die aufrufende app in der APP-Leiste auf der linken Seite des Teams-Clients verfügbar ist und ob Benutzer im privaten Chat Anruf-und Video Anrufoptionen sehen         |Auf "false" festlegen, um die Anruf-App aus der APP-Leiste auf der linken Seite von Teams zu entfernen und die Anruf-und Video Anrufoptionen im privaten Chat zu entfernen.          |

#### <a name="create-and-assign-a-calling-policy"></a>Erstellen und Zuweisen einer Anrufrichtlinie

1. Starten Sie eine Windows PowerShell-Sitzung als Administrator.
2. Stellen Sie eine Verbindung mit dem Skype Online-Connector her.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Anzeigen einer Liste der Anruf Richtlinienoptionen

       Get-CsTeamsCallingPolicy
 
4. Suchen Sie nach der integrierten Richtlinienoption, bei der alle Anruf Richtlinien deaktiviert sind. Es sieht so aus.
   
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

5. Wenden Sie die integrierte Richtlinienoption DisallowCalling auf alle Benutzer an, die Teams in einer virtualisierten Umgebung verwenden werden.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Weitere Informationen zu den Anruf Richtlinien für Teams finden Sie unter [Satz-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

#### <a name="meetings"></a>Besprechungen

Verwenden Sie die **CsTeamsMeetingPolicy** -Cmdlets, um die Art der Besprechungen zu steuern, die Benutzer erstellen können, die Features, auf die Sie während einer Besprechung zugreifen können, und die besprechungsfeatures, die anonymen und externen Benutzern zur Verfügung stehen. Hier sehen Sie die Liste der Richtlinieneinstellungen und empfohlenen Werte.

|Richtlinien Name |Beschreibung|Empfohlener Wert                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | Bestimmt, ob ein Benutzer private Besprechungen planen darf.| Auf "false" festlegen, um zu verhindern, dass der Benutzer private Besprechungen planen kann.  |
|AllowChannelMeetingScheduling  | Bestimmt, ob ein Benutzerkanal Besprechungen planen darf. | Auf "false" festlegen, um zu verhindern, dass der Benutzerkanal Besprechungen planen kann.                       |
|AllowMeetNow |Bestimmt, ob ein Benutzer die Möglichkeit hat, Ad-hoc-Besprechungen zu erstellen oder zu starten.              |  Legen Sie diesen Wert auf "false" fest, um zu verhindern, dass der Benutzer Ad-hoc-Besprechungen starten kann.                     |
|ScreenSharingMode | Bestimmt den Modus, in dem ein Benutzer seinen Bildschirm in anrufen oder Besprechungen freigeben darf. | Auf "deaktiviert" setzen, um zu verhindern, dass Benutzer ihre Bildschirme freigeben                          |
|AllowIPVideo |Bestimmt, ob Video in den Besprechungen oder Anrufen eines Benutzers aktiviert ist.                  |    Auf "false" festlegen, um zu verhindern, dass der Benutzer sein Video freigibt                                         |
| AllowAnonymousUsersToDialOut | Bestimmt, ob anonyme Benutzer die Möglichkeit haben, sich an eine PSTN-Nummer zu wählen. | Auf "false" festlegen, um zu verhindern, dass anonyme Benutzer sich auswählen                                  |
| AllowAnonymousUsersToStartMeeting | Bestimmt, ob anonyme Benutzer eine Besprechung starten können.     |  Auf "false" festlegen, um zu verhindern, dass Benutzer eine Besprechung starten                                            |
| AllowOutlookAddIn |Bestimmt, ob ein Benutzer Teambesprechungen im Outlook-Desktop Client planen kann.| Auf "false" festlegen, um einem Benutzer das Planen von Teams-Besprechungen im Outlook-Desktop Client zu verbieten|
| AllowParticipantGiveRequestControl|Bestimmt, ob Teilnehmer die Bildschirmfreigabe anfordern oder kontrollieren können.| Auf "false" festlegen, um zu verhindern, dass der Benutzer die Steuerung in einer Besprechung erteilt und anfordert    |
| AllowExternalParticipantGiveRequestControl | Bestimmt, ob externe Teilnehmer die Bildschirmfreigabe anfordern oder kontrollieren können.| Auf "false" festlegen, um zu verhindern, dass ein externer Benutzer die Steuerung in einer Besprechung anfordert|
|AllowPowerPointSharing|Bestimmt, ob PowerPoint-Freigabe in den Besprechungen eines Benutzers zulässig ist. |Auf "false" festlegen, um einen Benutzer zu verbieten, PowerPoint-Dateien in einer Besprechung freizugeben  |
|AllowWhiteboard | Bestimmt, ob Whiteboard in den Besprechungen eines Benutzers zulässig ist. |   Auf "false" festlegen, um das Whiteboard in einer Besprechung zu verbieten |
| AllowTranscription |Bestimmt, ob in den Besprechungen eines Benutzers Echt Zeit-und/oder Post-Meeting-Beschriftungen und-Transkriptionen zulässig sind.|    Auf "false" festlegen, um Transkription und Beschriftungen in einer Besprechung zu untersagen  |  
| AllowSharedNotes | Bestimmt, ob Benutzer freigegebene Notizen übernehmen dürfen. | Auf "false" festlegen, um zu verhindern, dass Benutzer freigegebene Notizen erstellen |
|MediaBitRateKB |Bestimmt die Medien Bitrate für Audio/Video/App-Freigabe Übertragungen in Besprechungen  | Der vorgeschlagene Wert ist 5000 (5 MB). Sie können es entsprechend den Anforderungen Ihrer Organisation ändern.| 

#### <a name="create-and-assign-a-meeting-policy"></a>Erstellen und Zuweisen einer Besprechungsrichtlinie

1. Starten Sie eine Windows PowerShell-Sitzung als Administrator.
2. Stellen Sie eine Verbindung mit dem Skype Online-Connector her.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Anzeigen einer Liste der Besprechungsrichtlinien Optionen

       Get-CsTeamsMeetingPolicy
 
4. Suchen Sie nach der integrierten Richtlinienoption, bei der alle Besprechungsrichtlinien deaktiviert sind. Es sieht so aus.
   
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

5. Wenden Sie die integrierte Richtlinienoption AllOff auf alle Benutzer an, die Teams in einer virtualisierten Umgebung verwenden werden. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Weitere Informationen zu den Team-Besprechungsrichtlinien finden Sie unter [Satz-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

### <a name="virtualization-provider-requirements"></a>Anforderungen des Virtualisierungs-Anbieters

Die Teams-App wurde bei führenden Anbietern von Virtualisierungslösungen validiert. Bei mehreren Marktanbietern wenden Sie sich an Ihren Anbieter von Virtualisierungslösungen, um sicherzustellen, dass die Mindestanforderungen erfüllt sind.

### <a name="virtual-machine-requirements"></a>Anforderungen virtueller Computer

Mit den unterschiedlichen Arbeitslasten und Benutzeranforderungen in einer virtualisierten Umgebung ist die folgende Mindestkonfiguration für VM empfohlen.

|Parameter  |Maßnahme  |
|---------|---------|
|vCPU    |  2 Kerne       |
|RAM     |  4 GB      |
|Speicher     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>Betriebssystemanforderungen für virtuelle Maschinen

Die unterstützten Betriebssysteme für VM sind:

- Windows 10 und höher
- Windows Server 2012 R2 und höher

## <a name="install-teams-on-vdi"></a>Installieren von Teams auf VDI

Hier sehen Sie den Prozess und die Tools zum Bereitstellen der Desktop-App von Teams. 

1. Laden Sie das MSI-Paket für Teams mit einem der folgenden Links in Abhängigkeit von der Umgebung herunter. Wir empfehlen die 64-Bit-Version für eine VDI-VM mit einem 64-Bit-Betriebssystem.

    - [32-Bit-Version](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64-Bit-Version](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Führen Sie den folgenden Befehl aus, um die MSI-Datei auf der VDI-VM zu installieren (oder vollständig zu aktualisieren).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Dadurch werden Teams in Programmdateien installiert. An diesem Punkt ist die Einrichtung des goldenen Bilds abgeschlossen.
 
    In der nächsten interaktiven Anmeldesitzung werden Teams gestartet, und es werden Anmeldeinformationen angefordert. Beachten Sie, dass es nicht möglich ist, den automatischen Start von Teams bei der Installation von Teams auf VDI mithilfe der alluser-Eigenschaft zu deaktivieren. 

3. Führen Sie den folgenden Befehl aus, um die MSI-Datei von der VDI-VM zu deinstallieren (oder die Aktualisierung vorzubereiten).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Dadurch wird Microsoft Teams aus Programmdateien deinstalliert.

## <a name="known-issues-and-limitations"></a>Bekannte Probleme und Einschränkungen

Im folgenden sind bekannte Probleme und Einschränkungen für Teams in VDI zu finden.

- **Bereitstellungen für Shared Session-Hosttypen**: Bereitstellungen für Shared Session-Hosttypen (beispielsweise freigegebene nicht persistente VM-Konfiguration) sind nicht im Bereich.
- **Anrufe und Besprechungen**:

    - Anruf-und Besprechungs Szenarien sind für VDI nicht optimiert. Diese Szenarien werden schlecht ausgeführt. Wir empfehlen die Verwendung von Richtlinien auf Benutzerebene, wie im Abschnitt [Richtlinien zum Deaktivieren von Anrufen und Besprechungsfunktionen in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) beschrieben.  
    - Die Anwendung der in diesem Artikel beschriebenen Richtlinien wirkt sich auf die Möglichkeit aus, die Funktionalität von Anrufen und Besprechungen zu verwenden, die sich je nach anderen Richtlinien auf andere Benutzer in Ihrer Organisation auswirken kann. Wenn Benutzer in Ihrer Organisation nicht-VDI-Clients verwenden, können Sie festlegen, dass die Richtlinien nicht angewendet werden.  

- **Teilnahme an anrufen und Besprechungen, die von anderen Benutzern erstellt wurden**: Obwohl die Richtlinien Benutzer daran hindern, Besprechungen zu erstellen, können Sie weiterhin an Besprechungen teilnehmen, wenn sich ein anderer Benutzer aus der Besprechung anwählt. In diesen Besprechungen hängt die Möglichkeit des Benutzers, Video zu teilen, die Verwendung von Whiteboard und anderen Features davon ab, ob Sie diese Features mithilfe von TeamsMeetingPolicy deaktiviert haben.  
- **Zwischengespeicherter Inhalt**: Wenn die virtuelle Umgebung, in der die Teams ausgeführt werden, nicht persistent ist (und die Daten am Ende jeder Benutzersitzung bereinigt werden), können Benutzer die Leistungsverschlechterung aufgrund der Inhaltsaktualisierung bemerken, unabhängig davon, ob der Benutzer auf dieselbe Inhalt in einer vorherigen Sitzung.
- **Client Updates**: Teams auf VDI werden nicht automatisch mit der MSI-Installation pro Computer aktualisiert. Sie müssen das VM-Abbild aktualisieren, indem Sie eine neue MSI-Datei installieren, wie im Abschnitt [Installieren von Teams im VDI](#install-teams-on-vdi) beschrieben. Sie müssen die aktuelle Version deinstallieren, um Sie auf eine neuere Version zu aktualisieren.
- **Benutzererfahrung**: die Benutzeroberfläche von Teams in einer VDI-Umgebung kann sich von einer nicht-VDI-Umgebung unterscheiden. Die Unterschiede sind möglicherweise auf Richtlinieneinstellungen und/oder Funktionsunterstützung in der Umgebung zurückzuführen.

Informationen zu bekannten Problemen, die nicht mit VDI in Verbindung stehen, finden Sie unter [bekannte Probleme für Microsoft Teams](Known-issues.md).

## <a name="related-topics"></a>Verwandte Themen

- [Installieren von Microsoft Teams mithilfe eines MSI-Pakets](msi-deployment.md)
