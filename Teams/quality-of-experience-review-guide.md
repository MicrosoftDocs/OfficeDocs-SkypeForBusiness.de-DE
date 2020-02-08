---
title: Leitfaden zur Überprüfung der Qualität der Umgebung für Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: siunies
audience: admin
description: Leitfaden zur Analyse der Echt Zeit Medien Leistung für Microsoft Teams mithilfe des Anruf Qualitäts Dashboards (CQD).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e11c7d479aeac6eef39fb38588a61c0c7be25a6
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863396"
---
# <a name="quality-of-experience-review-guide"></a>Handbuch für die Überprüfung der QoE (Quality of Experience)

<!-- Note that this link to the Word doc is intentionally NOT the aka.ms/qerquide link -->
In diesem Leitfaden geht es um die Antriebs Wert Phase für Microsoft Teams und Skype for Business Online. Sie können [eine Word-Version](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) dieses Handbuchs herunterladen.

## <a name="introduction"></a>Einführung

Um die größten Auswirkungen auf die Verbesserung der Benutzerfreundlichkeit zu haben, müssen Unternehmen die wichtigsten Bereiche, die in der folgenden Abbildung gezeigt werden, operativisieren. Zu den weiteren Bereichen zählen das Identifizieren von operativen Aufgaben, das Festlegen von Zielen für Qualitäts Metriken, das Ermitteln der Metriken zum Messen des organisatorischen Erfolgs sowie das Einschränken von Ermittlungs Bereichen nach Bedarf.


![Wichtige Bereiche für die Qualität der Benutzerfreundlichkeit](media/qerguide-image-keyareas.png "Die wichtigsten Bereiche für die Qualität der Benutzererfahrung sind Audio, Zuverlässigkeit, Benutzer Umfragen, Geräte und Clients.")

_Abbildung 1: wichtige operative Bereiche, die in diesem Leitfaden behandelt werden_

Indem Sie die in diesem Leitfaden beschriebenen Bereiche kontinuierlich bewerten und umsetzen, können Sie deren Potenzial verringern, die Qualität der Benutzererfahrung negativ zu beeinflussen. Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:

-   Unvollständige Firewall- oder Proxykonfiguration
-   Schlechte WLAN-Abdeckung
-   Unzureichende Bandbreite
-   VPN
-   Inkonsistente oder veraltete Clientversionen und Treiber
-   Nicht optimierte oder integrierte Audiogeräte
-   Problematische Subnetze oder Netzwerkgeräte

Durch die ordnungsgemäße Planung und Konzeption vor der Bereitstellung von Teams oder Skype for Business Online können Sie den Aufwand verringern, der erforderlich ist, um qualitativ hochwertige Erfahrungen zu erhalten.

Dieser Leitfaden konzentriert sich auf die Verwendung des Anruf Qualitäts Dashboards (CQD) online als primäres Tool für die Berichterstellung und Untersuchung der einzelnen Bereiche mit besonderem Augenmerk auf Audio, um die Akzeptanz und die Auswirkungen zu maximieren. Alle Verbesserungen am Netzwerk zur Verbesserung der Audioqualität werden auch direkt zu Verbesserungen bei der Video-und Desktopfreigabe übertragen.

Um Ihre Einschätzung zu beschleunigen, werden [zwei kuratierte CQD-Vorlagen](https://aka.ms/qertemplates) bereitgestellt: eine dient zum Verwalten aller Netzwerke, und die andere ist nur für verwaltete (interne) Netzwerke gefiltert. Obwohl die Berichte "alle Netzwerke" so konfiguriert sind, dass Sie Gebäude-und Netzwerkinformationen anzeigen, können Sie weiterhin verwendet werden, während Sie auf das Sammeln und Hochladen von Gebäudeinformationen hinarbeiten. Durch das Hochladen von Gebäudeinformationen in CQD kann der Dienst die Berichterstellung verbessern, indem benutzerdefinierte Gebäude-, Netzwerk-und Standortinformationen hinzugefügt werden, während interne von externen Subnetzen unterschieden werden Weitere Informationen finden Sie unter [Erstellen einer Zuordnung](#building-mapping) weiter unten in diesem Leitfaden.

### <a name="intended-audience"></a>Beabsichtigte Zielgruppe

Dieser Leitfaden soll von Partner-und Kundeninteressen Gruppen mit Rollen wie der Zusammenarbeit Lead/Architekt, Berater, Change Management/Adoptions Spezialist, Support/Help-Desk-Lead, Netzwerk Leiter, Desktop Lead und IT-Administrator verwendet werden.

Dieser Leitfaden ist auch für die Verwendung durch die Designated Quality Champion (s) vorgesehen. Weitere Informationen finden Sie in [der Rolle "Quality Champion"](4-envision-plan-my-service-management.md#the-quality-champion-role).

## <a name="assign-roles-for-accessing-cqd"></a>Zuweisen von Rollen für den Zugriff auf CQD

Bevor Sie dieses Handbuch verwenden, stellen Sie sicher, dass Sie die richtigen Mandanten [Rollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) zugewiesen haben, damit Sie auf CQD zugreifen können.

Diese Tabelle zeigt Ihnen, was jede Rolle in CQD tun kann:


|  |Anzeigen von Berichten  |Anzeigen von EUII-Feldern  |Erstellen von Berichten  |Hochladen von Gebäudedaten  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Office 365-globaler Administrator     |Ja          |Ja          |Ja          |Ja          |
|Teams-Dienstadministrator     |Ja          |Ja          |Ja          |Ja          |
|Teams-Kommunikationsadministrator     |Ja          |Ja          |Ja          |Ja          |
|Teams-Kommunikationssupporttechniker     |Ja          |Ja          |Ja         |Nein         |
|Supportfachmann für die Teams-Kommunikation     |Ja         |Nein         |Ja         |Nein         |
|Skype for Business-Administrator     |Ja          |Ja          |Ja          |Ja          |
|Azure AD-globaler Reader |Ja          |Ja          |Ja         |Nein         |
|Office 365-berichtsleser<sup>1</sup>     |Ja         |Nein         |Ja         |Nein         |

<sup>1</sup> neben dem Lesen von CQD-Berichten kann der Office 365-berichtsleser alle [Aktivitätsberichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Admin Center sowie alle Berichte des [Microsoft 365-Inhaltspakets zur Einführung](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)anzeigen.

> [!NOTE]
> Wenn Sie EUII (Endbenutzer-identifizierbare Informationen) nicht sehen und über eine der Rollen verfügen, die diese Informationen anzeigen dürfen, sollten Sie beachten, dass CQD nur 30 Tage lang EUII. Alle Elemente, die älter als 30 Tage sind, werden gelöscht.

## <a name="what-is-quality"></a>Was ist Qualität?

Bei der Besprechung von Qualität in Teams und Skype for Business ist es wichtig, den Begriff zu definieren, um ein gemeinsames Verständnis zu erreichen. Qualität, wie hier definiert, ist eine Kombination aus Dienst Metriken und Benutzerfreundlichkeit.

<!-- Note: need to update graphic-->
![Abbildung von Dienst Metriken und der Benutzeroberfläche](media/qerguide-image-whatisquality.png "Dienst Metriken bestehen aus unzureichendem Datenstrom Verhältnis, Zuverlässigkeit, Endpunkten/Geräten und Clientversionen. Die Benutzererfahrung besteht aus der Einschätzung des Benutzers zur Qualität des Diensts.")

_Abbildung 2: Was ist Qualität?_

### <a name="service-metrics"></a>Dienst Metriken

Dienst Metriken bestehen aus bestimmten clientbasierten Metriken. Bei jedem Anruf sammelt der Client Telemetrie-Informationen über den Anruf und übermittelt einen Bericht am Ende jedes Anrufs, auf den später über CQD oder [Call Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)zugegriffen werden kann. Zu diesen Metriken zählen:

-   Schlechte Datenstrom Rate
-   Setup-Fehler Rate
-   Abwurf Fehler Rate


#### <a name="poor-stream-rate"></a>Schlechte Datenstrom Rate

Die schlechte Datenstrom Rate (PSR) steht für den Gesamtanteil der Organisation an Datenströmen, die eine schlechte Qualität aufweisen. Diese Metrik dient zum Hervorheben von Bereichen, in denen Ihre Organisation die Anstrengungen konzentrieren kann, um die stärksten Auswirkungen auf die Verringerung dieses Werts und die Verbesserung der Benutzerfreundlichkeit zu haben, weshalb [verwaltete Netzwerke](#managed-vs-unmanaged-networks) beim Betrachten von PSR den primären Schwerpunkt darstellen. Externe Benutzer sind ebenfalls wichtig, die Untersuchung ist jedoch auf organisatorischer Grundlage unterschiedlich. Sie sollten bewährte Methoden für externe Benutzer bereitstellen und externe Anrufe unabhängig von der gesamten Organisation untersuchen.

Die tatsächliche Messung in CQD variiert je nach Arbeitsauslastung, aber für die Zwecke der Überprüfung der Qualitätserfahrung konzentrieren wir uns in erster Linie auf die schlechte Messung des _Audiosignals_ . PSR besteht aus den fünf in der folgenden Tabelle beschriebenen Netzwerk metrischen Mittelwerten. Damit ein Stream als "schlecht" klassifiziert werden kann, muss nur eine Metrik den definierten Schwellenwert überschreiten. Weitere Informationen zum Stream-Klassifizierungsprozess finden Sie in [diesem Artikel](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> CQD bietet das "schlechte wegen..." Messungen, um besser zu verstehen, welche Bedingung dazu führte, dass der Datenstrom als "schlecht" klassifiziert wurde.


_Tabelle 1 – Metriken für schlechte Tonqualität_

| Metrischer Mittelwert     | Beschreibung     | Benutzererfahrung |
|-------------|-----------------|-----------------|
| Jitter \>30 ms        | Dies ist die durchschnittliche Verzögerungs Änderung zwischen aufeinanderfolgenden Paketen. Teams und Skype for Business können sich durch Pufferung an einige Ebenen des Jitters anpassen. Dies ist nur der Fall, wenn der Jitter die Pufferzeit überschreitet, die ein Teilnehmer über die Auswirkungen von Jitter bemerkt.      | Die Pakete, die mit unterschiedlichen Geschwindigkeiten ankommen, führen dazu, dass die Stimme eines Sprechers robotisch klingt.   |
| Paketverlustrate \>10% oder 0,1        | Dies wird häufig als Prozentsatz der verloren gegangenen Pakete definiert. Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen auf Burst Verluste haben, die dazu führen, dass Audiodaten vollständig ausgeschnitten werden.     | Die Pakete, die gelöscht werden und nicht am vorgesehenen Zielort ankommen, führen zu Lücken in den Medien, was zu fehlenden Silben und Wörtern sowie abgehackten Video-und Freigabe Problemen führt. |
| Round-Trip- \>Zeit 500 ms        | Dies ist die Zeit, die erforderlich ist, um ein IP-Paket von Punkt a nach Punkt B und zurück zu Punkt a zu erhalten. Diese Verzögerung der Netzwerk Propagierung ist an den physikalischen Abstand zwischen den beiden Punkten und der Lichtgeschwindigkeit gebunden und umfasst zusätzlichen Overhead, der von den verschiedenen Geräten im Netzwerkpfad übernommen wird.      | Die Pakete, die zu lange dauern, bis Sie am Zielort ankommen, führen zu einem Walkie-Talkie-Effekt.   |
| NMOS-Degradations Durchschnitt \>1,0         | Durchschnittlicher [Netzwerk-Mittelwert (NMOS)-](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) Verschlechterung des Datenstroms. Gibt an, wie viel Netzwerk Verlust und Jitter die Qualität der empfangenen Audiodaten beeinträchtigt haben, die dazu geführt haben, dass der NMOS um mehr als einen Punkt abfällt. | Hierbei handelt es sich um eine Kombination aus Jitter, Paketverlust und – in geringerem Maße – erhöhter Roundtrip-Zeit. Der Benutzer kann eine Kombination dieser Symptome erleben.   |
| Durchschnittliches Verhältnis der verborgenen \>Samples 7% oder 0,07 | Durchschnittliches Verhältnis der Anzahl von Audioframes mit verborgenen Samples, die durch Paketverlust-Heilung an die Gesamtzahl der Audioframes generiert wurden. Ein verborgenes Audiobeispiel ist eine Technik, die verwendet wird, um den abrupten Übergang zu glätten, der in der Regel durch verworfene Netzwerkpakete verursacht wurde.      | Hohe Werte deuten darauf hin, dass ein erhebliches Maß an Verlust Verschleierung angewendet wurde und zu verzerrten oder verlorenen Audiodaten geführt hat.     |

#### <a name="setup-failure-rate"></a>Setup-Fehler Rate

Die Setup-Fehlerrate, auch bekannt als _Gesamtfehler Prozentsatz des Anruf Setups_ in CQD, ist die Anzahl der Datenströme, bei denen der Medienpfad zwischen den Endpunkten am Anfang des Anrufs nicht hergestellt werden konnte.

Dies stellt einen beliebigen Mediendatenstrom dar, der nicht hergestellt werden konnte. Angesichts des Schweregrads der Auswirkungen auf die hier gemessene Benutzererfahrung besteht das Ziel darin, diesen Wert so zu verringern, dass er so nahe wie möglich NULL ist. Ein höherer Wert für diese Metrik ist in neuen Bereitstellungen mit unvollständigen Firewallregeln häufiger als eine ausgereifte Bereitstellung, aber es ist immer noch wichtig, dass Sie regelmäßig überwacht werden.

Diese Metrik wird berechnet, indem die Gesamtanzahl der Streams, die nicht eingerichtet wurden, dividiert durch die Gesamtzahl der Datenströme, die einen erfolgreichen Anruf Detaildatensatz (CDR) übermittelt haben:

-   **Setup-Fehler Rate** = Gesamt Anrufeinrichtung fehlgeschlagen Datenstromanzahl/Gesamtanzahl der verfügbaren Datenströme für CDR

#### <a name="drop-failure-rate"></a>Abwurf Fehler Rate

Die Drop-Failure-Rate, auch bekannt als _Gesamt-Fehlerprozentsatz_ in CQD, ist der Prozentsatz der erfolgreich festgelegten Datenströme, bei denen der Medienpfad nicht normal beendet wurde.

Dies stellt einen Mediendatenstrom dar, der unerwartet beendet wurde. Auch wenn dies nicht so schwerwiegend ist wie ein Datenstrom, der nicht eingerichtet werden konnte, wirkt sich dies negativ auf die Benutzeroberfläche aus. Plötzliche und häufige Medien Abbrüche können nicht nur schwerwiegende Auswirkungen auf die Benutzeroberfläche haben, sondern auch dazu führen, dass die Benutzer die Verbindung wiederherstellen müssen, was zu einem Produktivitätsverlust führt.

Die Metrik wird berechnet, indem die Gesamtanzahl der verworfenen Datenströme dividiert durch die Gesamtanzahl der Datenströme, die erfolgreich eingerichtet wurden:

-   **Drop Failure Rate** = Gesamt Anruf sank Datenstromanzahl/Gesamt Anruf-Setup erfolgreich Datenstromanzahl

### <a name="define-your-target-metrics"></a>Definieren der Zielmetrik

In diesem Abschnitt werden einige der wichtigsten Dienst Metriken erläutert, mit denen wir beurteilen können, wie Dienste die Integrität erfahren. Indem Sie die Anstrengungen kontinuierlich bewerten und vorantreiben, um diese Metriken unter den definierten Zielen zu halten, können Sie sicherstellen, dass Ihre Benutzer konsistente, zuverlässige Anrufqualität erzielen. Um Ihnen den Einstieg zu verschaffen, stehen die folgenden Ziele zur Verfügung.

_Tabelle 2: grundlegende Kriterien für die Bewertung der Ziel Integrität_
<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Netzwerktyp</th><th rowspan="1">Qualitätsziele</th><th colspan="2">Zuverlässigkeits Ziele</th></tr>
<tr><th>Schlechte audioübertragungs Rate</th><th>Setup-Fehler Rate</th><th>Abwurf Fehler Rate</th></tr>
<tr><td rowspan="2"><strong>Alle</strong></td><td>Intern</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Gesamt</td><td>3,0%</td><td>1,0%</td><td>3,0%</td></tr>
<tr><td rowspan="5"><strong>Konferenzen</strong></td><td>Intern</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Intern verdrahtet</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wi-Fi 5 GHz intern</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wi-Fi 2,4 GHz intern</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Gesamt</td><td>2,0%</td><td>0,5%</td><td>3,0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Intern</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Verkabelt/Wi-Fi 5 GHz intern</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wired/Wi-Fi 5 GHz Gesamt</td><td>2,0%</td><td>1,0%</td><td>1,0%</td></tr>
<tr><td>Gesamt</td><td>2,0%</td><td>1,0%</td><td>3,0%</td></tr>
</table>


Es ist wichtig, die Ziele Ihrer Organisation zu besprechen und zu definieren, um Ihre geschäftlichen Ziele zu erreichen.

### <a name="user-experience"></a>Benutzererfahrung

Die Analyse der Benutzererfahrung ist mehr Kunst als Wissenschaft, da die hier versammelten Metriken nicht immer bedeuten, dass es ein Problem mit dem Netzwerk oder dem Dienst gibt, sondern vielmehr, dass Sie einfach angeben, dass der Benutzer ein Problem wahrnimmt. Microsoft bietet einen integrierten Umfrage Mechanismus, der als "Rate My Call (RMA)" bezeichnet wird, um die allgemeine Benutzerfreundlichkeit zu ermitteln. Mithilfe von RMA können Sie die folgenden Fragen aus der Perspektive ihrer Nutzer beantworten:

-   Weiß ich, wie ich die Lösung nutzen kann?
-   Ist die Lösung einfach zu verwenden und intuitiv und unterstützt Sie meine täglichen Kommunikationsanforderungen?
-   Hilft mir die Lösung dabei, meine Arbeit zu erledigen?
-   Was ist meine Gesamtvorstellung von der Lösung?
-   Kann ich die Lösung zu einem beliebigen Zeitpunkt verwenden, unabhängig davon, wo ich bin?
-   Kann ich einen Anruf einrichten und verwalten?

#### <a name="rate-my-call"></a>Meinen Anruf abstimmen 

"Mein Anruf abstimmen" (RMA) ist in Teams und Skype for Business integriert und wird automatisch so konfiguriert, dass Sie dem Teilnehmer nach einem von 10 anrufen oder 10 Prozent angezeigt werden. Diese kurze Umfrage fordert den Benutzer auf, den Anruf zu veranschlagen und einen kleinen Zusammenhang zu liefern, warum die Anrufqualität schlecht gewesen sein könnte. Ein oder zwei Bewertungen gelten als schlecht, drei bis vier sind gut und fünf sind hervorragend. Obwohl es sich um eine gewisse Verzögerungs Anzeige handelt, handelt es sich um eine hilfreiche Metrik zur aufdecken von Problemen, die Dienst Metriken verpassen können.

> [!Note]
> Bis die Benutzer zum Antworten auf die RMA-Umfragen ausgebildet sind, indem Sie neben "schlecht" ein gutes Feedback geben, kommen Antworten in der Regel als überwiegend negativ zurück. Die meisten Benutzer reagieren nur, wenn die Anrufqualität schlecht ist. Aus diesem Grund sind Ihre RMA-Berichte möglicherweise auf die schlechte Seite geneigt, auch wenn die Dienst Metrik gut ist.

Sie können CQD verwenden, um über RMA-Benutzer Antworten zu berichten, und Beispielberichte sind in der CQD-Vorlage enthalten. In diesem Leitfaden werden Sie jedoch nicht ausführlich erläutert. Weitere Informationen zu "RMA" in Skype for Business Online und Anleitungen für die Schulung von Benutzern, um nützliche Antworten auf die RMA zu erhalten, finden Sie in [diesem Blogbeitrag](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

#### <a name="client-and-device-readiness"></a>Client-und Geräte Bereitschaft

Sie benötigen eine solide Client-und Geräte Strategie, um sicherzustellen, dass Ihre Benutzer eine konsistente und positive Benutzererfahrung aufweisen. Die einzelnen Bereitschaftsstrategien werden durch einige wichtige Prinzipien vorangetrieben.

##### <a name="client-readiness"></a>Client Bereitschaft

Eine starke Client Readiness-Strategie stellt sicher, dass die Benutzer die neueste Version des Clients ausführen, während Sie die bestmögliche Nutzung genießen. Microsoft regelmäßig Patches für den Skype for Business-Client; sicherstellen, dass Sie es in Ihrer Umgebung auf dem neuesten Stand halten, ist für Ihren Gesamterfolg von entscheidender Bedeutung. Darüber hinaus ist es wichtig, Netzwerk-, Video-, USB-und Audiotreiber zu patchen, da diese häufig übersehen werden und die Benutzererfahrung beeinträchtigen können. Sie können Ihrem aktuellen Patchverwaltung-Prozessnetzwerk-, Wi-Fi-, Video-, USB-und Audiotreiber hinzufügen.

Wir empfehlen, dass Sie Ihre Clientversionen nicht mehr als sechs Monate zurücklegen können. Wenn Sie Office Klick-und-Los verwenden, werden Sie bereits vom Dienst auf dem neuesten Stand gehalten. Verwenden Sie die enthaltenen [Clientversionen](#client-versions)wie weiter unten in diesem Leitfaden beschrieben, um Sie bei diesem Prozess zu unterstützen. Sie können auch die Berichte für meine Anruf Rate nutzen, um die Strategie für die Client Bereitschaft weiter zu verbessern.

> [!IMPORTANT]
> Derzeit werden Teams-Clients automatisch über das Azure Content Delivery Network verteilt und aktualisiert und vom Dienst auf dem neuesten Stand gehalten. Aus diesem Grund gelten die Client Bereitschaft und Ermittlungsaktivitäten nicht für Teams.


##### <a name="device-readiness"></a>Geräte Bereitschaft

Keine einzige Strategie kann sich auf die Benutzererfahrung auswirken, als Ihre Geräte Bereitschafts Strategie. Die meisten Organisationen sind gerne bereit, unnötige Geräte (beispielsweise Telefonapparate oder andere dedizierte Audiogeräte) von Benutzern zu entfernen, und dies ist häufig eine grundlegende geschäftliche Berechtigung für den Wechsel zu Teams oder Skype for Business. Dieselben Organisationen zögern jedoch manchmal, Ersatzgeräte bereitzustellen, auch wenn diese Geräte günstiger sind. Moderne Laptops und PCs, die zwar mit integriertem Mikrofon und Lautsprecher ausgestattet sind, sind für VoIP (Business-Class Voice over IP) nicht optimiert. Dies führt oft zu einem schlechten Erlebnis für alle Teilnehmer, besonders, wenn sich der Lautsprecher in einer lauten Umgebung befindet. Das Geräte Zertifizierungsprogramm von Microsoft stellt sicher, dass ein Benutzer, der mit einem für Teams oder Skype for Business zertifizierten Gerät an einem Telefonanruf teilnimmt, eine Erfahrung herstellt, die einem nicht zertifizierten Gerät überlegen ist. 

Wir empfehlen immer, dass Teams und Skype for Business-Benutzer ein zertifiziertes Headset oder einen Lautsprecher verwenden, wenn Sie über den Desktop-Client an einem Sprachanruf teilnehmen. Weitere Informationen zu zertifizierten Microsoft-Geräten finden Sie in diesen Artikeln über das [Zertifizierungsprogramm](/SkypeForBusiness/certification/overview) und Anzeigen des [Partner Lösungskatalogs](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Verwenden Sie den weiter unten in diesem Leitfaden beschriebenen [gerätebericht](#devices), um Unterstützung bei der Verwaltung Ihrer Geräte zu erhalten.


### <a name="categories-of-quality"></a>Qualitätskategorien

Der Erfolg von Operationalisierung eine qualitativ hochwertige und zuverlässige Bereitstellung hängt von der operativen strenge des Gebäudes ab. Achten Sie insbesondere auf die drei Kategorien, die in der folgenden Abbildung dargestellt sind. Dies steht im Zentrum dieses Leitfadens:

-   **Netzwerk:** Die Audioqualität konzentriert sich auf das schlechte Datenstrom Verhältnis (PSR) Metrik, TCP-Nutzung, verdrahtete und drahtlose Subnetze sowie die Verwendung von HTTP-Proxys und VPN.

-   **Endpunkte:** Audiogeräte und Clientversionen (nur Skype for Business).

-   **Dienstverwaltung:** Diese Kategorie umfasst zwei Abschnitte:

    -   Zunächst ist Microsoft dafür verantwortlich, die Teams und Skype for Business Online-Dienste zu verwalten und zu verwalten.

    -   Zweitens sind Aufgaben, die Ihre Organisation verwalten muss, um einen zuverlässigen Zugriff auf den Dienst zu gewährleisten, beispielsweise das Aktualisieren von Gebäudeinformationen und das Verwalten von Firewalls für neue Office 365-IP-Adressen, wenn dem Dienstinfrastruktur hinzugefügt wird.

![Diagramm der Kategorien von Qualität in einer Organisation](media/qerguide-image-categories.png "Die Kategorien der Qualität in einer Organisation: Dienstverwaltung, Endpunkte und das Netzwerk.")

_Abbildung 3: kritische Kategorien für Teams und die Bereitstellung von Skype for Business Online_

Die folgende Grafik beschreibt die Aufgaben, die Sie für jede Kategorie ausführen müssen. Wir empfehlen, diese Aufgaben mindestens einmal pro Woche auszuführen.

Wenn Sie diese Aufgaben zum ersten Mal ausführen, benötigen Sie mehr Aufwand als nachfolgende Iterationen, da für viele dieser Kategorien die Überprüfung ihrer Bereitstellungskonfigurationen erforderlich ist. Nachdem Sie den gewünschten Zustand erreicht haben, indem Sie die von Ihnen festgelegten Ziele erfüllen, können Sie diesen Status durch Ausführen dieser Aufgaben beibehalten.

<!--  This is a net new graphic, never was included in the online article. OOPS! -->
![Liste der wöchentlichen Aufgaben pro Qualitätskategorie](media/qerguide-image-tasks.png "Liste der wöchentlichen Aufgaben pro Qualitätskategorie")

#### <a name="service-management-tasks"></a>Dienstverwaltungsaufgaben

In einer Cloud-First-Welt müssen Sie bestimmte Dienstverwaltungsaufgaben ausführen, um eine qualitativ hochwertige Benutzererfahrung zu gewährleisten. Diese Aufgaben reichen davon ab, sicherzustellen, dass genügend Bandbreite vorhanden ist, um den Dienst zu erreichen, ohne Internet-Links zu sättigen, zu überprüfen, ob QoS (Quality of Service) in allen verwalteten Netzwerkbereichen vorhanden ist, und – zuletzt – über die [IP-Bereiche von Office 365 auf Firewalls](https://aka.ms/o365ips)zu bleiben.

#### <a name="network-tasks"></a>Netzwerkaufgaben

Es gibt zwei Kategorien von Netzwerkaufgaben: Zuverlässigkeit und Qualität. Die Zuverlässigkeit konzentriert sich auf die Messung der Fähigkeit des Benutzers, Anrufe erfolgreich zu führen und in Verbindung zu bleiben. Die Qualität konzentriert sich auf die aggregierte Telemetrie, die vom Client des Benutzers während des Anrufs und nach dem Beenden an Teams und Skype for Business Online gesendet wurde. 

Angesichts der entscheidenden Auswirkungen, die die Zuverlässigkeit auf die Benutzeroberfläche hat, ist es wichtig, diese Metriken zu bewerten und zu untersuchen, bevor Sie in die Qualität eintauchen. 

#### <a name="endpoints-tasks"></a>Endpunkte-Aufgaben

Die wichtigste Aufgabe in dieser Kategorie besteht darin, zu überprüfen, welche Clientversionen in den letzten sechs Monaten in Skype for Business auf dem Desktop ausgeführt werden, um sicherzustellen, dass die Benutzer den Vorteil der kontinuierlichen Optimierungen des Skype for Business-Desktop Clients erhalten. Darüber hinaus werden dadurch die allgemeinen Client Verwaltungsaufgaben vereinfacht und eine konsistente Benutzeroberfläche bereitgestellt.

Der andere wichtige Bereich besteht darin, zu überwachen, welche Geräte in Ihrer Bereitstellung verbreitet sind, und die Verwendung zertifizierter Geräte zu steuern, um die optimale Benutzererfahrung bereitzustellen.


> [!IMPORTANT]
> Derzeit werden Teams-Clients automatisch über das Azure Content Delivery Network verteilt und aktualisiert und vom Dienst auf dem neuesten Stand gehalten. Client Bereitschaft und Ermittlungsaktivitäten gelten nicht für Teams.

## <a name="cqd-basics"></a>CQD-Grundlagen

In diesem Abschnitt werden die Grundlagen der Arbeit mit CQD beschrieben. Anleitungen zu den folgenden Themen:

-   Was ist CQD?
-   Erwartungen mit CQD
-   Auffinden Ihrer Mandanten-ID
-   Berichte zu Microsoft Teams im Vergleich zu Skype for Business
-   First-versus-Second-Klassifikationen
-   Dimensionen, Measures und Filter
-   Streams versus Anrufe
-   Gute, schlechte und nicht klassifizierte Anrufe
-   Allgemeine Subnetze

Weitere detaillierte Schulungen und Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="what-is-cqd"></a>Was ist CQD?

Sie verwenden das Anruf Qualitäts Dashboard (CQD), um Einblicke in die Qualität von Anrufen zu gewinnen, die mithilfe von Teams und Skype for Business-Diensten erfolgen. CQD wurde entwickelt, um Skype for Business-und Teams-Administratoren und Netzwerk Ingenieuren zu helfen, das Netzwerk zu optimieren und die Qualität, Zuverlässigkeit und Benutzerfreundlichkeit genau im Auge zu behalten. CQD befasst sich mit der aggregierten Telemetrie für eine gesamte Organisation, in der allgemeine Muster sichtbar werden können, sodass Mitarbeiter fundierte Bewertungen vornehmen und Sanierungs Aktivitäten planen können, um die Auswirkungen zu maximieren. CQD stellt Berichte zu Metriken bereit, die Einblicke in die allgemeine Qualität, Zuverlässigkeit und Benutzerfreundlichkeit bieten.

Dieser Leitfaden hilft Ihnen, die grundlegenden Konzepte von CQD zu verstehen, damit Sie die Auswirkungen maximieren können, die Sie bei der Verbesserung der Benutzererfahrung mit Teams oder Skype for Business Online erzielen können. Weitere CQD-Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="expectations-using-cqd"></a>Erwartungen mit CQD

CQD, obwohl nützlich zum Analysieren von Trends und Subnetzen, stellt nicht immer eine bestimmte Ursache für ein bestimmtes Szenario dar. Es ist wichtig, dies zu verstehen und bei Verwendung von CQD die richtige Erwartung zu definieren:

-   CQD stellt nicht die Ursache für jedes Szenario dar.
-   CQD enthält keine Telefon System-oder Audiokonferenz-Streams.
-   CQD ruft Bereiche zur weiteren Untersuchung basierend auf Trends auf.

### <a name="report-editions"></a>Berichts Editionen

Es gibt zwei Berichtsausgaben in CQD online: Zusammenfassung und detailliert. Verwenden Sie das Dropdownmenü in der Leiste am oberen Rand des Bildschirms, um eine Berichts Edition zu öffnen. Der Name der ausgewählten Berichts Edition wird oben auf dem Bildschirm angezeigt.

-   Zusammenfassungsberichte sind statisch und können nicht bearbeitet, heruntergeladen oder exportiert werden. 
-   Detaillierte Berichte sind vollständig anpassbar und können in eine CSV-Datei, exportiert oder geklont heruntergeladen werden.

Eine vollständige Beschreibung der Unterschiede zwischen den beiden Editionen finden Sie in [diesem Artikel](turning-on-and-using-call-quality-dashboard.md).

Neu im Januar 2020: [Herunterladen von Power BI-Abfragevorlagen für CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, die Sie verwenden können, um Ihre CQD-Daten zu analysieren und zu melden.

_Abbildung 4: CQD-Berichtskategorien_

Die Zusammenfassungsberichte sind in vier Kategorien unterteilt:

-   **Zusammenfassungsberichte** konzentrieren sich auf die Analyse von qualitätstrends mit täglichen, monatlichen und Tabellen Berichten, um Unterstützung bei der Ermittlung von Subnetzen zu finden, die schlechte Qualität aufweisen. Dies ist die standardmäßige Startseite, wenn Sie sich zum ersten Mal bei CQD Online anmelden.
-   **Standort optimierte Berichte** konzentrieren sich auf die Analyse von qualitätstrends auf der Grundlage von Standortinformationen. Um diese Berichte zu verwenden, müssen Sie eine Building-Datei hochgeladen haben.
-   **Zuverlässigkeitsberichte** konzentrieren sich auf die Analyse von Zuverlässigkeits Trends für Audio, Video, videobasierte Bildschirmfreigabe (schlechte VBSS) und App-Freigabe.
-   **Berichte über die Qualität der Erfahrung** sind eine abgespeckte Version der detaillierten QER-Vorlagen, die sich auf die wichtigsten Bereiche für die Analyse von Audioqualität und-Zuverlässigkeit konzentriert.

### <a name="report-types"></a>Berichtstypen

Je nachdem, wie die Daten angezeigt werden sollen, können Sie zwei Arten von Berichten in CQD auswählen. Auch wenn in diesem Leitfaden die Besonderheiten beim Erstellen eines Berichtstyps über einen anderen nicht behandelt werden, bieten die QER-CQD-Vorlagen eine Kombination aus anpassbaren Diagramm-und Tabellen Berichten, die Sie verwenden können:

-   Diagrammberichte erstellen grafische Balkendiagramme, um Daten in einem visuellen Format darzustellen. Diagrammberichte werden am besten verwendet, um Daten über einen bestimmten Zeitraum zu visualisieren.
-   Tabellen Berichte sind hilfreich für die Betrachtung einzelner Maße und Dimensionen, wenn Sie die Berichte in CSV-Dateien exportieren, um Sie in Microsoft Excel zu bearbeiten.

### <a name="tenant-id"></a>Mandanten-ID

Bei einigen CQD-Berichten müssen Sie einen Filter für Ihre Mandanten-ID angeben. Aufgrund der Art und Weise, wie CQD Daten aggregiert, ist die Telemetrie des Föderations Teilnehmers enthalten. Auch wenn dies bei der Analyse von Trends hilfreich sein kann, erfordern Client-und Geräte Berichte, dass Sie Daten nach einem bestimmten Mandanten filtern, um die Telemetrie von Verbund Teilnehmern auszuschließen. Wenn Sie Ihre Mandanten-ID nicht kennen, können Sie eine der folgenden Methoden verwenden, um Sie zu finden.

> [!Note]
> Für diese Methoden sind die folgenden Berechtigungen erforderlich:<ul><li>Rolle des globalen Administrators</li><li>Skype for Business-Administrator Rolle</li></ul>

#### <a name="azure-portal"></a>Azure-Portal

1.  Anmelden beim Microsoft Azure-Portal:<https://portal.azure.com>

2.  Wählen Sie **Azure Active Directory**aus.

3.  Wählen Sie unter **Verwalten**die Option **Eigenschaften**aus. Die Mandanten-ID wird im Feld **Verzeichnis-ID** angezeigt.

#### <a name="azure-powershell"></a>Azure PowerShell

1. [Installieren Sie das Microsoft Azure PowerShell-Dienst Verwaltungsmodul](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2. Öffnen Sie ein Azure PowerShell-Befehlsfenster, und führen Sie das folgende Skript aus, und geben Sie bei der entsprechenden Aufforderung Ihre Office 365-Anmeldeinformationen ein: 

   ```PowerShell
   Login-AzureRmAccount
   ```

3. Die Mandanten-ID wird in der Ausgabe aufgeführt.

#### <a name="skype-for-business-online-admin-center"></a>Skype for Business Online Admin Center

1.  Navigieren Sie in das Verzeichnis <https://portal.office.com>.

2.  Mit Ihrem mandantenadministrator-organisationskonto anmelden

3.  Wählen Sie **Skype for Business** unter **Admin Center**aus.

4.  Die Mandanten-ID wird auf der Willkommensseite als **Organisations-ID** aufgeführt.

#### <a name="skype-for-business-online-using-powershell"></a>Skype for Business Online mit PowerShell

1. [Richten Sie Ihren Computer für Windows PowerShell ein](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Führen Sie den folgenden Befehl aus:

   ```PowerShell
   (Get-cstenant).tenantid
   ```

3. Die Mandanten-ID wird als GUID angezeigt.

### <a name="teams-vs-skype-for-business"></a>Teams vs. Skype for Business

CQD kann sowohl über Teams als auch über die Telemetrie von Skype for Business Berichten. Es kann jedoch vorkommen, dass Sie einen Bericht entwickeln möchten, um die von Skype for Business getrennte Teams-Telemetrie zu betrachten.

#### <a name="summary-reports"></a>Zusammenfassungsberichte

Wenn Sie die Seite Zusammenfassungsberichte so ändern möchten, dass nur Teams oder Skype for Business angezeigt wird, wählen Sie das Dropdownmenü **Produkt Filter** oben auf dem Bildschirm aus, und wählen Sie dann das gewünschte Produkt aus.

![Screenshot des Dropdownmenüs mit den Filteroptionen](media/qerguide-image-productfilter.png)

_Abbildung 5: Auswählen eines Produkt Filters_

#### <a name="detailed-reports"></a>Detaillierte Berichte

Wenn Sie alle detaillierten Berichte filtern möchten, fügen Sie in der Browserleiste am Ende der URL Folgendes an:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Beispiel**

```https://cqd.lync.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Weitere Informationen zu URL-Filtern finden Sie unter [Filtern von Berichten](#filtering-reports) weiter unten in diesem Abschnitt.

Wenn Sie einen einzelnen detaillierten Bericht filtern möchten, fügen ``Is Teams`` Sie den Filter dem Bericht hinzu, und setzen Sie ihn auf wahr oder falsch. Weitere Informationen finden Sie unter [Bearbeiten von Berichten](#editing-reports) weiter unten in diesem Abschnitt.

![Screenshot der Seite "Filter hinzufügen"](media/qerguide-image-addteamsfilter.png)

_Abbildung 6: Hinzufügen eines Microsoft Teams-Filters zu einem Bericht_


### <a name="managed-vs-unmanaged-networks"></a>Verwaltete vs. nicht verwaltete Netzwerke

Standardmäßig werden alle Endpunkte in CQD als extern klassifiziert. Sobald eine Building-Datei eingeführt wurde, können wir mit der Suche nach verwalteten Endpunkt Daten beginnen. Wie bereits besprochen, werden Netzwerke in CQD wie folgt definiert:

-   Ein _verwaltetes Netzwerk_, das häufig als "intern" oder "Inside" bezeichnet wird, kann von der Organisation beeinflusst und gesteuert werden. Dazu gehören das interne LAN, das Remote-WAN und das VPN.
-   Ein nicht _verwaltetes Netzwerk_, das häufig als "extern" oder "extern" bezeichnet wird, kann nicht von der Organisation beeinflusst oder gesteuert werden. Ein Beispiel für ein nicht verwaltetes Netzwerk ist ein Hotel-oder AirPort-Netzwerk.

### <a name="dimensions-measures-and-filters"></a>Dimensionen, Measures und Filter

Eine wohlgeformte CQD-Abfrage enthält alle drei folgenden Parameter:

-   **Dimension:** Wie ich auf die Daten pivotieren möchte.

-   **Measure:** Was ich melden möchte.

-   **Filter:** Wie ich das DataSet reduzieren möchte, das die Abfrage zurückgibt.

Eine weitere Möglichkeit, dies zu betrachten, ist, dass eine _Dimension_ die Gruppierungsfunktion ist, ein _Measure_ die Daten ist, die mich interessieren, und ein _Filter_ ist, wie ich die Ergebnisse auf diejenigen einschränken möchte, die für meine Abfrage relevant sind.

Ein Beispiel für eine wohlgeformte Abfrage ist " **schlechte Datenströme anzeigen" [Measure] nach Subnetz [Dimension] für Building 6 [Filter]**. Weitere Informationen finden Sie unter [Dimensionen und Measures, die in CQD verfügbar sind](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>Erste vs. Sekunde 

Viele Dimensionen und Measures in CQD werden als erste oder zweite klassifiziert. CQD verwendet keine Caller/Callee-Felder – diese wurden in _erster_ und _zweiter_ Weise umbenannt, da zwischen dem Anrufer und dem angerufenen dazwischenliegende Schritte vorhanden sind. Mit der folgenden Logik wird bestimmt, welcher Endpunkt als erstes beschriftet ist:

-   **Zunächst** handelt es sich immer um einen Serverendpunkt (Konferenzserver, Vermittlungsserver usw.), wenn ein Server am Datenstrom oder-Anruf beteiligt ist.

-   **Second** ist immer ein Clientendpunkt, es sei denn, der Datenstrom liegt zwischen zwei Serverendpunkten.

-   Wenn beide Endpunkte den gleichen Typ aufweisen, basiert die Auswahl zunächst auf der internen Reihenfolge der Benutzer-Agent-Kategorie. Damit wird eine konsistente Anordnung sichergestellt.

Weitere Informationen zum Ermitteln des ersten oder zweiten Endpunkts, wenn beide identisch sind, finden Sie unter [Dimensionen und Measures, die in CQD verfügbar](https://aka.ms/cqd-dm)sind.

### <a name="stream-vs-call"></a>Stream vs. Call

Sie müssen den Unterschied zwischen einem Anruf und einem Datenstrom verstehen, um die Dimensionen oder Measures, die Sie in CQD suchen, richtig auszuwählen. Obwohl sich CQD hauptsächlich auf Streams beruft, stehen auch Anruf basierte Messungen zur Verfügung.

-   **Stream:** Zwischen zwei Endpunkten ist ein _Datenstrom_ vorhanden. Es gibt nur einen Datenstrom für jede Richtung, und für die Kommunikation sind zwei Datenströme erforderlich. Streams sind hilfreich bei der Untersuchung von Gebäuden, Netzwerken oder Subnetzen. In einigen Fällen werden sowohl "Call" als auch "Stream" im Namen der Messung verwendet (beispielsweise "Setup-Datenstrom aufrufen" oder "unterbrochener Stream aufrufen"). Diese werden weiterhin als Datenströme klassifiziert.

-   **Anruf:** Bei einem _Anruf_ handelt es sich um eine Gruppierung aller Datenströme aller Teilnehmer. Ein Anruf besteht aus mindestens zwei Streams. Ein einzelner Aufruf verfügt über mindestens zwei Endpunkte, die jeweils mindestens einen Datenstrom aufweisen.

Weitere Anleitungen dazu, ob sich die Dimension oder das Measure auf einen Anruf oder einen Datenstrom bezieht, finden Sie unter [Dimensionen und Measures, die in CQD verfügbar](https://aka.ms/cqd-dm) sind.

### <a name="good-poor-and-unclassified-calls"></a>Gute, schlechte und nicht klassifizierte Anrufe

Ein Anruf wird entweder als "gut", "schlecht" oder "nicht klassifiziert" kategorisiert. Nehmen Sie sich einen Moment Zeit, um über die einzelnen Details zu reden.

-   **Gut oder schlecht:** Ein guter oder schlechter Anruf besteht aus einem Anruf, der einen vollständigen Satz von Dienst Metriken enthält, für die ein vollständiger QoE-Bericht generiert und vom Dienst empfangen wurde. Wie Sie feststellen, ob ein Datenstrom gut oder schlecht ist, wird [weiter oben in diesem Leitfaden](#poor-stream-rate)beschrieben.

-   Nicht **klassifiziert:** Ein nicht klassifizierter Datenstrom enthält keinen vollständigen Satz von Dienst Metriken. Hierbei kann es sich um kurze Anrufe (in der Regel weniger als 60 Sekunden) handeln, bei denen der Mittelwert nicht berechnet und kein QoE-Bericht generiert wurde. Der häufigste Grund für Anrufe, die nicht klassifiziert werden müssen, besteht darin, dass die Paket Nutzung gering ist. Ein Beispiel hierfür wäre ein Teilnehmer, der sich über Stummschaltung an einer Besprechung anschließt und nie spricht. Der Teilnehmer empfängt, aber nicht sendet, Medien. Ohne Medien, die übertragen werden, gibt es keine Metriken, die CQD verwenden können, um den ausgehenden Mediendatenstrom des Endpunkts zu klassifizieren.

Weitere Informationen zum Stream-Klassifizierungsprozess finden Sie in [diesem Artikel](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Allgemeine Subnetze

Häufig verwendete Subnetze sind bestimmte private Subnetze, die von Hotels, privaten Netzwerken, Hotspots und ähnlichen Bereichen verwendet werden. Diese Subnetze sind aufgrund der weit verbreiteten Verwendung schwer zu selektieren. Wenn Ihre Organisation eines dieser häufig verwendeten Subnetze verwendet, empfehlen wir, dieses Netzwerk in ein anderes Subnetz zu verschieben. Dadurch wird die Berichterstellung in CQD vereinfacht. Wenn Sie darauf hingewiesen werden, wurden Berichte in der Vorlage alle Netzwerke so konfiguriert, dass diese Subnetze ausgeschlossen werden, um Sie als Quelle schlechter Qualität zu eliminieren. Allgemeine Subnetze werden nachstehend definiert. ihre Auswirkungen sind je nach Organisation unterschiedlich.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Wenn Sie ein verwaltetes Netzwerk untersuchen, das ein gemeinsames Subnetz verwendet, müssen Sie die zweite reflexive lokale IP-Dimension verwenden, um Subnets zu gruppieren. Diese Dimension enthält die öffentliche IP-Adresse des Endpunkts.

## <a name="cqd-online"></a>CQD Online

In diesem Abschnitt werden die Grundlagen für den Zugriff auf CQD beschrieben. Anleitungen zu den folgenden Themen:

-   Zugreifen auf CQD Online
-   Erste Schritte mit CQD
-   Bearbeiten von Berichten in CQD
-   Filtern von Berichten in CQD
-   Importieren von Berichten in CQD

Weitere detaillierte Schulungen und Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="access-cqd-online"></a>Zugreifen auf CQD Online

Sie können auf CQD auf eine von drei Arten zugreifen:

-   Navigieren Sie in das Verzeichnis <https://cqd.lync.com>.

-   Wechseln Sie zum **Microsoft Teams Admin Center** , und wählen Sie den Link zu CQD aus, wie in der folgenden Abbildung dargestellt.

![Screenshot des Dashboards "Anrufqualität" ausgewählt.](media/qerguide-image-mopo.png "Im linken Navigationsbereich ist das Dashboard "Link zur Anrufqualität" ausgewählt.")

_Abbildung 7: Zugreifen auf CQD über das Microsoft Teams Admin Center_

-   Wechseln Sie zu den Legacy**Tools** **für Skype for Business Admin Center** > , und wählen Sie den Link zu CQD aus, wie in der folgenden Abbildung dargestellt.

![Screenshot der im Hauptbereich ausgewählten CQD](media/qerguide-image-legacyui.png "Im linken Navigationsbereich ist "Tools" ausgewählt, und im Hauptbereich ist der Link zu CQD ausgewählt.")

_Abbildung 8: Zugreifen auf CQD über das Skype for Business Admin Center_


### <a name="getting-started"></a>Erste Schritte

Wenn Sie zum ersten Mal zu CQD navigieren, wird die Seite Zusammenfassungsberichte angezeigt. Die meisten in diesem Leitfaden beschriebenen Berichte sind benutzerdefinierte detaillierte Berichte. Um mit den detaillierten Berichten zu beginnen, wählen Sie oben auf der Seite **Zusammenfassungsberichte** aus, und wählen Sie dann **detaillierte Berichte**aus.

![Screenshot mit den in CQD verfügbaren Berichtstypen](media/qerguide-image-choosereports.png)

_Abbildung 9 – navigieren zu detaillierten Berichten_

Die Seite detaillierte Berichte in CQD sieht wie in der folgenden Abbildung aus.

![Screenshot zur Veranschaulichung von Elementen, die einen detaillierten Bericht bilden](media/qerguide-image-detailedreportspage.png)

|             |           |
| ------------|-----------|
| ![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout1.png "eine") | Der Bereich "Zusammenfassung" zeigt den Kontext für den auf der rechten Seite angezeigten Berichtssatz an. |
| ![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout2.png "zwei") | Sie können im Zusammenfassungsbereich **Bearbeiten** auswählen, um die Eigenschaften auf Berichtsebene (einschließlich der Höhe der y-Achse) zu definieren und neue Vorlagen zu importieren. |
| ![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout3.png "drei") | Mithilfe der Breadcrumb-Struktur können Benutzer Ihre aktuelle Position in der Berichtssatz Hierarchie ermitteln. |
| ![Symbol der Zahl 4, die auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout4.png "vier") | Berichte mit untergeordneten Berichten werden mit einem blauen Link angezeigt. Wenn Sie den Link auswählen, können Sie einen Drilldown zu den untergeordneten Berichten durchführen. |

_Abbildung 10 – Seite "detaillierte Berichte"_

Zeigen Sie auf Balkendiagramme und Trendlinien im Bericht, um detaillierte Werte anzuzeigen. In dem Bericht, der den Fokus hat, wird das Menü Aktion angezeigt: **Bearbeiten**, **Klonen**, **Löschen**, **herunterladen**und **Exportieren der Berichtsstruktur**.

### <a name="editing-reports"></a>Bearbeiten von Berichten

Wenn Sie im Aktionsmenü eines Berichts **Bearbeiten** auswählen, öffnen Sie den Abfrage-Editor. Jeder Bericht wird durch eine Abfrage an CQD gesichert. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Abfrage-Editor ist eine Benutzeroberfläche zum Bearbeiten dieser Abfragen zusätzlich zu den Anzeigeoptionen für den Bericht, wie in der folgenden Abbildung dargestellt.

![Screenshot zur Veranschaulichung von Elementen, die einen zu bearbeitenden Bericht darstellen.](media/qerguide-image-queryeditor.png)

|             |           |
| ------------|-----------|
| ![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout1.png "eine") | Im linken Bereich Wählen Sie Bemaßungen, Measures und Filter aus. Wenn Sie auf einen vorhandenen Wert zeigen, wird die Schaltfläche Schließen (**X**) angezeigt, die Sie auswählen können, um den Wert zu entfernen.<ul><li>Wenn Sie die Bemaßung oder das Measure auswählen, können Sie den Titel ändern, indem Sie das Feld " **Titel** " bearbeiten. Sie können die Reihenfolge auch ändern, indem Sie im oberen Bereich den blauen aufwärts-oder Abwärtspfeil auswählen.</li><li>Wenn Sie**+**() neben einer Überschrift auswählen, wird das Dialogfeld zum Hinzufügen einer neuen Bemaßung, eines Measures oder eines Filters geöffnet.</li><li>Geben Sie die ersten Buchstaben der Bemaßung, des Measures oder des Filters in das Feld **suchen ein** , um die Liste zu filtern, um die Suche zu vereinfachen.</li></ul> |
| ![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout2.png "zwei") | Der obere Bereich zeigt Optionen für die Anpassung des Diagramms an. |
| ![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout3.png "drei") | Der Abfrage-Editor zeigt eine Vorschau des Berichts an. |
| ![Symbol der Zahl 4, die auf eine Legende im vorherigen Screenshot verweist](media/qerguide-image-callout4.png "vier") | Verwenden Sie das **Bearbeitungs** Feld unten auf dem Bildschirm, um eine detaillierte Beschreibung des Berichts zu erstellen oder zu bearbeiten. |

_Abbildung 11: Abfrage-Editor_

### <a name="filtering-reports"></a>Filtern von Berichten

Zu den bereitgestellten Vorlagen gehören verschiedene integrierte Abfragen und Berichtsfilter. In den folgenden Abschnitten werden die am häufigsten verwendeten Filter in den Vorlagen beschrieben.

#### <a name="url-filter"></a>URL-Filter

Sie können einen URL-Filter verwenden, um jeden Bericht nach einer bestimmten Dimension zu filtern. Die am häufigsten verwendeten URL-Filter werden verwendet, um Berichte zu filtern, um die Telemetrie von Teilnehmern auszuschließen oder sich auf Teams oder Skype for Business Online zu konzentrieren. Wir empfehlen, dass Sie bei der Verwendung von Filtern eine Textmarke zur einfachen Referenz verwenden. 

Das Ausschließen von Verbund Daten aus CQD-Berichten ist hilfreich, wenn Sie verwaltete Gebäude oder Netzwerke remediationen, in denen Verbundendpunkte ihre Berichte beeinflussen könnten.

Wenn Sie einen URL-Filter implementieren möchten, fügen Sie in der Adressleiste des Browsers folgendes an das Ende der URL an:

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel  

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Wenn Sie die Berichte für Teams oder Skype for Business filtern möchten, fügen Sie am Ende der URL Folgendes an:

```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

Beispiel

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Is Teams]|[TRUE]```


> [!NOTE]
> Die obigen URL-Beispiele sind nur für die visuelle Darstellung vorgesehen. Bitte verwenden Sie den standardmäßigen <https://cqd.lync.com>CQD-Link von.


#### <a name="query-filters"></a>Abfragefilter

Abfragefilter werden mithilfe des Abfrage-Editors in CQD implementiert. Diese Filter werden verwendet, um die Anzahl der von CQD zurückgegebenen Datensätze zu verringern, wodurch die Gesamtgröße des Berichts und die Abfragezeiten minimiert werden. Dies ist besonders hilfreich beim Filtern von nicht verwalteten Netzwerken. Die in der folgenden Tabelle aufgelisteten Filter verwenden reguläre Ausdrücke (Regex).

_Tabelle 3 – Abfragefilter_

| Filter         | Beschreibung          | Beispiel für CQD-Abfragefilter      |
|----------------|----------------------|-------------------------------|
| Keine leeren Werte   | Einige Filter verfügen nicht über die Option, nach leeren Werten zu filtern. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und setzen Sie den Filter abhängig von Ihren Anforderungen auf Equals oder unequals.      | Zweiter Gebäude Name \< \> \^ \\s\*\$                       |
| Ausschließen von allgemeinen Subnetzen | Ohne eine gültige Building-Datei, die verwaltet von nicht verwalteten Netzwerken trennt, werden private Netzwerke in die Berichte aufgenommen. Diese Home-Subnetze liegen außerhalb des Kontrollbereichs und können schnell von einem Bericht ausgeschlossen werden. Allgemeine Subnets, wie in diesem Leitfaden definiert, sind 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweites Subnetz \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Nur innere Ansicht  | Wird verwendet, um einen Bericht für verwaltet (innerhalb) oder nicht verwaltet (extern) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.       | Second Inside Corp = innen        |

#### <a name="report-filters"></a>Berichtsfilter

Berichtsfilter werden durch Hinzufügen eines Filters zum gerenderten Bericht entweder im Abfrage-Editor oder direkt im Bericht implementiert. Die folgenden Berichtsfilter werden in der gesamten Vorlage verwendet.

_Tabelle 4 – Berichtsfilter_

| Filter     | Beschreibung                            | Beispiel für CQD-Berichtsfilter         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Beginnen Sie mit dem ersten Jahr und dann mit dem Monat. | 2017-10                           |
| Alphabetisches | Filtert nach alphabetischen Zeichen. | [a-z]                             |
| Numerische    | Filtert nach beliebigen numerischen Zeichen.    | [0-9]                             |
| Prozentsatz | Filtert nach einem Prozentsatz.              | ([3-9]\\.) \|([3-9])\|([1-9] [0-9]) |

## <a name="import-the-cqd-templates"></a>Importieren der CQD-Vorlagen

Dieser Leitfaden enthält [zwei kuratierte CQD-Vorlagen](https://aka.ms/qertemplates). Diese Vorlagen beschleunigen die Nutzung von CQD und bieten Ihnen die Möglichkeit, die Funktionen von CQD schnell zu nutzen, um die Benutzer Teams oder die Skype for Business-Umgebung zu beeinflussen. Die Vorlage "alle Netzwerke", obwohl für die Arbeit mit einer Gebäude Datendatei optimiert, kann verwendet werden, während Sie zum Sammeln und Hochladen von Gebäudeinformationen in CQD arbeiten, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (. CQDX) into CQD Online**

1. Navigieren Sie in das Verzeichnis <https://cqd.lync.com>.

2. Authentifizieren Sie sich mithilfe ihrer administrativen Office 365-Anmeldeinformationen.

   > [!NOTE]
   > Sie müssen über die Rolle "Office 365 Global Administrator", "Skype for Business-Administrator" oder "Leser des Berichts" verfügen, um auf CQD zugreifen zu können. 

3. Wählen Sie oben auf der Seite das Menü **Zusammenfassungsberichte** aus, und wählen Sie dann **detaillierte Berichte**aus.

4. Wählen Sie im Zusammenfassungsbereich **importieren**aus. Wechseln Sie zum CQDX gespeicherten Speicherort, wählen Sie die CQDX-Vorlage aus, und wählen Sie dann **Öffnen**aus.

5. Nachdem die Vorlage hochgeladen wurde, wird in einem Popupfenster die Meldung "Bericht Import war erfolgreich" angezeigt. Wählen Sie **OK aus.**

   ![Screenshot der erfolgreichen Import Benachrichtigung](media/qerguide-image-importmessage.png "Benachrichtigung, dass die Vorlage erfolgreich importiert wurde")

6. Wiederholen Sie die Schritte 4 und 5 für die zweite CQD-Vorlage.

> [!NOTE]
> Die CQD-Vorlagen werden pro Benutzer importiert. Wenn weitere Benutzer den Bericht verwenden müssen, müssen Sie sich anmelden und die Vorlagen in Ihre CQD-Instanz importieren. 


## <a name="building-mapping"></a>Gebäude Zuordnung

In einer Microsoft Teams-oder Skype for Business Online-Bereitstellung sind alle Clients extern. Dies hat die Implikation, dass standardmäßig alle Clients in CQD Online als "extern" gemeldet werden, unabhängig davon, ob der Client in einem internen Unternehmensnetzwerk verbunden war.

Wenn Sie mit CQD arbeiten, müssen Sie den Standort eines Endpunkts kennen und wissen, ob er mit einem Netzwerk verbunden ist, das Sie verwalten können, oder ein Netzwerk, das Sie nicht verwalten können – die Annahme ist, dass Sie nur Netzwerke verbessern können, die Sie verwalten können. Durch Hochladen von Subnetzen und Erstellen von Informationen in CQD Online können Sie CQD ermitteln, ob der Endpunkt mit einem internen Unternehmen/verwalteten Netzwerk oder mit einem externen/nicht verwalteten Netzwerk verbunden ist.

### <a name="building-data-file-structure"></a>Gebäudedaten Dateistruktur

Das Format der Datendatei, die Sie hochladen, muss die folgenden Voraussetzungen erfüllen, um die Gültigkeitsprüfung vor dem Upload durchführen zu können.

-   Bei der Datei muss es sich um eine TSV-Datei handeln, was bedeutet, dass für jede Zeile jede Spalte durch ein Tabstoppzeichen getrennt ist, oder eine CSV-Datei, in der jede Spalte durch ein Komma getrennt ist.

-   Die Datei kann nicht größer als 50 MB sein.

-   Der Inhalt der Datendatei *darf keine Tabellenüberschriften enthalten*. Mit anderen Worten: die erste Zeile der Datendatei muss reelle Daten und nicht Spaltenüberschriften wie "Netzwerk" sein.

-   In jeder Spalte kann der Datentyp nur eine Zeichenfolge, eine Zahl oder der boolesche Datentyp sein. Wenn der Datentyp number ist, muss der Wert ein numerischer Wert sein; Wenn es sich um bool handelt, muss der Wert entweder 0 oder 1 sein.

-   Wenn der Datentyp Zeichenfolge ist, können die Daten für jede Spalte leer sein (müssen aber immer noch durch ein entsprechendes Trennzeichen getrennt werden, d. h. ein Tabstoppzeichen oder ein Komma). Dadurch wird dem Feld eine leere Zeichenfolge zugewiesen.

-   Für jede Zeile müssen 14 Spalten vorhanden sein. Jede Spalte muss den in der folgenden Tabelle beschriebenen Datentyp aufweisen, und die Spalten müssen in der in der Tabelle aufgelisteten Reihenfolge sein.

_Tabelle 5 – Erstellen einer Dateistruktur_

| Spaltenname        | Datentyp | Beispiel                   | Anleitung    |
|--------------------|-----------|---------------------------|-------------|
| Netzwerk            | Zeichenfolge    | 192.168.1.0               | Erforderlich    |
| NetworkName        | Zeichenfolge    | USA/Seattle/SEATTLE-SEA-1 | Erforderlich\*  |
| NetworkRange       | Zahl    | 26                        | Erforderlich    |
| BuildingName       | Zeichenfolge    | SEATTLE-SEA-1             | Erforderlich\*  |
| Ownershiptype      | Zeichenfolge    | Contoso                   | Optional    |
| Buildingtype       | Zeichenfolge    | IT Termination            | Optional    |
| BuildingOfficeType | Zeichenfolge    | Engineering               | Optional    |
| Ort               | Zeichenfolge    | Seattle                   | Empfohlen |
| ZipCode            | Zeichenfolge    | 98001                     | Empfohlen |
| Land            | Zeichenfolge    | USA                        | Empfohlen |
| Bundesland              | Zeichenfolge    | WA                        | Empfohlen |
| Region             | Zeichenfolge    | MSUS                      | Empfohlen |
| InsideCorp         | Bool      | 1                         | Erforderlich    |
| Express Route       | Bool      | 0                         | Erforderlich    |

\*Obwohl es für CQD nicht erforderlich ist, sind die Vorlagen für die Anzeige von Gebäude-und Netzwerknamen konfiguriert.

#### <a name="supernetting"></a>Supernetting

Sie können das Supernetting verwenden, das im Allgemeinen als "Klassen übergreifendes Routing" (CIDR) bezeichnet wird, anstatt jedes Subnetz zu definieren. Eine *Supernet* ist eine Kombination aus mehreren Subnetzen, die ein einzelnes Routingpräfix verwenden. Anstatt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die übermäßige Adresse verwenden. Supernetting wird unterstützt, aber wir raten davon ab, es zu verwenden.

Das Marketing Gebäude von Contoso besteht beispielsweise aus den folgenden Subnetzen:

-   10.1.0.0/24 – erster Stock
-   10.1.1.0/24 – zweites Stockwerk
-   10.1.2.0/24 – dritte Etage
-   10.1.3.0/24 – Vierte Etage

Anstatt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die übermäßige Adresse verwenden – in diesem Beispiel 10.1.0.0/22.

-   Netzwerk = 10.1.0.0
-   Netzwerkbereich = 22

Hier sind ein paar Dinge zu bedenken, bevor Sie Supernetting implementieren:

-   Supernetting kann nur in einer Subnetz-Zuordnung mit 8-Bit-zu-28-Bit-Maske verwendet werden.

-   Supernetting nimmt im Vordergrund weniger Zeit in Anspruch, aber es geht um die Kosten für eine Verringerung des Umfangs ihrer Daten. Angenommen, es gibt ein Qualitätsproblem mit Subnetz-200.1.2.0. Wenn Sie Supernetting implementiert haben, wissen Sie nicht, an welcher Stelle im Gebäude sich das Subnetz befindet oder welche Art von Netzwerk es ist (beispielsweise eine Übungseinheit). Wenn Sie alle Subnetze für ein Gebäude definiert und Informationen zur bodenposition hochgeladen haben, können Sie diese Unterscheidung sehen.

-   Es ist wichtig, sicherzustellen, dass die überarbeiteten Adressen richtig sind und keine unerwünschten Subnetze fangen.

-   Es ist ziemlich üblich, 192.168.0.0 in Daten zu finden. Für viele Organisationen deutet dies darauf hin, dass der Benutzer zu Hause ist. Bei anderen handelt es sich um das IP-Adressschema für eine Satelliten Niederlassung. Wenn Ihre Organisation über Büros verfügt, die diese Konfiguration verwenden, fügen Sie Sie nicht in ihre Gebäude Datei ein, da es schwierig ist, zwischen privaten und internen Netzwerken unterscheiden zu können, indem Sie allgemeine Subnetze verwenden. Weitere Informationen finden Sie im Abschnitt zu [häufig verwendeten Subnetzen](#common-subnets)weiter oben in diesem Leitfaden.

> [!IMPORTANT]
> Der Netzwerkbereich kann verwendet werden, um einen Supernet darzustellen. Alle neuen Uploads von Gebäudedaten Dateien werden auf alle überlappenden Bereiche geprüft. Wenn Sie zuvor eine Building-Datei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um Überlappungen zu identifizieren und das Problem zu beheben. Jede Überlappung in zuvor hochgeladenen Dateien kann zu einer falschen Zuordnung von Subnetzen zu Gebäuden in den Berichten führen.

#### <a name="vpn"></a>VPN

Die QoE-Daten (Quality of Experience), die Clients an Office 365 senden, an denen CQD-Daten bezogen werden, enthalten ein VPN-Flag. CQD wird dies als erstes VPN-und zweites VPN-Maß sehen. Dieses Flag basiert jedoch auf der Berichterstellung des VPN-Anbieters an Windows, dass der registrierte VPN-Netzwerkadapter ein RAS-Adapter ist. Nicht alle VPN-Anbieter registrieren Remote Zugriffs Adapter ordnungsgemäß. Aus diesem Grund können Sie die integrierten VPN-Abfragefilter möglicherweise nicht verwenden. Es gibt zwei Ansätze für die Unterbringung von VPN-Subnetzen in der Gebäude Informationsdatei:

- Definieren Sie einen **Netzwerknamen** , indem Sie in diesem Feld den Text "VPN" für VPN-Subnetze verwenden.

  ![Screenshot des QCD-Berichts mit VPN-Netzwerknamen](media/qerguide-image-vpnnetworkname.png)

  _Abbildung 12 – VPN mit Netzwerknamen_

- Definieren Sie einen **Gebäudenamen** , indem Sie in diesem Feld den Text "VPN" für VPN-Subnetze verwenden.

  ![Screenshot des QCD-Berichts mit VPN mithilfe des Gebäude namens](media/qerguide-image-vpnbuildingname.png)

  _Abbildung 13 – VPN mit dem Gebäudenamen_

> [!IMPORTANT]
> Bei bestimmten VPN-Implementierungen werden die Subnetinformationen nicht genau gemeldet. Wenn dies in ihrer Berichterstattung auftritt, empfehlen wir, dass Sie, wenn Sie ein VPN-Subnetz zur Gebäude Datei hinzufügen, anstatt eines Eintrags für das Subnetz, separate Einträge für jede Adresse im VPN-Subnetz als separates 32-Bit-Netzwerk hinzufügen. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Anstelle einer Zeile für 172.16.18.0/24 verfügen Sie beispielsweise über 253 Zeilen mit einer Zeile für jede Adresse von 172.16.18.1/32 bis 172.16.18.254/32 inklusive.


> [!NOTE]
> Bei VPN-Verbindungen ist bekannt, dass die Netzwerkverbindung bei der WLAN-zugrunde liegenden Internetverbindung nicht als verkabelt festgestellt wird. Wenn Sie die Qualität über VPN-Verbindungen betrachten, können Sie nicht davon ausgehen, dass der Verbindungstyp genau identifiziert wurde.

### <a name="uploading-building-information"></a>Hochladen von Gebäudeinformationen

Das Dashboard für CQD-Zusammenfassungsberichte enthält eine Seite für **Mandantendaten Upload** , auf die durch Auswählen des Link Tags **Mandantendaten Upload** in der oberen rechten Ecke zugegriffen wird (suchen Sie nach dem Zahnradsymbol). Diese Seite wird für Administratoren verwendet, um Ihre eigenen Informationen hochzuladen, wie etwa die Zuordnung von IP-Adresse und geografischen Informationen, die Zuordnung der einzelnen WLAN-Zugriffspunkte und deren Mac-Adresse usw.

1. Wechseln Sie zu CQD Online, indem <https://cqd.lync.com>Sie zu navigieren.

2. Wählen Sie in der oberen rechten Ecke das Zahnradsymbol aus, und wählen Sie auf der Seite **Zusammenfassungsberichte** den Eintrag **Mandantendaten Upload** aus.

   ![Screenshot des Dialogfelds, das angezeigt wird, während Daten hochgeladen werden](media/qerguide-image-tenantdataupload.png)

   _Abbildung 14 – Menü "Mandantendaten Upload"_

3. Wenn Sie CQD zum ersten Mal besuchen, werden Sie aufgefordert, Gebäudedaten hochzuladen. Sie können **jetzt hochladen** auswählen, um schnell zur Seite **Mandantendaten Upload** zu navigieren.

   ![Screenshot eines Banners, das einen Benutzer zum Hochladen von Gebäudedaten benachrichtigt](media/qerguide-image-buildingdatauploadbanner.png)

   _Abbildung 15 – Banner zum Erstellen von Datenuploads_

4. Wählen Sie auf der Seite **Mandantendaten Upload** die Option **Durchsuchen** aus, um eine Datendatei auszuwählen.

5. Geben Sie nach Auswahl einer Datendatei das **Start Datum** und optional ein Enddatum an.

6. Wählen Sie nach der Auswahl von **Start Datum**die Option **hochladen** aus, um die Datei in CQD hochzuladen. <br><br>Bevor die Datei hochgeladen wird, wird Sie überprüft. Wenn die Überprüfung fehlschlägt, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, die Datei zu korrigieren. Die folgende Abbildung zeigt einen Fehler, der auftritt, wenn die Anzahl der Spalten in der Datendatei falsch ist.

   ![Beispiel für ein Dialogfeld, in dem ein Fehler beim Hochladen von Gebäudedaten angezeigt wird](media/qerguide-image-buildingdatauploaderror.png)
 
   _Abbildung 16 – Fehler beim Hochladen von Daten_

7. Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.

> [!NOTE]
> Es kann bis zu vier Stunden dauern, bis die Bearbeitung der Gebäude Datei abgeschlossen ist. <br><br> Wenn Sie bereits eine Gebäude Datei hochgeladen haben und Subnetze hinzufügen müssen, die möglicherweise verpasst oder ausgeschlossen wurden, ändern Sie die ursprüngliche Datei, indem Sie die neuen Subnetze hinzufügen, die aktuelle Datei entfernen und die neu bearbeitete Datei erneut hochladen. In CQD kann nur eine aktive Gebäude Datendatei vorhanden sein. 


### <a name="updating-a-building-file"></a>Aktualisieren einer Gebäude Datei

Beim Sammeln von Informationen zu Gebäuden und Subnetzen werden Administratoren die Gebäude Datei oft mit der Zeit in mehreren Iterationen hochladen, indem Sie neue Subnetze und deren Gebäudeinformationen hinzufügen, sobald diese verfügbar sind. In diesem Fall müssen Sie Ihre Gebäude Datei erneut hochladen. Dieser Vorgang ähnelt dem anfänglichen Upload, wie im vorherigen Abschnitt beschrieben, mit einigen Ausnahmen, wie im folgenden Abschnitt angegeben.

> [!Important]
> Es kann jeweils nur eine Gebäude Datei aktiv sein. Mehrere Gebäude Dateien sind nicht kumulativ.

#### <a name="adding-net-new-subnets"></a>Hinzufügen von neuen net-Subnetzen

Es gibt Situationen, in denen Sie neue net-Subnetze zu CQD hinzufügen müssen, die ursprünglich nicht Bestandteil Ihrer Netzwerktopologie waren. Gehen Sie zum Hinzufügen von Netto neuen Subnetzen im CQD-Mandantendaten-Upload-Portal wie folgt vor:

1.  Bearbeiten Sie die ursprüngliche Gebäude Datei, und geben Sie ein Enddatum ein, das mindestens einen Tag vor dem Erwerb der neuen Netto-Subnetze eintritt.
2.  Laden Sie die ursprüngliche Datei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.
3.  Fügen Sie die neuen net-Subnetze an die ursprüngliche Gebäude Datei an.
4.  Laden Sie die neu geänderte Gebäude Datei nach dem gleichen Verfahren wie oben ab, und legen Sie den Anfangstermin für einen Tag nach dem Ende der vorherigen Gebäude Datei ein.

#### <a name="updating-the-current-building-file"></a>Aktualisieren der aktuellen Gebäude Datei

Wenn eine Gebäude Datei bereits hochgeladen ist, Sie aber fehlende Subnets hinzufügen müssen, gehen Sie im CQD-Mandantendaten-Upload-Portal wie folgt vor:

1.  Laden Sie die ursprüngliche Datei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.
2.  Entfernen Sie die aktuelle Datei in CQD.
3.  Fügen Sie die neuen Subnetze an die ursprüngliche Datei an.
4.  Laden Sie die Gebäude Datei hoch. Stellen Sie sicher, dass das Startdatum auf mindestens acht Monate festgesetzt wird, damit CQD Verlaufsdaten verarbeitet.

### <a name="missing-subnets"></a>Fehlende Subnetze

Nachdem Sie die Gebäudeinformationen für verwaltete Netzwerke hochgeladen haben, sollte jedes verwaltete Netzwerk über eine Building Association verfügen. Dies ist allerdings nicht immer der Fall; in der Regel werden einige Subnetze übersehen. In diesem Abschnitt wird beschrieben, wie diese fehlenden Netzwerke überprüft werden.

Navigieren Sie in CQD online zur Seite **detaillierte Berichte** , und navigieren Sie zum **fehlenden subnetbericht** , der in den CQD-Vorlagen enthalten ist. Dadurch werden alle Subnetze mit 10 oder mehr Audiostreams dargestellt, die nicht in der Gebäudedaten Datei definiert sind und als "extern" gekennzeichnet sind. Stellen Sie sicher, dass in dieser Liste keine verwalteten Netzwerke vorhanden sind. Wenn Subnets fehlen, aktualisieren Sie die ursprüngliche Datendatei, und laden Sie Sie erneut in CQD hoch.

> [!IMPORTANT]
> Sie müssen Ihre Mandanten-ID als Abfragefilter für die **zweite Mandanten-ID** für diesen Bericht hinzufügen, um den Bericht so zu filtern, dass nur die Mandantendaten Ihrer Organisation angezeigt werden. Andernfalls werden im Bericht verbundene Subnetze angezeigt.

> [!NOTE] 
> Stellen Sie sicher, dass Sie den Monatsberichts Filter auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den **Monats** Berichtsfilter an, um den neuen Standardmonat zu speichern.

![Screenshot des fehlenden Subnet-Berichts](media/qerguide-image-missingbuildingreport.png)

_Abbildung 17 – fehlender Gebäude Bericht_

### <a name="building-mapping-tools"></a>Gebäude Zuordnungstools

Seien wir ehrlich, die Zuordnung von Subnetzen in Ihrer Organisation kann schwierig sein. Große globale Netzwerke sind sehr komplex, wobei unterschiedliche Teams ihre jeweiligen Regionen verwalten, und es gibt möglicherweise keine einzige Quelle der Wahrheit für die Netzwerktopologie. Es stehen zwei Tools zur Verfügung, die Sie beim Starten der Gebäude Zuordnungsübung unterstützen können, die in den folgenden Abschnitten beschrieben wird.

#### <a name="cqd-tools"></a>CQD-Tools

Diese Tools basieren auf PowerShell und können Active Directory (AD)-Websites und-Dienste sowie Microsoft DHCP-Dienste nutzen, um ihre Gebäude Datei vorab zu füllen.  Diese Tools sind für die folgenden Aufgaben hilfreich:

1.  Abfragen von anzeigen Websites und-Diensten und Erstellen einer Gebäude Datei basierend auf den darin enthaltenen Informationen
2.  Sie können einen Microsoft DHCP-Server oder Server Abfragen, um die Subnetinformationen abzurufen und automatisch eine Gebäude Datei zu erstellen.
3.  Überprüfen Sie eine vorhandene Gebäude Datei, und überprüfen Sie, ob Duplikate und Überlappungen vorhanden sind.
4.  Suchen Sie nicht zugeordnete Subnetze in CQD.

Weitere Informationen zu diesem Tool finden Sie in [diesem Blogbeitrag](https://aka.ms/cqdtools).

#### <a name="network-planner"></a>Netzwerkplaner

Der Network Planner ermittelt und organisiert Ihre Netzwerkanforderungen für Ihre Cloud-sprach Bereitstellung in nur wenigen einfachen Schritten. Durch die Bereitstellung von Netzwerkdetails und Cloud-VoIP-Nutzung in Ihrem Unternehmen können Sie eine ungefähre Berechnung der Netzwerkanforderungen für Ihre Cloud-VoIP-Bereitstellung, die Verwaltung und den Export dieser Details für die Berichterstellung und die Anzeige von Bereichen zur weiteren Untersuchung erhalten. und die nächsten Schritte.

Obwohl der Network Planner den Gebäude Zuordnungsprozess nicht vollständig automatisiert, kann nach dem Eintragen von Netzwerkinformationen in den Netzwerk Planner dann in eine für den Upload bereite Datei exportiert werden.

## <a name="reliability-investigations"></a>Zuverlässigkeits Ermittlungen

Der erste Schritt zur Verbesserung der Qualität besteht darin, den Zuverlässigkeits Status in der gesamten Organisation zu bewerten. Da Zuverlässigkeit für eine positive Benutzererfahrung von entscheidender Bedeutung ist, beginnen wir mit den beiden Komponenten zur Messung der Zuverlässigkeit:

1.  **Setup Fehler:** Der Anruf konnte nicht hergestellt werden.

2.  **Abwurf Fehler:** Der Anruf wurde eingerichtet und unerwartet beendet.

In diesem Abschnitt werden Methoden zur Untersuchung beider Bereiche behandelt.

> [!NOTE]
> In diesem Leitfaden werden nicht alle Berichte behandelt, die in den Vorlagen enthalten sind.  Die unten erläuterten Methoden der Untersuchung gelten jedoch weiterhin. Weitere Informationen finden Sie in der Beschreibung der einzelnen Berichte.


### <a name="setup-failures"></a>Setup Fehler

Priorisieren Sie das Beheben von Setupfehlern in diesem Bereich zuerst, da sich diese Fehler erheblich negativ auf die Benutzerfreundlichkeit auswirken.

Beginnen Sie mit der Untersuchung, indem Sie den Prozentsatz der allgemeinen Setupfehler für die Organisation bewerten und dann die Untersuchung von Bereichen basierend auf dem höchsten Prozentsatz für Gebäude oder Netzwerke priorisieren. 

#### <a name="setup-failure-trend-analysis"></a>Trendanalyse für Setup Fehler

In diesem Bericht werden die Gesamtmenge der Datenströme, Fehler bei der Datenstrom Einrichtung und die Fehlerrate des Datenstrom Setups angezeigt. Zeigen Sie auf eine der Spalten, um die einzelnen Werte anzuzeigen, wie in der folgenden Abbildung dargestellt. 

![Diagramm, in dem der Prozentsatz der Datenstrom Setupfehler angezeigt wird](media/qerguide-image-streamsetupfailures.png)

_Abbildung 19 – audiozuverlässigkeit – Fehler beim Stream-Setup_

##### <a name="analysis"></a>Analyse

Mit diesem Bericht können Sie die folgenden Fragen beantworten und Ihre nächste Vorgehensweise ermitteln:

-   Was ist der Gesamtfehler Prozentsatz für das Anruf Setup für den aktuellen Monat?

-   Ist der Prozentsatz der Gesamt Anrufeinrichtung unterhalb oder oberhalb der definierten Zielmetrik?

-   Ist der Fehlertrend schlechter oder besser als der vorherige Monat?

-   Wird der Fehlertrend immer größer, stetiger oder sinkender?

Ungeachtet der vorherigen Antworten sollten Sie sich die Zeit nehmen, um weitere Untersuchungen durchführen, indem Sie die begleitenden Unterberichte verwenden, um nach einzelnen Gebäuden oder Subnetzen zu suchen, die möglicherweise Behebungs bedürftig sind. Obwohl die Gesamtausfall Rate unter der Zielmetrik liegen kann, liegen die Fehlerraten für ein oder mehrere Gebäude oder Netzwerke möglicherweise oberhalb der Zielmetrik und müssen untersucht werden.

#### <a name="setup-failure-investigations"></a>Ermittlungen beim Setup Fehler 

Dieser Zusammenfassungsbericht wird verwendet, um alle Gebäude oder Netzwerke zu entdecken und zu isolieren, die möglicherweise Behebungs bedürftig sind.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Monatsberichts Filter auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den **Monats** Berichtsfilter an, um den neuen Standardmonat zu speichern.


![Screenshot mit Setupfehlern](media/qerguide-image-setupfailuresbysubnet.png)

_Abbildung 20: Fehler bei der Audioeinrichtung nach Subnetz_

##### <a name="remediation"></a>Wartung 

Konzentrieren Sie Ihre ersten Behebungs Bemühungen auf Gebäude oder Subnetze, die die größte Fehlermenge aufweisen. Dadurch werden die Auswirkungen auf die Benutzeroberfläche maximiert, und Sie können die Rate der Fehler bei der Einrichtung von Organisations anrufen schnell reduzieren. In der folgenden Tabelle sind die beiden Gründe für Setupfehler aufgeführt, die von CQD gemeldet wurden.

_Tabelle 7 – Gründe für Fehler bei der Anrufeinrichtung_

| Ursachen für Anruf Setup Fehler       | Typische Ursache                    |
|----------------------------------|----------------------------------|
| Fehlende FW Deep-Paket Prüf Befreiungs Regel | Gibt an, dass Netzwerkgeräte entlang des Pfads verhindert haben, dass der Medienpfad aufgrund umfassender Paket Inspektionsregeln eingerichtet wird. Dies ist wahrscheinlich auf Firewallregeln zurückzuführen, die nicht ordnungsgemäß konfiguriert sind. In diesem Szenario war der TCP-Handshake erfolgreich, doch der SSL-Handshake war nicht erfolgreich.      |
| Fehlende FW-IP-Blockierungs Ausnahmeregel      | Gibt an, dass Netzwerkgeräte entlang des Pfads verhindert haben, dass der Medienpfad im Office 365-Netzwerk eingerichtet wird. Dies kann auf Proxy-oder Firewallregeln zurückzuführen sein, die nicht ordnungsgemäß konfiguriert sind, um den Zugriff auf IP-Adressen und Ports zu ermöglichen, die für Teams und Skype for Business-Datenverkehr verwendet werden. |

Wenn Sie jetzt mit der Behebung beginnen, können Sie Ihre Bemühungen auf ein bestimmtes Gebäude oder Subnetz konzentrieren. Wie in der vorstehenden Tabelle zu sehen ist, sind diese Probleme auf Firewall-oder Proxy Konfigurationen zurückzuführen. Überprüfen Sie die Optionen in der folgenden Tabelle für Behebungsaktionen.

_Tabelle 8 – weitere Schritte zur Fehlerbehebung bei der Anrufeinrichtung_


|      Wartung      |                                                                                                                                                                                                                                                                                                                                                                   Anleitung                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Firewall (s) konfigurieren | Arbeiten Sie mit Ihrem Netzwerkteam zusammen, und überprüfen Sie Ihre Firewall (s)-Konfiguration mit [der Office 365-IP-Adressliste](https://aka.ms/o365ips).<br><br>Überprüfen Sie, ob die [Medien-Subnetze](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) und-Ports in den Firewall-Regeln enthalten sind. <br><br>Überprüfen Sie, ob die erforderlichen Anschlüsse (siehe unten) in der Firewall geöffnet sind. UDP sollte Vorrang eingeräumt werden, da TCP ein Failback-Protokoll für Audio-, Video-und videobasierte Bildschirm Übertragungen ist und sich die Nutzung auf die Qualität des Anrufs auswirkt. Die Legacy-RDP-Anwendungsfreigabe verwendet nur TCP.<br><ul><li>**TCP:** Port 443</li><li>**UDP:** Ports 3478 – 3481</li><ul> |
|        Prüfen         |                                                                                                                                                                                                                                                                 Verwenden Sie das [Tool Microsoft-Netzwerkbewertung](https://www.microsoft.com/download/details.aspx?id=53885) , um die Konnektivität aus dem betroffenen Gebäude oder Subnetz mithilfe der Funktion zur Überprüfung der Konnektivität zu überprüfen.                                                                                                                                                                                                                                                                  |

### <a name="drop-failures"></a>Abwurf Fehler

Im Gegensatz zu Setup-Fehlercodes hat CDQ keinen Absturzfehler Code, um anzugeben, warum Fehler auftreten, wodurch es schwierig ist, eine bestimmte Ursache zu isolieren. Verwenden Sie einen abgeleiteten Ansatz, um Abwurf Fehler besser zu selektieren. Wenn Sie alle Interessengebiete für Medien, Patches für Clients und Treiber sowie die Nutzung von zertifizierten Geräten für Teams und Skype for Business umsetzen, können Sie davon ausgehen, dass Fall Ausfälle abgelehnt werden.

#### <a name="drop-failure-trend-analysis"></a>Trendanalyse für Absturzfehler

In diesem Bericht werden die Gesamtmenge der Audiostreams, die Gesamtzahl der Fehler und die Fehlerrate für den Absturz angezeigt. Zeigen Sie auf eine der Spalten, um deren Werte anzuzeigen, wie in der folgenden Abbildung dargestellt. 

![Diagramm mit dem Prozentsatz der Datenströme, die gelöscht wurden](media/qerguide-image-droppedstreamrate.png)

_Abbildung 21 – gesunkene Datenstrom Rate_

##### <a name="analysis"></a>Analyse

Mithilfe dieser Art von Bericht können Sie die folgenden Fragen beantworten:

-   Was ist die aktuelle Absturz Rate?
-   Ist die Drop Failure-Rate unter der definierten Zielmetrik?
-   Ist der Fehlertrend schlechter oder besser als der vorherige Monat?
-   Wird der Fehlertrend immer größer, stetiger oder sinkender?

Ungeachtet der Antworten auf die obigen Fragen sollten Sie sich die Zeit nehmen, die Unterberichte zu untersuchen, um nach Gebäuden oder Netzwerken zu suchen, die möglicherweise Behebungs bedürftig sind. Obwohl sich die Gesamtausfall Rate des Abfalls möglicherweise unter der Zielmetrik befindet, liegt die Fehlerrate für ein oder mehrere Gebäude oder Netzwerke möglicherweise oberhalb der Zielmetrik und muss untersucht werden.

#### <a name="drop-failure-investigations"></a>Ermittlungen beim Absturz

Hier gemeldete Fehler deuten darauf hin, dass der Anruf unerwartet abgebrochen wurde und zu einer negativen Benutzererfahrung geführt hat. Im Gegensatz zu den Trendberichten bieten diese Berichte zusätzliche Einblicke in bestimmte Subnetze, die weiter untersucht werden müssen.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Monats Jahres Filter auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten**und dann **Monat Jahr** anpassen aus, um den neuen Standardmonat zu speichern.


![Bericht, der die Anzahl und den Prozentsatz der Ablage Fehler auflistet](media/qerguide-image-dropfailuresbysubnet.png)

_Abbildung 22 – Fehler beim Ablegen nach Subnetz_

##### <a name="remediation"></a>Wartung

Mithilfe der mitgelieferten Tabellen Berichte können Sie Problembereiche im Netzwerk isolieren, bei denen die Abwurf Rate über der von Ihnen definierten Zielmetrik liegt. Konzentrieren Sie Ihre ersten Behebungs Bemühungen auf Gebäude oder Subnetze, die die höchste Gesamtdaten Strom Anzahl aufweisen, um die größten Auswirkungen zu erzielen.

Häufige Ursachen für Anruf Abbrüche:

-   Unter bereitgestellte Netzwerk-oder Internet Ausgänge
-   Keine QoS-Konfiguration in abhängigen Netzwerken
-   Ältere Clientversionen
-   Benutzerverhalten

Nachdem Sie Ihre Problembereiche ermittelt haben, können Sie mithilfe der [anrufanalyse](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) die Benutzer in diesem Gebäude für bestimmte Probleme weiter überprüfen. Die anrufanalyse enthält zusätzliche PII-Daten und kann hilfreich sein, um mögliche Ursachen für die Fehler beim Ablegen weiter zu isolieren.

Unabhängig von Ihrem nächsten Schritt empfiehlt es sich, dem Helpdesk mitzuteilen, dass ein Problem mit bestimmten Gebäuden oder Subnetzen erkannt wurde. Auf diese Weise können Sie schnell auf eingehende Anrufe reagieren und Benutzer effizienter selektieren. Gekennzeichnete Benutzer können anschließend zur weiteren Untersuchung an das Entwicklungsteam zurückgemeldet werden.

In der folgenden Tabelle sind einige häufige Methoden zum Verwalten und Beheben von Ablage Fehlern aufgeführt.

_Tabelle 9 – nächste Schritte für die Wiederherstellung des Anruf Abfalls_

| Wartung                              | Anleitung                      |
|------------------------------------------|-------------------------------|
| **Netzwerk/Internet**                         | **Überlastung**: Arbeiten Sie mit Ihrem Netzwerkteam zusammen, um die Bandbreite in bestimmten Gebäuden/Subnetzen zu überwachen, um zu bestätigen, dass es Probleme mit der über Auslastung gibt. Wenn Sie sicherstellen, dass ein Netzwerkengpass vorliegt, sollten Sie die Bandbreite für dieses Gebäude erhöhen oder QoS anwenden. Verwenden Sie die [zusammen Fassungs Berichte "schlechte Qualität](#quality-investigations) ", um die problematischen Subnetze für Probleme mit Jitter, Latenz und Paketverlust zu überprüfen, da diese häufig einem gelöschten Datenstrom vorangestellt werden.<br><br>**QoS**: Wenn die zunehmende Bandbreite unpraktisch oder kostengünstig ist, sollten Sie die Implementierung von QoS in Frage stellen. Dieses Tool ist sehr effektiv bei der Verwaltung von über lastetem Datenverkehr und kann garantieren, dass Medienpakete im verwalteten Netzwerk Vorrang vor nicht-Mediendatenverkehr haben. Wenn es aber keinen eindeutigen Beweis dafür gibt, dass die Bandbreite der Täter ist, sollten Sie die folgenden Lösungen in Frage stellen:<ul><li>[QoS-Anleitung für Microsoft Teams](qos-in-teams.md)</li></ul><br>**Durchführen einer Netzwerk Eignungsbeurteilung**: eine Netzwerkbewertung enthält Details zur erwarteten Bandbreitennutzung, zur Bewältigung von Bandbreiten-und Netzwerkänderungen sowie Empfohlene Netzwerkmethoden für Teams und Skype for Business. Wenn Sie die vorhergehende Tabelle als Quelle verwenden, verfügen Sie über eine Liste von Gebäuden oder Subnetzen, die hervorragende Kandidaten für eine Bewertung sind.<ul><li>[Microsoft Teams-Netzwerk Bereitschaftsbewertung](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Microsoft Network Assessment Tool:** Mit diesem Tool können Sie einen einfachen Test der Netzwerkleistung durchführen, um festzustellen, wie gut das Netzwerk für ein Team oder einen Skype for Business Online-Anruf ist. Das Tool hilft Ihnen, die Leistung eines Subnetzes zu bewerten und die Bereitschaft des Netzwerks gegen die Microsoft-Leistungs [Anforderungen](https://aka.ms/performancerequirements)zu überprüfen.<ul><li>[Herunterladen des Netzwerk Bewertungstools](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul> |
| **Clients (nur Skype for Business Online)** | Einige ältere Clients haben bekannte Probleme mit der Medien Zuverlässigkeit dokumentiert. Überprüfen Sie die anrufanalyse Berichte von mehreren betroffenen Benutzern, oder erstellen Sie einen benutzerdefinierten Bericht zur Client Versionstabelle in CQD, der auf bestimmte Gebäude oder Subnetze gefiltert wurde, wobei Gesamtausfall%-Fehler% gemessen wurde. Diese Informationen werden Ihnen helfen zu verstehen, ob eine Beziehung zwischen Anruf Abbrüchen in diesem bestimmten Gebäude und einer bestimmten Version des Clients besteht.     |
| **Geräte**                                  | Wir empfehlen, dass alle Benutzer, die mit Anruf Abbrüchen konfrontiert sind – oder schlechte Anrufe im allgemeinen – und integrierte Geräte verwenden, ein [zertifiziertes Headset oder eine Freisprecheinrichtung](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) bereitstellen, um dies als potenzielle Quelle für schlechte Qualität und Zuverlässigkeit zu eliminieren. |
| **Benutzerverhalten**                            | Wenn Sie feststellen, dass es sich nicht um ein Netzwerk, Geräte oder Clients handelt, sollten Sie die Entwicklung einer Strategie für die Benutzereinführung in den Mittelpunkt stellen, um Benutzer zu informieren, wie Sie Besprechungen am besten teilnehmen und beenden Eine intelligentere Teams und ein Skype for Business-Benutzer werden für alle Teilnehmer der Besprechung eine bessere Benutzererfahrung bieten. Ein Benutzer, der seinen Laptop in den Standbymodus versetzt (durch Schließen des Deckels), ohne die Besprechung zu beenden, wird als unerwarteter Anruf Rückgang eingestuft.   |

## <a name="quality-investigations"></a>Qualitätsuntersuchungen

Der nächste Schritt zur Beurteilung des Zustands der Audioqualität in der gesamten Organisation besteht darin, die Verwendung schlechter Datenstrom Rate (PSR), TCP und Proxy zu untersuchen. Beachten Sie, dass CQD-Daten Ihnen keine spezifische Ursache liefern, sondern Ihnen wahrscheinlich Problembereiche bereitstellen, um eine gemeinsame Unterhaltung mit den entsprechenden Teams für Behebungs Aktivitäten zu beginnen. 

> [!NOTE]
> In diesem Leitfaden werden nicht alle Berichte behandelt, die in den Vorlagen enthalten sind. die unten erläuterten Ermittlungsmethoden gelten jedoch weiterhin für diese Berichte. Weitere Informationen finden Sie in der Beschreibung für den einzelnen Bericht. 

### <a name="quality"></a>Qualität

Die PSR-Prozentwerte werden verwendet, um anzugeben, ob die Organisation definierte metrische Ziele für einen bestimmten Fokusbereich erfüllt. Es ist wichtig zu beachten, dass einzelne Subnetze oder Gebäude möglicherweise nicht den definierten Zielen entsprechen und daher weitere Untersuchungen benötigen, selbst wenn sich die Prozentsätze auf höherer Ebene innerhalb des definierten Ziels befinden. Wenn beispielsweise der Gesamt-Audio-PSR-Prozentsatz im April 2 Prozent beträgt, was dem Beispiel Ziel entspricht, können einzelne Gebäude und Subnetze in Abhängigkeit von der Gesamtverteilung dieser 2 Prozent weiterhin schlechte Erfahrungen aufweisen. 

Verwenden Sie die Qualitätsberichte, um den Prozentsatz schlechter Datenströme zu bewerten. Es werden verschiedene Qualitätsberichte bereitgestellt, um Metriken für Gesamt-, Konferenz-, zwei Parteien-, PSTN-Anrufe, VPN und Besprechungsräume zu überprüfen. Monatliche, wöchentliche und tägliche Berichte werden zur Unterstützung dieses Prozesses bereitgestellt. Wöchentliche und tägliche Berichte sind auf die Vorlage für verwaltete Netzwerke eingeschränkt, um deren Effektivität zu erhöhen und die Geräuschentwicklung zu verringern. 

#### <a name="quality-trend-analysis"></a>Qualitätstrend Analyse

Trendberichte zeigen Qualitätsinformationen im Laufe der Zeit an und werden verwendet, um qualitätstrends in den einzelnen Interessengebieten zu erkennen und zu verstehen. Wie bereits erwähnt, gibt es Berichtsbäume, die in den Vorlagen zur Untersuchung von Qualität enthalten sind. Konferenzen, zwei Parteien, PSTN-Anrufe, VPN und Besprechungsräume. Zum Zweck der Analyse der Qualität ist der Ermittlungsprozess identisch. Es wird jedoch empfohlen, zunächst mit Conferencing zu beginnen, da sich die Verbesserungen bei der Konferenz Qualität auch positiv auf alle anderen Bereiche auswirken. 

> [!Note]
> Die Untersuchung von zwei Parteien, PSTN-anrufen und Besprechungsräumen ist mit der Untersuchung von Konferenzen vergleichbar. Der Fokus liegt auf der isloate von Gebäuden oder Subnetzen, die die schlechteste Qualität aufweisen, und die Ursache für die schlechte Qualität zu identifizieren.

> [!Important]
> VPN-basierte Berichte werden mithilfe der zweiten VPN-Dimension gefiltert. Für diese Dimension muss der VPN-Netzwerkadapter ordnungsgemäß als Remote Zugriffs Adapter registriert sein. VPN-Anbieter verwenden dieses Flag nicht zuverlässig, und ihre Kilometerleistung hängt vom VPN-Anbieter ab, der in Ihrer Organisation bereitgestellt wird. Befolgen Sie die Anleitungen [weiter oben in diesem Leitfaden](#vpn) , um die VPN-Berichte bei Bedarf mithilfe des Gebäude-oder Netzwerk namens zu ändern.

![Diagramm mit dem Prozentsatz der Datenströme in schlechter Qualität](media/qerguide-image-audioqualityconferencing.png)

_Abbildung 23 – Audioqualität – Konferenzen_

##### <a name="investigation"></a>Untersuchungs

Mithilfe dieser Berichte können Sie die folgenden Fragen beantworten:

-   Was ist der Gesamtwert b.a. für den aktuellen Monat?
-   Ist die PSR unter der definierten Zielmetrik?
-   Ist PSR schlechter oder besser als der vorherige Monat?
-   Wird der PSR-Trend immer größer, stabiler oder sinkender?

Ungeachtet der Antworten auf die obigen Fragen sollten Sie sich die Zeit nehmen, die Unterberichte zu verwenden, um nach Gebäuden oder Subnetzen zu suchen, die möglicherweise untersucht werden müssen. Obwohl sich das allgemeine PSR unter der Zielmetrik befinden kann, liegt der PSR für ein oder mehrere Gebäude oder Netzwerke häufig über der Metrik und muss wiederhergestellt werden.

#### <a name="quality-investigations"></a>Qualitätsuntersuchungen

Die Berichte zur Qualitäts Zusammenfassung geben Ihnen einen tieferen Einblick in die Beiträge, die dazu beigetragen haben, dass die Streams als "schlecht" klassifiziert wurden, und helfen dabei, Problembereiche im verwalteten Netzwerk zu isolieren.

Obwohl sich die verwendeten Dimensionen Zwischenbericht etwas unterscheiden können, enthält jeder Bericht Measures für Gesamtdaten Ströme, schlechte Gesamt Ströme, PSR und schlechte Qualität aufgrund von. Für jeden Interessenbereich wurden Berichte erstellt: Konferenzen, zwei Parteien, PSTN-Anrufe, VPN und Besprechungsräume. Die Vorlage "verwaltetes Netzwerk" enthält zusätzliche Berichte, um die Standortinformationen zu nutzen, die über die Building-Datei hochgeladen wurden.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Monats Jahres Filter auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten**und dann **Monat Jahr** anpassen aus, um den neuen Standardmonat zu speichern.

> [!Note]
> Häufig verwendete Subnetze sind aufgrund der weit verbreiteten Verwendung schwer zu selektieren. Ein separater Bericht, in dem die öffentliche IP-Adresse des Clients (zweite reflexive lokale IP-Adresse) angezeigt wird, wurde zur Vorlage "alle Netzwerke" hinzugefügt, um die Remediation von Offices zu unterstützen, die allgemeine Netzwerke


![Screenshot der unzureichenden Audiostream-Zusammenfassung](media/qerguide-image-poorqualitysummary.png)

_Abbildung 24 – schlechte Audiostream-Zusammenfassung durch Gebäude-und Subnet-Conferencing_

##### <a name="remediation"></a>Wartung

Konzentrieren Sie Ihre Behebungs Bemühungen auf Gebäude oder Subnetze mit dem größten Volumen an Datenströmen, denn dadurch werden die Auswirkungen maximiert, und Sie können die Benutzerfreundlichkeit schnell verbessern. Verwenden Sie die Messungen Jitter, Paketverlust und Roundtrip-Zeit (Round-Trip Time, RTT), um zu verstehen, was zu einer schlechten Qualität beiträgt (es ist möglich, dass mehrere Probleme auftreten):

-   **Jitter**: Medienpakete werden mit unterschiedlichen Geschwindigkeiten angekommen, was dazu führt, dass ein Lautsprecher zu einem robotischen Klang führt.
-   **Paketverlust**: Medienpakete werden gelöscht, wodurch der Effekt fehlender Wörter oder Silben entsteht.
-   **RTT**: Medienpakete nehmen lange Zeit in Anspruch, um zu Ihrem Ziel zu gelangen, wodurch ein Walkie-Talkie-Effekt entsteht.

Um die Untersuchung von Qualitätsproblemen zu unterstützen, können Sie die [anrufanalyse](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)nutzen. Mit der anrufanalyse können Sie eine bestimmte Konferenz oder einen detaillierten Anrufbericht der Benutzer betrachten. Dieser Bericht enthält PII-Daten und ist hilfreich, wenn Sie nach der Ursache eines Fehlers suchen. Nachdem Sie wissen, welche Gebäude betroffen sind, sollte es einfach sein, Benutzer in diesem Gebäude nachvollziehen zu können. 

Vergessen Sie nicht, dem Helpdesk mitzuteilen, dass bei diesen Netzwerken Qualitätsprobleme auftreten, damit Sie eingehende Anrufe schnell selektieren und beantworten können.

_Tabelle 10 – häufige Mitwirkende für "hoher PSR"_

| Wartung                              | Anleitung                         |
|------------------------------------------|----------------------------------|
| **Netzwerke**                                 | Überlastung: ein über **lastetes**oder unter bereitgestelltes Netzwerk kann zu Problemen mit der Medienqualität führen. Arbeiten Sie mit dem Netzwerkteam zusammen, um festzustellen, ob die Netzwerkverbindungen des Benutzers mit dem Internet-Ausgangspunkt genügend Bandbreite zur Unterstützung von Medien aufweisen. <br><br>**Durchführen einer Netzwerk Eignungsbeurteilung**: eine Netzwerkbewertung enthält Details zur erwarteten Bandbreitennutzung, zur Bewältigung von Bandbreiten-und Netzwerkänderungen sowie Empfohlene Netzwerkmethoden für Teams und Skype for Business. Wenn Sie die vorhergehende Tabelle als Quelle verwenden, verfügen Sie über eine Liste von Gebäuden oder Subnetzen, die hervorragende Kandidaten für eine Bewertung sind.<ul><li>[Microsoft Teams-Netzwerk Bereitschaftsbewertung](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Microsoft Network Assessment Tool:** Mit diesem Tool können Sie einen einfachen Test der Netzwerkleistung durchführen, um festzustellen, wie gut das Netzwerk für ein Team oder einen Skype for Business Online-Anruf ist. Das Tool hilft Ihnen, die Leistung eines Subnetzes zu bewerten und die Bereitschaft des Netzwerks gegen die Microsoft-Leistungs [Anforderungen](https://aka.ms/performancerequirements)zu überprüfen.<ul><li>[Herunterladen des Netzwerk Bewertungstools](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br> |
| **Quality of Service (QoS)**  | QoS ist ein bewährtes Tool, mit dem Sie Pakete in einem überlasteten Netzwerk priorisieren können, um sicherzustellen, dass Sie intakt und pünktlich an Ihrem Zielort ankommen. Sie sollten QoS in Ihrer Organisation implementieren, um die Qualität der Benutzerfreundlichkeit zu maximieren, bei der die Bandbreite beschränkt ist. QoS hilft bei der Lösung von Problemen, die in der Regel mit einem hohen Paketverlust verbunden sind, und – in geringerem Maße – Jitter-und Roundtrip-Zeiten.<ul><li>[QoS-Anleitung für Microsoft Teams](qos-in-teams.md)</li></ul> |
| **WLAN**               | Wi-Fi kann sich erheblich auf die Anrufqualität auswirken. Wi-Fi-Bereitstellungen berücksichtigen in der Regel nicht die Netzwerkanforderungen für VoIP-Dienste und sind häufig eine Quelle schlechter Qualität. Weitere Informationen zum Optimieren Ihrer Wi-Fi-Infrastruktur finden Sie in [diesem Artikel über die WLAN-Planung](/skypeforbusiness/certification/plan-wifi).<br><br>**WLAN-Treiber**: Stellen Sie sicher, dass drahtlose Treiber auf dem neuesten Stand sind. Auf diese Weise können Sie eine unzureichende Benutzererfahrung im Zusammenhang mit einem veralteten Treiber reduzieren. Viele Organisationen schließen keine WLAN-Treiber in Ihre Patch-Zyklen ein, und diese Treiber können jahrelang ungepatcht bleiben. Viele WLAN-Probleme werden behoben, indem Sie sicherstellen, dass die WLAN-Treiber auf dem neuesten Stand sind.<br><br>**WMM**: drahtlose Multimedia-Erweiterungen (WMM), auch bekannt als WLAN-Multimedia, bietet grundlegende QoS-Funktionen für drahtlose Netzwerke. Moderne drahtlose Netzwerke müssen viele Geräte unterstützen. Diese Geräte konkurrieren um die Bandbreite und können zu Qualitätsproblemen für VoIP-Dienste führen, bei denen Geschwindigkeit und Latenz wichtig sind. Erkundigen Sie sich bei Ihrem Mobilfunkanbieter nach Einzelheiten, und ziehen Sie die Implementierung von WMM in Ihrem Drahtlosnetzwerk in Frage, um Skype for Business-und Team Medien zu priorisieren.<br><br>**Zugriffspunkt Dichte**: die Zugriffspunkte sind möglicherweise zu weit auseinander oder nicht an einem idealen Ort. Um mögliche Interferenzen zu minimieren, platzieren Sie zusätzliche Zugriffspunkte in Konferenzräumen und an Orten, die nicht von Wänden oder anderen Objekten behindert werden, bei denen das WLAN-Signal schwach ist.<br><br>**2,4 GHz versus 5 GHz**: 5 GHz bietet geringere Hintergrundstörungen und höhere Geschwindigkeiten und sollte bei der Bereitstellung von VoIP über WLAN priorisiert werden. 5 GHz ist jedoch nicht so stark wie 2,4 GHz und dringt nicht so einfach in die Wände ein. Überprüfen Sie Ihr Gebäude Layout, um festzustellen, auf welche Häufigkeit Sie für die beste Verbindung vertrauen können. |
|**Netzwerkgerät** | Größere Organisationen haben möglicherweise Hunderte von Geräten, die über das Netzwerk verteilt sind. Arbeiten Sie mit Ihrem Netzwerkteam zusammen, um sicherzustellen, dass die Netzwerkgeräte des Benutzers mit dem Internet verwaltet und auf dem neuesten Stand sind. |
| **VPN**  | VPN-Appliances sind traditionell nicht für die Behandlung von Medien Auslastungen in Echtzeit konzipiert. Einige VPN-Konfigurationen untersagen die Verwendung von UDP (das bevorzugte Protokoll für Medien) und beruhen nur auf TCP. Sie sollten eine VPN-Split-Tunnel-Lösung implementieren, um VPN als Quelle schlechter Qualität zu reduzieren. |
| **Clients** <br>(Nur Skype for Business Online) | Stellen Sie sicher, dass alle Clients regelmäßig aktualisiert werden. |
| **Geräte** | Durch die Verwendung [optimierter Geräte](https://partnersolutions.skypeforbusiness.com/solutionscatalog) kann die Benutzererfahrung deutlich verbessert werden. Da alle Dinge gleich sind, wurden optimierte Geräte entwickelt, um die Benutzererfahrung mit Teams und Skype for Business zu maximieren und hervorragende Qualität zu erzielen. |
| **Treiber** | Patching-Netzwerk (Ethernet und WLAN), Audio-, Video-und USB-Treiber sollten Teil ihrer allgemeinen Patch-Verwaltungsstrategie sein. Viele Qualitätsprobleme werden durch Aktualisieren der Treiber behoben. |
| **Konferenzräume für WLAN** | Wir empfehlen dringend, dass Besprechungsraum Geräte über mindestens eine 1-Gbit/s-Ethernet-Verbindung mit dem Netzwerk verbunden sind. Besprechungsraum Geräte umfassen in der Regel mehrere Audio-und Videostreams sowie Besprechungsinhalte wie Bildschirmfreigabe und höhere Netzwerkanforderungen als andere Teams oder Skype for Business-Endpunkte. Besprechungsräume sind definitionsgemäß stationäre Geräte, bei denen Wi-Fi nur während der Installation einen Vorteil bietet.<br><br>Besprechungsräume müssen mit besonderem Interesse behandelt werden, um sicherzustellen, dass die Erfahrungen mit diesen Geräten die Erwartungen erfüllen oder übertreffen. Qualitätsprobleme mit Besprechungsräumen werden in der Regel schnell eskaliert, da Sie häufig von Mitarbeitern auf leitenden Ebenen verwendet werden.<br><br>Da alle Dinge gleich sind (abgesehen von der Bequemlichkeit), ist die WLAN-Leistung oft kleiner als eine Kabelverbindung. Mit dem Aufkommen von Richtlinien für "eigenes Gerät bringen" und der Verbreitung von Laptops sind WLAN-Zugriffspunkte häufig überlastet. Echt Zeit Medien werden in WLAN-Netzwerken möglicherweise nicht priorisiert, was zu Qualitätsproblemen während der Spitzennutzungszeiten führen kann. Diese schwerwiegende Nutzung kann mit einer Besprechung zusammenfallen, in der ein Dutzend Personen anwesend sein können, die jeweils über einen eigenen Laptop und ein Smartphone verfügen, die alle mit dem gleichen WLAN-Zugriffspunkt wie dem Besprechungsraum Gerät verbunden sind.<br><br>WLAN sollte nur als vorübergehende Lösung für eine mobile Installation oder, wenn die WLAN-Verbindung ordnungsgemäß bereitgestellt wurde, für die Unterstützung von echtzeitbasierten Medien auf Unternehmensniveau gelten. |


### <a name="tcp"></a>TCP

TCP gilt als Failback-Transport und nicht als primärer Transport für echt Zeit Medien. Der Grund dafür ist ein Failback-Transport, der auf die Stateful-Art von TCP zurückzuführen ist. Wenn beispielsweise ein Anruf in einem latenten Netzwerk erfolgt und die Medienpakete verzögert werden, konkurrieren die Pakete vor ein paar Sekunden, die nicht mehr nützlich sind, um die Bandbreite, um zum Empfänger zu gelangen, was eine schlechte Situation verschlimmern kann. Dadurch wird der audioheiler Stich-und Dehnungs-Audio, was zu hörbaren Artefakten führt, oft in Form von Jitter.

In den Berichten in diesem Abschnitt wird nicht zwischen guten und schlechten Datenströmen unterschieden. Da UDP bevorzugt wird, suchen die Berichte die Verwendung von TCP für Audio-, Video-und videobasierte Bildschirm Freigaben (schlechte VBSS). Es werden schlechte Datenstrom Raten bereitgestellt, die dazu beitragen, die UDP-Qualität im Vergleich zur TCP-Qualität zu vergleichen, damit Sie Ihre Bemühungen konzentrieren können, wenn die Auswirkungen am größten sind. Die TCP-Nutzung wird in erster Linie durch unvollständige Firewallregeln verursacht. Weitere Informationen zu Firewallregeln für Teams und Skype for Business Online finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips).

> [!Important]
> Wenn Sie eine [gültige Gebäude Datei](#building-mapping) hochgeladen haben, wird dringend empfohlen, damit Sie schnell innerhalb von externen Streams unterscheiden können, wenn Sie die TCP-Nutzung betrachten.

> [!Note]
> Audio-, Video-und schlechte VBSS bevorzugen UDP als primären Transport. Die ältere RDP-Anwendungsfreigabe-Arbeitsauslastung verwendet nur TCP.

#### <a name="tcp-usage"></a>TCP-Nutzung

TCP-Berichte kennzeichnet die gesamte TCP-Nutzung in den letzten sieben Monaten. Alle weiteren Berichte in diesem Abschnitt konzentrieren sich auf die Eingrenzung bestimmter Gebäude und Subnetze, in denen TCP am häufigsten verwendet wird. Getrennte Berichte sind sowohl für Konferenz-als auch für zwei Parteien-Streams verfügbar.

![Diagramm mit dem Prozentsatz der Audiostreams,](media/qerguide-image-audiostreamswithtcp.png)
die TCP verwenden_Abbildung 25 – audiodatendateien mit TCP-Nutzung_


##### <a name="investigation"></a>Untersuchungs

Mit diesem Bericht können Sie die folgenden Fragen beantworten:

-   Was ist das Gesamtvolumen der TCP-Streams für den aktuellen Monat?
-   Ist es schlechter oder besser als im vorherigen Monat?
-   Wird der TCP-Nutzungs Trend immer größer, stetiger oder sinkender?
-   Ist der TCP PSR identisch mit meinem gesamten PSR?

Wenn Sie feststellen, dass der TCP-Nutzungs Trend zunimmt oder über der normalen monatlichen Nutzung liegt, nehmen Sie sich die Zeit, die Unterberichte zu untersuchen, um nach Gebäuden oder Netzwerken zu suchen, die möglicherweise Behebung benötigen. Im Idealfall möchten Sie im verwalteten Netzwerk so wenige TCP-basierte audiositzungen wie möglich haben.

#### <a name="tcp-vs-udp"></a>TCP vs. UDP

Dieser Bericht identifiziert die Lautstärke der TCP-und UDP-Nutzungsberichterstattung für den letzten Monat für Audio-, Video-und videobasierte Bildschirmfreigabe (schlechte VBSS). 

![Bericht mit den Datenströmen, die TCP und UDP verwenden](media/qerguide-image-tcpvsudp.png)

_Abbildung 26 – TCP vs. UDP – Konferenzen_

##### <a name="analysis"></a>Analyse

Obwohl die TCP-Nutzung so gering wie möglich sein soll, wird bei einer ansonsten fehlerfreien Bereitstellung möglicherweise ein Bit der TCP-Nutzung angezeigt. TCP selbst trägt nicht zu einem schlechten Anruf bei, daher werden Datenstrom Gebühren bereitgestellt, um zu ermitteln, ob die TCP-Nutzung einen Beitrag zu schlechter Qualität leistet. 

#### <a name="tcp-investigations"></a>TCP-Untersuchungen

Navigieren Sie in den bereitgestellten CQD-Vorlagen zu den TCP-Datenströmen, indem Sie Berichte erstellen und Subnets verwenden, indem Sie entweder die Vorlage verwaltete Netzwerke oder alle Netzwerke verwenden. Zum Zweck der Untersuchung der TCP-Nutzung ist der Prozess derselbe, daher konzentrieren wir die Diskussion hier auf Konferenzen.

> [!IMPORTANT]
> Es wird empfohlen, eine gültige [Gebäude Datei](#building-mapping) hochgeladen zu haben, damit Sie schnell innerhalb von externen Streams unterscheiden können, wenn Sie die TCP-Nutzung betrachten. 

> [!NOTE]
> Stellen Sie sicher, dass Sie den Monats Jahres Filter auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten**und dann **Monat Jahr** anpassen aus, um den neuen Standardmonat zu speichern.                                  |

![Screenshot der TCP-Nutzung durch Gebäude und Subnetz](media/qerguide-image-tcpstreams.png)

_Abbildung 27 – TCP-Streams nach Gebäude-und Subnet-Conferencing_

##### <a name="remediation"></a>Wartung

In diesem Bericht werden bestimmte Gebäude und Subnetze identifiziert, die zum Volumen der TCP-Nutzung beitragen. Darüber hinaus wird ein zusätzlicher Bericht zur Identifizierung der im Anruf verwendeten Microsoft Relay-IP-Adresse angezeigt, die die Isolierung fehlender Firewall-Regeln unterstützt. Konzentrieren Sie Ihre Behebungs Bemühungen auf jene Gebäude, die das höchste Aufkommen an TCP-Streams haben, um die Auswirkungen zu maximieren.

Die häufigste Ursache für die TCP-Nutzung sind fehlende Ausnahmeregeln in Firewalls oder Proxys. Im nächsten Abschnitt werden wir über Proxys sprechen, also konzentrieren Sie sich jetzt auf die Firewalls. Wenn Sie das bereitgestellte Gebäude oder Subnetz verwenden, können Sie ermitteln, welche Firewall aktualisiert werden muss.


_Tabelle 11 – Korrekturhilfen für TCP-Streams nach Gebäude und Subnetz_

| Wartung        | Anleitung     |
|--------------------|--------------------------------------|
| Firewall konfigurieren | Überprüfen Sie, ob die [IP-Ports und-Adressen von Office 365](https://aka.ms/o365ips) von Ihrer Firewall ausgeschlossen werden. Konzentrieren Sie sich bei medienbezogenen TCP-Problemen zunächst auf Folgendes:<ul><li>Überprüfen Sie, ob sich die Client Medien-Subnetze 13.107.64.0/18 und 52.112.0.0/14 in ihren Firewallregeln befinden.</li><li>UDP-Ports 3478 – 3481 sind die erforderlichen Medienanschlüsse und müssen geöffnet werden, andernfalls wird der Client zurück zum TCP-Port 443.</li></ul> |
| Prüfen             | Verwenden Sie das [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) , um Probleme mit der Konnektivität zu bestimmten Office 365-IP-Adressen und Ports aus dem betroffenen Gebäude oder Subnetz zu überprüfen.    |

### <a name="http-proxy"></a>HTTP-Proxy

HTTP-Proxys sind aus einer Vielzahl von Gründen nicht der bevorzugte Pfad zum Einrichten von Mediensitzungen. Viele enthalten umfassende Funktionen zur Paketüberprüfung, die verhindern, dass Verbindungen mit dem Dienst abgeschlossen werden und Unterbrechungen eingeführt werden. Darüber hinaus erzwingen fast alle Proxys TCP im Gegensatz zum Zulassen von UDP, was für optimale Audioqualität empfohlen wird.

Wir empfehlen immer, den Client so zu konfigurieren, dass er direkt mit Teams und Skype for Business-Diensten verbunden ist. Dies ist besonders wichtig für medienbasierten Datenverkehr.


> [!IMPORTANT]
> Wenn Sie eine gültige [Gebäude Datei](#building-mapping) hochgeladen haben, können Sie bei der Analyse der Proxy Nutzung problemlos innerhalb von externen Audiostreams unterscheiden. 


#### <a name="http-proxy-usage"></a>HTTP-Proxyverwendung

Der HTTP-Proxy-Datenstrom Bericht in diesem Abschnitt der Vorlage ähnelt ähnlich wie die TCP-Berichte. Es wird nicht untersucht, ob Anrufe schlecht oder gut sind, sondern ob der Anruf über HTTP verbunden ist.

![Screenshot des Berichts über Audiostreams, die HTTP verwenden](media/qerguide-image-audiostreamswithhttp.png)

_Abbildung 28 – Audiostreams mit http-Proxy Verwendung_

##### <a name="analysis"></a>Analyse

Sie möchten so wenig http-Mediendatenströme wie möglich sehen. Wenn Sie über Streams verfügen, die Ihren Proxy durchlaufen, konsultieren Sie Ihr Netzwerkteam, um sicherzustellen, dass die richtigen Ausschlüsse vorhanden sind, damit Clients direkt an Teams oder Skype for Business Online-Medien Subnetze weiterleiten.

Wenn in Ihrer Organisation nur ein Internet Proxy vorhanden ist, überprüfen Sie die korrekten [Office 365-URLs und-Ausnahmen für den IP-Adressbereich](https://aka.ms/o365ips). Wenn in Ihrer Organisation mehr als ein Internet Proxy konfiguriert ist, verwenden Sie den HTTP-Unterbericht, um zu isolieren, welches Gebäude oder Subnetz betroffen ist.

Für Organisationen, die den Proxy nicht umgehen können, stellen Sie sicher, dass der Skype for Business-Client so konfiguriert ist, dass er sich ordnungsgemäß anmeldet, wenn er sich hinter einem Proxy befindet, wie in dem Artikel beschrieben, den [Skype for Business Proxy Server für die Anmeldung verwenden soll, anstatt eine direkte Verbindung zu versuchen](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>HTTP-Proxy Ermittlungen

In diesem Bericht werden bestimmte Gebäude und Subnetze identifiziert, die zur HTTP-Nutzung beitragen.

> [!IMPORTANT]
> Wenn Sie eine gültige [Gebäude Datei](#building-mapping) hochgeladen haben, können Sie bei der Analyse der Proxy Nutzung problemlos innerhalb von externen Audiostreams unterscheiden.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Monats Jahres Filter auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten**und dann **Monat Jahr** anpassen aus, um den neuen Standardmonat zu speichern.

![Sreen shot des Berichts zur HTTP-Proxy Verwendung nach Gebäude und Subnetz](media/qerguide-image-httpproxyusage.png)

_Abbildung 29 – http-Proxy Verwendung nach Gebäude und Subnetz_

##### <a name="remediation"></a>Wartung

Wir [empfehlen](proxy-servers-for-skype-for-business-online.md) , dass Sie immer Proxys für Skype for Business und Teams, insbesondere für den Medien Verkehr, umgehen. Proxys machen Skype for Business nicht sicherer, da der Datenverkehr bereits verschlüsselt ist. Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen. Probleme wie diese führen zu einer negativen Erfahrung mit Audio-, Video-und Bildschirmübertragung, bei der echt Zeitströme wichtig sind.

Die häufigste Ursache für die HTTP-Nutzung sind fehlende Ausnahmeregeln in Proxys. Wenn Sie das bereitgestellte Gebäude oder Subnetz verwenden, können Sie schnell ermitteln, welcher Proxy für die medienumgehung konfiguriert werden muss.

Überprüfen Sie, ob die erforderlichen [Office 365-FQDNs](https://aka.ms/o365ips) in Ihrem Proxy whitelisted sind.

## <a name="endpoint-investigations"></a>Endpunkt Ermittlungen

In diesem Abschnitt werden die Aufgaben für die Berichterstellung für Clientversionen und die Verwendung zertifizierter Geräte erläutert. Berichte stehen zur Verfügung, um die Verwendung von Clientversionen, Clienttyp, Aufnahmegeräten und Treibern (Mikrofon), Videoaufnahmegeräten und WLAN-Anbietern sowie Treiberversionen zu gliedern.

> [!NOTE]
> In diesem Leitfaden werden nicht alle Berichte behandelt, die in den Vorlagen enthalten sind. die unten erläuterten Methoden der Untersuchung gelten jedoch weiterhin. Weitere Informationen finden Sie in der Beschreibung für den einzelnen Bericht.

### <a name="client-versions"></a>Client Versionen

Die Berichte in diesem Bereich konzentrieren sich auf die Ermittlung der verwendeten Skype for Business-Clientversionen und deren relative Lautstärke in der Umgebung.

> [!IMPORTANT]
> Derzeit werden Teams-Clients automatisch über das Azure Content Delivery Network verteilt und aktualisiert und vom Dienst auf dem neuesten Stand gehalten. Client Bereitschaft und Ermittlungsaktivitäten gelten nicht für Teams.

> [!Important]
> Sofern Sie keine Verbund Teilnehmerdaten ausschließen, enthalten diese Berichte die Client-Telemetrie von verbundenen Endpunkten. Zum Ausschließen von Verbundendpunkten müssen Sie einen [Abfragefilter](#query-filters) für die zweite Mandanten-ID für die [Mandanten-ID](#tenant-id)Ihrer Organisation hinzufügen. Alternativ können Sie einen URL- [Filter](#url-filter) verwenden, um die Telemetrie für Teilnehmer auszuschließen.

> [!NOTE]
> Stellen Sie sicher, dass Sie den Monats Jahres Filter auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten**und dann **Monat Jahr** anpassen aus, um den neuen Standardmonat zu speichern.

![Screenshot des Berichts "Client und Geräte"](media/qerguide-image-clientversionreport.png)

_Abbildung 30 – Bericht zur Client Version_

#### <a name="remediation"></a>Wartung

Ein wichtiger Bestandteil beim führen von Benutzeroberflächen mit hoher Qualität ist die Gewährleistung, dass verwaltete Clients aktuelle Versionen von Skype for Business ausführen, und dass die unterstützenden Audio-, Video-, Netzwerk-und USB-Treiber auf dem neuesten Stand sind. Dies bietet mehrere Vorteile, darunter: 

-   Es ist einfacher, einige Versionen im Vergleich zu vielen Versionen zu verwalten.
-   Es bietet ein Maß an Konsistenz der Benutzerfreundlichkeit.
-   Es vereinfacht die Behandlung von Problemen mit der Anrufqualität und-Usability.
-   Microsoft führt kontinuierlich allgemeine Verbesserungen und Optimierungen im gesamten Produkt durch. Wenn Sie sicherstellen, dass Benutzer diese Updates erhalten, verringert sich das Risiko, dass ein Problem bereits gelöst ist.

Wenn Sie die Bereitstellung auf Clientversionen beschränken, die weniger als sechs Monate alt sind, verbessern Sie die Gesamtbenutzer Erfahrung und verbessern die Verwaltbarkeit, indem Sie die Anzahl der Versionen verringern, die unterstützt werden müssen.

Wenn Sie nur Office Klick-und-Los verwenden, befinden Sie sich automatisch im sechsmonatigen Fenster. Es ist keine weitere Aktion erforderlich.

Wenn Sie über eine Kombination aus Klick-und-Los-und Installationspaketen (MSI) verfügen, können Sie den Bericht verwenden, um zu überprüfen, ob die MSI-Clients regelmäßig aktualisiert werden. Wenn Sie feststellen, dass Clients zurückfallen, arbeiten Sie mit dem Team, das für die Verwaltung von Office-Updates verantwortlich ist, und stellen Sie sicher, dass Client-Patches regelmäßig genehmigt und bereitgestellt werden

Darüber hinaus ist es wichtig, zu prüfen und sicherzustellen, dass die Netzwerk-, Video-, USB-und Audiotreiber ebenfalls gepatcht werden. Es ist einfach, diese Treiber zu übersehen und Sie nicht in Ihre Patch-Verwaltungsstrategie einzubeziehen.

Versionsnummern für Skype for Business finden Sie über die folgenden Links:

-   [Freigeben von Informationen für Updates von Office ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Update Verlauf für Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Skype for Business – Downloads and Updates](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Geräte

Für die Verwendung des Mikrofon Geräte Berichts müssen wir das Konzept des mittleren Meinungs Bewertungs Faktors verstehen. MOS ist die Gold Standardmessung, um die wahrgenommene Klangqualität zu messen. Sie wird als ganzzahlige Bewertung von 0 bis 5 dargestellt.

Die Grundlage aller Maßnahmen der Sprachqualität ist, wie eine Person die Qualität der Sprache wahrnimmt. Weil es von der menschlichen Wahrnehmung beeinflusst wird, ist es inhärent subjektiv. Es gibt verschiedene Methoden für die subjektive Prüfung. Die meisten Measures für die Sprachqualität basieren auf einer absoluten Kategorisierungs Bewertungsskala (ACR).

In einem ACR-subjektiven Test wird eine statistisch signifikante Anzahl von Personen auf einer Skala von 1 (schlecht) bis 5 (hervorragend) die Qualität ihrer Erfahrungen beurteilen. Der Mittelwert der Kerben ist der Mos. Der resultierende Mos hängt vom Bereich der Erfahrungen ab, die für die Gruppe verfügbar gemacht wurden, und von der Art der bewerteten Erfahrung.

Da es unpraktisch ist, subjektive Tests der Sprachqualität für ein Live-Kommunikationssystem durchzuführen, generieren Microsoft Teams und Skype for Business Mos-Werte, indem Sie erweiterte Algorithmen verwenden, um die Ergebnisse einer subjektiven Prüfung Objektiv vorherzusagen.

Der verfügbare Satz von MOS-und zugehörigen Metriken bietet einen Überblick über die Qualität der Benutzererfahrung, die von einem Audiogerät an die Benutzer übermittelt wird. 

Durch die Bereitstellung von Benutzern mit Geräten, die für Teams und Skype for Business zertifiziert sind, verringern Sie die Wahrscheinlichkeit, dass aufgrund des Geräts selbst negative Erfahrungen auftreten (Dies ist wahrscheinlicher, beispielsweise mit integrierten Laptop-Lautsprechern und Mikrofonen). Weitere Informationen finden Sie in diesen Artikeln im [Zertifizierungsprogramm](/SkypeForBusiness/certification/overview) und im [Partner Lösungskatalog](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Die Geräte Berichte werden verwendet, um die Geräteverwendung nach Volumen und MOS Score (nur Audio) zu bewerten, und Sie finden Sie in den zugehörigen Vorlagen unter Clients #a0 Geräten. 

> [!IMPORTANT]
> Sofern Sie keine Verbund Teilnehmerdaten ausschließen, enthalten diese Berichte die Client-Telemetrie von verbundenen Endpunkten. Zum Ausschließen von Verbundendpunkten müssen Sie einen Abfragefilter für die **zweite Mandanten-ID** für die [Mandanten-ID](#tenant-id)Ihrer Organisation hinzufügen. Alternativ können Sie einen URL- [Filter](#url-filter) verwenden, um die Telemetrie für Teilnehmer auszuschließen.

> [!NOTE] 
> Stellen Sie sicher, dass Sie den Monats Jahres Filter auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten**und dann **Monat Jahr** anpassen aus, um den neuen Standardmonat zu speichern.

> [!Note]
> Wenn Sie diesen Bericht anzeigen, sehen Sie möglicherweise, dass das gleiche Gerät mehrmals gemeldet wurde. Dies ist darauf zurückzuführen, wie das Gerät gemeldet wird, dass es an CQD gemeldet wird. Unterschiede im Hardware-und Betriebssystem-Gebietsschema führen zu Unterschieden bei der Meldung von Gerätedaten.

![Screenshot des Berichts "Geräte (Mikrofon)"](media/qerguide-image-devicesmicrophone.png)

_Abbildung 31 – Bericht "Geräte (Mikrofon)"_

##### <a name="remediation"></a>Wartung

In der Regel müssen Sie nicht zertifizierte Geräte entdecken und Auslaufen und durch zertifizierte Geräte ersetzen. Bei der Überprüfung der Geräte Berichte sind einige Überlegungen zu berücksichtigen:

-   Sind die verwendeten Geräte für Teams und Skype for Business zertifiziert? 
-   Sie können die Benutzer eines bestimmten Geräts über die [anrufanalyse](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)identifizieren. Stellen Sie sicher, dass Sie über die neuesten Gerätetreiber verfügen und dass Ihr Gerät nicht über einen USB-Hub oder eine Dockingstation verbunden ist. 
-   Wie viele verschiedene Versionen von verschiedenen Treibern werden verwendet? Werden Sie regelmäßig gepatcht? Wenn Sie sicherstellen, dass Audio-, Video-und WLAN-Treiber regelmäßig gepatcht werden, können Sie diese als Quelle von Qualitätsproblemen eliminieren und die Benutzererfahrung vorhersehbarer und konsistenter machen.

##### <a name="audio"></a>Audio

Die nächste Aufgabe besteht in der Ermittlung der allgemeinen Nutzung [zertifizierter Audiogeräte](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Wir empfehlen, dass mindestens 80 Prozent aller Audiostreams ein zertifiziertes Audiogerät verwenden. Dies wird am besten erreicht, wenn der Bericht "Mikrofon Geräte" nach Excel exportiert wird, um die Verwendung von zertifizierten oder genehmigten Geräten zu berechnen. Organisationen führen in der Regel eine Liste aller genehmigten Geräte, sodass das Filtern und Sortieren der Daten unkompliziert sein sollte.

##### <a name="video"></a>Video

Video Treiber sind wichtig, um auch weiterhin aktualisiert zu werden. Wenn Sie sicherstellen, dass Videokarten regelmäßig gepatcht werden, können Sie Videotreiber als Quelle schlechter Qualität für Videostreams ausschließen. Durch die Verwendung von [zertifizierten Videogeräten](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) können Sie eine reibungslose und hochwertige Benutzererfahrung gewährleisten. Videogeräte, die H. 264-systemeigene Codierung unterstützen, werden bevorzugt, um die CPU-Auslastung während Videokonferenzen zu verringern.

##### <a name="wi-fi"></a>WLAN

WLAN-Treiber müssen ebenfalls in regelmäßigen Abständen gepatcht werden und sollten in ihrer Patch-Verwaltungsstrategie enthalten sein. Viele Qualitätsprobleme können durch die Beibehaltung aktueller WLAN-Treiber behoben werden. Weitere Informationen zum Optimieren Ihrer Wi-Fi-Infrastruktur finden Sie in [diesem Artikel über die WLAN-Planung](/skypeforbusiness/certification/networking-wifi).

## <a name="appendix"></a>Anhang 

### <a name="office-365-network-connectivity-principles"></a>Office 365-Netzwerk Verbindungs Prinzipien

Bevor Sie mit der Planung Ihres Netzwerks für die Office 365-Netzwerkkonnektivität beginnen, ist es wichtig, die Verbindungs Prinzipien für sicheres Verwalten von Office 365-Datenverkehr zu verstehen und die bestmögliche Leistung zu erzielen. Der folgende Artikel hilft Ihnen, die neuesten Anleitungen für die sichere Optimierung der Office 365-Netzwerkkonnektivität zu verstehen:

[Office 365-Netzwerk Verbindungs Prinzipien](https://aka.ms/pnc)

### <a name="planning-for-wi-fi"></a>Planen für WLAN

Der Ansatz von Microsoft zur Förderung von Qualität und Agilität in den drahtlosen Netzwerken umfasst drei Teile: End-to-End-Planung, bewährte Methoden für die Bereitstellung und proaktive Wartung und Vorgänge. Diese Lösungsübersicht führt Sie durch diesen Vorgang, um eine drahtlose Skype for Business-Umgebung für Unternehmen zu gewährleisten:

[Sicherstellen einer Unternehmensklasse für drahtlose Skype for Business-Benutzeroberfläche](https://www.microsoft.com/download/details.aspx?id=47257)

### <a name="lync-networking-guide"></a>Lync-Netzwerkhandbuch

Für mehr Hintergrundinformationen zu den Teams und den Skype for Business-Netzwerkkonzepten sowie zur Begründung für ihre Bedeutung für die Qualität ist der [lync Server 2013-Netzwerk Leit Faden](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) weiterhin anwendbar.

### <a name="network-performance-requirements"></a>Netzwerk Leistungsanforderungen

Die Qualität von Echt Zeit Medien (Audio-, Video-und Anwendungsfreigabe) über IP ist von der Qualität der End-to-End-Netzwerkkonnektivität stark betroffen. Für optimale Teams oder die Medienqualität von Skype for Business muss Ihr Netzwerk die folgenden Netzwerk Leistungs Metriken erfüllen.

_Tabelle 12 – Anforderungen an die Netzwerkleistung_

| Metrik                            | Vom Client zum Edge von Microsoft           | Vom Kundenedge zum Edge von Microsoft    |
|-----------------------------------|------------------------------------|------------------------------------|
| Latenz (unidirektional)                 | \<50 ms                            | \<30 ms                            |
| Latenz (RTT oder Round-Trip-Zeit) | \<100 MS                           | \<60 ms                            |
| Burstverlust von Paketen                 | \<10% während eines beliebigen 200-MS-Intervalls   | \<1% während eines beliebigen 200-MS-Intervalls    |
| Paketverlust                       | \<1% während eines 15-Sekunden-Intervalls    | \<0,1% während eines 15-Sekunden-Intervalls  |
| Paket Inter-arrival Jitter       | \<30 ms während eines 15-Sekunden-Intervalls | \<15 MS während eines 15-Sekunden-Intervalls |
| Neuanordnung von Paketen                    | \<0,05% Pakete außerhalb der Reihenfolge       | \<0,01% Pakete außerhalb der Reihenfolge      |

Weitere Informationen finden Sie in [diesem Artikel unter Medienqualität und Netzwerkleistung](https://aka.ms/performancerequirements) für Teams und Skype for Business Online.

### <a name="other-resources"></a>Weitere Ressourcen

#### <a name="building-data-file"></a>Erstellen einer Datendatei

-   [Aktivieren und Verwenden des Dashboards für die Anrufqualität für Microsoft Teams und Skype for Business Online](turning-on-and-using-call-quality-dashboard.md)

#### <a name="cqd-training"></a>CQD-Schulung

-   <https://aka.ms/sof-cqd>

-   [Erste Schritte mit CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) -Leitfaden und-Workshop

-   [Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](https://aka.ms/cqd-dm)

### <a name="call-analytics-training"></a>Schulung zur anrufanalyse

-   [Einführung in die anrufanalyse](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Einrichten von Anrufanalyse](set-up-call-analytics.md)

-   [Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?](difference-between-call-analytics-and-call-quality-dashboard.md)

-   [Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

### <a name="call-analytics-support"></a>Support für anrufanalyse

-   Community: [Skype for Business Preview-Programm](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

### <a name="devices"></a>Geräte

-   [Skype for Business-Lösungskatalog für persönliche Peripheriegeräte #a0 PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Mandanten Berichterstattung

-   [Inhaltspaket zur Einführung von Office 365](https://www.microsoft.com/microsoft-365/blog/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Analysen zur Anwendung von Microsoft 365](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)

-   [Skype for Business Online-Berichterstellung](/SkypeForBusiness/skype-for-business-online-reporting/skype-for-business-online-reporting)

-   [Microsoft Teams-Berichterstellung](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
