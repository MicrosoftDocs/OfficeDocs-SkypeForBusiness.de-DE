---
title: Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Erfahren Sie, wie Sie die Echtzeitmedienleistung in Microsoft Teams mithilfe des Anrufqualitäts-Dashboards (Call Quality Dashboard, CQD) analysieren und verwalten.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 45a52e438fb74286a571cd81461e3de174f9a38f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675057"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität in Microsoft Teams 

Dieser Artikel hilft Ihnen – dem Teams Administrator oder Support- und Helpdesktechniker – bei der Entwicklung eines Prozesses zur Überwachung und Aufrechterhaltung der Anruf- und Besprechungsqualität für Ihre Organisation mithilfe Microsoft Teams Anrufqualitäts-Dashboards (Call Quality Dashboard, CQD). Unsere Anleitung legt den Schwerpunkt auf Szenarien mit Audioqualität, da alle Netzwerkverbesserungen, die Sie zur Verbesserung der Audioerfahrung vornehmen, zu Verbesserungen bei Video und Freigabe führen.

Der Schlüssel zu diesem Leitfaden sind die beiden [kuratierten CQD-Vorlagen](https://aka.ms/QERtemplates) . Es wird empfohlen, sie herunterzuladen, bevor Sie die Anleitungen in diesem Artikel durchgehen.

In diesem Artikel wird davon ausgegangen, dass Sie [CQD bereits eingerichtet](turning-on-and-using-call-quality-dashboard.md) haben.


## <a name="categories-to-monitor-and-maintain"></a>Zu überwachenden und zu verwaltenden Kategorien

Nachdem Sie Besprechungen und VoIP in Teams eingeführt haben, benötigen Sie einen Plan für die laufende Überwachung und Wartung. Dadurch wird sichergestellt, dass Teams immer optimal läuft. Dieser Plan sollte die unten aufgeführten Schlüsselbereiche enthalten. Sie sollten auch Ziele für Qualitätsmetriken und einen Plan für die Problembehandlung und Isolierung von Problemen festlegen, wenn sie auftreten.

<table>
<thead>
<tr class="header">
<th>Kategorie</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Anrufqualität</strong></td>
<td>
<p>Aufschlüsseln der Metriken nach internen Anrufen (innerhalb Ihrer Organisation, z. B. VPN, WLAN, kabelgebunden) oder externen Anrufen</p>
<p>Aufschlüsseln der Metriken nach Gebäude oder Netzwerk</p>
<p>VPN-Anrufe</p>
<p>Aufrufe mit TCP, UDP oder Proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Anrufsicherheit</strong></td>
<td><p>Identifizieren und Beheben von Netzwerk- oder Firewallproblemen</p>
<p>Erhalten Sie Einblicke in die Prozentsätze von Anrufeinrichtungs- und Drop-Fehlern.</p>
<p>Erfahren Sie, wo der Großteil der Anrufeinrichtungs- und -ablagefehler auftritt.</p>
</td>
</tr>
<tr class="odd">
<td><strong>Benutzerumfrage</strong></td>
<td>
<p>Verwenden von "Meinen Anruf bewerten"-Daten, um mehr über die tatsächliche Benutzererfahrung zu erfahren</p>
<p>Wo treten die schlechten Erfahrungen auf?</p>
<p>Korrelieren der schlechten Erfahrung mit Anrufqualität, Zuverlässigkeit und Geräten</p>
</td>
</tr>
<tr class="even">
<td><strong>Geräte</strong></td>
<td><p>Erfahren Sie, welche Mikrofone und Lautsprecher am häufigsten verwendet werden und welche Auswirkungen sie auf die Anrufqualität haben.</p>
<p>Werden die unterstützenden Audio-, Video-, USB- und WLAN-Treiber regelmäßig gepatcht?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clients</strong></td>
<td>
<p>Erfahren Sie, welche Clienttypen und Versionen verwendet werden und welche Auswirkungen sie auf die Anrufqualität und -zuverlässigkeit haben.  </p>
</ol></td>
</tr>
</tbody>
</table>

Durch die kontinuierliche Bewertung und Behebung der in diesem Artikel beschriebenen Bereiche können Sie deren Potenzial verringern, ihre Benutzer negativ zu beeinflussen. Die meisten Benutzerprobleme können in die folgenden Kategorien unterteilt werden:

-   Unvollständige Firewall- oder Proxykonfiguration
-   Schlechte WLAN-Abdeckung
-   Unzureichende Bandbreite
-   VPN
-   Inkonsistente oder veraltete Clientversionen und Treiber
-   Nicht optimierte oder integrierte Audiogeräte
-   Problematische Subnetze oder Netzwerkgeräte

Durch die ordnungsgemäße Planung und Gestaltung vor der Bereitstellung von Teams oder Skype for Business Online können Sie den Aufwand verringern, der erforderlich ist, um die hohe Qualität des Erlebnisses aufrechtzuerhalten.

Dieser Artikel konzentriert sich auf die Verwendung des Anrufqualitätsdashboards (Call Quality Dashboard, CQD) Online als primäres Tool zum Melden und Untersuchen der einzelnen Bereiche, mit besonderem Schwerpunkt auf Audio, um die Akzeptanz und Wirkung zu maximieren. Alle zur Optimierung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Um Ihre Bewertung zu beschleunigen, werden [zwei zusammengestellte CQD-Vorlagen](https://aka.ms/qertemplates) bereitgestellt: eine ist für die Verwaltung aller Netzwerke und die andere wird nur nach verwalteten (internen) Netzwerken gefiltert. Obwohl die Vorlagenberichte „Alle Netzwerke“ so konfiguriert sind, dass sie Gebäude- und Netzwerkinformationen anzeigen, können sie dennoch verwendet werden, während Sie auf die Erfassung und das Hochladen von Gebäudeinformationen hinarbeiten. Durch das Hochladen von Gebäudeinformationen in CQD kann der Dienst die Berichterstellung verbessern, indem benutzerdefinierte Gebäude-, Netzwerk- und Standortinformationen hinzugefügt werden, wobei zwischen internen und externen Subnetzen unterschieden wird. Weitere Informationen finden Sie unter [Gebäudezuordnung](CQD-building-mapping.md).

### <a name="intended-audience"></a>Zielgruppe

Dieser Artikel soll von Partner- und Kundenbeteiligten mit Rollen wie Collaboration Lead/Architect, Consultant, Change Management/Adoption Specialist, Support/HelpDesk Lead, Network Lead, Desktop Lead und IT Admin verwendet werden.

Dieser Artikel ist auch für die Verwendung durch die designierten Qualitätspioniere vorgesehen. Weitere Informationen finden Sie unter [Die Rolle des Qualitätspioniers](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>Was ist Qualität?

In diesem Zusammenhang ist Qualität eine Kombination aus Dienstmetriken und Benutzererfahrung.


### <a name="service-metrics"></a>Dienstmetriken

Die Dienstmetriken umfassen bestimmte clientbasierten Metriken. Während jedes Anrufs sammelt der Client Telemetriedaten für den Anruf und übermittelt am Ende jedes Anrufs einen Bericht, auf den später in CQD oder in der [Anrufanalyse pro Benutzer](set-up-call-analytics.md) zugegriffen werden kann. Diese Metriken umfassen (sind aber nicht beschränkt auf):

-   Poor Stream (ein- und ausgehend)
-   Aufbaufehlerrate
-   Abbruchfehlerrate


#### <a name="poor-stream-rate"></a>Schlechte Streamrate

Die schlechte Datenstromrate (Poor Stream Rate, PSR) stellt den Gesamtprozentsatz der Datenströme der Organisation dar, die eine schlechte Qualität aufweisen. Diese Metrik soll Bereiche hervorheben, auf die sich Ihre Organisation konzentrieren kann, um den größten Einfluss auf die Reduzierung dieses Wertes und die Verbesserung des Benutzererlebnisses zu erzielen. Deshalb stehen [verwaltete Netzwerke](#managed-versus-unmanaged-networks) bei der Betrachtung des PSR im Vordergrund. Externe Benutzer sind ebenfalls wichtig, die Untersuchungen sind aber für die verschiedenen Betriebsebenen unterschiedlich. Überlegen Sie sich, bewährte Methoden für externe Benutzer bereitzustellen und externe Anrufe unabhängig von der Gesamtorganisation zu untersuchen.

Die tatsächliche Messung im CQD variiert je nach Workload, aber für die Zwecke dieses Artikels konzentrieren wir uns in erster Linie auf die Messung des _Audio Poor Percentage_ . Die PSR besteht aus den fünf durchschnittlichen Netzwerkmetriken, die in der folgenden Tabelle beschrieben sind. Damit ein Strom als schwach eingestuft wird, muss nur eine der Metriken den definierten Grenzwert überschreiten. CQD stellt die "Poor Due To..." Messungen, um besser zu verstehen, welche Bedingung dazu führte, dass der Datenstrom als "schlecht" klassifiziert wurde. Weitere Informationen finden Sie [in der Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> CQD bietet die "Poor due to..." Messungen, um besser zu verstehen, welche Bedingung dazu führte, dass der Datenstrom als "schlecht" klassifiziert wurde.


##### <a name="audio-poor-quality-metrics"></a>Metriken für audioarme Qualität

| Mittelwert der Metrik     | Beschreibung     | Benutzererfahrung |
|-------------|-----------------|-----------------|
| Jitter \>30 ms        | Dies ist die durchschnittliche Änderung bei der Verzögerung zwischen aufeinander folgenden Paketen. Teams und Skype for Business können ein gewisses Maß an Jitter durch Pufferung ausgleichen. Erst wenn der Jitter die Pufferung überschreitet, bemerkt ein Teilnehmer die Auswirkungen von Jitter.      | Die Pakete, die mit unterschiedlichen Geschwindigkeiten ankommen, bewirken, dass die Stimme eines Lautsprechers roboterhaft klingt.   |
| Paketverlustrate \>10 % oder 0,1        | Diese Eigenschaft wird oft als prozentualer Anteil der Pakete gemessen, die verloren gegangen sind. Paketverluste wirken sich direkt auf die Audioqualität aus. Sie reichen vom Verlust einzelner kleiner Pakete, der fast keine Auswirkung hat, bis hin zu direkt aufeinander folgenden Burstverlusten, die zu Tonaussetzern führen.     | Die verworfenen und nicht am vorgesehenen Bestimmungsort ankommenden Pakete führen zu Lücken in den Medien, was zu fehlenden Silben und Wörtern sowie abgehacktem Video und Störungen bei der Freigabe führen kann. |
| Round-trip-Zeit \>500 ms        | Dies ist die Zeit, die benötigt wird, um ein IP-Paket von Punkt А nach Punkt B und zurück zu Punkt А zu senden. Diese Verzögerung der Weitergabe im Netzwerk ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verknüpft. Dazu gehört auch der Mehraufwand durch die zwischen den Punkten vorhandenen Geräten.      | Die Pakete, die zu lange dauern, bis sie an Ihr Ziel gelangen, führen zu einem Walkie-Talkie-Effekt.   |


##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Warum bevorzugen wir die Verwendung von Datenströmen anstelle von Aufrufen?

Streams lassen Sie uns wissen, welches bestimmte Bein des Anrufs schlecht war - ausgehend oder eingehend. Wenn Sie sich die Anrufanalyse für einen schlechten Anruf ansehen, ermitteln Sie, ob der anrufarme Anruf auf den Datenstrom (ausgehend) oder den Datenstrom des Angerufenen (eingehend) zurückzuführen ist. Die Ermittlung, welcher Datenstrom sich auf die Anrufqualität auswirkt, ist für Konferenzen noch wichtiger. Wenn Sie nur Anrufdaten betrachten, werden Sie sehen, an wie vielen Konferenzen eine Person teilnimmt, aber Sie werden nicht sehen, welche Personen aktive Lautsprecher sind und dabei die meisten Bildschirmfreigaben ausführen.

Anrufdaten bieten Ihnen Nutzungsmetriken, führen aber nicht unbedingt zur Ursache für eine schlechte Anrufqualität. Wenn Sie sich die Datenstromrichtung ansehen, können Sie Faktoren identifizieren, z. B. einen Anruf, der sich nicht in einem verwalteten Netzwerk befindet, einen Anruf von einem Nicht-Mitarbeiter (z. B. einen Lieferanten oder eine Person in einem anderen Netzwerk). Wenn in diesen Fällen die Netzwerkverbindung der anderen Person schlecht war, wird der gesamte Anruf als "schlecht" gekennzeichnet. Sie können nichts gegen externe Faktoren tun, daher sind diese Daten nicht hilfreich.

Die Datenstromrichtung kann Ihnen auch dabei helfen, problematische Geräte oder Clients zu identifizieren.

 - Wenn Sie z. B. über ein begrenztes Budget für Geräte verfügen und Geräte nur für benutzer mit hohem Audiodatenstrom bereitstellen möchten, verwenden Sie den Audionutzungsbericht (VoIP) und filtern Sie nach ausgehenden Datenströmen und Konferenzen. Suchen Sie nach Audiobenutzern mit hoher Lautstärke, die in integrierte Mikrofone sprechen – diese korrelieren möglicherweise mit einer schlechteren Anrufqualität (und Sie möchten möglicherweise Audiogeräte für diese Personen bereitstellen). Aus Gründen der besseren Übersichtlichkeit können Sie nach der Paketauslastung filtern, wodurch Sie besonders für Audiobenutzer mit hoher Lautstärke sorgen können. 

  - Ein weiteres Beispiel ist die Bildschirmfreigabe. Wenn ein Kunde einen alten Teams-Client verwendet, kann die Leistung der Bildschirmfreigabe beeinträchtigt werden. Sie können dieses Problem beheben, indem Sie Clientupgrades für Personen priorisieren, die viel Bildschirmfreigabe durchführen.

 - Indem Sie ermitteln, welche Richtung eines Datenstroms eine schlechte Anrufqualität verursacht, können Sie ermitteln, ob Sie ein QoS- oder Bandbreitenproblem haben. Wenn Sie QoS noch nicht vollständig implementiert haben oder Pakete nur am Client und nicht am eingehenden Datenstrom markieren, wird möglicherweise eine schlechtere Anrufqualität angezeigt. Wenn Sie sich die Datenstromrichtung ansehen, können Sie eine genauere Ansicht des Paketverlusts, der Latenz oder des Jitters in einer bestimmten Richtung erhalten. 

   - Nehmen wir beispielsweise an, ein Benutzer beschwert sich über Roboteraudio, während er sich an einer kabelgebundenen Verbindung (Jitter) befindet. Wenn Sie sich den Datenstrom und die Richtung ansehen, können Sie feststellen, dass das Problem auf dem eingehenden Datenstrom nur für eine bestimmte Gruppe von Subnetzen auftritt. Nachdem Sie diese Informationen an Ihr Netzwerkteam übergeben haben, können sie diese auf eine falsch konfigurierte WAN-Zugriffstaste nachverfolgen, die den Mediendatenverkehr nicht umgangen hat. Sobald das Netzwerkteam die WAN-Zugriffstaste neu konfiguriert hat, verschwindet jitter, und die Anrufqualität verbessert sich. 


#### <a name="setup-failure-rate"></a>Aufbaufehlerrate

Die Setupfehlerrate, auch als _"Total Call Setup Failure Percentage_ "-Messung in CQD bezeichnet, ist die Anzahl der Datenströme, bei denen der Medienpfad zwischen den Endpunkten zu Beginn des Anrufs nicht erstellt werden konnte.

Dies stellt einen Mediendatenstrom dar, der nicht erstellt werden konnte. Angesichts des Schweregrads der Auswirkungen dieses Problems auf die Benutzererfahrung besteht das Ziel darin, diesen Wert auf so nahe wie möglich null zu reduzieren. Ein hoher Wert für diese Metrik ist in neuen Bereitstellungen mit unvollständigen Firewallregeln häufiger als bei einer ausgereiften Bereitstellung, aber es ist immer noch wichtig, regelmäßig zu beobachten.

Diese Metrik wird berechnet, indem die Gesamtzahl der Ströme, die nicht eingerichtet werden konnten, durch die Gesamtzahl der Ströme geteilt wird, die einen erfolgreichen Kommunikationsdatensatz (Call Detail Record, CDR) gesendet haben:

-   **Aufbaufehlerrate** = Gesamtanzahl der Ströme mit Ausfall des Rufaufbaus / Gesamtzahl der Ströme mit verfügbarem CDR

#### <a name="drop-failure-rate"></a>Abbruchfehlerrate

Die Drop-Fehlerrate, auch bekannt als " _Total Call Dropped Failure Percentage_ "-Messung in CQD, ist der Prozentsatz der erfolgreich eingerichteten Datenströme, bei denen der Medienpfad nicht normal beendet wurde.

Das steht für jeden Medienstrom, der unerwartet beendet wurde. Obwohl die Auswirkungen nicht so schwerwiegend sind wie ein Datenstrom, der nicht eingerichtet werden konnte, wirkt sich dies dennoch negativ auf die Benutzererfahrung aus. Plötzliche und häufige Medienverluste können nicht nur schwerwiegende Auswirkungen auf die Benutzererfahrung haben, sondern auch dazu führen, dass Benutzer sich erneut verbinden müssen, was zu produktivitätsbedingtem Verlust (ganz zu schweigen von Frustration) führt.

Die Metrik wird berechnet, indem die Gesamtzahl der abgebrochenen Ströme durch die Gesamtzahl der erfolgreich aufgebauten Datenströme dividiert wird:

-   **Abbruchfehlerrate** = Gesamtanzahl der abgebrochenen Anrufströme / Gesamtzahl der Ströme mit erfolgreichem Rufaufbau

### <a name="define-your-target-metrics"></a>Definieren Ihrer Zielmetriken

In diesem Abschnitt werden einige der wichtigsten Dienstmetriken erläutert, die wir verwenden, um den Status der Dienste zu bewerten. Durch die kontinuierliche Bewertung und Förderung der Bemühungen, diese Metriken unter den definierten Zielen zu halten, tragen Sie dazu bei, dass Ihre Benutzer eine konsistente, zuverlässige Anrufqualität erhalten. Verwenden Sie als Ausgangspunkt die vorgeschlagenen Ziele in der folgenden Tabelle. Passen Sie die Ziele nach Bedarf an, um Ihre Geschäftsziele zu erreichen.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Netzwerktyp</th><th rowspan="1">Qualitätsziele</th><th colspan="2">Zuverlässigkeitsziele</th></tr>
<tr><th>Schwache Audiostromrate</th><th>Aufbaufehlerrate</th><th>Abbruchfehlerrate</th></tr>
<tr><td rowspan="2"><strong>Alle</strong></td><td>Intern</td><td>2,0 %</td><td>0,5 %</td><td>2,0 %</td></tr>
<tr><td>Insgesamt</td><td>3,0 %</td><td>1,0 %</td><td>3,0 %</td></tr>
<tr><td rowspan="5"><strong>Konferenzen</strong></td><td>Intern</td><td>2,0 %</td><td>0,5 %</td><td>2,0 %</td></tr>
<tr><td>LAN intern</td><td>1,0 %</td><td>0,5 %</td><td>1,0 %</td></tr>
<tr><td>WLAN 5 GHz intern</td><td>1,0 %</td><td>0,5 %</td><td>1,0 %</td></tr>
<tr><td>WLAN 2,4 GHz intern</td><td>2,0 %</td><td>0,5 %</td><td>2,0 %</td></tr>
<tr><td>Insgesamt</td><td>2,0 %</td><td>0,5 %</td><td>3,0 %</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Intern</td><td>2,0 %</td><td>0,5 %</td><td>2,0 %</td></tr>
<tr><td>LAN/WLAN 5 GHz intern</td><td>1,0 %</td><td>0,5 %</td><td>1,0 %</td></tr>
<tr><td>LAN/WLAN 5 GHz allgemein</td><td>2,0 %</td><td>1,0 %</td><td>1,0 %</td></tr>
<tr><td>Insgesamt</td><td>2,0 %</td><td>1,0 %</td><td>3,0 %</td></tr>
</table>

### <a name="user-experience"></a>Benutzererfahrung

Das Analysieren der Benutzererfahrung ist mehr Kunst als Wissenschaft, da die hier gesammelten Metriken nicht immer bedeuten, dass es ein Problem mit dem Netzwerk oder dem Dienst gibt, sondern vielmehr einfach darauf hindeuten, dass der Benutzer ein Problem wahrnimmt. CQD enthält einen integrierten Umfragemechanismus – Rate My Call (RMC) –, um die allgemeine Benutzererfahrung zu messen. RMC gibt Ihnen Einblicke in die folgenden Fragen aus der Perspektive Ihrer Benutzer:

-   Weiß ich, wie die Lösung zu verwenden ist?
-   Ist die Lösung benutzerfreundlich und intuitiv und unterstützt Sie die täglichen Kommunikationsanforderungen?
-   Hilft mir die Lösung beim erledigen meiner Aufgabe?
-   Was ist meine Gesamtwahrnehmung über die Lösung?
-   Kann ich die Lösung jederzeit verwenden – unabhängig davon, wo ich gerade bin?
-   Kann ich einen Anruf aufbauen und aufrechterhalten?

#### <a name="rate-my-call"></a>Meinen Anruf bewerten 

Rate My Call (RMC) ist in Teams und Skype for Business integriert. Es wird automatisch nach einem von 10 Anrufen oder 10 Prozent angezeigt. In dieser kurzen Umfrage wird der Benutzer gebeten, den Anruf zu bewerten und ein wenig Kontext dafür zu liefern, warum die Anrufqualität schlecht gewesen sein könnte. Ein oder zwei Bewertungen werden als unzureichend betrachtet, drei bis vier sind gut und fünf ist ausgezeichnet. Obwohl es sich um einen etwas zurückgebliebenen Indikator handelt, ist dies eine nützliche Metrik, um Probleme aufzudecken, die dienstmetriken übersehen können.

> [!Note]
> Der menschliche Faktor: Benutzer ignorieren die Umfrage häufig, wenn die Anrufqualität gut ist, und füllen sie aus, wenn die Anrufqualität schlecht ist. Daher sind Ihre RMC-Berichte möglicherweise auf die schlechte Seite verzerrt, auch wenn die Dienstmetriken gut sind.

Sie können CQD verwenden, um über die Benutzerreaktionen von RMC zu berichten und Beispielberichte sind in der CQD-Vorlage enthalten. Sie werden in diesem Artikel jedoch nicht ausführlich behandelt. 

#### <a name="client-and-device-readiness"></a>Client- und Gerätebereitschaft

Sie benötigen eine solide Client- und Gerätestrategie, um sicherzustellen, dass Ihre Benutzer eine konsistente und positive Benutzererfahrung haben. Jede Bereitschaftsstrategie beruht auf einigen wenigen Schlüsselprinzipien.

##### <a name="client-readiness"></a>Client-Bereitschaft

Wenn Sie den Teams-Client auf dem neuesten Stand halten, wird sichergestellt, dass Ihre Benutzer immer die bestmögliche Erfahrung erhalten. Microsoft veröffentlicht häufige [Updates für den Teams-Client](teams-client-update.md) (das Update installiert sich selbst im Hintergrund, es sei denn, Sie haben diese Funktionalität deaktiviert – was wir nicht empfehlen). Es ist auch wichtig, sich daran zu erinnern, Netzwerk-, Video-, USB- und Audiotreiber zu patchen, da diese häufig übersehen werden und sich auf die Anruf- und Besprechungsqualität auswirken können. Überlegen Sie sich, Netzwerk-, WLAN-, Video-, USB -und Audiotreibern zum aktuellen Patchverwaltungsvorgang hinzuzufügen.


##### <a name="device-readiness"></a>Gerätebereitschaft

Keine einzelne Strategie kann das Benutzererlebnis mehr beeinflussen als Ihre Strategie zur Gerätebereitschaft. Benutzer, die sich beispielsweise auf ihre Laptoplautsprecher und ihr Mikrofon verlassen, haben in Anrufen und Besprechungen viel Hintergrundgeräusche. Teams ist so konzipiert, dass es mit fast jedem Gerät funktioniert. Wenn Sie jedoch gerätebezogene Probleme haben, schauen Sie sich [Telefon für Teams](./devices/phones-for-teams.md) an.


### <a name="categories-of-quality"></a>Qualitätskategorien

Operationalisieren Sie eine Reihe von Qualitätsmanagementpraktiken – dies gibt Ihnen die besten Chancen auf eine gute Anruf- und Besprechungsqualität. Ein guter Qualitätsmanagementplan befasst sich mit diesen Kategorien:

-   **Netzwerk:** Die Audioqualität konzentrierte sich auf die Metrik Poor Stream Ratio (PSR), tcp-Nutzung, kabelgebundene und drahtlose Subnetze und die Identifizierung der Verwendung von HTTP-Proxys und VPN

-   **Endpunkte:** Audiogeräte und aktuelle Clients

-   **Dienstverwaltung:** diese Kategorie umfasst zwei Abschnitte:

    -   Zunächst liegt die Verantwortung von Microsoft darin, die Teams und Skype for Business Onlinedienste zu verwalten und zu verwalten.

    -   Zweitens sind Aufgaben, die Ihre Organisation verwaltet, um zuverlässigen Zugriff auf den Dienst sicherzustellen, z. B. das Aktualisieren von Gebäudeinformationen und das Warten von Firewalls für neue Office 365 IP-Adressen, wenn dem Dienst Infrastruktur hinzugefügt wird.

![Graph der Qualitätskategorien in einer Organisation.](media/qerguide-image-categories.png "Die Qualitätskategorien in einer Organisation: Dienstverwaltung, Endpunkte und das Netzwerk.")

Überprüfen Sie die folgende Liste der Aufgaben, die zur Aufrechterhaltung der Qualität empfohlen werden. Sie sollten diese Aufgaben regelmäßig ausführen , z. B. wöchentlich.

#### <a name="service-management-tasks"></a>Dienstverwaltungsaufgaben

Diese Aufgaben reichen von der Sicherstellung, dass genügend Bandbreite vorhanden ist, um den Dienst zu erreichen, ohne Internetverbindungen zu sättigen, zu überprüfen, ob die Dienstqualität (Quality of Service, QoS) in allen verwalteten Netzwerkbereichen vorhanden ist, und über [Office 365 IP-Bereiche in Firewalls](/microsoft-365/enterprise/urls-and-ip-address-ranges) zu bleiben.

#### <a name="network-tasks"></a>Netzwerkaufgaben

Es gibt zwei Kategorien von Netzwerkaufgaben: Zuverlässigkeit und Qualität. Zuverlässigkeit konzentriert sich auf die Messung der Fähigkeit des Benutzers, erfolgreich Anrufe zu tätigen und in Verbindung zu bleiben. Die Qualität konzentriert sich auf die aggregierte Telemetrie, die während des Anrufs und nach beendigung des Anrufs vom Kunden des Benutzers an Teams und Skype for Business Online gesendet wird. 

Angesichts der kritischen Auswirkungen, die Die Zuverlässigkeit auf die Benutzererfahrung hat, empfehlen wir, die Zuverlässigkeitsmetriken zu bewerten und zu untersuchen, bevor Sie sich mit der Qualität befassen. 

#### <a name="endpoints-tasks"></a>Endpunktaufgaben

Die Hauptaufgabe in dieser Kategorie ist das Entfernen von Hindernissen für regelmäßige [Teams Clientupdates](teams-client-update.md). Standardmäßig wird Teams automatisch regelmäßig aktualisiert (es sei denn, Sie deaktivieren diese Einstellung, was nicht empfohlen wird). 

Sie sollten auch Geräte überwachen und Updates bereitstellen, wenn Sie Probleme im Zusammenhang mit einem Gerät erkennen.

## <a name="use-cqd-to-manage-call-quality"></a>Verwenden von CQD zum Verwalten der Anrufqualität

Nachdem Sie [CQD eingerichtet](turning-on-and-using-call-quality-dashboard.md) haben, können Sie damit beginnen, die Anruf- und Besprechungsqualität für Ihre Organisation zu verwalten.

Die meisten Probleme mit Teams Leistung fallen in die folgenden Kategorien:

-   Unvollständige Firewall- oder Proxykonfiguration
-   Schlechte WLAN-Abdeckung
-   Unzureichende Bandbreite
-   VPN
-   Inkonsistente oder veraltete Clientversionen und Treiber
-   Nicht optimierte oder integrierte Audiogeräte
-   Problematische Subnetze oder Netzwerkgeräte

Wenn Sie sich die Zeit nehmen, bevor Sie Teams bereitstellen, um diese Bereiche zu bewerten und Mängel zu beheben, reduzieren Sie den Aufwand, der erforderlich ist, um eine qualitativ hochwertige Teams-Erfahrung für alle Ihre Benutzer zu gewährleisten. Hilfe zur Bewertung Ihres Netzwerks bei der Vorbereitung ihres Teams Rollouts finden Sie [unter Advisor für Teams](use-advisor-teams-roll-out.md) und [Vorbereiten Ihres Netzwerks für Teams](prepare-network.md).

### <a name="expectations-using-cqd"></a>Erwartungen bei der Verwendung von CQD

Verwenden Sie das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD), um Einblicke in die Qualität von Anrufen zu erhalten, die mithilfe von Teams- und Skype for Business-Diensten getätigt werden. CQD soll Teams und Skype for Business Administratoren und Netzwerktechnikern dabei helfen, das Netzwerk zu optimieren und qualität, Zuverlässigkeit und Benutzerfreundlichkeit im Auge zu behalten. CQD untersucht die aggregierte Telemetrie für eine gesamte Organisation, in der allgemeine Muster sichtbar werden können; Auf diese Weise können Sie fundierte Bewertungen vornehmen und die Wartung planen. CQD bietet Metrikenberichte, die Einblicke in die Qualität, Zuverlässigkeit und Benutzerfreundlichkeit bieten.

Das CQD ist zwar nützlich für die Analyse von Trends und Subnetzen, bietet jedoch nicht immer eine spezifische Ursache für ein bestimmtes Szenario. Es ist wichtig, dies zu verstehen und die richtige Erwartung bei Verwendung von CQD festzulegen:

-   CQD liefert nicht die Ursache für jedes Szenario
-   CQD enthält keine Telefonsystem oder Audiokonferenz Streams
-   CQD wird Bereiche für weitere Untersuchungen auf der Grundlage von Trends ausrufen

### <a name="cqd-reports-overview"></a>Übersicht über CQD-Berichte

Verwenden Sie das Dropdownmenü oben auf dem Bildschirm, um einen Bericht zu öffnen. Eine Liste der in den einzelnen Berichten bereitgestellten Daten finden Sie [in den in CQD-Berichten verfügbaren Daten](CQD-data-and-reports.md#data-available-in-cqd-reports).

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.


### <a name="teams-vs-skype-for-business"></a>Teams vs. Skype for Business

CQD kann sowohl über Teams als auch über Skype for Business berichten. Es kann jedoch vorkommen, dass Sie einen Bericht entwickeln möchten, um die Telemetrie von Teams getrennt von Skype for Business zu betrachten.

#### <a name="summary-reports"></a>Zusammenfassungsberichte

Wenn Sie die Seite Zusammenfassungsberichte so ändern möchten, dass nur Teams oder Skype for Business angezeigt wird, wählen Sie am oberen Rand des Bildschirms das Dropdownmenü **Produktfilter** aus, und wählen Sie dann das gewünschte Produkt aus.

![Screenshot des Dropdownmenüs mit den Filteroptionen.](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Detaillierte Berichte

Wenn Sie alle detaillierten Berichte filtern möchten, fügen Sie in der Browserleiste Folgendes am Ende der URL an:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Beispiel:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Weitere Informationen zu URL-Filtern finden Sie in [den Filterberichten](CQD-data-and-reports.md#report-filters) weiter unten in diesem Abschnitt.

Wenn Sie einen einzelnen detaillierten Bericht filtern möchten, fügen Sie den Filter ``Is Teams`` zum Bericht hinzu und legen Sie ihn auf „True“ oder „False“ fest.

![Screenshot der Seite "Filter hinzufügen".](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Verwaltete und nicht verwaltete Netzwerke

Standardmäßig werden alle Endpunkte in CQD als extern eingestuft. Sobald eine Gebäudedatei eingeführt wird, können wir mit der Suche nach verwalteten Endpunktdaten beginnen. Wie bereits erwähnt, sind Netzwerke in CQD wie folgt definiert:

-   Ein _verwaltetes Netzwerk_, das häufig als "internes" oder "inneres" bezeichnet wird, kann von der Organisation beeinflusst und gesteuert werden. Dies umfasst das interne LAN, das Remote-WAN und VPN.
-   Ein _nicht verwaltetes Netzwerk_, das oft als extern oder außen bezeichnet wird, kann von der Organisation nicht beeinflusst oder kontrolliert werden. Ein Beispiel für ein nicht verwaltetes Netzwerk ist ein Hotel- oder Flughafennetzwerk.

### <a name="dimensions-measures-and-filters"></a>Dimensionen, Messungen und Filter

Eine gut formulierte CQD-Abfrage enthält alle drei der folgenden Parameter: 

-   **Dimension:** Wie ich die Daten betrachten möchte.

-   **Messung:** Worüber möchte ich berichten.

-   **Filter:** Wie ich den von der Abfrage zurückgegebenen Datensatz reduzieren möchte.

Eine andere Möglichkeit, dies zu betrachten, ist, dass eine _Dimension_ die Gruppierungsfunktion ist, ein _Measure_ die Daten ist, an denen ich interessiert bin, und ein _Filter_ ist, wie ich die Ergebnisse auf diejenigen einschränken möchte, die für meine Abfrage relevant sind.

Ein Beispiel für eine wohlgeformte Abfrage ist **Zeige schwache Ströme [Messung] nach Subnetz [Dimension] für Gebäude 6 [Filter] an**. Weitere Informationen finden Sie unter [Dimensionen und Messungen, die in CQD verfügbar sind](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="first-vs-second"></a>Erster vs. zweiter 

Viele Dimensionen und Kennzahlen im CQD werden als erster oder zweiter Endpunkt bezeichnet. In CQD werden keine Anrufer-/Angerufenenfelder verwendet– diese wurden _zuerst_ und _zweitens_ umbenannt, da zwischen dem Anrufer und dem Angerufenen Zwischenschritte ausgeführt werden. Die folgende Logik legt fest, welcher beteiligte Endpunkt als erster bezeichnet wird:

-   Der **erste** wird immer ein Serverendpunkt (Konferenzserver, Vermittlungsserver usw.) sein, wenn ein Server in den Strom oder Anruf einbezogen wird.

-   Der **zweite** ist immer ein Client-Endpunkt, es sei denn, der Datenstrom verläuft zwischen zwei Server-Endpunkten.

-   Wenn beide Endpunkte vom selben Typ sind, richtet sich die Auswahl des ersten Endpunkts nach der internen Anordnung der Benutzer-Agenten-Kategorie. Dadurch wird sichergestellt, dass die Reihenfolge konsistent ist.

Weitere Informationen zum Ermitteln des ersten oder zweiten Endpunkts, wenn beide identisch sind, finden Sie [unter Dimensionen und Measures, die in CQD verfügbar](./dimensions-and-measures-available-in-call-quality-dashboard.md) sind.

### <a name="stream-vs-call"></a>Datenstrom vs. Anruf

Sie müssen den Unterschied zwischen einem Anruf und einem Datenstrom verstehen, um richtig auszuwählen, welche Dimensionen oder Measures Sie im CQD betrachten möchten. Obwohl der Hauptfokus von CQD auf Datenströmen liegt, sind auch anrufbasierte Messungen verfügbar.

-   **Datenstrom:** Ein _Datenstrom_ ist nur zwischen zwei Endpunkten vorhanden. Es gibt nur einen Datenstrom für jede Richtung und für die Kommunikation sind zwei Datenströme erforderlich. Datenströme sind hilfreich, um Gebäude, Netzwerke oder Subnetze zu untersuchen. In einigen Fällen werden sowohl Der Anruf als auch der Datenstrom im Namen der Messung verwendet (z. B. "Anrufeinrichtungsstream" oder "Verworfener Anrufdatenstrom"). Diese werden weiterhin als Datenströme eingestuft.

-   **Anruf:** Ein _Anruf_ ist eine Gruppierung aller Datenströme aller Teilnehmer. Ein Anruf besteht aus mindestens zwei Ströme. Ein einzelner Anruf hat mindestens zwei Endpunkte mit jeweils mindestens einem Datenstrom.

Weitere Hinweise dazu, ob sich die Dimension oder Messung auf einen Anruf oder einen Datenstrom bezieht, finden Sie unter [Dimensionen und Messungen, die in CQD verfügbar sind](./dimensions-and-measures-available-in-call-quality-dashboard.md). 

### <a name="good-poor-and-unclassified-calls"></a>Gute, schlechte und nicht klassifizierte Anrufe

Ein Anruf wird entweder als "gut", "schlecht" oder "nicht klassifiziert" kategorisiert. Nehmen wir uns einen Moment Zeit, um ausführlicher über jeden einzelnen Zuschnitt zu sprechen.

-   **Gut oder schlecht:** Ein guter oder schlechter Anruf besteht aus einem Anruf, der eine vollständige Gruppe von Dienstmetriken enthält, für die ein vollständiger QoE-Bericht generiert und vom Dienst empfangen wurde. Das Ermitteln, ob ein Datenstrom gut oder schlecht ist, wird [weiter oben in diesem Artikel](#poor-stream-rate) beschrieben.

-   **Unklassifizierte:** Ein nicht klassifizierter Datenstrom enthält keinen vollständigen Satz von Dienstmetriken. Hierbei kann es sich um kurze Aufrufe (in der Regel weniger als 60 Sekunden) handelt, bei denen Mittelwerte nicht berechnet und kein QoE-Bericht generiert wurde. Der häufigste Grund für Anrufe, die nicht klassifiziert werden, besteht darin, dass die Paketnutzung nur geringfügig oder gar nicht funktioniert. Ein Beispiel hierfür wäre ein Teilnehmer, der sich an einer Besprechung stummgeschaltet anschließt und niemals spricht. Der Teilnehmer empfängt, sendet jedoch keine Medien. Ohne die Übertragung von Medien stehen keine Metriken für CQD zur Klassifizierung des ausgehenden Mediendatenstroms des Endpunkts zur Verfügung.

Weitere Informationen finden Sie [in der Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Häufig verwendete Subnetze

Häufig verwendete Subnetze sind bestimmte private Subnetze, die von Hotels, Heimnetzwerken, Hotspots und ähnlichen Bereichen verwendet werden. Diese Subnetze können aufgrund ihrer weit reichenden Nutzung nur schwer verfolgt werden. Wenn in Ihrer Organisation eines dieser häufig verwendeten Subnetze verwendet wird, empfehlen wir, dass Sie dieses Netzwerk in ein anderes Subnetz verschieben. Dies erleichtert die Berichterstellung in CQD. Wenn angegeben, wurden Berichte in der Vorlage "Alle Netzwerke" so konfiguriert, dass Sie diese Subnetze ausschließen, um sie als Quelle schlechter Qualität zu eliminieren. Nachstehend sind häufig verwendete Subnetze definiert. Ihre Auswirkung variiert je nach Organisation.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Bei der Untersuchung eines verwalteten Netzwerks, das ein gemeinsames Subnetz verwendet, müssen Sie die zweite reflexive lokale IP-Dimension verwenden, um Subnetze zu gruppieren. Diese Dimension enthält die öffentliche IP-Adresse des Endpunkts.


## <a name="reliability-investigations"></a>Zuverlässigkeitsuntersuchungen

Der erste Schritt zur Verbesserung der Qualität ist die Einschätzung des Status der Zuverlässigkeit innerhalb der gesamten Organisation. Da Zuverlässigkeit für eine positive Benutzererfahrung von entscheidender Bedeutung ist, beginnen wir mit den beiden Komponenten zur Messung der Zuverlässigkeit:

1.  **Setupfehler:** Der Anruf konnte nicht eingerichtet werden.

2.  **Abbruchfehler:** Ein ausgehender Anruf wurde hergestellt und unerwartet beendet.

In diesem Abschnitt werden Methoden behandelt, um beide Bereiche zu untersuchen.

> [!NOTE]
> Nicht alle Berichte, die in den Vorlagen enthalten sind, werden in diesem Artikel behandelt. Die nachstehend erläuterten Methoden für Untersuchungen gelten jedoch weiterhin. Weitere Informationen finden Sie in der Beschreibung des jeweiligen Berichts.


### <a name="setup-failures"></a>Aufbaufehler

Priorisieren Sie zunächst die Behebung von Aufbaufehlern in diesem Bereich, da diese Fehler erhebliche negative Auswirkungen auf die Benutzererfahrung haben.

Starten Sie Ihre Untersuchung, indem Sie den Prozentsatz der gesamten Aufbaufehler für die Organisation abschätzen und dann die Untersuchungsbereiche auf der Grundlage des höchsten Prozentsatzes nach Gebäude oder Netzwerk priorisieren. 

#### <a name="setup-failure-trend-analysis"></a>Trendanalyse der Aufbaufehler

In diesem Bericht werden die Gesamtmenge der Datenströme, Fehler bei dem Datenstromaufbau und die Fehlerrate des Datenstromaufbaus angezeigt. Zeigen Sie auf eine der Spalten, um die einzelnen Werte anzuzeigen. 

##### <a name="analysis"></a>Analyse

Mit diesem Bericht können Sie die folgenden Fragen beantworten und Ihre nächste Vorgehensweise festlegen:

-   Wie hoch ist der Prozentsatz der Fehler bei dem Anrufaufbau für den laufenden Monat?

-   Liegt der Prozentsatz der Fehler bei dem Anrufaufbau unterhalb oder oberhalb der festgelegten Zielmetrik?

-   Ist der Fehlertrend schlechter oder besser als im vorhergehenden Monat?

-   Steigt der Fehlertrend, wird er stetig oder sinkt er?

Nehmen Sie sich die Zeit, unabhängig von Ihren Antworten auf diese Fragen weiter zu untersuchen, indem Sie die Begleitunterberichte verwenden, um nach einzelnen Gebäuden oder Subnetzen zu suchen, die möglicherweise korrigiert werden müssen. Obwohl die Gesamtfehlerrate möglicherweise unter der Zielmetrik liegt, sind die Fehlerraten für ein oder mehrere Gebäude oder Netzwerke möglicherweise über der Zielmetrik und benötigen Untersuchungen.

#### <a name="setup-failure-investigations"></a>Untersuchungen bei Aufbaufehlern 

Dieser Zusammenfassungsbericht wird verwendet, um Gebäude oder Netzwerke zu finden und zu isolieren, die ggf. eine Fehlerbehebung bedürfen.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Berichtsfilter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie den Berichtsfilter **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.

##### <a name="remediation"></a>Fehlerbehebung 

Konzentrieren Sie sich auf Gebäude oder Subnetze, die das größte Fehlervolumen aufweisen. Auf diese Weise können Sie die Auswirkungen auf die Benutzeroberfläche maximieren und so die Aufbaufehlerrate von Organisationsanrufen schnell reduzieren. In der folgenden Tabelle sind die zwei Gründe für Aufbaufehler aufgelistet, die von CQD gemeldet wurden.

| Gründe für Anrufaufbaufehler       | Typische Ursache                    |
|----------------------------------|----------------------------------|
| Fehlende Ausnahmeregel für FW-DPI (Deep Packet Inspection) | Deutet darauf hin, dass die Netzwerkausrüstung entlang des Pfads verhindert hat, dass der Medienpfad aufgrund von DPI-Regeln nicht erstellt wurde. Dies ist möglicherweise auf nicht ordnungsgemäß konfigurierte Firewallregeln zurückzuführen. In diesem Szenario war der TCP-Handshake erfolgreich, der SSL-Handshake jedoch nicht.      |
| Fehlende Ausnahmeregel für FW-IP-Block      | Gibt an, dass die Netzwerkausrüstung entlang des Pfads verhindert hat, dass der Medienpfad zum Microsoft 365 oder Office 365 Netzwerk eingerichtet wurde. Dies könnte darauf zurückzuführen sein, dass Proxy- oder Firewallregeln nicht ordnungsgemäß konfiguriert wurden, um den Zugriff auf die für Teams- und Skype for Business-Datenverkehr verwendeten IP-Adressen und Ports nicht ordnungsgemäß konfiguriert wurden. |

Wenn Sie mit der Wartung beginnen, können Sie sich auf ein bestimmtes Gebäude oder Subnetz konzentrieren. Wie in der vorstehenden Tabelle zu sehen ist, sind diese Probleme auf Firewall- oder Proxy-Konfigurationen zurückzuführen. Überprüfen Sie die in der folgenden Tabelle aufgeführten Optionen für Wartungsaktionen.

|      Fehlerbehebung      |Anleitung  |
|-----------------------|----------|
| Konfigurieren von Firewalls | Arbeiten Sie mit Ihrem Netzwerkteam zusammen, und überprüfen Sie die Konfiguration Ihrer Firewalls anhand [der Office 365 IP-Adressliste](/microsoft-365/enterprise/urls-and-ip-address-ranges).<br><br>Vergewissern Sie sich, dass die [Medien-Subnetze](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) und -Ports in den Firewallregeln enthalten sind. <br><br>Stellen Sie sicher, dass die [erforderlichen Ports](prepare-network.md) in der Firewall geöffnet sind. UDP sollte vorrangig sein, da TCP als Rückfallprotokoll für Audio-, Video- und videobasierte Bildschirmfreigaben betrachtet wird und deren Verwendung sich auf die Qualität des Anrufs auswirkt. Die alte RDP-Anwendungsfreigabe verwendet nur TCP.|

### <a name="drop-failures"></a>Abbruchfehler

Im Gegensatz zu Setupfehlercodes verfügt CQD über keinen Drop-Fehlercode, der angibt, warum Drop-Fehler auftreten, was es schwierig macht, eine bestimmte Ursache zu isolieren. Verwenden Sie einen abgeleiteten Ansatz, um Abbruchfehler besser zu erkennen. Durch die Behebung aller Bereiche, die für die Medien von Interesse sind, das Patchen von Clients und Treibern und die Nutzung zertifizierter Geräte für Teams und Skype for Business können Sie erwarten, dass die Zahl der Abbrüche zurückgehen wird.

#### <a name="drop-failure-trend-analysis"></a>Trendanalyse der Abbruchfehler

In diesem Bericht werden die Gesamtmenge der Audiodatenströme, die Gesamtanzahl der Abbruchfehler und die Abbruchfehlerrate angezeigt. Zeigen Sie auf eine der Spalten, um deren Werte anzuzeigen. 


##### <a name="analysis"></a>Analyse

Mithilfe dieser Art von Bericht können Sie die folgenden Fragen beantworten:

-   Was ist die aktuelle Abbruchfehlerrate?
-   Liegt die Abbruchfehlerrate unter der definierten Zielmetrik?
-   Ist der Fehlertrend schlechter oder besser als im vorhergehenden Monat?
-   Steigt der Fehlertrend, wird er stetig oder sinkt er?

Unabhängig von den Antworten auf den obigen Fragen sollten Sie sich die Zeit für eine Untersuchung nehmen, bei der Sie die zugehörigen Unterberichte verwenden, um nach Gebäuden oder Netzwerken zu suchen, die möglicherweise eine Fehlerbehebung bedürfen. Obwohl die Gesamtrate der Abbruchfehler möglicherweise unter der Zielmetrik liegt, sind die Fehlerraten für ein oder mehrere Gebäude oder Netzwerke möglicherweise über der Zielmetrik und benötigen Untersuchungen.

#### <a name="drop-failure-investigations"></a>Untersuchungen bei Abbruchfehlern

Die hier aufgeführten Fehler geben an, dass der Anruf unerwartet abgebrochen wurde und zu einer negativen Benutzererfahrung geführt hat. Im Gegensatz zu den Trendberichten bieten diese Berichte zusätzliche Einblicke in bestimmte Subnetze, die weitere Untersuchungen benötigen.


##### <a name="remediation"></a>Fehlerbehebung

Mithilfe der enthaltenen Tabellenberichte können Sie Problembereiche im Netzwerk isolieren, in denen die Droprate über der von Ihnen definierten Zielmetrik liegt. Konzentrieren Sie sich auf Gebäude oder Subnetze, die die höchste Gesamtzahl von Datenströmen aufweisen, um die größten Auswirkungen auf Gebäude oder Subnetze zu erzielen.

Häufige Ursachen von Anrufabbrüchen:

-   Netzwerk- oder Internetdatenverkehr mit unzureichenden Ressourcen
-   Kein QoS konfiguriert in eingeschränkten Netzwerken
-   Ältere Clientversionen
-   Benutzerverhalten

Nachdem Sie Ihre Problembereiche ermittelt haben, können Sie die [Anrufanalyse pro Benutzer](use-call-analytics-to-troubleshoot-poor-call-quality.md) verwenden, um Benutzer in diesem Gebäude auf bestimmte Probleme zu überprüfen. Die Anrufanalyse enthält zusätzliche EUII-Daten und kann nützlich sein, um potenzielle Gründe für die Drop-Fehler weiter zu isolieren.

Unabhängig von Ihrem nächsten Schritt ist es ratsam, Ihren Helpdesk darüber zu informieren, dass ein Problem mit bestimmten Gebäuden oder Subnetzen entdeckt wurde. Auf diese Weise kann der Helpdesk schnell auf eingehende Anrufe reagieren und Benutzer effizienter selektieren. Gekennzeichnete Benutzer können dann an das Entwicklungsteam zur weiteren Untersuchung zurückgemeldet werden.

Die folgende Tabelle enthält einige häufige Methoden zum Verwalten und Beheben von Abbruchfehlern.

| Fehlerbehebung                              | Anleitung                      |
|------------------------------------------|-------------------------------|
| **Netzwerk/ Internet**                         | **Überlastung**: Arbeiten Sie mit Ihrem Netzwerkteam zusammen, um die Bandbreite bei bestimmten Gebäuden/ Subnetzen zu überwachen, um zu bestätigen, dass es Probleme mit der Übernutzung gibt. Wenn Sie feststellen, dass es zu einer Netzwerküberlastung kommt, überlegen Sie sich, die Bandbreite zu diesem Gebäude zu erhöhen oder QoS anzuwenden. Verwenden Sie die integrierten [Zusammenfassungsberichte über Datenströme mit schlechter Qualität](#quality-investigations), um die problematischen Subnetze bei Problemen mit Jitter, Latenz und Paketverlusten zu überprüfen, da diese häufig einem abgebrochenen Datenstrom vorausgehen.<br><br>**QoS**: Wenn eine Erhöhung der Bandbreite unpraktisch oder unerschwinglich sein sollte, überlegen Sie sich, QoS zu implementieren. Dieses Tool eignet sich besonders für die Verwaltung von überlasteten Datenverkehr und kann dafür sorgen, dass Medienpakete im verwalteten Netzwerk Vorrang vor nicht-Mediendatenverkehr haben. Wenn es keine eindeutigen Beweise dafür gibt, dass die Bandbreite der Ursache ist, sollten Sie die folgenden Lösungen in Betracht ziehen:<ul><li>[Microsoft Teams QoS-Anleitung](qos-in-teams.md)</li></ul><br>**Ausführen einer Bewertung der Netzwerkbereitschaft**: Eine Netzwerkbewertung liefert Details über die erwartete Bandbreitennutzung, die Beherrschung von Bandbreiten- und Netzwerkänderungen sowie empfohlene Netzwerkpraktiken für Teams und Skype for Business. Wenn Sie die vorstehende Tabelle als Quelle verwenden, haben Sie eine Liste von Gebäuden oder Subnetzen, die hervorragende Kandidaten für eine Bewertung sind.<ul><li>[Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md)</li></ul> |
| **Clients (nur für Skype for Business Online)** | Einige ältere Skype for Business Clients haben bekannte, dokumentierte Probleme mit der Mediensicherheit. Überprüfen Sie die Anrufanalyseberichte mehrerer betroffener Benutzer oder erstellen Sie einen benutzerdefinierten Bericht in einer Client-Versionstabelle in CQD, gefiltert nach bestimmten Gebäuden oder Subnetzen mit der Messung der Gesamtzahl an Anrufabbruchfehler in %. Anhand dieser Informationen können Sie erkennen, ob eine Beziehung zwischen Anrufabbrüchen in diesem spezifischen Gebäude und einer bestimmten Version des Clients besteht.     |
| **Geräte**                                  |Wenn Geräte die Ursache für Probleme mit der Anrufqualität sind, sollten Sie problematische Geräte aktualisieren. Lesen Sie [Telefone für Teams](./devices/phones-for-teams.md), um mehr zu erfahren. |
| **Benutzerverhalten**                            | Wenn Sie feststellen, dass weder Netzwerk, noch Geräte oder Clients das Problem sind, sollten Sie die Entwicklung einer Benutzeradaptionsstrategie in Betracht ziehen, um die Benutzer darüber aufzuklären, wie sie am besten an Besprechungen teilnehmen und diese verlassen können. Besser vorbereitete Teams- und Skype for Business-Benutzer sorgen für eine bessere Benutzererfahrung für alle Teilnehmer. Beispielsweise wird ein Benutzer, der den Laptop in den Ruhezustand versetzt (durch Schließen des Deckels), ohne die Besprechung zu verlassen, als unerwarteter Anrufabbruch klassifiziert.   |

## <a name="quality-investigations"></a>Qualitätsuntersuchungen

Der nächste Schritt zur Einschätzung des Zustands der Audioqualität innerhalb der Organisation ist die Untersuchung schlechter Datenstromraten (PSR), TCP und Proxy-Nutzung. Es ist wichtig, sich daran zu erinnern, dass CQD-Daten ihnen keine bestimmte Ursache bieten, sondern Ihnen stattdessen wahrscheinlich Problembereiche zur Verfügung stellen, um eine gemeinsame Unterhaltung mit den entsprechenden Teams für Wartungsaktivitäten zu beginnen. 

> [!NOTE]
> Nicht alle Berichte, die in den Vorlagen enthalten sind, werden in diesem Artikel behandelt. Die nachstehend erläuterten Untersuchungsmethoden gelten jedoch weiterhin für diese Berichte. Weitere Informationen finden Sie in der Beschreibung des jeweiligen Berichts. 

### <a name="quality"></a>Qualität

Die PSR-Prozentsätze werden verwendet, um anzugeben, ob die Organisation die festgelegten Metrikziele für einen bestimmten Schwerpunktbereich erfüllt. Es ist wichtig zu beachten, dass selbst wenn die hohen Prozentsätze innerhalb des definierten Ziels liegen, einzelne Subnetze oder Gebäude die definierten Ziele möglicherweise nicht erfüllen und daher eine weitere Untersuchung benötigen. Wenn beispielsweise der Gesamtprozentsatz des Audio-PSR im April 2 Prozent beträgt, was der Zielvorgabe der Stichprobe entspricht, könnten einzelne Gebäude und Subnetze immer noch schlechte Erfahrungen machen, abhängig von der Gesamtverteilung dieser 2 Prozent. 

Wenn Sie den Prozentsatz schlechter Datenströme bewerten möchten, verwenden Sie die Qualitätsberichte. Es werden verschiedene Qualitätsberichte bereitgestellt, um Metriken der Gesamtzahl der Anrufe, Konferenz-, Zwei-Parteien-, PSTN-Anrufe, VPN und Besprechungsräume zu überprüfen. Zur Unterstützung bei diesem Vorgang werden monatliche, wöchentliche und tägliche Berichte bereitgestellt. Die wöchentlichen und täglichen Berichte beschränken sich auf die Vorlage "Verwaltete Netzwerke", um ihre Wirksamkeit zu erhöhen und Störungen zu reduzieren. 

#### <a name="quality-trend-analysis"></a>Qualitätstrendanalyse

Trendberichte zeigen Qualitätsinformationen über die Zeit an und dienen dazu, Qualitätstrends in jedem Interessengebiet zu erkennen und zu verstehen. Wie oben erwähnt, sind in den Vorlagen zur Untersuchung der Qualität Berichtsbäume enthalten; Konferenz-, Zweiparteien-, PSTN-Telefonie, VPN und Besprechungsräume. Der Untersuchungsprozess zur Analyse der Qualität ist identisch. Allerdings empfiehlt es sich, bei den Konferenzbesprechungen zu beginnen, da sich alle Verbesserungen bei der Konferenzqualität positiv auf alle anderen Bereiche auswirken. 

> [!Note]
> Die Untersuchung von Zwei-Parteien-Anrufe, PSTN-Telefonie und Besprechungsräumen ist ähnlich wie die Untersuchung von Konferenzgesprächen. Der Fokus liegt darauf, Gebäude oder Subnetze mit der schlechtesten Qualität zu isolieren und den Grund für die schlechte Qualität zu identifizieren.

> [!Important]
> VPN-basierte Berichte werden mithilfe der zweiten VPN-Dimension gefiltert. Diese Dimension setzt voraus, dass der VPN-Netzwerkadapter ordnungsgemäß als Fernzugriffadapter registriert ist. VPN-Anbieter verwenden dieses Kennzeichen nicht zuverlässig, und Ihre Laufleistung variiert je nach dem in Ihrer Organisation bereitgestellten VPN-Anbieter. Ändern Sie die [VPN-Berichte](CQD-upload-tenant-building-data.md#vpn) bei Bedarf mithilfe des Gebäude- oder Netzwerknamens.

##### <a name="investigation"></a>Untersuchung

Mithilfe dieser Berichte können Sie die folgenden Fragen beantworten:

-   Wie hoch ist die gesamte PSR für den aktuellen Monat?
-   Liegt die PSR unter der definierten Zielmetrik?
-   Ist die PSR schlechter oder besser als im vorhergehenden Monat?
-   Steigt die PSR, wird sie stetig oder sinkt sie?

Unabhängig von den Antworten auf den obigen Fragen sollten Sie sich die Zeit für eine Untersuchung nehmen, bei der Sie die zugehörigen Unterberichte verwenden, um nach Gebäuden oder Subnetzen zu suchen, die möglicherweise eine Untersuchung bedürfen. Obwohl die allgemeine PSR möglicherweise unter der Zielmetrik liegt, liegt die PSR für ein oder mehrere Gebäude oder Netzwerke häufig über der Metrik und muss korrigiert werden.

#### <a name="quality-investigations"></a>Qualitätsuntersuchungen

Die Zusammenfassenden Qualitätsberichte geben Ihnen einen tieferen Einblick in die Beiträge, die dazu beigetragen haben, dass die Datenströme als "schlecht" klassifiziert wurden, und helfen, Problembereiche im verwalteten Netzwerk zu isolieren.

Obwohl sich die verwendeten Dimensionen von Bericht zu Bericht leicht unterscheiden können, wird jeder Bericht Maßnahmen für Gesamtdatenströme, schlechte Gesamtdatenströme, PSR und schlechte Qualität aufgrund schlechter Qualität enthalten. Es wurden Berichte für jeden Interessenbereich erstellt: Konferenzen, Zwei-Parteien-Gespräche, PSTN-Anrufe, VPN und Besprechungsräume. Die Vorlage zu verwalteten Netzwerke enthält zusätzliche Berichte, um die Standortinformationen zu nutzen, die über die Gebäudedatei hochgeladen wurden.


> [!Note]
> Häufig verwendete Subnetze können aufgrund ihrer weit reichenden Nutzung nur schwer verfolgt werden. Der Vorlage "Alle Netzwerke" wurde ein separater Bericht hinzugefügt, in dem die öffentliche IP des Clients (Second Reflexive Local IP) angezeigt wird, um bei der Behebung von Büros zu helfen, die allgemeine Netzwerke verwenden.


![Screenshot der Zusammenfassung des schlechten Audiodatenstroms.](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Fehlerbehebung

Konzentrieren Sie sich auf Gebäude oder Subnetze, die über die größten Mengen an Datenströmen verfügen, da sich dadurch die Wirkung maximieren lässt und die Benutzererfahrung schnell verbessert wird. Verwenden Sie die Messungen für Jitter, Paketverlust und Roundtripzeit (RTT), um zu verstehen, was zur schlechten Qualität beiträgt (es ist möglich, dass mehrere Probleme auftreten):

-   **Jitter**: Medienpakete kommen mit unterschiedlichen Geschwindigkeiten an, was dazu führt, dass der Sprechende robotisch klingt.
-   **Paketverlust**: Medienpakete werden ausgelassen, was den Effekt von fehlenden Wörtern oder Silben erzeugt.
-   **RTT**: Medienpakete brauchen lange, um an ihr Ziel zu gelangen, wodurch ein Walkie-Talkie-Effekt entsteht.

Um Ihre Untersuchung von Qualitätsproblemen zu unterstützen, verwenden Sie die [Anrufanalyse pro Benutzer](use-call-analytics-to-troubleshoot-poor-call-quality.md). Mit der Anrufanalyse können Sie sich eine bestimmte Konferenz oder den Anrufbericht eines Benutzers ansehen. Dieser Bericht enthält EUII/PII-Daten und ist nützlich, wenn Sie nach der Ursache eines Fehlers suchen. Nachdem Sie erkannt haben, welche Gebäude betroffen sind, sollten Sie die Benutzer in diesem Gebäude einfach nachverfolgen. 

Vergessen Sie nicht, Ihrem Helpdesk mitzuteilen, dass bei diesen Netzwerken Qualitätsprobleme auftreten, damit sie eingehende Anrufe schnell triagen und beantworten können.

| Fehlerbehebung                              | Anleitung                         |
|------------------------------------------|----------------------------------|
| **Netzwerke**                                 | **Überlastung**: Ein überlastetes Netzwerk oder ein Netzwerk mit mangelhaften Ressourcen kann Probleme mit der Medienqualität verursachen. Arbeiten Sie mit dem Netzwerkteam zusammen, um festzustellen, ob die Netzwerkverbindungen vom Benutzer zum Internet-Ausgangspunkt über genügend Bandbreite zur Unterstützung der Medien verfügen. <br><br>**Ausführen einer Bewertung der Netzwerkbereitschaft**: Eine Netzwerkbewertung liefert Details über die erwartete Bandbreitennutzung, die Beherrschung von Bandbreiten- und Netzwerkänderungen sowie empfohlene Netzwerkpraktiken für Teams und Skype for Business. Wenn Sie die vorstehende Tabelle als Quelle verwenden, haben Sie eine Liste von Gebäuden oder Subnetzen, die hervorragende Kandidaten für eine Bewertung sind.<ul><li>[Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md)</li></ul>|
| **Quality of Service (QoS)**  | QoS ist ein bewährtes Tool, das die Priorisierung von Paketen in einem überlasteten Netzwerk unterstützt, um sicherzustellen, dass sie im Ganzen und pünktlich am Bestimmungsort ankommen. Erwägen Sie die Implementierung von QoS in Ihrer Organisation, um die Qualität der Benutzererfahrung zu maximieren, wenn die Bandbreite eingeschränkt ist. QoS hilft beim Beheben von Problemen, die normalerweise mit einem hohen Maß an Paketverlust verbunden sind, und – zu einem geringeren Grad – von Problemen mit Jitter und Round-trip-Zeiten.<ul><li>[Teams QoS-Anleitung](qos-in-teams.md)</li></ul> |
| **WLAN**               | WLAN kann sich erheblich auf die Anrufqualität auswirken. Wi-Fi Bereitstellungen berücksichtigen in der Regel nicht die Netzwerkanforderungen für VoIP-Dienste und sind häufig eine Quelle schlechter Qualität. Weitere Informationen zur Optimierung Ihrer WLAN-Infrastruktur finden Sie [in diesem Artikel über die WLAN-Planung](/skypeforbusiness/certification/plan-wifi).<br><br>**WLAN-Treiber**: Stellen Sie sicher, dass die Treiber für die WLAN-Verbindung auf dem neuesten Stand sind. Auf diese Weise können Sie die schlechte Benutzererfahrung im Zusammenhang mit einem veralteten Treiber verringern. Viele Organisationen schließen in ihren Patchzyklen keine Drahtlostreiber ein, und diese Treiber können jahrelang nicht gepatcht werden. Viele WLAN-Probleme werden behoben, indem sichergestellt wird, dass die WLAN-Treiber aktuell sind.<br><br>**WMM**: WMM (Wireless Multimedia Extensions), auch als WLAN-Multimedia bezeichnet, bieten grundlegende QoS-Funktionalitäten für drahtlose Netzwerke. Moderne drahtlose Netzwerke müssen viele Geräte unterstützen. Diese Geräte konkurrieren um die Bandbreite und können zu Qualitätsproblemen für VoIP-Dienste führen, bei denen Geschwindigkeit und Latenz am wichtigsten sind. Erkundigen Sie sich bei Ihrem WLAN-Anbieter nach den Einzelheiten und erwägen Sie die Implementierung von WMM in Ihrem WLAN-Netzwerk, um den Medien von Skype for Business und Teams Priorität einzuräumen.<br><br>**Zugriffspunktdichte**: Zugriffspunkte sind möglicherweise zu weit voneinander entfernt oder nicht an einer idealen Position. Um potenzielle Störungen zu minimieren, platzieren Sie zusätzliche Zugriffspunkte in Konferenzräumen und an Orten, die nicht durch Wände oder andere Objekte blockiert werden, an denen das Wi-Fi Signal schwach ist.<br><br>**2,4 GHz gegenüber 5 GHz**: 5 GHz bietet weniger Hintergrundinterferenzen und höhere Geschwindigkeiten und sollte bei der Bereitstellung von VoIP über WLAN bevorzugt werden. 5 GHz ist jedoch nicht so stark wie 2,4 GHz und dringt nicht so leicht in Wände ein. Überprüfen Sie Ihr Gebäude-Layout, um festzustellen, auf welche Frequenz Sie sich für die beste Verbindung verlassen können. |
|**Netzwerkgerät** | In größeren Unternehmen gibt es möglicherweise Hunderte von Geräten, die über das Netzwerk verteilt sind. Arbeiten Sie mit Ihrem Netzwerkteam zusammen, um sicherzustellen, dass die Netzwerkgeräte vom Benutzer bis zum Internet gewartet und auf dem neuesten Stand sind. |
| **VPN**  | VPN-Appliances wurden traditionell nicht für die Verarbeitung von Medienworkloads in Echtzeit entwickelt. Einige VPN-Konfigurationen verbieten die Verwendung von UDP (das bevorzugte Protokoll für Medien) und verlassen sich nur auf TCP. Erwägen Sie die Implementierung einer VPN-Lösung mit geteiltem Tunnel, um VPN als Quelle schlechter Qualität zu reduzieren. |
| **Clients** <br>(Nur für Skype for Business Online) | Stellen Sie sicher, dass alle Clients regelmäßig aktualisiert werden. |
| **Geräte** | Wenn Geräte die Ursache für Probleme mit der Anrufqualität sind, sollten Sie problematische Geräte aktualisieren. Lesen Sie [Telefone für Teams](./devices/phones-for-teams.md), um mehr zu erfahren. |
| **Treiber** | Patchen von Netzwerk (Ethernet und WLAN), Audio-, Video- und USB-Treibern sollten Bestandteil ihrer Gesamtstrategie zur Patchverwaltung sein. Viele Qualitätsprobleme werden durch das Aktualisieren von Treibern behoben. |
| **Konferenzräume mit WLAN** | Es wird dringend empfohlen, dass Konferenzraumgeräte mit mindestens 1 Gbit/s Ethernet-Verbindung mit dem Netzwerk verbunden sind. Konferenzraumgeräte umfassen in der Regel mehrere Audio- und Videodatenströme sowie Konferenzinhalte wie Bildschirmfreigaben und höhere Netzwerkanforderungen als andere Teams oder Skype for Business-Endpunkte. Konferenzräume sind definitionsgemäß stationäre Geräte, bei denen WLAN nur während der Installation einen Nutzen bringt.<br><br>Konferenzräume müssen mit besonderer Sorgfalt behandelt werden, um sicherzustellen, dass die Erfahrung mit diesen Geräten die Erwartungen erfüllt oder übersteigt. Qualitätsprobleme mit Besprechungsräumen werden in der Regel schnell eskaliert, da sie häufig von Mitarbeitern auf oberster Ebene verwendet werden.<br><br>Bei gleicher Leistung (abgesehen von der Bequemlichkeit) ist die WLAN-Leistung oft geringer als bei einer kabelgebundenen Verbindung. Mit dem Anstieg der "Bring Your Own Device"-Richtlinien und der Verbreitung von Laptops werden Wi-Fi Zugriffspunkte häufig überlastet. Echtzeit-Medien werden in WLAN-Netzwerken möglicherweise nicht priorisiert, was zu Qualitätsproblemen während der Zeiten mit stärkster Nutzung führen kann. Diese intensive Nutzung kann mit einer Besprechung zusammenfallen, bei der es ein Dutzend Personen gibt, die jeweils über einen eigenen Laptop und ein Smartphone verfügen, die alle mit demselben WLAN-Zugangspunkt wie das Gerät für den Besprechungsraum verbunden sind.<br><br>WLAN sollte nur als eine vorübergehende Lösung für eine mobile Installation oder wenn WLAN ordnungsgemäß für die Unterstützung von Echtzeit-Medien der Unternehmensklasse bereitgestellt wurde, in Betracht gezogen werden. |


### <a name="tcp"></a>TCP 

Transmission Control Protocol (TCP) gilt als Failback-Transport und nicht als primärer Transport für Echtzeitmedien. Der Grund, warum es sich um einen Failback-Transport handelt, ist auf die zustandsbehaftete Natur von TCP zurückzuführen. Wenn beispielsweise ein Anruf in einem latenten Netzwerk getätigt wird und Medienpakete verzögert werden, dann konkurrieren Pakete von vor einigen Sekunden, die nicht mehr nützlich sind, um Bandbreite, um zum Empfänger zu gelangen, was eine schlechte Situation verschärft. Dies führt dazu, dass die Audioqualitätsbehebung den Ton zusammenfügt und streckt, was zu hörbaren Artefakten führt, oft in Form von Jitter.

Die Berichte in diesem Abschnitt unterscheiden nicht zwischen guten und schlechten Datenströmen. Da UDP bevorzugt wird, suchen die Berichte nach der Verwendung von TCP für Audio, Video und videobasierte Bildschirmfreigabe (VBSS). Es werden schlechte Datenstromraten zur Ansicht bereitgestellt, um die UDP-Qualität im Vergleich zur TCP-Qualität zu vergleichen, damit Sie sich auf die größten Auswirkungen konzentrieren können. Die TCP-Nutzung wird in erster Linie durch unvollständige Firewallregeln verursacht. Weitere Informationen zu Firewallregeln für Teams und Skype for Business Online finden Sie [unter Microsoft 365 und Office 365 von URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges).

> [!Note]
> Audio, Video und VBSS bevorzugen alle UDP als ihren Haupttransport. Die alte Arbeitsauslastung für RDP-Anwendungsfreigabe verwendet nur TCP.

#### <a name="tcp-usage"></a>TCP-Nutzung

TCP-Berichte geben die gesamte TCP-Nutzung in den letzten sieben Monaten an. In allen anderen Berichten in diesem Abschnitt geht es um das einschränken bestimmter Gebäude und Subnetze, in denen TCP am häufigsten verwendet wird. Für Konferenzen und Datenströme mit zwei Parteien stehen separate Berichte zur Verfügung.

![Diagramm, das den Prozentsatz der Audiodatenströme zeigt, die TCP verwenden.](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Untersuchung

Mithilfe dieses Berichts können Sie die folgenden Fragen beantworten:

-   Wie hoch ist das Gesamtvolumen der TCP-Datenströme für den aktuellen Monat?
-   Ist es schlechter oder besser als im vorhergehenden Monat?
-   Steigt der Trend der TCP-Nutzung, wird er stetig oder sinkt er?
-   Ist die TCP-PSR identisch mit meiner gesamten PSR?

Wenn Sie feststellen, dass der TCP-Nutzungstrend zunimmt oder über die normale monatliche Nutzung hinausgeht, nehmen Sie sich die Zeit, um mit Hilfe der Unterberichte nach Gebäuden oder Netzwerken zu suchen, die möglicherweise eine Fehlerbehebung erfordern. Im Idealfall möchten Sie so wenige TCP-basierte Audiositzungen wie möglich im verwalteten Netzwerk haben.

#### <a name="tcp-vs-udp"></a>TCP vs. UDP

In diesem Bericht wird das Volumen der TCP- und UDP-Nutzung im letzten Monat für Audio, Video und videobasierte Bildschirmfreigabe (VBSS) angegeben. 

![Bericht mit dem Volumen der Datenströme, die TCP im Vergleich zu UDP verwenden.](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Analyse

Obwohl Sie die TCP-Nutzung so gering wie möglich halten wollen, kann es sein, dass Sie in einer ansonsten gesunden Bereitstellung ein wenig TCP-Nutzung sehen. TCP allein trägt nicht zu einem schlechten Anruf bei, daher werden Datenstromraten bereitgestellt, um zu ermitteln, ob die TCP-Nutzung einen Beitrag zu schlechter Qualität leistet. 

#### <a name="tcp-investigations"></a>TCP-Untersuchungen

Navigieren Sie in den bereitgestellten CQD-Vorlagen zu den TCP-Datenströmen nach Gebäude- und Subnetzberichten mithilfe der Vorlage „Verwaltete Netzwerke“ oder „Alle Netzwerke“. Um die TCP-Verwendung zu untersuchen, ist der Prozess identisch, daher konzentrieren wir uns hier auf Konferenzen.


##### <a name="remediation"></a>Fehlerbehebung

In diesem Bericht werden bestimmte Gebäude und Subnetze identifiziert, die zum Volumen der TCP-Nutzung beitragen. Außerdem wird ein weiterer Bericht hinzugefügt, um die Microsoft Relay-IP zu identifizieren, die beim Anruf verwendet wurde, um fehlende Firewallregeln zu isolieren. Konzentrieren Sie sich auf die Gebäude, die den größten Teil der TCP-Datenströme haben, um die Auswirkungen zu maximieren.

Die häufigste Ursache für die TCP-Nutzung sind fehlende Ausnahmeregeln in Firewalls oder Proxys. Wir werden im nächsten Abschnitt über Proxys sprechen, also konzentrieren Sie sich vorerst auf die Firewalls. Wenn Sie das bereitgestellte Gebäude oder Subnetz verwenden, können Sie ermitteln, welche Firewall aktualisiert werden muss.

| Fehlerbehebung        | Anleitung     |
|--------------------|--------------------------------------|
| Konfigurieren der Firewall | Stellen Sie sicher, dass [Microsoft 365 oder Office 365 IP-Ports und -Adressen](/microsoft-365/enterprise/urls-and-ip-address-ranges) von Ihrer Firewall ausgeschlossen sind. Konzentrieren Sie sich bei medienbezogenen TCP-Problemen zunächst auf Folgendes:<ul><li>Vergewissern Sie sich, dass die Medien-Subnetze 13.107.64.0/18 und 52.112.0.0/14 des Clients in ihren Firewallregeln enthalten sind.</li><li>UDP-Ports 3478–3481 sind die erforderlichen Media-Ports und müssen geöffnet werden, andernfalls kehrt der Client zurück zu TCP-Port 443.</li></ul> |
| Überprüfen             | Verwenden Sie das [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885), um probleme mit der Konnektivität mit bestimmten Microsoft 365 oder Office 365 IP-Adressen und Ports aus dem betroffenen Gebäude oder Subnetz zu überprüfen.    |

### <a name="http-proxy"></a>HTTP-Proxy

HTTP-Proxys sind aus einer Vielzahl von Gründen nicht der bevorzugte Pfad zum Einrichten von Mediensitzungen. Viele bieten umfassende Funktionen zur Paketprüfung, die verhindern, dass Verbindungen mit dem Dienst ausgeführt werden, wodurch Unterbrechungen auftreten. Darüber hinaus erzwingen nahezu alle Proxys TCP im Gegensatz zu der zuzulassenden UDP-Funktion, die für optimale Audioqualität empfohlen wird.

Es wird immer empfohlen, den Client so zu konfigurieren, dass er eine direkte Verbindung mit Teams und Skype for Business-Diensten herstellt. Dies ist besonders wichtig für den medienbasierten Datenverkehr.


> [!IMPORTANT]
> Es wird empfohlen, eine [gültige Gebäudedatei](CQD-upload-tenant-building-data.md) hochzuladen, damit Sie bei der Analyse der Proxynutzung innerhalb von externen Audiodatenströmen unterscheiden können. 


#### <a name="http-proxy-usage"></a>Nutzung von HTTP-Proxys

Der Bericht über den HTTP-Proxy-Datenstrom in diesem Abschnitt der Vorlage ähnelt den TCP-Berichten. Es wird nicht untersucht, ob Anrufe schlecht oder gut sind, sondern ob der Aufruf über HTTP verbunden ist.

![Screenshot des Berichts von Audiodatenströmen, die HTTP verwenden.](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Analyse

Sie möchten so wenige HTTP-Medienstreams wie möglich anzeigen. Wenn Sie Datenströme über Ihren Proxy laufen sehen, wenden Sie sich an Ihr Netzwerkteam, um sicherzustellen, dass die richtigen Ausschlüsse vorhanden sind, damit die Kunden direkt an die Teams oder die Mediensubnetze von Skype for Business Online weitergeleitet werden.

Wenn In Ihrer Organisation nur ein Internetproxy vorhanden ist, überprüfen Sie die [richtigen Microsoft 365 oder Office 365 URLs und IP-Adressbereichsausschlüsse](/microsoft-365/enterprise/urls-and-ip-address-ranges). Wenn in Ihrer Organisation mehrere Internet-Proxys konfiguriert sind, können Sie mit dem HTTP-Unterbericht isolieren, welches Gebäude oder Subnetz betroffen ist.

Stellen Sie für Organisationen, die den Proxy nicht umgehen können, sicher, dass der Skype for Business-Client so konfiguriert ist, dass er sich ordnungsgemäß anmeldet, wenn er sich hinter einem Proxy befindet, wie im Artikel [beschrieben, Skype for Business proxyserver verwenden sollten, um sich anzumelden, anstatt eine direkte Verbindung zu versuchen](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>HTTP-Proxy-Untersuchungen

In diesem Bericht werden bestimmte Gebäude und Subnetze identifiziert, die zur HTTP-Nutzung beitragen.


##### <a name="remediation"></a>Fehlerbehebung

Wir [empfehlen](proxy-servers-for-skype-for-business-online.md), dass Sie die Proxys für Skype for Business und Teams immer umgehen, insbesondere für Mediendatenverkehr. Da der Datenverkehr bereits verschlüsselt ist, wird Skype for Business durch Proxys nicht sicherer. Leistungsbezogene Probleme können durch Latenz und Paketverluste in die Umgebung eingebracht werden. Solche Probleme führen zu einer negativen Erfahrung mit Audio, Video und Bildschirmfreigaben, in denen Echtzeitdatenströme unerlässlich sind.

Die häufigste Ursache für die HTTP-Nutzung sind fehlende Ausnahmeregeln in Proxys. Wenn Sie das bereitgestellte Gebäude oder Subnetz verwenden, können Sie schnell ermitteln, welcher Proxy für die Medienumgehung konfiguriert werden muss.

Stellen Sie sicher, dass die erforderlichen [Microsoft 365 oder Office 365 FQDNs einer Zulassungsliste](/microsoft-365/enterprise/urls-and-ip-address-ranges) in Ihrem Proxy hinzugefügt werden.

## <a name="endpoint-investigations"></a>Endpunktuntersuchungen

In diesem Abschnitt geht es um die Aufgaben für die Berichterstattung über Client-Versionen und die Verwendung zertifizierter Geräte. Es stehen Berichte zur Verfügung, die die Verwendung für Clientversionen, den Clienttyp, Erfassungsgeräte und Treiber (Mikrofon), Videoerfassungsgeräte und WLAN-Anbieter- und Treiberversionen umreißen.

> [!NOTE]
> Nicht alle Berichte, die in den Vorlagen enthalten sind, werden in diesem Artikel behandelt. die nachstehend erläuterten Untersuchungsmethoden gelten jedoch weiterhin. Weitere Informationen finden Sie in der Beschreibung des jeweiligen Berichts.

### <a name="client-versions"></a>Clientversionen

Diese Berichte konzentrieren sich auf die Identifizierung Skype for Business verwendeten Clientversionen und deren relatives Volumen in der Umgebung.

> [!IMPORTANT]
> Derzeit werden Teams-Clients automatisch über das Azure Content Delivery Network verteilt und aktualisiert und vom Dienst auf dem neuesten Stand gehalten. Daher müssen Sie Teams Clientversionen nicht überwachen (es sei denn, Sie deaktivieren die automatische Aktualisierung, was nicht empfohlen wird).

Sofern Sie keine Verbunddaten über die Teilnehmer ausschließen, umfassen diese Berichte die Clienttelemetrie von verbundenen Endpunkten. Um Verbundendpunkte auszuschließen, müssen Sie einen Abfragefilter für die zweite Mandanten-ID hinzufügen, der auf die [Mandanten-ID](CQD-data-and-reports.md#how-to-find-your-tenant-id) Ihrer Organisation festgelegt ist. Alternativ können Sie einen [URL-Filter](CQD-data-and-reports.md#url-filters) verwenden, um die Telemetrie des Verbundteilnehmers auszuschließen.



#### <a name="remediation"></a>Fehlerbehebung

Ein wichtiger Teil der Gewährleistung einer qualitativ hochwertigen Benutzererfahrung besteht darin, sicherzustellen, dass die verwalteten Clients aktuelle Versionen von Skype for Business ausführen und dass die unterstützenden Audio-, Video-, Netzwerk- und USB-Treiber auf dem neuesten Stand sind. Das bietet verschiedene Vorteile, einschließlich: 

-   Es ist einfacher, einige Versionen im Vergleich zu vielen Versionen zu verwalten.
-   Dadurch wird eine gewisse Konsistenz der Benutzererfahrungen erreicht.
-   Dies erleichtert die Fehlersuche bei Problemen mit der Qualität von Anrufen und der Benutzerfreundlichkeit.
-   Microsoft führt kontinuierlich allgemeine Verbesserungen und Optimierungen im gesamten Produkt durch. Wenn Sie sicherstellen, dass Benutzer diese Updates erhalten, verringert sich das Risiko, dass ein bereits behobenes Problem auftritt.

Durch Einschränken ihrer Bereitstellung auf Clientversionen, die weniger als sechs Monate alt sind, können Sie die allgemeine Benutzererfahrung und die Verwaltbarkeit verbessern, indem Sie die Anzahl der unterstützten Versionen verringern.

Wenn Sie nur Office Klick-und-Los verwenden, befinden Sie sich automatisch innerhalb des Sechsmonatsfensters. Es sind keine weiteren Schritte erforderlich.

Wenn Sie über eine Kombination aus Klick-und-Los und Installationspaketen (MSI) verfügen, können Sie den Bericht verwenden, um zu überprüfen, ob die MSI-Clients regelmäßig aktualisiert werden. Wenn Sie feststellen, dass Clients zurückfallen, arbeiten Sie mit dem Team zusammen, das für die Verwaltung Office Updates verantwortlich ist, und stellen Sie sicher, dass sie Clientpatches regelmäßig genehmigen und bereitstellen.

Es ist auch wichtig zu berücksichtigen und sicherzustellen, dass die Netzwerk-, Video-, USB- und Audiotreiber ebenfalls gepatcht werden. Diese Treiber können leicht übersehen und dadruch nicht in Ihre Patch-Verwaltungsstrategie einbezogen werden.

Die Versionsnummern für Skype for Business finden Sie über die folgenden Links:

-   [Versionsinformationen für Updates für Microsoft 365 Apps](/officeupdates/release-notes-office365-proplus)
-   [Updateverlauf für Microsoft 365 Apps for Enterprise](/officeupdates/update-history-office365-proplus-by-date)
-   [Skype for Business – Downloads und Updates](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Geräte

Um den Bericht über das Mikrofongerät nutzen zu können, müssen wir das Konzept des Mean Opinion Score (MOS) verstehen. MOS ist die wichtigste Norm zur Messung der empfundenen Tonqualität. Es wird als eine ganzzahlige Bewertung von 0 bis 5 dargestellt.

Die Grundlage aller Messungen der Sprachqualität ist die Art und Weise, wie eine Person die Sprachqualität wahrnimmt. Weil es von der menschlichen Wahrnehmung beeinflusst wird, ist es inhärent subjektiv. Es gibt mehrere unterschiedliche Methoden für die subjektive Prüfung. Die meisten Messungen für die VoIP-Qualität basieren auf einer ACR (Absolute Categorization Rating, d.h. Absolute Kategorisierungsbewertung).

Bei einer subjektiven ACR-Prüfung bewertet eine statistisch signifikante Anzahl von Personen ihre Erlebnisqualität auf einer Skala von 1 (schlecht) bis 5 (ausgezeichnet). Der Mittelwert der Ergebnisse ist der MOS. Der resultierende MOS hängt von der Reichweite der Erfahrungen ab, die der Gruppe ausgesetzt waren, und von der Art der Erfahrung, die bewertet wird.

Da es unpraktisch ist, subjektive Tests der Sprachqualität für ein Live-Kommunikationssystem durchzuführen, generieren Microsoft Teams und Skype for Business MOS-Werte mithilfe fortschrittlicher Algorithmen, um die Ergebnisse eines subjektiven Tests objektiv vorherzusagen.

Der verfügbare Satz von MOS- und zugehörigen Metriken bietet einen Einblick in die Qualität der Benutzererfahrung, die von einem Audiogerät an die Benutzer gesendet wird. 

Indem Sie den Benutzern Geräte zur Verfügung stellen, die für Teams und Skype for Business zertifiziert sind, verringern Sie die Wahrscheinlichkeit negativer Erfahrungen, die auf das Gerät selbst zurückzuführen sind (was z. B. bei eingebauten Laptop-Lautsprechern und Mikrofonen wahrscheinlicher ist). Weitere Informationen finden Sie in diesen Artikeln über das [Zertifizierungsprogramm](/SkypeForBusiness/certification/overview) und den [Katalog der Partnerlösungen](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Die Geräteberichte werden verwendet, um die Gerätenutzung nach Volumen und MOS-Bewertung (nur Audio) zu bewerten, und sie sind in den zugehörigen Vorlagen unter Clients & Geräte zu finden. 

> [!IMPORTANT]
> Sofern Sie keine Verbunddaten über die Teilnehmer ausschließen, umfassen diese Berichte die Clienttelemetrie von verbundenen Endpunkten. Um Verbundendpunkte auszuschließen, müssen Sie einen Abfragefilter für **die zweite Mandanten-ID** hinzufügen, der auf die [Mandanten-ID](CQD-data-and-reports.md#how-to-find-your-tenant-id) Ihrer Organisation festgelegt ist. Alternativ können Sie einen [URL-Filter](CQD-data-and-reports.md#url-filters) verwenden, um die Telemetrie des Verbundteilnehmers auszuschließen.


> [!Note]
> Möglicherweise bemerken Sie beim Anzeigen dieses Berichts, dass das gleiche Gerät mehrmals gemeldet wurde. Dies ist auf die Art und Weise zurückzuführen, wie das Gerät an das CQD gemeldet wird. Unterschiede in der Hardware und im Betriebssystem-Gebietsschema führen zu Unterschieden in der Art und Weise, wie Gerätedaten gemeldet werden.

##### <a name="remediation"></a>Fehlerbehebung

In der Regel müssen Sie nicht zertifizierte Geräte ermitteln und auslaufen lassen und durch zertifizierte Geräte ersetzen. Einige Überlegungen bei der Überprüfung der Geräteberichte umfassen:

-   Sind die verwendeten Geräte für Teams und Skype for Business zertifiziert? 
-   Mithilfe der [Anrufanalyse pro Benutzer](use-call-analytics-to-troubleshoot-poor-call-quality.md) können Sie Benutzer eines bestimmten Geräts identifizieren. Stellen Sie sicher, dass sie über die neuesten Gerätetreiber verfügen und dass ihr Gerät nicht über einen USB-Hub oder eine Dockingstation verbunden ist. 
-   Wie viele verschiedene Versionen unterschiedlicher Treiber werden verwendet? Werden diese regelmäßig gepatcht? Wenn Sie sicherstellen, dass Audio-, Video- und WLAN-Treiber regelmäßig gepatcht werden, können Sie diese als Quelle für Qualitätsprobleme ausschließen und die Benutzererfahrung vorhersehbarer und konsistenter machen.

##### <a name="audio"></a>Audio

Die nächste Aufgabe besteht darin, die allgemeine Nutzung von [zertifizierten Audiogeräten](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) zu ermitteln. Wir empfehlen, dass mindestens 80 Prozent aller Audiodatenströme über ein zertifiziertes Audiogerät erfolgen. Dazu exportieren Sie den Bericht "Mikrofongeräte" nach Excel, um die Verwendung von zertifizierten oder zugelassenen Geräten zu berechnen. Die Organisationen führen in der Regel eine Liste aller zugelassenen Geräte aus, daher sollten Sie die Daten ohne Weiteres filtern und sortieren können.

##### <a name="video"></a>Video

Außerdem ist es wichtig, dass Videotreiber aktualisiert werden. Wenn Sie sicherstellen, dass Videokarten regelmäßig gepatcht werden, können Sie die Videotreiber als Quelle schlechter Qualität für Videodatenströme ausschließen. Die Verwendung [zertifizierter Videogeräte](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) trägt dazu bei, eine reibungslose und qualitativ hochwertige Benutzererfahrung zu gewährleisten. Videogeräte, die die native Codierung von H.264 unterstützen, werden bevorzugt, um die CPU-Auslastung während Videokonferenzen zu verringern.

##### <a name="wi-fi"></a>WLAN

Außerdem müssen die WLAN-Treiber in regelmäßigen Abständen gepatcht werden und sollten in Ihre Patch-Verwaltungsstrategie einbezogen werden. Viele Qualitätsprobleme lassen sich beheben, indem Sie die WLAN-Treiber auf dem neusten Stand halten. Weitere Informationen zur Optimierung Ihrer WLAN-Infrastruktur finden Sie [in diesem Artikel über die WLAN-Planung](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Advisor für Teams](use-advisor-teams-roll-out.md)

[Vorbereiten Ihres Netzwerks für Teams](prepare-network.md)

[Prinzipien von Office 365-Netzwerkverbindungen](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams – Analyse und Berichterstellung](teams-analytics-and-reports/teams-reporting-reference.md)

[Verwalten Ihrer Geräte in Teams](./devices/device-management.md).

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitäts-Dashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[In CQD verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
