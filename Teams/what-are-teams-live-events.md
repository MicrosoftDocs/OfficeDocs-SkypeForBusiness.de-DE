---
title: Was sind Teams live Ereignisse?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviwer: tonysmit
description: Hier erfahren Sie, wie Live Ereignisse Benutzer Video- und große online Publikum in Microsoft-Teams, Yammer und Stream Microsoft Content übertragen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b545f0b151c9d23d22f165c475aa972cc9f89ec4
ms.sourcegitcommit: 905ba61de9622dd485ff375fa75bb0d76bac0b55
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "22196099"
---
# <a name="what-are-teams-live-events"></a>Was sind Teams live Ereignisse?
> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview"></a>Übersicht
Live Ereignisse in Microsoft 365 können Benutzer Video- und große online Publikum Content übertragen. Microsoft 365 live Ereignisse bringen live Videostreaming auf eine neue Ebene, Förderung der Verbindung während des gesamten Projekts Lebenszyklus mit Teilnehmer vor, während und nach live-Ereignissen. Sie können ein live-Ereignis erstellen, unabhängig von dessen Speicherort Ihrer Benutzergruppe, Team oder Community befindet sich mit Microsoft Stream, Microsoft-Teams, oder Yammer.  

Microsoft-Teams, bietet Chat-basierte Zusammenarbeit, aufrufen, Besprechungen und mit live Ereignisse können Sie die Benutzergruppe Besprechungsliste erweitern. Microsoft-Teams live Ereignisse ist eine Erweiterung von Teams Besprechungen, die Benutzern ermöglichen, Video- und Meeting Inhalte an eine große online Benutzergruppe übertragen. Diese sind für die 1: n-Kommunikation vorgesehen, in denen der Host des Ereignisses wird die Interaktionen führende und die Teilnahme Benutzergruppe ist in erster Linie zum Anzeigen des Inhalts von Host gemeinsam genutzt werden. Die Teilnehmer können das live oder aufgezeichnete-Ereignis im Yammer, Teams und/oder Microsoft Stream Video und können mit dem Referenten über moderierte f & A interagieren oder Yammer Unterhaltung. 

Ersetzen Sie Teams live Ereignisse gilt die nächste Version von Skype Besprechung übertragen und schließlich wird die Funktionen in Skype Besprechung übertragen. Für die public Preview-Version von live-Ereignissen weiterhin Microsoft Skype Besprechung übertragen, ohne Unterbrechung im Dienst für neue oder zukünftigen Ereignisse unterstützen. Wir empfehlen Ihnen, live Ereignisse in Teams Bildschirmfreigabe, einschließlich der neuen Features nutzen Teilnehmeranzahl, testen und Unterstützung für externe Hardware und Software Encoder. 

Im folgende Diagramm werden die Komponenten auf hohe Ebene zum Microsoft 365 live Ereignisse gezeigt. 

![Teams live-Ereignisse](media/teams-live-events.png)

## <a name="key-components"></a>Wichtige Komponenten
Es gibt mehrere wichtige Komponenten, die mit Live Ereignisse verwendet werden.

### <a name="scheduling"></a>Planung
Teams bietet die Möglichkeit für die Verwaltung von Organisatoren auf ein Ereignis mit der entsprechenden Teilnehmer Berechtigungen erstellen, Ereignis Teammitglieder festzulegen, wählen Sie Produktionsmethode und Teilnehmer einladen. Wenn das live-Ereignis innerhalb einer Gruppe Yammer erstellt wurde, werden die Teilnehmer live-Ereignis Yammer Unterhaltung für die Interaktion mit dem Ereignis Team verwenden können. 

### <a name="production"></a>Produktion
Die live-Ereignisse in Microsoft 365 ein Spektrum der Produktionsszenarien unterstützen, schließen Sie ein Schnellstart-Ereignis mithilfe von Webcams oder externen Encoder Ereignisse mit dem Studio Qualität Equipment. Video Eingabe bildet die Grundlage für die live-Ereignisse und kann aus einer einzelnen Webcam an eine professionelle video Multi-Kamera-Produktion variieren. Kunden können diese Optionen je nach ihren Project-Anforderungen und Ihrem Budget auswählen. Es gibt zwei Methoden, um Ereignisse zu erzeugen:

- **Schnellstart**: die Schnellstart-Methode können Benutzer ihre live Ereignissen mithilfe von Teams Besprechungen zu erstellen. Diese Option ist am besten, wenn Sie die Audiodaten verwenden möchten, und Videogeräte an den PC angeschlossenes und/oder remote Referenten einladen / Diskussionsteilnehmer für das Ereignis beteiligt sind. Mit dieser Option können Benutzer auf einfache Weise verwenden, deren Webcams und ihren Bildschirm als Eingabe für die Übertragung freigeben. 

- **Externe Encoder**: externe Encoder zulassen, dass Benutzer ihre live Ereignisse direkt aus einer externen Hardware oder softwarebasierte Encoder mit Microsoft Stream zu erstellen. Diese Option empfiehlt sich, wenn Sie bereits Studio Qualität Equipment (z. B. Media Mischern) verfügen, welche Unterstützung streaming an einen RTMP-Dienst. Diese Option wird im großen Maßstab Fälle wie executive Stadt Hallen – in der Regel verwendet, in ein einzelner Datenstrom aus einem Media Mixer auf die Benutzergruppe übertragen wird. 

### <a name="streaming-platform"></a>Streaming-Plattform
Die live-Ereignis-streaming-Plattform besteht aus die folgenden Teile:

- **Azure Media-Dienste** [Azure Media-Dienste](https://docs.microsoft.com/en-us/azure/media-services/previous/) können Sie die Übertragung Qualität video streaming-Dienste größere Benutzergruppen auf heutigen am häufigsten verwendeten mobilen Geräten zu erreichen.   Media-Dienste verbessert Eingabehilfen, Verteilergruppen und Skalierbarkeit und können sie einfach und kostengünstige Stream von Inhalten für Ihre lokale und weltweit Zielgruppe – alle beim Schützen Ihrer Inhalte.
- **Azure Content Delivery Network (CDN)**  Nachdem Ihre Stream live geschaltet wird, wird es über dem [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/en-us/azure/cdn/)bereitgestellt. Azure Media-Dienste bietet integrierte CDN für streaming-Endpunkte. Dies ermöglicht die Datenströme weltweit mit keine Pufferung angezeigt werden.
- **Enterprise Content Delivery Network (eCDN)**  Das Ziel des eCDN ist den Videoinhalt aus dem Internet und verteilen die Inhalte im gesamten Unternehmen ohne Beeinträchtigung der Leistung des Netzwerks. Die folgenden certified Partner können Sie Ihr Netzwerk für Live Ereignisse optimieren:
    - Struktur
    - Kollective
    - Lernen
- **Erleben Sie die Teilnehmer**  Umgebung der Teilnehmer ist der wichtigste Aspekt der live Ereignisse, und es ist wichtig, dass die Teilnehmer im live-Ereignis ohne Probleme teilnehmen können. Umgebung der Teilnehmer Azure Media Player verwendet und kann über den Desktop, Browser und Mobile (iOS Android). Office 365 bietet Yammer und Teams als zwei Zusammenarbeit Hubs und die Teilnehmer live Erfahrung in diese Tools für die Zusammenarbeit integriert ist. Die externe Encoder-basierten live-Ereignisse können auch von Teilnehmern in der **Microsoft-Stream Portal**zugegriffen werden.

## <a name="planning-for-live-events"></a>Planen von live Ereignisse
Wenn Sie bei der Planung auf halten von großen Besprechungen mithilfe von Teams live Ereignissen sind verschiedene Faktoren, die Sie berücksichtigen, bevor sie alle bis festlegen müssen. 

### <a name="who-can-create-and-schedule-live-events"></a>Wer kann erstellen und planen live Ereignisse?
Die folgenden erforderlichen Komponenten sind erforderlich für den Benutzer ein live-Ereignis in der Vorschau Zeitrahmen planen:  
- Benutzer verfügt über eine Lizenz für Office 365 Enterprise E3 oder E5 zugewiesen wurde. 
- Für Microsoft-Teams, Skype für Business Online und Microsoft Stream ist Benutzer aktiviert.
- Benutzer für die Planung von privaten Besprechung in Teams aktiviert ist (TeamsMeetingPolicy AllowPrivateMeetingScheduling auf True festgelegt ist).
- Benutzer für die Planung von live-Ereignis in Teams aktiviert ist (TeamsMeetingBroadcastPolicy AllowBroadcastScheduling auf True festgelegt ist).
- Benutzer verfügt über Berechtigungen zum Erstellen von live Ereignisse in Microsoft Stream (für externe Encoder Produktion).

> [!NOTE]
> Office 365 Gäste, Verbund- und anonyme Benutzer können nicht als Hersteller oder Referenten in Teams live Ereignisse eingeladen werden. 
 
### <a name="who-can-watch-live-events"></a>Wer live Ereignisse überwachen können?
|**ATTENDEE Sichtbarkeit**           |**Schnellstart** |**Externe encoder**  |
|------------------------------|-------------|------------------|
|Öffentliche (anonyme Benutzer)      |  Ja        |  Nein              |
|Gast Benutzer *                   |  Nein         |  Nein              |
|Jede Person in einer verbundenen Unternehmen * |  Nein         |  Nein              |
|Jeder in Unternehmen           |  Ja        |  Ja             |
|Spezifische Gruppen / für die Personensuche      |  Ja        |  Ja             |

*Gast und Verbundbenutzer können als live-Ereignis anonyme Teilnehmer beitreten.*

Es ist wichtig, zu wissen, dass eine Office 365-Lizenz erforderlich ist, um ein live-Ereignis als authentifizierter Benutzer teilnehmen, aber dies hängt von der Produktionsmethode verwendet:

- **Für Quick Start Produktion**  Der Benutzer muss eine Microsoft-Teams Lizenz zugewiesen werden.
- **Für externe Encoder Produktion** Der Benutzer muss eine Microsoft-Stream-Lizenz zugewiesen werden.
 
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

**Ausschlüsse und Überlegungen**
- **Lokal wechseln:** Unitied Königreich (Großbritannien), Indien und andere Microsoft-Teams wechseln Sie lokal werden derzeit nicht unterstützt.
- **Wechseln Sie lokal - Kanada:** Während dieser Preview bietet Ihnen Ereignisse erstellen kann, aber ihre Daten werden in Nordamerika Region verwaltet werden.
- **China:** Ereignis Teammitglieder und Teilnehmer ist nicht möglich Teams live Ereignisse verwendet werden, da Azure CDN nicht in China zugegriffen werden kann. Eine problemumgehung besteht darin, ein Unternehmen VPN-Verbindung verwenden, die über das Unternehmensnetzwerk des Kunden zu CDN verbundenen Client fungiert.

## <a name="setting-up-for-live-events"></a>Einrichten von für live Ereignisse
Beim Einrichten für live Ereignisse sind mehrere Schritte, die Sie durchführen müssen:

#### <a name="step-1-set-up-skype-for-business-online"></a>Schritt 1: Einrichten von Skype für Business Online
Wenn Sie dies noch nicht getan haben richten Sie [Skype für Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online?redirectSourcePath=%252fen-us%252farticle%252fset-up-skype-for-business-online-40296968-e779-4259-980b-c2de1c044c6e) für Ihre Organisation ein.

#### <a name="step-2-setting-up-a-ecdn-provider"></a>Schritt 2: Einrichten eines eCDN-Anbieters
Wenn Sie Teilnehmer beitreten von innerhalb des Unternehmensnetzwerks haben, sollten Sie Onboarding und [Einrichten eines Anbieters für die von Microsoft empfohlenen eCDN](#set-up-ecdn-provider-for-teams-live-events) Bandbreite in Ihrem Netzwerk zu optimieren. 

#### <a name="step-3-getting-licenses"></a>Schritt 3: Abrufen von Lizenzen
Stellen Sie sicher, dass Sie die richtige Lizenz Zuordnungen für [Benutzer können live Ereignisse erstellen](#who-can-create-live-events) und [können, die live Ereignisse Video](#who-can-watch-live-event)verfügen. 

#### <a name="step-4-enable-live-event-scheduling"></a>Schritt 4: Aktivieren von live-Ereignis planen
Für die Benutzer, die live Ereignisse in Ihrem Unternehmen erstellen können, sollten [live-Ereignis Zeitplan aktivieren](#enable-live-event-scheduling-for-the-user) . Dies ist erforderlich für Schnellstart & externe Encoder Ereignisse.

#### <a name="step-5-enable-users-for-microsoft-stream"></a>Schritt 5: Aktivieren von Benutzern für Microsoft-Stream
Für externe Encoder Ereignisse, [aktivieren Benutzer für die Erstellung von live Ereignisse Stream Verwaltungsportal von Microsoft](#enable-microsoft-stream-for-users-in-the-organization).  

#### <a name="step-6-set-up-your-network-for-live-events-in-microsoft-teams"></a>Schritt 6: Richten Sie Ihr Netzwerk für live Ereignisse in der Microsoft-Teams
Die Schnellstart live Ereignisse müssen Sie zum [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft-Teams](https://docs.microsoft.com/en-us/microsoftteams/prepare-network).  

#### <a name="step-7-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Schritt 7: Einrichten von eCDN-Anbieter für live Ereignisse in der Microsoft-Teams 
Wiedergabe von Videos live-Ereignis verwendet adaptive Bitrate (ABR) streaming, aber es ist eine Unicast-Stream, was bedeutet, dass jeder Viewer eigene Videostream aus dem Internet abrufen ist. Für live Ereignisse oder Videos an große Teile Ihrer Organisation gesendet kann sehr viel Internetbandbreite Identitätsdaten durch Viewer handeln. Für Organisationen, die diesen Internet-Datenverkehr für live Ereignisse reduzieren möchten, vertrauenswürdige live Ereignisse, die von Microsoft Solutions integriert sind video Delivery Partner, anbietet Software Netzwerke (SDNs) oder Enterprise Content Delivery Networks (eCDNs) definiert. Diese SDN / eCDN Plattformen können Organisationen zum Optimieren der Netzwerkbandbreite ohne Beeinträchtigung Endbenutzer Erfahrungen anzeigen. Unsere Partner helfen, eine skalierbare und effiziente video Verteilung über Ihr Unternehmensnetzwerk zu aktivieren.

**Purchase & Setup Ihrer Lösung außerhalb von Microsoft-Teams,** Hier erhalten Sie Hilfe Experten video Übermittlung durch die Nutzung von Microsoft vertrauenswürdigen video Delivery Partner skalieren. Bevor Sie einen video Delivery-Anbieter mit Microsoft-Teams verwendet werden, müssen Sie erwerben und einrichten die Lösung SDN/eCDN äußeren und getrennt von Microsoft-Teams, aktivieren können.

SDN/eCDN Folgendes können bereits integriert werden und Setup mit Microsoft-Streams verwendet werden.

- **Streaming Struktur** bietet eine einfache und leistungsstarke Lösung für die Live- und on-Demand Enterprise video Verteilung. Struktur ist eine softwarebasierte Lösung, die erfordert keine zusätzliche Hardware oder Bandbreite und auf sichere Weise Tausende von gleichzeitigen video Viewer ohne Auswirkung auf das Netzwerk zu aktivieren. Für Kunden, die zum Verständnis, dass das Video Auswirkung in ihrem Netzwerk vor dem Kauf einer Lösung SDN/eCDN hat bietet Streaming Struktur auch eine browserbasierte Analytics Lösung zur Microsoft-Kunden. [Weitere Informationen](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
- **Kollective** ist eine Cloud-basierten, intelligente Peers Verteilung Plattform, die nutzt die vorhandene Netzwerkinfrastruktur zum Übermitteln von Inhalten, in vielen Formen, (live Videostreams, bei Bedarf Video, Softwareupdates, Sicherheitspatches usw.), schneller zuverlässig und mit weniger Bandbreite. Unsere sichere Plattform ist vertrauenswürdig, von der weltweit größten Finanzinstituten und mit keine zusätzliche Hardware, Installation und Wartung einfach sind. [Weitere Informationen](http://www.kollective.com)
 
- **Lernen OmniCache** ermöglicht die Verteilung der nächsten Generation Netzwerk und sorgt für nahtlose Bereitstellung von Videoinhalten auf globale WANs, Netzwerkbandbreite zu optimieren und unterstützen erfolgreiches Ereignis live Übertragungen und on-Demand Ereignis Hersteller helfen Streaming. Die Unterstützung für lernen OmniCache Schnellstart live Ereignisse wird in Kürze bereitgestellt.  [Weitere Informationen](http://www.ramp.com) 
 
> [!NOTE] 
> Ihre Lösung gewählten eCDN unterliegt den ausgewählten [3. Anbieters Bedingungen Service und der Datenschutzrichtlinie](), die Ihre Verwendung des Anbieters eCDN Lösung gesteuert wird. Ihre Verwendung des Anbieters eCDN Lösung werden nicht unter der Microsoft Volume licensing Begriffe oder Online Services-Ausdrücken. Wenn Sie nicht den [3. Anbieters Begriffe]()zustimmen, aktivieren Sie dann nicht eCDN Lösung im Microsoft-Teams. 

**Richten Sie ein eCDN für "Schnellstart" live Ereignisse** Sie können eCDN-Anbieter für live Ereignisse in Microsoft-Teams von PowerShell konfigurieren. 

> [!NOTE] 
> Ein einzelnes eCDN Anbieter kann für Ihre Organisation konfiguriert werden. 

**Richten Sie einen Anbieter für eCDN Struktur** [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) -PowerShell-Cmdlets können Sie eCDN Anbieter konfigurieren. Erhalten Sie zuerst die Lizenz-ID und API-Vorlagen-URL aus der Struktur Kontakt führen Sie die folgenden:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Richten Sie einen Kollective eCDN-Anbieter** [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) -PowerShell-Cmdlets können Sie eCDN Anbieter konfigurieren. Zunächst erhalten Sie das Token API und die URL der API-Vorlage aus dem Kollective Kontakt, und führen Sie folgenden Befehl:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Richten Sie ein eCDN für "Externe Encoder" live-Ereignisse** Wenn Sie planen, live Ereignisse erstellen, die externe Encoder verwenden, müssen Sie ebenfalls [Konfigurieren des Anbieters eCDN mit Microsoft-Stream](https://docs.microsoft.com/stream/network-caching) . Wenn Sie "Schnellstart" live Ereignisse über Microsoft-Teams oder Yammer erstellen möchten, müssen Sie Ihren SDN/eCDN-Anbieter sowie mit Microsoft-Teams integriert werden konfigurieren.

#### <a name="step-8-enable-live-event-scheduling-for-the-user"></a>Schritt 8: Aktivieren von live-Ereignis planen für den Benutzer
Die Planung von live-Ereignis wird für einen Benutzer Teams standardmäßig aktiviert.  

Verwenden Sie die Einstellung AllowBroadcastScheduling in TeamsMeetingBroadcastPolicy in PowerShell Teams können Sie steuern, ob der Benutzer live Ereignisse in Teams oder nicht erstellen kann. Weitere Informationen finden Sie Informationen zum Verwalten von TeamsMeetingBroadcastPolicy mit Office 365 PowerShell [hier](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Es sei denn, die Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer die globale Richtlinie, Aufzeichnung, die in der Standardeinstellung aktiviert hat. 

 Verwenden Sie das folgende Cmdlet für einen Benutzer zum Zugreifen auf globale Richtlinie um eine bestimmte Richtlinie-Zuordnung für einen Benutzer zu entfernen.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Um den Wert von AllowBroadcastScheduling in globale Richtlinie zu ändern, verwenden Sie das folgende Cmdlet aus:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastScheduling $false
```
#### <a name="user-scenarios"></a>Benutzerszenarien
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

#### <a name="enable-external-encoder-based-live-events-for-users"></a>Aktivieren Sie externe Encoder-basierten live Ereignissen für Benutzer

**Aktivieren von Microsoft-Stream für Benutzer in der Organisation** Microsoft-Stream steht als Teil von Office 365-Abonnements zu auswählbaren oder als eigenständigen Dienst. Einzelheiten finden Sie unter [Stream Lizenzierung Overview](https://docs.microsoft.com/stream/license-overview) . Hinweis Microsoft Stream ist nicht in Business Essentials oder Business Premium-Plänen enthalten.  

Erfahren Sie mehr dazu, wie Sie [Lizenzen für Benutzer in Office 365 zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , damit Benutzer Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft-Stream für die Benutzer nicht ausgeschlossen wird, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization)definiert.

**Sicherstellen, dass Benutzer über die live-Ereignis Erstellungsberechtigung in Microsoft Stream-Objekt** Standardmäßig kann jeder Benutzer im Unternehmen Inhalte in Stream-Objekt, erstellen, nach Stream aktiviert ist und der Benutzer eine Lizenz zugewiesen ist. Microsoft Stream-Administrator können [Mitarbeiter bei der Erstellung von einschränken](https://docs.microsoft.com/stream/restrict-uploaders) , in Stream-Objekt. Der Benutzer, die in dieser Liste beschränkt sind möglich zum Aufzeichnen von Besprechungen nicht.

**Sicherstellen, dass live-Ereignis Organisatoren auf die Unternehmensrichtlinie durch den Administrator des Datenstroms festlegen zugestimmt haben** Wenn ein Microsoft-Stream-Administrator [eine Unternehmensrichtlinie Richtlinien einrichten hat](https://docs.microsoft.com/stream/company-policy-and-consent) und Mitarbeiter dieser Richtlinie zu akzeptieren erfordert, bevor das Speichern von Inhalten, klicken Sie dann müssen Benutzer vor dem Erstellen einer live-Ereignis (mit der externen Encoder Produktion) in Microsoft-Teams. Sicherstellen Sie bevor Sie Einführung das Feature live Ereignisse in der Organisation, dass Benutzer, die diese live Ereignisse erstellen werden die Richtlinie zugestimmt haben. 

## <a name="configure-live-events"></a>Konfigurieren des live-Ereignisse

### <a name="set-up-event-support-link"></a>Einrichten von Ereignis Support link
Dies ist die Verknüpfung, die an die Teilnehmer live-Ereignis angezeigt werden. 

Führen Sie in Windows PowerShell das folgende Cmdlet aus:
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
 
Führen Sie in Windows PowerShell das folgende Cmdlet aus, damit Benutzer anonyme Ereignisse in der globalen Richtlinie erstellen können:
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

Verwenden Sie die Einstellung BroadcastRecordingMode in TeamsMeetingBroadcastPolicy in PowerShell Steuerelement Aufzeichnungsoptionen live Ereignisse vom Organisator live-Ereignis erstellt.

Führen Sie in Windows PowerShell das folgende Cmdlet, um Aufzeichnungsmodus in der globalen Richtlinie zu aktualisieren:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Konfigurieren von Real-Time Lautschrift und Übersetzung in Teams live-Ereignisse (bald verfügbar)
> [!NOTE]
> Diese Option ist für Ereignisse, die der Schnellstart Produktion-nur Methode anwendbar.

Dadurch können live-Ereignis Organisatoren, Real-Time Beschriftungen und Übersetzung für den Teilnehmern live-Ereignis zu aktivieren. 

Verwenden Sie die Einstellung AllowBroadcastTranscription in TeamsMeetingBroadcastPolicy in PowerShell Kontrolle, ob die Teilnehmer live-Ereignis Umsetzung und Übersetzung finden Sie unter können. Erfahren Sie mehr über das Verwalten von TeamsMeetingBroadcastPolicy mit Office 365 PowerShell hier.  

Es sei denn, die Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer globale Richtlinie ein, die Umsetzung und Übersetzung standardmäßig deaktiviert hat.

Führen Sie in Windows PowerShell das folgende Cmdlet, um die Umsetzung und eine Übersetzung auf Ereignis Teilnehmer in der globalen Richtlinie zu aktivieren:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
### <a name="self-service-administration-tools"></a>Self-service-Verwaltungstools 
Obwohl Microsoft Office 365 Online Rechenzentren alle Steuerelemente direkt und verantwortlich für die Leistung des gesamten Systems ist, kann es nur einen Teil der Elemente steuern, die kombiniert werden, um den Gesamtnutzen für Office 365-Benutzer bereitzustellen. Organisationen selbst die Verantwortung für die Netzwerkverbindungen mit der Rechenzentren, die Kunden Fernnetz (WAN), und der Kunde lokale Netzwerke (LANs). Darüber hinaus sind für Benutzer Geräte und deren Konfiguration.Sie werden darüber hinaus verantwortlich für die Verwaltung der erforderliche Lizenzierung pro Benutzer für alle gewünschten Features, einschließlich, aber nicht beschränkt auf die Möglichkeit, diese Features für verwalten, solange der Benutzer Zugriff auf dieses Feature benötigt.

Kunden können die folgenden Tools verwenden, um eine Vielzahl von Teams live Ereignisse Aufgaben im Zusammenhang mit verwalten.
- [Microsoft Office 365 Administrationscenter](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft-Teams und Skype für Business Online Administrationscenter](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- Microsoft-Stream-Verwaltungskonsole
- [Windows PowerShell-Remotesitzungen](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?
Wenn es auf Windows PowerShell, es darum geht alle Informationen zum Verwalten von Benutzern und welche Benutzer zulässig sind oder nicht durchgeführt werden darf. Mit Windows PowerShell können Sie Office 365 und Skype verwalten, für die Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen müssen. Siehe folgende Themen, um Windows PowerShell zu verwenden:
 - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
 - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)

### <a name="related-topics"></a>Verwandte Themen: 
- [Ereignisse über Microsoft 365 in Yammer, Microsoft-Teams und Stream Microsoft Live](https://docs.microsoft.com/stream/live-event-m365)
- [Live-Ereignisse im Microsoft-Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Live Ereignisse in Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Live-Ereignisse im Microsoft-Stream](https://docs.microsoft.com/stream/live-event-overview)