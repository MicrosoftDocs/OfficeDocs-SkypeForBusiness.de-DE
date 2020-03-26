---
title: Leitfaden zur Überprüfung der Erlebnisqualität für Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: siunies, gageames
audience: admin
description: Leitfaden zum Analysieren der Leistung von Echtzeit-Medien für Microsoft Teams mithilfe des Dashboards für Anrufqualität (Call Quality Dashboard, CQD).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ced9ab01c5f33ef2b8095079443c447c301ee742
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978597"
---
# <a name="quality-of-experience-review-guide"></a>Leitfaden zur Überprüfung der Erlebnisqualität

<!-- Note that this link to the Word doc is intentionally NOT the aka.ms/qerquide link -->
In diesem Leitfaden finden Sie Informationen zur Wertschöpfungsphase für Microsoft Teams und Skype for Business Online. Sie können eine Word-Version dieses Leitfadens [herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true).

## <a name="introduction"></a>Einführung

Um die größtmögliche Wirkung auf die Verbesserung der Benutzererfahrung zu haben, müssen Organisationen die wichtigsten Bereiche operationalisieren, die in der folgenden Abbildung dargestellt sind. Weitere Bereiche umfassen das Identifizieren von operativen Aufgaben, das Festlegen von Zielen für Qualitätskennzahlen, das Ermitteln der Metriken zur Messung des organisatorischen Erfolgs und das Präzisieren von Untersuchungsbereichen nach Bedarf.


![Die wichtigsten Bereiche für die Qualität der Benutzererfahrung](media/qerguide-image-keyareas.png "Die wichtigsten Bereiche für die Qualität der Benutzererfahrung sind Audio, Zuverlässigkeit, Benutzerumfragen, Geräte und Clients.")

_Abbildung 1 – Wichtige Betriebsbereiche, die in diesem Leitfaden behandelt werden_

Durch kontinuierliches Bewerten und Verbessern der in diesem Leitfaden beschriebenen Bereiche können Sie die Wahrscheinlichkeit verringern, dass sie sich nachteilig auf die Qualität Ihrer Benutzerfreundlichkeit auswirken. Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:

-   Unvollständige Firewall- oder Proxykonfiguration
-   Schlechte WLAN-Abdeckung
-   Unzureichende Bandbreite
-   VPN
-   Inkonsistente oder veraltete Clientversionen und Treiber
-   Nicht optimierte oder integrierte Audiogeräte
-   Problematische Subnetze oder Netzwerkgeräte

Durch die ordnungsgemäße Planung und Gestaltung vor der Bereitstellung von Teams oder Skype for Business Online können Sie den Aufwand verringern, der erforderlich ist, um die hohe Qualität des Erlebnisses aufrechtzuerhalten.

Dieser Leitfaden konzentriert sich auf die Verwendung des online verfügbaren Anrufqualitäts-Dashboards (AQD) als primäres Tool zum Melden und Untersuchen der einzelnen Bereiche. Der Schwerpunkt liegt dabei auf Audio, um die Einführung und die Auswirkungen zu maximieren. Alle zur Optimierung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Um Ihre Bewertung zu beschleunigen, werden [zwei zusammengestellte CQD-Vorlagen](https://aka.ms/qertemplates) bereitgestellt: eine ist für die Verwaltung aller Netzwerke und die andere wird nur nach verwalteten (internen) Netzwerken gefiltert. Obwohl die Vorlagenberichte „Alle Netzwerke“ so konfiguriert sind, dass sie Gebäude- und Netzwerkinformationen anzeigen, können sie dennoch verwendet werden, während Sie auf die Erfassung und das Hochladen von Gebäudeinformationen hinarbeiten. Durch das Hochladen von Gebäudeinformationen in CQD kann der Dienst die Berichterstellung verbessern, indem benutzerdefinierte Gebäude-, Netzwerk- und Standortinformationen hinzugefügt werden, wobei zwischen internen und externen Subnetzen unterschieden wird. Weitere Informationen finden Sie unter [Gebäudezuordnung](#building-mapping) weiter unten in diesem Leitfaden.

### <a name="intended-audience"></a>Zielgruppe

Dieser Leitfaden richtet sich an Beteiligten seitens der Partner und Kunden mit Rollen wie „Zusammenarbeitsleiter/ Architekt", "Berater", "Change Management-/ Einführungsexperte", "Support-/ Helpdesk-Leiter", "Netzwerk-Leiter", "Desktop-Leiter" und „IT-Administrator“ arbeiten.

Dieser Leitfaden ist auch für die Verwendung durch die benannten Qualitätsverantwortlichen vorgesehen. Weitere Informationen finden Sie unter [Die Rolle des Qualitätspioniers](4-envision-plan-my-service-management.md#the-quality-champion-role).

## <a name="assign-roles-for-accessing-cqd"></a>Zuweisen von Rollen für den Zugriff auf CQD

Bevor Sie diesen Leitfaden verwenden, stellen Sie sicher, dass Sie die richtigen [Mandantenrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) zugewiesen haben, damit Sie auf CQD zugreifen können.

In dieser Tabelle wird dargestellt, was jede einzelne Rollen in CQD tun darf:


|  |Berichte anzeigen  |EUII-Felder anzeigen  |Berichte erstellen  |Gebäudedaten hochladen  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Globaler Office 365-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Dienstadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationsadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationssupporttechniker     |Ja         |Ja         |Ja         |Nein         |
|Supportfachmann für die Teams-Kommunikation     |Ja         |Nein         |Ja         |Nein         |
|Skype for Business-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Azure AD globaler Leseberechtigter |Ja         |Ja         |Ja         |Nein         |
|Office 365-Berichtleseberechtigter<sup>1</sup>     |Ja         |Nein         |Ja         |Nein         |

<sup>1</sup> Zusätzlich zum Lesen von CQD-Berichten kann der Office 365-Berichtleseberechtigter alle [Aktivitätsberichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Admin Center sowie alle Berichte aus dem [Inhaltspaket zur Microsoft 365-Einführung](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) anzeigen.

> [!NOTE]
> Wenn Sie keine EUII sehen („end-user identifiable information“ – identifizierbare Informationen über den Endbenutzer) und Sie eine der Rollen haben, die diese Informationen anzeigen dürfen, denken Sie daran, dass CQD EUII nur 30 Tage lang aufbewahrt. Alle Elemente, die älter als 30 Tage sind, werden gelöscht.

## <a name="what-is-quality"></a>Was ist Qualität?

Wenn Qualität in Teams und Skype for Business diskutiert wird, ist es wichtig, den Begriff zu definieren, um ein gemeinsames Verständnis zu erzielen. Die hier definierte Qualität ist eine Kombination aus Dienstmetriken und Benutzererfahrung.

<!-- Note: need to update graphic-->
![Darstellung der Dienstmetriken und der Benutzererfahrung](media/qerguide-image-whatisquality.png "Die Dienstmetriken setzen sich aus einem schlechten Datenstromverhältnis, der Zuverlässigkeit, den Endpunkten/ Geräten und den Client-Versionen zusammen. Die Benutzererfahrung setzt sich aus der Wahrnehmung der Qualität des Dienstes durch den Benutzer zusammen.")

_Abbildung 2 – Was ist Qualität?_

### <a name="service-metrics"></a>Dienstmetriken

Die Dienstmetriken umfassen bestimmte clientbasierten Metriken. Während jedes Anrufs sammelt der Client Telemetrie-Informationen zu dem Anruf und übermittelt einen Bericht am Ende jedes Anrufs, auf den später über CQD oder die [Anrufanalyse](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) zugegriffen werden kann. Diese Metriken umfassen:

-   Schwache Stromrate
-   Aufbaufehlerrate
-   Abbruchfehlerrate


#### <a name="poor-stream-rate"></a>Schwache Stromrate

Die schwache Stromrate (poor stream rate, PSR) stellt den Gesamtanteil der Ströme mit schlechter Qualität in der Organisation dar. Diese Metrik soll Bereiche hervorheben, auf die sich Ihre Organisation konzentrieren kann, um den größten Einfluss auf die Reduzierung dieses Wertes und die Verbesserung des Benutzererlebnisses zu erzielen. Deshalb stehen [verwaltete Netzwerke](#managed-vs-unmanaged-networks) bei der Betrachtung des PSR im Vordergrund. Externe Benutzer sind ebenfalls wichtig, die Untersuchungen sind aber für die verschiedenen Betriebsebenen unterschiedlich. Überlegen Sie sich, bewährte Methoden für externe Benutzer bereitzustellen und externe Anrufe unabhängig von der Gesamtorganisation zu untersuchen.

Die tatsächliche Messung in CQD variiert je nach Auslastung, aber für die Zwecke der Überprüfung der Erlebnisqualität konzentrieren wir uns hauptsächlich auf die Messung _Anteil der Anrufe mit schlechter Qualität_. Die PSR besteht aus den fünf durchschnittlichen Netzwerkmetriken, die in der folgenden Tabelle beschrieben sind. Damit ein Strom als schwach eingestuft wird, muss nur eine der Metriken den definierten Grenzwert überschreiten. Weitere Informationen zum Stromklassifizierungsprozess finden Sie in [diesem Artikel](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> CQD liefert die "Schwach auf der Basis von..." -Messungen, um besser zu verstehen, welcher Zustand dazu führte, dass der Strom als schlecht eingestuft wurde.


_Tabelle 1 – Metriken für Audio mit schlechter Qualität_

| Mittelwert der Metrik     | Beschreibung     | Benutzererfahrung |
|-------------|-----------------|-----------------|
| Jitter \>30 ms        | Dies ist die durchschnittliche Änderung bei der Verzögerung zwischen aufeinander folgenden Paketen. Teams und Skype for Business können ein gewisses Maß an Jitter durch Pufferung ausgleichen. Erst wenn der Jitter die Pufferung übersteigt, bemerken die Teilnehmer die Auswirkungen.      | Dass Pakete mit unterschiedlichen Geschwindigkeiten ankommen, führt dazu, dass die Stimme des Sprechers robotisch klingt.   |
| Paketverlustrate \>10 % oder 0,1        | Diese Eigenschaft wird oft als prozentualer Anteil der Pakete gemessen, die verloren gegangen sind. Paketverluste wirken sich direkt auf die Audioqualität aus. Sie reichen vom Verlust einzelner kleiner Pakete, der fast keine Auswirkung hat, bis hin zu direkt aufeinander folgenden Burstverlusten, die zu Tonaussetzern führen.     | Die verworfenen und nicht am vorgesehenen Bestimmungsort ankommenden Pakete führen zu Lücken in den Medien, was zu fehlenden Silben und Wörtern sowie abgehacktem Video und Störungen bei der Freigabe führen kann. |
| Round-trip-Zeit \>500 ms        | Dies ist die Zeit, die benötigt wird, um ein IP-Paket von Punkt А nach Punkt B und zurück zu Punkt А zu senden. Diese Verzögerung der Weitergabe im Netzwerk ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verknüpft. Dazu gehört auch der Mehraufwand durch die zwischen den Punkten vorhandenen Geräten.      | Die Pakete, die zu lange dauern, bis sie an Ihr Ziel gelangen, führen zu einem Walkie-Talkie-Effekt.   |
| NMOS-Beeinträchtigungsdurchschnitt \>1,0         | Durchschnittliche Beeinträchtigung des [Netzwerk-MOS (Mean Opinion Score)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) für den Datenstrom. Stellt dar, wie stark sich der Netzwerkverlust und der Jitter auf die Qualität des empfangenen Audios auswirkten, das dazu führte, dass der NMOS um mehrere Punkte sank. | Hierbei handelt es sich um eine Kombination aus Jitter, Paketverlust und – zu einem geringeren Grad – erhöhter Round-trip-Zeit. Möglicherweise erfährt der Benutzer eine Kombination dieser Symptome.   |
| Durchschnittsanteil der verdeckten Beispiele \>7 % oder 0,07 | Durchschnittliches Verhältnis der Anzahl der Audioframes mit verdeckten Beispielen, die durch die Paketverlustreparatur generiert wurden, zur Gesamtzahl der Audioframes. Versteckte Audiobeispiele sind ein Verfahren zum „Glätten“ der „holprigen“ Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.      | Ein hoher Wert gibt an, dass Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.     |

#### <a name="setup-failure-rate"></a>Aufbaufehlerrate

Die Aufbaufehlerrate, die in CQD auch als Messung des _Gesamtprozentsatzes der Aufbaufehler_ bezeichnet wird, ist die Anzahl der Ströme, bei denen der Medienpfad zwischen den Endpunkten zu Beginn des Anrufs nicht hergestellt werden konnte.

Dies stellt jeden Medienstrom dar, der nicht eingerichtet werden konnte. Angesichts des Schweregrads der Auswirkungen auf die hier gemessene Benutzererfahrung besteht das Ziel darin, diesen Wert möglichst auf Null zu reduzieren. Ein hoher Wert für diese Metrik ist in neuen Bereitstellungen mit unvollständigen Firewallregeln häufiger als bei einer ausgereiften Bereitstellung, aber es ist immer wichtig, dass sie in regelmäßigen Abständen beobachtet wird.

Diese Metrik wird berechnet, indem die Gesamtzahl der Ströme, die nicht eingerichtet werden konnten, durch die Gesamtzahl der Ströme geteilt wird, die einen erfolgreichen Kommunikationsdatensatz (Call Detail Record, CDR) gesendet haben:

-   **Aufbaufehlerrate** = Gesamtanzahl der Ströme mit Ausfall des Rufaufbaus / Gesamtzahl der Ströme mit verfügbarem CDR

#### <a name="drop-failure-rate"></a>Abbruchfehlerrate

Die Abbruchfehlerrate, auch bekannt als die Messung der _Gesamtausfallrate bei Abbruch_ im CQD (Total Call Dropped Failure Percentage), ist der Prozentsatz der erfolgreich aufgebauten Streams, bei denen der Medienpfad nicht normal beendet wurde.

Das steht für jeden Medienstrom, der unerwartet beendet wurde. Obwohl die Auswirkungen dieses Fehlers nicht so stark sind wie ein Strom, der nicht aufgebaut werden konnte, hat dies einen negativen Einfluss auf die Benutzererfahrung. Plötzliche und häufige Medienabbrüche können nicht nur die Benutzererfahrung erheblich beeinträchtigen, sondern sie führen dazu, dass Benutzer wieder verbunden werden müssen, was zu einem Produktivitätsverlust führt.

Die Metrik wird berechnet, indem die Gesamtzahl der abgebrochenen Ströme durch die Gesamtzahl der erfolgreich aufgebauten Datenströme dividiert wird:

-   **Abbruchfehlerrate** = Gesamtanzahl der abgebrochenen Anrufströme / Gesamtzahl der Ströme mit erfolgreichem Rufaufbau

### <a name="define-your-target-metrics"></a>Definieren Ihrer Zielmetriken

In diesem Abschnitt werden einige der zentralen Dienstmetriken erörtert, die wir zur Bewertung der Statuserfassung von Diensten verwenden. Indem Sie die Bemühungen, diese Kennzahlen unter den definierten Zielen zu halten, kontinuierlich bewerten und vorantreiben, tragen Sie dazu bei, dass Ihre Benutzer eine konsistente, zuverlässige Anrufqualität erhalten. Für die ersten Schritte werden die folgenden Ziele bereitgestellt.

_Tabelle 2 – Kernmetriken für die Statusbewertung_
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


Es ist wichtig, die Ziele Ihrer Organisation zu besprechen und zu definieren, um Ihre geschäftlichen Ziele zu erreichen.

### <a name="user-experience"></a>Benutzererfahrung

Die Analyse der Benutzererfahrung ist eher Kunst als Wissenschaft, da die hier versammelten Metriken nicht immer bedeuten, dass es ein Problem mit dem Netzwerk oder dem Dienst gibt, sondern einfach angeben, dass der Benutzer ein Problem wahrnimmt. Microsoft bietet einen integrierten Umfragemechanismus – bezeichnet als "Meinen Anruf bewerten (Rate My Call, RMC)", – um die allgemeine Benutzerfreundlichkeit zu beurteilen. Mithilfe von RMS können die folgenden Fragen aus der Sicht der Benutzer beantworten:

-   Weiß ich, wie die Lösung zu verwenden ist?
-   Ist die Lösung benutzerfreundlich und intuitiv und unterstützt Sie die täglichen Kommunikationsanforderungen?
-   Hilft mir die Lösung beim erledigen meiner Aufgabe?
-   Was halte ich von der Lösung im Allgemeinen?
-   Kann ich die Lösung jederzeit verwenden – unabhängig davon, wo ich gerade bin?
-   Kann ich einen Anruf aufbauen und aufrechterhalten?

#### <a name="rate-my-call"></a>Meinen Anruf bewerten 

„Meinen Anruf bewerten“ (Rate My Call, RMC) ist in Teams und Skype for Business integriert und wird automatisch so konfiguriert, dass es dem Teilnehmer nach jeweils 10 anrufen oder 10 Prozent angezeigt wird. In dieser kurzen Umfrage wird der Benutzer gebeten, den Anruf zu bewerten und ein wenig Kontext dafür zu liefern, warum die Anrufqualität schlecht gewesen sein könnte. Ein oder zwei Bewertungen werden als unzureichend betrachtet, drei bis vier sind gut und fünf ist ausgezeichnet. Obwohl es sich gewissermaßen um einen verzögerten Indikator handelt, ist dies eine hilfreiche Metrik zur Aufdeckung von Problemen, die von Dienstmetriken nicht entdeckt werden können.

> [!Note]
> Solange die Benutzer nicht dazu geschult werden, auf RMC-Umfragen nicht nur mit schlechtem, sondern auch mit gutem Feedback zu antworten, werden die Antworten in der Regel als überwältigend negativ zurückkommen. Die meisten Benutzer Antworten nur, wenn die Anrufqualität schlecht ist. Aus diesem Grund sind Ihre RMAC-Berichte möglicherweise eher schlecht, auch wenn die Dienstmetriken gut sind.

Sie können CQD verwenden, um über die Benutzerreaktionen von RMC zu berichten und Beispielberichte sind in der CQD-Vorlage enthalten. Sie werden jedoch nicht in diesem Leitfaden im Detail erläutert. Weitere Informationen zu RMC in Skype for Business Online und Anleitungen für die Schulung der Benutzer zur Bereitstellung von nützlichen Reaktionen auf die RMC finden Sie in [diesem Blogbeitrag](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

#### <a name="client-and-device-readiness"></a>Client- und Gerätebereitschaft

Sie benötigen eine solide Client- und Gerätestrategie, um sicherzustellen, dass Ihre Benutzer eine konsistente und positive Benutzererfahrung haben. Jede Bereitschaftsstrategie beruht auf einigen wenigen Schlüsselprinzipien.

##### <a name="client-readiness"></a>Client-Bereitschaft

Eine starke Client-Bereitschaftsstrategie stellt sicher, dass Ihre Benutzer die aktuellste Version des Clients ausführen und gleichzeitig die bestmögliche Erfahrung machen. Der Skype for Business-Client wird von Microsoft regelmäßig gepatcht. Sicherstellen, dass Sie die Daten in Ihrer Umgebung stets auf dem neuesten Stand halten, ist für Ihren Gesamterfolg unerlässlich. Außerdem ist es wichtig, dass Sie sich daran erinnern, Netzwerk-, Video-, USB- und Audiotreiber zu patchen, da sie häufig übersehen werden und sich auf die Benutzererfahrung auswirken können. Überlegen Sie sich, Netzwerk-, WLAN-, Video-, USB -und Audiotreibern zum aktuellen Patchverwaltungsvorgang hinzuzufügen.

Wir empfehlen Ihnen, Ihre Client-Versionen nicht länger als sechs Monate in Rückstand geraten zu lassen. Wenn Sie mit Office Klick-und-Los arbeiten, werden Sie vom Dienst bereits auf dem neuesten Stand gehalten. Verwenden Sie die im Lieferumfang enthaltenen [Client-Versionen](#client-versions), wie weiter unten in diesem Leitfaden beschrieben, um Unterstützung bei diesem Vorgang zu erhalten. Sie können auch die Beispielberichte von „;Meine Anrufe bewerten" verwenden, um Ihre Client-Bereitschaftsstrategie weiter auszufeilen.

> [!IMPORTANT]
> Derzeit werden Teams-Clients automatisch über das Azure Content Delivery Network verteilt und aktualisiert und vom Dienst auf dem neuesten Stand gehalten. Aus diesem Grund sind Client-Bereitschaft und Ermittlungsaktivitäten nicht für Teams anwendbar.


##### <a name="device-readiness"></a>Gerätebereitschaft

Keine einzelne Strategie kann das Benutzererlebnis mehr beeinflussen als Ihre Strategie zur Gerätebereitschaft. In den meisten Organisationen ist es sehr wahrscheinlich, dass nicht benötigte Geräte (z. B. Telefonapparate oder andere dedizierte Audiogeräte) von Benutzern entfernt werden. Dies ist häufig ein grundlegender geschäftlicher Grund für den Wechsel zu Teams oder Skype for Business. Die gleichen Organisationen zögern aber manchmal, Ersatzgeräte bereitzustellen, auch wenn diese Geräte billiger sind. Laptops und PCs mit integriertem Mikrofon und Lautsprecher sind heute nicht für VoIP der Unternehmensklasse optimiert. Dies verursacht häufig eine schlechte Benutzererfahrung für alle Teilnehmer, insbesondere, wenn sich der Sprecher in einer lauten Umgebung befindet. Das Gerätezertifizierungsprogramm von Microsoft stellt sicher, dass ein Benutzer, der mit einem von Teams oder Skype for Business zertifizierten Gerät an einem Telefonanruf teilnimmt, eine besser Erfahrung als an einem nicht zertifizierten Gerät hat. 

Wir empfehlen immer, dass Teams und Skype for Business-Benutzer ein zertifiziertes Headset oder einen Sprecher verwenden, wenn Sie an einem Sprachanruf über den Desktop-Client teilnehmen. Weitere Informationen zu Geräten, die von Microsoft zertifiziert sind, finden Sie in den folgenden Artikeln zum [Zertifizierungsprogramm](/SkypeForBusiness/certification/overview) und zum [Katalog der Partnerlösungen](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Verwenden Sie den [Gerätebericht](#devices) für Unterstützung bei der Verwaltung Ihrer Geräte, die weiter unten in diesem Leitfaden beschrieben sind.


### <a name="categories-of-quality"></a>Qualitätskategorien

Der Erfolg von der Operationalisierung eine qualitativ hochwertige und zuverlässige Bereitstellung hängt von dem Aufbau operativer Exaktheit ab. Achten Sie insbesondere auf die drei Kategorien, die in der folgenden Abbildung dargestellt sind. Sie sind der Schwerpunkt dieses Leitfadens:

-   **Netzwerk:** Audioqualität, die sich auf die Metrik "Schwache Stromrate (PSR)", TCP-Nutzung, verdrahtete und drahtlose Subnetze und die Erkennung der Verwendung von HTTP-Proxys und VPN konzentriert.

-   **Endpunkte:** Audiogeräte und Client-Versionen (nur Skype for Business).

-   **Dienstverwaltung:** diese Kategorie umfasst zwei Abschnitte:

    -   An erster Stelle geht es um die Verantwortung von Microsoft, die Teams- und Skype for Business Online-Dienste zu verwalten und aufrechtzuerhalten.

    -   An zweiter Stelle kommen die Aufgaben, die Ihre Organisation verwalten muss, um einen zuverlässigen Zugriff auf den Dienst zu gewährleisten, z. B. die Aktualisierung von Gebäudeinformationen und die Verwaltung von Firewalls für neue Office 365-IP-Adressen, wenn dem Dienst Infrastruktur hinzugefügt wird.

![Diagramm der Qualitätskategorien in einer Organisation](media/qerguide-image-categories.png "Die Qualitätskategorien in einer Organisation: Dienstverwaltung, Endpunkte und das Netzwerk.")

_Abbildung 3 – Wichtige Kategorien für die Bereitstellung von Teams und Skype for Business Online_

In der folgenden Abbildung sind die Aufgaben aufgeführt, die Sie für jede Kategorie erledigen müssen. Wir empfehlen Ihnen, diese Aufgaben mindestens einmal pro Woche auszuführen.

Wenn Sie diese Aufgaben zum ersten Mal ausführen, müssen Sie mehr Aufwand als nachfolgende Durchläufe ausführen, da für viele dieser Kategorien die Überprüfung ihrer Bereitstellungskonfigurationen erforderlich ist. Nachdem Sie den gewünschten Zustand erreicht haben, indem Sie die von Ihnen festgelegten Ziele erreichen, können Sie diesen Status beibehalten.

<!--  This is a net new graphic, never was included in the online article. OOPS! -->
![Liste der wöchentlichen Aufgaben pro Qualitätskategorie](media/qerguide-image-tasks.png "Liste der wöchentlichen Aufgaben pro Qualitätskategorie")

#### <a name="service-management-tasks"></a>Dienstverwaltungsaufgaben

In einer von der Cloud abhängigen Umgebung müssen Sie bestimmte Dienstverwaltungsaufgaben ausführen, um eine qualitativ hochwertige Benutzererfahrung zu sichern. Diese Aufgaben reichen von der Sicherstellung einer ausreichenden Bandbreite, um den Dienst ohne Sättigung der Internetverbindungen zu erreichen, über die Validierung der Dienstqualität (QoS) in allen verwalteten Netzwerkbereichen bis hin zu den [IP-Bereichen von Office 365 auf Firewalls](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Netzwerkaufgaben

Es gibt zwei Kategorien von Netzwerkaufgaben: Zuverlässigkeit und Qualität. Der Schwerpunkt der Zuverlässigkeit ist die Messung der Fähigkeit des Benutzers, Anrufe erfolgreich zu tätigen die Verbindung aufrechtzuerhalten. Der Fokus der Qualität liegt auf der aggregierten Telemetrie, die vom Client des Benutzers während des Anrufs und nach dessen Beendigung an Teams und Skype for Business Online gesendet wird. 

Angesichts des kritischen Einflusses, den die Zuverlässigkeit auf die Benutzererfahrung hat, ist es wichtig, dass Sie mit der Beurteilung und Untersuchung dieser Metriken beginnen, bevor Sie sich auf die Qualität stürzen. 

#### <a name="endpoints-tasks"></a>Endpunktaufgaben

Die Hauptaufgabe in dieser Kategorie ist die Überprüfung, welche Client-Versionen in den letzten sechs Monaten in Skype for Business auf dem Desktop ausgeführt werden, um sicherzustellen, dass die Benutzer von den kontinuierlichen Optimierungen profitieren, die am Desktop-Client für Skype for Business vorgenommen werden. Darüber hinaus vereinfacht dies die allgemeinen Client-Verwaltungsaufgaben und bietet eine konsistente Benutzererfahrung.

Zu den anderen wichtigen Bereichen gehört das Überwachen der Geräte, die bei der Bereitstellung weit verbreitet sind, und das Antreiben der Verwendung von zertifizierten Geräten, um eine optimale Benutzererfahrung zu bieten.


> [!IMPORTANT]
> Derzeit werden Teams-Clients automatisch über das Azure Content Delivery Network verteilt und aktualisiert und vom Dienst auf dem neuesten Stand gehalten. Client-Bereitschaft und Ermittlungsaktivitäten sind nicht für Teams anwendbar.

## <a name="cqd-basics"></a>Grundlagen von CQD

In diesem Abschnitt werden die Grundlagen der Arbeit mit CQD beschrieben. Hier finden Sie Anleitungen für die folgenden Themen:

-   Was ist CQD?
-   Erwartungen bei der Verwendung von CQD
-   Auffinden Ihrer Mandanten-ID
-   Berichterstattung in Microsoft Teams im Vergleich zu Skype for Business
-   Klassifizierung als erster vs. zweiter Endpunkt
-   Dimensionen, Messungen und Filter
-   Ströme im Vergleich zu Anrufen
-   Gute, schlechte und nicht klassifizierte Anrufe
-   Häufig verwendete Subnetze

Ausführlichere Schulungen und Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="what-is-cqd"></a>Was ist CQD?

Das Dashboard für die Anrufqualität (Call Quality Dashboard, CQD) wird verwendet, um Einblicke in die die Qualität von Anrufen, die mit Teams und Skype for Business-Diensten getätigt wurden, zu erhalten. CQD ist so konzipiert, dass die Admins und Netzwerkingenieure von Skype for Business und Teams das Netzwerk optimieren und die Qualität, die Zuverlässigkeit und das Benutzererlebnis im Auge behalten können. CQD befasst sich mit der aggregierten Telemetrie eines ganzen Unternehmens, in der sich allgemeine Muster erkennen lassen, die Mitarbeiter in die Lage versetzen, informierte Einschätzungen zu treffen und Problembehebungsmaßnahmen zu planen, um die Wirkung zu maximieren. CQD bietet Metrikenberichte, die Einblicke in die Qualität, Zuverlässigkeit und Benutzerfreundlichkeit bieten.

Dieser Leitfaden hilft Ihnen, die Kernkonzepte von CQD zu verstehen, damit Sie den größtmöglichen Einfluss auf die Verbesserung der Erfahrungen Ihrer Nutzer mit Teams oder Skype for Business Online ausüben können. Weitere CQD-Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="expectations-using-cqd"></a>Erwartungen bei der Verwendung von CQD

CQD ist zwar nützlich für die Analyse von Trends und Subnetzen, ermöglicht aber nicht immer die Ermittlung einer spezifischen Ursache für ein bestimmtes Szenario. Es ist wichtig, dass Sie dies wissen und bei der Verwendung von CQD die richtige Erwartung festlegen:

-   CQD stellt nicht die Ursache für jedes Szenario dar.
-   CQD enthält keine Telefonsystem- oder Audiokonferenzströme.
-   Das CQD wird auf der Grundlage von Tendenzen Bereiche für weitere Untersuchungen aufzeigen.

### <a name="report-editions"></a>Berichtsversionen

Es gibt zwei Berichtsversionen in CQD Online: Zusammenfassung und Detailliert. Verwenden Sie das Dropdownmenü in der Leiste am oberen Rand des Bildschirms, um eine Berichtsversion zu öffnen. Der Name der ausgewählten Berichtsversion wird am oberen Rand des Bildschirms angezeigt.

-   Zusammenfassungsberichte sind statisch und können nicht bearbeitet, heruntergeladen oder exportiert werden. 
-   Detaillierte Berichte sind vollständig anpassbar und können in eine CSV-Datei heruntergeladen, exportiert oder geklont werden.

Eine vollständige Beschreibung des Unterschieds zwischen den beiden Versionen finden Sie in [diesem Artikel](turning-on-and-using-call-quality-dashboard.md).

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

_Abbildung 4 – CQD-Berichtskategorien_

Die Zusammenfassungsberichte sind in vier Kategorien unterteilt:

-   Der Schwerpunkt der **Zusammenfassungsberichte** liegt auf der Analyse von Qualitätstendenzen mit täglichen, monatlichen und Tabellenberichten zur Unterstützung bei der Identifizierung von Subnetzen, die schlechte Qualität aufweisen. Das ist die standardmäßige Startseite, wenn Sie sich zum ersten Mal bei CQD Online anmelden.
-   Bei den **standortbezogenen Berichten** liegt der Schwerpunkt auf der Analyse von Qualitätstendenzen basierend auf Standortinformationen. Um diese Berichte zu verwenden, müssen Sie eine Gebäudedatei hochgeladen haben.
-   Bei **Zuverlässigkeitsberichten** liegt der Schwerpunkt auf der Analyse von Zuverlässigkeitstendenzen für Audio, Video, videobasierte Bildschirmfreigabe (VBSS) und die App-Freigabe.
-   Die **Berichte über die Erlebnisqualität** sind eine "abgespeckte" Version der detaillierten QER-Vorlagen, die sich auf die wichtigsten Bereiche für die Analyse der Audioqualität und Zuverlässigkeit konzentrieren.

### <a name="report-types"></a>Berichtstypen

Sie können in CQD zwei Arten von Berichten auswählen, je nachdem, wie Sie Ihre Daten anzeigen möchten. Obwohl dieser Leitfaden nicht auf die Besonderheiten der Erstellung eines Berichtstyps über einen anderen eingeht, bieten die QER CQD-Vorlagen eine Mischung aus anpassbaren Diagramm- und Tabellenberichten, die Sie verwenden können:

-   Diagrammberichte erstellen grafische Balkendiagramme, die Daten in einem visuellen Format darstellen. Diagrammberichte eignen sich am besten zum Visualisieren von Daten über einen bestimmten Zeitraum.
-   Tabellenberichte sind hilfreich beim Anzeigen einzelner Messungen und Maße, wenn Sie die Berichte zur Bearbeitung in Microsoft Excel in CSV-Dateien exportieren.

### <a name="tenant-id"></a>Mandanten-ID

Einige CQD-Berichte erfordern einen Filter für Ihre Mandanten-ID. Aufgrund der Art und Weise, wie CQD Daten aggregiert, ist die verknüpfte Teilnehmer-Telemetrie enthalten. Dies kann sich beim Analysieren von Tendenzen als nützlich erweisen, aber Client- und Geräteberichte setzen voraus, dass Sie Daten nach einem bestimmten Mandanten filtern, um die verknüpfte Teilnehmer-Telemetrie auszuschließen. Wenn Sie Ihre Mandanten-ID nicht kennen, können Sie eine der folgenden Methoden verwenden, um diese zu finden.

> [!Note]
> Für diese Methoden sind die folgenden Berechtigungen erforderlich:<ul><li>Die Rolle „Globaler Administrator“</li><li>Die Rolle von Skype for Business-Administrator</li></ul>

#### <a name="azure-portal"></a>Azure-Portal

1.  Melden Sie sich im Microsoft Azure-Portal an: <https://portal.azure.com>

2.  Wählen Sie **Azure Active Directory** aus.

3.  Wählen Sie unter **Verwalten** **Eigenschaften** aus. Die Mandanten-ID wird im Feld **Verzeichnis-ID** angezeigt.

#### <a name="azure-powershell"></a>Azure PowerShell

1. [Installieren Sie das Microsoft Azure PowerShell Service Management-Modul](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2. Öffnen Sie ein Azure PowerShell-Befehlsfenster, führen Sie das folgende Skript aus, und geben Sie dabei Ihre Office 365-Anmeldeinformationen ein, wenn Sie dazu aufgefordert werden: 

   ```PowerShell
   Login-AzureRmAccount
   ```

3. Die Mandanten-ID wird in der Ausgabe aufgeführt.

#### <a name="skype-for-business-online-admin-center"></a>Skype for Business Online Admin Center

1.  Navigieren Sie in das Verzeichnis <https://portal.office.com>.

2.  Melden Sie sich mit dem Organisationskonto Ihres Mandantenadministrators an.

3.  Wählen Sie **Skype for Business** unter **Admin Centers** aus.

4.  Die Mandanten-ID wird auf der Willkommensseite als **Organisations-ID** aufgelistet.

#### <a name="skype-for-business-online-using-powershell"></a>Skype for Business Online unter Verwendung von PowerShell

1. [Richten Sie Ihr Computer für Windows PowerShell ein](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Führen Sie den folgenden Befehl aus:

   ```PowerShell
   (Get-cstenant).tenantid
   ```

3. Die Mandanten-ID wird als GUID angezeigt.

### <a name="teams-vs-skype-for-business"></a>Teams vs. Skype for Business

CQD kann sowohl über die Teams- als auch über die Skype for Business-Telemetrie berichten. Es kann jedoch vorkommen, dass Sie einen Bericht entwickeln möchten, um die Telemetrie von Teams getrennt von Skype for Business zu betrachten.

#### <a name="summary-reports"></a>Zusammenfassungsberichte

Wenn Sie die Seite Zusammenfassungsberichte so ändern möchten, dass nur Teams oder Skype for Business angezeigt wird, wählen Sie am oberen Rand des Bildschirms das Dropdownmenü **Produktfilter** aus, und wählen Sie dann das gewünschte Produkt aus.

![Screenshot des Dropdownmenüs mit den Filteroptionen](media/qerguide-image-productfilter.png)

_Abbildung 5 – Auswählen eines Produktfilters_

#### <a name="detailed-reports"></a>Detaillierte Berichte

Wenn Sie alle detaillierten Berichte filtern möchten, fügen Sie in der Browserleiste Folgendes am Ende der URL an:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Beispiel:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Weitere Informationen zu URL-Filtern finden Sie unter [Filtern von Berichten](#filtering-reports) weiter unten in diesem Abschnitt.

Wenn Sie einen einzelnen detaillierten Bericht filtern möchten, fügen Sie den Filter ``Is Teams`` zum Bericht hinzu und legen Sie ihn auf „True“ oder „False“ fest. Weitere Informationen finden Sie unter [Bearbeiten von Berichten](#editing-reports) weiter unten in diesem Abschnitt.

![Screenshot der Seite „Filter hinzufügen“](media/qerguide-image-addteamsfilter.png)

_Abbildung 6 – Hinzufügen eines Microsoft Teams-Filters zu einem Bericht_


### <a name="managed-vs-unmanaged-networks"></a>Verwaltete vs. nicht verwaltete Netzwerke

Standardmäßig werden alle Endpunkte in CQD als extern eingestuft. Sobald eine Gebäudedatei eingeführt wird, können wir mit der Suche nach verwalteten Endpunktdaten beginnen. Wie bereits erwähnt, sind Netzwerke in CQD wie folgt definiert:

-   Ein _verwaltetes Netzwerk_, das häufig als "internes" oder "inneres" bezeichnet wird, kann von der Organisation beeinflusst und gesteuert werden. Dies umfasst das interne LAN, das Remote-WAN und VPN.
-   Ein _nicht verwaltetes Netzwerk_, das häufig als "externes" oder "äußeres" bezeichnet wird, kann von der Organisation nicht beeinflusst oder gesteuert werden. Ein Beispiel für ein nicht verwaltetes Netzwerk ist ein Hotel- oder Flughafennetzwerk.

### <a name="dimensions-measures-and-filters"></a>Dimensionen, Messungen und Filter

Eine gut formulierte CQD-Abfrage enthält alle drei der folgenden Parameter: 

-   **Dimension:** Wie ich die Daten betrachten möchte.

-   **Messung:** Worüber möchte ich berichten.

-   **Filter:** Wie ich den von der Abfrage zurückgegebenen Datensatz reduzieren möchte.

Eine andere Möglichkeit, dies zu betrachten, ist, dass eine _Dimension_ die Gruppierungsfunktion bezeichnet, eine _Messung_ die Daten, an denen ich interessiert bin, und ein _Filter_ die Art und Weise, wie ich die Ergebnisse auf diejenigen eingrenzen möchte, die für meine Abfrage relevant sind.

Ein Beispiel für eine wohlgeformte Abfrage ist **Zeige schwache Ströme [Messung] nach Subnetz [Dimension] für Gebäude 6 [Filter] an**. Weitere Informationen finden Sie unter [Dimensionen und Messungen, die in CQD verfügbar sind](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>Erster vs. zweiter 

Viele Dimensionen und Kennzahlen im CQD werden als erster oder zweiter Endpunkt bezeichnet. CQD verwendet keine Felder für Anrufer/Angerufene. Diese wurden umbenannt in _Erster_ und _Zweiter_, weil zwischen dem Anrufer und dem Angerufenen Zwischenschritte vorhanden sind. Die folgende Logik legt fest, welcher beteiligte Endpunkt als erster bezeichnet wird:

-   Der **erste** wird immer ein Serverendpunkt (Konferenzserver, Vermittlungsserver usw.) sein, wenn ein Server in den Strom oder Anruf einbezogen wird.

-   Der **zweite** ist immer ein Client-Endpunkt, es sei denn, der Datenstrom verläuft zwischen zwei Server-Endpunkten.

-   Wenn beide Endpunkte vom selben Typ sind, richtet sich die Auswahl des ersten Endpunkts nach der internen Anordnung der Benutzer-Agenten-Kategorie. Dadurch wird sichergestellt, dass die Reihenfolge konsistent ist.

Weitere Informationen dazu, wie der erste oder zweite Endpunkt ermittelt wird, wenn beide identisch sind, finden Sie unter [Dimensionen und Messungen, die in CQD verfügbar sind](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Datenstrom vs. Anruf

Sie müssen den Unterschied zwischen einem Anruf und einem Datenstrom kennen, um ordnungsgemäß die Dimensionen oder Messungen auswählen zu können, die Sie in CQD sehen werden. Der Hauptfokus von CQD liegt auf Datenströme, aber auch anrufbasierte Messungen stehen zur Verfügung.

-   **Datenstrom:** Ein _Datenstrom_ ist nur zwischen zwei Endpunkten vorhanden. Es gibt nur einen Datenstrom für jede Richtung und für die Kommunikation sind zwei Datenströme erforderlich. Datenströme sind hilfreich, um Gebäude, Netzwerke oder Subnetze zu untersuchen. In einigen Fällen werden sowohl Anrufe als auch Datenströme im Namen der Messung verwendet (z. b. "Datenstrom zur Anruferstellung" oder "Datenstrom eines abgebrochenen Anrufs"). Diese werden weiterhin als Datenströme eingestuft.

-   **Anruf:** Ein _Anruf_ ist eine Gruppierung aller Datenströme aller Teilnehmer. Ein Anruf besteht aus mindestens zwei Ströme. Ein einzelner Anruf hat mindestens zwei Endpunkte mit jeweils mindestens einem Datenstrom.

Weitere Hinweise dazu, ob sich die Dimension oder Messung auf einen Anruf oder einen Datenstrom bezieht, finden Sie unter [Dimensionen und Messungen, die in CQD verfügbar sind](https://aka.ms/cqd-dm). 

### <a name="good-poor-and-unclassified-calls"></a>Gute, schlechte und nicht klassifizierte Anrufe

Ein Anruf wird entweder als "gut", "schlecht" oder "nicht klassifiziert" kategorisiert. Doch lassen Sie uns jeden einzelnen Punkt näher besprechen.

-   **Gut oder schlecht:** Ein guter oder schlechter Anruf besteht aus einem Anruf, der eine vollständige Gruppe von Dienstmetriken enthält, für die ein vollständiger QoE-Bericht generiert und vom Dienst empfangen wurde. Wie man feststellt, ob ein Datenstrom gut oder schlecht ist, wird [weiter oben in diesem Leitfaden beschrieben](#poor-stream-rate).

-   **Nicht klassifiziert:** Ein nicht klassifizierter Datenstrom enthält keine vollständige Gruppe von Dienstmetriken. Hierbei kann es sich um kurze Anrufe handeln – in der Regel weniger als 60 Sekunden, – wobei Durchschnittswerte nicht berechnet und kein QoE-Bericht generiert wurde. Der häufigste Grund für Anrufe, die nicht klassifiziert werden, besteht darin, dass die Paketnutzung nur geringfügig oder gar nicht funktioniert. Ein Beispiel hierfür wäre ein Teilnehmer, der sich an einer Besprechung stummgeschaltet anschließt und niemals spricht. Der Teilnehmer empfängt, sendet jedoch keine Medien. Wenn Medien nicht übertragen werden, gibt es für CQD keine Metriken, die Sie verwenden können, um den ausgehenden Medienstrom des Endpunkts zu klassifizieren.

Weitere Informationen zum Stromklassifizierungsprozess finden Sie in [diesem Artikel](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Häufig verwendete Subnetze

Häufig verwendete Subnetze sind bestimmte private Subnetze, die von Hotels, Heimnetzwerken, Hotspots und ähnlichen Bereichen verwendet werden. Diese Subnetze können aufgrund ihrer weit reichenden Nutzung nur schwer verfolgt werden. Wenn in Ihrer Organisation eines dieser häufig verwendeten Subnetze verwendet wird, empfehlen wir, dass Sie dieses Netzwerk in ein anderes Subnetz verschieben. Dies erleichtert die Berichterstellung in CQD. Wenn angegeben, wurden Berichte in der Vorlage "Alle Netzwerke" so konfiguriert, dass Sie diese Subnetze ausschließen, um sie als Quelle schlechter Qualität zu eliminieren. Nachstehend sind häufig verwendete Subnetze definiert. Ihre Auswirkung variiert je nach Organisation.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Bei der Untersuchung eines verwalteten Netzwerks, das ein häufig verwendetes Subnetz verwendet, müssen Sie die zweite reflexive lokale IP-Dimension zum Gruppieren von Subnetzen verwenden. Diese Dimension enthält die öffentliche IP-Adresse des Endpunkts.

## <a name="cqd-online"></a>CQD Online

In diesem Abschnitt werden die Grundlagen des Zugriffs auf CQD beschrieben. Hier finden Sie Anleitungen für die folgenden Themen:

-   Zugreifen auf CQD Online
-   Erste Schritte mit CQD
-   Bearbeiten von Berichten in CQD
-   Filtern von Berichten in CQD
-   Importieren von Berichten in CQD

Ausführlichere Schulungen und Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="access-cqd-online"></a>Zugreifen auf CQD Online

Sie können auf eine von drei Arten auf CQD zugreifen:

-   Wechseln Sie zu <https://cqd.teams.microsoft.com>.

-   Wechseln Sie zu **Microsoft Teams Admin Center** und wählen Sie den Link zu CQD aus, wie in der folgenden Abbildung gezeigt.

![Screenshot des ausgewählten Dashboards für die Anrufqualität.](media/qerguide-image-mopo.png "Im linken Navigationsbereich ist der Link zum Dashboard für die Anrufqualität ausgewählt.")

_Abbildung 7 – Zugreifen auf CQD über das Microsoft Teams Admin Center_

-   Wechseln Sie zum alten **Skype for Busines Admin Center** > **Tools** und wählen Sie den Link zu CQD aus, wie in der folgenden Abbildung gezeigt.

![Screenshot von CQD, der im Hauptbereich ausgewählt ist.](media/qerguide-image-legacyui.png "Im linken Navigationsbereich ist "Tools" ausgewählt und der Link zu CQD ist im Hauptbereich ausgewählt.")

_Abbildung 8 – Zugreifen auf CQD über das Skype for Business Admin Center_


### <a name="getting-started"></a>Erste Schritte

Wenn Sie zum ersten Mal zu CQD navigieren, wird die Seite Zusammenfassungsberichte angezeigt. Die meisten der in diesem Leitfaden beschriebenen Berichte sind benutzerdefinierte Detailberichte. Um die detaillierten Berichte zu verwenden, wählen Sie oben auf der Seite **Zusammenfassungsberichte** aus und wählen Sie dann **Detaillierte Berichte** aus.

![Screenshot der Typen von Berichten, die in CQD verfügbar sind](media/qerguide-image-choosereports.png)

_Abbildung 9 – Navigieren zu „Detaillierte Berichte“_

Die Seite „Detaillierte Berichte“ in CQD sieht wie in der folgenden Abbildung aus.

![Screenshot, der die Elemente darstellt, die einen detaillierten Bericht bilden](media/qerguide-image-detailedreportspage.png)

|             |           |
| ------------|-----------|
| ![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout1.png "eins") | Im Zusammenfassungsbereich wird der Kontext für den auf der rechten Seite angezeigten Berichtssatz angezeigt. |
| ![Symbol der Zahl 2, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout2.png "zwei") | Sie können im Bereich "Zusammenfassung" **Bearbeitung** auswählen, um Eigenschaften auf Berichtsebene (einschließlich Höhe der y-Achse) festzulegen und neue Vorlagen zu importieren. |
| ![Symbol der Zahl 3, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout3.png "drei") | Die Breadcrumb-Navigation hilft Benutzern, ihren aktuellen Standort in der Berichtssatzhierarchie zu identifizieren.  |
| ![Symbol der Zahl 4, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout4.png "vier") | Berichte mit untergeordneten Berichten werden mit einem blauen Link angezeigt. Wenn Sie diesen Link auswählen, können Sie einen Drilldown zu den untergeordneten Berichten ausführen. |

_Abbildung 10 – Seite "Detaillierte Berichte"_

Zeigen Sie auf Balkendiagramme und Trendlinien im Bericht, um detaillierte Werte anzuzeigen. Der Bericht, der einen Fokus besitzt, zeigt das Aktionsmenü an: **Bearbeitung**, **Klonen**, **Löschen**, **Herunterladen** und **Exportieren**.

### <a name="editing-reports"></a>Bearbeiten von Berichten

Wenn Sie in einem Bericht im Aktionsmenü auf **Bearbeiten** klicken, wird der Abfrage-Editor geöffnet. Jeder Bericht basiert auf einer Abfrage nach CQD. Ein Bericht ist eine Visualisierung der Daten, die von der Abfrage zurückgegeben werden. Der Abfrage-Editor ist eine Benutzeroberfläche zum Bearbeiten dieser Abfragen zusätzlich zu den Anzeigeoptionen für den Bericht, wie in der folgenden Abbildung dargestellt.

![Screenshot, der die Elemente darstellt, die einen zu bearbeitenden Bericht bilden.](media/qerguide-image-queryeditor.png)

|             |           |
| ------------|-----------|
| ![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout1.png "eins") | Sie wählen Dimensionen, Messungen und Filter aus dem linken Bereich aus. Beim zeigen auf einen vorhandenen Wert wird eine Schaltfläche "Schließen" (**X**) angezeigt, die Sie auswählen können, um den Wert zu entfernen.<ul><li>Wenn Sie die Dimension oder die Messung auswählen, können Sie den Titel ändern, indem Sie das Feld **Titel** bearbeiten. Sie können die Reihenfolge auch ändern, indem Sie im oberen Bereich die blauen Pfeile nach oben oder nach unten auswählen.</li><li>Wenn Sie (**+**) neben einer Überschrift auswählen, wird das Dialogfeld zum Hinzufügen einer neuen Dimension, einer Messung oder eines Filters geöffnet.</li><li>Geben Sie die ersten Buchstaben der Dimension, Messung oder des Filters in das **Suchen von**-Feldes ein, um die Liste zur einfacheren Suche zu filtern.</li></ul> |
| ![Symbol der Zahl 2, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout2.png "zwei") | Im oberen Bereich werden Optionen für die Diagrammanpassung angezeigt. |
| ![Symbol der Zahl 3, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout3.png "drei") | Im Abfrage-Editor wird eine Vorschau des Berichts angezeigt. |
| ![Symbol der Zahl 4, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout4.png "vier") | Verwenden Sie das Feld **Bearbeiten** am unteren Rand des Bildschirms, um eine detaillierte Beschreibung des Berichts zu erstellen oder zu bearbeiten. |

_Abbildung 11 – Abfrage-Editor_

### <a name="filtering-reports"></a>Filtern von Berichten

Die bereitgestellten Vorlagen umfassen mehrere integrierte Abfragen und Berichtsfilter. In den folgenden Abschnitten werden die am häufigsten verwendeten Filter in den Vorlagen beschrieben.

#### <a name="url-filter"></a>URL-Filter

Sie können einen URL-Filter verwenden, um jeden Bericht für eine bestimmte Dimension zu filtern. Die am häufigsten verwendeten URL-Filter werden zum Filtern von Berichten verwendet, um die Telemetrie des Teilnehmers auszuschließen oder sich auf Teams oder Skype for Business Online zu konzentrieren. Wenn Sie Filter verwenden, empfiehlt es sich, diese mit einem Lesezeichen zu versehen. 

Das Ausschließen von Verbunddaten aus CQD-Berichten ist hilfreich, wenn Sie verwaltete Gebäude oder Netzwerke beheben, in denen Verbundendpunkte ihre Berichte beeinflussen können.

Wenn Sie einen URL-Filter einsetzen möchten, fügen Sie in der Adressleiste des Browsers Folgendes am Ende der URL an:

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Wenn Sie die Berichte für Teams oder Skype for Business filtern möchten, fügen Sie am Ende der URL Folgendes ein:

```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

Beispiel:

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Is Teams]|[TRUE]```


> [!NOTE]
> Die oben aufgeführten URL-Beispiele dienen nur der visuellen Darstellung. Verwenden Sie den standardmäßigen CQD-Link <https://cqd.teams.microsoft.com>.


#### <a name="query-filters"></a>Abfragefilter

Abfragefilter werden mithilfe des Abfrage-Editors in CQD implementiert. Diese Filter werden verwendet, um die Anzahl der von CQD zurückgegebenen Datensätze zu verringern, wodurch die Gesamtgröße und die Abfragezeiten des Berichts minimiert werden. Dies ist besonders hilfreich, wenn nicht verwaltete Netzwerke ausgefiltert werden sollen. Die in der folgenden Tabelle aufgelisteten Filter verwenden reguläre Ausdrücke (RegEx).

_Tabelle 3 – Abfragefilter_

| Filter         | Beschreibung          | Beispiel für CQD-Abfragefilter      |
|----------------|----------------------|-------------------------------|
| Keine leeren Werte   | Einige Filter verfügen nicht über die Option zum Filtern nach leeren Werten. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und legen Sie den Filter abhängig von Ihren Anforderungen auf "Equals" oder "Not Equals" fest.      | Zweiter Gebäudename \<\> \^\\s\*\$                       |
| Häufig verwendete Subnetze ausschließen | Ohne eine gültige Gebäudedatei, um verwaltete von nicht verwalteten Netzwerken zu trennen, werden Heimnetzwerke in die Berichte aufgenommen. Diese Heimsubnetze sind außerhalb des Umfangs der Steuerung und können schnell aus einem Bericht ausgeschlossen werden. Häufig verwendete Subnetze laut der Definition in diesem Leitfaden sind 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweites Subnetz \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Nur innere anzeigen  | Wird verwendet, um einen Bericht für verwaltete (interne) oder nicht verwaltete (externe) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.       | Zweiter innerhalb des Unternehmens = Intern        |

#### <a name="report-filters"></a>Berichtsfilter

Berichtsfilter werden implementiert, indem dem eingereichten Bericht ein Filter entweder im Abfrage-Editor oder direkt im Bericht hinzugefügt wird. Die folgenden Berichtsfilter werden in der gesamten Vorlage verwendet.

_Tabelle 4 – Berichtsfilter_

| Filter     | Beschreibung                            | Beispiel für CQD-Berichtsfilter         |
|------------|----------------------------------------|-----------------------------------|
| Monat      | Beginnen Sie zuerst mit dem Jahr und dann mit dem Monat. | 2017-10                           |
| Alphabetisch | Filtert nach alphabetischen Zeichen. | [a-z]                             |
| Numerisch    | Filtert nach allen numerischen Zeichen.    | [0-9]                             |
| Prozent | Filtert nach einem Prozentsatz.              | ([3-9]\\.)\|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importieren der CQD-Vorlagen

Dieser Leitfaden enthält [zwei zusammengestellte CQD-Vorlagen](https://aka.ms/qertemplates). Diese Vorlagen beschleunigen Ihre Nutzung von CQD und bieten Ihnen die Möglichkeit, die Funktionalitäten von CQD rasch einzusetzen, um einen Einfluss auf die Erfahrung Ihrer Nutzer bei Teams oder Skype for Business zu haben. Die Vorlage "Alle Netzwerke", die für die Arbeit mit einer Gebäudedatendatei optimiert ist, kann verwendet werden, während Sie auf die Erfassung und das Hochladen von Gebäudeinformationen in CQD hinarbeiten, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (.CQDX) in CQD Online**

1. Wechseln Sie zu <https://cqd.teams.microsoft.com>.

2. Authentifizieren Sie sich mit Ihren Admin-Anmeldeinformationen für Office 365.

   > [!NOTE]
   > Sie müssen über die Rolle "Globaler Office 365-Administratorr", "Skype for Business-Administrator" oder "Berichtleseberechtigter" für den Zugriff auf CQD verfügen. 

3. Wählen Sie oben auf der Seite das Menü **Zusammenfassungsberichte** aus und wählen Sie dann **Detaillierte Berichte** aus.

4. Wählen Sie im Zusammenfassungsbereich **Importieren** aus. Wechseln Sie zum CQDX-Speicherort, wählen Sie die CQDX-Vorlage aus und wählen Sie dann **Öffnen**aus.

5. Nachdem die Vorlage hochgeladen wurde, wird in einem Popupfenster die Meldung "Der Berichte wurde erfolgreich importiert" angezeigt. Wählen Sie **OK** aus.

   ![Screenshot der Benachrichtigung über den erfolgreichen Import](media/qerguide-image-importmessage.png "Benachrichtigung, dass die Vorlage erfolgreich importiert wurde")

6. Wiederholen Sie die Schritte 4 und 5 für die zweite CQD-Vorlage.

> [!NOTE]
> Die CQD-Vorlagen werden pro Benutzer importiert. Wenn der Bericht von weiteren Benutzern verwendet werden soll, müssen sie sich anmelden und die Vorlagen in Ihre CQD-Instanz importieren. 


## <a name="building-mapping"></a>Gebäudezuordnung

In einer Teams- oder Skype for Business Online-Bereitstellung sind alle Clients extern. Dies hat zur Folge, dass in CQD Online standardmäßig alle Clients als "extern" gemeldet werden, unabhängig davon, ob der Client über ein internes Unternehmensnetzwerk verbunden war.

Wenn Sie mit CQD arbeiten, müssen Sie den Standort eines Endpunkts kennen und wissen, ob er mit einem Netzwerk verbunden ist, das Sie verwalten können, oder mit einem Netzwerk, das Sie nicht verwalten können – die Annahme ist, dass Sie nur die Netzwerke verbessern können, die Sie verwalten können. Durch Hochladen von Subnetz- und Gebäudeinformationen in CQD Online kann CQD festlegen, ob der Endpunkt mit einem internen Unternehmens-/ verwalteten Netzwerk oder einem externen/ nicht verwalteten Netzwerk verbunden.

### <a name="building-data-file-structure"></a>Struktur der Gebäudedatendatei

Das Format der Datei, die Sie hochladen, muss folgende Bedingungen erfüllen, um die Validierungsprüfung vor dem Hochladen zu bestehen.

-   Die Datei muss entweder eine TSV-Datei sein – was bedeutet, dass für jede Zeile jede Spalte durch ein Tabstoppzeichen getrennt ist – oder eine CSV-Datei, in der jede Spalte durch ein Komma getrennt ist.

-   Die Datei darf nicht größer als 50 MB sein.

-   Der Inhalt der Datendatei *darf keine Tabellenüberschriften umfassen*. In anderen Worten muss die erste Zeile der Datendatei aus echten Daten bestehen und nicht aus Spaltenüberschriften wie "Netzwerk".

-   Für jede Spalte kann der Datentyp "Zeichenfolge", "Zahl" oder "boolesch" lauten. Falls der Datentyp eine Zahl ist, muss es sich um einen numerischen Wert handeln; falls es der boolesche Datentyp ist, muss der Wert entweder 0 oder 1 betragen.

-   In jeder Spalte können die Daten leer sein, falls der Datentyp „Zeichenfolge" verwendet wird (jedoch müssen sie durch ein passendes Trennzeichen wie zum Beispiel ein Tabstoppzeichen oder ein Komma getrennt werden). Dadurch wird diesem Feld nur ein leerer Zeichenfolgenwert zugewiesen.

-   Jede Zeile muss 14 Spalten aufweisen. Jede Spalte muss den in der folgenden Tabelle beschriebenen Datentyp aufweisen und die Spalten müssen in der in der Tabelle aufgeführten Reihenfolge stehen.

_Tabelle 5 – Struktur der Gebäudedatei_

| Spaltenname        | Datentyp | Beispiel                   | Anleitung    |
|--------------------|-----------|---------------------------|-------------|
| Netzwerk            | Zeichenfolge    | 192.168.1.0               | Erforderlich    |
| NetworkName        | Zeichenfolge    | USA/Seattle/SEATTLE-SEA-1 | Erforderlich\*  |
| NetworkRange       | Zahl    | 26                        | Erforderlich    |
| BuildingName       | Zeichenfolge    | SEATTLE-SEA-1             | Erforderlich\*  |
| OwnershipType      | String    | Contoso                   | Optional    |
| BuildingType       | Zeichenfolge    | IT Termination            | Optional    |
| BuildingOfficeType | Zeichenfolge    | Engineering (Technik)               | Optional    |
| Stadt/Ort               | Zeichenfolge    | Seattle                   | Empfohlen |
| ZipCode            | Zeichenfolge    | 98001                     | Empfohlen |
| Land            | Zeichenfolge    | US                        | Empfohlen |
| Status              | Zeichenfolge    | WA                        | Empfohlen |
| Region             | String    | MSUS                      | Empfohlen |
| InsideCorp         | Boolescher Wert      | 1                         | Erforderlich    |
| ExpressRoute       | Boolescher Wert      | 0                         | Erforderlich    |
| VPN                | Boolescher Wert      | 0                         | Optional    |

\*Obwohl es von CQD nicht gefordert wird, sind die Vorlagen für die Anzeige von Gebäude- und Netzwerknamen konfiguriert.

#### <a name="supernetting"></a>Supernetting

Sie können Supernetting verwenden, das gewöhnlich als "Klassenloses domänenübergreifendes Routing (Classless Inter-Domain Routing, CIDR)" bezeichnet wird, anstatt jedes Subnetz zu definieren. Bei einem *Supernet* handelt es sich um eine Kombination aus mehreren Subnetzen, die ein einzelnes Routingpräfix aufweisen. Statt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die Supernetting-Adresse verwenden. Supernetting wird unterstützt, aber es wird nicht empfohlen, es zu verwenden.

Beispielsweise besteht das Marketinggebäude von Contoso aus den darunter liegenden Subnetzen:

-   10.1.0.0/24—1. OG
-   10.1.1.0/24—2. OG
-   10.1.2.0/24—3. OG
-   10.1.3.0/24—4. OG

Statt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die Supernetting-Adresse verwenden. In diesem Beispiel 10.1.0.0/22.

-   Netzwerk = 10.1.0.0
-   Netzwerkbereich = 22

Hier einige Punkte, die Sie berücksichtigen sollten, bevor Sie Supernetting implementieren:

-   Supernetting kann nur in einer Subnetz-Zuordnung mit einer 8-Bit-zu-28-Bit-Maske verwendet werden.

-   Supernetting nimmt im Vorfeld weniger Zeit in Anspruch, aber es geht darum, die Reichhaltigkeit ihrer Daten zu verringern. Nehmen wir einmal an, dass es ein Qualitätsproblem mit Subnetz 200.1.2.0 gibt. Wenn Sie Supernetting implementiert haben, können Sie nicht wissen, wo sich das Subnetz befindet oder welchen Typ von Netzwerk es hat (z. B. ein Labor). Wenn Sie alle Subnetze für ein Gebäude definiert und Informationen zur Geschosslage hochgeladen hätten, könnten Sie diese Unterscheidung sehen.

-   Es ist wichtig, dass Sie sicherstellen, dass die Supernetting-Adresse korrekt ist und keine unerwünschte Subnetze fängt.

-   Es ist üblich, 192.168.0.0 in den Daten zu finden. Für viele Organisationen gibt dies an, dass der Benutzer zu Hause ist. Bei anderen handelt es sich um das IP-Adressschema für ein Satellitenbüro. Wenn Ihre Organisation über Büros verfügt, in denen diese Konfiguration verwendet wird, sollten Sie sie nicht in ihre Gebäudedatei einschließen, da es schwierig ist, Unterschiede zwischen privaten und internen Netzwerken zu finden, indem Sie häufig verwendete Subnetze verwenden. Informationen hierzu finden Sie im Abschnitt zu [Häufig verwendete Subnetzen](#common-subnets) weiter oben in diesem Leitfaden.

> [!IMPORTANT]
> Der Netzwerkbereich kann verwendet werden, um ein Supernet darzustellen. Alle neuen Uploads von Gebäudedatendateien werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien könnten zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen.

#### <a name="vpn"></a>VPN

Die QoE-Daten (Erlebnisqualität), die von Clients an Office 365 gesendet werden, d. h., aus dem CQD-Daten stammen, umfassen eine VPN-Kennzeichnung. CQD sieht dies als die erste und die zweite VPN-Dimension. Dieses Kennzeichen hängt jedoch davon ab, dass die VPN-Anbieter Windows mitteilen, dass der registrierte VPN-Netzwerkadapter ein Fernzugriffsadapter ist. Nicht alle VPN-Anbieter registrieren die Fernzugriffsadapter ordnungsgemäß. Aus diesem Grund sind Sie möglicherweise nicht in der Lage, die integrierten VPN-Abfragefilter zu verwenden. Es gibt zwei Vorgehensweisen für die Aufnahme von VPN-Subnetzen in die Gebäudeinformationsdatei:

- Definieren Sie einen **Netzwerknamen**, indem Sie den Text "VPN" in diesem Feld für VPN-Subnetze verwenden.

  ![Screenshot des QCD-Berichts mit VPN-Netzwerknamen](media/qerguide-image-vpnnetworkname.png)

  _Abbildung 12 – VPN mit Netzwerknamen_

- Definieren Sie einen **Gebäudenamen**, indem Sie den Text "VPN" in diesem Feld für VPN-Subnetze verwenden.

  ![Screenshot des QCD-Berichts mit VPN-Gebäudenamen](media/qerguide-image-vpnbuildingname.png)

  _Abbildung 13 – VPN mit Gebäudenamen_

> [!IMPORTANT]
> Bestimmte VPN-Implementierungen melden die Subnetzinformationen nicht präzise. Dies liegt daran, dass der VPN-Client mit einem 32-Bit-Subnetz bereitgestellt wird.  Wie im vorherigen Abschnitt erwähnt, kann CQD ein 32-Bit-Subnetz nicht ordnungsgemäß identifizieren.  Um ein VPN-Subnetz in CQD genau zu identifizieren, legen Sie das VPN-Feld in der Gebäude Datei auf 1 fest.


> [!NOTE]
> Bei VPN-Verbindungen ist bekannt, dass die Netzwerkverbindung als verdrahtet gekennzeichnet ist, wenn die zugrundeliegende Internetverbindung drahtlos ist. Wenn Sie Qualität über VPN-Verbindungen untersuchen, können Sie nicht davon ausgehen, dass der Verbindungstyp genau erkannt wurde.

### <a name="uploading-building-information"></a>Hochladen von Gebäudeinformationen

Das Dashboard "CQD-Zusammenfassungsberichte" enthält eine Seite zum **Mandantendaten hochladen**, auf die Sie zugreifen können, indem Sie in der oberen rechten Ecke das verknüpfende Tag **Mandantendaten hochladen** auswählen (suchen Sie nach dem Zahnradsymbol). Diese Seite wird für Administratoren zum Hochladen Ihrer eigenen Informationen verwendet, z. B. zur Zuordnung der IP-Adresse und von geographischen Informationen, zum Zuordnen jedes Funkzugriffspunkts und dessen MAC-Adresse usw.

1. Wechseln Sie zu CQD Online, indem Sie zu <https://cqd.teams.microsoft.com> navigieren.

2. Wählen Sie das Zahnradsymbol in der oberen rechten Ecke aus und wählen Sie auf der Seite **Zusammenfassungsberichte** die Option **Mandantendaten hochladen** aus.

   ![Screenshot des Dialogfelds, das angezeigt wird, während Daten hochgeladen werden](media/qerguide-image-tenantdataupload.png)

   _Abbildung 14 – Menü zum Hochladen von Mandantendaten_

3. Wenn Sie CQD zum ersten Mal besuchen, werden Sie aufgefordert, die Gebäudedaten hochzuladen. Sie können **Jetzt Hochladen** auswählen, um schnell zur Seite **Mandantendaten hochladen** zu navigieren.

   ![Screenshot eines Banners, das einen Benutzer zum Hochladen von Gebäudedaten auffordert](media/qerguide-image-buildingdatauploadbanner.png)

   _Abbildung 15 – Banner zum Hochladen von Gebäudedaten_

4. Wählen Sie auf der Seite **Mandantendaten hochladen** **Durchsuchen** aus, um eine Datendatei auszuwählen.

5. Geben Sie nach Auswahl einer Datendatei das **Startdatum** und optional ein Enddatum ein.

6. Wählen Sie nach der Auswahl von **Startdatum** die Option **Hochladen** aus, um die Datei in CQD hochzuladen. <br><br>Bevor die Datei hochgeladen wird, wird sie validiert. Wenn die Validierung fehlschlägt, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, die Datei zu korrigieren. Die folgende Abbildung zeigt einen Fehler, der auftritt, wenn die Anzahl der Spalten in der Datendatei falsch ist.

   ![Beispiel für ein Dialogfeld mit einem Fehler beim Hochladen der Gebäudedaten](media/qerguide-image-buildingdatauploaderror.png)
 
   _Abbildung 16 – Fehler beim Hochladen von Gebäudedaten_

7. Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.

> [!NOTE]
> Es kann bis zu vier Stunden dauern, bis die Bearbeitung der Datei abgeschlossen ist.<br><br> Wenn Sie bereits eine Gebäudedatei hochgeladen haben und Subnetze hinzufügen müssen, die möglicherweise ausgelassen oder ausgeschlossen wurden, ändern Sie die ursprüngliche Datei, indem Sie die neuen Subnetze hinzufügen, die aktuelle Datei entfernen und die neu bearbeitete Datei erneut hochladen. In CQD kann nur eine einzige aktive Gebäudedatendatei vorhanden sein. 


### <a name="updating-a-building-file"></a>Aktualisieren einer Gebäudedatei

Beim Sammeln von Gebäude- und Subnetzinformationen laden Administratoren die Gebäudedatei oft in mehreren Versionen im Laufe der Zeit hoch und fügen neue Subnetze und ihre Gebäudeinformationen hinzu, sobald diese verfügbar sind. Wenn dies geschieht, müssen Sie Ihre Gebäudedatei erneut hochladen. Dieser Vorgang ähnelt dem anfänglichen Upload gemäß der Beschreibung im vorherigen Abschnitt, mit ein paar Ausnahmen, wie im folgenden Abschnitt beschrieben.

> [!Important]
> Es kann jeweils nur eine Gebäudedatei aktiv sein. Mehrere Gebäudedateien dürfen nicht gesammelt werden.

#### <a name="adding-net-new-subnets"></a>Hinzufügen von neuen Nettosubnetzen

Es gibt Zeiten, in denen Sie neue Nettosubnetze zu CQD hinzufügen müssen, die ursprünglich nicht Teil Ihrer Netzwerktopologie waren. Wenn Sie neue Nettosubnetze hinzufügen möchten, führen Sie im CQD-Mandantendatenportal folgende Schritte aus:

1.  Bearbeiten Sie die ursprüngliche Erstellungsdatei, und geben Sie ein Enddatum ein, das mindestens einen Tag vor dem Erwerb der neuen Nettosubnetze stattfindet.
2.  Laden Sie die ursprüngliche Datei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.
3.  Fügen Sie die neuen Nettosubnetze der ursprünglichen Gebäudedatei hinzu.
4.  Laden Sie die frisch geänderte Gebäudedatei nach demselben Verfahren wie oben und geben Sie ein Startdatum, das ein Tag nach dem Ende der vorherigen Gebäudedatei liegt.

#### <a name="updating-the-current-building-file"></a>Aktualisieren der aktuellen Gebäudedatei

Wenn eine Gebäudedatei bereits hochgeladen wurde, Sie aber fehlende Subnetze hinzufügen müssen, führen Sie im CQD-Mandantendatenportal folgende Schritte aus:

1.  Laden Sie die ursprüngliche Datei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.
2.  Entfernen Sie die aktuelle Datei in CQD.
3.  Fügen Sie die neuen Subnetze der ursprünglichen Datei hinzu.
4.  Laden Sie die Gebäudedatei hoch. Stellen Sie sicher, dass das Startdatum mindestens acht Monate zurückliegt, damit das CQD historische Daten verarbeiten kann.

### <a name="missing-subnets"></a>Fehlende Subnetze

Nachdem Sie die Gebäudeinformationen für verwaltete Netzwerke hochgeladen haben, sollte jedes verwaltete Netzwerk über eine Gebäudezuordnung verfügen. Dies ist allerdings nicht immer der Fall. In der Regel werden einige Subnetze ausgelassen. In diesem Abschnitt wird erläutert, wie diese fehlenden Netzwerke validiert werden.

Navigieren Sie in CQD online zur Seite **Detaillierte Berichte** und navigieren Sie zum **Bericht über die fehlenden Subnetze**, der in den CQD-Vorlagen enthalten ist. Dadurch werden alle Subnetze mit mindestens 10 Audiodatenströme vorgestellt, die in der Gebäudedatendatei nicht definiert sind und als "extern" gekennzeichnet sind. Stellen Sie sicher, dass in dieser Liste keine verwalteten Netzwerke vorhanden sind. Wenn keine Subnetze vorhanden sind, aktualisieren Sie die ursprüngliche Datendatei, und laden Sie sie erneut ins CQD.

> [!IMPORTANT]
> Sie müssen Ihre Mandanten-ID diesem Bericht als Abfragefilter für **Zweiten Mandanten-ID** hinzufügen, um den Bericht so zu filtern, dass nur die Mandantendaten Ihrer Organisation angezeigt werden. Andernfalls zeigt der Bericht Partnersubnetze an.

> [!NOTE] 
> Stellen Sie sicher, dass Sie den Berichtsfilter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie den Berichtsfilter **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.

![Screenshot des Berichts über die fehlenden Subnetze](media/qerguide-image-missingbuildingreport.png)

_Abbildung 17 – Bericht über fehlende Gebäude_

### <a name="building-mapping-tools"></a>Tools für die Gebäudezuordnung

Seien wir mal ehrlich, das Zuordnen von Subnetzen in Ihrer Organisation kann schwierig sein. Große globale Netzwerke sind sehr komplex, mit verschiedenen Teams, die ihre jeweiligen Regionen verwalten, und für die Netzwerktopologie gibt es möglicherweise keine einzige Wahrheit. Es stehen zwei Tools zur Verfügung, das Ihnen beim Start des in den folgenden Abschnitten beschriebenen Verfahrens der Gebäudezuordnung helfen kann.

#### <a name="cqd-tools"></a>CQD-Tools

Diese Tools basieren auf PowerShell und können Active Directory-Websites und -Dienste sowie Microsoft-DHCP-Dienste nutzen, um die Datei vorab auszufüllen.  Diese Tools können Ihnen bei den folgenden Aufgaben helfen:

1.  AD-Websites und -Dienste abfragen und basierend auf den darin enthaltenen Informationen eine Gebäudedatei erstellen.
2.  Abfragen eines Microsoft DHCP-Servers oder mehrerer Server ab, um Subnetzinformationen abzurufen, und automatisches Erstellen einer Gebäudedatei.
3.  Validieren einer vorhandenen Gebäudedatei, Durchsuchen nach Duplikaten und Überlappungen.
4.  Suchen nach nicht zugeordneten Subnetzen in CQD.

Weitere Informationen zu diesem Tool finden Sie in [diesem Blogbeitrag](https://aka.ms/cqdtools).

#### <a name="network-planner"></a>Netzwerkplaner

Der Netzwerkplaner ermittelt und organisiert mit wenigen einfachen Schritten die Netzwerkanforderungen für Ihre Cloud Voice-Bereitstellung. Wenn Sie die Details zum Netzwerk Ihrer Organisation und zur Nutzung von Cloud-VoIP bereitstellen, können Sie eine ungefähre Berechnung der Netzwerkanforderungen für Ihre Cloud-VoIP-Bereitstellung erhalten und diese Details zur Berichterstellung verwalten und exportieren und Bereiche betrachten, die Sie näher untersuchen möchten. Außerdem erhalten Sie Informationen zu den nächsten Schritten.

Obwohl der Netzwerkplaner den Prozess der Gebäudezuordnung nicht vollständig automatisiert, können die Netzwerkinformationen nach der Eingabe in den Netzwerkplaner in eine Gebäudedatei exportiert werden, die zum Hochladen bereit ist.

## <a name="reliability-investigations"></a>Zuverlässigkeitsuntersuchungen

Der erste Schritt zur Verbesserung der Qualität ist die Einschätzung des Status der Zuverlässigkeit innerhalb der gesamten Organisation. Da Zuverlässigkeit für eine positive Benutzererfahrung von entscheidender Bedeutung ist, beginnen wir mit den beiden Komponenten zur Messung der Zuverlässigkeit:

1.  **Aufbaufehler:** Ein ausgehender Anruf konnte nicht hergestellt werden.

2.  **Abbruchfehler:** Ein ausgehender Anruf wurde hergestellt und unerwartet beendet.

In diesem Abschnitt befassen wir uns mit Methoden zur Untersuchung beider Bereiche.

> [!NOTE]
> In diesem Leitfaden werden nicht alle in den Vorlagen enthaltenen Berichte behandelt.  Die nachstehend erläuterten Methoden für Untersuchungen gelten jedoch weiterhin. Weitere Informationen finden Sie in der Beschreibung des jeweiligen Berichts.


### <a name="setup-failures"></a>Aufbaufehler

Priorisieren Sie zunächst die Behebung von Aufbaufehlern in diesem Bereich, da diese Fehler erhebliche negative Auswirkungen auf die Benutzererfahrung haben.

Starten Sie Ihre Untersuchung, indem Sie den Prozentsatz der gesamten Aufbaufehler für die Organisation abschätzen und dann die Untersuchungsbereiche auf der Grundlage des höchsten Prozentsatzes nach Gebäude oder Netzwerk priorisieren. 

#### <a name="setup-failure-trend-analysis"></a>Trendanalyse der Aufbaufehler

In diesem Bericht werden die Gesamtmenge der Datenströme, Fehler bei dem Datenstromaufbau und die Fehlerrate des Datenstromaufbaus angezeigt. Zeigen Sie auf eine der Spalten, um die einzelnen Werte anzuzeigen, wie in der folgenden Abbildung dargestellt. 

![Diagramm, das den Prozentsatz der Fehler beim Datenstromaufbau anzeigt](media/qerguide-image-streamsetupfailures.png)

_Abbildung 19 – Zuverlässigkeit der Audiowiedergabe – Datenstromaufbaufehler_

##### <a name="analysis"></a>Analyse

Mit diesem Bericht können Sie die folgenden Fragen beantworten und Ihre nächste Vorgehensweise festlegen:

-   Wie hoch ist der Prozentsatz der Fehler bei dem Anrufaufbau für den laufenden Monat?

-   Liegt der Prozentsatz der Fehler bei dem Anrufaufbau unterhalb oder oberhalb der festgelegten Zielmetrik?

-   Ist der Fehlertrend schlechter oder besser als im vorhergehenden Monat?

-   Steigt der Fehlertrend, wird er stetig oder sinkt er?

Unabhängig von den vorhergehenden Antworten sollten Sie sich die Zeit nehmen, weiter zu untersuchen, indem Sie die zugehörigen Unterberichte verwenden, um nach einzelnen Gebäuden oder Subnetzen zu suchen, die möglicherweise eine Fehlerbehebung bedürfen. Obwohl die Gesamtfehlerrate möglicherweise unter der Zielmetrik liegt, sind die Fehlerraten für ein oder mehrere Gebäude oder Netzwerke möglicherweise über der Zielmetrik und benötigen Untersuchungen.

#### <a name="setup-failure-investigations"></a>Untersuchungen bei Aufbaufehlern 

Dieser Zusammenfassungsbericht wird verwendet, um Gebäude oder Netzwerke zu finden und zu isolieren, die ggf. eine Fehlerbehebung bedürfen.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Berichtsfilter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie den Berichtsfilter **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.


![Screenshot mit Aufbaufehlern](media/qerguide-image-setupfailuresbysubnet.png)

_Abbildung 20 – Audioaufbaufehler nach Subnetz_

##### <a name="remediation"></a>Fehlerbehebung 

Konzentrieren Sie sich auf Gebäude oder Subnetze, die das größte Fehlervolumen aufweisen. Auf diese Weise können Sie die Auswirkungen auf die Benutzeroberfläche maximieren und so die Aufbaufehlerrate von Organisationsanrufen schnell reduzieren. In der folgenden Tabelle sind die zwei Gründe für Aufbaufehler aufgelistet, die von CQD gemeldet wurden.

_Tabelle 7 – Gründe für Anrufaufbaufehler_

| Gründe für Anrufaufbaufehler       | Typische Ursache                    |
|----------------------------------|----------------------------------|
| Fehlende Ausnahmeregel für FW-DPI (Deep Packet Inspection) | Deutet darauf hin, dass die Netzwerkausrüstung entlang des Pfads verhindert hat, dass der Medienpfad aufgrund von DPI-Regeln nicht erstellt wurde. Dies ist möglicherweise auf nicht ordnungsgemäß konfigurierte Firewallregeln zurückzuführen. In diesem Szenario war der TCP-Handshake erfolgreich, aber der SSL-Handshake nicht.      |
| Fehlende Ausnahmeregel für FW-IP-Block      | Deutet darauf hin, dass die Netzwerkausstattung entlang des Pfads verhindert hat, dass der Medienpfad zum Office 365-Netzwerk erstellt wurde. Dies könnte darauf zurückzuführen sein, dass Proxy- oder Firewallregeln nicht ordnungsgemäß konfiguriert wurden, um den Zugriff auf die für Teams- und Skype for Business-Datenverkehr verwendeten IP-Adressen und Ports nicht ordnungsgemäß konfiguriert wurden. |

Wenn Sie mit der Behebung beginnen, können Sie Ihre Bemühungen nun auf ein bestimmtes Gebäude oder Subnetz konzentrieren. Wie in der vorstehenden Tabelle zu sehen ist, sind diese Probleme auf Firewall- oder Proxy-Konfigurationen zurückzuführen. Überprüfen Sie die in der folgenden Tabelle aufgeführten Optionen für Wartungsaktionen.

_Tabelle 8 – Nächste Schritte für die Behebung von Anrufaufbaufehlern_


|      Fehlerbehebung      |                                                                                                                                                                                                                                                                                                                                                                   Anleitung                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurieren von Firewall(s) | Arbeiten Sie mit Ihrem Netzwerkteam zusammen und überprüfen Sie die Konfiguration Ihrer Firewall(s) für [die Office 365-IP-Adressliste](https://aka.ms/o365ips).<br><br>Vergewissern Sie sich, dass die [Medien-Subnetze](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) und -Ports in den Firewallregeln enthalten sind. <br><br>Überprüfen Sie, ob die erforderlichen Ports (siehe unten) in der Firewall geöffnet sind. UDP sollte vorrangig sein, da TCP als Rückfallprotokoll für Audio-, Video- und videobasierte Bildschirmfreigaben betrachtet wird und deren Verwendung sich auf die Qualität des Anrufs auswirkt. Die alte RDP-Anwendungsfreigabe verwendet nur TCP.<br><ul><li>**TCP:** Port 443</li><li>**UDP:** Ports 3478–3481</li><ul> |
|        Überprüfen         |                                                                                                                                                                                                                                                                 Verwenden Sie das [Microsoft Network Assessment-Tool](https://www.microsoft.com/download/details.aspx?id=53885), um die Konnektivität aus dem betroffenen Gebäude oder Subnetz über die Funktion "Konnektivität prüfen" zu überprüfen.                                                                                                                                                                                                                                                                  |

### <a name="drop-failures"></a>Abbruchfehler

Im Gegensatz zu Aufbaufehlercodes hat CDQ keinen Abbruchfehlercode, um anzugeben, warum es zu Abbrüche kommt, wodurch es schwierig wird, eine bestimmte Ursache zu isolieren. Verwenden Sie einen abgeleiteten Ansatz, um Abbruchfehler besser zu erkennen. Durch die Behebung aller Bereiche, die für die Medien von Interesse sind, das Patchen von Clients und Treibern und die Nutzung zertifizierter Geräte für Teams und Skype for Business können Sie erwarten, dass die Zahl der Abbrüche zurückgehen wird.

#### <a name="drop-failure-trend-analysis"></a>Trendanalyse der Abbruchfehler

In diesem Bericht werden die Gesamtmenge der Audiodatenströme, die Gesamtanzahl der Abbruchfehler und die Abbruchfehlerrate angezeigt. Zeigen Sie auf eine der Spalten, um die Werte anzuzeigen, wie in der folgenden Abbildung dargestellt. 

![Diagramm, das den Prozentsatz der abgebrochenen Datenströme zeigt](media/qerguide-image-droppedstreamrate.png)

_Abbildung 21 – Rate der abgebrochenen Datenströme_

##### <a name="analysis"></a>Analyse

Mithilfe dieser Art von Bericht können Sie die folgenden Fragen beantworten:

-   Was ist die aktuelle Abbruchfehlerrate?
-   Liegt die Abbruchfehlerrate unter der definierten Zielmetrik?
-   Ist der Fehlertrend schlechter oder besser als im vorhergehenden Monat?
-   Steigt der Fehlertrend, wird er stetig oder sinkt er?

Unabhängig von den Antworten auf den obigen Fragen sollten Sie sich die Zeit für eine Untersuchung nehmen, bei der Sie die zugehörigen Unterberichte verwenden, um nach Gebäuden oder Netzwerken zu suchen, die möglicherweise eine Fehlerbehebung bedürfen. Obwohl die Gesamtrate der Abbruchfehler möglicherweise unter der Zielmetrik liegt, sind die Fehlerraten für ein oder mehrere Gebäude oder Netzwerke möglicherweise über der Zielmetrik und benötigen Untersuchungen.

#### <a name="drop-failure-investigations"></a>Untersuchungen bei Abbruchfehlern

Die hier aufgeführten Fehler geben an, dass der Anruf unerwartet abgebrochen wurde und zu einer negativen Benutzererfahrung geführt hat. Im Gegensatz zu den Trendberichten bieten diese Berichte zusätzliche Einblicke in bestimmte Subnetze, die weitere Untersuchungen benötigen.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Filter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.


![Bericht, in dem die Anzahl und der Prozentsatz der Abbruchfehler aufgelistet sind](media/qerguide-image-dropfailuresbysubnet.png)

_Abbildung 22 – Abbruchfehler nach Subnetz_

##### <a name="remediation"></a>Fehlerbehebung

Mithilfe der integrierten Tabelle „Berichte“ können Sie Problembereiche im Netzwerk isolieren, bei denen die Abbruchrate über der von Ihnen festgelegten Zielmetrik liegt. Konzentrieren Sie sich auf Gebäude oder Subnetze, die die höchste Gesamtzahl von Datenströmen aufweisen, um die größten Auswirkungen auf Gebäude oder Subnetze zu erzielen.

Häufige Ursachen von Anrufabbrüchen:

-   Netzwerk- oder Internetdatenverkehr mit unzureichenden Ressourcen
-   Kein QoS konfiguriert in eingeschränkten Netzwerken
-   Ältere Clientversionen
-   Benutzerverhalten

Nachdem Sie die Problembereiche ermittelt haben, können Sie mithilfe von [Anrufanalyse](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) die Benutzer in diesem Gebäude für bestimmte Probleme weiter überprüfen. Die Anrufanalyse enthält zusätzliche PII-Daten und kann nützlich sein, um potenzielle Gründe für die Abbruchfehler weiter zu isolieren.

Ungeachtet des nächsten Schritts empfiehlt es sich, dem Helpdesk mitzuteilen, dass ein Problem mit bestimmten Gebäuden oder Subnetzen ermittelt wurde. Auf diese Weise können sie auf eingehende Anrufe schnell reagieren und Benutzer effizienter einführen. Gekennzeichnete Benutzer können dann an das Entwicklungsteam zur weiteren Untersuchung zurückgemeldet werden.

Die folgende Tabelle enthält einige häufige Methoden zum Verwalten und Beheben von Abbruchfehlern.

_Tabelle 9 – Nächste Schritte für die Behebung von Anrufabbrüchen_

| Fehlerbehebung                              | Anleitung                      |
|------------------------------------------|-------------------------------|
| **Netzwerk/ Internet**                         | **Überlastung**: Arbeiten Sie mit Ihrem Netzwerkteam zusammen, um die Bandbreite bei bestimmten Gebäuden/ Subnetzen zu überwachen, um zu bestätigen, dass es Probleme mit der Übernutzung gibt. Wenn Sie feststellen, dass es zu einer Netzwerküberlastung kommt, überlegen Sie sich, die Bandbreite zu diesem Gebäude zu erhöhen oder QoS anzuwenden. Verwenden Sie die integrierten [Zusammenfassungsberichte über Datenströme mit schlechter Qualität](#quality-investigations), um die problematischen Subnetze bei Problemen mit Jitter, Latenz und Paketverlusten zu überprüfen, da diese häufig einem abgebrochenen Datenstrom vorausgehen.<br><br>**QoS**: Wenn eine Erhöhung der Bandbreite unpraktisch oder unerschwinglich sein sollte, überlegen Sie sich, QoS zu implementieren. Dieses Tool eignet sich besonders für die Verwaltung von überlasteten Datenverkehr und kann dafür sorgen, dass Medienpakete im verwalteten Netzwerk Vorrang vor nicht-Mediendatenverkehr haben. Wenn aber keine eindeutigen Anhaltspunkte dafür vorliegen, dass Bandbreite der Täter ist, können Sie die folgenden Lösungen in Betracht ziehen:<ul><li>[Microsoft Teams QoS-Anleitung](qos-in-teams.md)</li></ul><br>**Ausführen einer Bewertung der Netzwerkbereitschaft**: Eine Netzwerkbewertung liefert Details über die erwartete Bandbreitennutzung, die Beherrschung von Bandbreiten- und Netzwerkänderungen sowie empfohlene Netzwerkpraktiken für Teams und Skype for Business. Wenn Sie die vorstehende Tabelle als Quelle verwenden, haben Sie eine Liste von Gebäuden oder Subnetzen, die hervorragende Kandidaten für eine Bewertung sind.<ul><li>[Microsoft Teams Bewertung der Netzwerkbereitschaft](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Microsoft Network Assessment-Tool:** Verwenden Sie dieses Tool für einen einfachen Test der Netzwerkleistung, um zu ermitteln, wie gut das Netzwerk bei einem Teams- oder Skype for Business Online-Anruf funktionieren würde. Das Tool hilft Ihnen, die Leistung eines Subnetzes zu bewerten und die Bereitschaft des Netzwerks anhand der [Leistungsanforderungen](https://aka.ms/performancerequirements)# von Microsoft zu validieren.<ul><li>[Das Network Assessment-Tool herunterladen](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul> |
| **Clients (nur für Skype for Business Online)** | Einige ältere Clients haben bekannte Probleme mit der Zuverlässigkeit der Medien. Überprüfen Sie die Anrufanalyseberichte mehrerer betroffener Benutzer oder erstellen Sie einen benutzerdefinierten Bericht in einer Client-Versionstabelle in CQD, gefiltert nach bestimmten Gebäuden oder Subnetzen mit der Messung der Gesamtzahl an Anrufabbruchfehler in %. Anhand dieser Informationen können Sie erkennen, ob eine Beziehung zwischen Anrufabbrüchen in diesem spezifischen Gebäude und einer bestimmten Version des Clients besteht.     |
| **Geräte**                                  | Wir empfehlen, dass alle Benutzer, die mit Anrufabbrüchen oder schlechten Anrufen im Allgemeinen konfrontiert sind und integrierte Geräte verwenden, ein [zertifiziertes Headset oder eine Freisprechanlage](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) erhalten sollten, um dies als potenzielle Quelle schlechter Qualität und Zuverlässigkeit auszuschließen. |
| **Benutzerverhalten**                            | Wenn Sie feststellen, dass weder Netzwerk, noch Geräte oder Clients das Problem sind, sollten Sie die Entwicklung einer Benutzeradaptionsstrategie in Betracht ziehen, um die Benutzer darüber aufzuklären, wie sie am besten an Besprechungen teilnehmen und diese verlassen können. Besser vorbereitete Teams- und Skype for Business-Benutzer sorgen für eine bessere Benutzererfahrung für alle Teilnehmer. Wenn ein Benutzer seinen Laptop in den Ruhezustand versetzt (durch Schließen des Deckels), ohne die Besprechung zu verlassen, wird als unerwarteter Anrufabbruch eingestuft.   |

## <a name="quality-investigations"></a>Qualitätsuntersuchungen

Der nächste Schritt zur Einschätzung des Zustands der Audioqualität innerhalb der Organisation ist die Untersuchung schlechter Datenstromraten (PSR), TCP und Proxy-Nutzung. Es ist wichtig, sich daran zu erinnern, dass die CQD-Daten Ihnen keine spezifische Ursache liefern, sondern Ihnen stattdessen wahrscheinliche Problembereiche zur Verfügung stellen, um ein gemeinsames Gespräch mit den entsprechenden Teams für Abhilfemaßnahmen zu beginnen. 

> [!NOTE]
> In diesem Leitfaden werden nicht alle in den Vorlagen enthaltenen Berichte behandelt. Die nachstehend erläuterten Methoden für die Untersuchung gelten jedoch weiterhin für diese Berichte. Weitere Informationen finden Sie in der Beschreibung des jeweiligen Berichts. 

### <a name="quality"></a>Qualität

Die PSR-Prozentsätze werden verwendet, um anzugeben, ob die Organisation die festgelegten Metrikziele für einen bestimmten Schwerpunktbereich erfüllt. Es ist wichtig zu beachten, dass einzelne Subnetze oder Gebäude die definierten Ziele möglicherweise nicht erreichen, auch wenn sich die Prozentsätze auf hoher Ebene innerhalb des definierten Ziels befinden, und daher weitere Untersuchungen erforderlich sind. Wenn beispielsweise der Gesamtprozentsatz des Audio-PSR im April 2 Prozent beträgt, was der Zielvorgabe der Stichprobe entspricht, könnten einzelne Gebäude und Subnetze immer noch schlechte Erfahrungen machen, abhängig von der Gesamtverteilung dieser 2 Prozent. 

Wenn Sie den Prozentsatz schlechter Datenströme bewerten möchten, verwenden Sie die Qualitätsberichte. Es werden verschiedene Qualitätsberichte bereitgestellt, um Metriken der Gesamtzahl der Anrufe, Konferenz-, Zwei-Parteien-, PSTN-Anrufe, VPN und Besprechungsräume zu überprüfen. Zur Unterstützung bei diesem Vorgang werden monatliche, wöchentliche und tägliche Berichte bereitgestellt. Die wöchentlichen und täglichen Berichte beschränken sich auf die Vorlage "Verwaltete Netzwerke", um ihre Wirksamkeit zu erhöhen und Störungen zu reduzieren. 

#### <a name="quality-trend-analysis"></a>Qualitätstrendanalyse

Trendberichte zeigen Qualitätsinformationen über die Zeit an und dienen dazu, Qualitätstrends in jedem Interessengebiet zu erkennen und zu verstehen. Wie oben erwähnt, sind in den Vorlagen zur Untersuchung der Qualität Berichtsbäume enthalten; Konferenz-, Zweiparteien-, PSTN-Telefonie, VPN und Besprechungsräume. Der Untersuchungsprozess zur Analyse der Qualität ist identisch. Allerdings empfiehlt es sich, bei den Konferenzbesprechungen zu beginnen, da sich alle Verbesserungen bei der Konferenzqualität positiv auf alle anderen Bereiche auswirken. 

> [!Note]
> Die Untersuchung von Zwei-Parteien-Anrufe, PSTN-Telefonie und Besprechungsräumen ist ähnlich wie die Untersuchung von Konferenzgesprächen. Der Schwerpunkt liegt darauf, die Gebäude oder Subnetze, die die schlechteste Qualität aufweisen, zu isolieren und die Gründe für die schlechte Qualität zu ermitteln.

> [!Important]
> VPN-basierte Berichte werden mithilfe der zweiten VPN-Dimension gefiltert. Diese Dimension setzt voraus, dass der VPN-Netzwerkadapter ordnungsgemäß als Fernzugriffadapter registriert ist. VPN-Anbieter verwenden dieses Kennzeichen nicht zuverlässig, und Ihr Verbrauch hängt von dem in Ihrem Unternehmen eingesetzten VPN-Anbieter ab. Befolgen Sie die [weiter oben in diesem Leitfaden](#vpn) beschriebenen Anweisungen, um die VPN-Berichte bei Bedarf unter Verwendung des Gebäude- oder Netzwerknamens zu modifizieren.

![Diagramm, das den Prozentsatz der Datenströme mit schlechter Qualität zeigt](media/qerguide-image-audioqualityconferencing.png)

_Abbildung 23 – Audioqualität – Konferenzen_

##### <a name="investigation"></a>Untersuchung

Mithilfe dieser Berichte können Sie die folgenden Fragen beantworten:

-   Wie hoch ist die gesamte PSR für den aktuellen Monat?
-   Liegt die PSR unter der definierten Zielmetrik?
-   Ist die PSR schlechter oder besser als im vorhergehenden Monat?
-   Steigt die PSR, wird sie stetig oder sinkt sie?

Unabhängig von den Antworten auf den obigen Fragen sollten Sie sich die Zeit für eine Untersuchung nehmen, bei der Sie die zugehörigen Unterberichte verwenden, um nach Gebäuden oder Subnetzen zu suchen, die möglicherweise eine Untersuchung bedürfen. Obwohl die allgemeine PSR möglicherweise unter der Zielmetrik liegt, liegt die PSR für ein oder mehrere Gebäude oder Netzwerke häufig über der Metrik und muss korrigiert werden.

#### <a name="quality-investigations"></a>Qualitätsuntersuchungen

Die zusammenfassenden Qualitätsberichte geben Ihnen einen tieferen Einblick in das, was dazu beigetragen hat, dass die Datenströme als schlecht eingestuft wurden, und helfen, Problembereiche im verwalteten Netzwerk zu isolieren.

Obwohl sich die verwendeten Dimensionen von Bericht zu Bericht leicht unterscheiden können, wird jeder Bericht Maßnahmen für Gesamtdatenströme, schlechte Gesamtdatenströme, PSR und schlechte Qualität aufgrund schlechter Qualität enthalten. Es wurden Berichte für jeden Interessenbereich erstellt: Konferenzen, Zwei-Parteien-Gespräche, PSTN-Anrufe, VPN und Besprechungsräume. Die Vorlage zu verwalteten Netzwerke enthält zusätzliche Berichte, um die Standortinformationen zu nutzen, die über die Gebäudedatei hochgeladen wurden.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Filter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.

> [!Note]
> Häufig verwendete Subnetze können aufgrund ihrer weit reichenden Nutzung nur schwer verfolgt werden. Ein separater Bericht, der die öffentliche IP (zweite reflexive lokale IP) des Clients anzeigt, wurde der Vorlage "Alle Netzwerke" hinzugefügt, um bei der Fehlerbehebung in Büros, die gemeinsame Netzwerke verwenden, zu helfen.


![Screenshot mit der Zusammenfassung des schlechten Audiodatenstroms](media/qerguide-image-poorqualitysummary.png)

_Abbildung 24 – Zusammenfassung unzureichender Audiodatenströme nach Gebäude und Subnetz-Konferenzgesprächen_

##### <a name="remediation"></a>Fehlerbehebung

Konzentrieren Sie sich auf Gebäude oder Subnetze, die über die größten Mengen an Datenströmen verfügen, da sich dadurch die Wirkung maximieren lässt und die Benutzererfahrung schnell verbessert wird. Verwenden Sie Jitter-, Paket- und Round-trip-Messungen, um zu verstehen, was zu schlechter Qualität beiträgt (es ist möglich, dass mehr als ein Problem vorliegt):

-   **Jitter**: Medienpakete kommen mit unterschiedlichen Geschwindigkeiten an, was dazu führt, dass der Sprechende robotisch klingt.
-   **Paketverlust**: Medienpakete werden ausgelassen, was den Effekt von fehlenden Wörtern oder Silben erzeugt.
-   **RTT**: Medienpakete brauchen lange, um an ihr Ziel zu gelangen, wodurch ein Walkie-Talkie-Effekt entsteht.

Um Ihre Untersuchung von Qualitätsproblemen zu unterstützen, können Sie die [Anrufanalyse](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) nutzen. Mithilfe der Anrufanalyse können Sie sich den Bericht über eine bestimmte Konferenz oder den detaillierten Anrufbericht der Benutzer ansehen. Dieser Bericht enthält PII-Daten und ist nützlich, wenn Sie nach der Ursache eines Fehlers suchen. Nachdem Sie erkannt haben, welche Gebäude betroffen sind, sollten Sie die Benutzer in diesem Gebäude einfach nachverfolgen. 

Vergessen Sie nicht, dem Helpdesk mitzuteilen, dass es bei diesen Netzwerken Qualitätsprobleme gibt, damit Sie eingehende Anrufe schnell auswerten und darauf reagieren können.

_Tabelle 10 –Häufige Ursachen einer hohen PSR_

| Fehlerbehebung                              | Anleitung                         |
|------------------------------------------|----------------------------------|
| **Netzwerke**                                 | **Überlastung**: Ein überlastetes Netzwerk oder ein Netzwerk mit mangelhaften Ressourcen kann Probleme mit der Medienqualität verursachen. Arbeiten Sie mit dem Netzwerkteam zusammen, um festzustellen, ob die Netzwerkverbindungen vom Benutzer zum Internet-Ausgangspunkt über genügend Bandbreite zur Unterstützung der Medien verfügen. <br><br>**Ausführen einer Bewertung der Netzwerkbereitschaft**: Eine Netzwerkbewertung liefert Details über die erwartete Bandbreitennutzung, die Beherrschung von Bandbreiten- und Netzwerkänderungen sowie empfohlene Netzwerkpraktiken für Teams und Skype for Business. Wenn Sie die vorstehende Tabelle als Quelle verwenden, haben Sie eine Liste von Gebäuden oder Subnetzen, die hervorragende Kandidaten für eine Bewertung sind.<ul><li>[Microsoft Teams Bewertung der Netzwerkbereitschaft](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Microsoft Network Assessment-Tool:** Verwenden Sie dieses Tool für einen einfachen Test der Netzwerkleistung, um zu ermitteln, wie gut das Netzwerk bei einem Teams- oder Skype for Business Online-Anruf funktionieren würde. Das Tool hilft Ihnen, die Leistung eines Subnetzes zu bewerten und die Bereitschaft des Netzwerks anhand der [Leistungsanforderungen](https://aka.ms/performancerequirements)# von Microsoft zu validieren.<ul><li>[Das Network Assessment-Tool herunterladen](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br> |
| **Quality of Service (QoS)**  | QoS ist ein bewährtes Tool, das die Priorisierung von Paketen in einem überlasteten Netzwerk unterstützt, um sicherzustellen, dass sie im Ganzen und pünktlich am Bestimmungsort ankommen. Erwägen Sie die Implementierung von QoS in Ihrer Organisation, um die Qualität der Benutzererfahrung zu maximieren, wenn die Bandbreite eingeschränkt ist. QoS hilft beim Beheben von Problemen, die normalerweise mit einem hohen Maß an Paketverlust verbunden sind, und – zu einem geringeren Grad – von Problemen mit Jitter und Round-trip-Zeiten.<ul><li>[Microsoft Teams QoS-Anleitung](qos-in-teams.md)</li></ul> |
| **WLAN**               | WLAN kann sich erheblich auf die Anrufqualität auswirken. Bei WLAN-Bereitstellungen werden die Netzwerkanforderungen für VoIP-Dienste in der Regel nicht berücksichtigt und sie stellen häufig eine Quelle schlechter Qualität dar. Weitere Informationen zur Optimierung Ihrer WLAN-Infrastruktur finden Sie [in diesem Artikel über die WLAN-Planung](/skypeforbusiness/certification/plan-wifi).<br><br>**WLAN-Treiber**: Stellen Sie sicher, dass die Treiber für die WLAN-Verbindung auf dem neuesten Stand sind. Auf diese Weise können Sie die schlechte Benutzererfahrung im Zusammenhang mit einem veralteten Treiber verringern. In vielen Organisationen sind keine WLAN-Treiber in den Patch-Zyklen enthalten und diese Treiber können jahrelang ohne Patches arbeiten. Viele WLAN-Probleme werden behoben, indem sichergestellt wird, dass die WLAN-Treiber aktuell sind.<br><br>**WMM**: WMM (Wireless Multimedia Extensions), auch als WLAN-Multimedia bezeichnet, bieten grundlegende QoS-Funktionalitäten für drahtlose Netzwerke. Moderne drahtlose Netzwerke müssen viele Geräte unterstützen. Diese Geräte konkurrieren um die Bandbreite und können zu Qualitätsproblemen für VoIP-Dienste führen, bei denen Geschwindigkeit und Latenz am wichtigsten sind. Erkundigen Sie sich bei Ihrem WLAN-Anbieter nach den Einzelheiten und erwägen Sie die Implementierung von WMM in Ihrem WLAN-Netzwerk, um den Medien von Skype for Business und Teams Priorität einzuräumen.<br><br>**Zugriffspunktdichte**: Zugriffspunkte sind möglicherweise zu weit voneinander entfernt oder nicht an einer idealen Position. Um potenzielle Interferenzen zu minimieren, setzen Sie zusätzliche Zugriffspunkte in Konferenzräumen und an Orten, die nicht durch Wände oder andere Objekte behindert werden, in denen das WLAN-Signal schwach ist.<br><br>**2,4 GHz gegenüber 5 GHz**: 5 GHz bietet weniger Hintergrundinterferenzen und höhere Geschwindigkeiten und sollte bei der Bereitstellung von VoIP über WLAN bevorzugt werden. Allerdings ist 5 GHz nicht so stark wie 2,4 GHz und durchdringt Wände nicht so leicht. Überprüfen Sie Ihr Gebäude-Layout, um festzustellen, auf welche Frequenz Sie sich für die beste Verbindung verlassen können. |
|**Netzwerkgerät** | In größeren Unternehmen gibt es möglicherweise Hunderte von Geräten, die über das Netzwerk verteilt sind. Arbeiten Sie mit Ihrem Netzwerkteam zusammen, um sicherzustellen, dass die Netzwerkgeräte vom Benutzer bis zum Internet gewartet und auf dem neuesten Stand sind. |
| **VPN**  | VPN-Geräte sind normalerweise nicht für die Bewältigung von Echtzeit-Medienarbeitslasten ausgelegt. Einige VPN-Konfigurationen verbieten die Verwendung von UDP (das bevorzugte Protokoll für Medien) und verlassen sich nur auf TCP. Erwägen Sie die Implementierung einer VPN-Lösung mit geteiltem Tunnel, um VPN als Quelle schlechter Qualität zu reduzieren. |
| **Clients** <br>(Nur für Skype for Business Online) | Stellen Sie sicher, dass alle Clients regelmäßig aktualisiert werden. |
| **Geräte** | Die Verwendung von [optimierten Geräten](https://partnersolutions.skypeforbusiness.com/solutionscatalog) kann dabei helfen, die Benutzererfahrung erheblich zu verbessern. Die optimierten Geräte sind so konzipiert, dass sie die Benutzererfahrung mit Teams und Skype for Business maximieren und höchste Qualität erzielen. |
| **Treiber** | Patchen von Netzwerk (Ethernet und WLAN), Audio-, Video- und USB-Treibern sollten Bestandteil ihrer Gesamtstrategie zur Patchverwaltung sein. Viele Qualitätsprobleme werden durch das Aktualisieren von Treibern behoben. |
| **Konferenzräume mit WLAN** | Es wird dringend empfohlen, dass Konferenzraumgeräte mit mindestens 1 Gbit/s Ethernet-Verbindung mit dem Netzwerk verbunden sind. Konferenzraumgeräte umfassen in der Regel mehrere Audio- und Videodatenströme sowie Konferenzinhalte wie Bildschirmfreigaben und höhere Netzwerkanforderungen als andere Teams oder Skype for Business-Endpunkte. Konferenzräume sind definitionsgemäß stationäre Geräte, bei denen WLAN nur während der Installation einen Nutzen bringt.<br><br>Konferenzräume müssen mit besonderer Sorgfalt behandelt werden, um sicherzustellen, dass die Erfahrung mit diesen Geräten die Erwartungen erfüllt oder übersteigt. Qualitätsprobleme mit Konferenzräumen werden in der Regel schnell eskaliert, da Sie häufig von Mitarbeitern des obersten Rangs verwendet werden.<br><br>Bei gleicher Leistung (abgesehen von der Bequemlichkeit) ist die WLAN-Leistung oft geringer als bei einer kabelgebundenen Verbindung. Mit dem Aufkommen der "Bring your own device"-Politik und der Verbreitung von Laptops werden WLAN-Zugangspunkte oft übermäßig genutzt. Echtzeit-Medien werden in WLAN-Netzwerken möglicherweise nicht priorisiert, was zu Qualitätsproblemen während der Zeiten mit stärkster Nutzung führen kann. Diese intensive Nutzung kann mit einer Besprechung zusammenfallen, bei der es ein Dutzend Personen gibt, die jeweils über einen eigenen Laptop und ein Smartphone verfügen, die alle mit demselben WLAN-Zugangspunkt wie das Gerät für den Besprechungsraum verbunden sind.<br><br>WLAN sollte nur als eine vorübergehende Lösung für eine mobile Installation oder wenn WLAN ordnungsgemäß für die Unterstützung von Echtzeit-Medien der Unternehmensklasse bereitgestellt wurde, in Betracht gezogen werden. |


### <a name="tcp"></a>TCP

TCP wird als Failback-Transport und nicht als primärer Transport für Echtzeitmedien betrachtet. Der Grund dafür, dass es sich um einen Failback-Transport handelt, liegt in der zustandsabhängigen Natur von TCP. Wenn beispielsweise ein Anruf in einem latenten Netzwerk getätigt wird und Medienpakete verzögert werden, dann konkurrieren Pakete von vor einigen Sekunden, die nicht mehr nützlich sind, um Bandbreite, um zum Empfänger zu gelangen, was eine schlechte Situation verschärft. Dies führt dazu, dass die Audioqualitätsbehebung den Ton zusammenfügt und streckt, was zu hörbaren Artefakten führt, oft in Form von Jitter.

In den Berichten in diesem Abschnitt wird nicht zwischen guten und schlechten Datenströmen unterschieden. Da UDP bevorzugt wird, suchen die Berichte nach der Verwendung von TCP für Audio, Video und videobasierte Bildschirmfreigabe (VBSS). Es werden schlechte Datenstromraten zur Ansicht bereitgestellt, um die UDP-Qualität im Vergleich zur TCP-Qualität zu vergleichen, damit Sie sich auf die größten Auswirkungen konzentrieren können. Die TCP-Nutzung wird in erster Linie durch unvollständige Firewallregeln verursacht. Weitere Informationen zu Firewallregeln für Teams und Skype for Business Online finden Sie unter [Office 365-URLs und -IP-Adressbereiche](https://aka.ms/o365ips).

> [!Important]
> Es wird dringend empfohlen, eine [gültige Gebäudedatei](#building-mapping) hochgeladen zu haben, damit Sie beim Betrachten der TCP-Nutzung schnell zwischen internen und externen Datenströmen unterscheiden können.

> [!Note]
> Audio, Video und VBSS bevorzugen alle UDP als ihren Haupttransport. Die alte Arbeitsauslastung für RDP-Anwendungsfreigabe verwendet nur TCP.

#### <a name="tcp-usage"></a>TCP-Nutzung

TCP-Berichte geben die gesamte TCP-Nutzung in den letzten sieben Monaten an. In allen anderen Berichten in diesem Abschnitt geht es um das einschränken bestimmter Gebäude und Subnetze, in denen TCP am häufigsten verwendet wird. Für Konferenzen und Datenströme mit zwei Parteien stehen separate Berichte zur Verfügung.

![Diagramm mit dem Prozentsatz der Audiodatenströme, die TCP verwenden](media/qerguide-image-audiostreamswithtcp.png)
_Abbildung 25 – Audiodatenströme mit TCP-Nutzung_


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

_Abbildung 26 – TCP- vs. UDP-Konferenzgespräche_

##### <a name="analysis"></a>Analyse

Obwohl Sie die TCP-Nutzung so gering wie möglich halten wollen, kann es sein, dass Sie in einer ansonsten gesunden Bereitstellung ein wenig TCP-Nutzung sehen. TCP allein trägt nicht zu einem schlechten Anruf bei, daher werden Datenstromraten bereitgestellt, um festzustellen, ob die TCP-Nutzung zu einer schlechten Qualität beiträgt. 

#### <a name="tcp-investigations"></a>TCP-Untersuchungen

Navigieren Sie in den bereitgestellten CQD-Vorlagen zu den TCP-Datenströmen nach Gebäude- und Subnetzberichten mithilfe der Vorlage „Verwaltete Netzwerke“ oder „Alle Netzwerke“. Um die TCP-Nutzung zu untersuchen, ist der Prozess identisch. Deshalb konzentriert wir uns hier auf Konferenzen.

> [!IMPORTANT]
> Es wird empfohlen, eine [gültige Gebäudedatei](#building-mapping) hochgeladen zu haben, damit Sie beim Betrachten der TCP-Nutzung schnell zwischen internen und externen Datenströmen unterscheiden können. 

> [!NOTE]
> Stellen Sie sicher, dass Sie den Filter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.                                  |

![Screenshot der TCP-Nutzung nach Gebäude und Subnetz](media/qerguide-image-tcpstreams.png)

_Abbildung 27 – TCP-Datenströme nach Gebäude und Subnetz – Konferenzbesprechungen_

##### <a name="remediation"></a>Fehlerbehebung

In diesem Bericht werden bestimmte Gebäude und Subnetze identifiziert, die zum Volumen der TCP-Nutzung beitragen. Außerdem wird ein weiterer Bericht hinzugefügt, um die Microsoft Relay-IP zu identifizieren, die beim Anruf verwendet wurde, um fehlende Firewallregeln zu isolieren. Konzentrieren Sie sich auf die Gebäude, die den größten Teil der TCP-Datenströme haben, um die Auswirkungen zu maximieren.

Die häufigste Ursache für die TCP-Nutzung sind fehlende Ausnahmeregeln in Firewalls oder Proxys. Wir werden über Proxys im nächsten Abschnitt sprechen, also konzentrieren Sie sich jetzt auf die Firewalls. Wenn Sie das bereitgestellte Gebäude oder Subnetz verwenden, können Sie ermitteln, welche Firewall aktualisiert werden muss.


_Tabelle 11 – Leitfaden zur Fehlerbehebung von TCP-Datenströmen nach Gebäude und Subnetz_

| Fehlerbehebung        | Anleitung     |
|--------------------|--------------------------------------|
| Konfigurieren der Firewall | Stellen Sie sicher, dass die [Office 365-IP-Ports und -Adressen](https://aka.ms/o365ips) aus Ihrer Firewall ausgeschlossen sind. Konzentrieren Sie sich bei medienbezogenen TCP-Problemen zunächst auf Folgendes:<ul><li>Vergewissern Sie sich, dass die Medien-Subnetze 13.107.64.0/18 und 52.112.0.0/14 des Clients in ihren Firewallregeln enthalten sind.</li><li>UDP-Ports 3478–3481 sind die erforderlichen Media-Ports und müssen geöffnet werden, andernfalls kehrt der Client zurück zu TCP-Port 443.</li></ul> |
| Überprüfen             | Verwenden Sie das [Microsoft Network Assessment-Tool](https://www.microsoft.com/download/details.aspx?id=53885), um nach Problemen mit der Verbindung zu bestimmten Office 365-IP-Adressen und Ports aus dem betroffenen Gebäude oder Subnetz zu suchen.    |

### <a name="http-proxy"></a>HTTP-Proxy

HTTP-Proxys sind aus einer Vielzahl von Gründen nicht der bevorzugte Weg zum Aufbauen von Mediensitzungen. Viele bieten umfassende Funktionen zur Paketprüfung, die verhindern, dass Verbindungen mit dem Dienst ausgeführt werden, wodurch Unterbrechungen auftreten. Darüber hinaus erzwingen nahezu alle Proxys TCP im Gegensatz zu der zuzulassenden UDP-Funktion, die für optimale Audioqualität empfohlen wird.

Es wird immer empfohlen, den Client so zu konfigurieren, dass er eine direkte Verbindung mit Teams und Skype for Business-Diensten herstellt. Dies ist besonders wichtig für den medienbasierten Datenverkehr.


> [!IMPORTANT]
> Wenn Sie eine gültige [Gebäudedatei ](#building-mapping) hochgeladen haben, können Sie bei der Analyse der Proxy-Nutzung ganz einfach zwischen internen und externen Audiodatenströmen unterscheiden. 


#### <a name="http-proxy-usage"></a>Nutzung von HTTP-Proxys

Der Bericht über den HTTP-Proxy-Datenstrom in diesem Abschnitt der Vorlage ähnelt den TCP-Berichten. Dabei wird nicht untersucht, ob die Aufrufe schlecht oder gut sind, sondern ob der Anruf über HTTP verbunden ist.

![Screenshot des Berichts über Audiodatenströme, die HTTP verwenden](media/qerguide-image-audiostreamswithhttp.png)

_Abbildung 28 – Audiodatenströme mit HTTP-Proxy-Nutzung_

##### <a name="analysis"></a>Analyse

Sie möchten möglichst wenig HTTP-Medienströme sehen. Wenn Sie Datenströme über Ihren Proxy laufen sehen, wenden Sie sich an Ihr Netzwerkteam, um sicherzustellen, dass die richtigen Ausschlüsse vorhanden sind, damit die Kunden direkt an die Teams oder die Mediensubnetze von Skype for Business Online weitergeleitet werden.

Wenn in Ihrer Organisation nur ein Internet-Proxy vorhanden ist, vergewissern Sie sich, dass die [Ausschlüsse für Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips) korrekt sind. Wenn in Ihrer Organisation mehrere Internet-Proxys konfiguriert sind, können Sie mit dem HTTP-Unterbericht isolieren, welches Gebäude oder Subnetz betroffen ist.

Für Organisationen, die den Proxy nicht umgehen können, stellen Sie sicher, dass der Skype for Business-Client so konfiguriert ist, dass er sich ordnungsgemäß anmeldet, wenn er sich hinter einem Proxy befindet, wie es im Artikel [Skype for Business sollte sich über einen Proxy-Server anmelden, anstatt eine direkte Verbindung zu versuchen](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin) beschrieben ist. 


#### <a name="http-proxy-investigations"></a>HTTP-Proxy-Untersuchungen

In diesem Bericht werden bestimmte Gebäude und Subnetze identifiziert, die zur HTTP-Nutzung beitragen.

> [!IMPORTANT]
> Wenn Sie eine gültige [Gebäudedatei ](#building-mapping) hochgeladen haben, können Sie bei der Analyse der Proxy-Nutzung ganz einfach zwischen internen und externen Audiodatenströmen unterscheiden.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Filter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.

![Screenshot des Berichts über die HTTP-Proxy-Nutzung nach Gebäude und Subnetz](media/qerguide-image-httpproxyusage.png)

_Abbildung 29 – HTTP-Proxy-Nutzung nach Gebäude und Subnetz_

##### <a name="remediation"></a>Fehlerbehebung

Wir [empfehlen](proxy-servers-for-skype-for-business-online.md), dass Sie die Proxys für Skype for Business und Teams immer umgehen, insbesondere für Mediendatenverkehr. Da der Datenverkehr bereits verschlüsselt ist, wird Skype for Business durch Proxys nicht sicherer. Leistungsbezogene Probleme können durch Latenz und Paketverluste in die Umgebung eingebracht werden. Solche Probleme führen zu einer negativen Erfahrung mit Audio, Video und Bildschirmfreigaben, in denen Echtzeitdatenströme unerlässlich sind.

Die häufigste Ursache für die HTTP-Nutzung sind fehlende Ausnahmeregeln in Proxys. Wenn Sie das bereitgestellte Gebäude oder Subnetz verwenden, können Sie schnell ermitteln, welcher Proxy für die Medienumgehung konfiguriert werden muss.

Überprüfen Sie, ob die erforderlichen [Office 365 FQDNs](https://aka.ms/o365ips) in Ihrem Proxy in der Genehmigungsliste enthalten sind.

## <a name="endpoint-investigations"></a>Endpunktuntersuchungen

In diesem Abschnitt geht es um die Aufgaben für die Berichterstattung über Client-Versionen und die Verwendung zertifizierter Geräte. Es stehen Berichte zur Verfügung, die die Verwendung für Clientversionen, den Clienttyp, Erfassungsgeräte und Treiber (Mikrofon), Videoerfassungsgeräte und WLAN-Anbieter- und Treiberversionen umreißen.

> [!NOTE]
> In diesem Leitfaden werden nicht alle in den Vorlagen enthaltenen Berichte behandelt. Die nachstehend erläuterten Methoden für die Untersuchung gelten jedoch weiterhin. Weitere Informationen finden Sie in der Beschreibung des jeweiligen Berichts.

### <a name="client-versions"></a>Clientversionen

In den Berichten in diesem Bereich liegt der Schwerpunkt auf der Identifizierung der verwendeten Skype for Business-Clientversionen und deren relative Volumen in der Umgebung.

> [!IMPORTANT]
> Derzeit werden Teams-Clients automatisch über das Azure Content Delivery Network verteilt und aktualisiert und vom Dienst auf dem neuesten Stand gehalten. Client-Bereitschaft und Ermittlungsaktivitäten sind nicht für Teams anwendbar.

> [!Important]
> Sofern Sie keine Verbunddaten über die Teilnehmer ausschließen, umfassen diese Berichte die Clienttelemetrie von verbundenen Endpunkten. Um Verbundendpunkte auszuschließen, müssen Sie der [Mandanten-ID](#tenant-id) Ihrer Organisation einen [Abfragefilter](#query-filters) für die zweite Mandanten-ID hinzufügen. Alternativ können Sie einen [URL-Filter](#url-filter) verwenden, um die Telemetrie des Verbundteilnehmers auszuschließen.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Filter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.

![Screenshot des Berichts „Client und Geräte“](media/qerguide-image-clientversionreport.png)

_Abbildung 30 – Bericht "Clientversion"_

#### <a name="remediation"></a>Fehlerbehebung

Ein wichtiger Teil der Gewährleistung einer qualitativ hochwertigen Benutzererfahrung besteht darin, sicherzustellen, dass die verwalteten Clients aktuelle Versionen von Skype for Business ausführen und dass die unterstützenden Audio-, Video-, Netzwerk- und USB-Treiber auf dem neuesten Stand sind. Das bietet verschiedene Vorteile, einschließlich: 

-   Es ist einfacher, wenige Versionen im Vergleich zu vielen Versionen zu verwalten.
-   Dadurch wird eine gewisse Konsistenz der Benutzererfahrungen erreicht.
-   Dies erleichtert die Fehlersuche bei Problemen mit der Qualität von Anrufen und der Benutzerfreundlichkeit.
-   Microsoft führt kontinuierlich allgemeine Verbesserungen und Optimierungen im gesamten Produkt durch. Wenn Sie sicherstellen, dass Benutzer diese Updates erhalten, verringert sich das Risiko, dass ein bereits behobenes Problem auftritt.

Durch Einschränken ihrer Bereitstellung auf Clientversionen, die weniger als sechs Monate alt sind, können Sie die allgemeine Benutzererfahrung und die Verwaltbarkeit verbessern, indem Sie die Anzahl der unterstützten Versionen verringern.

Wenn Sie nur Office Klick-und-Los verwenden, befinden Sie sich automatisch innerhalb des sechsmonatigen Fensters. Es sind keine weiteren Schritte erforderlich.

Wenn Sie über eine Kombination aus Klick-und-Los und Installationspaketen (MSI) verfügen, können Sie den Bericht verwenden, um zu überprüfen, ob die MSI-Clients regelmäßig aktualisiert werden. Wenn Sie feststellen, dass die Clients älter als empfohlen sind, arbeiten Sie mit dem Team zusammen, das für die Verwaltung von Office-Updates zuständig ist, und stellen Sie sicher, dass Clientupdates regelmäßig genehmigt und bereitgestellt werden.

Außerdem ist es wichtig, zu bedenken, dass auch Netzwerk-, Video-, USB- und Audiotreiber gepatcht werden. Diese Treiber können leicht übersehen und dadruch nicht in Ihre Patch-Verwaltungsstrategie einbezogen werden.

Die Versionsnummern für Skype for Business finden Sie über die folgenden Links:

-   [Versionsinformationen zu Updates für Office ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Updateverlauf für Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Skype for Business – Downloads und Updates](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Geräte

Um den Bericht über das Mikrofongerät nutzen zu können, müssen wir das Konzept des Mean Opinion Score (MOS) verstehen. MOS ist die wichtigste Norm zur Messung der empfundenen Tonqualität. Er wird als ganze Zahl von 0 bis 5 dargestellt.

Die Grundlage aller Messungen der Sprachqualität ist die Art und Weise, wie eine Person die Sprachqualität wahrnimmt. Weil sie von der menschlichen Wahrnehmung beeinflusst wird, ist sie inhärent subjektiv. Es gibt mehrere unterschiedliche Methoden für die subjektive Prüfung. Die meisten Messungen für die VoIP-Qualität basieren auf einer ACR (Absolute Categorization Rating, d.h. Absolute Kategorisierungsbewertung).

Bei einer subjektiven ACR-Prüfung bewertet eine statistisch signifikante Anzahl von Personen ihre Erlebnisqualität auf einer Skala von 1 (schlecht) bis 5 (ausgezeichnet). Der Mittelwert der Ergebnisse ist der MOS. Der resultierende MOS hängt von der Reichweite der Erfahrungen ab, die der Gruppe ausgesetzt waren, und von der Art der Erfahrung, die bewertet wird.

Da es nicht praktikabel ist, subjektive Tests der Sprachqualität für ein Live-Kommunikationssystem durchzuführen, generieren Microsoft Teams und Skype for Business MOS-Werte mit erweiterten Algorithmen, um die Ergebnisse eines subjektiven Tests objektiv vorherzusagen.

Der verfügbare Satz von MOS- und zugehörigen Metriken bietet einen Einblick in die Qualität der Benutzererfahrung, die von einem Audiogerät an die Benutzer gesendet wird. 

Indem Sie den Benutzern Geräte zur Verfügung stellen, die für Teams und Skype for Business zertifiziert sind, verringern Sie die Wahrscheinlichkeit negativer Erfahrungen, die auf das Gerät selbst zurückzuführen sind (was z. B. bei eingebauten Laptop-Lautsprechern und Mikrofonen wahrscheinlicher ist). Weitere Informationen finden Sie in diesen Artikeln über das [Zertifizierungsprogramm](/SkypeForBusiness/certification/overview) und den [Katalog der Partnerlösungen](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Die Geräteberichte werden verwendet, um die Gerätenutzung nach Volumen und MOS-Bewertung (nur Audio) zu bewerten, und sie sind in den zugehörigen Vorlagen unter Clients & Geräte zu finden. 

> [!IMPORTANT]
> Sofern Sie keine Verbunddaten über die Teilnehmer ausschließen, umfassen diese Berichte die Clienttelemetrie von verbundenen Endpunkten. Um Verbundendpunkte auszuschließen, müssen Sie der [Mandanten-ID](#tenant-id) Ihrer Organisation einen **Abfragefilter** für die zweite Mandanten-ID hinzufügen. Alternativ können Sie einen [URL-Filter](#url-filter) verwenden, um die Telemetrie des Verbundteilnehmers auszuschließen.

> [!NOTE] 
> Stellen Sie sicher, dass Sie den Filter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.

> [!Note]
> Möglicherweise bemerken Sie beim Anzeigen dieses Berichts, dass das gleiche Gerät mehrmals gemeldet wurde. Dies ist auf die Art und Weise zurückzuführen, wie das Gerät an das CQD gemeldet wird. Unterschiede in der Hardware und im Betriebssystem-Gebietsschema führen zu Unterschieden in der Art und Weise, wie Gerätedaten gemeldet werden.

![Screenshot des Berichts "Geräte (Mikrofon)"](media/qerguide-image-devicesmicrophone.png)

_Abbildung 31 – Bericht "Geräte (Mikrofon)"_

##### <a name="remediation"></a>Fehlerbehebung

Normalerweise müssen Sie die nicht zertifizierten Geräte finden und ausrangieren und durch zertifizierte Geräte ersetzen. Einige Überlegungen bei der Überprüfung der Geräteberichte umfassen:

-   Sind die verwendeten Geräte für Teams und Skype for Business zertifiziert? 
-   Sie können Benutzer eines bestimmten Geräts mithilfe von [Anrufanalyse](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) identifizieren. Vergewissern Sie sich, dass die Benutzer über die neuesten Gerätetreiber verfügen und dass ihr Gerät nicht über einen USB-Hub oder eine Dockingstation verbunden ist. 
-   Wie viele verschiedene Versionen unterschiedlicher Treiber werden verwendet? Werden diese regelmäßig gepatcht? Wenn Sie sicherstellen, dass Audio-, Video- und WLAN-Treiber regelmäßig gepatcht werden, können Sie diese als Quelle für Qualitätsprobleme ausschließen und die Benutzererfahrung vorhersehbarer und konsistenter machen.

##### <a name="audio"></a>Audio

Die nächste Aufgabe besteht darin, die allgemeine Nutzung von [zertifizierten Audiogeräten](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) zu ermitteln. Wir empfehlen, dass mindestens 80 Prozent aller Audiodatenströme über ein zertifiziertes Audiogerät erfolgen. Dazu exportieren Sie den Bericht "Mikrofongeräte" nach Excel, um die Verwendung von zertifizierten oder zugelassenen Geräten zu berechnen. Die Organisationen führen in der Regel eine Liste aller zugelassenen Geräte aus, daher sollten Sie die Daten ohne Weiteres filtern und sortieren können.

##### <a name="video"></a>Video

Außerdem ist es wichtig, dass Videotreiber aktualisiert werden. Wenn Sie sicherstellen, dass Videokarten regelmäßig gepatcht werden, können Sie die Videotreiber als Quelle schlechter Qualität für Videodatenströme ausschließen. Die Verwendung [zertifizierter Videogeräte](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) trägt dazu bei, eine reibungslose und qualitativ hochwertige Benutzererfahrung zu gewährleisten. Videogeräte, die die native Codierung von H.264 unterstützen, werden bevorzugt, um die CPU-Auslastung während Videokonferenzen zu verringern.

##### <a name="wi-fi"></a>WLAN

Außerdem müssen die WLAN-Treiber in regelmäßigen Abständen gepatcht werden und sollten in Ihre Patch-Verwaltungsstrategie einbezogen werden. Viele Qualitätsprobleme lassen sich beheben, indem Sie die WLAN-Treiber auf dem neusten Stand halten. Weitere Informationen zur Optimierung Ihrer WLAN-Infrastruktur finden Sie [in diesem Artikel über die WLAN-Planung](/skypeforbusiness/certification/networking-wifi).

## <a name="appendix"></a>Anhang 

### <a name="office-365-network-connectivity-principles"></a>Prinzipien von Office 365-Netzwerkverbindungen

Bevor Sie mit der Planung Ihres Netzwerks für die Office 365-Netzwerkkonnektivität beginnen, ist es wichtig, dass Sie sich mit den Prinzipien von Verbindungen für die sichere Verwaltung von Office 365-Datenverkehr und optimaler Leistung vertraut machen. Der folgende Artikel hilft Ihnen, die neuesten Hinweise für die sichere Optimierung der Office 365-Netzwerkkonnektivität zu verstehen:

[Prinzipien von Office 365-Netzwerkverbindungen](https://aka.ms/pnc)

### <a name="planning-for-wi-fi"></a>Planen für WLAN

Die Vorgehensweise von Microsoft zur Förderung der Qualität und Flexibilität in den Drahtlosnetzwerken besteht aus drei Teilen: umfassende Planung, bewährte Methoden für die Bereitstellung und proaktive Wartung und Betrieb. Diese Lösungsübersicht führt Sie durch diesen Vorgang, um eine Skype for Business-Erfahrung der Unternehmensklasse im WLAN zu gewährleisten:

[Sicherstellen einer Skype for Business-Erfahrung der Unternehmensklasse im WLAN](https://www.microsoft.com/download/details.aspx?id=47257)

### <a name="lync-networking-guide"></a>Lync-Netzwerkleitfaden

Für weitere Hintergrundinformationen zu den Netzwerkkonzepten von Teams und Skype for Business und den Gründen für ihren Stellenwert für die Qualität ist der [Lync Server 2013 Netzwerkleitfaden](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) weiterhin anwendbar.

### <a name="network-performance-requirements"></a>Anforderungen an die Netzwerkleistung

Die Qualität der End-to-End-Netzwerkkonnektivität hat großen Einfluss auf die Qualität von Echtzeitmedien (Audio, Video und Anwendungsfreigabe) über IP. Für eine optimale Medienqualität für Teams oder Skype for Business muss Ihr Netzwerk die folgenden Netzwerkleistungskennzahlen erfüllen.

_Tabelle 12 – Anforderungen an die Netzwerkleistung_

| Metrik                            | Vom Client zum Edge von Microsoft           | Vom Kundenedge zum Edge von Microsoft    |
|-----------------------------------|------------------------------------|------------------------------------|
| Latenz (unidirektional)                 | \<50 ms                            | \<30 ms                            |
| Latenz (Roundtripzeit oder RTT) | \<100 ms                           | \<60 ms                            |
| Burstverlust von Paketen                 | \<10 % in einem Intervall von 200 ms   | \<1 % in einem Intervall von 200 ms    |
| Paketverlust                       | \<1 % in einem Intervall von 15 s    | \<0.1 % in einem Intervall von 15 s  |
| Jitter zwischen der Ankunftszeit von Paketen       | \<30 ms in einem Intervall von 15 s | \<15 ms in einem Intervall von 15 s |
| Neuanordnung von Paketen                    | \<0,05 % Pakete in falscher Reihenfolge       | \< 0,01 % Pakete in falscher Reihenfolge      |

Weitere Informationen finden Sie [in diesem Artikel über die Medienqualität und Leistung der Netzwerkkonnektivität](https://aka.ms/performancerequirements) in Teams und Skype for Business Online.

### <a name="other-resources"></a>Sonstige Ressourcen

#### <a name="building-data-file"></a>Gebäudedatendatei

-   [Aktivieren und Verwenden des Dashboards zur Anrufqualität in Microsoft Teams und Skype for Business Online](turning-on-and-using-call-quality-dashboard.md)

#### <a name="cqd-training"></a>CQD-Schulung

-   <https://aka.ms/sof-cqd>

-   [Erste Schritte mit CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) – Leitfaden und Workshop

-   [Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](https://aka.ms/cqd-dm)

### <a name="call-analytics-training"></a>Anrufanalyse – Schulung

-   [Einführung in die Anrufanalyse](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Einrichten von Anrufanalyse](set-up-call-analytics.md)

-   [Woran bestehen die Unterschiede zwischen der Anrufanalyse und dem Anrufqualitäts-Dashboard?](difference-between-call-analytics-and-call-quality-dashboard.md)

-   [Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

### <a name="call-analytics-support"></a>Anrufanalyse – Support

-   Community: [Skype for Business Vorschauprogramm](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

### <a name="devices"></a>Geräte

-   [Skype for Business – Lösungenkatalog der persönlichen Peripheriegeräte und PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Mandantenberichterstattung

-   [Inhaltspakets zur Einführung von Office 365](https://www.microsoft.com/microsoft-365/blog/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Analysen zur Anwendung von Microsoft 365](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)

-   [Skype for Business Online-Berichterstellung](/SkypeForBusiness/skype-for-business-online-reporting/skype-for-business-online-reporting)

-   [Microsoft Teams – Berichterstattung](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
 
