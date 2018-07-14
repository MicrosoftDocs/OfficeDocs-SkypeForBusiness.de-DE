---
title: Was sind Teams live Ereignisse?
author: TonySmith
ms.author: tonysmit
manager: serdars
ms.date: 7/11/2018
ms.topic: article
ms.service: msteams
ms.reviwer: tonysmit
description: Hier erfahren Sie, wie Live Ereignisse Benutzer Video- und Content an Microsoft-Teams, Yammer und Microsoft Stream große online Benutzergruppe übertragen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a00d9e25b68380a6b44346f0eef628b8aa5c1308
ms.sourcegitcommit: 11adc15c5191d7bf6bb37058cae3d54649c25e97
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2018
ms.locfileid: "20364642"
---
# <a name="what-are-teams-live-events"></a>Was sind Teams live Ereignisse?
**Zusammenfassung**: Hier erfahren Sie, wie live Ereignisse Benutzer Video- und Content an Microsoft-Teams, Yammer und Microsoft Stream große online Benutzergruppe übertragen können.

## <a name="overview"></a>Übersicht
Live Ereignisse in Microsoft 365 können Benutzer Video- und Content an Microsoft-Teams, Yammer und [Microsoft Stream](https://docs.microsoft.com/en-us/stream/)große online Benutzergruppe übertragen.    

Microsoft-Teams, bietet Chat-basierte Zusammenarbeit aufrufen, Besprechungen und mit live Ereignisse können Sie die Benutzergruppe Besprechungsliste erweitern.  Microsoft-Teams live Ereignisse ist eine Erweiterung von Teams Besprechungen, die Benutzern ermöglichen, Video, Inhalte und Besprechung an eine große online Benutzergruppe übertragen. Diese sind dafür verantwortlich, die viele Communications bedeutete, in dem der Host des Ereignisses wird die Interaktionen führende und die Teilnahme Benutzergruppe ist in erster Linie zum Anzeigen des Inhalts von Host gemeinsam genutzt werden. Die Teilnehmer können das live oder aufgezeichnete-Ereignis im Yammer, Teams und/oder Microsoft Stream Video und können mit dem Referenten über moderierte f & A interagieren oder Yammer Unterhaltung. 

Ersetzen Sie Teams live Ereignisse gilt die nächste Version von Skype Besprechung übertragen und schließlich wird die Funktionen in Skype Besprechung übertragen. Für die public Preview-Version von live-Ereignissen weiterhin Microsoft Skype Besprechung übertragen, ohne Unterbrechung im Dienst für neue oder zukünftigen Ereignisse unterstützen. Wir empfehlen Ihnen, live-Ereignis im Teams Bildschirmfreigabe, einschließlich der neuen Features nutzen Teilnehmeranzahl, testen und Unterstützung für externe Hardware und Software Encoder. 

Verwandte: [Microsoft-Teams live Ereignisse Overview](https://support.office.com/en-us/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US).

## <a name="key-components"></a>Wichtige Komponenten
Im folgende Diagramm werden die Komponenten auf hohe Ebene zum Microsoft 365 live Ereignisse gezeigt. 

![Teams live-Ereignisse](media/teams-live-events.png)

### <a name="scheduling"></a>Planung
Teams für die Organisatoren, ein Ereignis mit der entsprechenden Teilnehmer Berechtigungen erstellen, Ereignis Teammitglieder festzulegen, wählen Sie Produktion-Methode einladen Teilnehmer ermöglicht. Wenn das live-Ereignis innerhalb einer Gruppe Yammer erstellt wurde, werden die Teilnehmer live-Ereignis Yammer Unterhaltung für die Interaktion mit dem Ereignis Team verwenden können. 

### <a name="production"></a>Produktion
Die live-Ereignisse in Microsoft 365 ein Spektrum der Produktionsszenarien unterstützen, schließen Sie ein Schnellstart-Ereignis mithilfe von Webcams oder externen Encoder Ereignisse mit dem Studio Qualität Equipment. Video Eingabe bildet die Grundlage für die live-Ereignisse und kann aus einer einzelnen Webcam an eine professionelle video Multi-Kamera-Produktion variieren. Kunden können diese Optionen je nach ihren Project-Anforderungen und Ihrem Budget auswählen. 
- **Schnellstart**: die Schnellstart-Methode ermöglicht es, Benutzer, deren live Ereignisse mithilfe von Teams Besprechungen zu erstellen. Diese Option ist am besten, wenn Sie die Audiodaten verwenden möchten, und Videogeräte an den PC angeschlossenes und/oder remote Referenten einladen / Diskussionsteilnehmer für das Ereignis beteiligt sind.  Mit dieser Option können Benutzer auf einfache Weise verwenden, deren Webcams und ihren Bildschirm als Eingabe für die Übertragung freigeben.  
- **Externe Encoder (bald verfügbar)**: externe Encoder zulassen, dass Benutzer ihre live Ereignisse direkt aus einer externen Hardware oder softwarebasierte Encoder mit Microsoft Stream zu erstellen.  Diese Option ist am besten für Sie bereits über eine Studio Qualität Equipment (z. B. Media Mischern) verfügen, das an einen Dienst RTMP streaming unterstützt.  Diese Option wird im großen Maßstab Fälle wie executive Stadt Hallen – in der Regel verwendet, in ein einzelner Datenstrom aus einem Media Mixer auf die Benutzergruppe gesendet wird.  

### <a name="streaming-platform"></a>Streaming-Plattform
Dies die folgenden Teile besteht.

#### <a name="azure-media-services"></a>Azure Media-Dienste
[Azure Media-Dienste](https://docs.microsoft.com/en-us/azure/media-services/previous/) können Sie die Übertragung Qualität video streaming-Dienste größere Benutzergruppen auf heutigen am häufigsten verwendeten mobilen Geräten zu erreichen. Media-Dienste verbessert Eingabehilfen, Verteilergruppen und Skalierbarkeit und können sie einfach und kostengünstige Stream von Inhalten für Ihre lokale und weltweit Zielgruppe – alle beim Schützen Ihrer Inhalte.

#### <a name="azure-content-delivery-network-cdn"></a>Azure Content Delivery Network (CDN)
Nachdem Ihre Stream live geschaltet wird, wird es über dem [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/en-us/azure/cdn/)bereitgestellt. Azure Media-Dienste bietet integrierte CDN für streaming-Endpunkte. Dies ermöglicht die Datenströme weltweit mit keine Pufferung angezeigt werden. 

### <a name="enterprise-content-delivery-network-ecdn"></a>Enterprise Content Delivery Network (eCDN) 
Das Ziel des eCDN ist den Videoinhalt aus dem Internet und verteilen die Inhalte im gesamten Unternehmen ohne Beeinträchtigung der Leistung des Netzwerks. Die folgenden certified Partner können Sie Ihr Netzwerk für live Ereignisse optimieren: 
- Struktur
- Kollective
- Lernen (bald verfügbar zum Schnellstart)

### <a name="attendee-experience"></a>Umgebung Teilnehmer
Umgebung der Teilnehmer ist der wichtigste Aspekt der live Ereignisse, und es ist wichtig, dass die Teilnehmer im live-Ereignis ohne Probleme teilnehmen können. Umgebung der Teilnehmer Azure Media Player verwendet und kann über den Desktop, Browser und Mobile (iOS Android). Microsoft 365 bietet Yammer und Teams als zwei Zusammenarbeit Hubs und die Teilnehmer live Erfahrung in diese Tools für die Zusammenarbeit integriert ist.  Die externe Encoder-basierten live-Ereignisse können auch von Teilnehmern in der Microsoft-Stream Portal zugegriffen werden.

## <a name="prerequisites"></a>Voraussetzungen

### <a name="who-can-create-live-events"></a>Wer kann live Ereignisse erstellen
Die folgenden erforderlichen Komponenten sind erforderlich für den Benutzer ein live-Ereignis in der Vorschau Zeitrahmen planen:   
- Benutzer verfügt über eine Lizenz für Office 365 Enterprise E3 oder E5. 
- Für Microsoft-Teams, Skype für Business Online und Microsoft Stream ist Benutzer aktiviert.
- Benutzer für die Planung von privaten Besprechung in Teams aktiviert ist (TeamsMeetingPolicy AllowPrivateMeetingScheduling auf True festgelegt ist).
- Benutzer für die Planung von live-Ereignis in Teams aktiviert ist (TeamsMeetingBroadcastPolicy AllowBroadcastScheduling auf True festgelegt ist).
- Benutzer verfügt über Berechtigungen zum Erstellen von live Ereignisse in Microsoft Stream (für externe Encoder Produktion).

> [!NOTE]
> O365 Gäste, Verbund- und anonyme Benutzer können nicht als Hersteller oder Referenten in Teams live Ereignisse eingeladen werden. 
 
### <a name="who-can-watch-live-event"></a>Wer live-Ereignis überwachen können
Überprüfen Sie die Tabelle unten, um anzuzeigen, die an ein live-Ereignis teilnehmen können. 

|ATTENDEE Sichtbarkeit           |Schnellstart  |Externe encoder  |
|------------------------------|-------------|------------------|
|Öffentliche (anonyme Benutzer)      |  Ja        |  Nein              |
|Gast Benutzer *                   |  Nein         |  Nein              |
|Jede Person in einer verbundenen Unternehmen * |  Nein         |  Nein              |
|Jeder in Unternehmen           |  Ja        |  Ja             |
|Spezifische Gruppen / für die Personensuche      |  Ja        |  Ja             |
* Gast und Verbundbenutzer können als live-Ereignis anonyme Teilnehmer beitreten.

Zur Teilnahme an einer live-Ereignis als authentifizierter Benutzer, je nach der Produktionsmethode ist eine Office 365-Lizenz erforderlich.

- **Für Quick Start Produktion**: der Benutzer muss ein Benutzer Teams sein.
- **Für externe Encoder Produktion**: der Benutzer muss ein Stream-Benutzer sein.
 
## <a name="capabilities"></a>Funktionen
In der folgenden Tabelle werden die Hauptfunktionen in Live Ereignisse und wie unterscheiden sich von Skype Besprechung übertragen angebotenen behandelt. 

|Funktion   |Skype-Livekonferenzen |Teams live Ereignisse (Schnellstart) |Teams live Ereignisse (externe Encoder) |
|---------|---------|---------|---------|
|Maximale Benutzergruppe Größe |10.000 Teilnehmer |10.000 Teilnehmer |10.000 Teilnehmer |
|Erstellung des Live-Ereignis |   Skype-Meeting Broadcast-Portal |Teams, Yammer über Teams | Teams, über den Teams, Stream Yammer |
|Benutzergruppe Engagements – Yammer |& #x 2714; |& #x 2714; (integrierte Experience) |& #x 2714; (integrierte Experience) |
|Benutzergruppe Engagements – moderiert f & A |& #x 2714;  |& #x 2714; |& #x 2714; |
|Hersteller-Client für Windows |& #x 2714; (Skype für Unternehmen) |& #x 2714; (Teams) |& #x 2714; (Stream-Objekt einbetten Teams über Stream) |
|Hersteller-Client auf einem Mac |X  | & #x 2714; (Teams) |& #x 2714; (Stream-Objekt einbetten Teams über Stream) |
|Teilnehmeranzahl in Producer-Benutzeroberfläche |X  |& #x 2714; (Teams) |& #x 2714; (Stream-Objekt einbetten Teams über Stream) |
|Ermöglicht es mehrere Referenten |& #x 2714; (Skype für Unternehmen) |& #x 2714; (Teams) |-  |
Ein Referent während der Besprechung einladen |& #x 2714; (Skype für Unternehmen) |X |- |
|Referent beitreten auf Webservern und Mobile |& #x 2714; (Skype für Unternehmen)  |X |- |
|Referenten – PSTN-Zugang |X |& #x 2714; (Teams) |- |
|Ein Bildschirm angezeigt |X |& #x 2714; (Teams) |- |
|Präsentieren Sie eine PowerPoint (PPT-Freigabe) |& #x 2714; |X (per Bildschirmfreigabe gemindert) |- |
|Cloud-basierten besprechungsaufzeichnung |& #x 2714; |& #x 2714; |& #x 2714; |
|Automatische veröffentlichen Aufzeichnung in Microsoft Stream-Objekt |X |X |& #x 2714; |
|Echtzeit Beschriftungen und Übersetzung |& #x 2714; |& #x 2714; (bald verfügbar) |X |
|Beschriftungen in Aufzeichnungen live-Ereignis |& #x 2714; |& #x 2714; (bald verfügbar) |& #x 2714; |
|ATTENDEE DVR-Steuerelemente (anhalten, Zurückspulen) |& #x 2714; |& #x 2714; |& #x 2714; |
|Partner eCDN Support |& #x 2714; (Struktur, Kollective, lernen) |& #x 2714; (bald verfügbar) |& #x 2714; (Struktur, Kollective, lernen) |
|Nach dem broadcast Anwesenheitsbericht für Hersteller |& #x 2714; |& #x 2714; (bald verfügbar) |X |
|Benutzergruppe Stimmung Analyse – Live Stimmabgabe & Umfragen |& #x 2714; (Microsoft Pulse) |X |X |

## <a name="planning--setup"></a>Planung und Setup
In diesem Artikel wird erläutert, wie Sie Benutzer mithilfe von Teams live-Ereignissen in Ihrer Organisation einrichten können.

1. Überprüfen Sie die [regionale Verfügbarkeit für Teams live Ereignisse](#configure-live-events) , um die Regionen Verständnis darüber, wie live Ereignisse in derzeit verfügbar sind.
2. Wenn Sie dies noch nicht getan haben richten Sie [Skype für Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online?redirectSourcePath=%252fen-us%252farticle%252fset-up-skype-for-business-online-40296968-e779-4259-980b-c2de1c044c6e) für Ihre Organisation ein.
3. Wenn Sie Teilnehmer beitreten von innerhalb des Unternehmensnetzwerks haben, sollten Sie Onboarding und [Einrichten eines Anbieters für die von Microsoft empfohlenen eCDN](#set-up-ecdn-provider-for-teams-live-events) Bandbreite in Ihrem Netzwerk zu optimieren. 
4. Stellen Sie sicher, dass Sie die richtige Lizenz Zuordnungen für [Benutzer können live Ereignisse erstellen](#who-can-create-live-events) und [können, die live Ereignisse Video](#who-can-watch-live-event)verfügen. 
5. Für die Benutzer, die live Ereignisse in Ihrem Unternehmen erstellen können, sollten [live-Ereignis Zeitplan aktivieren](#enable-live-event-scheduling-for-the-user) . Dies ist erforderlich für Schnellstart & externe Encoder Ereignisse. 
6. Für externe Encoder Ereignisse, [aktivieren Benutzer für die Erstellung von live Ereignisse Stream Verwaltungsportal von Microsoft](#enable-microsoft-stream-for-users-in-the-organization).  

### <a name="regional-availability-for-teams-live-events"></a>Regionale Verfügbarkeit für Teams live-Ereignisse
Sie können mehrere Regionen Teams live Ereignisse verwenden. Die folgende Informationen zeigt Verfügbarkeit für Teammitglieder Ereignis und Teilnehmer. Die Region für das Ereignis wird je nach der Organisator und die Office 365-Mandanten automatisch ausgewählt.

#### <a name="regions-available"></a>Bereichen verfügbar sind
- Amerikanischen Kontinent
- Europa/Afrika
- Asien-Pazifik

#### <a name="exclusions"></a>Ausschlüsse
- Wechseln Sie lokal
  - Großbritannien, Indien und andere Microsoft-Teams wechseln Sie lokal werden derzeit nicht unterstützt.
- Wechseln Sie auf lokal - Kanada 
  - In der Vorschau Kunden können Ereignisse erstellen, aber ihre Daten werden in Nordamerika Region verwaltet werden.
- China
  - Ereignis Teammitglieder und Teilnehmer ist nicht möglich Teams live Ereignisse verwendet werden, da Azure CDN nicht in China zugegriffen werden kann. Eine problemumgehung besteht darin, ein Unternehmen VPN-Verbindung verwenden, die über das Unternehmensnetzwerk des Kunden zu CDN verbundenen Client fungiert.

### <a name="set-up-your-network-for-teams-live-events"></a>Richten Sie Ihr Netzwerk für Teams live Ereignisse 
Wechseln Sie zur [Richten Sie Ihr Netzwerk für Teams live Ereignisse](https://review.docs.microsoft.com/en-us/MicrosoftTeams/teams-live-events-set-up-your-network?branch=teams-live-events).

### <a name="set-up-ecdn-provider-for-teams-live-events"></a>Einrichten von eCDN-Anbieter für Teams live Ereignisse
Demnächst.

### <a name="enable-live-event-scheduling-for-the-user"></a>Aktivieren Sie planen von live-Ereignis für den Benutzer
Die Planung von live-Ereignis wird für einen Benutzer Teams standardmäßig aktiviert.  

Verwenden Sie die Einstellung AllowBroadcastScheduling in TeamsMeetingBroadcastPolicy in PowerShell Teams können Sie steuern, ob der Benutzer live Ereignisse in Teams oder nicht erstellen kann.  Weitere Informationen finden Sie Informationen zum Verwalten von TeamsMeetingBroadcastPolicy mit Office 365 PowerShell [hier](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Wenn der Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer globale Richtlinie ein, die Aufzeichnung, die in der Standardeinstellung aktiviert hat. 

 Verwenden Sie das folgende Cmdlet für einen Benutzer zum Zugreifen auf globale Richtlinie um eine bestimmte Richtlinie-Zuordnung für einen Benutzer zu entfernen.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Um Wert der AllowBroadcastScheduling in der globalen Richtlinie zu ändern, verwenden Sie das folgende Cmdlet aus:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastScheduling $false
```
#### <a name="scenarios"></a>Scenarios
**Ich möchte alle Benutzer in meinem Unternehmen live Ereignisse erstellen können.**
1. Bestätigen Sie globale CsTeamsMeetingBroadcastPolicy hat AllowBroadcastScheduling = True.
2. Vergewissern Sie sich alle Benutzer haben die globalen CsTeamsMeetingBroadcastPolicy oder eine der Richtlinien CsTeamsMeetingBroadcastPolicy mit AllowBroadcastScheduling = True.

**Ich möchte, dass die meisten Benutzer live Ereignisse erstellen können, aber ich möchte selektiv bestimmte Benutzer zu deaktivieren, die nicht zulässig ist.**
1. Bestätigen Sie globale CsTeamsMeetingBroadcastPolicy hat AllowBroadcastScheduling = True.
2. Bestätigen Sie die Mehrzahl der Benutzer haben die globalen CsTeamsMeetingBroadcastPolicy oder eine der Richtlinien CsTeamsMeetingBroadcastPolicy mit AllowBroadcastScheduling = True.
3. Vergewissern Sie sich alle anderen Benutzer gewährt wurden eine der Richtlinien CsTeamsMeetingBroadcastPolicy mit AllowBroadcastScheduling = False.

**Planen von live-Ereignis auf 100 % deaktiviert werden sollen.**
1. Bestätigen Sie globale CsTeamsMeetingBroadcastPolicy hat AllowBroadcastScheduling = False.
2. Vergewissern Sie sich alle Benutzer der globalen CsTeamsMeetingBroadcastPolicy oder eine der Richtlinien CsTeamsMeetingBroadcastPolicy mit AllowBroadcastScheduling gewährt wurden = False.

**Ich möchte live Ereignisse für die Mehrheit der Benutzer deaktiviert, aber bestimmte Benutzer für live Ereignisse selektiv zu aktivieren.** 
1. Bestätigen Sie globale CsTeamsMeetingBroadcastPolicy hat AllowBroadcastScheduling = False.
2. Vergewissern Sie sich die meisten Benutzer gewährt wurde der globalen CsTeamsMeetingBroadcastPolicy oder eine der Richtlinien CsTeamsMeetingBroadcastPolicy mit AllowBroadcastScheduling = False.
3. Vergewissern Sie sich alle anderen Benutzer gewährt wurden eine der Richtlinien CsTeamsMeetingBroadcastPolicy mit AllowBroadcastScheduling = True.

### <a name="enable-creation-of-external-encoder-based-live-events-for-users"></a>Aktivieren Sie Erstellung von externen Encoder-basierten live Ereignissen für Benutzer

#### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Aktivieren von Microsoft-Stream für Benutzer in der Organisation
Microsoft-Stream steht als Teil von Office 365-Abonnements zu auswählbaren oder als eigenständigen Dienst. Einzelheiten finden Sie unter [Stream Lizenzierung Overview](https://docs.microsoft.com/en-us/stream/license-overview) . Hinweis Microsoft Stream ist nicht in Business Essentials oder Business Premium-Plänen enthalten.  

Erfahren Sie mehr dazu, wie Sie [Lizenzen für Benutzer in Office 365 zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , damit Benutzer Microsoft Stream zugreifen können.  Stellen Sie sicher, dass Microsoft-Stream für die Benutzer nicht ausgeschlossen wird, wie in [diesem Artikel](https://docs.microsoft.com/en-us/stream/disable-user-organization)definiert.

#### <a name="ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Sicherstellen Sie, dass Benutzer über Berechtigungen zum Erstellen live-Ereignis in Microsoft Stream haben
In der Standardeinstellung kann Person im Unternehmen Inhalte in Stream-Objekt erstellen, sobald Stream aktiviert ist und die Lizenz für den Benutzer zugewiesen ist. Microsoft Stream-Administrator können [Mitarbeiter bei der Erstellung von einschränken](https://docs.microsoft.com/en-us/stream/restrict-uploaders) , in Stream-Objekt. Der Benutzer, die in dieser Liste beschränkt sind möglich zum Aufzeichnen von Besprechungen nicht.

#### <a name="ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Stellen Sie sicher live-Ereignis, das die Unternehmensrichtlinie durch den Administrator des Datenstroms festlegen Organisatoren zugestimmt haben
Wenn ein Microsoft-Stream-Administrator [eine Unternehmensrichtlinie Richtlinien einrichten hat](https://docs.microsoft.com/en-us/stream/company-policy-and-consent) und Mitarbeiter dieser Richtlinie zu akzeptieren erfordert, bevor das Speichern von Inhalten, klicken Sie dann müssen Benutzer vor dem Erstellen einer live-Ereignis (mit der externen Encoder Produktion) in Microsoft-Teams. Bevor Sie Einführung live Ereignisse Feature in der Organisation, stellen Sie sicher, dass haben Benutzer, die diese live Ereignisse erstellen werden die Richtlinie zugestimmt. 

## <a name="configure-live-events"></a>Konfigurieren des live-Ereignisse

### <a name="set-up-event-support-link-coming-soon"></a>Einrichten von Ereignis Support Link (bald verfügbar)
Dies ist die Verknüpfung, die an die Teilnehmer live-Ereignis angezeigt werden. 

PowerShell

Führen Sie in Windows PowerShell das folgende Cmdlet aus:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
### <a name="configure-attendee-visibility-options"></a>Konfigurieren Sie die Sichtbarkeitsoptionen für Teilnehmer
Live-Ereignis Organisatoren Ereignisse mit entsprechenden Attendee Sichtbarkeit erstellen können.

|Werte  |Verhalten  |
|---------|---------|
|Jeder     |Der Benutzer hat eine Option zum Erstellen von live Ereignisse mit dem folgenden Attendee Sichtbarkeit: Public, jede Person in Unternehmen und bestimmte Personen. |
|EveryoneInCompany     |Der Benutzer hat eine Option zum Erstellen von live Ereignisse mit dem folgenden Attendee Sichtbarkeit: alle Benutzer im Unternehmen und bestimmte Personen. Der Benutzer kann nicht live Ereignisse erstellen, die durch anonyme Benutzer behandelt werden kann.|
|InvitedUsers |Der Benutzer kann nur live Ereignisse erstellen, die auf bestimmte Personen beschränkt sind durch den Organisator des Ereignisses eingegeben wurde.  Der Benutzer kann nicht mit öffentlichen und alle Benutzer im Unternehmen Authentifizierung live Ereignisse erstellen. |

PowerShell

Verwenden Sie die Einstellung BroadcastAttendeeVisibility in TeamsMeetingBroadcastPolicy in PowerShell können Sie steuern, ob die Benutzer broadcast Ereignisse planen können, die durch anonyme Teilnehmer beobachtet werden kann. Erfahren Sie mehr über das Verwalten von TeamsMeetingBroadcastPolicy mit Office 365 PowerShell hier.  

Es sei denn, die Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer globale Richtlinie ein, die standardmäßig auf EveryoneInCompany festgelegt hat. 
 
Führen Sie in Windows PowerShell das folgende Cmdlet aus, damit Benutzer anonyme Ereignisse in der globalen Richtlinie erstellen können:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>Konfigurieren Sie die Aufzeichnungsoptionen
> [!NOTE]
> Diese Option ist für Ereignisse, die nur Schnellstart Produktion-Methode verwenden.

Dies ermöglicht Administratoren zur Steuerelement an, ob die live Ereignisse immer nie aufgezeichnet aufgezeichnet werden, oder Organisator des Ereignisses zum Aufzeichnen des Ereignisses oder nicht entscheiden kann.  

|Werte  |Verhalten  |
|---------|---------|
|Immer aktiviert |Die von diesem Benutzer organisierte live Ereignisse werden immer aufgezeichnet.  Benutzer keine Option außer Kraft gesetzt.  Wenn das live Ereignis aufgezeichnet wird, die Mitglieder des Teams können die Aufzeichnung nach dem Ereignis herunterzuladen und die Teilnehmer können sehen Sie sich das Ereignis nach Abschluss des Ereignisses. |
|AlwaysDisabled |Die von diesem Benutzer organisierte live Ereignisse werden nie aufgezeichnet.  Benutzer keine Option außer Kraft gesetzt.  Wenn das live-Ereignis gespeichert ist, keine Aufzeichnung wird für die Mitglieder des Teams erstellt, und die Teilnehmer können nicht sehen Sie sich das Ereignis aus, nachdem sie sich über befindet. |
|UserOverride |Benutzer kann entscheiden, ob das live-Ereignis aufgezeichnet wird, damit eine Aufzeichnungsdatei für die Mitglieder des Teams erstellt werden kann und Teilnehmer können sehen Sie sich das Ereignis nach Abschluss des Ereignisses. |

PowerShell

Verwenden Sie die Einstellung BroadcastRecordingMode in TeamsMeetingBroadcastPolicy in PowerShell Steuerelement Aufzeichnungsoptionen live Ereignisse vom Organisator live-Ereignis erstellt.

Führen Sie in Windows PowerShell das folgende Cmdlet, um Aufzeichnungsmodus in der globalen Richtlinie zu aktualisieren:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Konfigurieren von Real-Time Lautschrift und Übersetzung in Teams live-Ereignisse (bald verfügbar)
> [!NOTE]
> Diese Option ist für Ereignisse, die nur Schnellstart Produktion-Methode verwenden.

Dadurch wird die live-Ereignis Organisatoren aktivieren in Echtzeit Beschriftungen und Übersetzung für den Teilnehmern live-Ereignis. 

PowerShell

Verwenden Sie die Einstellung AllowBroadcastTranscription in TeamsMeetingBroadcastPolicy in PowerShell Kontrolle, ob die live-Ereignis Teilnehmer werden zu prüfen, ob Sie mehr über das Verwalten von TeamsMeetingBroadcastPolicy mit Office 365 PowerShell Hier erfahren können.  

Wenn der Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer globale Richtlinie ein, die Lautschrift & Übersetzung standardmäßig deaktiviert hat.

Führen Sie in Windows PowerShell das folgende Cmdlet, um die Umsetzung und eine Übersetzung auf Ereignis Teilnehmer in der globalen Richtlinie zu aktivieren:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $True 
```
## <a name="self-service-administration-tools"></a>Self-service-Verwaltungstools 
Obwohl Microsoft Office 365 Online Rechenzentren alle Steuerelemente direkt und verantwortlich für die Leistung des gesamten Systems ist, kann es nur einen Teil der Elemente steuern, die kombiniert werden, um den Gesamtnutzen für Office 365-Benutzer bereitzustellen. Organisationen selbst die Verantwortung für die Netzwerkverbindungen mit der Rechenzentren, die Kunden Fernnetz (WAN), und der Kunde lokale Netzwerke (LANs). Darüber hinaus sind für Benutzer Geräte und deren Konfiguration.Sie werden darüber hinaus verantwortlich für die Verwaltung der erforderliche Lizenzierung pro Benutzer für alle gewünschten Features, einschließlich, aber nicht beschränkt auf die Möglichkeit, diese Features für verwalten, solange der Benutzer Zugriff auf dieses Feature benötigt.

Kunden können die folgenden Tools verwenden, um eine Vielzahl von Teams live Ereignisse Aufgaben im Zusammenhang mit verwalten.
- [Microsoft Office 365 Administrationscenter](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft-Teams und Skype für Business Online Administrationscenter](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- Microsoft-Stream-Verwaltungskonsole
- [Windows PowerShell-Remotesitzungen](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?
- Wenn kommt es zu Windows PowerShell, geht es Verwalten von Benutzern und welche Benutzer zugelassen oder Aktionen nicht zulässig sind. Mit Windows PowerShell können Sie Office 365 und Skype verwalten, für die Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen müssen. Siehe folgende Themen, um Windows PowerShell zu verwenden:
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)

