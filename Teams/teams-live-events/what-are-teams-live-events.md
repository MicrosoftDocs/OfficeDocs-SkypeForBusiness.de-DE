---
title: Was sind Teams live Ereignisse?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Teams_ITAdmin_Help
ms.reviewer: tonysmit
search.appverid: MET150
description: Hier erfahren Sie, wie Live Ereignisse Benutzer Video- und große online Publikum in Microsoft-Teams, Yammer und Stream Microsoft Content übertragen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f985164385179c64c05fdadea1c6df5854583e3
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017945"
---
# <a name="what-are-teams-live-events"></a>Was sind Teams live Ereignisse?
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="overview"></a>Übersicht
Live Ereignisse in Microsoft 365 können Benutzer Video- und große online Publikum Content übertragen. Microsoft 365 live Ereignisse bringen live Videostreaming auf eine neue Ebene, Förderung der Verbindung während des gesamten Projekts Lebenszyklus mit Teilnehmer vor, während und nach live-Ereignissen. Sie können ein live-Ereignis erstellen, unabhängig von dessen Speicherort Ihrer Benutzergruppe, Team oder Community befindet sich mit Microsoft Stream, Microsoft-Teams, oder Yammer.  

Microsoft-Teams, bietet Chat-basierte Zusammenarbeit, Anrufe, Konferenzen und live-Ereignissen, Sie können erweitern Sie die Benutzergruppe Besprechungsliste. Microsoft-Teams live Ereignisse ist eine Erweiterung von Teams Besprechungen, die Benutzern ermöglichen, Video- und Meeting Inhalte an eine große online Benutzergruppe übertragen. Diese sind für die 1: n-Kommunikation vorgesehen, in denen der Host des Ereignisses wird die Interaktionen führende und die Teilnahme Benutzergruppe ist in erster Linie zum Anzeigen des Inhalts von Host gemeinsam genutzt werden. Die Teilnehmer können sehen Sie sich das live oder aufgezeichnete-Ereignis im Yammer, Teams und/oder Microsoft Stream und mit der Referenten mithilfe moderierte Q & A oder Yammer-Unterhaltung interagieren können. 

Ersetzen Sie Teams live Ereignisse gelten die nächste Version von Skype Besprechung übertragen und schließlich werden die Funktionen in Skype Besprechung übertragen. Während der public Preview-Version von Teams live-Ereignissen wird es weiterhin Skype Besprechung übertragen,-ohne Unterbrechung im Dienst für neue oder zukünftigen Ereignisse unterstützen. Jedoch wir empfehlen Ihnen, Teams live Ereignisse aller Bildschirmfreigabe Teilnehmeranzahl, einschließlich neue und interessante Features nutzen, um zu testen und Unterstützung für externe Hardware und Software Encoder. 

Also lasst uns loslegen. Betrachten Sie zuerst das folgende Diagramm, das zeigt, beteiligten Komponenten auf hohe Ebene in Microsoft 365 live Ereignisse und wie sie verbunden sind. 

![Teams live-Ereignisse](../media/teams-live-events.png)

## <a name="key-components"></a>Wichtige Komponenten
Sie können aus dem obigen Bild sehen, sind vier wichtige Komponenten, die mit Live Ereignisse in der Microsoft-Teams verwendet werden.

### <a name="scheduling"></a>Planung
Teams bietet die Möglichkeit für die Verwaltung von Organisatoren auf ein Ereignis mit der entsprechenden Teilnehmer Berechtigungen erstellen, Ereignis Teammitglieder festzulegen, wählen Sie Produktionsmethode und Teilnehmer einladen. Wenn das live-Ereignis innerhalb einer Gruppe Yammer erstellt wurde, werden die live-Ereignis Teilnehmer Yammer Unterhaltung verwenden für die Interaktion mit Personen in das Ereignis können. 

### <a name="production"></a>Produktion
Die live-Ereignisse in Microsoft 365 ein Spektrum der Produktionsszenarien unterstützen, schließen Sie ein Schnellstart-Ereignis mithilfe von Webcams oder externen Encoder Ereignisse mit dem Studio Qualität Equipment. Video Eingabe bildet die Grundlage für die Live-Ereignisse und kann aus einer einzelnen Webcam an eine professionelle video Multi-Kamera-Produktion variieren. Sie können diese Optionen je nach ihren Project-Anforderungen und Ihrem Budget auswählen. Es gibt zwei Methoden, um Ereignisse zu erzeugen:

- **Schnellstart Produktion**: die Schnellstart Produktion-Methode können Benutzer ihre live Ereignissen mithilfe von Teams Besprechungen zu erstellen. Diese Option eignet sich am besten und schnellste Option aus, wenn Sie die Audio- und Videogeräte automatisch verwenden möchten verbunden mit dem PC oder remote Referenten für das Ereignis Teilnahme einladen. Mit dieser Option können Benutzer auf einfache Weise ihre Webcams verwenden und Freigeben von ihren Bildschirm als Eingabe für das Ereignis. 


- **Externe Encoder Produktion**: externe Encoder zulassen, dass Benutzer ihre live Ereignisse direkt aus einer externen Hardware oder eine softwarebasierte Encoder mit [Microsoft Stream-Objekt](https://stream.microsoft.com)zu erstellen. Diese Option empfiehlt sich, wenn Sie bereits Studio Qualität Equipment (beispielsweise Media Mischern) verfügen, welche Unterstützung streaming an einen Dienst Real-Time Messaging Protocol (RTMP). Diese Art der Produktion wird normalerweise in großem Umfang Ereignisse wie executive Stadt Hallen – verwendet, in ein einzelner Datenstrom aus einem Media Mixer auf die Benutzergruppe gesendet wird. 

### <a name="streaming-platform"></a>Streaming-Plattform
Die live-Ereignis-streaming-Plattform besteht aus die folgenden Teile:

- **Azure Media-Dienste** [Azure Media-Dienste](https://docs.microsoft.com/azure/media-services/previous/) können Sie die Übertragung Qualität video streaming-Dienste größere Benutzergruppen auf heutigen am häufigsten verwendeten mobilen Geräten zu erreichen.   Media-Dienste verbessert Eingabehilfen, Verteilergruppen und Skalierbarkeit und können sie einfach und kostengünstige Stream von Inhalten für Ihre lokale oder weltweit Zielgruppe – alle beim Schützen Ihrer Inhalte.
- **Azure Content Delivery Network (CDN)**  Nachdem Ihre Stream live geschaltet wird, wird es über dem [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/)bereitgestellt. Azure Media-Dienste bietet integrierte CDN für streaming-Endpunkte. Dies ermöglicht die Datenströme weltweit mit keine Pufferung angezeigt werden.

### <a name="enterprise-content-delivery-network-ecdn"></a>Enterprise Content Delivery Network (eCDN)
Das Ziel des eCDN ist den Videoinhalt aus dem Internet und verteilen die Inhalte im gesamten Unternehmen ohne Beeinträchtigung der Leistung des Netzwerks. Eine der folgenden können certified Partner eCDN Sie um Ihr Netzwerk für Live Ereignisse frei, die in Ihrem Unternehmen zu optimieren:
    - Struktur
    - Kollective
    - Lernen

### <a name="attendee-experience"></a>Umgebung Teilnehmer 
Umgebung der Teilnehmer ist der wichtigste Aspekt der live Ereignisse, und es ist wichtig, dass die Teilnehmer im live-Ereignis teilnehmen können, ohne Probleme. Umgebung der Teilnehmer Azure Media Player verwendet und kann über den Desktop, Browser und Mobile (iOS Android). Office 365 bietet Yammer und Teams als zwei Zusammenarbeit Hubs und die Teilnehmer live Erfahrung in diese Tools für die Zusammenarbeit integriert ist. 

## <a name="planning-for-live-events"></a>Planen von live Ereignisse
Beim Planen der Teams live Ereignisse in Ihrer Erstellen von großen Besprechungen halten, gibt es mehrere Faktoren, die Sie berücksichtigen, bevor sie alle bis festgelegt wird gestartet müssen. 

### <a name="who-can-create-and-schedule-live-events"></a>Wer kann erstellen und planen live Ereignisse? 
Die folgenden erforderlichen Komponenten sind erforderlich für den Benutzer ein Teams live-Ereignis planen.

Hier werden die Lizenzen, die zugewiesen werden müssen:  
- Eine Lizenz für Office 365 Enterprise E1, E3 oder E5 oder eine Lizenz für Office 365 A3 oder A5. 
- Skype für Unternehmen, und eine Microsoft-Teams und Microsoft Stream-Lizenz.

Es ist wichtig, zu wissen, dass eine Office 365-Lizenz erforderlich ist, um ein live-Ereignis als authentifizierter Benutzer teilnehmen, aber dies hängt von der Produktionsmethode verwendet:

- **Für Quick Start Produktion**  Der Benutzer muss eine Microsoft-Teams Lizenz zugewiesen werden.
- **Für externe Encoder Produktion** Der Benutzer muss eine Microsoft-Stream-Lizenz zugewiesen werden.

Weitere Informationen zur Lizenzierung finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).

Der Benutzer benötigt:
- Planen von privaten Besprechung in Teams aktiviert (*der TeamsMeetingPolicy AllowPrivateMeetingScheduling - Parameter = True*).
- Live Ereignis Planung in Teams aktiviert (*der TeamsMeetingBroadcastPolicy AllowBroadcastScheduling - Parameter = True*).
- Berechtigungen zum Erstellen von live Ereignisse in Microsoft Stream (für [externe Encoder Produktion](#production)).

> [!IMPORTANT]
> Office 365 Gäste, Verbund- und anonyme Benutzer können nicht als Hersteller oder Referenten in Teams live Ereignisse eingeladen werden. Gast und Verbundbenutzer können jedoch als Live-Ereignis anonyme Teilnehmer beitreten. 
 
### <a name="who-can-watch-live-events"></a>Wer live Ereignisse überwachen können?

|**ATTENDEE Sichtbarkeit**           |**Schnellstart** |**Externe encoder**  |
|------------------------------|-------------|------------------|
|Öffentliche (anonyme Benutzer)      |  Ja        |  Nein              |
|Gast-Benutzer                   |  Nein         |  Nein              |
|Jede Person in einer verbundenen Unternehmen |  Nein         |  Nein              |
|Jeder in Unternehmen           |  Ja        |  Ja             |
|Spezifische Gruppen / für die Personensuche      |  Ja        |  Ja             |
 
### <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams live Ereignisse und Skype Besprechung übertragen
In der folgenden Tabelle werden wichtige Funktionen und Features in live Ereignisse und wie unterscheiden sich von Skype Besprechung übertragen angebotenen behandelt. 

|**Funktion**   |**Skype-Livekonferenzen** |**Teams live Ereignisse (Schnellstart)** |**Teams live Ereignisse (externe Encoder)** |
|---------|---------|---------|---------|
|Maximale Benutzergruppe Größe |10.000 Teilnehmer |10.000 Teilnehmer * |10.000 Teilnehmer * |
|Erstellung des Live-Ereignis |   Skype-Meeting Broadcast-Portal |Teams, Yammer über Teams | Teams, über den Teams, Stream Yammer |
|Benutzergruppe Engagements – Yammer |& #x 2714; |& #x 2714; (integrierte Experience) |& #x 2714; (integrierte Experience) |
|Benutzergruppe Engagements – moderiert f & A |& #x 2714;  |& #x 2714; |& #x 2714; |
|Hersteller-Client für Windows |& #x 2714; (Skype für Unternehmen) |& #x 2714; (Teams) |& #x 2714; (Stream-Objekt einbetten Teams über Stream) |
|Hersteller-Client auf einem Mac |X  | & #x 2714; (Teams) |& #x 2714; (Stream-Objekt einbetten Teams über Stream) |
|Teilnehmeranzahl in Producer-Benutzeroberfläche |X  |& #x 2714; (Teams) |& #x 2714; (Stream-Objekt einbetten Teams über Stream) |
|Ermöglicht es mehrere Referenten |& #x 2714; (Skype für Unternehmen) |& #x 2714; (Teams) |n/v  |
Ein Referent während der Besprechung einladen |& #x 2714; (Skype für Unternehmen) |X |n/v |
|Referent beitreten auf Webservern und Mobile |& #x 2714; (Skype für Unternehmen)  |X |n/v |
|Referenten – PSTN-Zugang |X |& #x 2714; (Teams) |n/v |
|Ein Bildschirm angezeigt |X |& #x 2714; (Teams) |n/v |
|Präsentieren Sie eine PowerPoint (PPT-Freigabe) |& #x 2714; |X (per Bildschirmfreigabe gemindert) |n/v |
|Cloud-basierten besprechungsaufzeichnung |& #x 2714; |& #x 2714; |& #x 2714; |
|Automatische veröffentlichen Aufzeichnung in Microsoft Stream-Objekt |X |X |& #x 2714; |
|Echtzeit Beschriftungen und Übersetzung |& #x 2714; |& #x 2714; (bald verfügbar) |X |
|Beschriftungen in Aufzeichnungen live-Ereignis |& #x 2714; |& #x 2714; (bald verfügbar) |& #x 2714; |
|ATTENDEE DVR-Steuerelemente (anhalten, Zurückspulen) |& #x 2714; |& #x 2714; |& #x 2714; |
|Partner eCDN Support |& #x 2714; (Struktur, Kollective, lernen) |& #x 2714; (Struktur, Kollective) |& #x 2714; (Struktur, Kollective, lernen) |
|Nach dem broadcast Anwesenheitsbericht für Hersteller |& #x 2714; |& #x 2714; (Feature Version) |X |
|Benutzergruppe Stimmung Analyse – Live Stimmabgabe & Umfragen |& #x 2714; (Microsoft Pulse) |X |X |

> [!IMPORTANT]
> Die Grenzwerte, die festgelegt werden können geändert werden.

### <a name="regional-availability"></a>Regionale Verfügbarkeit
Sie können Teams live Ereignisse auf der ganzen Welt mehrere Regionen verwenden. Die folgende Informationen zeigt Verfügbarkeit für Teammitglieder Ereignis und Teilnehmer. 

> [!IMPORTANT]
> Die Region für das Ereignis wird je nach der Organisator und der Office 365-Organisation automatisch ausgewählt.

**In diesen Regionen verfügbar**
- Amerikanischen Kontinent
- Europa/Afrika
- Asien-Pazifik
- Wechseln Sie lokale Kanada

**Ausschlüsse und Überlegungen**
- **Lokal wechseln:** Unitied Königreich (Großbritannien), Indien und andere Microsoft-Teams wechseln Sie lokal werden derzeit nicht unterstützt.
- **China:** Ereignis Teammitglieder und Teilnehmer ist nicht möglich Teams live Ereignisse verwendet werden, da Azure CDN nicht in China zugegriffen werden kann. Eine problemumgehung besteht darin, ein Unternehmen VPN-Verbindung verwenden, die über das Unternehmensnetzwerk des Kunden zu CDN verbundenen Client fungiert.

## <a name="setting-up-for-live-events"></a>Einrichten von für live Ereignisse
Beim Einrichten für live Ereignisse sind mehrere Schritte, die Sie durchführen müssen:

### <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Schritt 1: Richten Sie Ihres Netzwerks für live Ereignisse in der Microsoft-Teams ein
Die Schnellstart live Ereignisse müssen Sie zum [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/prepare-network).  

### <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
Sicherzustellen, dass der richtige Lizenz Zuordnungen für [Erstellen und Planen Sie live Ereignisse zu können?](#who-can-create-and-schedule-live-events) und [können, die live Ereignisse überwachen?](#who-can-watch-live-events).

### <a name="step-3-enable-live-event-scheduling-for-users"></a>Schritt 3: Aktivieren von live-Ereignis planen für Benutzer
Planen von Live-Ereignis ist standardmäßig aktiviert, für Teams Benutzer, aber Sie möchten Benutzer externe Encoder Ereignisse planen, sind zusätzliche Schritte, die Sie durchführen müssen.

#### <a name="for-quick-start-events"></a>Schnellstart-Ereignisse
Verwenden Sie die Einstellung *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in PowerShell Teams können Sie steuern, ob der Benutzer live Ereignisse in Teams oder nicht erstellen kann. Weitere Informationen finden Sie Informationen zum Verwalten von TeamsMeetingBroadcastPolicy [hier](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Wenn Sie eine benutzerdefinierte Richtlinie an, die Benutzern zugewiesen zugewiesen haben, erhalten die Benutzer die *globale* Richtlinie ein, die Aufzeichnung, die in der Standardeinstellung aktiviert hat.

Stellen Sie sicher, dass *AllowBroadcastScheduling* -Parameter auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Weisen Sie den Benutzer die *globale* Richtlinie, ausführen:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

##### <a name="user-scenarios"></a>Benutzerszenarien
**Sollen alle Benutzer in Ihrem Unternehmen live Ereignisse erstellen können.**

Wenn Benutzer die *globalen* Richtlinie zugewiesen sind, ausführen, und stellen Sie sicher, *AllowBroadcastScheduling* * auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Wenn der Benutzer eine Richtlinie als die *globale* Richtlinie zugewiesen sind, führen Sie folgenden Befehl ein, und stellen Sie sicher, dass *- AllowBroadcastScheduling* auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**Live-Ereignis Planung in Ihrer Organisation 100 % deaktiviert werden soll.**

Führen Sie deaktivieren broadcast planen:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Die *globale* Richtlinie, führen weisen Sie alle Benutzer in Ihrer Organisation zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Sie möchten eine große Anzahl von Benutzern live Ereignisse erstellen können, aber verhindern, dass eine Gruppe von Benutzern erstellen möchten.**

Weisen Sie die *globale* Richtlinie mit dem **Grant-CsTeamsMeetingBroadcastPolicy** für einige Benutzer (, die Sie aktivieren möchten), aber zuerst führen Sie folgenden Befehl, und stellen Sie sicher, dass *AllowBroadcastScheduling* auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Weisen Sie mindestens ein Benutzer die *globale* Richtlinie, ausführen:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Erstellen und Zuweisen einer Richtlinie für die Deaktivierung planen, mit dem Cmdlet **Grant-CsTeamsMeetingBroadcastPolicy** an andere Benutzer ein (deaktiviert). 

Erstellen Sie die neue Richtlinie deaktiviert, ausführen:
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
Deaktivieren Sie planen, ausführen:
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Sie live Ereignisse für eine große Anzahl von Benutzern deaktiviert werden soll, jedoch eine Gruppe von Benutzern, deren Erstellung zu zulassen möchten.**

Führen Sie deaktivieren broadcast planen:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Die *globale* Richtlinie, führen Sie anschließend weisen Sie diese Benutzer zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Erstellen und Zuweisen einer Richtlinie für die Aktivierung planen, ausführen:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Führen Sie Zeitplan aktivieren:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

#### <a name="for-external-encoder-events"></a>Für externe Encoder-Ereignisse
Sie müssen Folgendes ein, um die Live-Ereignis Zeitplan für diesen Benutzer aktivieren.

##### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>Schritt 1: Aktivieren von Microsoft-Stream für Benutzer in Ihrer Organisation **
Microsoft-Stream steht als Teil von Office 365-Abonnements zu auswählbaren oder als eigenständigen Dienst. Einzelheiten finden Sie unter [Stream Lizenzierung Overview](https://docs.microsoft.com/stream/license-overview) .

> ! [Hinweis] Microsoft-Stream ist nicht in Business Essentials oder Business Premium-Plänen enthalten.  

Erfahren Sie mehr dazu, wie Sie [Lizenzen für Benutzer in Office 365 zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , damit Benutzer Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft-Stream für die Benutzer nicht ausgeschlossen wird, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization)definiert.

##### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Schritt 2: Stellen Sie sicher, dass Benutzer über Berechtigungen zum Erstellen live-Ereignis in Microsoft Stream ** verfügen
In der Standardeinstellung können Administratoren externe Encoder live Ereignisse erstellen. Microsoft-Stream-Administrator können in Stream-Objekt [für die Erstellung des live-Ereignis weitere Benutzer aktivieren](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) .  

##### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Schritt 3: Stellen Sie sicher, die Organisatoren die Unternehmensrichtlinie festlegen, indem Stream Admin ** zugestimmt haben live-Ereignis
Wenn ein Microsoft-Stream-Administrator [eine Unternehmensrichtlinie Richtlinien einrichten hat](https://docs.microsoft.com/stream/company-policy-and-consent) und Mitarbeiter dieser Richtlinie zu akzeptieren erfordert, bevor das Speichern von Inhalten, klicken Sie dann müssen Benutzer vor dem Erstellen einer live-Ereignis (mit der externen Encoder Produktion) in Microsoft-Teams. Sicherstellen Sie bevor Sie Einführung das Feature live Ereignisse in der Organisation, dass Benutzer, die diese live Ereignisse erstellen werden die Richtlinie zugestimmt haben. 

### <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Schritt 4: Einrichten von eCDN-Anbieter für live Ereignisse in der Microsoft-Teams 
Wiedergabe von Videos live-Ereignis verwendet adaptive Bitrate (ABR) streaming, aber es ist eine Unicast-Stream, was bedeutet, dass jeder Viewer eigene Videostream aus dem Internet abrufen ist. Für live Ereignisse oder Videos an große Teile Ihrer Organisation gesendet kann sehr viel Internetbandbreite Identitätsdaten durch Viewer handeln. Für Organisationen, die diesen Internet-Datenverkehr für live Ereignisse reduzieren möchten, vertrauenswürdige live Ereignisse, die von Microsoft Solutions integriert sind video Delivery Partner, anbietet Software Netzwerke (SDNs) oder Enterprise Content Delivery Networks (eCDNs) definiert. Diese SDN / eCDN Plattformen können Organisationen zum Optimieren der Netzwerkbandbreite ohne Beeinträchtigung Endbenutzer Erfahrungen anzeigen. Unsere Partner helfen, eine skalierbare und effiziente video Verteilung über Ihr Unternehmensnetzwerk zu aktivieren.

**Purchase & Setup Ihrer Lösung außerhalb von Microsoft-Teams,** Hier erhalten Sie Hilfe Experten video Übermittlung durch die Nutzung von Microsoft vertrauenswürdigen video Delivery Partner skalieren. Bevor Sie einen video Delivery-Anbieter mit Microsoft-Teams verwendet werden, müssen Sie erwerben und einrichten die Lösung SDN/eCDN äußeren und getrennt von Microsoft-Teams, aktivieren können.

SDN/eCDN Folgendes können bereits integriert werden und Setup mit Microsoft-Streams verwendet werden.

- **Streaming Struktur** bietet eine einfache und leistungsstarke Lösung für die Live- und on-Demand Enterprise video Verteilung. Struktur ist eine softwarebasierte Lösung, die erfordert keine zusätzliche Hardware oder Bandbreite und auf sichere Weise Tausende von gleichzeitigen video Viewer ohne Auswirkung auf das Netzwerk zu aktivieren. Für Kunden, die zum Verständnis, dass das Video Auswirkung in ihrem Netzwerk vor dem Kauf einer Lösung SDN/eCDN hat bietet Streaming Struktur auch eine browserbasierte Analytics Lösung zur Microsoft-Kunden. [Weitere Informationen](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
- **Kollective** ist eine Cloud-basierten, intelligente Peers Verteilung Plattform, die nutzt die vorhandene Netzwerkinfrastruktur zum Übermitteln von Inhalten, in vielen Formen, (live Videostreams, bei Bedarf Video, Softwareupdates, Sicherheitspatches usw.), schneller zuverlässig und mit weniger Bandbreite. Unsere sichere Plattform ist vertrauenswürdig, von der weltweit größten Finanzinstituten und mit keine zusätzliche Hardware, Installation und Wartung einfach sind. [Weitere Informationen](http://www.kollective.com)
 
- **Lernen OmniCache** ermöglicht die Verteilung der nächsten Generation Netzwerk und sorgt für nahtlose Bereitstellung von Videoinhalten auf globale WANs, Netzwerkbandbreite zu optimieren und unterstützen erfolgreiches Ereignis live Übertragungen und on-Demand Ereignis Hersteller helfen Streaming. Die Unterstützung für lernen OmniCache Schnellstart live Ereignisse wird in Kürze bereitgestellt.  [Weitere Informationen](http://www.ramp.com) 
 
> [!NOTE] 
> Ihre Lösung gewählten eCDN unterliegt den ausgewählten **3. Anbieters Bedingungen Service und der Datenschutzrichtlinie**, Ihre Verwendung des Anbieters eCDN Lösung, welche wird steuert. Ihre Verwendung des Anbieters eCDN Lösung werden nicht unter der Microsoft Volume licensing Begriffe oder Online Services-Ausdrücken. Wenn Sie nicht den **3. Anbieters Begriffe**zustimmen, aktivieren Sie dann nicht eCDN Lösung im Microsoft-Teams. 

**Richten Sie ein eCDN für "Schnellstart" live Ereignisse** Sie können eCDN-Anbieter für live Ereignisse in Microsoft-Teams von PowerShell konfigurieren. 

> [!NOTE] 
> Ein einzelnes eCDN Anbieter kann für Ihre Organisation konfiguriert werden. 

***Struktur*** [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) -PowerShell-Cmdlets können Sie eCDN Anbieter konfigurieren. Erhalten Sie zuerst die Lizenz-ID und API-Vorlagen-URL aus der Struktur Kontakt führen Sie die folgenden:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective*** [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) -PowerShell-Cmdlets können Sie eCDN Anbieter konfigurieren. Zunächst erhalten Sie das Token API und die URL der API-Vorlage aus dem Kollective Kontakt, und führen Sie folgenden Befehl:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Richten Sie ein eCDN für "Externe Encoder" live-Ereignisse** 

Wenn Sie planen, live Ereignisse erstellen, die externe Encoder verwenden, müssen Sie ebenfalls [Konfigurieren des Anbieters eCDN mit Microsoft-Stream](https://docs.microsoft.com/stream/network-caching) . 

## <a name="configure-live-events"></a>Konfigurieren des live-Ereignisse

### <a name="set-up-event-support-link"></a>Einrichten von Ereignis Support link
Dies ist die Verknüpfung, die an die Teilnehmer live-Ereignis angezeigt werden. 

Führen Sie in Windows PowerShell folgenden Befehl:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
### <a name="configure-attendee-visibility-options"></a>Konfigurieren Sie die Sichtbarkeitsoptionen für Teilnehmer
Live-Ereignis Organisatoren Ereignisse mit entsprechenden Attendee Sichtbarkeit erstellen können.

|**Werte**  |**Verhalten**  |
|---------|---------|
|Jeder     |Der Benutzer hat eine Option zum Erstellen von live Ereignisse mit dem folgenden Attendee Sichtbarkeit: Public, jede Person in Unternehmen und bestimmte Personen. |
|EveryoneInCompany     |Der Benutzer hat eine Option zum Erstellen von live Ereignisse mit dem folgenden Attendee Sichtbarkeit: alle Benutzer im Unternehmen und bestimmte Personen. Der Benutzer kann nicht live Ereignisse erstellen, die durch anonyme Benutzer behandelt werden kann.|
|InvitedUsers |Der Benutzer kann nur live Ereignisse erstellen, die auf bestimmte Personen beschränkt sind durch den Organisator des Ereignisses eingegeben wurde. Der Benutzer kann nicht mit öffentlichen und alle Benutzer im Unternehmen Authentifizierung live Ereignisse erstellen. |

Verwenden Sie die Einstellung BroadcastAttendeeVisibility in TeamsMeetingBroadcastPolicy in PowerShell können Sie steuern, ob die Benutzer broadcast Ereignisse planen können, die durch anonyme Teilnehmer beobachtet werden kann. 

Es sei denn, die Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer globale Richtlinie ein, die standardmäßig auf EveryoneInCompany festgelegt hat. 
 
Führen Sie den folgenden damit anonyme Ereignisse in der globalen Richtlinie erstellen, die Benutzer können in Windows PowerShell aus:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>Konfigurieren Sie die Aufzeichnungsoptionen
> [!NOTE]
> Diese Option ist für Ereignisse, die der Schnellstart Produktion-nur Methode anwendbar.

Dies ermöglicht Administratoren zur Steuerelement an, ob die live Ereignisse immer noch nie aufgezeichnet, aufgezeichnet werden, oder der Organisator des Ereignisses zum Aufzeichnen des Ereignisses oder nicht entscheiden kann.  

|**Werte**  |**Verhalten**  |
|---------|---------|
|Immer aktiviert |Die von diesem Benutzer organisierte live Ereignisse werden immer aufgezeichnet. Der Benutzer keine Option außer Kraft gesetzt. Wenn das live Ereignis aufgezeichnet wird, die Mitglieder des Teams können die Aufzeichnung nach dem Ereignis herunterzuladen und die Teilnehmer können sehen Sie sich das Ereignis nach Abschluss des Ereignisses. |
|AlwaysDisabled |Die von diesem Benutzer organisierte live Ereignisse werden nie aufgezeichnet. Der Benutzer keine Option außer Kraft gesetzt. Wenn das live Ereignis aufgezeichnet wird, wird keine Aufzeichnung für die Mitglieder des Teams erstellt, und die Teilnehmer können nicht sehen Sie sich das Ereignis nach über ist. |
|UserOverride |Benutzer kann entscheiden, ob das live-Ereignis, damit eine Aufzeichnungsdatei für die Mitglieder des Teams erstellt werden kann und Teilnehmer können sehen Sie sich das Ereignis nach Abschluss des Ereignisses aufgezeichnet wird. |

Verwenden Sie die Einstellung *BroadcastRecordingMode* in **TeamsMeetingBroadcastPolicy** in PowerShell Steuerelement Aufzeichnungsoptionen live Ereignisse vom Organisator live-Ereignis erstellt.

Führen Sie in Windows PowerShell das folgende Cmdlet, um Aufzeichnungsmodus in der globalen Richtlinie zu aktualisieren:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Konfigurieren von Real-Time Lautschrift und Übersetzung in Teams live-Ereignisse (bald verfügbar)
> [!NOTE]
> Diese Option ist für Ereignisse, die der Schnellstart Produktion-nur Methode anwendbar.

Dadurch können live-Ereignis Organisatoren, Real-Time Beschriftungen und Übersetzung für den Teilnehmern live-Ereignis zu aktivieren. 

Verwenden Sie die Einstellung *AllowBroadcastTranscription* in **TeamsMeetingBroadcastPolicy** in PowerShell Kontrolle, ob die Teilnehmer live-Ereignis Umsetzung und Übersetzung finden Sie unter können. Erfahren Sie mehr über das Verwalten von **TeamsMeetingBroadcastPolicy** mit Office 365 PowerShell hier.  

Es sei denn, die Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer globale Richtlinie ein, die Umsetzung und Übersetzung standardmäßig deaktiviert hat.

Führen Sie in Windows PowerShell das folgende Cmdlet, um die Umsetzung und eine Übersetzung auf Ereignis Teilnehmer in der globalen Richtlinie zu aktivieren:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
### <a name="administrative-tools"></a>Verwaltungstools 
Obwohl Microsoft Office 365 Online Rechenzentren alle Steuerelemente direkt und verantwortlich für die Leistung des gesamten Systems ist, kann es nur einen Teil der Elemente steuern, die kombiniert werden, um den Gesamtnutzen für Office 365-Benutzer bereitzustellen. Organisationen selbst die Verantwortung für die Netzwerkverbindungen mit der Rechenzentren, die Kunden Fernnetz (WAN), und der Kunde lokale Netzwerke (LANs). Darüber hinaus sind für Benutzer Geräte und deren Konfiguration.Sie werden darüber hinaus verantwortlich für die Verwaltung der erforderliche Lizenzierung pro Benutzer für alle gewünschten Features, einschließlich, aber nicht beschränkt auf die Möglichkeit, diese Features für verwalten, solange der Benutzer Zugriff auf dieses Feature benötigt.

Kunden können die folgenden Tools verwenden, um eine Vielzahl von Teams live Ereignisse Aufgaben im Zusammenhang mit verwalten.
- [Microsoft Office 365 Administrationscenter](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft-Teams und Skype für Business Online Administrationscenter](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Microsoft-Stream-Verwaltungskonsole](https://stream.microsoft.com)
- [Windows PowerShell-Remotesitzungen](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?
Wenn es auf Windows PowerShell, es darum geht alle Informationen zum Verwalten von Benutzern und welche Benutzer zulässig sind oder nicht durchgeführt werden darf. Mit Windows PowerShell können Sie Office 365 und Skype verwalten, für die Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen müssen. Siehe folgende Themen, um Windows PowerShell zu verwenden:
 - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
 - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

### <a name="related-topics"></a>Verwandte Themen: 
- [Ereignisse über Microsoft 365 in Yammer, Microsoft-Teams und Stream Microsoft Live](https://docs.microsoft.com/stream/live-event-m365)
- [Live-Ereignisse im Microsoft-Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Live Ereignisse in Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Live-Ereignisse im Microsoft-Stream](https://docs.microsoft.com/stream/live-event-overview)
