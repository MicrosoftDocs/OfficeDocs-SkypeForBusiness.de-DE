---
title: Quality of Experience überprüfen Handbuch für Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/24/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Handbuch für die Analyse der Leistung für Microsoft-Teams, Real-Time Media mithilfe von Anrufen Quality Dashboard (CQD).
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f9f50cd0751a64fb0e76793dfc45c1c2278a143b
ms.sourcegitcommit: 77ac57c5dc3f5836915d02e3e61305f1d3ea1600
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "23042583"
---
# <a name="quality-of-experience-review-guide"></a>Quality of Experience überprüfen Guide

<!-- Note that the link to the Word doc is intentionally NOT the aka.ms/qerquide link -->In diesem Handbuch wird über das Laufwerk Wert Phase für Microsoft-Teams und Skype für Business Online. Sie können dieses Handbuchs [eine Word-Version herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) .

## <a name="introduction"></a>Einführung

Um am stärksten zur Verbesserung der benutzerfreundlichkeit haben, müssen Unternehmen wichtige Bereiche durchsetzen, die in der folgenden Abbildung dargestellt sind. Weitere Bereiche umfassen, Betriebsaufgaben identifiziert, Zielvorgaben für Qualitätsmetriken, die Metriken zu verwenden, um Erfolg einzuschätzen Punkte und Bereiche der Untersuchung einschränken, je nach Bedarf.


![Schlüssel Bereiche für die Qualität des Benutzererlebnisses einschließen, Audio, Zuverlässigkeit, den benutzerumfragen, Geräte und Clients.] (media/qerguide-image-keyareas.png "Schlüssel Bereiche für die Qualität des Benutzererlebnisses einschließen, Audio, Zuverlässigkeit, den benutzerumfragen, Geräte und Clients.")

_Abbildung 1: Schlüssel betriebliche Bereiche behandelt, die in diesem Handbuch_

Ständig bewerten und Korrigieren von die Bereiche, die in diesem Handbuch beschrieben, können Sie ihre Potenzial, die sich negativ auf die Qualität Ihrer Benutzer-Erfahrung auswirken reduziert. Die meisten Benutzer-Erlebnis Probleme in einer Bereitstellung können in die folgenden Kategorien unterteilt werden:

-   Unvollständige Firewall oder der Proxyserver-Konfiguration
-   Schlechte Wi-Fi-Abdeckung
-   Unzureichende Bandbreite
-   VPN
-   Inkonsistente oder veraltete Clientversionen und Treiber
-   Nicht optimierte oder integrierte Audiogeräte
-   Problematisch Subnetze oder Netzwerkgeräte

Durch sorgfältige Planung und Entwurf vor der Bereitstellung von Teams oder Skype für Business Online können Sie Aufwand reduzieren, die erforderlich sind, um qualitativ hochwertige guter maintain.

Dieses Handbuch konzentriert sich auf Online aufrufen Quality Dashboard (CQD) als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche mit besonders auf die Annahme und Auswirkungen auf die Maximieren-Audio verwenden. Versucht, das Netzwerk zur Verbesserung der Audioqualität Verbesserungen übersetzt auch direkt in Verbesserungen bei video sowie die Desktopfreigabe.

Um die Bewertung zu beschleunigen, werden [zwei curated CQD-Vorlagen](https://aka.ms/qertemplates) zur Verfügung gestellt: eine ist für die Verwaltung von allen Netzwerken und die andere für verwaltete (intern) Netzwerke nur gefiltert. Obwohl der Berichte alle Netzwerke Vorlage zum Erstellen von und Netzwerkinformationen anzeigen konfiguriert sind, können sie während der Arbeit in Richtung sammeln und Hochladen von Informationen zum Erstellen von weiterhin verwendet. Erstellen von Informationen in CQD hochladen ermöglicht dem Dienst durch Hinzufügen von benutzerdefinierten erstellen, Netzwerk und Speicherort Informationen beim Unterscheidung von externen Subnetzen interne reporting optimiert. Weitere Informationen finden Sie unter [Erstellen von Zuordnung](#building-mapping) weiter unten in diesem Handbuch.

### <a name="intended-audience"></a>Zielgruppe

In diesem Handbuch wird für die direkte Verwendung von Partnern und Kunden Beteiligten mit Rollen wie leitender/Architekt für die Zusammenarbeit, Berater, Change Management/Annahme Specialist, Unterstützung/Help Desk führen, Netzwerk führen, Desktops führen und IT-Administrator verwendet werden

Dieses Handbuch soll auch von der festgelegten Qualität Champion(s) verwendet werden. Weitere Informationen finden Sie unter [der Qualität Champion-Rolle](4-envision-plan-my-service-management.md#the-quality-champion-role).

## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie bevor Sie dieses Handbuch verwenden sicher, dass Sie die richtige Mandanten [Rollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) zugewiesen, sodass Sie CQD zugreifen können.

-   **Globalen Administratorrolle von Office 365:** Greift auf alle administrativen Funktionen in Office 365-Suite von Diensten in Ihrem Plan, einschließlich Skype für Unternehmen.

-   **Skype für Business Administratorrolle:** Skype für Unternehmen für Ihre Organisation konfiguriert, und ist berechtigt, die [Berichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Office 365 Administrationscenter anzeigen. Diese Rolle ist erforderlich, auch wenn Sie nur Teams bereitstellen.

Alternativ können Sie ein Office 365-Benutzerkonto den Zugriff auf Berichtsfunktionen nur folgende Rolle zuweisen.

-   **Leser von Berichten:** Können die [Berichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Office 365 Administrationscenter, alle Berichte aus dem [Office 365 Annahme Inhaltspaket](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)und CQD Berichte anzeigen.

## <a name="what-is-quality"></a>Was ist die Qualität?

Im Zusammenhang mit Qualität in Teams und Skype für Unternehmen ist es wichtig, definieren Sie den Begriff, um eine allgemeine Grundlegendes zu erreichen. Qualität, ist wie hier definiert eine Kombination von Metriken und benutzerfreundlichkeit Service.

<!-- Note: need to update graphic-->
![Service Metriken bestehen aus schlechter Stream Verhältnis, Zuverlässigkeit, Endpunkte-Geräte und Clientversionen. Die Benutzeroberfläche des Benutzers Wahrnehmung der die Qualität des Diensts bestehen.] (media/qerguide-image-whatisquality.png "Service Metriken bestehen aus schlechter Stream Verhältnis, Zuverlässigkeit, Endpunkte-Geräte und Clientversionen. Die Benutzeroberfläche des Benutzers Wahrnehmung der die Qualität des Diensts bestehen.")

_Abbildung 2: Was Qualität ist?_

### <a name="service-metrics"></a>Service-Metriken

Service-Metriken bestehen bestimmte clientbasierte Metriken. Bei jedem Aufruf der Client sammelt Telemetrie Informationen über den Anruf und sendet einen Bericht am Ende jeder Anruf, die später über CQD oder [Rufen Sie Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)zugegriffen werden kann. Diese Kennzahlen:

-   Schlechte Stream Rate
-   Setup-Fehlerrate
-   Drop-Fehlerrate


#### <a name="poor-stream-rate"></a>Schlechte Stream Rate

Die niedrige Stream Rate (a.) stellt der Organisation Gesamtprozentsatz schlechten Qualität denen Datenströme. Diese Metrik dient zum Hervorheben von Bereichen, in Ihrer Organisation Aufwand für die stärksten wirken sich in Richtung verringern diesen Wert und Verbessern der benutzererfahrung, weshalb konzentrieren kann, [verwaltete Netzwerke](#managed-vs-unmanaged-networks) der Schwerpunkt sind, wenn a. betrachten. Externe Benutzer zu wichtig sind, aber Untersuchung unterscheidet sich für eine einzelne Organisationseinheit. Erwägen Sie, bewährte Methoden für externe Benutzer, und überprüfen Sie externe Anrufe unabhängig von der gesamten Organisation.

Die tatsächliche Messung in CQD variiert je nach Arbeitslast, aber für die Zwecke der Qualität Erfahrung Überprüfung wir konzentrieren Sie sich hauptsächlich auf die Messung _Audio schlechter Prozentsatz_ . A. besteht aus den fünf Netzwerk metrischen Durchschnittswerte in der folgenden Tabelle beschrieben. Für ein Stream-Objekt als schlecht klassifiziert werden muss nur eine Metrik den definierten Schwellenwert überschreitet. Weitere Informationen zum Vorgang, Stream Klassifizierung finden Sie unter [in diesem Artikel](/skypeforbusiness/using-call-quality-in-your-organization/stream-classification-in-call-quality-dashboard).

> [!Note]
> CQD enthält die "schlechter Fälligkeitsdatum an..." Maßeinheiten für ein besseres Verständnis welcher Bedingung den Stream, der als schlecht eingestuft verursacht.


_Tabelle 1: Schlechte Service Metriken_

| Metrische Durchschnitt     | Beschreibung     | Benutzererfahrung |
|-------------|-----------------|-----------------|
| Jitter \>30 ms        | Dies ist die durchschnittliche Änderung Verzögerung zwischen aufeinander folgende Pakete. Für einige Ebenen von Jitter über Pufferung können Teams und Skype für Unternehmen anpassen. Es ist nur, wenn die Jitter überschreitet die Pufferung, dass ein Teilnehmer die Effekte der Jitter bemerkt.      | Die Pakete an einem anderen kumulativ dazu führen, dass ein Lautsprecher Stimme zum automatischen auszugeben.   |
| Paketverlustrate \>10 % oder 0,1        | Dies ist häufig als Prozentsatz der Pakete definiert, die verloren gegangen sind. Paketverlust wirkt sich direkt auf die Audioqualität – von kleinen, verloren Person Pakete, die fast keine Auswirkungen auf Back Bursts von Verlusten haben, Ursache Audio vollständig Ausschneiden.     | Die Pakete werden verworfen und nicht eingehenden an das vorgesehene Ziel verursachen Lücken in den Medien, resultierende in verpassten Silben und Wörter und abgehackte video und Freigabe. |
| Roundtripzeit \>500 ms        | Dies ist der Zeitaufwand zum Abrufen von ein IP-Paket von Punkt A nach Punkt B und an Punkt A. Diese Netzwerk Verteilung Verzögerung ist mit der physischen Abstand zwischen zwei Punkte und der Lichtgeschwindigkeit verknüpft und zusätzlichen Aufwand, die von den verschiedenen Geräten im Netzwerkpfad geschaltet enthält.      | Die Pakete braucht zu lange zum am Ziel eingehen dazu führen, dass einen Effekt Walkie-talkie.   |
| NMOS-Beeinträchtigung Durchschnitt \>1.0         | Durchschnittliche [Netzwerk Mean Opinion Score (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) Beeinträchtigung für den Datenstrom. Stellt dar, wie viel die Netzwerk-Verlust und Jitter hat beeinflusst die Qualität der empfangenen, das die NMOS, um mehr als einen Punkt zu löschen. | Hierbei handelt es sich um eine Kombination von Jitter Paketverlust, und – in geringerem Maße – Roundtripzeit erhöht. Der Benutzer kann eine Kombination der folgenden Symptome auftreten.   |
| Durchschnittliches Verhältnis zwischen ausgeblendeten Samples \>7 % oder 0,07 | Durchschnittliches Verhältnis zwischen der Anzahl von audio Frames mit ausgeblendeten Samples, generiert von Paketverlust und der Gesamtzahl der audio Frames Reparatur. Ein ausgeblendeter audio Beispiel ist ein Verfahren zur abrupten Übergang zu glätten, die in der Regel durch Initiale Netzwerkpaketen verursacht werden würde.      | Hohe Werte anzugeben, dass erhebliche Ebenen der Verlust zum Verbergen verzerrt oder verlorenen Audio ergab und angewendet wurden.     |

#### <a name="setup-failure-rate"></a>Setup-Fehlerrate

Setup-Fehlerrate bekannt als die Messung _Rufen Sie Setup Fehler Gesamtprozentsatz_ in CQD, ist die Anzahl an, der Medienpfad zwischen den Endpunkten am Anfang des Anrufs eingerichtet werden konnte nicht Datenströme.

Dies stellt Mediendaten, die konnte nicht hergestellt werden. Aufgrund den Schweregrad der Auswirkungen ermittelte Benutzerinteraktion ist das Ziel dieser Wert als erreicht bald wie möglich bei Null zu reduzieren. Ein hoher Wert für diese Metrik ist in neuen Bereitstellungen mit unvollständiger Firewallregeln häufiger als eine über Erfahrungswerte zur Bereitstellung, aber es ist wichtig, die in regelmäßigen Abständen Video.

Nutzen die Gesamtzahl der Streams, die Fehler beim Einrichten von dividiert durch die Gesamtzahl von Datenströmen, die einer erfolgreichen Aufruf Detaildatensatz (CDR) übermittelt wird diese Metrik berechnet:

-   **Setup-Fehlerrate** insgesamt Anruf = Setup fehlgeschlagenen Stream Count / insgesamt CDR verfügbaren Stream Count

#### <a name="drop-failure-rate"></a>Drop-Fehlerrate

Die Drop Fehlerrate bekannt als die Messung _Aufrufen abgelegten Fehler Gesamtprozentsatz_ in CQD, ist der Prozentsatz der erfolgreich hergestellte Datenströme, in dem der Medienpfad ordnungsgemäß beendet wurde nicht.

Dies stellt Mediendaten, die unerwartet beendet. Obwohl die Auswirkung dieser wie erheblich als Stream nicht zur Verfügung, die nicht ordnungsgemäß eingerichtet, wirkt es sich negativ auf die Benutzeroberfläche. Plötzlichen und häufige Medien setzt nicht nur können wirken sich erheblich auf die Benutzeroberfläche, sie führen die Notwendigkeit für Benutzer eine Verbindung herzustellen, was zu einem Verlust Produktivität.

Nutzen die Gesamtzahl der Initiale Streams geteilt durch die Gesamtzahl der Datenströme, die erfolgreich eingerichtet wird die Metrik berechnet:

-   **Drop-Fehlerrate** = insgesamt abgebrochen Stream Count / insgesamt Verbindungsaufbau erfolgreich Stream Count

### <a name="define-your-target-metrics"></a>Definieren Sie die Ziel-Metriken

In diesem Abschnitt werden einige der Core Service Metriken, die wir verwenden bewerten, wie Dienste Health auftreten. Helfen Sie ständig bewerten und Entwicklung, diese Metriken unten ihre definierten Ziele zu halten, stellen Sie sicher, dass Ihre Benutzer konsistente, zuverlässige Anrufqualität auftreten. Um Ihnen den Einstieg zu erleichtern, werden die folgenden Ziele bereitgestellt.

_Tabelle 2 - Core Ziel Health Assessment Metriken_
<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Netzwerktyp</th><th rowspan="1">Ziele der Qualität</th><th colspan="2">Ziele der Zuverlässigkeit</th></tr>
<tr><th>Schlechte Audiostream Rate</th><th>Setup-Fehlerrate</th><th>Drop-Fehlerrate</th></tr>
<tr><td rowspan="2">**Alle**</td><td>Intern</td><td>2.0 %</td><td>0,5 %</td><td>2.0 %</td></tr>
<tr><td>Gesamt</td><td>3,0 %</td><td>1.0 %</td><td>3,0 %</td></tr>
<tr><td rowspan="5">**Konferenzen**</td><td>Intern</td><td>2.0 %</td><td>0,5 %</td><td>2.0 %</td></tr>
<tr><td>Interne verkabelt</td><td>1.0 %</td><td>0,5 %</td><td>1.0 %</td></tr>
<tr><td>Wi-Fi 5 GHz interne</td><td>1.0 %</td><td>0,5 %</td><td>1.0 %</td></tr>
<tr><td>Interne der Wi-Fi 2,4 GHz</td><td>4.0 %</td><td>0,5 %</td><td>2.0 %</td></tr>
<tr><td>Gesamt</td><td>2.0 %</td><td>0,5 %</td><td>3,0 %</td></tr>
<tr><td rowspan="4">**P2P**</td><td>Intern</td><td>2.0 %</td><td>0,5 %</td><td>2.0 %</td></tr>
<tr><td>Verkabelt/Wi-Fi 5 GHz interne</td><td>1.0 %</td><td>0,5 %</td><td>1.0 %</td></tr>
<tr><td>Verkabelt/Wi-Fi 5 GHz insgesamt</td><td>2.0 %</td><td>1.0 %</td><td>1.0 %</td></tr>
<tr><td>Gesamt</td><td>2.0 %</td><td>1.0 %</td><td>3,0 %</td></tr>
</table>


Es ist wichtig, zu besprechen und definieren die Ziele Ihrer Organisation, um Ihre Geschäftsziele zu erfüllen.

### <a name="user-experience"></a>Benutzererfahrung

Analysieren die Benutzeroberfläche ist mehr Kunst als Science, da hier die Metriken gesammelt nicht immer bedeuten, es ein Problem mit dem Netzwerk oder Dienst ist, sondern vielmehr sie einfach darauf hinzuweisen, dass der Benutzer ein Problem wahrnimmt. Microsoft bietet einen Umfragemechanismus integrierten – bekannt als Rate Meine aufrufen (RMC) – Hilfe benutzerfreundlichkeit zu ermitteln. RMC hilft Ihnen die aus Sicht des Benutzers die folgenden Fragen beantworten:

-   Weiß ich, wie Sie die Lösung verwenden können?
-   Ist die Lösung, einfach zu verwendenden und intuitiv, und wird über die alltägliche Kommunikation führe unterstützt?
-   Kann die Lösung mich Meine erledigen?
-   Was ist meine allgemeine Wahrnehmung der Lösung?
-   Kann ich verwenden die Lösung an einer beliebigen Stelle in der Zeit, unabhängig davon, an denen ich bin?
-   Kann ich einrichten und verwalten ein Anrufs?

#### <a name="rate-my-call"></a>Bewerten von Meine Anruf 

Rate Meine aufrufen (RMC) ist in Teams und Skype für Unternehmen integriert und wird automatisch so konfiguriert, dass nach einem in jeder 10 Anrufe oder 10 Prozent der Teilnehmer angezeigt werden. In diesem kurzen Umfrage fordert den Benutzer den Anruf bewerten und einen wenig Kontext für warum die Anrufqualität schlechter wurden möglicherweise bereitstellen. Eine Bewertung ein oder zwei schlechter gilt, eignet sich drei bis vier und fünf ist hervorragend. Obwohl es etwas eines Indikators Verzögerung beim ist, ist dies eine nützliche Metrik für Unternehmensdaten Probleme, die Service-Metriken verpassen können.

> [!Note]
> Bis Benutzer geschult sind, durch das Erteilen von guten Feedback zusätzlich zu schlecht, Antworten in der Regel auf RMC Umfragen reagieren zurückkehren Sie als überwältigend negativ. Die meisten Benutzer reagieren nur, wenn die Anrufqualität schlechter befindet. Aus diesem Grund können RMC Berichte auf der Seite schlechter verzerrt angezeigt werden auch dann, wenn der Dienst Metriken gute sind.

Sie können CQD verwenden, um einen Bericht über RMC Benutzerantworten und Beispielberichte sind in der Vorlage CQD enthalten. Sie sind nicht jedoch in diesem Handbuch ausführlich erläutert. Weitere Informationen zu RMC in Skype für Business Online und Richtlinien für die Schulung der Benutzer auf nützliche RMC Antworten zu erteilen finden Sie unter [in diesem Blogbeitrag](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

#### <a name="client-and-device-readiness"></a>Client- und Gerätefunktionen Bereitschaft

Benötigen Sie eine solide Client- und Gerätefunktionen Strategie zur Sicherstellung, dass die Benutzer eine konsistente und positive Benutzeroberfläche zur Verfügung haben. Einige wichtige Prinzipien Laufwerk jeweiligen Strategie Readiness.

##### <a name="client-readiness"></a>Client-Bereitschaft

Eine Strategie für die sichere Client Bereitschaft wird sichergestellt, dass Ihre Benutzer die neueste Version des Clients und genießen dabei die bestmögliche Erfahrung ausgeführt werden. Microsoft-patches routinemäßig die Skype für Business Client; sicherstellen, dass Sie es in Ihrer Umgebung Stand ist entscheidend für Ihre gesamten Erfolg. Es ist außerdem mit Patch-Netzwerk, video, USB und Audiotreiber, denken Sie daran, da sie oft übersehen sind und sich auf das Benutzererlebnis auswirken können. Erwägen Sie Netzwerk, Wi-Fi, Video, USB, und Audiotreiber, um Ihre aktuelle Patchverwaltung.

Es wird empfohlen, dass Sie nicht in Ihrer Client-Versionen von mehr als sechs Monaten fallen hinter lassen. Wenn Sie Office Klick-und-Los verwenden, sind Sie bereits auf dem aktuellen Stand vom Dienst gespeichert wird. Verwenden Sie enthalten [Clientversionen](#client-versions)wie weiter unten in diesem Handbuch wird beschrieben, die Sie bei diesem Prozess unterstützen. Sie können auch die Beispielberichte Rate Meine aufrufen zu steigern Ihrer Strategie für die Client-Bereitschaft nutzen.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt sind, und durch die Azure Content Delivery Network automatisch aktualisiert, und wird von der Dienst auf dem aktuellen Stand gehalten werden. Aus diesem Grund nicht Client Bereitschafts- und genauer Aktivitäten für Teams gelten.


##### <a name="device-readiness"></a>Gerät Bereitschaft

Keine einer Strategie für die einzelne kann die Benutzeroberfläche, die mehr als Ihrer Strategie für die Bereitschaft Gerät auswirken. Die meisten Organisationen freuen, entfernen Sie unnötige Geräte (beispielsweise Telefonapparate oder anderen dedizierten Audiogeräte) von Benutzern, und dies ist häufig als Rechtfertigung Core für den Wechsel zu Teams oder Skype für Unternehmen. Allerdings zögern gleichen Organisationen manchmal Replacement-Geräte bereitstellen, auch wenn diese Geräte kostengünstigeren wurden. Modernen Laptops und PCs, jedoch mit integrierten Mikrofon und Lautsprecher, ausgestattet sind nicht für die Business-Klasse Voice over IP (VoIP) optimiert. Dadurch wird erstellt oft eine schlechte Erfahrung für alle Teilnehmer, insbesondere dann, wenn der Lautsprecher in einer lauten Umgebung ist. Zertifizierungsprogramm für Microsoft Gerät wird sichergestellt, dass, wenn ein Benutzer einen Telefonanruf gehört mithilfe von jedem Gerät zertifiziert für Teams oder Skype für Unternehmen, eine wünschen erzeugt, die zu einem Gerät nicht zertifizierter überlegen ist. 

Wir empfehlen immer Teams und Skype für Unternehmensbenutzer eine zertifizierten Kopfhörer oder Lautsprecher verwenden, wenn einen Anruf über den Desktopclient teilnehmen. Weitere Informationen zu Microsoft zertifizierte Geräte überprüfen Sie in diesen Artikeln zum [Zertifizierungsprogramm](/SkypeForBusiness/certification/overview) und zeigt den [Lösungskatalog für Partner](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Verwenden Sie den [Bericht Geräte](#devices), weiter unten in diesem Handbuch Unterstützung bei der Verwaltung Ihrer Geräte beschrieben.


### <a name="categories-of-quality"></a>Kategorien von Qualität

Der Erfolg der operationalizing einer hohe Qualität und zuverlässigen bereitstellungs hängt von Ihrer Erstellen von betrieblichen Genehmigungsverfahren ab. Achten Sie insbesondere, besonders auf die drei Kategorien, die in der folgenden Abbildung dargestellt; Hierbei handelt es sich um den Fokus dieses Handbuchs:

-   **Netzwerk:** Audioqualität konzentriert sich auf die Metrik schlechter Stream-Verhältnis (a.), TCP-Verwendung, verkabelten und drahtlosen Subnetze, und identifizieren die Verwendung von HTTP-Proxys und VPN.

-   **Endpunkte:** Audiogeräte und Clientversionen (Skype für nur Unternehmen).

-   **Dienstverwaltung:** Dieser Kategorie besteht aus zwei Abschnitten:

    -   Zunächst wird Microsofts Verantwortung zu verwalten und Verwalten von Teams und Skype für Business Online-Dienste.

    -   Zweitens sind Aufgaben, die Ihre Organisation verwalten muss, um sicherzustellen, dass zuverlässigen Zugriff auf den Dienst, beispielsweise zum Erstellen von Informationen zu aktualisieren und Verwalten von Firewalls für neue Office 365-IP-Adressen, sobald Infrastruktur mit dem Dienst hinzugefügt wird.

![Die Kategorien von Qualität in einer Organisation: service-Management, Endpunkte und dem Netzwerk.] (media/qerguide-image-categories.png "Die Kategorien von Qualität in einer Organisation: service-Management, Endpunkte und dem Netzwerk.")

_Abbildung 3 – wichtige Kategorien für Teams und Skype für Business Online-Bereitstellung_

In der folgenden Grafik werden die Aufgaben erläutert, die Sie für jede Kategorie ausführen müssen. Es wird empfohlen, dass Sie diese Aufgaben einmal pro Woche mindestens ausgeführt.

Der ersten dieser Aufgaben Ausführung dauert aufwändiger als nachfolgende Iterationen, da viele dieser Kategorien erfordern, dass Sie Ihre Bereitstellungskonfigurationen auf Gültigkeit überprüfen. Nachdem Sie den Status aus, indem Sie die von die Ihnen definierten Ziele meeting erreicht haben, helfen diese Aufgaben Ihnen bei diesem Zustand verwalten.

<!--  This is a net new graphic, never was included in the online article. OOPS! -->
![Wöchentliche Aufgabenliste pro Quality-Kategorie] (media/qerguide-image-tasks.png "Wöchentliche Aufgabenliste pro Quality-Kategorie")

#### <a name="service-management-tasks"></a>Service-Management-Aufgaben

In einer Cloud-First-Welt müssen Sie bestimmte Verwaltungsaufgaben Service zum Verwalten von hochwertigen benutzerumgebungen ausführen. Diese Aufgaben im Bereich von sicherstellen, dass ausreichend Bandbreite, um den Dienst zu erreichen, ohne eine Internetlinks, validieren, Dienstqualität (QoS) auf alle verwalteten Netzwerks Bereiche ist und – und schließlich – [Griff Office 365 IP-Bereiche auf Firewalls](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Netzwerkaufgaben

Es gibt zwei Kategorien von Netzwerk-Tasks: Zuverlässigkeit und Qualität. Zuverlässigkeit konzentriert sich auf Messen der Fähigkeit des Benutzers tätigen erfolgreich und in Verbindung bleiben. Qualität konzentriert sich auf die aggregierten Telemetrie gesendeten Teams und Skype für Business Online-Client des Benutzers während des Anrufs und es beendet wurde. 

Wichtige Auswirkung auf die, Zuverlässigkeit Benutzerinteraktion hat, angegeben, es ist wichtig, beginnen bewerten und Untersuchen von diese Metriken vor Qualität. 

#### <a name="endpoints-tasks"></a>Endpunkte Aufgaben

Die Hauptaufgabe in dieser Kategorie ist wird überprüft, welche Clientversionen Skype für Unternehmen ausgeführt werden, auf dem desktop Builds aus den letzten sechs Monaten, um sicherzustellen, dass Benutzer die Vorteile der kontinuierlichen Optimierungen versucht, der Skype für Business desktop Client abrufen. Darüber hinaus Dies vereinfacht die allgemeinen Verwaltungsaufgaben von Client und stellt ein einheitliches Benutzererlebnis.

Der anderen wichtige Bereich ist monitoring, welche Geräte in Ihrer Bereitstellung betroffen sind und die Verwendung von zertifizierte Geräte bieten die beste benutzerumgebung gesteuerter.


> [!IMPORTANT]
> Derzeit Teams Clients verteilt sind, und durch die Azure Content Delivery Network automatisch aktualisiert, und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.

## <a name="cqd-basics"></a>CQD-Grundlagen

In diesem Abschnitt werden die Grundlagen der Arbeit mit CQD beschrieben. Anleitung erhält für den folgenden Themen:

-   Was ist CQD?
-   Die Erwartungen CQD
-   Suchen die Mandanten-ID
-   Berichten über Microsoft-Teams, im Vergleich zu Skype für Unternehmen
-   Zuerst im Vergleich zur zweiten Klassifikationen
-   Dimensionen und Measures Filter
-   Datenströme im Vergleich zu Anrufen
-   Gut, schlecht und nicht klassifizierte Anrufe
-   Allgemeine Subnetze

Ausführlicheren Schulungen und Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="what-is-cqd"></a>Was ist CQD?

Sie verwenden rufen Quality Dashboard (CQD) Einblick in die Qualität der Anrufe mithilfe von Teams und Skype für BusinessServices. CQD soll helfen, Skype für Geschäfts- und Teams-Admins und Netzwerktechniker Optimieren des Netzwerks und für die Qualität, Zuverlässigkeit und die Benutzeroberfläche Auge behalten. CQD untersucht aggregierte Telemetrie für eine ganze Organisation, auf dem können allgemeine Muster offensichtlich, zulassen der Mitarbeiter informiert Bewertung und Abhilfemaßnahmen zur Maximierung der Auswirkungen planen. CQD bietet Berichte der Metriken, die einen Einblick in die allgemeine Qualität, Zuverlässigkeit und benutzerfreundlichkeit bieten.

> [!Note]
> CQD enthalten keine personenbezogene Informationen (PII). PII sind Informationen, die verwendet werden kann allein oder mit anderen Informationen bezeichnen, wenden Sie sich an, oder suchen eine einzelne Person oder um eine einzelne Person im Kontext zu identifizieren.

Dieses Handbuch hilft Verständnis der Kernkonzepte CQD um die Auswirkungen zu maximieren, die Sie bei der Verbesserung Ihrer Benutzer Erfahrung mit Teams oder Skype für Business Online vornehmen können. Zusätzliche CQD Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="expectations-using-cqd"></a>Die Erwartungen CQD

CQD, Bereitstellen nicht zwar zum Analysieren von Trends und Subnetze, immer eine bestimmte Ursache für ein bestimmtes Szenario. Es ist wichtig zu verstehen sind dies und der richtigen Annahme bei der Verwendung von CQD festgelegt:

-   CQD wird nicht die Ursache für jedes Szenario angeben.
-   CQD enthalten keine Telefonsystem oder Audiokonferenzen Datenströme sein.
-   CQD werden bestimmte Bereiche zur weiteren Untersuchung basierend auf Trends aufrufen.
-   CQD enthalten nicht personenbezogene Informationen.

### <a name="tenant-id"></a>Mandanten-ID

Einige Berichte CQD erfordern, dass Sie einen Filter für Ihre Mandanten-ID einschließen Daran CQD Daten aggregiert ist federated Teilnehmer Telemetrie enthalten. Obwohl dies wertvolle nachweisen kann bei der Analyse von Trends, müssen Client- und Gerätefunktionen Berichte Filtern von Daten an einen bestimmten Mandanten federated Teilnehmer Telemetrie ausgeschlossen. Wenn Sie Ihre Mandanten-ID nicht kennen, können Sie eine der folgenden Methoden verwenden, sie zu finden sind.

> [!Note]
> Diese Methoden sind die folgenden Berechtigungen erforderlich:<ul><li>Globalen Administratorrolle</li><li>Skype für Business Administratorrolle</li></ul>

#### <a name="azure-portal"></a>Azure-portal

1.  Melden Sie sich bei des Microsoft Azure-Portals an:<https://portal.azure.com>

2.  Wählen Sie **Azure Active Directory**aus.

3.  Wählen Sie unter **Manage** **Eigenschaften**aus. Die Mandanten-ID wird in das **Verzeichnis-ID** angezeigt.

#### <a name="azure-powershell"></a>Azure PowerShell

1.  [Installieren des Microsoft Azure PowerShell Service-Management-Moduls](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Öffnen Sie ein Befehlsfenster Azure PowerShell und führen Sie das folgende Skript, indem Sie bei entsprechender Aufforderung Ihre Office 365-Anmeldeinformationen eingeben: 

  ```
  Login-AzureRmAccount
  ```

3.  Die Mandanten-ID wird in der Ausgabe aufgeführt.

#### <a name="skype-for-business-online-admin-center"></a>Skype für Business Online Admin Center

1.  Wechseln Sie zu <https://portal.office.com>.

2.  Melden Sie sich mit Ihrer Organisation Administratorkonto eines Mandanten.

3.  Wählen Sie **Skype für Unternehmen** unter **Admin Center**aus.

4.  Die Mandanten-ID wird als **Organisations-ID** auf der Seite Willkommen aufgelistet.

#### <a name="skype-for-business-online-using-powershell"></a>Skype für Business Online mithilfe von PowerShell

1.  [Einrichten des Computers für Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2.  Führen Sie den folgenden Befehl aus:

  ```
  (Get-cstenant).tenantid
  ```

3.  Die Mandanten-ID wird als GUID angezeigt.

### <a name="teams-vs-skype-for-business"></a>Teams im Vergleich zu Skype für Unternehmen

CQD kann Teams und Skype für Business Telemetrie melden. Möglicherweise gibt es jedoch vorkommen, dass Sie einen Bericht betrachten Teams Telemetrie getrennt von Skype für Unternehmen entwickeln möchten.

#### <a name="summary-reports"></a>Zusammenfassungsberichte

Um die Seite Zusammenfassungsberichte betrachten nur Teams oder Skype für Unternehmen zu ändern, wählen Sie das **Produktfilter** Dropdown-Menü vom oberen Rand des Bildschirms, und wählen Sie dann das gewünschte Produkt aus.

![Im Dropdownmenü die Option zum Filtern von CQD Berichten nach Arbeitslast anzeigen](media/qerguide-image-productfilter.png)

_Abbildung 4: Auswählen eines Filters Produkt_

#### <a name="detailed-reports"></a>Ausführliche Berichte

Zum Filtern von allen ausführliche Berichte in der browserleiste fügen Sie die folgenden am Ende der URL an:

```
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Beispiel:**

```https://cqd.lync.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Weitere Informationen zu URL-Filter finden Sie unter [Filtern Berichte](#filtering-reports) weiter unten in diesem Abschnitt.

Um eine einzelne detaillierter Bericht zu filtern, den Filter hinzufügen ``Is Teams`` auf den Bericht, und legen Sie es auf True oder False. Weitere Informationen finden Sie unter [Bearbeiten Berichte](#editing-reports) weiter unten in diesem Abschnitt.

![Fügen Sie einen Filter, um einen detaillierten Bericht.](media/qerguide-image-addteamsfilter.png)

_Abbildung 5: Hinzufügen eines Microsoft-Teams Filters in einem Bericht_


### <a name="managed-vs-unmanaged-networks"></a>Verwaltete und nicht verwalteten Netzwerken

Standardmäßig werden alle Endpunkte in CQD als extern klassifiziert. Als eine Datei zum Erstellen von eingeführt wird, können wir beginnen, verwaltete Endpunktdaten betrachten. Wie bereits erläutert,-Netze in CQD werden wie folgt definiert:

-   _Netzwerk verwaltet_, kann von der Organisation häufig bezeichnet als interne oder innerhalb, beeinflusst und gesteuert werden. Dazu gehören das interne LAN, remote WAN und VPN.
-   Ein _nicht verwalteten Netzwerk_häufig bezeichnet als externer oder außerhalb, nicht beeinflusst oder von der Organisation gesteuert wird. Ein Beispiel für eine nicht verwaltete Netzwerk ist ein Hotel oder am Flughafen Netzwerk.

### <a name="dimensions-measures-and-filters"></a>Dimensionen und Measures Filter

Eine wohlgeformte CQD Abfrage enthält alle drei der folgenden Parameter:

-   **Dimension:** Wie soll ich auf die Daten von PivotTables.

-   **Measure:** Was ich melden möchten.

-   **Filter:** Gibt zurück, wie ich möchte das Dataset die Abfrage zu reduzieren.

Alternativ können Sie dies: eine _Dimension_ ist der Grouping-Funktion, ein _Measure_ befinden sich die Daten, die ich interessiert bin und ein _Filter_ ist wie ich möchte die Ergebnisse auf diejenigen zu beschränken, die für eine Abfrage relevant sind.

Ein Beispiel für eine wohlgeformte Abfrage wird **Demo schlechter Datenströme [messen] Subnetz [Dimension] für das Erstellen von 6 [Filter]**. Weitere Informationen finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>Zuerst im Vergleich zu Sekunde 

Viele der Dimensionen und Measures in CQD werden als erste oder zweite klassifiziert. CQD nicht Anrufer/angerufenen Felder verwenden – diese Waren umbenannte _ersten_ und _zweiten_ , da sind dazwischenliegende Schritte zwischen dem Anrufer und des angerufenen. Die folgende Logik bestimmt geklebtem Endpunkt Beteiligten als erstes gekennzeichnet ist:

-   **Erste** ist immer Endpunkt eines Servers (Konferenzserver, Vermittlungsserver usw.), wenn ein Server in der Stream oder Anruf beteiligt ist.

-   **Zweite** werden immer ein Clientendpunkt, wenn der Stream zwischen zwei Serverendpunkten ist.

-   Wenn beide Endpunkte den gleichen Typ, sind die Wahl, der zwischen dem ersten ist basiert auf internen Reihenfolge der Benutzer-Agent Kategorie. Damit wird eine konsistente Anordnung sichergestellt.

Weitere Informationen zum Bestimmen des ersten oder zweiten Endpunkts, wenn sie beide identisch sind finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream im Vergleich zu Anrufen

Sie verstehen des Unterschieds zwischen eines Anrufs und einem Stream ordnungsgemäß auswählen, welche Dimensionen oder Measures, die Sie in CQD angezeigt werden sollen. Zwar CQDs primäre Fokus auf Streams, sind aufrufbasierte Maße auch verfügbar.

-   **Stream:** Ein _Stream-Objekt_ besteht zwischen nur zwei Endpunkte. Es ist nur ein Stream-Objekt für jede Richtung und zwei Datenströme sind erforderlich für die Kommunikation. Datenströme eignen sich zum Untersuchen von Gebäude, Netzwerke oder Subnetze. In einigen Fällen werden Anruf und Stream in die Messung Namen (beispielsweise Anruf Setup Stream oder Anruf verworfen Stream) verwendet. Diese werden weiterhin als Streams klassifiziert.

-   **Aufrufen:** Ein _Anruf_ ist eine Gruppierung aller Streams aus allen Teilnehmern. Umfasst ein Anruf – mindestens – zwei Datenströme. Ein einzigen Aufruf müssen mindestens zwei Endpunkte mit mindestens einem Stream-Objekts.

Weitere Anleitungen gibt an, ob die Dimension oder Measure eines Anrufs oder eines Stream-Objekts verweist finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Gut, schlecht und nicht klassifizierte Anrufe

Ein Aufruf ist entweder als gut, schlecht oder nicht klassifizierte kategorisiert. Betrachten wir kurz jeweils ausführlich behandelt.

-   **Gut oder schlecht:** Gespräch gut oder schlecht umfasst einen Anruf, der einen kompletten Satz von Kriterien Service, für die ein vollständiger QoE-Bericht generiert und vom Dienst enthält. Bestimmen, ob ein Stream gut oder schlecht ist wird beschrieben [Weiter oben in diesem Handbuch](#poor-stream-rate).

-   **Nicht klassifizierte:** Ein nicht klassifizierter Stream enthalten keine umfassende Auswahl an Service Metriken. Dabei kann es sich um kurze Anrufe – normalerweise weniger als 60 Sekunden – wobei Durchschnittswerte konnte nicht berechnet werden und ein QoE-Bericht wurde nicht generiert. Die häufigste Ursache für Anrufe nicht vertraulich ist, dass es keine Paket Auslastung wenig wurde. Ein Beispiel wäre ein Teilnehmer, der teilnimmt einer Besprechung auf Stummschalten und nie spricht. Der Teilnehmer empfangen, aber nicht übertragen, Medien. Ohne Medium übertragen werden es keine Metriken verfügbar für CQD zu verwenden, um den Endpunkt ausgehende videomedienströmen klassifizieren.

Weitere Informationen zum Vorgang, Stream Klassifizierung finden Sie unter [in diesem Artikel](/skypeforbusiness/using-call-quality-in-your-organization/stream-classification-in-call-quality-dashboard).

### <a name="common-subnets"></a>Allgemeine Subnetze

Allgemeine Subnetze sind bestimmte private Subnetze, die von Hotels, Heimnetzwerken, Hotspots und ähnlichen Bereiche verwendet werden. Diese Subnetze sind schwieriger zu Ursachenanalyse aufgrund der weit verbreitete Verwendung. Wenn Ihre Organisation eine allgemeine Subnetz verwendet, wird empfohlen, dass Sie das Netzwerk an ein anderes Subnetz verschieben. So stellen Sie einfacher in CQD reporting. Wenn bereits erwähnt, wurden Berichte in der Vorlage für alle Netzwerke konfiguriert zum Ausschließen von der Subnets, um sie als Quelle von schlechter Qualität zu vermeiden. Allgemeine Subnetze werden nachfolgend definiert. deren Einfluss wird je nach Organisation variieren.

-   10.0.0.0
-   192.168.0.0
-   192.168.1.0
-   192.168.2.0
-   172.20.10.0
-   192.168.43.0

Bei ein verwaltetes Netzwerk untersucht werden, das ein allgemeine Subnetz verwendet, müssen Sie die Dimension zweiten Reflexive lokale IP-Subnetze Gruppe verwenden. Diese Dimension enthält die öffentliche IP-Adresse des Endpunkts.

## <a name="cqd-online"></a>CQD Online

In diesem Abschnitt werden die Grundlagen für den Zugriff auf CQD. Anleitung erhält für den folgenden Themen:

-   Zugreifen auf CQD online
-   Erste Schritte mit CQD
-   Bearbeiten von Berichten in CQD
-   Filtern von Berichten in CQD
-   Importieren von Berichten in CQD

Ausführlicheren Schulungen und Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="access-cqd-online"></a>Access CQD Online

Sie können drei verschiedene Arten CQD zugreifen:

-   Wechseln Sie zu <https://cqd.lync.com>.

-   Wechseln Sie zur **Microsoft-Teams & Skype für Business Admin Center** , und wählen Sie den Link zur CQD, wie in der folgenden Abbildung dargestellt.

![In den linken Navigationsbereich der Link zur Anrufqualität Dashboard aktiviert ist.] (media/qerguide-image-mopo.png "In den linken Navigationsbereich der Link zur Anrufqualität Dashboard aktiviert ist.")

_Abbildung 6 – Zugriff auf CQD über die Microsoft-Teams & Skype für Business Admin Center_

-   Wechseln Sie zu der Vorversion **Skype für Business Administrationscenter** > **Extras**, und wählen Sie den Link zur CQD, wie in der folgenden Abbildung dargestellt.

![Tools in den linken Navigationsbereich ausgewählt ist, und der Link zur CQD ausgewählt ist, klicken Sie im Hauptfenster.] (media/qerguide-image-legacyui.png "Tools in den linken Navigationsbereich ausgewählt ist, und der Link zur CQD ausgewählt ist, klicken Sie im Hauptfenster.")

_Abbildung 7: Zugreifen auf CQD über die Skype für Business Administrationscenter_


### <a name="getting-started"></a>Erste Schritte

Wenn Sie zuerst CQD durchsuchen, sehen Sie auf der Seite Zusammenfassung Berichte. Die meisten der Berichte in diesem Handbuch beschrieben sind benutzerdefinierte ausführliche Berichte. Erste Schritte mit der ausführliche Berichte, wählen **Zusammenfassung Berichte** am oberen Rand der Seite, und wählen Sie dann **Ausführliche Berichte**.

![Unterschiedliche Arten von Berichten, die in CQD verfügbar sind](media/qerguide-image-choosereports.png)

_Abbildung 8: Navigieren zum ausführliche Berichte_

Die Seite ausführliche Berichte in CQD sieht wie in der folgenden Abbildung aus.

![Andere Elemente, die einen detaillierten Bericht bilden.](media/qerguide-image-detailedreportspage.png)

|             |           |
| ------------|-----------|
| ![ein] (media/qerguide-image-callout1.png "ein") | Bereich "Zusammenfassung" zeigt Kontext für den Bericht ein, der auf der rechten Seite angezeigt wird. |
| ![zwei] (media/qerguide-image-callout2.png "zwei") | Sie können **Bearbeiten** im Bereich "Zusammenfassung" auf Bericht-Ebene-Eigenschaften (y-Achse Höhe einschließlich) festgelegt und Importieren von neuen Vorlagen auswählen. |
| ![drei] (media/qerguide-image-callout3.png "drei") | Die Breadcrumb-Leiste hilft Benutzern bei ihrer aktuellen Position in der Berichtshierarchie zu identifizieren. |
| ![vier] (media/qerguide-image-callout4.png "vier") | Berichte, die ist der untergeordneten Berichte, werden mit einer blauen Link angezeigt. Wenn Sie den Link auswählen, können Sie nach unten zu den untergeordneten Berichte anzeigen. |

_Abbildung 9: ausführliche Berichtsseite_

Zeigen Sie auf Balkendiagrammen und Trendlinien im Bericht detaillierte Werte angezeigt. Zeigt der Bericht, den Fokus hat im Aktionsmenü: **Bearbeiten**, **Wenn Sie den Klon**, **Löschen**, **herunterladen**und **Berichtsstruktur exportieren**.

### <a name="editing-reports"></a>Bearbeiten von Berichten

Beim **Bearbeiten** eines Berichts im Menü Aktion auswählen, werden Sie Abfrage-Editor zu öffnen. Jeder Bericht wird durch eine Abfrage zu CQD unterstützt. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Abfrage-Editor ist eine Benutzeroberfläche zur Bearbeitung diese Abfragen zusätzlich zu den Optionen für die Anzeige für den Bericht, wie in der folgenden Abbildung dargestellt.

![Andere Elemente, die einen Bericht bilden, wenn der Bericht bearbeitet werden.](media/qerguide-image-queryeditor.png)

|             |           |
| ------------|-----------|
| ![ein] (media/qerguide-image-callout1.png "ein") | Wählen Sie Dimensionen und Measures Filter im linken Bereich. Verweisen auf einen vorhandenen Wert zeigt eine Schaltfläche zum Schließen (**X**) Sie auswählen können, um den Wert zu entfernen.<ul><li>Indem Sie die Dimension oder Measure auswählen, können Sie den Titel durch Bearbeiten im Feld **Titel** ändern. Sie können auch die Reihenfolge ändern, indem Sie die blaue nach oben oder nach unten weisenden Pfeil im oberen Bereich auswählen.</li><li>Auswählen (**+**) neben einer Überschrift Öffnet das Dialogfeld für eine neue Dimension, Measure oder Filter hinzufügen.</li><li>Geben Sie die ersten Buchstaben der Dimension, Measure oder Filter in der **Hier finden Sie eine** zum Filtern der Liste für die Suche einfacher dar.</li></ul> |
| ![zwei] (media/qerguide-image-callout2.png "zwei") | Der obere Ausschnitt zeigt Optionen zur Anpassung des Diagramms. |
| ![drei] (media/qerguide-image-callout3.png "drei") | Der Abfrage-Editor zeigt eine Vorschau des Berichts. |
| ![vier] (media/qerguide-image-callout4.png "vier") | Verwenden Sie das **Bearbeiten** am unteren Rand des Bildschirms zum Erstellen oder bearbeiten eine detaillierte Beschreibung des Berichts. |

_Abbildung 10 - Abfrage-Editor_

### <a name="filtering-reports"></a>Filtern von Berichten

Bereitgestellten Vorlagen enthalten mehrere Filter im Bericht und integrierte Abfragen. In den folgenden Abschnitten wird beschrieben, die am häufigsten verwendeten Filter in allen Vorlagen verwendet.

#### <a name="url-filter"></a>URL-filter

Sie können eine URL Filter zum Filtern jedem Bericht für eine bestimmte Dimension verwenden. Die am häufigsten verwendeten URL-Filter dienen zum Filtern von Berichten federated Teilnehmer Telemetrie ausschließen oder Teams oder Skype für Business Online Schwerpunktthemen. Es wird empfohlen, dass bei der Verwendung von Filtern Sie sie zur Hand Lesezeichen. 

Ausschließen von föderierten Data aus CQD Berichte ist nützlich, wenn Sie sind Korrigieren von verwalteten Gebäude oder Netzwerken, in dem federated Endpunkte Berichte beeinflussen können.

Um eine URL-Filter in der Adressleiste des Browsers zu implementieren, fügen Sie die folgenden am Ende der URL an:

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:  

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Um die Berichte für Teams oder Skype für Unternehmen zu filtern, fügen Sie die folgenden am Ende der URL an:

```
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

Beispiel:

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Is Teams]|[TRUE]```


> [!NOTE]
> Die URL Beispiele sind nur die visuelle Darstellung. Verwenden Sie die standardmäßige CQD Verknüpfung von <https://cqd.lync.com>.


#### <a name="query-filters"></a>Abfragefiltern

Abfragefiltern werden mithilfe des Abfrage-Editors in CQD implementiert. Diese Filter dienen zum Verringern der Anzahl von CQD, daher Minimierung des Berichts Gesamtgröße und wie oft die Abfrage zurückgegebenen Datensätze. Dies ist insbesondere dann sinnvoll für nicht verwalteten Netzwerken herausfiltern. Die Filter, die in der folgenden Tabelle verwenden regulärer Ausdrücke (RegEx) aufgeführt.

_Tabelle 3 - Abfragefilter_

| Filter         | Beschreibung          | Filter-Abfragebeispiel CQD      |
|----------------|----------------------|-------------------------------|
| Keine leeren Werte   | Einige Filter haben nicht die Option zum Filtern von leere Werte. Um leere Werte manuell zu filtern, verwenden Sie den Ausdruck leeren, und setzen Sie den Filter auf gleich oder ungleich, je nach Ihren Anforderungen.      | Erstellen von Sekunde Name \< \> \^ \\s\*\$                       |
| Allgemeine Subnetze ausschließen | Ohne eine Datei gültige Erstellen von verwalteten von nicht verwalteten Netzwerken getrennt werden in den Berichten Heimnetzwerken enthalten sein. Diese private Subnetze sind außerhalb des Bereichs des Steuerelements die und schnell aus einem Bericht ausgeschlossen werden. Allgemeine Subnetze sind gemäß Definition in diesem Handbuch 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweite Subnetz \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Nur innerhalb anzeigen  | Zum Filtern von Berichten für (inside) verwaltetem oder nicht verwaltetem (externe) verwendet. Die verwaltete CQD-Vorlage ist bereits vorkonfigurierten mit diesen filtern.       | Sekunde innerhalb Corp = innerhalb        |

#### <a name="report-filters"></a>Filter im Bericht

Filter im Bericht werden durch einen Filter hinzufügen, mit dem gerenderten Bericht entweder im Abfrage-Editor oder direkt mit dem Bericht implementiert. Die folgenden Filter im Bericht werden in der Vorlage verwendet.

_Tabelle 4 – Filter im Bericht_

| Filter     | Beschreibung                            | Beispiel für einen Filter CQD Bericht         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Beginnen Sie mit der Jahr zuerst, dann Monat. | 2017-10                           |
| Alphabetische | Filter für alle alphabetischen Zeichen. | [a-Z]                             |
| Numerische    | Filter für eine beliebige numerischen Zeichen.    | [0-9]                             |
| Prozentsatz | Filtert nach Prozentsatz.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importieren Sie die CQD-Vorlagen

Dieses Handbuch umfasst [zwei curated CQD Vorlagen](https://aka.ms/qertemplates). Diese Vorlagen die Verwendung von CQD beschleunigen und bieten Ihnen die Möglichkeit, schnell nutzen CQDs-Funktionen zu einer Beeinträchtigung der Benutzer Teams oder Skype Business wünschen. Die Vorlage alle Netzwerke optimiert gegenüber einem Gebäude entwickelt Datendatei, kann verwendet werden, während der Arbeit in Richtung sammeln und Hochladen von Erstellen von Informationen in CQD, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (. CQDX) in CQD Online**

1.  Wechseln Sie zu <https://cqd.lync.com>.

2.  Authentifizieren Sie mithilfe Ihrer Office 365-Administratoranmeldeinformationen ein.

  > [!NOTE]
  > Sie benötigen die Office 365 globaler Administrator Skype für Business Administrator oder Berichtleser-Rolle auf CQD zuzugreifen. 

3.  Wählen Sie im Menü **Zusammenfassung Berichte** am oberen Rand der Seite aus, und wählen Sie dann **Ausführliche Berichte**.

4.  Wählen Sie im Bereich "Zusammenfassung" **Importieren**aus. Besuchen Sie die CQDX Speicherort gespeichert, wählen Sie die Vorlage CQDX, und wählen Sie dann auf **Öffnen**.

5.  Nachdem die Vorlage hochgeladen wurde, wird ein Popup-Fenster Anzeigen der Meldung "Bericht Importvorgang war erfolgreich." Wählen Sie **OK.**

  ![Benachrichtigung, dass die Vorlage erfolgreich importiert wurde] (media/qerguide-image-importmessage.png "Benachrichtigung, dass die Vorlage erfolgreich importiert wurde")

6.  Wiederholen Sie die Schritte 4 und 5 für die zweite CQD-Vorlage.

> [!NOTE]
> Die Vorlagen CQD werden pro Benutzer importiert. Wenn weitere Benutzer den Bericht verwenden müssen, müssen sie anmelden und die Vorlagen in ihrer Instanz CQD importieren. 


## <a name="building-mapping"></a>Erstellen von Zuordnung

In einer Teams oder Skype für Business Online-Bereitstellung, sind alle Clients extern. Die hat der Auswirkung, dass alle Clients sind standardmäßig gemeldeten als außerhalb in CQD Online, unabhängig davon, ob der Client eine interne Unternehmensnetzwerk verbunden wurde.

Wenn Sie mit CQD arbeiten, müssen Sie den Speicherort eines Endpunkts kennen und, ob eine Verbindung mit einem zur Verwaltung oder ein Netzwerk hergestellt wurde Sie nicht verwalten – der Annahme, dass Sie nur Netzwerke verbessert werden können, können Sie verwalten. Hochladen von Subnetz und Erstellen von Informationen zu CQD Online, können Sie CQD, um zu bestimmen, ob der Endpunkt zu einem internen Netzwerk im Unternehmen/verwaltet oder mit einem externen/nicht verwaltete Netzwerk verbunden wurde.

### <a name="building-data-file-structure"></a>Erstellen von Daten-Dateistruktur

Das Format der Datei, die Sie hochladen muss die folgenden Anforderungen, übergeben die Überprüfung vor dem Hochladen erfüllen.

-   Die Datei muss entweder eine TSV-Datei, was bedeutet, dass für jede Zeile jeder Spalte durch ein Tabstoppzeichen getrennt ist – oder einer CSV-Datei, in dem jede Spalte durch ein Komma getrennt ist.

-   Die Datei darf nicht größer als 50 MB sein.

-   Der Inhalt der Daten Datei *Tabellenüberschriften nicht berücksichtigt*. Die erste Zeile der Datendatei muss mit anderen Worten, realen Daten, nicht Spaltenüberschriften wie "Netzwerk." sein.

-   In jeder Spalte kann der Datentyp nur eine Zeichenfolge, eine Zahl oder der boolesche Datentyp sein. Wenn der Datentyp Zahl ist, muss der Wert einen numerischen Wert; Wenn es Bool ist, muss der Wert 0 oder 1.

-   Für jede Spalte, wenn der Datentyp String, ist die Daten können leer sein (aber dennoch durch eine entsprechende Trennzeichen getrennt werden müssen, d. h., ein Tabulatorzeichen oder ein Komma). Dadurch wird dem Feld eine leere Zeichenfolge zugewiesen.

-   Es muss für jede Zeile von 14 Spalten. Jeder Spalte benötigen den Datentyp in der folgenden Tabelle beschrieben und die Spalten in der Reihenfolge, in der Tabelle aufgeführten sein müssen.

_Tabelle 5: Erstellen von Dateistruktur_

| Spaltenname        | Datentyp | Beispiel                   | Anleitung    |
|--------------------|-----------|---------------------------|-------------|
| Netzwerk            | Zeichenfolge    | 192.168.1.0               | Erforderlich    |
| Netzwerkname        | Zeichenfolge    | USA/Seattle/SEATTLE-SEA-1 | Erforderlich\*  |
| NetworkRange       | Zahl    | 26                        | Erforderlich    |
| BuildingName       | Zeichenfolge    | SEATTLE-SEA-1             | Erforderlich\*  |
| OwnershipType      | Zeichenfolge    | Contoso                   | Optional     |
| BuildingType       | Zeichenfolge    | IT Termination            | Optional     |
| BuildingOfficeType | Zeichenfolge    | Engineering               | Optional     |
| Ort               | Zeichenfolge    | Seattle                   | Empfohlen |
| Postleitzahl            | Zeichenfolge    | 98001                     | Empfohlen |
| Land            | Zeichenfolge    | USA                        | Empfohlen |
| Bundesland              | Zeichenfolge    | WA                        | Empfohlen |
| Region             | Zeichenfolge    | MSUS                      | Empfohlen |
| InsideCorp         | Bool      | 1                         | Erforderlich    |
| ExpressRoute       | Bool      | 0                         | Erforderlich    |

\*Während der CQD nicht erforderlich, werden die Vorlagen zum Erstellen von und Netzwerk anzeigen konfiguriert Name.

#### <a name="supernetting"></a>Supernetting

Supernetting, so genannte Classless Inter-Domain Routing (CIDR), können Sie anstelle der einzelnen Subnetze definieren. Eine *Supernetting* ist eine Kombination von mehrere Subnetze, die ein routing Präfix freigeben. Anstatt einen Eintrag für jedes Subnetz, können Sie die Adresse Supernetz verwenden. Supernetting wird unterstützt, aber es wird nicht empfohlen, dessen Verwendung.

Beispielsweise Contoso marketing erstellen die folgenden Subnetze besteht:

-   10.1.0.0/24—First Stock
-   10.1.1.0/24—Second Stock
-   10.1.2.0/24—Third Stock
-   10.1.3.0/24—Fourth Stock

Anstatt einen Eintrag für jedes Subnetz, können die Adresse Supernetz – in diesem Beispiel 10.1.0.0/22.

-   Netzwerk = 10.1.0.0
-   Netzwerk-Bereich = 22

Hier sind einige Punkte zu berücksichtigen sind vor der Implementierung von Supernetting:

-   Supernetting kann nur in einer Zuordnung Subnetz mit 8-Bit-Version auf 28-Bit-Maske verwendet werden.

-   Supernetting weniger Zeit voraus, aber es geht aber vom Umfang der Daten zu reduzieren. Nehmen wir an, dass ein Qualität Problem büroumzüge Subnetz 200.1.2.0 vorhanden ist. Wenn Sie Supernetting implementiert, werden nicht Sie wissen, wo sich das Subnetz im Gebäude befindet oder welche Art von Netzwerk (beispielsweise eine Übungseinheit) ist. Wenn Sie hatte definiert alle Subnetze für ein Gebäude und Floor Standortinformationen hochgeladen, würden Sie diese Unterscheidung finden Sie unter sein.

-   Es ist wichtig, um sicherzustellen, dass die Adresse Supernetz richtig ist und unerwünschte Subnetze abfangen nicht zur Verfügung.

-   Es ist häufig 192.168.0.0 in Daten suchen. Für viele Organisationen bedeutet dies, dass der Benutzer zu Hause ist. Für andere ist dies das IP-Adressschema für eine Zweigstelle. Wenn Ihre Organisation Büros, die diese Konfiguration verwenden verfügt, fügen Sie keine es in der Datei zum Erstellen von da es schwierig ist privat und internen Netzwerken mithilfe von gemeinsamen Subnetze unterscheiden. Finden Sie im Abschnitt zu [allgemeinen Subnetze](#common-subnets)weiter oben in diesem Handbuch.

> [!IMPORTANT]
> Der Netzwerkbereich kann verwendet werden, um eine Supernetting darzustellen. Erstellen alle neuen Daten Dateiuploads wird für überlappenden Bereiche überprüft werden soll. Wenn Sie eine Datei zum Erstellen von zuvor hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und Hochladen erneut aus, um alle überlappt identifizieren und beheben Sie das Problem. Alle Überlappung in zuvor hochgeladenen Dateien möglicherweise falschen Zuordnungen von Subnetzen zu Gebäude in den Berichten.

#### <a name="vpn"></a>VPN

Die Daten Quality of Experience (QoE), die Clients zu Office 365 senden – wobei stammende CQD Daten aus ist also – ein VPN-Flag enthält. CQD wird dies als VPN erste und zweite VPN Dimensionen angezeigt. Dieses Kennzeichen nutzt VPN-Anbieter reporting Windows, dass die VPN-Netzwerkadapter registriert einen RAS-Adapter ist jedoch. Nicht alle VPN-Anbieter registrieren ordnungsgemäß RAS-Adapter. Aus diesem Grund können Sie nicht die integrierte VPN-Abfragefilter verwenden können. Es gibt zwei Ansätze für die Einbindung der VPN-Subnetze im Gebäude Informationsdatei:

-   Definieren Sie einen **Netzwerkname** , indem Sie mit dem Text "VPN" in diesem Feld für VPN-Subnetze.

  ![CQD-Bericht, der definiert, wie ein VPN-Subnetz erstellen](media/qerguide-image-vpnnetworkname.png)

  _Abbildung 11: Netzwerkname mit VPN_

-   Definieren Sie einen **Namen erstellen** , indem Sie mit dem Text "VPN" in diesem Feld für VPN-Subnetze.

  ![CQD-Bericht, der definiert, wie eine Definition Erstellen von erstellen, die ein VPN-Subnetz umfasst.](media/qerguide-image-vpnbuildingname.png)

  _Abbildung 12: Verwenden Sie zum Erstellen von Namen VPN_

> [!IMPORTANT]
> Bestimmte VPN-Implementierungen meldet nicht genau Subnetzinformationen. In diesem Fall in Ihre Berichte, empfehlen wir, wenn Sie die Datei zum Erstellen von anstelle eines Eintrags für das Subnetz ein VPN Subnetz hinzufügen fügen Sie separate Einträge für jede Adresse als ein separates 32-Bit-Netzwerk im VPN-Subnetz hinzu. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Beispielsweise müssen Sie anstelle einer Zeile für 172.16.18.0/24, 253 Zeilen, mit einer Zeile für jede Adresse aus 172.16.18.1/32 über 172.16.18.254/32, inklusive.


> [!NOTE]
> VPN-Verbindungen bekanntermaßen die Netzwerkschnittstelle unter Umständen nicht richtig wie verkabelt, wenn die zugrunde liegende Verbindung Internet ist kabellos. Beim Betrachten der Qualität über VPN-Verbindungen können nicht vorausgesetzt, dass der Verbindungstyp genau identifiziert wurde.

### <a name="uploading-building-information"></a>Informationen zum Erstellen von hochladen

Das Dashboard CQD Zusammenfassung Berichte umfasst eine Seite **Mandanten Daten hochladen** , durch Auswählen des **Mandanten Datenupload** Link-Tags in der oberen rechten Ecke (Design für das Zahnradsymbol) zugegriffen. Auf dieser Seite wird für Administratoren ihre eigenen Informationen wie die Zuordnung von IP-Adresse und geografische Informationen, zuordnen jeder drahtlosen Zugriffspunkt und die MAC-Adresse, hochladen und so weiter.

1.  Wechseln Sie zu Online CQD, indem Sie auf <https://cqd.lync.com>.

2.  Wählen Sie in der oberen rechten Ecke der Zahnradsymbol aus, und wählen Sie auf der Seite **Zusammenfassung Berichte** **Mandanten Hochladen von Daten** .

  ![Im Dialogfeld, das angezeigt wird, während Daten hochgeladen wird](media/qerguide-image-tenantdataupload.png)

  _Abbildung 13: Menü Mandanten Daten hochladen_

3.  Alternativ ist dies Ihre zum ersten Mal CQD besuchen, werden Sie aufgefordert, Erstellen von Daten hochzuladen. Sie können **Jetzt hochladen** , navigieren zur Seite **Mandanten Datenupload** schnell auswählen.

  ![Banner, die einen Benutzer das Erstellen von Datenupload benachrichtigt.](media/qerguide-image-buildingdatauploadbanner.png)

  _Abbildung 14: Building Daten hochladen banner_

4.  Wählen Sie **Durchsuchen** , um eine Datendatei auszuwählen, auf der Seite **Mandanten Hochladen von Daten** .

5.  **Startdatum** Geben Sie an, nach dem Auswählen einer Datendatei, und geben Sie optional ein Enddatum.

6.  Nach dem **Startdatum**auswählen, wählen Sie in der Datei in CQD hoch **Hochladen** . <br><br>Bevor Sie die Datei hochgeladen wurde, wird es überprüft. Wenn die Überprüfung fehlschlägt, wird eine Fehlermeldung angezeigt anfordern, dass Sie die Datei zu korrigieren. Die folgende Abbildung zeigt einen Fehler auftritt, wenn die Anzahl der Spalten in der Datendatei nicht korrekt ist.

  ![Beispiel für ein Dialogfeld an, die beim Importieren von Daten zum Erstellen von wird eine Fehlermeldung angezeigt.](media/qerguide-image-buildingdatauploaderror.png)
 
  _Abbildung 15: Fehler beim Upload von Daten erstellen_

7.  Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.

> [!NOTE]
> Es kann zum Abschließen der Verarbeitung der Datei zum Erstellen von bis zu vier Stunden dauern. <br><br> Wenn Sie eine Datei zum Erstellen von bereits hochgeladen haben und müssen Subnetze hinzu, die möglicherweise entgangene oder ausgeschlossen werden, wurden die ursprüngliche Datei ändern, indem Sie die neue Subnetze hinzufügen, entfernen Sie die aktuelle Datei und wieder neu bearbeitete Datei hochladen. Es kann nur eine aktive Erstellen von CQD-Datendatei. 


### <a name="updating-a-building-file"></a>Erstellen von Dateien aktualisieren

Beim Sammeln von Gebäude und Subnetzinformationen, die Administratoren häufig das Erstellen von in mehreren Iterationen über einen Zeitraum Dateiupload wird, wird das Hinzufügen neuer Subnetze und Erstellen von Informationen, wie er verfügbar. In diesem Fall müssen Sie Ihre Datei Building erneut hochladen. Dieser Vorgang entspricht der anfänglichen Upload gemäß der Beschreibung im vorherigen Abschnitt, mit einigen Ausnahmen, wie im folgenden Abschnitt beschrieben.

> [!Important]
> Zum Erstellen von nur eine Datei kann gleichzeitig aktiv sein. Mehrere Gebäude-Dateien sind nicht kumulativ.

#### <a name="adding-net-new-subnets"></a>Hinzufügen neuer Subnetze net

Es gibt Situationen, wenn Sie net neue Subnetze CQD hinzufügen, die ursprünglich Teil der Topologie des Netzwerks nicht benötigen. Um net neue Subnetze hinzuzufügen, gehen Sie im Portal CQD Mandanten Hochladen von Daten:

1.  Bearbeiten Sie Erstellen von Originaldatei, und geben Sie ein Enddatum, das mindestens einen Tag vor der neuen Net auftritt, dass die Subnetze erworben wurden.
2.  Wenn Sie noch nicht über eine aktuelle Kopie verfügen, laden Sie die Originaldatei.
3.  Fügen Sie die net neue Subnetze auf die Originaldatei erstellen.
4.  Laden Sie die geänderten Erstellen von Datei nach demselben Prozess wie oben beschrieben, und legen Sie den Anfangstermin für einen Tag nach die vorherigen Erstellen von Datei endet.

#### <a name="updating-the-current-building-file"></a>Aktualisieren der aktuellen Datei erstellen

Wenn eine Datei zum Erstellen von bereits hochgeladen wird, aber fehlenden Subnetze hinzugefügt werden müssen, gehen Sie im Portal CQD Mandanten Hochladen von Daten:

1.  Wenn Sie noch nicht über eine aktuelle Kopie verfügen, laden Sie die Originaldatei.
2.  Entfernen der aktuellen Datei in CQD.
3.  Fügen Sie die neue Subnetze auf die Originaldatei.
4.  Laden Sie die Datei erstellen. Achten Sie darauf, dass das Startdatum auf mindestens acht Monate vorherige so festgelegt, dass CQD Verlaufsdaten verarbeitet werden soll.

### <a name="missing-subnets"></a>Fehlende Subnetze

Nach dem Erstellen von Informationen für verwaltete Netzwerke hochladen, sollte jeder verwalteten Netzwerks einer Zuordnung erstellen. Dies wird nicht jedoch immer der Fall sein. in der Regel werden einige Subnetze nicht eingehalten. In diesem Abschnitt wird das Überprüfen dieser fehlenden Netzwerke behandelt.

Wechseln Sie zur Seite **Ausführliche Berichte** in CQD Online, und navigieren Sie zu der **Fehlende Subnetz Bericht** in die CQD Vorlagen enthalten. Dies stellt alle Subnetze mit 10 oder mehr audio-Streams, die in die Daten zum Erstellen von definiert werden nicht Datei und markiert werden als "außen". Stellen Sie sicher, dass es keine verwalteten Netzwerke in dieser Liste sind. Wenn Subnetze nicht vorhanden sind, aktualisieren Sie die ursprünglichen Erstellen von Daten Datei und erneutes Hochladen auf CQD.

> [!IMPORTANT]
> Sie müssen Ihre Mandanten-ID als Abfragefilter für die **Zweite Mandanten-ID** für diesen Bericht Filtern des Berichts, um nur die Daten des Unternehmen Mandanten anzuzeigen hinzufügen. Andernfalls wird der Bericht federated Subnetze anzeigen.

> [!NOTE] 
> Achten Sie darauf, dass Berichtsfilter Monat-Jahr mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den Filter **Monat-Jahr** -Bericht, um den neuen Standardmonat zu speichern.

![Bericht mit Subnetze in der Datei CQD Erstellen von nicht enthalten, die Verwendung anzeigen.](media/qerguide-image-missingbuildingreport.png)

_Abbildung 16: Erstellen von Bericht fehlt_

### <a name="building-mapping-tools"></a>Erstellen von Zuordnung tools

Seien wir ehrlich, Zuordnen von Subnetzen in Ihrer Organisation kann schwierig sein. Große globale Netzwerke sind sehr komplex; mit verschiedenen Teams verwalten ihre jeweiligen Regionen und möglicherweise keine zentrale Quelle Wahrheit für die Topologie des Netzwerks. Es gibt zwei Tools unterstützen Sie beim Starten der Zuordnung erstellen von Übung in den folgenden Abschnitten beschrieben.

#### <a name="cqd-tools"></a>CQD-tools

Diese Tools basieren auf PowerShell und Active Directory (AD)-Standorte und -Dienste nutzen können, und Microsoft DHCP-Dienste, mit denen Ihre Datei zum Erstellen von vorab auszufüllen.  Diese Tools hilft bei den folgenden Aufgaben:

1.  Abfragen von Active Directory-Standorte und Dienste, und erstellen Sie eine anhand der enthaltenen Informationen zum Erstellen von Datei.
2.  Fragen Sie einen Microsoft DHCP-Server oder Server Subnetzinformationen und automatisch eine Datei zum Erstellen von erstellt ab.
3.  Überprüfen einer vorhandenen Erstellen von Datei überprüfen auf Duplikate und überlappt.
4.  Hier finden Sie nicht zugeordnete Subnetze in CQD.

Weitere Informationen zu diesem Tool finden Sie unter [in diesem Blogbeitrag](https://aka.ms/cqdtools).

#### <a name="network-planner"></a>Netzwerk-Planner

Der Netzwerk-Planner bestimmt und die netzwerkanforderungen für Ihre Cloud-VoIP-Bereitstellung in nur wenigen Schritten organisiert. Durch bereitstellen, dass Ihre Organisation Details und Cloud Voicemail Nutzung networking des, können Sie eine ungefähre Berechnung der netzwerkanforderungen für Ihre Cloud-VoIP-Bereitstellung abgerufen, verwalten und Exportieren diese Details für reporting und zur weiteren Untersuchung Bereiche anzeigen und nächste Schritte.

Obwohl der Netzwerk-Planner Erstellen von Zuordnung vollständig automatisieren nicht nach Eingabe Netzwerkinformationen in der Netzwerk-Planner können sie in eine Building-Datei für den Upload vorbereitet exportiert werden.

Es wird dringend empfohlen, dass Sie bei der Bereitstellung von Medien Arbeitslasten in Ihrem Netzwerk bewerten Sie die gesamte Auswirkung der Netzwerk-Planner nutzen. Weitere Informationen zu der Netzwerk-Planner finden Sie auf [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).


## <a name="reliability-investigations"></a>Zuverlässigkeit Untersuchungen

Der erste Schritt zum Verbessern der Qualität wird den Status der Zuverlässigkeit in der gesamten Organisation bewerten. Da Zuverlässigkeit entscheidend für eine positive Benutzeroberfläche zur Verfügung steht, starten wir mit den zwei Komponenten, die Zuverlässigkeit messen:

1.  **Setup-Fehler:** Die Verbindung konnte nicht hergestellt werden.

2.  **Drop-Fehler:** Der Anruf wurde eingerichtet und unerwartet beendet.

In diesem Abschnitt werden Methoden zum Untersuchen Sie beide Bereiche behandelt.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt.  Die Methoden des Untersuchung nachfolgend erläuterten gelten jedoch weiterhin. Die Beschreibung der einzelnen Berichts Weitere Informationen finden.


### <a name="setup-failures"></a>Fehler bei der Installation

Priorisieren Sie korrigieren von Setupfehler in diesem Bereich zuerst, da diese Fehler erhebliche negative Auswirkungen auf die Benutzeroberfläche vorhanden ist.

Zunächst die Bewertung des Prozentsatz der gesamten Setupfehler für die Organisation der Überprüfung, und klicken Sie dann priorisieren Bereiche der Untersuchung basierend auf den höchsten Prozentsatz von erstellen oder im Netzwerk. 

#### <a name="setup-failure-trend-analysis"></a>Setup-Fehler Trendanalysen

In diesem Bericht werden angezeigt, der die Gesamtmenge des Streams, Stream Setupfehler und Stream-Setup-Fehlerrate. Zeigen Sie auf eine der Spalten auf die einzelnen Werte, anzuzeigen, wie in der folgenden Abbildung dargestellt. 

![Ein Diagramm, Prozentsatz der Stream Setupfehler](media/qerguide-image-streamsetupfailures.png)

_Abbildung 16 - Audiozuverlässigkeit - Stream Setupfehler_

##### <a name="analysis"></a>Analyse

Mithilfe dieses Berichts können Sie die folgenden Fragen beantworten und Ihre weitere Vorgehensweise bestimmen:

-   Was ist der Prozentsatz der gesamten Anruf Setup Fehler für den aktuellen Monat?

-   Ist insgesamt Anruf Setup Fehler Prozentsatz unter oder über die Metrik definierten Ziel?

-   Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

-   Ist der Ausfall Trend erhöhen, steady, oder verringern?

Selbst wenn der vorherigen Antworten Zeit in Anspruch nehmen die untersuchen Weitere mithilfe der Companion Unterberichte für jeden einzelnen Gebäude oder die Subnetze, die möglicherweise Remediation gesucht. Zwar die Fehlerrate insgesamt unterhalb der Ziel-Metrik die Fehlerraten für eine oder mehrere Gebäude oder Netzwerke möglicherweise über die Ziel-Metrik und Untersuchung erfordern.

#### <a name="setup-failure-investigations"></a>Setup-Fehler Untersuchungen 

Diese Zusammenfassungsbericht wird verwendet, zu ermitteln und alle Gebäude oder Netzwerke, die möglicherweise Remediation isolieren.

> [!NOTE]
> Achten Sie darauf, dass Berichtsfilter Monat-Jahr mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den Filter **Monat-Jahr** -Bericht, um den neuen Standardmonat zu speichern.


![Eine Liste der Gründe für die Anruf-Setupfehler organisiert erstellen, Netzwerk und Subnetz pro Monat](media/qerguide-image-setupfailuresbysubnet.png)

_Abbildung 18: Audio Setupfehler von Subnetz_

##### <a name="remediation"></a>Wartung 

Konzentrieren Sie sich Ihre ersten Remediation-Maßnahmen auf Gebäude oder Subnetze abgerufen, die das größte Volume der Fehler haben. Dies maximieren Auswirkung auf die Benutzeroberfläche und Ihnen dabei helfen, um schnell die Rate der Organisationseinheit Anruf Setupfehler zu reduzieren. Die folgende Tabelle enthält die beiden Gründe für Fehler bei der Installation von CQD gemeldet.

_Tabelle 6 – Gründe für Setup Anruffehlern_

| Rufen Sie die Ursache für Fehler bei der Installation       | Typische Ursache                    |
|----------------------------------|----------------------------------|
| Fehlende Firmware Tiefe Paket Prüfung Ausnahmeregel | Gibt an, dass Netzwerkgeräte entlang des Pfads der Medienpfad daran gehindert, aufgrund von Tiefe Paket Prüfung Regeln hergestellt wird. Dies ist wahrscheinlich durch die Firewall-Regeln wird nicht ordnungsgemäß konfiguriert. In diesem Szenario der TCP-Handshake erfolgreich abgeschlossen wurde, aber nicht SSL-Handshake.      |
| Fehlende Firmware IP-Block Ausnahme-Regel      | Gibt an, dass Netzwerkgeräte entlang des Pfads der Medienpfad daran gehindert, mit dem Office 365-Netzwerk hergestellt wird. Dies kann aufgrund von Proxy oder der Firewall-Regeln wird nicht Gewährung des Zugriffs für IP-Adressen und Ports für Teams und Skype für Business-Datenverkehr verwendet, um ordnungsgemäß konfiguriert sein. |

Nun, wie Sie Ihre Remediation beginnen, können Sie sich in einem bestimmten Gebäude oder Subnetz konzentrieren. Wie in die obigen Tabelle gezeigt wird, werden diese Probleme aufgrund der Firewall oder der Proxyserver Konfigurationen. Überprüfen Sie die Optionen in der folgenden Tabelle für Remediation Aktionen.

_Tabelle 7: nächste Schritte für Anruf Setup Fehler-Wartung_

| Wartung           | Anleitung     |
|-----------------------|--------------|
| Konfigurieren von firewall(s) | Arbeiten mit Ihrem Netzwerkteam, und überprüfen Sie Ihre Konfiguration Firewall(s) anhand [der Liste der Office 365-IP-Adresse](https://aka.ms/o365ips).<br><br>Stellen Sie sicher, dass die [Medien Subnetze](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) und Ports in der Firewall-Regeln enthalten sind. <br><br>Stellen Sie sicher, dass die erforderlichen Ports (siehe unten) in der Firewall geöffnet werden. UDP sollte Priorität erteilt werden, da TCP ein Failback-Protokoll für Audio-, Video-gilt und videobasierte Bildschirmfreigabe und dessen Verwendung sich auf die Qualität des Anrufs wirkt. TCP verwendet nur Legacy RDP-Anwendungsfreigabe.<br><ul><li>**TCP:** -port 443</li><li>**UDP:** 3478 – 3481 ports</li><ul> |
| Vergewissern Sie sich                | Verwenden Sie das [Tool zur Bewertung der Microsoft Network](https://www.microsoft.com/download/details.aspx?id=53885) , um die Konnektivität von der betroffenen Gebäude oder Subnetz mithilfe der Konnektivität Kontrollkästchen-Funktion zu überprüfen.    |


### <a name="drop-failures"></a>Drop-Fehlern

Im Gegensatz zu Setup-Fehlercodes hat CDQ keine Drop-Fehlercode an, warum Drop Auftreten von Fehlern die macht es schwierig, eine bestimmte Ursache zu isolieren. Um eine bessere Ursachenanalyse drop Fehlern, einen abgeleiteten Ansatz verwenden. Durch Korrigieren von Bereiche von Interesse für Medien, patching Clients und Treiber und treibende Verwendung der zertifizierte Geräte für Teams und Skype für Unternehmen, können Sie die Drop-Fehlern so lehnen Sie erwarten.

#### <a name="drop-failure-trend-analysis"></a>Drop Fehler Trendanalysen

In diesem Bericht werden angezeigt, der die Gesamtmenge des Audiostreams insgesamt Drop-Fehlern und die Drop-Fehlerrate. Zeigen Sie auf eine der Spalten zur Anzeige der Werte wie in der folgenden Abbildung dargestellt. 

![Diagramm mit den Prozentsatz der Datenströme, die gelöscht wurden](media/qerguide-image-droppedstreamrate.png)

_Abbildung 19: Initiale Stream rate_

##### <a name="analysis"></a>Analyse

Diese Art von Bericht verwenden, können Sie die folgenden Fragen beantworten:

-   Was ist die aktuelle Drop-Fehlerrate?
-   Ist die Drop-Fehlerrate unterhalb der definierten Ziel Metrik?
-   Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?
-   Ist der Ausfall Trend erhöhen, steady, oder verringern?

Antworten auf die obigen Fragen unabhängig nehmen die Zeit, überprüfen Sie die Verwendung der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Remediation. Zwar die Fehlerrate insgesamt Drop unterhalb der Ziel-Metrik die Drop-Fehlerrate für eine oder mehrere Gebäude oder Netzwerke möglicherweise über die Ziel-Metrik und Untersuchung erfordern.

#### <a name="drop-failure-investigations"></a>Drop Fehler Untersuchungen

Hier gemeldeten Fehler hervor, dass der Anruf wurde unerwartet gelöscht und eine negative Benutzeroberfläche zur Verfügung führte. Im Gegensatz zu der Trend Berichte ermöglichen diese Berichte zusätzliche Einblicke in bestimmten Subnetze, die weitere Untersuchung benötigen.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.


![Meldet, dass die Listen Anzahl und den Prozentsatz der Drop-Fehler erstellen, Netzwerk und Subnetz pro Monat geordnet](media/qerguide-image-dropfailuresbysubnet.png)

_Abbildung 20 – Drop Fehler durch Subnetz_

##### <a name="remediation"></a>Wartung

Die Tabellenberichte enthalten können Sie Problem isolieren, die Bereiche im Netzwerk, in dem die Drop-Rate über die Ziel-Metrik Sie liegt, definiert haben. Konzentrieren Sie sich Ihre ersten Remediation-Maßnahmen auf Gebäude oder Subnetze abgerufen, die die höchste insgesamt Stream Count am stärksten beeinträchtigt vornehmen müssen.

Häufige Ursachen für Anruf Ansätzen:

-   Klicken Sie unter bereitgestellte Netzwerk oder Internet Ausgang
-   Keine QoS auf eingeschränkte Netzwerke konfiguriert ist
-   Ältere Clientversionen
-   Verhalten der Benutzer

Nachdem Sie Ihr Problembereiche erkennen, können [Analytics aufrufen,](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) Sie um Benutzer in das Gebäude für bestimmte Probleme weiter zu überprüfen. Anruf Analytics enthält PII-Daten und hilfreich, um weitere mögliche Gründe für die Drop-Fehler werden kann.

Unabhängig von der nächste Schritt ist es ratsam, dem Helpdesk benachrichtigen, dass es sich bei Auftreten eines Problems mit einem bestimmten Gebäude oder Subnetzen. Auf diese Weise können schnell reagieren auf eingehende Anrufe und Benutzer effizienter selektieren. Gekennzeichnete Benutzer können dann wieder an das Entwicklungsteam zur weiteren Untersuchung gemeldet werden.

Die folgende Tabelle enthält einige allgemeinen Methoden zum Verwalten und Warten von Drop-Fehler.

_Tabelle 8: nächste Schritte für Anruf drop-Wartung_

| Wartung                              | Anleitung                      |
|------------------------------------------|-------------------------------|
| **Netzwerk/internet**                         | **Eine Überlastung**: Arbeiten mit Ihrem Netzwerkteam zum Überwachen der Bandbreite bei bestimmten Gebäude/Subnetze zu bestätigen, dass Probleme mit übermäßiger vorliegen. Bestätigen Sie, dass Überlastung des Netzwerks vorhanden ist, sollten Sie sich eine Erhöhung Bandbreite für das Gebäude oder QoS anwenden. Verwenden Sie, der [Anrufe schlechter Qualität-Stream zusammenfassende Bericht](#quality-investigations) enthalten um die Subnetze Problem bei Problemen mit Jitter, der Wartezeit und Paketverlust, prüfen, da diese oft einen Initiale Stream vorangestellt werden.<br><br>Das [Netzwerk Planner-Tool](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) können auch unterstützen die bandbreitenanforderungen Ihrer Organisation besser zu verstehen.<br><br>**QoS**: Wenn einer steigenden Bandbreite nicht praktikabel oder kostspielig ist, sollten Sie die Implementierung der QoS. Dieses Tool ist sehr effektiv bei der Verwaltung von überlastete Datenverkehr und kann sicherstellen, dass Media-Pakete im verwalteten Netzwerk oben nicht Mediendatenverkehr priorisiert werden. Auch wenn es gibt keine klare Hinweise, dass die Bandbreite Ursache ist, sollten Sie diese Lösungen:<ul><li>[Microsoft-Teams QoS-Anweisungen](qos-in-teams.md)</li><li>[Skype für Business QoS-Anweisungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Durchführen einer Netzwerk-Bereitschaft**: eine Netzwerk-Bewertung enthält Details zur Nutzung der erwarteten Bandbreite, wie bewältigen Bandbreite und Netzwerk ändert und empfohlenen Netzwerke Methoden für Teams und Skype für Unternehmen. Verwenden der obigen Tabelle als Quelle, müssen Sie eine Liste von Gebäude oder Subnetze, die eignen sich für eine Bewertung sind.<ul><li>[Microsoft-Teams, Netzwerk-Bereitschaft](3-envision-evaluate-my-environment.md#test-the-network)</li><li>[Skype für Business Netzwerk Bereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Tool zur Bewertung der Microsoft Network:** Verwenden Sie dieses Tool für einen einfachen Test der Leistung des Netzwerks, um zu bestimmen, wie gut das Netzwerk für eine Teams ausführen würden oder Skype für Business Online Anruf. Das Tool können Sie die Leistung eines Subnetzes bewerten und überprüfen die Bereitschaft des Netzwerks gegen Microsoft Leistung [Anforderungen](https://aka.ms/performancerequirements).<ul><li>[Laden Sie das Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br>**CxdCallData**: Dieses Skript zum Zuordnen eines Subnetzes auf bestimmte Benutzer innerhalb von Anrufen Analytics-Hilfe verwendet werden. CQD keinen PII Daten, damit es zum Zuordnen von Subnetzen tatsächliche Benutzer schwierig sein kann. Wenn Sie feststellen, dass bestimmte Subnetze hohe Jitter oder Paketverlusten auftritt, können Sie das Skript verwenden, zum Extrahieren von Daten direkt aus dem Dienst zum Anzeigen einzelner Anruf Informationen wie Benutzernamen, Transport, Jitter, Paketverlust, Wartezeit und vieles mehr. Das Skript wird ebenfalls eine direkte Verknüpfung mit dem Bericht in Analytics aufrufen, um zusätzliche Ursachenanalyse ermöglichen zurückgegeben. Dieses Skript finden Sie in der Galerie PowerShell:<ul><li>[https://www.powershellgallery.com/packages/CxdCallData](https://www.powershellgallery.com/packages/CxdCallData)</li></ul> |
| **Clients (Skype für Unternehmen nur Online)** | Einige ältere Clients wissen müssen, werden Probleme mit der Zuverlässigkeit Media dokumentiert. Überprüfen Sie die aufrufen Analytics-Berichte aus mehreren betroffenen Benutzer, oder erstellen Sie einen benutzerdefinierten Bericht der Clientversion-Tabelle in CQD in bestimmten Gebäude oder Subnetze mit Fehler insgesamt aufrufen abgelegten % Measure gefiltert. Diese Informationen helfen Ihnen beim verstehen, ob eine Beziehung zwischen Anruf setzt in dieser bestimmten Gebäude und eine bestimmte Version des Clients vorhanden ist.     |
| **Geräte**                                  | Es wird empfohlen, dass alle Benutzer, die auftreten, setzt aufrufen – oder schlecht Anrufe im Allgemeinen – und werden mithilfe von integrierten Geräte werden sollte bereitgestellt wird, ein [certified Kopfhörer oder eines Freisprechtelefons](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) um dies als potenzielle Quelle schlechter Qualität und Zuverlässigkeit zu entfernen. |
| **Verhalten der Benutzer**                            | Wenn Sie feststellen, dass weder Netzwerk, Geräte oder Clients behoben werden, sollten Sie ansprechender [Meine Advisor](https://aka.ms/myadvisor) Anleitung bei der Entwicklung einer Strategie für die Einführung, um Benutzer informieren, wie Sie bewährte beitreten und Besprechungen zu beenden. Ein intelligenter Teams und Skype für Geschäftsbenutzer erzeugt eine höhere benutzerfreundlichkeit für alle Teilnehmer in der Besprechung. Ein Benutzer, der ihren Laptop in den Energiesparmodus (von der Abdeckung schließen) versetzt, ohne zu verlassen der Besprechung werden als ein unerwarteter Aufruf Drop klassifiziert werden.   |

## <a name="quality-investigations"></a>Qualität Untersuchungen

Im nächste Schritt den Zustand der Audioqualität in der gesamten Organisation bewerten ist schlecht Stream Rate (a.), TCP und Proxy Verwendung untersuchen. Es ist wichtig, denken Sie daran, dass CQD Daten bestimmte Ursache nicht enthalten, aber Sie stattdessen wahrscheinlich Problembereiche zu Beginn einer gemeinsame Unterhaltung mit der entsprechenden Teams für Abhilfemaßnahmen bietet. 

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte enthalten in den Vorlagen enthalten; die Methoden des nachfolgend erläuterten Untersuchung werden jedoch weiterhin für diese Berichte angewendet. Verweisen Sie auf die einzelnen Beschreibung Weitere Informationen. 

### <a name="quality"></a>Qualität

Die Prozentsätze a. werden verwendet, um anzugeben, ob die Organisation definierten metrischen Ziele für einen bestimmten Fokusbereich erfüllt. Es ist wichtig, beachten Sie, dass, auch wenn die allgemeine Prozentsätze innerhalb des Ziels definiert sind, einzelnen Subnetze oder Gebäuden möglicherweise nicht die definierten Ziele erfüllen und, daher weitere Untersuchung sollten. Beispielsweise ist der gesamte audio a. Prozentsatz 2 Prozent in möglicherweise April, die die Beispiel-Ziel, einzelne Gebäude und Subnetzen entspricht weiterhin schlechte Erfahrungen, je nach der allgemeinen Verteilung dieser 2 Prozent haben. 

Informationen zum Bewerten des Prozentsatz der Anrufe schlechter Datenströme, verwenden Sie die Berichte für die Qualität. Metriken für allgemeine, Konferenzen, zwei Teilnehmern PSTN aufrufen, VPN- und Besprechungsräumen überprüfen werden verschiedene Qualität-Berichte bereitgestellt. In diesem Prozess unterstützen, werden monatlich, wöchentlich oder täglich Berichte bereitgestellt. Wöchentliche und tägliche Berichte können nur die verwalteten Netzwerken Vorlage zum Erhöhen von Effizienz und Rauschen. 

#### <a name="quality-trend-analysis"></a>Qualität Trendanalysen

Trend-Berichte anzeigen von Informationen über einen Zeitraum Qualität und dienen zum Identifizieren und verstehen Qualität Trends in jedem Bereich von Interesse. Wie bereits erwähnt, existieren Bericht Strukturen in den Vorlagen für die Qualität untersuchen enthalten ist. Konferenz-, zwei Teilnehmern, PSTN-Anrufe, VPN und Besprechungsräumen. Für die Qualität analysieren Zwecke ist der Einsatz Vorgang identisch. Jedoch wird empfohlen, dass Sie zuerst mit Konferenz beginnen, da Verbesserungen in Konferenz Qualität positiv auch alle anderen Bereiche auswirkt. 

> [!Note]
> Untersuchen von zwei Teilnehmern, PSTN-Anrufe und Besprechungsräumen ähneln Untersuchen von Konferenzen. Der Schwerpunkt liegt auf Isloate Gebäude oder Subnetze, die die schlechteste Qualität und identifizieren Sie den Grund für die schlechter Qualität.

> [!Important]
> VPN-basierte Berichte werden mithilfe der zweite VPN-Dimension gefiltert. Diese Dimension erfordert, dass die VPN-Netzwerkadapter als Remote Access Adapter ordnungsgemäß registriert sein.  VPN-Herstellern don'tt zuverlässig verwenden Sie dieses Flag und Ihre Mileage variiert je nach dem VPN-Anbieter in Ihrer Organisation bereitgestellt. Befolgen Sie die Anleitung konturierte [Weiter oben in diesem Handbuch](NEED LINK) zum Ändern des VPNs gibt an, ob mit dem Namen Erstellen von oder im Netzwerk benötigt.

![Diagramm mit den Prozentsatz Anrufe schlechter Qualität Datenströme](media/qerguide-image-audioqualityconferencing.png)

_Abbildung 21 – Audioqualität - Konferenzen_

##### <a name="investigation"></a>Untersuchung

Mithilfe dieser Berichte können Sie die folgenden Fragen beantworten:

-   Was ist der gesamte a. für den aktuellen Monat?
-   Ist die a. unterhalb der definierten Ziel Metrik?
-   Ist a. schlechter oder höherer Leistung als den vorherigen Monat?
-   Ist der Trend a. erhöhen, steady, oder verringern?

Antworten auf die obigen Fragen unabhängig Zeit in Anspruch nehmen die mithilfe der Unterberichte, suchen Sie nach Gebäude oder Subnetze, die möglicherweise Untersuchung untersuchen. Zwar die allgemeine a. unterhalb der Ziel-Metrik oft die a. für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und-Wartung benötigt.

#### <a name="quality-investigations"></a>Qualität Untersuchungen

Die Qualität Zusammenfassungsberichte Sie tiefere Einblicke übergeben in was beigetragen an die Datenströme, das als schlecht klassifiziert und trägt dazu bei, um Problembereiche im verwalteten Netzwerk zu isolieren.

Obwohl die Dimensionen zwischen Bericht etwas abweichen, wird jede Bericht Maßnahmen zur Datenströme gesamt, insgesamt schlechte Datenströme, a. und schlechter Qualität aufgrund von enthalten. Tabellenberichte für die einzelnen Bereiche von Interesse erstellt wurden:-Konferenzfunktion, mit zwei Teilnehmern PSTN aufrufen, VPN- und meeting Räumen. Die verwalteten Netzwerk-Vorlage enthält weitere Berichte nutzen die Standortinformationen, die über das Erstellen von Datei hochgeladen.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.

> [!Note]
> Allgemeine Subnetze sind schwieriger zu Ursachenanalyse aufgrund der weit verbreitete Verwendung. Ein separater Bericht, der Client öffentliche IP-Adresse (zweite Reflexive lokale IP-Adresse) angezeigt, wurde hinzugefügt, um die Vorlage alle Netzwerke mit Korrigieren von Büros unterstützen, die gängigen Netzwerke verwenden.


![Schlechte Audiostream Zusammenfassung](media/qerguide-image-poorqualitysummary.png)

_Abbildung 22 – Zusammenfassung durch Erstellen von schlechter Audiostream- und Subnetz Konferenzen_

##### <a name="remediation"></a>Wartung

Konzentrieren Sie Ihre Remediation auf Gebäude oder Subnetze abgerufen, die das größte Volume Datenströme, haben, da dies Auswirkungen maximieren und Ihnen dabei helfen, die um der Benutzer schnell zu optimieren. Verwenden Sie die Jitter, Paketverlust und Round-Trip Zeitmaßeinheiten (Zeit) um zu verstehen, was zu schlechter Qualität beitragen ist (es ist möglich, mehr als ein Problem werden):

-   **Jitter**: eingeht Media-Pakete mit unterschiedlichen-Geschwindigkeit, dass bei einen Lautsprecher, um automatischen auszugeben.
-   **Paketverlust**: Media-Pakete werden verworfen wird, wodurch die Auswirkung der fehlenden Wörter oder Silbenschrift verwenden erstellt.
-   **Zeit**: Media-Pakete sind sehr lange dauert, an das Ziel abgerufen werden, das einen Effekt Walkie-talkie erstellt.

Um Ihre Untersuchung Qualitätsprobleme rechten zu unterstützen, können Sie [Rufen Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)nutzen. Mit Analysen aufrufen können Sie einer bestimmten Konferenz oder Benutzer detaillierte Anruf Bericht anzeigen. Dieser Bericht enthält PII-Daten und ist hilfreich, wenn Sie für die Fehlerursache suchen. Nachdem Sie wissen, welche Building betroffen ist, sollte die Benutzer in das Gebäude ausfindig unkompliziert sein. Hilfe bei der Zuordnung eines Subnetzes schlechten zu einem Benutzer verwenden Sie das [CxdCallData](https://github.com/jasonshave/CxdCallData) -Skript mithilfe der SubnetCsvFile-Funktion.

Vergessen Sie nicht, lassen Sie das Helpdesk wissen, dass diese Netzwerke Qualität, Probleme haben, sodass sie schnell selektieren und eingehende Anrufe beantworten können.

_Tabelle 9: Allgemeine Beiträge zu hohe a._

| Wartung                              | Anleitung                         |
|------------------------------------------|----------------------------------|
| **Netzwerke**                                 | **Eine Überlastung**: ein Netzwerk Überbelastung oder unter bereitgestellte kann Probleme mit der Medienqualität. Arbeiten mit dem Netzwerkteam, um festzustellen, ob die Netzwerkverbindungen aus der Benutzer auf das Internet Ausgang zeigen hat genügend Bandbreite für Medien unterstützen. Der [Planner Netzwerk](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) helfen Ihnen die Bandbreite-Anforderungen Ihrer Organisation besser zu verstehen.<br><br>**Durchführen einer Netzwerk-Bereitschaft**: eine Netzwerk-Bewertung enthält Details zur Nutzung der erwarteten Bandbreite, wie bewältigen Bandbreite und Netzwerk ändert und empfohlenen Netzwerke Methoden für Teams und Skype für Unternehmen. Verwenden der obigen Tabelle als Quelle, müssen Sie eine Liste von Gebäude oder Subnetze, die eignen sich für eine Bewertung sind.<ul><li>[Microsoft-Teams, Netzwerk-Bereitschaft](3-envision-evaluate-my-environment.md#test-the-network)</li><li>[Skype für Business Netzwerk Bereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Tool zur Bewertung der Microsoft Network:** Verwenden Sie dieses Tool für einen einfachen Test der Leistung des Netzwerks, um zu bestimmen, wie gut das Netzwerk für eine Teams ausführen würden oder Skype für Business Online Anruf. Das Tool können Sie die Leistung eines Subnetzes bewerten und überprüfen die Bereitschaft des Netzwerks gegen Microsoft Leistung [Anforderungen](https://aka.ms/performancerequirements).<ul><li>[Laden Sie das Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br>**CxdCallData**: Dieses Skript zum Zuordnen eines Subnetzes auf bestimmte Benutzer innerhalb von Anrufen Analytics-Hilfe verwendet werden. CQD keinen PII Daten, damit es zum Zuordnen von Subnetzen tatsächliche Benutzer schwierig sein kann. Wenn Sie feststellen, dass bestimmte Subnetze hohe Jitter oder Paketverlusten auftritt, können Sie das Skript verwenden, zum Extrahieren von Daten direkt aus dem Dienst zum Anzeigen einzelner Anruf Informationen wie Benutzernamen, Transport, Jitter, Paketverlust, Wartezeit und vieles mehr. Das Skript wird ebenfalls eine direkte Verknüpfung mit dem Bericht in Analytics aufrufen, um zusätzliche Ursachenanalyse ermöglichen zurückgegeben. Dieses Skript finden Sie in der Galerie PowerShell:<ul><li>[https://www.powershellgallery.com/packages/CxdCallData](https://www.powershellgallery.com/packages/CxdCallData)</li></ul> |
| **Quality of Service (QoS)**  | QoS ist eine bewährte Tool, das Ihnen Pakete in einem Netzwerk überlastete, um sicherzustellen, dass sie am Ziel intakt eingehen und priorisieren. Berücksichtigen Sie die Implementierung der QoS in Ihrer Organisation, die die Qualität des Benutzererlebnisses maximieren, in dem Bandbreite eingeschränkt wurde. QoS helfen, Probleme, die in der Regel mit hoher Paketverlust, lösen und – in geringerem Maße – Jitter und Round-Trip Zeiten.<ul><li>[Microsoft-Teams QoS-Anweisungen](qos-in-teams.md)</li><li>[Skype für Business QoS-Anweisungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul> |
| **Wi-Fi**               | Wi-Fi kann eine erhebliche Auswirkungen auf die Anrufqualität haben. Wi-Fi-Bereitstellungen nicht in der Regel berücksichtigen Sie die netzwerkanforderungen für die VoIP-Dienste und sind häufig die Ursache von schlechter Qualität. Weitere Informationen zum Optimieren der Wi-Fi-Infrastruktur finden Sie unter [in diesem Artikel zur Planung der Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**WLAN-Treiber**: Stellen Sie sicher, dass wireless-Treiber auf dem aktuellen Stand sind. Dadurch wird eine beliebige benutzerfreundlich im Zusammenhang mit einer veralteten Treiber zu mindern. Viele Organisationen ohne wireless-Treiber in ihre Patch-Zyklen einzuschließen können, und diese Treiber ohne Patch Jahren. Viele drahtlose Probleme werden gelöst, indem sichergestellt wird, dass die WLAN-Treiber auf dem aktuellen Stand sind.<br><br>**WMM**: Wireless Multimedia Extensions (WMM), auch bekannt als Wi-Fi Multimedia bietet grundlegende QoS-Features für drahtlose Netzwerke. Moderne drahtlose Netzwerke müssen vielen Geräten unterstützen. Diese Geräte konkurrieren für Bandbreiten- und können dazu führen, dass Qualitätsprobleme für VoIP-Dienste, wo sind Geschwindigkeit und Wartezeit wichtiger. Wenden Sie sich an den Hersteller Ihres drahtlosen Einzelheiten und implementieren Sie WMM im drahtlosen Netzwerk Skype für Geschäfts- und Teams Medien priorisieren.<br><br>**Access Point Dichte**: Zugriffspunkte können weit auseinander oder nicht in einen ideale Ort zu sein. Um Probleme zu minimieren, setzen Sie zusätzliche Zugriffspunkte in Konferenzräumen und Speicherorte, die blockiert werden nicht durch Wände oder sonstigen Objekte, in dem das Wi-Fi-Signal schwach ist.<br><br>**Mit 2,4 GHz statt 5 GHz**: 5 GHz enthält weniger Störungen im Hintergrund und einer höheren Geschwindigkeit und bei der Bereitstellung von VoIP über Wi-Fi priorisiert werden sollte. Jedoch 5 GHz ist nicht so stark wie mit 2,4 GHz nicht zugelassen und Walls so einfach. Überprüfen Sie vom Layout erstellen, um die Häufigkeit bestimmen Sie für die optimale Verbindung verwenden können. |
|**Netzwerkgerät** | In größeren Organisationen möglicherweise Hunderte von Geräten, die über das Netzwerk verteilt. Arbeiten Sie mit Ihrem Netzwerkteam, um sicherzustellen, dass die Netzwerkgeräte vom Benutzer mit dem Internet verwaltet und auf dem aktuellen Stand sind. |
| **VPN**  | VPN-Geräte eignen sich nicht traditionell, Real-Time Media Arbeitslasten zu behandeln. Einige VPN-Konfigurationen verhindern die Verwendung von UDP (Dies ist das bevorzugte Protokoll für Medien) und stützen sich nur auf TCP. Berücksichtigen Sie die Implementierung einer [VPN-Split-Tunnel Lösung](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) zur Verringerung der VPN als Quelle von schlechter Qualität. |
| **Clients** <br>(Skype für Unternehmen nur Online) | Ältere Clients wurden als verursacht Probleme mit Medien. Stellen Sie sicher, dass Clients innerhalb von sechs Monaten nach Veröffentlichung gepatcht werden. [MyAdvisor](https://aka.ms/myadvisor) Hinweise zum Entwickeln einer Strategie für die Bereitschaft Client verwenden und Bereitstellen von [Klick-und-Los](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus). |
| **Geräte** | Die Verwendung der [Geräte optimiert](https://partnersolutions.skypeforbusiness.com/solutionscatalog) , damit die Benutzeroberfläche wesentlich verbessert. Optimierte Geräte dienen mit alles gleich können Sie die Arbeit mit Teams und Skype für Unternehmen zu maximieren und Erstellen von höchster Qualität. Verwenden Sie [MyAdvisor](https://aka.ms/myadvisor) Anleitungen zum Entwickeln einer Strategie für die Bereitschaft Gerät. |
| **Treiber** | Patchen von Netzwerk (Ethernet und Wi-Fi), Audio-, Video- und USB-Treiber sollten Bestandteil Ihrer gesamten Patch-Management-Strategie sein. Viele Qualitätsprobleme werden durch Aktualisieren der Treiber gelöst. |

### <a name="tcp"></a>TCP

TCP gilt ein Failback Transport- und nicht den primären Transport für Real-Time Media gewünschte. Der Grund dafür, dass sie ein Failback Transport ist besteht aufgrund der dynamische TCP. Beispielsweise, wenn ein Anruf erfolgt in einem Netzwerk latente und Medien Pakete verzögert werden klicken Sie dann Pakete von ein paar Sekunden vor – die eignen sich nicht mehr – konkurrieren für Bandbreite, um an den Empfänger zu abzurufen, die eine ungültige Situation verschlechtern können. Dadurch wird das audio Reparatur zusammenfügen und Dehnen Audio, wodurch hörbaren Artefakte, häufig in Form von Jitter.

Die Berichte in diesem Abschnitt stellen keine Unterscheidung zwischen gute und schlechte Datenströme. UDP bevorzugte ist, suchen die Berichte für die Verwendung von TCP für Audio-, Video- und videobasierte Bildschirmfreigabe (VBSS). Dies wird hauptsächlich durch unvollständig Firewallregeln verursacht. Weitere Informationen zu Firewall-Regeln für Teams und Skype für Business Online finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips).

> [!Important]
> Bei Verwendung einer [gültigen Erstellen von Datei](#building-mapping) hochgeladen wird dringend empfohlen, sodass Sie schnell innerhalb von externen Datenströme unterscheiden können bei der Suche unter Verwendung von TCP.

> [!Note]
> Audio-, Video- und VBSS bevorzugen UDP als ihren primären Transport. Die Vorversion Arbeitslast RDP-Anwendungsfreigabe verwendet nur TCP.

#### <a name="tcp-usage"></a>TCP-Verwendung

TCP-Berichte gibt die TCP-Gesamtverwendung in den letzten sieben Monaten an. Alle weiteren Berichte in diesem Abschnitt Schwerpunkt auf Eingrenzung bestimmte Gebäude und Subnetzen, wo TCP am häufigsten verwendet wird. Separate Berichte stehen für Konferenzen und zwei Datenströme.

![Diagramm mit den Prozentsatz der Audiostreams, die TCP verwenden](media/qerguide-image-audiostreamswithtcp.png)
_Abbildung 23 – Audiostreams mit TCP-Verwendung_


##### <a name="investigation"></a>Untersuchung

Mit diesem Bericht können Sie die folgenden Fragen beantworten:

-   Was ist das Gesamtvolumen des TCP-Datenströme für den aktuellen Monat?
-   Handelt es sich verschlechtert oder besser als den vorherigen Monat?
-   Ist die TCP-nutzungstrend erhöhen, steady, oder verringern?
-   Ist der TCP PSR meine allgemeine a. identisch?

Dauern Sie Wenn Sie feststellen, dass die TCP-nutzungstrend zunimmt oder über normale monatlichen Nutzung der mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Remediation untersuchen. Idealerweise sollten Sie so wenig TCP-basierte audiositzungen wie möglich im verwalteten Netzwerk.

#### <a name="tcp-vs-udp"></a>TCP und UDP

In diesem Bericht werden die Lautstärke von TCP und UDP Verwendungsberichten auf den aktuellen Monat für Audio-, Video- und videobasierte Bildschirmfreigabe (VBSS) identifiziert. 

![Bericht mit der Lautstärke des Streams, die TCP und UDP verwenden](media/qerguide-image-tcpvsudp.png)

_Abbildung 24 – TCP und UDP - Konferenzen_

##### <a name="analysis"></a>Analyse

Obwohl Sie TCP-Nutzung so gering wie möglich sein soll, wird möglicherweise ein Bit der TCP-Verwendung in einer Bereitstellung andernfalls fehlerfrei angezeigt. Obwohl es immer einige wenige TCP Auslastung könnten, als für Audio-, Video- und VBSS möglichst wenig TCP-Verwendung finden Sie unter werden soll.

Auch in den Bericht einbezogen ist die schlechter Stream Rate. Dies bietet Ihnen eine Ansicht in dem Vergleich zwischen zwei UDP und TCP zum Visualisieren wie TCP Usage allgemeine Qualität auswirkt.

#### <a name="tcp-investigations"></a>TCP Untersuchungen

Navigieren Sie in den bereitgestellten CQD Vorlagen zu der TCP-Datenströme von Berichten erstellen und Subnetz mithilfe der verwalteten Netzwerken oder allen Netzwerken Vorlage. Zum Untersuchen der TCP, ist der Prozess, gleich, damit wir die Diskussion auf Konferenzen näher erläutert wird.

> [!IMPORTANT]
> Ein gültiger [Erstellen Sie die Datei](#building-mapping) hochgeladen haben, wird empfohlen, sodass Sie schnell innerhalb von externen Datenströme unterscheiden können bei der Suche unter Verwendung von TCP. 

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.                                  |

![TCP-Nutzung durch Erstellen und Subnetz](media/qerguide-image-tcpstreams.png)

_Abbildung 25 – TCP-Datenströme durch die Erstellung- und Subnetz Konferenzen_

##### <a name="remediation"></a>Wartung

In diesem Bericht identifiziert bestimmte Gebäude und Subnetze abgerufen, die dem Volumen der Verwendung von TCP beitragen. Ein Bericht zusätzlicher ist ebenfalls enthalten, um die IP-Adresse des Microsoft-Relay zu identifizieren, die in den Anruf verwendet wurde, um zu isolieren fehlenden Firewallregeln. Konzentrieren Sie Ihre Remediation auf diese Gebäude, die dem höchsten zu erwartenden TCP Datenströme maximieren Auswirkungen haben.

Die häufigste Ursache für die Verwendung von TCP fehlt Ausnahmeregeln in Firewalls oder Proxyserver. Wir sprechen Proxys im nächsten Abschnitt, also für jetzt Ihrer Arbeit Schwerpunkte auf die Firewalls. Über das Erstellen von oder Subnetz bereitgestellt, können Sie bestimmen, welche Firewall aktualisiert werden muss.


_Tabelle 10 - Remediation * Richtlinien für die TCP-Datenströme durch Erstellen und Subnetz_

| Wartung        | Anleitung     |
|--------------------|--------------------------------------|
| Konfigurieren der firewall | Stellen Sie sicher, dass [Office 365 IP-Ports und Adressen](https://aka.ms/o365ips) aus Ihrer Firewall ausgeschlossen werden. Media-bezogene TCP Probleme konzentrieren Sie Ihrer anfänglichen auf Folgendes:<ul><li>Stellen Sie sicher, dass der Client Media Subnetze 13.107.64.0/18 und 52.112.0.0/14 in die Firewall-Regeln sind.</li><li>UDP-Ports 3478 – 3481 sind die erforderlichen medienports und geöffnet werden müssen, andernfalls der Client wieder auf TCP-Port 443 fehl.</li></ul> |
| Vergewissern Sie sich             | Verwenden Sie das [Tool zur Bewertung der Microsoft Network](https://www.microsoft.com/download/details.aspx?id=53885) auf Probleme mit der Konnektivität mit bestimmten Office 365-IP-Adressen und Ports aus dem betroffenen Gebäude oder Subnetz.    |

### <a name="http-proxy"></a>HTTP-proxy

HTTP-Proxys sind die Bevorzugter Pfad für die Herstellung von mediensitzungen für eine Vielzahl von Gründen nicht. Viele Tiefe Paket Prüfung Features enthalten, die verhindern, dass Verbindungen mit dem Dienst abgeschlossen und Systemausfallzeit einführen können. Darüber hinaus erzwingen fast alle Proxys TCP im Gegensatz zu zulassen UDP, die für eine optimale Audioqualität empfohlen wird.

Es wird immer empfohlen, dass Sie den Client für die Verbindung direkt Teams und Skype für BusinessServices konfigurieren. Dies ist besonders wichtig für basierenden Media-Datenverkehr.


> [!IMPORTANT]
> Ein gültiger [Erstellen Sie die Datei](#building-mapping) hochgeladen haben erleichtert es ordnungsgemäß innerhalb von externen Audiostreams zu unterscheiden beim Proxy Analyse. 


#### <a name="http-proxy-usage"></a>HTTP-Proxy-Verwendung

Der HTTP-Proxy Stream-Bericht in diesem Abschnitt der Vorlage ähnelt der TCP-Berichte. Es überprüfen nicht, ob Anrufe schlechter oder eine gute sind, aber gibt an, ob die Verbindung über HTTP hergestellt wurde.

![Bericht der Audiostreams, die Verwendung von HTTP](media/qerguide-image-audiostreamswithhttp.png)

_In Abbildung 26 – Audiostreams mit HTTP-Proxy-Verwendung_

##### <a name="analysis"></a>Analyse

Als möglichst wenig HTTP-Mediendatenströme angezeigt werden soll. Wenn Sie Datenströme Proxy durchlaufen haben, wenden Sie sich an Netzwerke Team um sicherzustellen, dass die erforderlichen Ausnahmen vorhanden sind, damit Clients direkt Teams oder Skype für Business Online Media Subnetze weiterleiten.

Wenn Sie nur eine Internet-Proxy in Ihrer Organisation haben, überprüfen Sie die ordnungsgemäße [Office 365-URLs und IP-Adresse Bereich Ausschlüsse](https://aka.ms/o365ips). Wenn mehr als eine Internet-Proxy in Ihrer Organisation konfigurierten wird die HTTP verwenden Unterseite isolieren, welche Erstellen von Berichten oder Subnetz beeinflusst werden.

Für Organisationen, die den Proxy umgehen können nicht sicherstellen, dass die Skype für Business-Client konfiguriert ist, um sich anzumelden sollten ordnungsgemäß, wenn sie einen Proxyserver befindet, wie im Artikel [beschrieben Skype für Unternehmen Proxyserver verwenden, um anstatt direkt anmelden Verbindung](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>HTTP-Proxy Untersuchungen

In diesem Bericht identifiziert bestimmte Gebäude und Subnetze abgerufen, die zur Verwendung von HTTP-beitragen.

> [!IMPORTANT]
> Ein gültiger [Erstellen Sie die Datei](#building-mapping) hochgeladen haben erleichtert es ordnungsgemäß innerhalb von externen Audiostreams zu unterscheiden beim Proxy Analyse.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.

![Bericht über HTTP-Proxy-Nutzung durch die Erstellung und Subnetz](media/qerguide-image-httpproxyusage.png)

_Abbildung 27 – HTTP-Proxy-Nutzung durch die Erstellung und Subnetz_

##### <a name="remediation"></a>Wartung

Es [wird empfohlen](/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) , dass Sie immer Proxys für Skype für Unternehmen und Teams, insbesondere Mediendatenverkehr umgehen. Proxys sicherer nicht Skype für Unternehmen, da seine Datenverkehr bereits verschlüsselt ist. Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen. Probleme wie diese führt eine negative Erfahrung mit Audio-, Video- und Bildschirmfreigabe, wobei in Echtzeit Datenströme wichtig sind.

Die häufigste Ursache für HTTP-Verwendung fehlt Ausnahmeregeln in Proxys. Umgehen Sie mithilfe der Gebäude oder Subnetz, sofern Sie schnell ermitteln können, welche Proxy für Medien konfiguriert werden muss.

Stellen Sie sicher, dass die erforderlichen [Office 365 FQDNs](https://aka.ms/o365ips) sind White im Proxy.

Weitere Informationen zum Verwenden von Proxys mit Skype für Business Online und Teams finden Sie unter [in diesem Artikel](/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online).

## <a name="clients-and-devices"></a>Clients und Geräten

In diesem Abschnitt konzentriert sich auf die Aufgaben für die Berichte zur Clientversionen und die Verwendung von zertifizierte Geräte. Berichte sind zur Verwendung für Clientversionen, Clienttyp, Capture Geräte und Treiber (Mikrofon), Videoaufnahmegeräte und Lieferanten und der Treiberversion Wi-Fi-Versionen Gliederung verfügbar.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte enthalten in den Vorlagen enthalten; die Methoden des Untersuchung nachfolgend erläuterten gelten jedoch weiterhin. Verweisen Sie auf die einzelnen Beschreibung Weitere Informationen.

### <a name="client-versions"></a>Client-Versionen

Die Berichte in diesem Bereich konzentrieren Sie sich zum Identifizieren von Skype für Business Clientversionen verwendet und ihren relativen Lautstärke in der Umgebung.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt sind, und durch die Azure Content Delivery Network automatisch aktualisiert, und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.

> [!Important]
> Es sei denn, Sie federated Teilnehmer Daten ausschließen, werden dieser Berichte Client Telemetrie von Verbund-Endpunkten enthalten. Um Verbund Endpunkte auszuschließen, müssen Sie einen [Abfragefilter](#query-filters) für zweiten Mandanten-ID auf Ihrer Organisation [Mandanten-ID](#tenant-id)hinzufügen. Alternativ können Sie einen [URL-Filter](#url-filter) federated Teilnehmer Telemetrie ausgeschlossen.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.

![Bericht-Clients und-Geräten](media/qerguide-image-clientversionreport.png)

_Abbildung 28 - Client-Version-Bericht_

#### <a name="remediation"></a>Wartung

Ein wichtiger Aspekt gesteuerter hochwertigen benutzerumgebungen müssen Sie sicherstellen, dass verwaltete Clients auf dem neuesten Stand Versionen von Skype für Unternehmen, die ausgeführt werden, zusätzlich zur Sicherstellung, dass die unterstützenden Treiber auf dem aktuellen Stand sind. Dies bietet verschiedene Vorteile, dazu zählen: 

-   Es ist einfacher, einige Versionen im Vergleich zu viele Versionen zu verwalten.
-   Es bietet eine einheitliche Erfahrung.
-   Es erleichtert die Problembehandlung bei Anrufqualität und Verwendbarkeit.
-   Microsoft stellt allgemeine Verbesserungen und Optimierungen ständig über das Produkt. Sicherstellen, dass Benutzer diese Updates erhalten, die ihre Risiken der Ausführung in ein Problem, das bereits behoben ist.

Einschränken des Ihre Bereitstellung Clientversionen, die weniger als sechs Monaten sind wird die gesamten Benutzeroberfläche verbessert und Verbesserung der Verwaltbarkeit im Vergleich zu großen Anzahl von verschiedenen Versionen des Clients in der gleichen Umgebung müssen.

Wenn Sie nur Office Klick-und-Los verwenden, werden Sie automatisch binnen sechs Monaten sein. Es ist keine weitere Aktion erforderlich.

Wenn Sie eine Kombination von Klick-und-Los und Installer-Pakete (MSI) verfügen, können Sie den Bericht verwenden, um sicherzustellen, dass die MSI-Clients regelmäßig aktualisiert werden. Wenn Sie, dass Clients feststellen hinter sinkt, arbeiten mit dem Team verantwortlich für die Verwaltung von Office-Updates, und stellen Sie sicher, dass sie genehmigen und Bereitstellen von Client-Patches regelmäßig sind.

Es ist außerdem wichtig, zu berücksichtigen und stellen Sie sicher, dass die USB- und Audiotreiber sowie gepatcht werden. Es werden einfach nicht verändert werden diese Treiber und nicht in Ihrer Strategie Patch Management einbinden.

Versionsnummern für Skype für Unternehmen finden Sie über die folgenden Links:

-   [Freigeben von Informationen nach Updates für Office ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Updateverlauf für Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Skype für Business-Downloads und-Updates](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Geräte

So tätigen des geräteberichts Mikrofon verwenden, müssen wir das Konzept der Mittelwert Opinion Score verstanden haben (MOS). MOS ist die Messung Gold-Standard: die wahrgenommene Audioqualität zu ermitteln. Es wird als eine Bewertung ganze Zahl im Bereich von 0 bis 5 dargestellt.

Die Grundlage für alle Maßnahmen der Sprachqualität ist wie eine Person für die Qualität der Speech Verbindungsmodus. Da es von human Wahrnehmung betroffen ist, ist es grundsätzlich subjektive. Es gibt mehrere verschiedene Methoden subjektive testen. Die meisten VoIP Qualität Measures basieren auf einer absoluten Kategorisierung Bewertungsskala (ACR).

Ein ACR subjektive Test bewerten in eine statistisch signifikante Anzahl von Personen ihre Qualität auf einer Skala von 1 (schlecht) auf 5 (hervorragend). Der Mittelwert der Ergebnisse ist die MOS. Die resultierende MOS hängt von den Bereich der Erfahrungen, die die Gruppe und den Typ des Erfahrung bewertet wird verfügbar gemacht wurden.

Da es nicht sinnvoll, um für ein Kommunikationssystem live subjektive Tests der Sprachqualität auszuführen ist, Microsoft-Teams und Skype für Unternehmen mithilfe von erweiterten Algorithmen objektive eine subjektive Testergebnisse vorhergesagt MOS Werte generieren.

Der verfügbare Satz mit MOS und Metrik bieten eine Ansicht die Qualität der Erfahrung von einem Audiogerät an die Benutzer übermittelt werden. 

Durch Bereitstellen von Benutzern mit Geräten zertifiziert für Teams und Skype für Unternehmen, verringern Sie die Wahrscheinlichkeit solch negative Erfahrungen aufgrund des Geräts selbst (die wahrscheinlicher, beispielsweise mit integrierten Laptop-Lautsprecher und Mikrofon ist). Weitere Informationen finden Sie in diesen Artikeln auf das [Zertifizierungsprogramm](/SkypeForBusiness/certification/overview) und den [Lösungskatalog für Partner](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Gerät Berichte dienen zum Bewerten der Device-Auslastung von Volume und MOS (nur Audio), und in den zugehörigen Vorlagen unter Clients und Geräte gefunden werden können. 

> [!IMPORTANT]
> Es sei denn, Sie federated Teilnehmer Daten ausschließen, werden dieser Berichte Client Telemetrie von Verbund-Endpunkten enthalten. Um Verbund Endpunkte auszuschließen, müssen Sie einen Abfragefilter für **Zweiten Mandanten-ID** in Ihrer Organisation [Mandanten-ID](#tenant-id)festlegen hinzufügen. Alternativ können Sie einen [URL-Filter](#url-filter) federated Teilnehmer Telemetrie ausgeschlossen.

> [!NOTE] 
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.

> [!Note]
> Sie möglicherweise feststellen, wenn mehrere Male gemeldet, dass Sie dasselbe Gerät finden Sie unter Bericht anzeigen. Dies liegt daran, die das Gerät gemeldet wird an CQD gemeldet werden. Unterschiede in der Hardware und Betriebssystem-Gebietsschema verursachen Unterschiede bei Gerätedaten wie gemeldet werden.

![Bericht Geräte (Mikrofon)](media/qerguide-image-devicesmicrophone.png)

_Abbildung 29 - Geräte (Mikrofon)_

##### <a name="remediation"></a>Wartung

In der Regel müssen Sie ermitteln und Auslaufen nicht zertifizierte Geräte und zertifizierte Geräte ersetzen. Einige Aspekte beim Überprüfen der Gerät Berichte umfassen:

-   Werden die Geräte zertifiziert für Teams und Skype für Unternehmen verwendet? 
-   Sie können Benutzer über [Analytics rufen Sie](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)ein bestimmtes Gerät identifizieren. Überprüfen Sie, um sicherzustellen, über die neuesten Gerätetreiber verfügen und, dass ihr Gerät über ein USB-Hub oder Dockingstation verbunden ist. 
-   Wie viele verschiedene Versionen von verschiedenen Faktoren verwendet werden? Sind sie regelmäßig gepatcht? Sicherstellen, dass Audio-, Video- und Wi-Fi-Treiber regelmäßig gepatcht werden hilft Ihnen, diese als Quelle für die Qualitätsprobleme zu vermeiden und erleichtern den Benutzer besser vorhersehbare und konsistent.

##### <a name="audio"></a>Audio

Die nächste Aufgabe ist die Gesamtauslastung des [certified Audiogeräte](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)zu bestimmen. Es wird empfohlen, mindestens 80 Prozent der alle Audiostreams ein zertifizierten Audiogerät verwenden. Dies geschieht am besten durch Exportieren der Mikrofon Geräte-Berichts in Excel die Verwendung von zertifizierten oder genehmigten Geräten berechnet. Organisationen lassen in der Regel eine Liste mit allen genehmigten Geräten, damit filtern und Sortieren von Daten einfach sein sollte.

##### <a name="video"></a>Video

Grafiktreiber sind wichtig, ebenfalls aktualisierte zu halten. Sicherstellen, dass regelmäßig Grafikkarten gepatcht werden helfen Grafiktreiber als Quelle von schlechter Qualität bei Videostreams ausschließen. Mit [certified Videogeräte](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) können Sie ein reibungsloses und qualitativ hochwertige Benutzererlebnis sicherstellen. Videogeräte, die systemeigene h. 264-Codierung unterstützen, werden bevorzugt CPU-Auslastung bei Videokonferenzen zu reduzieren.

##### <a name="wi-fi"></a>Wi-Fi

Wi-Fi-Treiber auch auf einer regulären Trittfrequenz sowie gepatcht werden müssen und Ihre Strategie für Patch Management einbezogen werden soll. Durch aktuelle Wi-Fi-Treiber verwalten, können viele Qualitätsprobleme korrigiert werden. Weitere Informationen zum Optimieren der Wi-Fi-Infrastruktur finden Sie unter [in diesem Artikel zur Planung der Wi-Fi](/skypeforbusiness/certification/networking-wifi).

## <a name="appendix"></a>Anhang 

### <a name="planning-for-wi-fi"></a>Planen von Wi-Fi

Microsoft Methode zum Laufwerk Qualität und Flexibilität in der Drahtlosnetzwerke stammen aus drei Teilen: Ende zum Planen, bewährte Methoden in der Bereitstellung, und proaktive Wartung und Betrieb. Diese Lösungsübersicht führt Sie durch diesen Vorgang, um sicherzustellen, dass ein Enterprise-Klasse drahtlosen Skype Business wünschen: [sicherstellen, dass die drahtlosen Skype ein Unternehmen für Business auftreten](https://www.microsoft.com/download/details.aspx?id=47257)

### <a name="lync-networking-guide"></a>Lync-Netzwerke (engl.)

Für weitere Hintergrund auf der Teams und Skype für Netzwerke Business-Konzepte und Gründe für die Qualität ihrer Wichtigkeit ist der [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) gelten auch weiterhin.

### <a name="network-performance-requirements"></a>Netzwerkanforderungen für die Leistung

Die Qualität von Real-Time-Medien (Audio, Video und Anwendungsfreigabe) Implementation wird durch die Qualität der End-to-End-Netzwerkkonnektivität erheblich beeinträchtigt. Für eine optimale Teams oder Skype für Business Medienqualität muss Ihr Netzwerk die folgenden Leistungsmetriken Netzwerk erfüllen.

_In Tabelle 11 - Netzwerk leistungsanforderungen_

| Metrik                            | Client zu Microsoft Edge           | Kundenedge zu Microsoft Edge    |
|-----------------------------------|------------------------------------|------------------------------------|
| Latenz (ein Weg)                 | \<50 ms                            | \<30 ms                            |
| Wartezeit (Zeit oder Roundtripzeit) | \<100 ms                           | \<60 ms                            |
| Burstverlust von Paketen                 | \<10 % Intervall 200 ms   | \<1 % Intervall 200 ms    |
| Paketverlust                       | \<1 % Intervall 15 s    | \<0,1 % Intervall 15 s  |
| Jitter zwischen der Ankunftszeit von Paketen       | \<während ein Intervall von 15 s 30 ms | \<15 ms Intervall 15 s |
| Neuanordnung von Paketen                    | \<0,05 % außerhalb der Reihenfolge Pakete       | \<0,01 % außerhalb der Reihenfolge Pakete      |

Weitere Informationen finden Sie unter [in diesem Artikel zur Leistung von Medien Qualität und Netzwerk](https://aka.ms/performancerequirements) für Teams und Skype für Business Online.

### <a name="other-resources"></a>Weitere Ressourcen

#### <a name="building-data-file"></a>Erstellen von-Datendatei

-   [Einschalten und Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)

#### <a name="cqd-training"></a>CQD-Schulung

-   <https://aka.ms/sof-cqd>

-   Workshop und Handbuch [Erste Schritte mit CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment)

-   [Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](https://aka.ms/cqd-dm)

### <a name="call-analytics-training"></a>Rufen Sie Analytics-Schulung

-   [Einführung in Anruf Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Einrichten von Anrufen Analytics](/SkypeForBusiness/using-call-quality-in-your-organization/set-up-call-analytics)

-   [Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

-   [Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)

### <a name="call-analytics-support"></a>Wenden Sie Analytics

-   Community: [Skype für Business Preview-Programm](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Wenn Sie Unterstützung erhalten möchten, melden Sie sich unsere Preview Portal [www.skypepreview.com](http://www.skypepreview.com), wählen Sie **Bericht ein Problem**und verwenden Sie die Option **Erstellen eines neuen Fehler** Berichten eines Problems. Beachten Sie, dass Supporttechniker unterstützen von Montag zwischen 6 Uhr und 9 Uhr Eastern Zeit (USA) zur Verfügung stehen. Anfragen außerhalb Stunden, werden der folgende Tag selektierender.

### <a name="devices"></a>Geräte

-   [Skype für Business Solutions Catalog Peripheriegeräte & PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Mandanten reporting

-   [Office 365 Annahme Inhaltspaket](https://www.microsoft.com/microsoft-365/blog/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Verwendungsanalyse für Microsoft 365](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)

-   [Skype for Business Online-Berichterstellung](/SkypeForBusiness/skype-for-business-online-reporting/skype-for-business-online-reporting)

-   [Microsoft-Teams, reporting](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
