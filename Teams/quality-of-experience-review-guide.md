---
title: Verwenden des AQD zum Verwalten der Anruf- und Besprechungsqualität in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Erfahren Sie, wie Sie die Leistung von Echtzeitmedien in Microsoft Teams mithilfe des Anrufqualitätsdashboards analysieren und verwalten.
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
ms.openlocfilehash: 275d1c9b3b60a5a1cd25c0991e35f40712fa332e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627317"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Verwenden des AQD zum Verwalten der Anruf- und Besprechungsqualität in Microsoft Teams 

Dieser Artikel hilft Ihnen – Teams-Administrator oder Support- und Helpdesk-Entwickler – beim Entwickeln eines Prozesses zum Überwachen und Verwalten der Anruf- und Besprechungsqualität für Ihre Organisation mithilfe des Microsoft Teams-Anrufqualitäts-Dashboards (CQD). Unsere Anleitungen heben Szenarien für die Audioqualität hervor, da alle Netzwerkverbesserungen, die Sie zur Verbesserung der Audioqualität vorgenommen haben, Zu Verbesserungen bei Video und Freigabe führen.

Schlüssel zu dieser Anleitung sind die beiden kuratierten [CQD-Vorlagen–](https://aka.ms/QERtemplates) wir empfehlen, sie herunterzuladen, bevor Sie die Anleitungen in diesem Artikel durchgehen.

In diesem Artikel wird davon ausgegangen, dass Sie [das CQD bereits eingerichtet haben.](turning-on-and-using-call-quality-dashboard.md)


## <a name="categories-to-monitor-and-maintain"></a>Kategorien zum Überwachen und Verwalten

Sobald Sie Besprechungen und Sprachanrufe in Teams haben, benötigen Sie einen Plan für die kontinuierliche Überwachung und Wartung. Dadurch wird sichergestellt, dass Teams immer optimal ausgeführt wird. Dieser Plan sollte die unten aufgeführten Hauptbereiche enthalten. Sie sollten auch Ziele für Qualitätsmetriken festlegen und einen Plan für die Behandlung und Isolierung von Problemen festlegen, sobald diese auftreten.

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
<p>Unterlegen Sie die Metriken nach internen Anrufen (innerhalb Ihrer Organisation, z. B. VPN, WLAN, verkabelt) oder externen Anrufen.</p>
<p>Aufbrechen der Metriken durch Erstellen oder Netzwerk</p>
<p>VPN-Anrufe</p>
<p>Anrufe mit TCP, UDP oder Proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Zuverlässigkeit bei Anrufen</strong></td>
<td><p>Identifizieren und Beheben von Netzwerk- oder Firewallproblemen</p>
<p>Gewinnen Sie Einblicke in die Prozentsätze von Anrufeinrichtungs- und Drop-Fehlern</p>
<p>Hier erfahren Sie, wo die meisten Fehler beim Einrichten und Ablegen von Anrufen auftreten.</p>
</td>
</tr>
<tr class="odd">
<td><strong>Benutzerumfrage</strong></td>
<td>
<p>Verwenden Von "Meinen Anruf bewerten"-Daten, um mehr über die tatsächliche Benutzererfahrung zu erfahren</p>
<p>Wo befinden sich die schlechten Erfahrungen?</p>
<p>Korrelieren der schlechten Benutzererfahrung mit Anrufqualität, Zuverlässigkeit und Geräten</p>
</td>
</tr>
<tr class="even">
<td><strong>Geräte</strong></td>
<td><p>Erfahren Sie, welche Mikrofone und Lautsprecher am häufigsten verwendet werden und welche Auswirkungen dies auf die Anrufqualität hat.</p>
<p>Werden für die unterstützenden Audio-, Video-, USB- und WLAN-Treiber regelmäßig Patches installiert?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clients</strong></td>
<td>
<p>Erfahren Sie, welche Clienttypen und Versionen verwendet werden und welche Auswirkungen dies auf Anrufqualität und Zuverlässigkeit hat.  </p>
</ol></td>
</tr>
</tbody>
</table>

Durch die kontinuierliche Bewertung und Behebung der in diesem Artikel beschriebenen Bereiche können Sie deren potenzielle negative Auswirkungen auf die Benutzer verringern. Die meisten Benutzerprobleme können in die folgenden Kategorien eingeteilt werden:

-   Unvollständige Firewall- oder Proxykonfiguration
-   Schlechte WLAN-Abdeckung
-   Unzureichende Bandbreite
-   VPN
-   Inkonsistente oder veraltete Clientversionen und Treiber
-   Nicht optimierte oder integrierte Audiogeräte
-   Problematische Subnetze oder Netzwerkgeräte

Durch die ordnungsgemäße Planung und Gestaltung vor der Bereitstellung von Teams oder Skype for Business Online können Sie den Aufwand verringern, der erforderlich ist, um die hohe Qualität des Erlebnisses aufrechtzuerhalten.

Dieser Artikel konzentriert sich auf die Verwendung des Anrufqualitätsdashboards (CQD) Online als primäres Tool zum Melden und Untersuchen der einzelnen Bereich, mit einem besonderen Schwerpunkt auf Audio, um die Verbreitung und die Auswirkungen zu maximieren. Alle zur Optimierung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Um Ihre Bewertung zu beschleunigen, werden [zwei zusammengestellte CQD-Vorlagen](https://aka.ms/qertemplates) bereitgestellt: eine ist für die Verwaltung aller Netzwerke und die andere wird nur nach verwalteten (internen) Netzwerken gefiltert. Obwohl die Vorlagenberichte „Alle Netzwerke“ so konfiguriert sind, dass sie Gebäude- und Netzwerkinformationen anzeigen, können sie dennoch verwendet werden, während Sie auf die Erfassung und das Hochladen von Gebäudeinformationen hinarbeiten. Durch das Hochladen von Gebäudeinformationen in CQD kann der Dienst die Berichterstellung verbessern, indem benutzerdefinierte Gebäude-, Netzwerk- und Standortinformationen hinzugefügt werden, wobei zwischen internen und externen Subnetzen unterschieden wird. Weitere Informationen finden Sie unter [Gebäudezuordnung.](CQD-building-mapping.md)

### <a name="intended-audience"></a>Zielgruppe

Dieser Artikel soll von Partnern und Kunden mit Rollen wie "Lead/Architect", "Berater", "Change Management/Adoption Specialist", "Support/Helpdesk Lead", "Network Lead", "Desktop Lead" und "IT-Administrator" verwendet werden.

Dieser Artikel ist auch für die Verwendung durch die designierten Qualitäts-Champion(en) bestimmt. Weitere Informationen finden Sie unter [Die Rolle des Qualitätspioniers](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>Was ist Qualität?

In diesem Zusammenhang ist Qualität eine Kombination aus Dienstmetriken und Benutzeroberfläche.


### <a name="service-metrics"></a>Dienstmetriken

Die Dienstmetriken umfassen bestimmte clientbasierten Metriken. Während jedes Anrufs erfasst der Client Telemetrie für den Anruf und übermittelt am Ende jedes Anrufs einen Bericht, auf den später über das CQD oder in der Anrufanalyse pro Benutzer zugegriffen werden [kann.](set-up-call-analytics.md) Diese Metriken umfassen (aber sind nicht beschränkt auf):

-   Poor Stream (posteingangs- und ausgehender Datenstrom)
-   Aufbaufehlerrate
-   Abbruchfehlerrate


#### <a name="poor-stream-rate"></a>Schlechte Datenstromrate

Die schlechte Datenstromrate (PSR) stellt den Gesamtprozentsatz der Datenströme in der Organisation dar, die eine schlechte Qualität haben. Diese Metrik soll Bereiche hervorheben, auf die sich Ihre Organisation konzentrieren kann, um den größten Einfluss auf die Reduzierung dieses Wertes und die Verbesserung des Benutzererlebnisses zu erzielen. Deshalb stehen [verwaltete Netzwerke](#managed-versus-unmanaged-networks) bei der Betrachtung des PSR im Vordergrund. Externe Benutzer sind ebenfalls wichtig, die Untersuchungen sind aber für die verschiedenen Betriebsebenen unterschiedlich. Überlegen Sie sich, bewährte Methoden für externe Benutzer bereitzustellen und externe Anrufe unabhängig von der Gesamtorganisation zu untersuchen.

Die tatsächliche Messung im AQD variiert je nach Arbeitsauslastung, aber im Sinne dieses Artikels konzentrieren wir uns in erster Linie auf die Messung _"Audio poor Percentage"._ Die PSR besteht aus den fünf durchschnittlichen Netzwerkmetriken, die in der folgenden Tabelle beschrieben sind. Damit ein Strom als schwach eingestuft wird, muss nur eine der Metriken den definierten Grenzwert überschreiten. Das CQD stellt die "Poor Due To..." um besser zu verstehen, welche Bedingung dazu führte, dass der Datenstrom als "schlecht" klassifiziert wurde. Weitere Informationen finden Sie unter [Streamklassifizierung im CQD.](stream-classification-in-call-quality-dashboard.md)

> [!Note]
> Im CQD wird der "Schlecht aufgrund..." um besser zu verstehen, welche Bedingung dazu führte, dass der Datenstrom als "schlecht" klassifiziert wurde.


##### <a name="audio-poor-quality-metrics"></a>Metriken für schlechte Audioqualität

| Mittelwert der Metrik     | Beschreibung     | Benutzererfahrung |
|-------------|-----------------|-----------------|
| Jitter \>30 ms        | Dies ist die durchschnittliche Änderung bei der Verzögerung zwischen aufeinander folgenden Paketen. Teams und Skype for Business können ein gewisses Maß an Jitter durch Pufferung ausgleichen. Erst wenn der Jitter die Pufferung überschreitet, bemerkt ein Teilnehmer die Auswirkungen von Jitter.      | Die Pakete, die mit unterschiedlichen Geschwindigkeiten empfangen werden, führen dazu, dass die Stimme eines Lautsprechers klingt.   |
| Paketverlustrate \>10 % oder 0,1        | Diese Eigenschaft wird oft als prozentualer Anteil der Pakete gemessen, die verloren gegangen sind. Paketverluste wirken sich direkt auf die Audioqualität aus. Sie reichen vom Verlust einzelner kleiner Pakete, der fast keine Auswirkung hat, bis hin zu direkt aufeinander folgenden Burstverlusten, die zu Tonaussetzern führen.     | Die verworfenen und nicht am vorgesehenen Bestimmungsort ankommenden Pakete führen zu Lücken in den Medien, was zu fehlenden Silben und Wörtern sowie abgehacktem Video und Störungen bei der Freigabe führen kann. |
| Round-trip-Zeit \>500 ms        | Dies ist die Zeit, die benötigt wird, um ein IP-Paket von Punkt А nach Punkt B und zurück zu Punkt А zu senden. Diese Verzögerung der Weitergabe im Netzwerk ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verknüpft. Dazu gehört auch der Mehraufwand durch die zwischen den Punkten vorhandenen Geräten.      | Die Pakete, die zu lange dauern, bis sie an Ihr Ziel gelangen, führen zu einem Walkie-Talkie-Effekt.   |
| NMOS-Beeinträchtigungsdurchschnitt \>1,0         | Durchschnittliche Beeinträchtigung des [Netzwerk-MOS (Mean Opinion Score)](/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) für den Datenstrom. Stellt dar, wie stark sich der Netzwerkverlust und der Jitter auf die Qualität des empfangenen Audios auswirkten, das dazu führte, dass der NMOS um mehrere Punkte sank. | Hierbei handelt es sich um eine Kombination aus Jitter, Paketverlust und – zu einem geringeren Grad – erhöhter Round-trip-Zeit. Möglicherweise erfährt der Benutzer eine Kombination dieser Symptome.   |
| Durchschnittsanteil der verdeckten Beispiele \>7 % oder 0,07 | Durchschnittliches Verhältnis der Anzahl der Audioframes mit verdeckten Beispielen, die durch die Paketverlustreparatur generiert wurden, zur Gesamtzahl der Audioframes. Versteckte Audiobeispiele sind ein Verfahren zum „Glätten“ der „holprigen“ Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.      | Ein hoher Wert gibt an, dass Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Warum verwenden wir lieber Datenströme als Anrufe?

Streams uns wissen lassen, welcher Teil des Anrufs schlecht war – ausgehend oder eingehend. Wenn Sie die Anrufanalyse für einen schlechten Anruf überprüfen möchten, ermitteln Sie, ob der schlechte Anruf auf den Datenstrom (ausgehend) oder den Datenstrom des Anrufers (eingehende) des Anrufers zurück ging. Für Konferenzen ist es noch wichtiger zu bestimmen, welcher Datenstrom sich auf die Anrufqualität auswirken soll. Wenn Sie nur Anrufdaten anzeigen, sehen Sie, an wie vielen Konferenzen eine Person teil nimmt, aber Sie sehen nicht, welche Personen aktive Lautsprecher sind, da Sie die meisten Bildschirmfreigaben machen.

Anrufdaten geben Ihnen Nutzungsmetriken, führen aber nicht zwangsläufig zur Ursache für eine schlechte Anrufqualität. Wenn Sie sich die Datenstromrichtung anschauen, können Sie Faktoren erkennen, z. B. einen Anruf, der nicht in einem verwalteten Netzwerk geführt wird, oder einen Anruf von einem Mitarbeiter (z. B. einem Lieferanten oder einer Person in einem anderen Netzwerk). Wenn die Netzwerkverbindung der anderen Person in diesen Fällen schlecht war, wird der gesamte Anruf als "schlecht" gekennzeichnet. Sie können keine externen Faktoren berücksichtigen, daher sind diese Daten nicht hilfreich.

Die Datenstromrichtung kann Ihnen auch dabei helfen, problematische Geräte oder Clients zu identifizieren.

 - Wenn Sie beispielsweise nur über ein begrenztes Budget für Geräte verfügen und Geräte nur für Nutzer mit starken Audiodaten bereitstellen möchten, verwenden Sie den Audioverwendungsbericht (VoIP) und filtern Sie nach ausgehenden Datenströmen und Konferenzen. Suchen Sie nach Audiobenutzern mit hoher Lautstärke, die in integrierte Mikrofone sprechen. Diese korrelieren möglicherweise mit einer schlechteren Anrufqualität (und Möglicherweise möchten Sie für diese Personen Audiogeräte bereitstellen). Um mehr Klarheit zu schaffen, könnten Sie nach Paketauslastung filtern, wodurch Sie besonders große Audiogeräte verwenden können. 

  - Ein weiteres Beispiel ist die Bildschirmfreigabe. Wenn ein Kunde einen alten Teams verwendet, kann die Leistung der Bildschirmfreigabe beeinträchtigt werden. Sie könnten dieses Problem beheben, indem Sie Kundenupgrades für Personen mit einer großen Bildschirmfreigabe priorisieren.

 - Indem Sie feststellen, welche Richtung eines Datenstroms zu einer schlechten Anrufqualität führt, können Sie feststellen, ob ein QoS- oder Bandbreitenproblem vor liegt. Wenn Sie QoS noch nicht vollständig implementiert haben oder nur Pakete auf dem Client und nicht im eingehenden Datenstrom markieren, wird möglicherweise eine schlechtere Anrufqualität zu sehen sein. Wenn Sie sich die Datenstromrichtung ansehen, erhalten Sie eine genauere Ansicht des Paketverlusts, der Latenz oder des Jitters in einer bestimmten Richtung. 

   - Nehmen wir beispielsweise an, ein Benutzer beschwert sich über Audiowiedergabe über eine Kabelverbindung (Jitter). Wenn Sie sich den Datenstrom und die Richtung anschauen, können Sie feststellen, dass das Problem nur für eine bestimmte Gruppe von Subnetzen im eingehenden Datenstrom vor liegt. Nachdem Sie Ihrem Netzwerkteam diese Informationen zur Verfügung haben, kann es sie bis zu einem falsch konfigurierten WAN-Beschleuniger nachverfolgen, der den Medienverkehr nicht umgangen hat. Sobald das Netzwerkteam den WAN-Beschleuniger neu konfiguriert hat, verschwindet Jitter, und die Anrufqualität verbessert sich. 


#### <a name="setup-failure-rate"></a>Aufbaufehlerrate

Die Fehlerrate bei der Einrichtung, auch als Messung "Total _Call Setup Failure Percentage"_ (Prozentsatz der Gesamtanrufeinrichtungsfehler im Anruf-CQD) bezeichnet, ist die Anzahl der Datenströme, für die der Medienpfad zwischen den Endpunkten am Anfang des Anrufs nicht eingerichtet werden konnte.

Dies stellt einen Medienstream dar, der nicht aufgebaut werden konnte. Angesichts des Schweregrads der Auswirkungen dieses Problems auf die Benutzerfreundlichkeit ist es das Ziel, diesen Wert so nahe wie möglich auf null zu verringern. Ein hoher Wert für diese Metrik ist bei neuen Bereitstellungen mit unvollständigen Firewallregeln gebräuchlicher als eine reife Bereitstellung, aber es ist trotzdem wichtig, sie in regelmäßigen Abständen zu beobachten.

Diese Metrik wird berechnet, indem die Gesamtzahl der Ströme, die nicht eingerichtet werden konnten, durch die Gesamtzahl der Ströme geteilt wird, die einen erfolgreichen Kommunikationsdatensatz (Call Detail Record, CDR) gesendet haben:

-   **Aufbaufehlerrate** = Gesamtanzahl der Ströme mit Ausfall des Rufaufbaus / Gesamtzahl der Ströme mit verfügbarem CDR

#### <a name="drop-failure-rate"></a>Abbruchfehlerrate

Die Drop-Fehlerrate( auch bekannt als Messung des Prozentsatzes des Total _Call Dropped Failure im_ CQD) ist der Prozentsatz der erfolgreich aufgebauten Datenströme, bei denen der Medienpfad nicht normal beendet wurde.

Das steht für jeden Medienstrom, der unerwartet beendet wurde. Obwohl die Auswirkungen hier nicht so stark wie bei einem Datenstrom sind, der nicht eingerichtet werden konnte, wirkt sich dies trotzdem negativ auf die Benutzererfahrung aus. Plötzliche und häufige Medienverluste können nicht nur schwerwiegende Auswirkungen auf die Benutzererfahrung haben, sondern auch dazu führen, dass die Benutzer erneut eine Verbindung herstellen müssen, was zu einem Produktivitätsverlust führt (nicht zu Frust).

Die Metrik wird berechnet, indem die Gesamtzahl der abgebrochenen Ströme durch die Gesamtzahl der erfolgreich aufgebauten Datenströme dividiert wird:

-   **Abbruchfehlerrate** = Gesamtanzahl der abgebrochenen Anrufströme / Gesamtzahl der Ströme mit erfolgreichem Rufaufbau

### <a name="define-your-target-metrics"></a>Definieren Ihrer Zielmetriken

In diesem Abschnitt werden einige der wichtigsten Dienstmetriken erläutert, die wir zum Bewerten der Integrität der Dienste verwenden. Indem Sie diese Metriken kontinuierlich bewerten und die Leistung unter ihren definierten Zielen halten, tragen Sie dazu bei, für Ihre Benutzer eine konsistente und zuverlässige Anrufqualität zu gewährleisten. Verwenden Sie als Ausgangspunkt die vorgeschlagenen Ziele in der nachstehenden Tabelle. Passen Sie die Ziele nach Bedarf an, um Ihre Geschäftsziele zu erreichen.

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

Das Analysieren der Benutzererfahrung ist mehr Kunst als Wissenschaft, da die hier gesammelten Metriken nicht immer bedeuten, dass es ein Problem mit dem Netzwerk oder Dienst gibt, sondern lediglich, dass der Benutzer ein Problem wahr nimmt. Das CQD umfasst einen integrierten Umfragemechanismus – Bewerten meines Anrufs (Rate My Call, RMC), um die Gesamtbenutzerfreundlichkeit zu messen. RMC bietet Ihnen Einblicke in die folgenden Fragen aus der Perspektive Ihrer Benutzer:

-   Weiß ich, wie die Lösung zu verwenden ist?
-   Ist die Lösung benutzerfreundlich und intuitiv und unterstützt Sie die täglichen Kommunikationsanforderungen?
-   Hilft mir die Lösung beim erledigen meiner Aufgabe?
-   Wie sieht meine Gesamtwahrnehmung der Lösung aus?
-   Kann ich die Lösung jederzeit verwenden – unabhängig davon, wo ich gerade bin?
-   Kann ich einen Anruf aufbauen und aufrechterhalten?

#### <a name="rate-my-call"></a>Meinen Anruf bewerten 

"Meinen Anruf bewerten" (Rate My Call, RMC) ist in Teams und Skype for Business. Er wird automatisch nach einem in jedem 10-Anruf oder 10 Prozent angezeigt. In dieser kurzen Umfrage wird der Benutzer gebeten, den Anruf zu bewerten und ein wenig Kontext dafür zu liefern, warum die Anrufqualität schlecht gewesen sein könnte. Ein oder zwei Bewertungen werden als unzureichend betrachtet, drei bis vier sind gut und fünf ist ausgezeichnet. Obwohl es sich um einen eher lausenden Indikator handelt, ist dies eine hilfreiche Metrik zum Aufdecken von Problemen, die bei Dienstmetriken auftreten können.

> [!Note]
> Der Menschliche Faktor: Benutzer ignorieren die Umfrage häufig, wenn die Anrufqualität gut ist, und füllen sie aus, wenn die Anrufqualität schlecht ist. Dies kann dazu führen, dass Ihre RMC-Berichte auf die schlechte Seite verzerrt sind, auch wenn die Dienstmetriken gut sind.

Sie können CQD verwenden, um über die Benutzerreaktionen von RMC zu berichten und Beispielberichte sind in der CQD-Vorlage enthalten. Sie werden jedoch nicht detailliert in diesem Artikel erläutert. 

#### <a name="client-and-device-readiness"></a>Client- und Gerätebereitschaft

Sie benötigen eine solide Client- und Gerätestrategie, um sicherzustellen, dass Ihre Benutzer eine konsistente und positive Benutzererfahrung haben. Jede Bereitschaftsstrategie beruht auf einigen wenigen Schlüsselprinzipien.

##### <a name="client-readiness"></a>Client-Bereitschaft

Indem Sie Teams auf dem neuesten Stand halten, stellen Sie sicher, dass Die Benutzer immer die bestmögliche Benutzererfahrung erhalten. Microsoft veröffentlicht häufige Updates für den [Teams-Client](teams-client-update.md) (das Update wird automatisch im Hintergrund installiert, es sei denn, Sie haben diese Funktionalität deaktiviert ( was von uns nicht empfohlen wird). Außerdem ist es wichtig, an das Patchen von Netzwerk-, Video-, USB- und Audiotreibern zu denken, da diese häufig übersehen werden und sich auf die Anruf- und Besprechungsqualität auswirken können. Überlegen Sie sich, Netzwerk-, WLAN-, Video-, USB -und Audiotreibern zum aktuellen Patchverwaltungsvorgang hinzuzufügen.


##### <a name="device-readiness"></a>Gerätebereitschaft

Keine einzelne Strategie kann das Benutzererlebnis mehr beeinflussen als Ihre Strategie zur Gerätebereitschaft. Beispielsweise erleben Benutzer, die auf ihre Laptoplautsprecher und das Mikrofon angewiesen sind, bei Anrufen und Besprechungen eine Menge Hintergrundgeräusche. Teams ist für die Arbeit mit fast jedem Gerät konzipiert. Wenn Sie jedoch gerätebezogene Probleme haben, suchen Sie in Telefon [nach Teams.](./devices/phones-for-teams.md)


### <a name="categories-of-quality"></a>Qualitätskategorien

Operationalisieren Sie eine Reihe von Qualitätsmanagementpraktiken – Dadurch erhalten Sie die beste Chance für eine gute Anruf- und Besprechungsqualität. Ein guter Qualitätsmanagementplan befasst sich mit den folgenden Kategorien:

-   **Netzwerk:** Schwerpunkt der Audioqualität auf der Metrik "Schlechtes Streamverhältnis", TCP-Nutzung, verkabelte und drahtlose Subnetze und Identifizieren der Verwendung von HTTP-Proxys und VPN

-   **Endpunkte:** Audiogeräte und aktuelle Clients

-   **Dienstverwaltung:** diese Kategorie umfasst zwei Abschnitte:

    -   Zuerst ist Microsoft dafür verantwortlich, die Onlinedienste zu Teams und Skype for Business verwalten.

    -   Zweitens werden Aufgaben in Ihrer Organisation verwaltet, um einen zuverlässigen Zugriff auf den Dienst sicherzustellen, z. B. die Aktualisierung von Gebäudeinformationen und die Verwaltung von Firewalls für neue Office 365-IP-Adressen, wenn dem Dienst eine Infrastruktur hinzugefügt wird.

![Diagramm der Qualitätskategorien in einer Organisation](media/qerguide-image-categories.png "Die Qualitätskategorien in einer Organisation: Dienstverwaltung, Endpunkte und das Netzwerk.")

Überprüfen Sie die folgende Liste der empfohlenen Aufgaben, um die Qualität zu gewährleisten. Sie sollten diese Aufgaben regelmäßig ausführen , z. B. wöchentlich.

#### <a name="service-management-tasks"></a>Dienstverwaltungsaufgaben

Diese Aufgaben reichen von der Sicherstellung, dass ausreichend Bandbreite verfügbar ist, um zum Dienst zu gelangen, ohne Internetlinks zu sättig zu machen, das Überprüfen der Dienstqualität (Quality of Service, QoS) in allen Bereichen verwalteter Netzwerke und das Behalten der IP-Bereiche der Office 365 in [Firewalls.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

#### <a name="network-tasks"></a>Netzwerkaufgaben

Es gibt zwei Kategorien von Netzwerkaufgaben: Zuverlässigkeit und Qualität. Zuverlässigkeit ist darauf konzentriert, die Fähigkeit des Benutzers zu messen, anrufe erfolgreich zu halten und in Verbindung zu bleiben. Die Qualität konzentriert sich auf die aggregierten Telemetriedaten, die während und nach dem Anruf vom Kunden des Benutzers an Teams und Skype for Business Online gesendet werden. 

Angesichts der kritischen Auswirkungen, die Zuverlässigkeit auf die Benutzerfreundlichkeit hat, empfehlen wir, Zuverlässigkeitsmetriken zu bewerten und zu untersuchen, bevor Sie sich mit der Qualität abmäten. 

#### <a name="endpoints-tasks"></a>Endpunktaufgaben

Die Hauptaufgabe in dieser Kategorie entfernt alle Hindernisse für normale [Teams Clientupdates.](teams-client-update.md) Standardmäßig wird Teams automatisch aktualisiert (es sei denn, Sie deaktivieren diese Einstellung, was nicht empfohlen wird). 

Sie sollten auch Geräte überwachen und Updates bereitstellen, sobald Sie Probleme im Zusammenhang mit einem Gerät erkennen.

## <a name="use-cqd-to-manage-call-quality"></a>Verwalten der Anrufqualität mithilfe des Anrufqualitäts-AQD

Nachdem Sie das [AQD](turning-on-and-using-call-quality-dashboard.md)eingerichtet haben, können Sie es verwenden, um die Anruf- und Besprechungsqualität für Ihre Organisation zu verwalten.

Die meisten Probleme mit Teams Leistung fallen in die folgenden Kategorien:

-   Unvollständige Firewall- oder Proxykonfiguration
-   Schlechte WLAN-Abdeckung
-   Unzureichende Bandbreite
-   VPN
-   Inkonsistente oder veraltete Clientversionen und Treiber
-   Nicht optimierte oder integrierte Audiogeräte
-   Problematische Subnetze oder Netzwerkgeräte

Wenn Sie sich die Zeit nehmen, bevor Sie Teams nutzen, um diese Bereiche zu bewerten und etwaige Mängel zu beheben, verringern Sie den Aufwand, der erforderlich ist, um eine qualitativ hochwertige Teams-Erfahrung für alle Benutzer zu gewährleisten. Hilfe bei der Bewertung des Netzwerks als Vorbereitung [](use-advisor-teams-roll-out.md) auf Teams Rollouts erhalten Sie unter Ratgeber für Teams und Vorbereiten Ihres Netzwerks [für Teams.](prepare-network.md)

### <a name="expectations-using-cqd"></a>Erwartungen bei der Verwendung von CQD

Verwenden Sie das Anrufqualitätsdashboard (CQD), um einen Einblick in die Qualität von Anrufen zu erhalten, die mithilfe von Teams und Skype for Business werden. Das CQD soll Teams und Skype for Business-Administratoren und Netzwerktechnikern dabei helfen, das Netzwerk zu optimieren und die Qualität, Zuverlässigkeit und Benutzerfreundlichkeit genau im Auge zu behalten. Das CQD betrachtet die Aggregierte Telemetrie für die gesamte Organisation, wobei allgemeine Muster sichtbar werden können. auf diese Weise können Sie fundierte Bewertungen erstellen und eine Problembehebung planen. CQD bietet Metrikenberichte, die Einblicke in die Qualität, Zuverlässigkeit und Benutzerfreundlichkeit bieten.

Obwohl das CQD zum Analysieren von Trends und Subnetzen nützlich ist, bietet es nicht immer eine bestimmte Ursache für ein bestimmtes Szenario. Es ist wichtig, dass Sie dies verstehen und die richtige Erwartung festlegen, wenn Sie das AQD verwenden:

-   Das CQD stellt nicht die Ursache für jedes Szenario
-   Das CQD enthält keine Telefonsystem oder Audiokonferenzdatenströme.
-   Das CQD gibt Bereiche zur weiteren Untersuchung auf der Grundlage von Trends an.

### <a name="cqd-reports-overview"></a>Übersicht über CQD-Berichte

Verwenden Sie das Dropdownmenü am oberen Rand des Bildschirms, um einen Bericht zu öffnen. Eine Liste der in den einzelnen Berichten bereitgestellten Daten finden Sie unter In [AQD-Berichten](CQD-data-and-reports.md#data-available-in-cqd-reports)verfügbare Daten.

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.


### <a name="teams-vs-skype-for-business"></a>Teams vs. Skype for Business

Das CQD kann sowohl über Teams als Skype for Business. Es kann jedoch vorkommen, dass Sie einen Bericht entwickeln möchten, um die Telemetrie von Teams getrennt von Skype for Business zu betrachten.

#### <a name="summary-reports"></a>Zusammenfassungsberichte

Wenn Sie die Seite Zusammenfassungsberichte so ändern möchten, dass nur Teams oder Skype for Business angezeigt wird, wählen Sie am oberen Rand des Bildschirms das Dropdownmenü **Produktfilter** aus, und wählen Sie dann das gewünschte Produkt aus.

![Screenshot des Dropdownmenüs mit den Filteroptionen](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Detaillierte Berichte

Wenn Sie alle detaillierten Berichte filtern möchten, fügen Sie in der Browserleiste Folgendes am Ende der URL an:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Beispiel:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Weitere Informationen zu URL-Filtern finden Sie unter [Filtern von Berichten](CQD-data-and-reports.md#report-filters) weiter unten in diesem Abschnitt.

Wenn Sie einen einzelnen detaillierten Bericht filtern möchten, fügen Sie den Filter ``Is Teams`` zum Bericht hinzu und legen Sie ihn auf „True“ oder „False“ fest.

![Screenshot der Seite „Filter hinzufügen“](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Verwaltete und nicht verwaltete Netzwerke

Standardmäßig werden alle Endpunkte in CQD als extern eingestuft. Sobald eine Gebäudedatei eingeführt wird, können wir mit der Suche nach verwalteten Endpunktdaten beginnen. Wie bereits erwähnt, sind Netzwerke in CQD wie folgt definiert:

-   Ein _verwaltetes Netzwerk_, das häufig als "internes" oder "inneres" bezeichnet wird, kann von der Organisation beeinflusst und gesteuert werden. Dies umfasst das interne LAN, das Remote-WAN und VPN.
-   Ein _nicht verwaltetes_ Netzwerk, das häufig als extern oder außerhalb bezeichnet wird, kann nicht von der Organisation beeinflusst oder gesteuert werden. Ein Beispiel für ein nicht verwaltetes Netzwerk ist ein Hotel- oder Flughafennetzwerk.

### <a name="dimensions-measures-and-filters"></a>Dimensionen, Messungen und Filter

Eine gut formulierte CQD-Abfrage enthält alle drei der folgenden Parameter: 

-   **Dimension:** Wie ich die Daten betrachten möchte.

-   **Messung:** Worüber möchte ich berichten.

-   **Filter:** Wie ich den von der Abfrage zurückgegebenen Datensatz reduzieren möchte.

Eine weitere Möglichkeit, dies zu betrachten, ist,  dass eine Dimension die Gruppierungsfunktion  ist, ein Measure die Daten sind, die mich interessieren, und ein Filter ist, wie ich die Ergebnisse auf die für meine Abfrage relevanten Ergebnisse einkreisen möchte. 

Ein Beispiel für eine wohlgeformte Abfrage ist **Zeige schwache Ströme [Messung] nach Subnetz [Dimension] für Gebäude 6 [Filter] an**. Weitere Informationen finden Sie unter [Dimensionen und Messungen, die in CQD verfügbar sind](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="first-vs-second"></a>Erster vs. zweiter 

Viele Dimensionen und Kennzahlen im CQD werden als erster oder zweiter Endpunkt bezeichnet. CQD verwendet keine Anrufer-/Anruferfelder– diese  wurden  zuerst und zweiter umbenannt, weil zwischen Anrufer und Anrufer Zwischenschritte erforderlich sind. Die folgende Logik legt fest, welcher beteiligte Endpunkt als erster bezeichnet wird:

-   Der **erste** wird immer ein Serverendpunkt (Konferenzserver, Vermittlungsserver usw.) sein, wenn ein Server in den Strom oder Anruf einbezogen wird.

-   Der **zweite** ist immer ein Client-Endpunkt, es sei denn, der Datenstrom verläuft zwischen zwei Server-Endpunkten.

-   Wenn beide Endpunkte vom selben Typ sind, richtet sich die Auswahl des ersten Endpunkts nach der internen Anordnung der Benutzer-Agenten-Kategorie. Dadurch wird sichergestellt, dass die Reihenfolge konsistent ist.

Weitere Informationen zum Bestimmen des ersten oder zweiten Endpunkts, wenn beide gleich sind, finden Sie unter Im [AQD](./dimensions-and-measures-available-in-call-quality-dashboard.md)verfügbare Dimensionen und Measures.

### <a name="stream-vs-call"></a>Datenstrom vs. Anruf

Sie müssen den Unterschied zwischen einem Anruf und einem Datenstrom verstehen, um richtig auswählen zu können, welche Dimensionen oder Measures im AQD angezeigt werden sollen. Obwohl der Hauptschwerpunkt des AQD auf Datenströmen liegt, stehen auch anrufbasierte Messungen zur Verfügung.

-   **Datenstrom:** Ein _Datenstrom_ ist nur zwischen zwei Endpunkten vorhanden. Es gibt nur einen Datenstrom für jede Richtung und für die Kommunikation sind zwei Datenströme erforderlich. Datenströme sind hilfreich, um Gebäude, Netzwerke oder Subnetze zu untersuchen. In einigen Fällen werden sowohl der Aufruf als auch der Datenstrom im Namen der Messung verwendet (z. B. Anrufeinrichtungsstream oder Gelöschter Datenstrom). Diese werden weiterhin als Datenströme eingestuft.

-   **Anruf:** Ein _Anruf_ ist eine Gruppierung aller Datenströme aller Teilnehmer. Ein Anruf besteht aus mindestens zwei Ströme. Ein einzelner Anruf hat mindestens zwei Endpunkte mit jeweils mindestens einem Datenstrom.

Weitere Hinweise dazu, ob sich die Dimension oder Messung auf einen Anruf oder einen Datenstrom bezieht, finden Sie unter [Dimensionen und Messungen, die in CQD verfügbar sind](./dimensions-and-measures-available-in-call-quality-dashboard.md). 

### <a name="good-poor-and-unclassified-calls"></a>Gute, schlechte und nicht klassifizierte Anrufe

Ein Anruf wird entweder als "gut", "schlecht" oder "nicht klassifiziert" kategorisiert. Lassen Sie uns einen Moment Zeit nehmen, um uns ausführlicher damit zu unterhalten.

-   **Gut oder schlecht:** Ein guter oder schlechter Anruf besteht aus einem Anruf, der eine vollständige Gruppe von Dienstmetriken enthält, für die ein vollständiger QoE-Bericht generiert und vom Dienst empfangen wurde. Die Ermittlung, ob ein Datenstrom gut oder schlecht ist, wird [weiter oben in diesem Artikel beschrieben.](#poor-stream-rate)

-   **Unclassified:** Ein nicht klassifizierter Datenstrom enthält keinen vollständigen Satz von Dienstmetriken. Dies können kurze Aufrufe sein – in der Regel weniger als 60 Sekunden –, bei denen keine Durchschnittswerte berechnet werden konnten und kein QoE-Bericht generiert wurde. Der häufigste Grund für Anrufe, die nicht klassifiziert werden, besteht darin, dass die Paketnutzung nur geringfügig oder gar nicht funktioniert. Ein Beispiel hierfür wäre ein Teilnehmer, der sich an einer Besprechung stummgeschaltet anschließt und niemals spricht. Der Teilnehmer empfängt, sendet jedoch keine Medien. Ohne übertragene Medien sind für das AQD keine Metriken zum Klassifizieren des ausgehenden Medienstreams des Endpunkts verfügbar.

Weitere Informationen finden Sie unter [Streamklassifizierung im CQD.](stream-classification-in-call-quality-dashboard.md)

### <a name="common-subnets"></a>Häufig verwendete Subnetze

Häufig verwendete Subnetze sind bestimmte private Subnetze, die von Hotels, Heimnetzwerken, Hotspots und ähnlichen Bereichen verwendet werden. Diese Subnetze können aufgrund ihrer weit reichenden Nutzung nur schwer verfolgt werden. Wenn in Ihrer Organisation eines dieser häufig verwendeten Subnetze verwendet wird, empfehlen wir, dass Sie dieses Netzwerk in ein anderes Subnetz verschieben. Dies erleichtert die Berichterstellung in CQD. Wenn angegeben, wurden Berichte in der Vorlage "Alle Netzwerke" so konfiguriert, dass Sie diese Subnetze ausschließen, um sie als Quelle schlechter Qualität zu eliminieren. Nachstehend sind häufig verwendete Subnetze definiert. Ihre Auswirkung variiert je nach Organisation.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Beim Untersuchen eines verwalteten Netzwerks, das ein gemeinsames Subnetz verwendet, müssen Sie die Second Reflexive Local IP-Dimension verwenden, um Subnetze zu gruppieren. Diese Dimension enthält die öffentliche IP-Adresse des Endpunkts.


## <a name="reliability-investigations"></a>Zuverlässigkeitsuntersuchungen

Der erste Schritt zur Verbesserung der Qualität ist die Einschätzung des Status der Zuverlässigkeit innerhalb der gesamten Organisation. Da Zuverlässigkeit für eine positive Benutzererfahrung von entscheidender Bedeutung ist, beginnen wir mit den beiden Komponenten zur Messung der Zuverlässigkeit:

1.  **Setupfehler:** Der Anruf konnte nicht aufgebaut werden.

2.  **Abbruchfehler:** Ein ausgehender Anruf wurde hergestellt und unerwartet beendet.

In diesem Abschnitt werden Methoden zum Untersuchen beider Bereiche erläutert.

> [!NOTE]
> Nicht alle in den Vorlagen enthaltenen Berichte werden in diesem Artikel behandelt. Die nachstehend erläuterten Methoden für Untersuchungen gelten jedoch weiterhin. Weitere Informationen finden Sie in der Beschreibung des jeweiligen Berichts.


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

Nehmen Sie sich unabhängig von Ihren Antworten auf diese Fragen Zeit, weitere Informationen zu erhalten. Verwenden Sie dazu die Begleitunterberichte, um nach einzelnen Gebäuden oder Subnetzen zu suchen, die möglicherweise saniert werden müssen. Obwohl die Gesamtfehlerrate möglicherweise unter der Zielmetrik liegt, sind die Fehlerraten für ein oder mehrere Gebäude oder Netzwerke möglicherweise über der Zielmetrik und benötigen Untersuchungen.

#### <a name="setup-failure-investigations"></a>Untersuchungen bei Aufbaufehlern 

Dieser Zusammenfassungsbericht wird verwendet, um Gebäude oder Netzwerke zu finden und zu isolieren, die ggf. eine Fehlerbehebung bedürfen.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Berichtsfilter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie den Berichtsfilter **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.

##### <a name="remediation"></a>Fehlerbehebung 

Konzentrieren Sie sich auf Gebäude oder Subnetze, die das größte Fehlervolumen aufweisen. Auf diese Weise können Sie die Auswirkungen auf die Benutzeroberfläche maximieren und so die Aufbaufehlerrate von Organisationsanrufen schnell reduzieren. In der folgenden Tabelle sind die zwei Gründe für Aufbaufehler aufgelistet, die von CQD gemeldet wurden.

| Gründe für Anrufaufbaufehler       | Typische Ursache                    |
|----------------------------------|----------------------------------|
| Fehlende Ausnahmeregel für FW-DPI (Deep Packet Inspection) | Deutet darauf hin, dass die Netzwerkausrüstung entlang des Pfads verhindert hat, dass der Medienpfad aufgrund von DPI-Regeln nicht erstellt wurde. Dies ist möglicherweise auf nicht ordnungsgemäß konfigurierte Firewallregeln zurückzuführen. In diesem Szenario war der TCP-Handshake erfolgreich, der SSL-Handshake jedoch nicht.      |
| Fehlende Ausnahmeregel für FW-IP-Block      | Gibt an, dass die Netzwerkausrüstung entlang des Pfads verhindert hat, dass der Medienpfad zum Netzwerk Microsoft 365 oder Office 365 wurde. Dies könnte darauf zurückzuführen sein, dass Proxy- oder Firewallregeln nicht ordnungsgemäß konfiguriert wurden, um den Zugriff auf die für Teams- und Skype for Business-Datenverkehr verwendeten IP-Adressen und Ports nicht ordnungsgemäß konfiguriert wurden. |

Während Sie mit der Problembehebung beginnen, können Sie sich auf ein bestimmtes Gebäude oder Subnetz konzentrieren. Wie in der vorstehenden Tabelle zu sehen ist, sind diese Probleme auf Firewall- oder Proxy-Konfigurationen zurückzuführen. Überprüfen Sie die in der folgenden Tabelle aufgeführten Optionen für Wartungsaktionen.

|      Fehlerbehebung      |Anleitung  |
|-----------------------|----------|
| Konfigurieren von Firewalls | Arbeiten Sie mit Ihrem Netzwerkteam zusammen, und überprüfen Sie die Firewallkonfiguration für Office 365 [IP-Adressliste .](/microsoft-365/enterprise/urls-and-ip-address-ranges)<br><br>Vergewissern Sie sich, dass die [Medien-Subnetze](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) und -Ports in den Firewallregeln enthalten sind. <br><br>Vergewissern Sie [sich, dass die erforderlichen Ports](prepare-network.md) in der Firewall geöffnet sind. UDP sollte vorrangig sein, da TCP als Rückfallprotokoll für Audio-, Video- und videobasierte Bildschirmfreigaben betrachtet wird und deren Verwendung sich auf die Qualität des Anrufs auswirkt. Die alte RDP-Anwendungsfreigabe verwendet nur TCP.|

### <a name="drop-failures"></a>Abbruchfehler

Im Gegensatz zu Setupfehlercodes enthält das CQD keinen Drop-Fehlercode, der angibt, warum Drop-Fehler auftreten, wodurch das Isolieren einer bestimmten Stammursache erschwert wird. Verwenden Sie einen abgeleiteten Ansatz, um Abbruchfehler besser zu erkennen. Durch die Behebung aller Bereiche, die für die Medien von Interesse sind, das Patchen von Clients und Treibern und die Nutzung zertifizierter Geräte für Teams und Skype for Business können Sie erwarten, dass die Zahl der Abbrüche zurückgehen wird.

#### <a name="drop-failure-trend-analysis"></a>Trendanalyse der Abbruchfehler

In diesem Bericht werden die Gesamtmenge der Audiodatenströme, die Gesamtanzahl der Abbruchfehler und die Abbruchfehlerrate angezeigt. Zeigen Sie auf eine der Spalten, um die Werte anzuzeigen. 


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

Mithilfe der enthaltenen Tabellenberichte können Sie Problembereiche im Netzwerk isolieren, deren Ab drop rate oberhalb der von Ihnen definierten Zielmetrik liegt. Konzentrieren Sie sich auf Gebäude oder Subnetze, die die höchste Gesamtzahl von Datenströmen aufweisen, um die größten Auswirkungen auf Gebäude oder Subnetze zu erzielen.

Häufige Ursachen von Anrufabbrüchen:

-   Netzwerk- oder Internetdatenverkehr mit unzureichenden Ressourcen
-   Kein QoS konfiguriert in eingeschränkten Netzwerken
-   Ältere Clientversionen
-   Benutzerverhalten

Nachdem Sie Ihre Problembereiche ermittelt [](use-call-analytics-to-troubleshoot-poor-call-quality.md) haben, können Sie die Anrufanalyse pro Benutzer verwenden, um die Benutzer in diesem Gebäude auf bestimmte Probleme zu überprüfen. Die Anrufanalyse enthält zusätzliche EUII-Daten und kann hilfreich sein, um potenzielle Ursachen für Drop-Fehler weiter zu isolieren.

Unabhängig vom nächsten Schritt sollten Sie Ihren Helpdesk darüber informieren, dass bei bestimmten Gebäuden oder Subnetzen ein Problem entdeckt wurde. Auf diese Weise kann der Helpdesk schneller auf eingehende Anrufe reagieren und Benutzer effizienter ernennen. Gekennzeichnete Benutzer können dann an das Entwicklungsteam zur weiteren Untersuchung zurückgemeldet werden.

Die folgende Tabelle enthält einige häufige Methoden zum Verwalten und Beheben von Abbruchfehlern.

| Fehlerbehebung                              | Anleitung                      |
|------------------------------------------|-------------------------------|
| **Netzwerk/ Internet**                         | **Überlastung**: Arbeiten Sie mit Ihrem Netzwerkteam zusammen, um die Bandbreite bei bestimmten Gebäuden/ Subnetzen zu überwachen, um zu bestätigen, dass es Probleme mit der Übernutzung gibt. Wenn Sie feststellen, dass es zu einer Netzwerküberlastung kommt, überlegen Sie sich, die Bandbreite zu diesem Gebäude zu erhöhen oder QoS anzuwenden. Verwenden Sie die integrierten [Zusammenfassungsberichte über Datenströme mit schlechter Qualität](#quality-investigations), um die problematischen Subnetze bei Problemen mit Jitter, Latenz und Paketverlusten zu überprüfen, da diese häufig einem abgebrochenen Datenstrom vorausgehen.<br><br>**QoS**: Wenn eine Erhöhung der Bandbreite unpraktisch oder unerschwinglich sein sollte, überlegen Sie sich, QoS zu implementieren. Dieses Tool eignet sich besonders für die Verwaltung von überlasteten Datenverkehr und kann dafür sorgen, dass Medienpakete im verwalteten Netzwerk Vorrang vor nicht-Mediendatenverkehr haben. Alternativ können Sie, wenn es keinen eindeutigen Nachweis gibt, dass Bandbreite die Schuld ist, die folgenden Lösungen in Betracht ziehen:<ul><li>[Microsoft Teams QoS-Anleitung](qos-in-teams.md)</li></ul><br>**Ausführen einer Bewertung der Netzwerkbereitschaft**: Eine Netzwerkbewertung liefert Details über die erwartete Bandbreitennutzung, die Beherrschung von Bandbreiten- und Netzwerkänderungen sowie empfohlene Netzwerkpraktiken für Teams und Skype for Business. Wenn Sie die vorstehende Tabelle als Quelle verwenden, haben Sie eine Liste von Gebäuden oder Subnetzen, die hervorragende Kandidaten für eine Bewertung sind.<ul><li>[Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md)</li></ul> |
| **Clients (nur für Skype for Business Online)** | Einige ältere Skype for Business-Clients haben bekannte, dokumentierte Probleme mit der Medienzuverlässigkeit. Überprüfen Sie die Anrufanalyseberichte mehrerer betroffener Benutzer oder erstellen Sie einen benutzerdefinierten Bericht in einer Client-Versionstabelle in CQD, gefiltert nach bestimmten Gebäuden oder Subnetzen mit der Messung der Gesamtzahl an Anrufabbruchfehler in %. Anhand dieser Informationen können Sie erkennen, ob eine Beziehung zwischen Anrufabbrüchen in diesem spezifischen Gebäude und einer bestimmten Version des Clients besteht.     |
| **Geräte**                                  |Wenn Geräte die Schuld an Problemen mit der Anrufqualität sind, sollten Sie erwägen, beleidende Geräte zu aktualisieren. Weitere [Informationen finden Teams](./devices/phones-for-teams.md) unter Telefone für weitere Informationen. |
| **Benutzerverhalten**                            | Wenn Sie feststellen, dass weder Netzwerk, noch Geräte oder Clients das Problem sind, sollten Sie die Entwicklung einer Benutzeradaptionsstrategie in Betracht ziehen, um die Benutzer darüber aufzuklären, wie sie am besten an Besprechungen teilnehmen und diese verlassen können. Besser vorbereitete Teams- und Skype for Business-Benutzer sorgen für eine bessere Benutzererfahrung für alle Teilnehmer. Ein Benutzer, der beispielsweise seinen Laptop in den Ruhezustand versetzt (indem er den Deckel schließt), ohne die Besprechung zu verlassen, wird als unerwarteter Anrufabbruch klassifiziert.   |

## <a name="quality-investigations"></a>Qualitätsuntersuchungen

Der nächste Schritt zur Einschätzung des Zustands der Audioqualität innerhalb der Organisation ist die Untersuchung schlechter Datenstromraten (PSR), TCP und Proxy-Nutzung. Es ist wichtig daran zu denken, dass CQD-Daten keine bestimmte Ursache für Sie liefern, sondern Ihnen wahrscheinliche Problembereiche bieten, um eine zusammenarbeitliche Unterhaltung mit den entsprechenden Teams für Problembehebungsaktivitäten zu beginnen. 

> [!NOTE]
> Nicht alle in den Vorlagen enthaltenen Berichte werden in diesem Artikel behandelt. allerdings gelten die unten erläuterten Methoden zur Untersuchung nach wie vor für diese Berichte. Weitere Informationen finden Sie in der Beschreibung des jeweiligen Berichts. 

### <a name="quality"></a>Qualität

Die PSR-Prozentsätze werden verwendet, um anzugeben, ob die Organisation die festgelegten Metrikziele für einen bestimmten Schwerpunktbereich erfüllt. Es ist wichtig zu beachten, dass auch wenn sich die hohen Prozentsätze innerhalb des definierten Ziels befinden, einzelne Subnetze oder Gebäude die definierten Ziele möglicherweise nicht erfüllen und daher weitere Untersuchungen ausführen müssen. Wenn beispielsweise der Gesamtprozentsatz des Audio-PSR im April 2 Prozent beträgt, was der Zielvorgabe der Stichprobe entspricht, könnten einzelne Gebäude und Subnetze immer noch schlechte Erfahrungen machen, abhängig von der Gesamtverteilung dieser 2 Prozent. 

Wenn Sie den Prozentsatz schlechter Datenströme bewerten möchten, verwenden Sie die Qualitätsberichte. Es werden verschiedene Qualitätsberichte bereitgestellt, um Metriken der Gesamtzahl der Anrufe, Konferenz-, Zwei-Parteien-, PSTN-Anrufe, VPN und Besprechungsräume zu überprüfen. Zur Unterstützung bei diesem Vorgang werden monatliche, wöchentliche und tägliche Berichte bereitgestellt. Die wöchentlichen und täglichen Berichte beschränken sich auf die Vorlage "Verwaltete Netzwerke", um ihre Wirksamkeit zu erhöhen und Störungen zu reduzieren. 

#### <a name="quality-trend-analysis"></a>Qualitätstrendanalyse

Trendberichte zeigen Qualitätsinformationen über die Zeit an und dienen dazu, Qualitätstrends in jedem Interessengebiet zu erkennen und zu verstehen. Wie oben erwähnt, sind in den Vorlagen zur Untersuchung der Qualität Berichtsbäume enthalten; Konferenz-, Zweiparteien-, PSTN-Telefonie, VPN und Besprechungsräume. Der Untersuchungsprozess zur Analyse der Qualität ist identisch. Allerdings empfiehlt es sich, bei den Konferenzbesprechungen zu beginnen, da sich alle Verbesserungen bei der Konferenzqualität positiv auf alle anderen Bereiche auswirken. 

> [!Note]
> Die Untersuchung von Zwei-Parteien-Anrufe, PSTN-Telefonie und Besprechungsräumen ist ähnlich wie die Untersuchung von Konferenzgesprächen. Der Fokus liegt darauf, Gebäude oder Subnetze abzugrenzen, die die schlechteste Qualität haben, und den Grund für die schlechte Qualität zu identifizieren.

> [!Important]
> VPN-basierte Berichte werden mithilfe der zweiten VPN-Dimension gefiltert. Diese Dimension setzt voraus, dass der VPN-Netzwerkadapter ordnungsgemäß als Fernzugriffadapter registriert ist. VPN-Anbieter verwenden diese Kennzeichnung nicht zuverlässig, und Ihre gefahrenen Kilometer variieren je nach vpn-Anbieter, der in Ihrer Organisation bereitgestellt wurde. Ändern Sie [die VPN-Berichte](CQD-upload-tenant-building-data.md#vpn) bei Bedarf unter Verwendung des Gebäude- oder Netzwerknamens.

##### <a name="investigation"></a>Untersuchung

Mithilfe dieser Berichte können Sie die folgenden Fragen beantworten:

-   Wie hoch ist die gesamte PSR für den aktuellen Monat?
-   Liegt die PSR unter der definierten Zielmetrik?
-   Ist die PSR schlechter oder besser als im vorhergehenden Monat?
-   Steigt die PSR, wird sie stetig oder sinkt sie?

Unabhängig von den Antworten auf den obigen Fragen sollten Sie sich die Zeit für eine Untersuchung nehmen, bei der Sie die zugehörigen Unterberichte verwenden, um nach Gebäuden oder Subnetzen zu suchen, die möglicherweise eine Untersuchung bedürfen. Obwohl die allgemeine PSR möglicherweise unter der Zielmetrik liegt, liegt die PSR für ein oder mehrere Gebäude oder Netzwerke häufig über der Metrik und muss korrigiert werden.

#### <a name="quality-investigations"></a>Qualitätsuntersuchungen

Die Qualitätszusammenfassungsberichte geben Ihnen tiefere Einblicke in die Ursache, die die Datenströme als "schlecht" klassifiziert haben, und helfen, Problembereiche im verwalteten Netzwerk zu isolieren.

Obwohl sich die verwendeten Dimensionen von Bericht zu Bericht leicht unterscheiden können, wird jeder Bericht Maßnahmen für Gesamtdatenströme, schlechte Gesamtdatenströme, PSR und schlechte Qualität aufgrund schlechter Qualität enthalten. Es wurden Berichte für jeden Interessenbereich erstellt: Konferenzen, Zwei-Parteien-Gespräche, PSTN-Anrufe, VPN und Besprechungsräume. Die Vorlage zu verwalteten Netzwerke enthält zusätzliche Berichte, um die Standortinformationen zu nutzen, die über die Gebäudedatei hochgeladen wurden.


> [!Note]
> Häufig verwendete Subnetze können aufgrund ihrer weit reichenden Nutzung nur schwer verfolgt werden. Der Vorlage "Alle Netzwerke" wurde ein separater Bericht hinzugefügt, in dem die öffentliche IP des Clients (Second Reflexive Local IP) angezeigt wird, um die Behebung von Büros zu unterstützen, die gemeinsame Netzwerke verwenden.


![Screenshot mit der Zusammenfassung des schlechten Audiodatenstroms](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Fehlerbehebung

Konzentrieren Sie sich auf Gebäude oder Subnetze, die über die größten Mengen an Datenströmen verfügen, da sich dadurch die Wirkung maximieren lässt und die Benutzererfahrung schnell verbessert wird. Verwenden Sie Jitter-, Paketverlust- und Roundtripzeitmessungen (Round-Trip Time, RTT), um zu verstehen, was zu der schlechten Qualität beitragen kann (es kann mehrere Probleme geben):

-   **Jitter**: Medienpakete kommen mit unterschiedlichen Geschwindigkeiten an, was dazu führt, dass der Sprechende robotisch klingt.
-   **Paketverlust**: Medienpakete werden ausgelassen, was den Effekt von fehlenden Wörtern oder Silben erzeugt.
-   **RTT**: Medienpakete brauchen lange, um an ihr Ziel zu gelangen, wodurch ein Walkie-Talkie-Effekt entsteht.

Verwenden Sie zur Unterstützung Ihrer Untersuchung von Qualitätsproblemen die [Anrufanalyse pro Benutzer.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Mit der Anrufanalyse können Sie sich den Anrufbericht einer bestimmten Konferenz oder eines bestimmten Benutzers anschauen. Dieser Bericht enthält EUII/PII-Daten und ist nützlich, wenn Sie nach der Ursache für einen Fehler suchen. Nachdem Sie erkannt haben, welche Gebäude betroffen sind, sollten Sie die Benutzer in diesem Gebäude einfach nachverfolgen. 

Vergessen Sie nicht, Ihren Helpdesk wissen zu lassen, dass in diesen Netzwerken Qualitätsprobleme auftreten, damit sie eingehende Anrufe schnell durch ein Quizing abfragen und darauf reagieren können.

| Fehlerbehebung                              | Anleitung                         |
|------------------------------------------|----------------------------------|
| **Netzwerke**                                 | **Überlastung**: Ein überlastetes Netzwerk oder ein Netzwerk mit mangelhaften Ressourcen kann Probleme mit der Medienqualität verursachen. Arbeiten Sie mit dem Netzwerkteam zusammen, um festzustellen, ob die Netzwerkverbindungen vom Benutzer zum Internet-Ausgangspunkt über genügend Bandbreite zur Unterstützung der Medien verfügen. <br><br>**Ausführen einer Bewertung der Netzwerkbereitschaft**: Eine Netzwerkbewertung liefert Details über die erwartete Bandbreitennutzung, die Beherrschung von Bandbreiten- und Netzwerkänderungen sowie empfohlene Netzwerkpraktiken für Teams und Skype for Business. Wenn Sie die vorstehende Tabelle als Quelle verwenden, haben Sie eine Liste von Gebäuden oder Subnetzen, die hervorragende Kandidaten für eine Bewertung sind.<ul><li>[Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md)</li></ul>|
| **Quality of Service (QoS)**  | QoS ist ein bewährtes Tool, das die Priorisierung von Paketen in einem überlasteten Netzwerk unterstützt, um sicherzustellen, dass sie im Ganzen und pünktlich am Bestimmungsort ankommen. Erwägen Sie die Implementierung von QoS in Ihrer Organisation, um die Qualität der Benutzererfahrung zu maximieren, wenn die Bandbreite eingeschränkt ist. QoS hilft beim Beheben von Problemen, die normalerweise mit einem hohen Maß an Paketverlust verbunden sind, und – zu einem geringeren Grad – von Problemen mit Jitter und Round-trip-Zeiten.<ul><li>[Teams QoS-Leitfaden](qos-in-teams.md)</li></ul> |
| **WLAN**               | WLAN kann sich erheblich auf die Anrufqualität auswirken. Wi-Fi Für Bereitstellungen werden in der Regel die Netzwerkanforderungen für VoIP-Dienste nicht berücksichtigt, und sie sind häufig eine Ursache für eine schlechte Qualität. Weitere Informationen zur Optimierung Ihrer WLAN-Infrastruktur finden Sie [in diesem Artikel über die WLAN-Planung](/skypeforbusiness/certification/plan-wifi).<br><br>**WLAN-Treiber**: Stellen Sie sicher, dass die Treiber für die WLAN-Verbindung auf dem neuesten Stand sind. Auf diese Weise können Sie die schlechte Benutzererfahrung im Zusammenhang mit einem veralteten Treiber verringern. Viele Organisationen schließen keine Drahtlostreiber in ihre Patchzyklen ein, und diese Treiber können Jahre lang ohnePatch sein. Viele WLAN-Probleme werden behoben, indem sichergestellt wird, dass die WLAN-Treiber aktuell sind.<br><br>**WMM**: WMM (Wireless Multimedia Extensions), auch als WLAN-Multimedia bezeichnet, bieten grundlegende QoS-Funktionalitäten für drahtlose Netzwerke. Moderne drahtlose Netzwerke müssen viele Geräte unterstützen. Diese Geräte konkurrieren um die Bandbreite und können zu Qualitätsproblemen für VoIP-Dienste führen, bei denen Geschwindigkeit und Latenz am wichtigsten sind. Erkundigen Sie sich bei Ihrem WLAN-Anbieter nach den Einzelheiten und erwägen Sie die Implementierung von WMM in Ihrem WLAN-Netzwerk, um den Medien von Skype for Business und Teams Priorität einzuräumen.<br><br>**Zugriffspunktdichte**: Zugriffspunkte sind möglicherweise zu weit voneinander entfernt oder nicht an einer idealen Position. Um mögliche Störungen zu minimieren, platzieren Sie zusätzliche Zugriffspunkte in Konferenzräumen und an Orten, die nicht durch Wände oder andere Objekte, an denen das Signal Wi-Fi schwach ist.<br><br>**2,4 GHz gegenüber 5 GHz**: 5 GHz bietet weniger Hintergrundinterferenzen und höhere Geschwindigkeiten und sollte bei der Bereitstellung von VoIP über WLAN bevorzugt werden. 5 GHz sind jedoch nicht so stark wie 2,4 GHz und werden nicht so leicht aus der Wand wandbar. Überprüfen Sie Ihr Gebäude-Layout, um festzustellen, auf welche Frequenz Sie sich für die beste Verbindung verlassen können. |
|**Netzwerkgerät** | In größeren Unternehmen gibt es möglicherweise Hunderte von Geräten, die über das Netzwerk verteilt sind. Arbeiten Sie mit Ihrem Netzwerkteam zusammen, um sicherzustellen, dass die Netzwerkgeräte vom Benutzer bis zum Internet gewartet und auf dem neuesten Stand sind. |
| **VPN**  | VPN-Geräte sind normalerweise nicht für die Verarbeitung von Echtzeitmedienarbeitsauslastungen ausgelegt. Einige VPN-Konfigurationen verbieten die Verwendung von UDP (das bevorzugte Protokoll für Medien) und verlassen sich nur auf TCP. Erwägen Sie die Implementierung einer VPN-Lösung mit geteiltem Tunnel, um VPN als Quelle schlechter Qualität zu reduzieren. |
| **Clients** <br>(Nur für Skype for Business Online) | Stellen Sie sicher, dass alle Clients regelmäßig aktualisiert werden. |
| **Geräte** | Wenn Geräte die Schuld an Problemen mit der Anrufqualität sind, sollten Sie erwägen, beleidende Geräte zu aktualisieren. Weitere [Informationen finden Teams](./devices/phones-for-teams.md) unter Telefone für weitere Informationen. |
| **Treiber** | Patchen von Netzwerk (Ethernet und WLAN), Audio-, Video- und USB-Treibern sollten Bestandteil ihrer Gesamtstrategie zur Patchverwaltung sein. Viele Qualitätsprobleme werden durch das Aktualisieren von Treibern behoben. |
| **Konferenzräume mit WLAN** | Es wird dringend empfohlen, dass Konferenzraumgeräte mit mindestens 1 Gbit/s Ethernet-Verbindung mit dem Netzwerk verbunden sind. Konferenzraumgeräte umfassen in der Regel mehrere Audio- und Videodatenströme sowie Konferenzinhalte wie Bildschirmfreigaben und höhere Netzwerkanforderungen als andere Teams oder Skype for Business-Endpunkte. Konferenzräume sind definitionsgemäß stationäre Geräte, bei denen WLAN nur während der Installation einen Nutzen bringt.<br><br>Konferenzräume müssen mit besonderer Sorgfalt behandelt werden, um sicherzustellen, dass die Erfahrung mit diesen Geräten die Erwartungen erfüllt oder übersteigt. Qualitätsprobleme bei Besprechungsräumen werden in der Regel schnell eskaliert, weil sie häufig von Mitarbeitern der Senior Ebene verwendet werden.<br><br>Bei gleicher Leistung (abgesehen von der Bequemlichkeit) ist die WLAN-Leistung oft geringer als bei einer kabelgebundenen Verbindung. Mit der Verbreitung von Richtlinien zur "Mit eigenen Geräten" und der Verbreitung von Laptops werden Wi-Fi Zugriffspunkte häufig überlastet. Echtzeit-Medien werden in WLAN-Netzwerken möglicherweise nicht priorisiert, was zu Qualitätsproblemen während der Zeiten mit stärkster Nutzung führen kann. Diese intensive Nutzung kann mit einer Besprechung zusammenfallen, bei der es ein Dutzend Personen gibt, die jeweils über einen eigenen Laptop und ein Smartphone verfügen, die alle mit demselben WLAN-Zugangspunkt wie das Gerät für den Besprechungsraum verbunden sind.<br><br>WLAN sollte nur als eine vorübergehende Lösung für eine mobile Installation oder wenn WLAN ordnungsgemäß für die Unterstützung von Echtzeit-Medien der Unternehmensklasse bereitgestellt wurde, in Betracht gezogen werden. |


### <a name="tcp"></a>TCP 

TCP (Transmission Control Protocol) wird als Failbacktransport und nicht als primärer Transport betrachtet, den Sie für Echtzeitmedien wünschen. Der Grund für den Failback-Transport ist die Zustandsbehaftetheit von TCP. Wenn beispielsweise ein Anruf in einem latenten Netzwerk getätigt wird und Medienpakete verzögert werden, dann konkurrieren Pakete von vor einigen Sekunden, die nicht mehr nützlich sind, um Bandbreite, um zum Empfänger zu gelangen, was eine schlechte Situation verschärft. Dies führt dazu, dass die Audioqualitätsbehebung den Ton zusammenfügt und streckt, was zu hörbaren Artefakten führt, oft in Form von Jitter.

In den Berichten in diesem Abschnitt wird nicht zwischen guten und schlechten Datenströmen unterschieden. Da UDP bevorzugt wird, suchen die Berichte nach der Verwendung von TCP für Audio, Video und videobasierte Bildschirmfreigabe (VBSS). Es werden schlechte Datenstromraten zur Ansicht bereitgestellt, um die UDP-Qualität im Vergleich zur TCP-Qualität zu vergleichen, damit Sie sich auf die größten Auswirkungen konzentrieren können. Die TCP-Nutzung wird in erster Linie durch unvollständige Firewallregeln verursacht. Weitere Informationen zu Firewallregeln für Teams und Skype for Business Online finden Sie unter Microsoft 365 und Office 365 von URLs und [IP-Adressbereichen.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

> [!Note]
> Audio, Video und VBSS bevorzugen alle UDP als ihren Haupttransport. Die alte Arbeitsauslastung für RDP-Anwendungsfreigabe verwendet nur TCP.

#### <a name="tcp-usage"></a>TCP-Nutzung

TCP-Berichte geben die gesamte TCP-Nutzung in den letzten sieben Monaten an. In allen anderen Berichten in diesem Abschnitt geht es um das einschränken bestimmter Gebäude und Subnetze, in denen TCP am häufigsten verwendet wird. Für Konferenzen und Datenströme mit zwei Parteien stehen separate Berichte zur Verfügung.

![Diagramm mit dem Prozentsatz der Audiodatenströme, die TCP verwenden](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Untersuchung

Mithilfe dieses Berichts können Sie die folgenden Fragen beantworten:

-   Wie hoch ist das Gesamtvolumen der TCP-Datenströme für den aktuellen Monat?
-   Ist es schlechter oder besser als im vorhergehenden Monat?
-   Steigt der Trend der TCP-Nutzung, wird er stetig oder sinkt er?
-   Ist die TCP-PSR identisch mit meiner gesamten PSR?

Wenn Sie feststellen, dass der TCP-Nutzungstrend zunimmt oder über die normale monatliche Nutzung hinausgeht, nehmen Sie sich die Zeit, um mit Hilfe der Unterberichte nach Gebäuden oder Netzwerken zu suchen, die möglicherweise eine Fehlerbehebung erfordern. Im Idealfall möchten Sie so wenige TCP-basierte Audiositzungen wie möglich im verwalteten Netzwerk haben.

#### <a name="tcp-vs-udp"></a>TCP vs. UDP

In diesem Bericht wird das Volumen der TCP- und UDP-Nutzung im letzten Monat für Audio, Video und videobasierte Bildschirmfreigabe (VBSS) angegeben. 

![Bericht über das Volumen der Datenströme, die TCP und UDP verwenden](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Analyse

Obwohl Sie die TCP-Nutzung so gering wie möglich halten wollen, kann es sein, dass Sie in einer ansonsten gesunden Bereitstellung ein wenig TCP-Nutzung sehen. TCP allein trägt nicht zu einem schlechten Anruf bei, daher werden Streamraten bereitgestellt, um zu ermitteln, ob die TCP-Nutzung einen Beitrag zu einer schlechten Qualität leisten kann. 

#### <a name="tcp-investigations"></a>TCP-Untersuchungen

Navigieren Sie in den bereitgestellten CQD-Vorlagen zu den TCP-Datenströmen nach Gebäude- und Subnetzberichten mithilfe der Vorlage „Verwaltete Netzwerke“ oder „Alle Netzwerke“. Für die Untersuchung der TCP-Nutzung ist der Vorgang identisch, daher konzentrieren wir uns hier auf Konferenzen.


##### <a name="remediation"></a>Fehlerbehebung

In diesem Bericht werden bestimmte Gebäude und Subnetze identifiziert, die zum Volumen der TCP-Nutzung beitragen. Außerdem wird ein weiterer Bericht hinzugefügt, um die Microsoft Relay-IP zu identifizieren, die beim Anruf verwendet wurde, um fehlende Firewallregeln zu isolieren. Konzentrieren Sie sich auf die Gebäude, die den größten Teil der TCP-Datenströme haben, um die Auswirkungen zu maximieren.

Die häufigste Ursache für die TCP-Nutzung sind fehlende Ausnahmeregeln in Firewalls oder Proxys. Wir werden uns im nächsten Abschnitt über Proxys unterhalten, also konzentrieren Sie sich vorerst auf die Firewalls. Wenn Sie das bereitgestellte Gebäude oder Subnetz verwenden, können Sie ermitteln, welche Firewall aktualisiert werden muss.

| Fehlerbehebung        | Anleitung     |
|--------------------|--------------------------------------|
| Konfigurieren der Firewall | Stellen Sie [sicher, Microsoft 365 oder Office 365-IP-Ports](/microsoft-365/enterprise/urls-and-ip-address-ranges) und -Adressen von Ihrer Firewall ausgeschlossen sind. Konzentrieren Sie sich bei medienbezogenen TCP-Problemen zunächst auf Folgendes:<ul><li>Vergewissern Sie sich, dass die Medien-Subnetze 13.107.64.0/18 und 52.112.0.0/14 des Clients in ihren Firewallregeln enthalten sind.</li><li>UDP-Ports 3478–3481 sind die erforderlichen Media-Ports und müssen geöffnet werden, andernfalls kehrt der Client zurück zu TCP-Port 443.</li></ul> |
| Überprüfen             | Verwenden Sie das [Microsoft-Netzwerkbewertungstool,](https://www.microsoft.com/download/details.aspx?id=53885) um nach Problemen mit der Konnektivität mit bestimmten Microsoft 365 oder Office 365 IP-Adressen und Ports aus dem betroffenen Gebäude oder Subnetz zu suchen.    |

### <a name="http-proxy"></a>HTTP-Proxy

HTTP-Proxys sind aus vielen verschiedenen Gründen nicht der bevorzugte Pfad zum Einrichten von Mediensitzungen. Viele bieten umfassende Funktionen zur Paketprüfung, die verhindern, dass Verbindungen mit dem Dienst ausgeführt werden, wodurch Unterbrechungen auftreten. Darüber hinaus erzwingen nahezu alle Proxys TCP im Gegensatz zu der zuzulassenden UDP-Funktion, die für optimale Audioqualität empfohlen wird.

Es wird immer empfohlen, den Client so zu konfigurieren, dass er eine direkte Verbindung mit Teams und Skype for Business-Diensten herstellt. Dies ist besonders wichtig für den medienbasierten Datenverkehr.


> [!IMPORTANT]
> Es wird empfohlen, [](CQD-upload-tenant-building-data.md) eine gültige Gebäudedatei hochzuladen, damit Sie sich bei der Analyse der Proxyverwendung von außerhalb des Audiodatenstroms unterscheiden können. 


#### <a name="http-proxy-usage"></a>Nutzung von HTTP-Proxys

Der Bericht über den HTTP-Proxy-Datenstrom in diesem Abschnitt der Vorlage ähnelt den TCP-Berichten. Es wird nicht nachschaut, ob Anrufe schlecht oder gut sind, aber ob der Aufruf über HTTP verbunden ist.

![Screenshot des Berichts über Audiodatenströme, die HTTP verwenden](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Analyse

Sie möchten so wenige HTTP-Medienstreams wie möglich sehen. Wenn Sie Datenströme über Ihren Proxy laufen sehen, wenden Sie sich an Ihr Netzwerkteam, um sicherzustellen, dass die richtigen Ausschlüsse vorhanden sind, damit die Kunden direkt an die Teams oder die Mediensubnetze von Skype for Business Online weitergeleitet werden.

Wenn Sie nur über einen Internetproxy in Ihrer Organisation verfügen, überprüfen Sie die korrekte Microsoft 365 oder Office 365 urLs und [IP-Adressbereichsausschlüsse .](/microsoft-365/enterprise/urls-and-ip-address-ranges) Wenn in Ihrer Organisation mehrere Internet-Proxys konfiguriert sind, können Sie mit dem HTTP-Unterbericht isolieren, welches Gebäude oder Subnetz betroffen ist.

Stellen Sie für Organisationen, die den Proxy nicht umgehen können, sicher, dass der Skype for Business-Client so konfiguriert ist, dass er sich ordnungsgemäß anmeldet, wenn er sich hinter einem Proxy befindet. Dies wird im Artikel [Skype for Business](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin)beschrieben, wenn anstelle einer direkten Verbindung ein Proxyserver zum Anmelden verwendet wird. 


#### <a name="http-proxy-investigations"></a>HTTP-Proxy-Untersuchungen

In diesem Bericht werden bestimmte Gebäude und Subnetze identifiziert, die zur HTTP-Nutzung beitragen.


##### <a name="remediation"></a>Fehlerbehebung

Wir [empfehlen](proxy-servers-for-skype-for-business-online.md), dass Sie die Proxys für Skype for Business und Teams immer umgehen, insbesondere für Mediendatenverkehr. Da der Datenverkehr bereits verschlüsselt ist, wird Skype for Business durch Proxys nicht sicherer. Leistungsbezogene Probleme können durch Latenz und Paketverluste in die Umgebung eingebracht werden. Solche Probleme führen zu einer negativen Erfahrung mit Audio, Video und Bildschirmfreigaben, in denen Echtzeitdatenströme unerlässlich sind.

Die häufigste Ursache für die HTTP-Nutzung sind fehlende Ausnahmeregeln in Proxys. Wenn Sie das bereitgestellte Gebäude oder Subnetz verwenden, können Sie schnell ermitteln, welcher Proxy für die Medienumgehung konfiguriert werden muss.

Stellen Sie sicher, [dass Microsoft 365 oder Office 365 FQDNs](/microsoft-365/enterprise/urls-and-ip-address-ranges) zu einer Allowlist in Ihrem Proxy hinzugefügt werden.

## <a name="endpoint-investigations"></a>Endpunktuntersuchungen

In diesem Abschnitt geht es um die Aufgaben für die Berichterstattung über Client-Versionen und die Verwendung zertifizierter Geräte. Es stehen Berichte zur Verfügung, die die Verwendung für Clientversionen, den Clienttyp, Erfassungsgeräte und Treiber (Mikrofon), Videoerfassungsgeräte und WLAN-Anbieter- und Treiberversionen umreißen.

> [!NOTE]
> Nicht alle in den Vorlagen enthaltenen Berichte werden in diesem Artikel behandelt. jedoch gelten die unten erläuterten Methoden zur Untersuchung weiterhin. Weitere Informationen finden Sie in der Beschreibung des jeweiligen Berichts.

### <a name="client-versions"></a>Clientversionen

Bei diesen Berichten geht es darum, Skype for Business verwendeten Clientversionen und deren relatives Volumen in der Umgebung zu identifizieren.

> [!IMPORTANT]
> Derzeit werden Teams-Clients automatisch über das Azure Content Delivery Network verteilt und aktualisiert und vom Dienst auf dem neuesten Stand gehalten. Daher müssen Sie keine Teams-Clientversionen überwachen (es sei denn, Sie deaktivieren die automatische Aktualisierung, was nicht empfohlen wird).

Sofern Sie keine Verbunddaten über die Teilnehmer ausschließen, umfassen diese Berichte die Clienttelemetrie von verbundenen Endpunkten. Um Verbundendpunkte auszuschließen, müssen Sie einen Abfragefilter für die Zweite Mandanten-ID hinzufügen, die der Mandanten-ID Ihrer [Organisation festgelegt ist.](CQD-data-and-reports.md#how-to-find-your-tenant-id) Alternativ können Sie einen [URL-Filter](CQD-data-and-reports.md#url-filters) verwenden, um die Telemetrie des Verbundteilnehmers auszuschließen.



#### <a name="remediation"></a>Fehlerbehebung

Ein wichtiger Teil der Gewährleistung einer qualitativ hochwertigen Benutzererfahrung besteht darin, sicherzustellen, dass die verwalteten Clients aktuelle Versionen von Skype for Business ausführen und dass die unterstützenden Audio-, Video-, Netzwerk- und USB-Treiber auf dem neuesten Stand sind. Das bietet verschiedene Vorteile, einschließlich: 

-   Im Vergleich zu vielen Versionen ist es einfacher, einige Versionen zu verwalten.
-   Dadurch wird eine gewisse Konsistenz der Benutzererfahrungen erreicht.
-   Dies erleichtert die Fehlersuche bei Problemen mit der Qualität von Anrufen und der Benutzerfreundlichkeit.
-   Microsoft führt kontinuierlich allgemeine Verbesserungen und Optimierungen im gesamten Produkt durch. Wenn Sie sicherstellen, dass Benutzer diese Updates erhalten, verringert sich das Risiko, dass ein bereits behobenes Problem auftritt.

Durch Einschränken ihrer Bereitstellung auf Clientversionen, die weniger als sechs Monate alt sind, können Sie die allgemeine Benutzererfahrung und die Verwaltbarkeit verbessern, indem Sie die Anzahl der unterstützten Versionen verringern.

Wenn Sie nur das Office Klick-und-Ausführen verwenden, wird das sechsmonatige Fenster automatisch angezeigt. Es sind keine weiteren Schritte erforderlich.

Wenn Sie über eine Kombination aus Klick-und-Los und Installationspaketen (MSI) verfügen, können Sie den Bericht verwenden, um zu überprüfen, ob die MSI-Clients regelmäßig aktualisiert werden. Wenn Sie feststellen, dass Kunden zurückfallen, arbeiten Sie mit dem Team zusammen, das für die Verwaltung von Office-Updates zuständig ist, und stellen Sie sicher, dass diese Clientpatches regelmäßig genehmigen und bereitstellen.

Darüber hinaus ist es wichtig, dass Netzwerk-, Video-, USB- und Audiotreiber ebenfalls mit Patches installiert werden. Diese Treiber können leicht übersehen und dadruch nicht in Ihre Patch-Verwaltungsstrategie einbezogen werden.

Die Versionsnummern für Skype for Business finden Sie über die folgenden Links:

-   [Versionsinformationen für Updates für Microsoft 365 Apps](/officeupdates/release-notes-office365-proplus)
-   [Updateverlauf für Microsoft 365 Apps for Enterprise](/officeupdates/update-history-office365-proplus-by-date)
-   [Skype for Business – Downloads und Updates](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Geräte

Um den Bericht über das Mikrofongerät nutzen zu können, müssen wir das Konzept des Mean Opinion Score (MOS) verstehen. MOS ist die wichtigste Norm zur Messung der empfundenen Tonqualität. Sie wird als ganzzahlige Bewertung von 0 bis 5 dargestellt.

Die Grundlage aller Messungen der Sprachqualität ist die Art und Weise, wie eine Person die Sprachqualität wahrnimmt. Da sie vom Menschen wahrgenommen wird, ist sie von Natur aus subjektiv. Es gibt mehrere unterschiedliche Methoden für die subjektive Prüfung. Die meisten Messungen für die VoIP-Qualität basieren auf einer ACR (Absolute Categorization Rating, d.h. Absolute Kategorisierungsbewertung).

Bei einer subjektiven ACR-Prüfung bewertet eine statistisch signifikante Anzahl von Personen ihre Erlebnisqualität auf einer Skala von 1 (schlecht) bis 5 (ausgezeichnet). Der Mittelwert der Ergebnisse ist der MOS. Der resultierende MOS hängt von der Reichweite der Erfahrungen ab, die der Gruppe ausgesetzt waren, und von der Art der Erfahrung, die bewertet wird.

Da es unpraktisch ist, für ein Live-Kommunikationssystem subjektive Tests der Sprachqualität durchzuführen, generieren Microsoft Teams und Skype for Business MOS-Werte mithilfe erweiterter Algorithmen, um die Ergebnisse eines subjektiven Tests objektiv vorherzusagen.

Der verfügbare Satz von MOS- und zugehörigen Metriken bietet einen Einblick in die Qualität der Benutzererfahrung, die von einem Audiogerät an die Benutzer gesendet wird. 

Indem Sie den Benutzern Geräte zur Verfügung stellen, die für Teams und Skype for Business zertifiziert sind, verringern Sie die Wahrscheinlichkeit negativer Erfahrungen, die auf das Gerät selbst zurückzuführen sind (was z. B. bei eingebauten Laptop-Lautsprechern und Mikrofonen wahrscheinlicher ist). Weitere Informationen finden Sie in diesen Artikeln über das [Zertifizierungsprogramm](/SkypeForBusiness/certification/overview) und den [Katalog der Partnerlösungen](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Die Geräteberichte werden verwendet, um die Gerätenutzung nach Volumen und MOS-Bewertung (nur Audio) zu bewerten, und sie sind in den zugehörigen Vorlagen unter Clients & Geräte zu finden. 

> [!IMPORTANT]
> Sofern Sie keine Verbunddaten über die Teilnehmer ausschließen, umfassen diese Berichte die Clienttelemetrie von verbundenen Endpunkten. Um Verbundendpunkte auszuschließen, müssen Sie einen Abfragefilter für die Zweite **Mandanten-ID** hinzufügen, die der Mandanten-ID Ihrer [Organisation festgelegt ist.](CQD-data-and-reports.md#how-to-find-your-tenant-id) Alternativ können Sie einen [URL-Filter](CQD-data-and-reports.md#url-filters) verwenden, um die Telemetrie des Verbundteilnehmers auszuschließen.


> [!Note]
> Möglicherweise bemerken Sie beim Anzeigen dieses Berichts, dass das gleiche Gerät mehrmals gemeldet wurde. Dies ist auf die Art und Weise zurückzuführen, wie das Gerät an das CQD gemeldet wird. Unterschiede in der Hardware und im Betriebssystem-Gebietsschema führen zu Unterschieden in der Art und Weise, wie Gerätedaten gemeldet werden.

##### <a name="remediation"></a>Fehlerbehebung

In der Regel müssen Sie nicht zertifizierte Geräte ermitteln und ausdingen und durch zertifizierte Geräte ersetzen. Einige Überlegungen bei der Überprüfung der Geräteberichte umfassen:

-   Sind die verwendeten Geräte für Teams und Skype for Business zertifiziert? 
-   Sie können benutzerspezifische Anrufanalysen verwenden, um Benutzer [eines bestimmten Geräts zu identifizieren.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Stellen Sie sicher, dass die aktuellen Gerätetreiber installiert sind und das Gerät nicht über einen USB-Hub oder eine Dockingstation verbunden ist. 
-   Wie viele verschiedene Versionen unterschiedlicher Treiber werden verwendet? Werden diese regelmäßig gepatcht? Wenn Sie sicherstellen, dass Audio-, Video- und WLAN-Treiber regelmäßig gepatcht werden, können Sie diese als Quelle für Qualitätsprobleme ausschließen und die Benutzererfahrung vorhersehbarer und konsistenter machen.

##### <a name="audio"></a>Audio

Die nächste Aufgabe besteht darin, die allgemeine Nutzung von [zertifizierten Audiogeräten](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) zu ermitteln. Wir empfehlen, dass mindestens 80 Prozent aller Audiodatenströme über ein zertifiziertes Audiogerät erfolgen. Dazu exportieren Sie den Bericht "Mikrofongeräte" nach Excel, um die Verwendung von zertifizierten oder zugelassenen Geräten zu berechnen. Die Organisationen führen in der Regel eine Liste aller zugelassenen Geräte aus, daher sollten Sie die Daten ohne Weiteres filtern und sortieren können.

##### <a name="video"></a>Video

Außerdem ist es wichtig, dass Videotreiber aktualisiert werden. Wenn Sie sicherstellen, dass Videokarten regelmäßig gepatcht werden, können Sie die Videotreiber als Quelle schlechter Qualität für Videodatenströme ausschließen. Die Verwendung [zertifizierter Videogeräte](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) trägt dazu bei, eine reibungslose und qualitativ hochwertige Benutzererfahrung zu gewährleisten. Videogeräte, die die native Codierung von H.264 unterstützen, werden bevorzugt, um die CPU-Auslastung während Videokonferenzen zu verringern.

##### <a name="wi-fi"></a>WLAN

Außerdem müssen die WLAN-Treiber in regelmäßigen Abständen gepatcht werden und sollten in Ihre Patch-Verwaltungsstrategie einbezogen werden. Viele Qualitätsprobleme lassen sich beheben, indem Sie die WLAN-Treiber auf dem neusten Stand halten. Weitere Informationen zur Optimierung Ihrer WLAN-Infrastruktur finden Sie [in diesem Artikel über die WLAN-Planung](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Ratgeber Teams](use-advisor-teams-roll-out.md)

[Vorbereiten Ihres Netzwerks für Teams](prepare-network.md)

[Prinzipien von Office 365-Netzwerkverbindungen](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams – Analyse und Berichterstellung](teams-analytics-and-reports/teams-reporting-reference.md)

[Verwalten Ihrer Geräte in Teams](./devices/device-management.md).

[Verbessern und überwachen Sie die Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Stream Classification in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)