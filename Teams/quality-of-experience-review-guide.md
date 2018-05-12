---
title: Quality of Experience überprüfen Handbuch für Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Handbuch für die Analyse der Leistung für Microsoft-Teams, Real-Time Media mithilfe von Anrufen Quality Dashboard (CQD).
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e6ee8ac7201aad39e6dd3af8887854f080f8a60
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
---
# <a name="quality-of-experience-review-guide"></a>Quality of Experience überprüfen Guide

In diesem Handbuch wird über das Laufwerk Wert Phase für Microsoft-Teams und Skype für Business Online. Sie können dieses Handbuchs [eine Word-Version herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) .

## <a name="introduction"></a>Einführung

Um am stärksten zur Verbesserung der benutzerfreundlichkeit haben, müssen Unternehmen wichtige Bereiche durchsetzen, die in der folgenden Abbildung dargestellt sind.
Weitere Bereiche umfassen, Betriebsaufgaben identifiziert, Zielvorgaben für Qualitätsmetriken, die Metriken zu verwenden, um Erfolg einzuschätzen Punkte und Bereiche der Untersuchung einschränken, je nach Bedarf.

![Wichtige Bereiche für die Qualität des Benutzererlebnisses enthalten, Audio, Zuverlässigkeit, den benutzerumfragen, Geräte und Clients.](media/quality-of-experience-review-guide-image1.png)

_Abbildung 1: Schlüssel betriebliche behandelten im gesamten Dokument_

Ständig bewerten und Korrigieren von den in diesem Dokument beschriebenen Gebieten, können Sie ihre Potenzial, die sich negativ auf die Qualität Ihrer Benutzer-Erfahrung auswirken reduziert. Die meisten Benutzer-Erlebnis Probleme in einer Bereitstellung können in die folgenden Kategorien unterteilt werden:

-   Unvollständige Firewall oder der Proxyserver-Konfiguration

-   Schlechte Wi-Fi-Abdeckung

-   Unzureichende Bandbreite

-   VPN

-   Inkonsistente oder veraltete Clientversionen

-   Nicht optimierte oder integrierte Audiogeräte

-   Problematisch Subnetze oder Netzwerkgeräte

Durch sorgfältige Planung und Entwurf vor der Bereitstellung von Teams oder Skype für Business Online können Sie Aufwand reduzieren, die erforderlich sind, um qualitativ hochwertige guter maintain.

Dieses Handbuch konzentriert sich auf Online aufrufen Quality Dashboard (CQD) als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche mit besonders auf die Annahme und Auswirkungen auf die Maximieren-Audio verwenden. Versucht, das Netzwerk zur Verbesserung der Audioqualität Verbesserungen übersetzt auch direkt in Verbesserungen bei video sowie die Desktopfreigabe.

Um die Bewertung zu beschleunigen, werden zwei curated CQD-Vorlagen zur Verfügung gestellt: eine für alle Netzwerke und der andere verwalten für gefiltert wird verwaltet wird nur Netzwerke (intern). Obwohl der Berichte alle Netzwerke Vorlage zum Erstellen von und Netzwerkinformationen anzeigen konfiguriert sind, kann es bei der Arbeit zu sammeln und Hochladen von Informationen zum Erstellen von dennoch verwendet. Erstellen von Informationen in CQD hochladen ermöglicht dem Dienst durch Hinzufügen von benutzerdefinierten erstellen, Netzwerk und Speicherort Informationen beim Unterscheidung von externen Subnetzen interne reporting optimiert. Weitere Informationen finden Sie unter [Erstellen von Zuordnung](#building-mapping) weiter unten in diesem Dokument.

### <a name="what-is-the-cqd"></a>Was ist die CQD?

Sie verwenden rufen Quality Dashboard (CQD) Einblick in die Qualität der Anrufe mithilfe von Teams und Skype für BusinessServices. CQD soll helfen, Skype für Geschäfts- und Teams-Admins und Netzwerktechniker Optimieren des Netzwerks. CQD untersucht aggregierte Informationen für eine ganze Organisation, auf dem gesamten Muster offensichtlich, werden können Mitarbeiter informiert Bewertung der Anrufqualität zu ermöglichen. CQD bietet Berichte der Anruf-Metriken, die Ihnen Einblick in die allgemeine Anrufqualität, Anruf Zuverlässigkeit und benutzerfreundlichkeit bieten.

> [!NOTE]
> CQD enthalten keine personenbezogene Informationen (PII). PII sind Informationen, die verwendet werden kann allein oder mit anderen Informationen bezeichnen, wenden Sie sich an, oder suchen eine einzelne Person oder um eine einzelne Person im Kontext zu identifizieren. 

### <a name="intended-audience"></a>Zielgruppe

Dieses Dokument ist für die direkte Verwendung von Partnern und Kunden Beteiligten mit Rollen wie leitender/Architekt für die Zusammenarbeit, Berater, Change Management/Annahme Specialist, Unterstützung/Help Desk führen, Netzwerk führen, Desktops führen und IT-Administrator verwendet werden

Dieses Dokument ist auch von der festgelegten Qualität Champion(s) verwendet werden soll.
Weitere Informationen finden Sie unter [der Qualität Champion-Rolle](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie bevor Sie dieses Handbuch verwenden sicher, dass Sie die richtige Mandanten [Rollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) zugewiesen, sodass Sie CQD zugreifen können.

-   **Globalen Administratorrolle von Office 365:** Greift auf alle administrativen Funktionen in Office 365-Suite von Diensten in Ihrem Plan, einschließlich Skype für Unternehmen.

-   **Skype für Business Administratorrolle:** Skype für Unternehmen für Ihre Organisation konfiguriert, und ist berechtigt, die [Berichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Office 365 Administrationscenter anzeigen. Diese Rolle ist erforderlich, auch wenn Sie nur Teams bereitstellen.

Alternativ können Sie ein Office 365-Benutzerkonto den Zugriff auf Berichtsfunktionen nur folgende Rolle zuweisen.

-   **Leser von Berichten:** Können die [Berichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Office 365 Administrationscenter, alle Berichte aus dem [Office 365 Annahme Inhaltspaket](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)und CQD Berichte anzeigen.

Grundlegendes zu den grundlegenden Konzepten von CQD maximieren können die Auswirkung, die Sie bei der Verbesserung Ihrer Benutzer Erfahrung mit Teams oder Skype für Business Online vornehmen können.
Weitere Ressourcen finden Sie im [Anhang](#other-resources).

## <a name="what-is-quality"></a>Was ist die Qualität?

Im Zusammenhang mit Qualität in Teams und Skype für Unternehmen ist es wichtig, definieren Sie den Begriff, um eine allgemeine Grundlegendes zu erreichen. Qualität, ist wie hier definiert eine Kombination von Metriken und benutzerfreundlichkeit Service.

![Service-Metriken bestehen aus der Anrufe schlechter Qualität Verhältnis, Zuverlässigkeit, Endpunkte-Geräte und Client-Versionen. End User Experience Wahrnehmung der Dienstqualität des Benutzers besteht.](media/quality-of-experience-review-guide-image2.png)

_Abbildung 2: Was Qualität ist?_

### <a name="define-your-target-metrics"></a>Definieren Sie die Ziel-Metriken

In diesem Abschnitt werden die Core Service-Metriken, die wir verwenden, um bewerten, wie Dienste Health auftreten. Ständig bewerten und Entwicklung, diese Metriken unter Ziel zu halten, helfen Ihnen, sicherzustellen, dass Ihre Benutzer konsistente, zuverlässige Anrufqualität auftreten. Um Ihnen den Einstieg zu erleichtern, werden die folgenden Ziele bereitgestellt.
Lassen Sie uns kurz den Unterschied zwischen einem verwalteten und nicht verwalteten Netzwerk:

-   Eine *verwaltete* Netzwerk beeinflusst, und von der Organisation gesteuert werden kann.
    Dazu gehören das interne LAN, remote WAN und VPN.

-   Ein *nicht verwalteten* Netzwerk werden nicht beeinflusst oder von der Organisation gesteuert. Ein Beispiel für eine nicht verwaltete Netzwerk ist ein Hotel oder am Flughafen Netzwerk.

_Tabelle 1: Core Ziel Health Assessment Metriken_

|               | Qualität für verwaltete Netzwerke | Zuverlässigkeit für verwaltete Netzwerke |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Metrische name   | Trefferquote % der Audio-Anrufe schlechter Qualität      | Rufen Sie Setup mit Fehlern %            | Rufen Sie die Drop Fehler % |
| Beispiel-Ziel | \<3 %                         | \<1 %                             | \<4 %                 |

Es ist wichtig, zu besprechen und definieren die Ziele Ihrer Organisation, um Ihre Geschäftsziele zu erfüllen. Idealerweise sollten Sie diesen Zielen vor der Bereitstellung identifizieren.

#### <a name="audio-pcr-"></a>Audio PCR % 

Audio schlechter aufrufen Verhältnis (PCR) stellt allgemeine Prozentsatz an anrufen, die Audioqualität Ihres Unternehmens. Diese Metrik dient zum Hervorheben von Bereichen, in Ihrer Organisation Aufwand für die stärksten wirken sich in Richtung verringern diesen Wert und Verbessern der benutzererfahrung, weshalb verwaltete Netzwerken der Schwerpunkt sind beim Betrachten PCR konzentrieren können. Externe Benutzer zu wichtig sind, aber Untersuchungen unterscheidet sich regelmäßig Organisations- und Benutzer.
Erwägen Sie, bewährte Methoden für externe Benutzer, und externe Anrufe unabhängig von der gesamten Organisation betrachten.

#### <a name="call-setup-failures-"></a>Rufen Sie Setup mit Fehlern % 

Dies ist eine beliebige Media-Sitzung, die konnte nicht hergestellt werden. Aufgrund den Schweregrad der Auswirkungen ermittelte Benutzerinteraktion ist das Ziel dieser Wert als erreicht bald wie möglich bei Null zu reduzieren. Ein hoher Wert für diese Metrik ist in neuen Bereitstellungen mit unvollständiger Firewallregeln häufiger als eine über Erfahrungswerte zur Bereitstellung, aber es ist wichtig, die in regelmäßigen Abständen Video. Ihre betriebliche Genehmigungsverfahren Laufe der Zeit können Sie diese Metrik zum Einschließen von Video- und Desktopfreigabe Arbeitslasten erweitern.

#### <a name="call-drop-failures-"></a>Rufen Sie die Drop Fehler % 

Dies gilt für ein audio Arbeitslast, in dem die Sitzung unerwartet beendet. Ihre betriebliche Genehmigungsverfahren Laufe der Zeit können Sie diese Metrik zum Einschließen von Video- und Desktopfreigabe Arbeitslasten erweitern.

### <a name="service-metrics"></a>Service-Metriken

Dienst metrischen Ziele bestehen bestimmte clientbasierte Metriken.

#### <a name="pcr"></a>PCR

Die Grundlage für die Bestimmung, ob ein Anruf schlechter eingestuft ist, wird mithilfe des Anrufe schlechter Qualität-Verhältnis (PCR). PCR besteht aus fünf Netzwerk-Metriken, die in der folgenden Tabelle beschrieben. Für einen Anruf als schlecht klassifiziert werden muss nur eine Metrik den definierten Schwellenwert überschreitet. Weitere Informationen zum Vorgang, Anruf Klassifizierung finden Sie unter [in diesem Blogbeitrag](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tabelle 2: Service-Metriken Anrufe schlechter Qualität_

| Metrik                                           | Beschreibung                                                                                                                                                                                                                                                                                                                                                                  | Benutzererfahrung                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jitter \>30 ms                                   | Dies ist die durchschnittliche Änderung Verzögerung zwischen aufeinander folgende Pakete. Für einige Ebenen von Jitter über Pufferung können Teams und Skype für Unternehmen anpassen. Es ist nur, wenn die Jitter überschreitet die Pufferung, dass ein Teilnehmer die Effekte der Jitter bemerkt.                                                                                                                         | Die Pakete an einem anderen kumulativ dazu führen, dass ein Lautsprecher Stimme zum automatischen auszugeben.                                                                                       |
| Paketverlustrate \>10 % oder 0,1                    | Dies ist häufig als Prozentsatz der Pakete definiert, die verloren gegangen sind. Paketverlust wirkt sich direkt auf die Audioqualität – von kleinen, verloren Person Pakete, die fast keine Auswirkungen auf Back Bursts von Verlusten haben, Ursache Audio vollständig Ausschneiden.                                                                                                                               | Die Pakete werden verworfen und nicht eingehenden an das vorgesehene Ziel verursachen Lücken in den Medien, resultierende in verpassten Silben und Wörter und abgehackte video und Freigabe. |
| Roundtripzeit \>500 ms                         | Dies ist der Zeitaufwand zum Abrufen von ein IP-Paket von Punkt A nach Punkt B und an Punkt A. Diese Netzwerk Verteilung Verzögerung ist mit der physischen Abstand zwischen zwei Punkte und der Lichtgeschwindigkeit verknüpft und enthält zusätzlichen Aufwand, die von den verschiedenen Geräten im Netzwerkpfad übernommen.                                                                                  | Die Pakete braucht zu lange zum am Ziel eingehen dazu führen, dass einen Effekt Walkie-talkie.                                                                                 |
| NMOS-Beeinträchtigung Durchschnitt \> 1.0                  | Eine oder mehrere der folgenden Metriken Netzwerk zwar einzeln waren nicht schlecht, verursacht zusammen um mehr als einen Punkt der Netzwerk- [Mean Opinion Score](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS), zu löschen. Dies bedeutet nicht unbedingt die Netzwerkschnittstelle ist schlecht, aber genügend Probleme aufgetreten sind, während des Anrufs, dass Qualität reduziert wurde. | Hierbei handelt es sich um eine Kombination von Jitter Paketverlust, und – in geringerem Maße – Roundtripzeit erhöht. Der Benutzer kann eine Kombination der folgenden Symptome auftreten.          |
| Durchschnittliches Verhältnis zwischen ausgeblendeten Samples \> 7 % oder 0,07 | Eine oder mehrere der folgenden Metriken Netzwerk zwar einzeln waren nicht schlecht, verursacht dem Client selbst reparieren das Medium. Ein ausgeblendeter audio Beispiel ist ein Verfahren zur abrupten Übergang zu glätten, die in der Regel durch Initiale Netzwerkpaketen verursacht werden würde.                                                                                                                | Hohe Werte anzugeben, dass erhebliche Ebenen der Verlust zum Verbergen angewendet wurden, und ergab Audio verzerrt oder verloren.                                                  |

#### <a name="client-and-device-readiness"></a>Client- und Gerätefunktionen Bereitschaft

Benötigen Sie eine solide Client- und Gerätefunktionen Strategie um sicherzustellen, dass die Benutzer eine konsistente und positive Benutzeroberfläche zur Verfügung haben. Einige wichtige Prinzipien Laufwerk jeweiligen Strategie Readiness.

##### <a name="client-readiness"></a>Client-Bereitschaft

Eine Strategie für die sichere Client Bereitschaft wird sichergestellt, dass Ihre Benutzer die neueste Version des Clients und genießen dabei die bestmögliche Erfahrung ausgeführt werden.
Microsoft-patches routinemäßig die Skype für Business Client; sicherstellen, dass Sie es in Ihrer Umgebung Stand ist entscheidend für Ihre gesamten Erfolg.

Es wird empfohlen, dass Sie nicht in Ihrer Client-Versionen von mehr als sechs Monaten fallen hinter lassen. Wenn Sie Office Klick-und-Los verwenden, sind Sie bereits auf dem aktuellen Stand vom Dienst gespeichert wird. Verwenden Sie enthalten [Kundenbericht](#determine-client-versions)wie weiter unten in diesem Handbuch wird beschrieben, die Sie dabei unterstützen. Sie können auch die Beispielberichte Rate Meine aufrufen zu steigern Ihrer Strategie für die Client-Bereitschaft nutzen.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt sind, und durch die Azure Content Delivery Network automatisch aktualisiert, und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.


##### <a name="device-readiness"></a>Gerät Bereitschaft

Keine einer Strategie für die einzelne kann die Benutzeroberfläche, die mehr als Ihrer Strategie für die Bereitschaft Gerät auswirken. Die meisten Organisationen freuen, entfernen Sie unnötige Geräte von Benutzern (beispielsweise Telefonapparate oder anderen dedizierten Audiogeräte), und dies ist häufig als Rechtfertigung Core für den Wechsel zu Teams oder Skype für Unternehmen. Allerdings zögern gleichen Organisationen manchmal Replacement-Geräte bereitstellen, auch wenn diese Geräte kostengünstigeren wurden. Modernen Laptops und PCs, jedoch mit integrierten Mikrofon und Lautsprecher, ausgestattet sind nicht für die Business-Klasse Voice over IP (VoIP) optimiert. Dadurch wird erstellt oft eine schlechte Erfahrung für alle Teilnehmer, insbesondere dann, wenn der Lautsprecher in einer lauten Umgebung ist. Zertifizierungsprogramm für Microsoft Gerät wird sichergestellt, dass, wenn ein Benutzer einen Telefonanruf gehört mithilfe von jedem Gerät zertifiziert für Teams oder Skype für Unternehmen, eine wünschen erzeugt, die zu einem Gerät nicht zertifizierter überlegen ist.

Wir empfehlen immer Teams und Skype für Unternehmensbenutzer eine zertifizierten Kopfhörer oder Lautsprecher verwenden, wenn einen Anruf durch mithilfe eines Desktopclients teilnehmen.
Weitere Informationen zu Microsoft überprüfen zertifizierte Geräte in diesem [Artikel über das Telefone und Geräte qualifizierten](https://technet.microsoft.com/office/dn788944.aspx). Verwenden Sie den [Device Report](#devices-investigations)Unterstützung bei der Verwaltung Ihrer Geräte weiter unten in diesem Handbuch. Die Beispielberichte Rate Meine aufrufen, können auch um Ihrer Strategie für die Bereitschaft Gerät weiter zu verbessern.

### <a name="user-experience"></a>Benutzererfahrung

Analysieren die Benutzeroberfläche ist mehr Kunst als Science, da hier die Metriken gesammelt nicht immer bedeuten, es ein Problem mit dem Netzwerk oder Service ist, sondern vielmehr sie hinweisen, dass der Benutzer ein Problem wahrnimmt. Microsoft bietet einen Umfragemechanismus integrierten – bekannt als Rate Meine aufrufen (RMC) – Hilfe benutzerfreundlichkeit zu ermitteln. RMC hilft Ihnen die aus Sicht des Benutzers die folgenden Fragen beantworten:

-   Weiß ich, wie Sie die Lösung verwenden können?

-   Ist die Lösung, einfach zu verwendenden und intuitiv, und wird über die alltägliche Kommunikation führe unterstützt?

-   Kann die Lösung mich Meine erledigen?

-   Was ist meine allgemeine Wahrnehmung der Lösung?

-   Kann ich verwenden die Lösung an einer beliebigen Stelle in der Zeit, unabhängig davon, an denen ich bin?

-   Kann ich einrichten und verwalten ein Anrufs?

#### <a name="rmc"></a>RMC

RMC Teams und Skype für Unternehmen integriert und wird automatisch so konfiguriert, dass nach einem in jeder 10 Anrufe oder 10 Prozent aller Anrufe angezeigt werden. In diesem kurzen Umfrage fordert den Benutzer den Anruf bewerten und einen wenig Kontext für warum die Anrufqualität schlechter wurden möglicherweise bereitstellen. Eine Bewertung ein oder zwei schlechter gilt, eignet sich drei bis vier und fünf ist hervorragend. Obwohl es etwas eines Indikators Verzögerung beim ist, ist dies eine nützliche Metrik für Unternehmensdaten Probleme, die Service-Metriken verpassen können.

> [!NOTE]
> Bis der Benutzer aufgefordert werden, durch das Erteilen von guten Feedback zusätzlich zu schlecht, Antworten in der Regel auf RMC Umfragen reagieren zurückkehren Sie als überwältigend negativ. Die meisten Benutzer reagieren nur, wenn die Anrufqualität schlechter befindet. Aus diesem Grund können RMC Berichte auf der Seite schlechter verzerrt angezeigt werden auch dann, wenn der Dienst Metriken gute sind. 


Sie können CQD verwenden, um einen Bericht über RMC Benutzerantworten und Beispielberichte sind in der Vorlage CQD enthalten. Sie sind nicht jedoch in diesem Handbuch ausführlich erläutert. Weitere Informationen zu RMC in Skype für Business Online und Richtlinien für die Schulung von Benutzern zum Vorführen nützliche RMC Antworten finden Sie unter in diesem [Blogbeitrag](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Kategorien von Qualität

Der Erfolg der operationalizing einer hohe Qualität und zuverlässigen bereitstellungs hängt von Ihrer Erstellen von betrieblichen Genehmigungsverfahren ab. Achten Sie insbesondere, besonders auf die drei Kategorien, die in der folgenden Abbildung dargestellt; Hierbei handelt es sich um den Fokus dieses Handbuchs:

-   **Netzwerk:** Audioqualität konzentriert sich auf die PCR Metrik, TCP-Verwendung, verkabelten und drahtlosen Subnetze, und identifizieren die Verwendung von HTTP-Proxys und VPN.

-   **Endpunkte:** Audiogeräte und der Clientversion (Skype für nur Unternehmen).

-   **Dienstverwaltung:** Dieser Kategorie besteht aus zwei Abschnitten:

    -   Zunächst wird Microsofts Verantwortung zu verwalten und Verwalten von Teams und Skype für Business Online-Dienste.

    -   Zweitens sind Aufgaben, die Ihre Organisation verwalten muss, um sicherzustellen, dass zuverlässigen Zugriff auf den Dienst, beispielsweise zum Erstellen von Informationen zu aktualisieren und Verwalten von Firewalls für neue Office 365-IP-Adressen, sobald Infrastruktur mit dem Dienst hinzugefügt wird.

![Die Kategorien von Qualilty in einer Organisation: service-Management, Endpunkte und im Netzwerk.](media/quality-of-experience-review-guide-image3.png)

_Abbildung 3 – wichtige Kategorien für Teams und Skype für Business Online-Bereitstellung_

Die folgende Grafik werden die Aufgaben erläutert, die Sie für jede Kategorie ausführen müssen. Es wird empfohlen, dass Sie diese Aufgaben einmal pro Woche mindestens ausgeführt.

Der ersten dieser Aufgaben Ausführung dauert aufwändiger als nachfolgende Iterationen, da viele dieser Kategorien erfordern, dass Sie Ihre Bereitstellungskonfigurationen auf Gültigkeit überprüfen. Nachdem Sie den Status aus, indem Sie die von die Ihnen definierten Ziele meeting erreicht haben, helfen diese Aufgaben Ihnen bei diesem Zustand verwalten.

#### <a name="service-management-tasks"></a>Service-Management-Aufgaben

In einer Cloud-First-Welt müssen Sie bestimmte Verwaltungsaufgaben Service zum Verwalten von hochwertigen benutzerumgebungen ausführen. Diese Aufgaben im Bereich von sicherstellen, dass ausreichend Bandbreite, um den Dienst zu erreichen, ohne eine Internetlinks, validieren, Dienstqualität (QoS) auf alle verwalteten Netzwerks Bereiche ist und – und schließlich – [Griff Office 365 IP-Bereiche auf Firewalls](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Netzwerkaufgaben

Es gibt zwei Kategorien von Netzwerk-Tasks: Zuverlässigkeit und Qualität. Zuverlässigkeit konzentriert sich auf Messen der Fähigkeit des Benutzers tätigen erfolgreich und in Verbindung bleiben. Qualität konzentriert sich auf die aggregierten Telemetrie vom Client des Benutzers, während und nach Beendigung des Anrufs an Teams und Skype für Business Online gesendet.

Wichtige Auswirkung auf die, Zuverlässigkeit Benutzerinteraktion hat, angegeben, beginnen bewerten und Untersuchen von diese Metriken vor Qualität.

#### <a name="endpoints-tasks"></a>Endpunkte Aufgaben

Die Hauptaufgabe in dieser Kategorie ist wird überprüft, welche Clientversionen Skype für Unternehmen ausgeführt werden, auf dem desktop Builds aus den letzten sechs Monaten, um sicherzustellen, dass Benutzer die Vorteile der kontinuierlichen Optimierungen versucht, der Skype für Business desktop Client abrufen. Darüber hinaus Dies vereinfacht die allgemeinen Verwaltungsaufgaben von Client und stellt ein einheitliches Benutzererlebnis.

Der anderen wichtige Bereich ist monitoring, welche Geräte in Ihrer Bereitstellung betroffen sind und die Verwendung von zertifizierte Geräte bieten die beste benutzerumgebung gesteuerter.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt sind, und durch die Azure Content Delivery Network automatisch aktualisiert, und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.


## <a name="using-the-reports"></a>Verwenden die Berichte

In diesem Abschnitt werden die Grundlagen der Arbeit mit CQD beschrieben. Anleitung erhält für den folgenden Themen:

-   Suchen die Mandanten-ID

-   Berichten über Teams im Vergleich zu Skype für Unternehmen

-   Zuerst im Vergleich zur zweiten Klassifikationen

-   Dimensionen und Measures Filter

-   Datenströme im Vergleich zu Anrufen

-   Gut, schlecht und nicht klassifizierte Anrufe

-   Erste Schritte mit CQD

-   Bearbeiten von Berichten in CQD

-   Filtern von Berichten in CQD

Ausführlicheren Schulungen und Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="tenant-id"></a>Mandanten-ID

Einige Berichte CQD erfordern, dass Sie einen Filter für Ihre Mandanten-ID einschließen Daran CQD Daten aggregiert ist federated Teilnehmer Telemetrie enthalten.
Obwohl dies wertvolle beim Analysieren der Anrufe schlechter Qualität Metriken nachweisen kann, erfordern Client- und Gerätefunktionen Berichte das Filtern von Daten an einen bestimmten Mandanten federated Teilnehmer Telemetrie ausgeschlossen. Wenn Sie Ihre Mandanten-ID nicht kennen, können Sie eine der folgenden Methoden verwenden, sie zu finden sind.

Erforderliche Berechtigungen

-   Globalen Administratorrolle

-   Skype für Business Administratorrolle

#### <a name="azure-ad-portal"></a>Azure AD-Portal

1.  Melden Sie sich bei des Microsoft Azure-Portals an:<https://portal.azure.com>

2.  Wählen Sie **Azure Active Directory**aus.

3.  Wählen Sie unter **Manage** **Eigenschaften**aus. Die Mandanten-ID wird in das **Verzeichnis-ID** angezeigt.

#### <a name="azure-powershell"></a>Azure PowerShell

1.  [Installieren des Microsoft Azure PowerShell Service-Management-Moduls](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Öffnen Sie ein Befehlsfenster Azure PowerShell und führen Sie das folgende Skript, indem Sie bei entsprechender Aufforderung Ihre Office 365-Anmeldeinformationen eingeben:  
    **Anmeldung-AzureRmAccount**

3.  Die Mandanten-ID wird in der Ausgabe aufgeführt.

#### <a name="skype-for-business-online-admin-center"></a>Skype für Business Online Admin Center

1.  Gehe zu<https://portal.office.com>

2.  Melden Sie sich mit Ihrer Organisation Administratorkonto eines Mandanten.

3.  Wählen Sie **Skype für Unternehmen** unter **Admin Center**aus.

4.  Die Mandanten-ID wird als **Organisations-ID** auf der Seite Willkommen aufgelistet.

#### <a name="skype-for-business-online-using-powershell"></a>Skype für Business Online mithilfe von PowerShell

1.  [Verbinden mit Skype für Unternehmen Online über die PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Führen Sie den folgenden Befehl aus:  
    **.Tenantid (Get-Cstenant)**

3.  Die Mandanten-ID wird als GUID angezeigt.

### <a name="teams-vs-skype-for-business"></a>Teams im Vergleich zu Skype für Unternehmen

CQD kann Teams und Skype für Business Telemetrie melden. Möglicherweise gibt es jedoch vorkommen, dass Sie einen Bericht betrachten Teams Telemetrie getrennt von Skype für Unternehmen entwickeln möchten.

#### <a name="summary-reports"></a>Zusammenfassungsberichte

Um die Seite Zusammenfassungsberichte betrachten nur Teams oder Skype für Unternehmen zu ändern, wählen Sie das **Produktfilter** Dropdown-Menü vom oberen Rand des Bildschirms, und wählen Sie dann das gewünschte Produkt aus.

![Screenshot des Dashboards Qualität aufrufen ein Dropdown-Menü die Option zum Filtern nach Arbeitslast mit widerspiegelt.](media/quality-of-experience-review-guide-image4.png)

_Abbildung 4: Auswählen eines Filters Produkt_

#### <a name="detailed-reports"></a>Ausführliche Berichte

Fügen Sie des Filters **Teams ist** mit dem Bericht hinzu, und legen Sie es auf True oder False, um einen detaillierten Bericht zu filtern. Weitere Informationen finden Sie unter [Bearbeiten Berichte](#editing-reports) weiter unten in diesem Abschnitt.

![Screenshot des Dashboards Qualität rufen Sie mit der Dateneinheit, die einen detaillierten Bericht hinzugefügt werden kann.](media/quality-of-experience-review-guide-image5.png)

_Abbildung 5: Hinzufügen eines Microsoft-Teams Filters in einem Bericht_

### <a name="dimensions-measures-and-filters"></a>Dimensionen und Measures Filter

Eine wohlgeformte CQD Abfrage enthält alle drei der folgenden Parameter:

-   **Dimension:** Wie soll ich auf die Daten von PivotTables.

-   **Measure:** Was ich melden möchten.

-   **Filter:** Wie sollen das Dataset zu reduzieren, die, das die Abfrage zurückgibt.

Eine andere Möglichkeit, dies ist eine Dimension ist der Grouping-Funktion, ein Measure befinden sich die Daten, die, denen ich interessant, und ein Filter ist wie ich möchte die Ergebnisse auf diejenigen zu beschränken, die für eine Abfrage relevant sind.

Ein Beispiel für eine Abfrage wohlgeformt ist "meinen Status schlechter Datenströme [Measure] durch Subnetz [Dimension] für das Erstellen von 6 [Filter]."

Weitere Informationen finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm).

Dimensionen, Measures und Filter für die Berichte in den CQD Vorlagen verwendet finden Sie im [Anhang](#CQD-training).

### <a name="first-vs-second"></a>Zuerst im Vergleich zu Sekunde 

Viele der Dimensionen und Measures in CQD werden als erste oder zweite klassifiziert.
CQD nicht Anrufer/angerufenen Felder verwenden – diese Waren umbenannte _ersten_ und _zweiten_ , da sind dazwischenliegende Schritte zwischen dem Anrufer und des angerufenen. Die folgende Logik legt fest, welcher am Datenstrom oder Anruf beteiligte Endpunkt als erster Endpunkt bezeichnet wird:

-   Zuerst wird immer Endpunkt eines Servers (Konferenzserver, Vermittlungsserver usw.), wenn ein Server in der Stream oder Anruf beteiligt ist.

-   Zweitens werden immer ein Clientendpunkt, wenn der Stream zwischen zwei Serverendpunkten ist.

-   Wenn beide Endpunkte den gleichen Typ, sind die Wahl, der zwischen dem ersten ist basiert auf internen Reihenfolge der Benutzer-Agent Kategorie. Damit wird eine konsistente Anordnung sichergestellt.

Weitere Informationen zum Bestimmen des ersten oder zweiten Endpunkts, wenn sie beide identisch sind finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream im Vergleich zu Anrufen

Sie verstehen des Unterschieds zwischen eines Anrufs und einem Stream ordnungsgemäß auswählen, welche Dimensionen oder Measures, die Sie in CQD angezeigt werden sollen.

**Stream:** Ein Datenstrom zwischen nur zwei Endpunkte vorhanden ist. Es ist nur ein Stream-Objekt für jede Richtung und zwei Datenströme sind erforderlich für die Kommunikation. Datenströme eignen sich für die Analyse der Gebäude oder Netzwerke. In einigen Fällen werden Anruf und Stream in den Namen (beispielsweise Anruf Setup Stream oder Anruf verworfen Stream) verwendet.
Diese werden weiterhin als einzelne Datenströme klassifiziert.

**Aufrufen:** Ein Anruf ist eine Gruppierung aller Streams aus allen Teilnehmern. Umfasst ein Anruf – mindestens – zwei Datenströme. Ein einzigen Aufruf müssen zwei Teilnehmern mit mindestens einem Stream-Objekts. Anrufe eignen sich für die Analyse der Trends über einen Zeitraum.

Weitere Anleitungen gibt an, ob die Dimension oder Measure eines Anrufs oder eines Stream-Objekts verweist finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Gut, schlecht und nicht klassifizierte Anrufe

Ein Aufruf ist entweder als gut, schlecht oder nicht klassifizierte kategorisiert. Betrachten wir kurz jeweils ausführlich behandelt.

**Gut oder schlecht:** Gespräch gut oder schlecht besteht aus einem Anruf, der einen kompletten Satz von Kriterien Service, enthält, für die ein vollständiger QoE-Bericht generiert wurde.
Bestimmen, ob ein Anruf gut oder schlecht ist wird beschrieben [Weiter oben in diesem Handbuch](#pcr).

**Nicht klassifizierte:** Ein nicht klassifizierter Anruf enthalten keine umfassende Auswahl an Service Metriken. Dies sind häufig kurze Anrufe – normalerweise weniger als 60 Sekunden – wobei Durchschnittswerte konnte nicht berechnet werden und ein QoE-Bericht wurde nicht generiert.

### <a name="access-cqd-online"></a>Access CQD Online

Sie können auf zwei Arten CQD zugreifen.

-   Wechseln Sie zu <https://cqd.lync.com>.

-   Wechseln Sie zu **Skype für Business Administrationscenter** \> **Extras**, und wählen Sie den Link zur CQD, wie unten dargestellt.

![Screenshot, der zeigt "Tools" in den linken Navigationsbereich und den Link zu "Skype für Business Online aufrufen Qualitätsdashboard" ausgewählt ausgewählt.](media/quality-of-experience-review-guide-image6.png)

_Abbildung 6 – zugreifen auf CQD über die Skype für Business Administrationscenter_

### <a name="getting-started"></a>Erste Schritte

Wenn Sie zuerst CQD durchsuchen, sehen Sie auf der Seite Zusammenfassung Berichte. Die meisten der Berichte in diesem Handbuch beschrieben sind benutzerdefinierte ausführliche Berichte. Erste Schritte mit der ausführliche Berichte, wählen **Zusammenfassung Berichte** am oberen Rand der Seite, und wählen Sie dann **Ausführliche Berichte**.

![Screenshot von der Qualitätsdashboard aufrufen Depcting der verschiedenen Arten von Berichten, die verfügbar sind.](media/quality-of-experience-review-guide-image7.png)

_Abbildung 7: Navigieren zum ausführliche Berichte_

Die ausführliche Berichte Seite in CQD sieht wie in der nachfolgenden Abbildung.

![Screenshot der Seite detaillierten Bericht in CQD und die verschiedenen Elemente, die einen Bericht bilden.](media/quality-of-experience-review-guide-image8.png)

_Abbildung 8: ausführliche Berichtsseite_

1.  Bereich "Zusammenfassung" zeigt Kontext für den Bericht ein, der auf der rechten Seite angezeigt wird.

2.  Sie können **Bearbeiten** im Bereich "Zusammenfassung" auf Bericht-Ebene-Eigenschaften (einschließlich y-Achse Höhe) festlegen auswählen.

3.  Die Breadcrumb-Leiste hilft Benutzern bei ihrer aktuellen Position in der Berichtshierarchie zu identifizieren.

4.  Berichte, die ist der untergeordneten Berichte, werden mit einer blauen Link angezeigt. Wenn Sie den Link auswählen, können Sie nach unten zu den untergeordneten Berichte anzeigen.

Zeigen Sie auf die Balkendiagramme und Trendlinien detaillierte Werte angezeigt. Zeigt der Bericht, den Fokus hat im Aktionsmenü: **Bearbeiten**, **Wenn Sie den Klon**, **Löschen**, **herunterladen**und **Berichtsstruktur exportieren**.

### <a name="editing-reports"></a>Bearbeiten von Berichten

Beim **Bearbeiten** eines Berichts im Menü Aktion auswählen, werden Sie Abfrage-Editor zu öffnen. Jeder Bericht wird durch eine Abfrage unterstützt. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Abfrage-Editor ist eine Benutzeroberfläche zur Bearbeitung diese Abfragen zusätzlich zu den Optionen für die Anzeige für den Bericht, wie in der folgenden Abbildung dargestellt.

![Screenshot der Seite detaillierten Bericht in CQD und die verschiedenen Elemente, die einen Bericht bilden, wenn der Bericht bearbeitet werden.](media/quality-of-experience-review-guide-image9.png)

_Abbildung 9: Bericht-Editors_

1.  Wählen Sie Dimensionen und Measures Filter im linken Bereich. Verweisen auf einen vorhandenen Wert zeigt eine Schaltfläche zum Schließen (**X**) Sie auswählen können, um den Wert zu entfernen.

    1.  Indem Sie die Dimension oder Measure auswählen, können Sie den Titel durch Bearbeiten im Feld **Titel** ändern. Sie können auch die Reihenfolge ändern, indem Sie die blaue nach oben oder nach unten weisenden Pfeil im oberen Bereich auswählen.

    2.  Auswählen (**+**) neben einer Überschrift Öffnet das Dialogfeld für eine neue Dimension, Measure oder Filter hinzufügen.

    3.  Geben Sie die ersten Buchstaben der Dimension, Measure oder Filter in der **Hier finden Sie eine** zum Filtern der Liste für die Suche einfacher dar.

2.  Der obere Ausschnitt zeigt Optionen zur Anpassung des Diagramms.

3.  Der Abfrage-Editor zeigt eine Vorschau des Berichts.

4.  Verwenden Sie das **Bearbeiten** am unteren Rand des Bildschirms zum Erstellen oder bearbeiten eine detaillierte Beschreibung des Berichts.

### <a name="filtering-reports"></a>Filtern von Berichten

Die bereitgestellten Vorlagen umfasst mehrere integrierte Abfragen und Filter im Bericht. In den folgenden Abschnitten wird beschrieben, die am häufigsten verwendeten Filter in allen Vorlagen verwendet.

#### <a name="cqd-filter"></a>CQD filter

Sie können die CQD Filter oder URL-Filter verwenden, um jedes Berichtsabfrage vorübergehend zu filtern. Der am häufigsten verwendete CQD Filter, den Sie verwenden ist zum Filtern von Berichten auszuschließende federated Teilnehmer Telemetrie. Es wird empfohlen, dass Sie diesen Filter Lesezeichen, damit es die Standardansicht zu. Ausschließen von föderierten Data aus CQD Berichte ist nützlich, wenn Sie sind Korrigieren von verwalteten Gebäude oder Netzwerken, in dem zusammengestellten Daten Ihres Berichts beeinflussen können.

Um einen Filter CQD in der Adressleiste des Browsers zu implementieren, fügen Sie die folgenden am Ende der URL:

/Filter/ [AllStreams]. [Zweiten Mandanten-Id] \|[IHRE MANDANTEN-ID hier]

**Beispiel:**  
https://cqd.lync.com/cqd/\#/1234567/2018-02/filter/[AllStreams]. [Zweiten Mandanten-Id] \|[TENANTID] & Mandanten = TENANTID

> [!NOTE]
> URL-Beispiel oben wird nur die visuelle Darstellung. Verwenden Sie die standardmäßige CQD Verknüpfung von <https://cqd.lync.com>.

#### <a name="query-filters"></a>Abfragefiltern

Abfragefiltern werden mithilfe des Bericht-Editors implementiert. Diese Filter werden verwendet, um die Anzahl von Datensätzen zurückgegebene CQD, daher minimieren Gesamtgröße des Berichts zu verringern. Dies ist insbesondere dann sinnvoll für nicht verwalteten Netzwerken herausfiltern.
Die unten aufgeführten Filter verwenden regulärer Ausdrücke (RegEx).

_Tabelle 3 - Abfragefilter_

| Filter               | Beschreibung          | Filter-Abfragebeispiel CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Leere Werte         | Einige Filter haben nicht die Option zum Filtern von leere Werte. Um leere Werte manuell zu filtern, verwenden Sie den Ausdruck leeren, und setzen Sie den Filter auf gleich oder ungleich, je nach Ihren Anforderungen.                                                                                                                             | Erstellen von Sekunde Name \< \> \^ \\s\*\$                       |
| Beliebte home Subnetze | Ohne eine Datei gültige Erstellen von verwalteten von nicht verwalteten Netzwerken trennen werden Heimnetzwerken in den Berichten einbezogen werden. Diese private Subnetze sind außerhalb des Bereichs des Steuerelements die und schnell aus einem Bericht ausgeschlossen werden. Beliebte home Subnetze, sind gemäß Definition in diesem Handbuch 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweite Subnetz \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Innerhalb im Vergleich zu außen   | Zum Filtern von Berichten für (inside) verwaltetem oder nicht verwaltetem (externe) verwendet. Die verwaltete CQD-Vorlage ist bereits vorkonfigurierten mit diesen filtern.                                                                                                                                                                                | Sekunde innerhalb Corp = innerhalb                               |

#### <a name="report-filters"></a>Filter im Bericht

Filter im Bericht werden durch einen Filter hinzufügen, mit dem gerenderten Bericht entweder im Bericht-Editor oder direkt mit dem Bericht implementiert. Die folgenden Berichte Filter werden in der Vorlage verwendet.

_Tabelle 4 – Filter melden_

| Filter     | Beschreibung                            | Beispiel für einen Filter CQD Bericht         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Beginnen Sie mit der Jahr zuerst, dann Monat. | 2017-10                           |
| Alphabetische | Filter für alle alphabetischen Zeichen. | [a-Z]                             |
| Numerische    | Filter für eine beliebige numerischen Zeichen.    | [0-9]                             |
| Prozentsatz | Filtert nach Prozentsatz.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importieren Sie die CQD-Vorlagen

Dieses Handbuch umfasst [zwei curated CQD Vorlagen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Diese Vorlagen die Verwendung von CQD beschleunigen und bieten Ihnen die Möglichkeit, schnell nutzen CQDs-Funktionen zu einer Beeinträchtigung der Benutzer Teams oder Skype Business wünschen. Die Vorlage alle Netzwerke optimiert gegenüber einem Gebäude entwickelt Datendatei, kann verwendet werden, während der Arbeit in Richtung sammeln und Hochladen von Erstellen von Informationen in CQD, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (. CQDX) in CQD Online**

1.  Wechseln Sie zu <https://cqd.lync.com>.

2.  Authentifizieren Sie mithilfe Ihrer Office 365-Administratoranmeldeinformationen ein.

> [!NOTE]
> Sie benötigen die Office 365 globaler Administrator Skype für Business Administrator oder Berichtleser-Rolle auf CQD zuzugreifen. 


3.  Wählen Sie im Menü **Zusammenfassung Berichte** am oberen Rand der Seite aus, und wählen Sie dann **Ausführliche Berichte**.

4.  Wählen Sie im Bereich "Zusammenfassung" **Importieren**aus. Besuchen Sie die CQDX Speicherort gespeichert, wählen Sie die Vorlage CQDX, und wählen Sie dann auf **Öffnen**.

5.  Nachdem die Vorlage hochgeladen wurde, wird ein Popup-Fenster Anzeigen der Meldung "Bericht Importvorgang war erfolgreich." Wählen Sie **OK.**

![Screenshot des ein Popup-Fenster, das dem Benutzer benachrichtigt, dass die Vorlage erfolgreich importiert wurde.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Wiederholen Sie die Schritte 4 und 5 für die zweite CQD-Vorlage.

> [!NOTE]
> Die Vorlagen CQD werden pro Benutzer importiert. Wenn weitere Benutzer den Bericht verwenden müssen, müssen sie anmelden und die Vorlagen in ihrer Instanz CQD importieren. 


## <a name="building-mapping"></a>Erstellen von Zuordnung

In einer Teams oder Skype für Business Online-Bereitstellung, sind alle Clients extern.
Die hat der Auswirkung, dass alle Clients sind standardmäßig gemeldeten als außerhalb in CQD Online, unabhängig davon, ob der Client eine interne Unternehmensnetzwerk verbunden wurde.

Wenn Sie die Anrufqualität verwenden, müssen Sie den Speicherort eines Clients kennen und, ob eine Verbindung mit einem zur Verwaltung oder ein Netzwerk hergestellt wurde Sie nicht verwalten – der Annahme, dass Sie nur Netzwerke verbessert werden können, können Sie verwalten.
Hochladen von Netzwerk- und Erstellen von Informationen zu CQD Online, können Sie CQD, um zu bestimmen, ob ein Client zu einem internen Netzwerk im Unternehmen/verwaltet oder mit einem externen/nicht verwaltete Netzwerk verbunden wurde.

### <a name="building-data-file-structure"></a>Erstellen von Daten-Dateistruktur

Das Format der Datei, die Sie hochladen muss die folgenden Anforderungen, übergeben die Überprüfung vor dem Hochladen erfüllen.

-   Die Datei muss eine TSV-Datei, was bedeutet, dass für jede Zeile jeder Spalte durch ein Tabstoppzeichen getrennt ist, oder eine CSV-Datei, in der jede Spalte durch ein Komma getrennt ist.

-   Die Datei darf nicht größer als 50 MB sein.

-   Der Inhalt der Daten Datei *Tabellenüberschriften nicht berücksichtigt*. Die erste Zeile der Datendatei muss mit anderen Worten, realen Daten, nicht Spaltenüberschriften wie "Netzwerk." sein.

-   In jeder Spalte kann der Datentyp nur eine Zeichenfolge, eine Zahl oder der boolesche Datentyp sein. Wenn der Datentyp Zahl ist, muss der Wert einen numerischen Wert; Wenn es Bool ist, muss der Wert 0 oder 1.

-   Für jede Spalte ist der Datentyp String, die Daten können leer sein (jedoch weiterhin durch eine entsprechende Trennzeichen, die ein Tabulatorzeichen oder ein Komma getrennt werden müssen). Dadurch wird dem Feld eine leere Zeichenfolge zugewiesen.

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

Supernetting, so genannte Classless Inter-Domain Routing (CIDR), können Sie anstelle der einzelnen Subnetze definieren. Eine *Supernetting* ist eine Kombination von mehrere Subnetze, die ein routing Präfix freigeben. Anstatt einen Eintrag für jedes Subnetz, können Sie die Supernetz/CIDR-Adresse verwenden. Supernetting wird unterstützt, aber es wird nicht empfohlen, dessen Verwendung.

Beispielsweise Contoso marketing erstellen die folgenden Subnetze besteht:

-   10.1.0.0/24 – Erdgeschoss

-   10.1.1.0/24 – zweiter Stock

-   10.1.2.0/24 – Dritter Stock

-   10.1.3.0/24 – vierten floor

Anstatt einen Eintrag für jedes Subnetz, können die Supernetz/CIDR-Adresse – in diesem Beispiel 10.1.0.0/22.

-   Netzwerk = 10.1.0.0

-   Netzwerk-Bereich = 22

Hier sind einige Punkte zu berücksichtigen sind vor der Implementierung von Supernetting:

-   Supernetting weniger Zeit voraus, aber es geht aber vom Umfang der Daten zu reduzieren. Nehmen wir an, dass ein Qualität Problem büroumzüge Subnetz 200.1.2.0 vorhanden ist. Wenn Sie Supernetting implementiert, werden nicht Sie wissen, wo sich das Subnetz im Gebäude befindet oder welche Art von Netzwerk (beispielsweise eine Übungseinheit) ist. Wenn Sie hatte definiert alle Subnetze für ein Gebäude und Floor Standortinformationen hochgeladen, würden Sie diese Unterscheidung finden Sie unter sein.

-   Es ist wichtig, um sicherzustellen, dass die Supernetz/CIDR-Adresse richtig ist und unerwünschte Subnetze abfangen nicht zur Verfügung.

-   Supernetting kann in einer Zuordnung erstellen von mit 8-Bit-Version auf 28-Bit-Maske verwendet werden.

-   Es ist häufig 192.168.0.0 in Daten suchen. Für viele Organisationen bedeutet dies, dass der Benutzer zu Hause ist. Für andere ist dies das IP-Adressschema für eine Zweigstelle. Wenn Ihre Organisation Büros, die diese Konfiguration verwenden verfügt, fügen Sie keine es in der Datei zum Erstellen von unverändert schwierig home und internen Netzwerken mithilfe von gemeinsamen Subnetze unterscheiden.

> [!IMPORTANT]
> Der Netzwerkbereich kann verwendet werden, um eine Supernetting darzustellen. Erstellen alle neuen Daten Dateiuploads wird für überlappenden Bereiche überprüft werden soll. Wenn Sie eine Datei zum Erstellen von zuvor hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und Hochladen erneut aus, um alle überlappt identifizieren und beheben Sie das Problem. Alle Überlappung in zuvor hochgeladenen Dateien möglicherweise falschen Zuordnungen von Subnetzen zu Gebäude in den Berichten. 


#### <a name="vpn"></a>VPN

Die Daten Quality of Experience (QoE), die Clients zu Office 365 senden – wobei stammende CQD Daten aus ist also – ein VPN-Flag enthält. Dieses Kennzeichen nutzt VPN-Anbieter reporting Windows, dass die VPN-Netzwerkadapter registriert einen RAS-Adapter ist jedoch. Nicht alle VPN-Anbieter registrieren ordnungsgemäß RAS-Adapter. Aus diesem Grund können Sie nicht die integrierte VPN-Abfragefilter verwenden können. Es gibt zwei Ansätze für die Einbindung der VPN-Subnetze im Gebäude Informationsdatei.

-   Definieren Sie einen **Netzwerkname** , indem Sie mit dem Text "VPN" in diesem Feld für VPN-Subnetze.

![Screenshot eines Berichts in der aufrufen Qualität-Dashboard, das zum Erstellen einer VPN-Subnetz definiert](media/quality-of-experience-review-guide-image10.png)

_Abbildung 10: Netzwerkname mit VPN_

-   Definieren Sie einen **Namen erstellen** , indem Sie mit dem Text "VPN" in diesem Feld für VPN-Subnetze.

![Screenshot eines Berichts im Aufrufen Qualität-Dashboard, die definiert, wie eine Definition Erstellen von erstellen, die ein VPN-Subnetz umfasst.](media/quality-of-experience-review-guide-image11.png)

_Abbildung 11: VPN verwenden Sie zum Erstellen von Namen_

> [!IMPORTANT]
> Bestimmte VPN-Implementierungen meldet nicht genau Subnetzinformationen. In diesem Fall in Ihre Berichte, empfehlen wir, wenn Sie die Datei zum Erstellen von anstelle eines Eintrags für das Subnetz ein VPN Subnetz hinzufügen fügen Sie separate Einträge für jede Adresse als ein separates 32-Bit-Netzwerk im VPN-Subnetz hinzu. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Beispielsweise müssen Sie anstelle einer Zeile für 172.16.18.0/24, 253 Zeilen, mit einer Zeile für jede Adresse aus 172.16.18.1/32 über 172.16.18.254/32, inklusive.


> [!NOTE]
> VPN-Verbindungen bekanntermaßen die Netzwerkschnittstelle unter Umständen nicht richtig wie verkabelt, wenn die zugrunde liegende Verbindung Internet ist kabellos. Beim Betrachten der Qualität über VPN-Verbindungen können nicht vorausgesetzt, dass der Verbindungstyp genau identifiziert wurde.

### <a name="uploading-building-information"></a>Informationen zum Erstellen von hochladen

Das Dashboard CQD Zusammenfassung Berichte umfasst eine Seite **Mandanten Daten hochladen** , durch Auswählen des **Mandanten Datenupload** Link-Tags in der oberen rechten Ecke (Design für das Zahnradsymbol) zugegriffen. Auf dieser Seite wird für Administratoren ihre eigenen Informationen wie die Zuordnung von IP-Adresse und geografische Informationen, zuordnen jeder drahtlosen Zugriffspunkt und die MAC-Adresse, hochladen und so weiter.

1.  Wechseln Sie zu Online CQD, indem Sie auf <https://cqd.lync.com>.

2.  Wählen Sie in der oberen rechten Ecke der Zahnradsymbol aus, und wählen Sie auf der Seite **Zusammenfassung Berichte** **Mandanten Hochladen von Daten** .

![Screenshot eines Dialogfelds im Dashboard angezeigt wird, während Daten hochgeladen werden Qualität aufrufen.](media/quality-of-experience-review-guide-image12.png)

_Abbildung 12 - Menü Mandanten Daten hochladen_

1.  Alternativ ist dies Ihre zum ersten Mal CQD besuchen, werden Sie aufgefordert, Erstellen von Daten hochzuladen. Sie können **Jetzt hochladen** , navigieren zur Seite **Mandanten Datenupload** schnell auswählen.

![Screenshot des Banner in das Aufrufen Qualität-Dashboard, das einen Benutzer das Erstellen von Datenupload benachrichtigt.](media/quality-of-experience-review-guide-image13.png)

_Abbildung 13: Erstellen von Daten hochladen banner_

1.  Wählen Sie **Durchsuchen** , um eine Datendatei auszuwählen, auf der Seite **Mandanten Hochladen von Daten** .

2.  **Startdatum** Geben Sie an, nach dem Auswählen einer Datendatei, und geben Sie optional ein Enddatum.

3.  Nach dem **Startdatum**auswählen, wählen Sie auf die Datei in die CQD hoch **Hochladen** . <br><br>Bevor Sie die Datei hochgeladen wurde, wird es überprüft. Wenn die Überprüfung fehlschlägt, wird eine Fehlermeldung angezeigt anfordern, dass Sie die Datei zu korrigieren. Die folgende Abbildung zeigt einen Fehler auftritt, wenn die Anzahl der Spalten in der Datendatei nicht korrekt ist.

![Screenshot eines Dialogfelds in das Aufrufen Qualität-Dashboard, das eine Fehlermeldung beim Importieren von Daten zum Erstellen von beschreibt.](media/quality-of-experience-review-guide-image14.png)

_Abbildung 14: Building Fehler beim Upload von Daten_

4.  Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.

> [!NOTE]
> Es kann zum Abschließen der Verarbeitung der Datei zum Erstellen von bis zu vier Stunden dauern. <br><br> Wenn Sie eine Datei zum Erstellen von bereits hochgeladen haben und müssen Subnetze hinzu, die möglicherweise entgangene oder ausgeschlossen werden, wurden die ursprüngliche Datei ändern, indem Sie die neue Subnetze hinzufügen, entfernen Sie die aktuelle Datei und wieder neu bearbeitete Datei hochladen. Es kann nur eine aktive Erstellen von CQD-Datendatei. 

### <a name="missing-subnets"></a>Fehlende Subnetze

Nach dem Erstellen von Informationen für verwaltete Netzwerke hochladen, sollte jeder verwalteten Netzwerks eine Zuordnung erstellen. Jedoch nicht immer die Groß-/Kleinschreibung; in der Regel werden einige Subnetze nicht eingehalten. In diesem Abschnitt wird das Überprüfen dieser fehlenden Netzwerke behandelt.

Wechseln Sie zur Seite **Ausführliche Berichte** in CQD Online, und navigieren Sie zu der **Fehlende Subnetz Bericht** in die CQD Vorlagen enthalten. Dies stellt alle Subnetze mit 10 oder mehr audio-Streams, die nicht im Gebäude definiert sind-Datendatei. Stellen Sie sicher, dass es keine verwalteten Netzwerke in dieser Liste sind. Wenn Subnetze nicht vorhanden sind, aktualisieren Sie die ursprünglichen Erstellen von Daten Datei und erneutes Hochladen auf CQD.

> [!IMPORTANT]
> Sie müssen Ihre Mandanten-ID als Abfragefilter für die **Zweite Mandanten-ID** für diesen Bericht Filtern des Berichts, um nur die Daten des Unternehmen Mandanten anzuzeigen hinzufügen. Andernfalls wird der Bericht federated Subnetze anzeigen.

> [!NOTE] 
> Achten Sie darauf, dass Berichtsfilter Monat-Jahr mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den Filter **Monat-Jahr** -Bericht, um den neuen Standardmonat zu speichern.                                                  |

![Bericht mit Subnetze in der Datei CQD Erstellen von nicht enthalten, die Verwendung anzeigen.](media/quality-of-experience-review-guide-image15.png)

_Abbildung 15: Erstellen von Bericht fehlt_

## <a name="reliability-investigations"></a>Zuverlässigkeit Untersuchungen

Der erste Schritt zum Verbessern der Qualität ist den Status der audiozuverlässigkeit in der gesamten Organisation bewerten. Da audiozuverlässigkeit entscheidend für eine positive Benutzeroberfläche zur Verfügung steht, starten wir mit den zwei Komponenten, die Zuverlässigkeit messen:

1.  **Aufrufen Setupfehler:** Sitzung konnte nicht hergestellt werden.

2.  **Rufen Sie die Drop-Fehler:** Sitzung wurde eingerichtet und unerwartet beendet

In diesem Abschnitt werden Methoden zum Untersuchen Sie beide Bereiche behandelt.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt. Die Beschreibung der einzelnen Berichts Weitere Informationen finden.


### <a name="call-setup"></a>Verbindungsaufbau

Priorisieren Sie korrigieren von Setup anruffehlern in diesem Bereich zuerst, da diese Fehler erhebliche negative Auswirkungen auf die Benutzeroberfläche vorhanden ist.

Zunächst die Bewertung des Prozentsatz der gesamten Anruf Setupfehler für die Organisation der Überprüfung, und klicken Sie dann priorisieren Bereiche der Untersuchung basierend auf den höchsten Prozentsatz von erstellen oder im Netzwerk.

#### <a name="call-setup-failures-overall"></a>Rufen Sie allgemeine Setupfehler

In diesem Diagrammbericht zeigt die Gesamtsumme der erfolgreichen Aufruf einrichten, und rufen Setupfehler über einen Zeitraum. Zeigen Sie auf eine der Spalten auf die einzelnen Werte, anzuzeigen, wie in der folgenden Abbildung dargestellt.

![Screenshot eines Diagramms, das zeigt, Prozentsatz der Audio aufrufen Stream Fehler bei der Installation](media/quality-of-experience-review-guide-image16.png)

_Abbildung 16 - Audiozuverlässigkeit - Anruffehlern Stream Setup_

##### <a name="analysis"></a>Analyse

In diesem Bericht werden Ihrer Organisation Audioanruf-Setup-Syntax und Fehler über einen Zeitraum angezeigt. Mithilfe dieses Berichts können Sie die folgenden Fragen beantworten und Ihre weitere Vorgehensweise bestimmen:

1.  Was ist der Prozentsatz der gesamten Anruf Setup Fehler für den aktuellen Monat?

2.  Ist insgesamt Anruf Setup Fehler Prozentsatz unter oder über die Metrik definierten Ziel?

3.  Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Ausfall Trend erhöhen, steady, oder verringern?

Die Informationen in diesem Bericht informiert die Geschichte des wie oft Ihrer gesamten Anruf Installationen in Ihrer Organisation ein Fehler auftritt.

Selbst wenn der vorherigen Antworten Zeit in Anspruch nehmen die untersuchen Weitere mithilfe der enthaltenen untergeordneten Berichte für einzelne Gebäude oder Netzwerke, die möglicherweise Remediation gesucht. Zwar die Fehlerrate insgesamt unterhalb der Ziel-Metrik oft die Fehlerraten für eine oder mehrere Gebäude oder Netzwerke befinden sich über die Metrik und-Wartung benötigen.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Rufen Sie Fehler bei der Installation auf, indem Sie erstellen und Subnetz 

Dieser Tabellenbericht wird verwendet, zu ermitteln und isolieren alle Gebäude oder Netzwerke, die Remediation benötigen.

> [!NOTE]
> Achten Sie darauf, dass Berichtsfilter Monat-Jahr mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den Filter **Monat-Jahr** -Bericht, um den neuen Standardmonat zu speichern.


![Meldet, dass die Listen Anruf Setup Gründe, erstellen, Netzwerk und Subnetz pro Monat organisiert.](media/quality-of-experience-review-guide-image17.png)

_Abbildung 17: Audio Setupfehler durch die Erstellung oder Subnetz_

##### <a name="remediation"></a>Wartung 

Konzentrieren Sie Ihre Remediation auf Gebäude oder Subnetze abgerufen, die die größte Lautstärke der Fehler Sie zuerst haben, da dies Auswirkungen auf die Benutzeroberfläche maximieren und Ihnen dabei helfen, um schnell die Organisationseinheit anruffehlern Setup zu reduzieren.
Die folgende Tabelle enthält die zwei Gründe für die Setup-Fehler beim Aufrufen von CQD gemeldet.

_Tabelle 6 – Gründe für Setup Anruffehlern_

| Rufen Sie die Ursache für Fehler bei der Installation                       | Typische Ursache                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fehlende Firmware Tiefe Paket Prüfung Ausnahmeregel | Gibt an, dass Netzwerkgeräte entlang des Pfads der Medienpfad daran gehindert, aufgrund von Tiefe Paket Prüfung Regeln hergestellt wird. Dies ist wahrscheinlich durch die Firewall-Regeln wird nicht ordnungsgemäß konfiguriert. In diesem Fall der TCP-Handshake war erfolgreich, aber der SSL-Handshake nicht.               |
| Fehlende Firmware IP-Block Ausnahme-Regel               | Gibt an, dass Netzwerkgeräte entlang des Pfads der Medienpfad daran gehindert, mit dem Office 365-Netzwerk hergestellt wird. Dies kann aufgrund von Proxy oder der Firewall-Regeln wird nicht Gewährung des Zugriffs für IP-Adressen und Ports für Teams und Skype für Business-Datenverkehr verwendet, um ordnungsgemäß konfiguriert sein. |

Nun, wie Sie Ihre Remediation beginnen, können Sie sich in einem bestimmten Gebäude oder Subnetz konzentrieren. Wie in die obigen Tabelle gezeigt wird, werden diese Probleme aufgrund der Firewall oder der Proxyserver Konfigurationen. Überprüfen Sie die Optionen in der folgenden Tabelle für Remediation Aktionen.

_Tabelle 7: nächste Schritte für Anruf Setup Fehler-Wartung_

| Wartung           | Anleitung     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurieren von firewall(s) | Arbeiten mit Ihrem Netzwerkteam, und überprüfen Sie Ihre Konfiguration Firewall(s) anhand [der Liste der Office 365-IP-Adresse](https://aka.ms/o365ips). Stellen Sie sicher, dass die [Medien Subnetze](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) und Ports in der Firewall-Regeln enthalten sind. Stellen Sie sicher, dass die erforderlichen TCP- und UDP-Ports in der Firewall geöffnet werden. Media bevorzugt UDP über TCP an. TCP gilt ein Failback-Protokoll.<br><ul><li>**TCP:** -port 443</li><li>**UDP:** 3478 – 3481 ports</li><ul> |
| Vergewissern Sie sich                | Nutzen Sie die [Microsoft Network Assessment-Tool](https://www.microsoft.com/download/details.aspx?id=53885) aus, um die Konnektivität von der betroffenen Gebäude oder Subnetz mithilfe der Konnektivität Kontrollkästchen-Funktion zu überprüfen.    |


### <a name="call-drop"></a>Rufen Sie die drop

Im Gegensatz zu anruffehlern-Setup, ist kein Code Grund an, warum Fehler abgebrochen aufgetreten ist, die einer bestimmten Problemursachen isolieren erschwert. Verworfene Anrufe, um eine bessere Ursachenanalyse einen abgeleiteten Ansatz bereitzustellen. Korrigieren von Bereichen des Zinsen für Audio und fördern der Verwendung von zertifizierte Geräte für Teams und Skype für Business Patchen von Clients, würden Sie abgelegten anruffehlern so lehnen Sie erwarten.

#### <a name="call-drop-failures-overall"></a>Rufen Sie die Drop-Fehler insgesamt

In diesem Diagrammbericht zeigt die Gesamtsumme der Audiostreams insgesamt Audiostreams gelöscht, und insgesamt Stream getrennt Prozentsatz. Zeigen Sie auf eine der Spalten zur Anzeige der Werte wie in der folgenden Abbildung dargestellt.

![Screenshot des ein Diagramm mit Prozentsatz der Audio aufrufen Datenströme gelöscht.](media/quality-of-experience-review-guide-image18.png)

_Prozentsatz der Abbildung 18 - insgesamt Anruf abgelegten Fehler_

##### <a name="analysis"></a>Analyse

Der Diagrammbericht zeigt Verwendung und Fehlern Ihrer Organisation über einen Zeitraum im Zusammenhang mit setzt aufrufen. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist der aktuelle Anruf insgesamt abgelegten Prozentsatz?

2.  Ist der Prozentsatz insgesamt Drop unterhalb der definierten Ziel Metrik?

3.  Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Ausfall Trend erhöhen, steady, oder verringern?

Die Informationen in diesem Bericht kann anweisen, die Geschichte des wie oft Ihrer gesamten Anruf setzt in Ihrer Organisation ausgeführt werden.

Antworten auf die obigen Fragen unabhängig nehmen die Zeit, überprüfen Sie die Verwendung der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Remediation. Zwar die Drop Gesamtrate unterhalb der Ziel-Metrik oft die Drop-Rate für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und-Wartung benötigt.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Rufen Sie Drop-Fehlern auf, indem Sie erstellen oder Subnetz

Fehler in dieser Tabellenbericht anzugeben, dass der Anruf wurde unerwartet gelöscht und eine negative Benutzeroberfläche zur Verfügung führte. Es gibt zwei-Berichte in der Vorlage, eine für Untersuchen von Konferenz- und das andere für zwei Teilnehmern enthalten.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.


![Meldet, dass die Anzahl von Listen und Prozentsatz Initiale Anrufe erstellen, Netzwerk und Subnetz pro Monat organisiert.](media/quality-of-experience-review-guide-image19.png)

_Abbildung 19 – Audio Anruf abgelegten Fehler durch Erstellen oder Subnetz_

##### <a name="remediation"></a>Wartung

Mit der vorstehenden Tabellenbericht können Sie jetzt "Hotspot" im verwalteten Netzwerk isolieren, in dem Anruf über die definierten Ziel Metrik vorkommen. Konzentrieren Sie sich auf Gebäude oder Netzwerken, in denen die Anzahl der höchste insgesamt Stream Sie zuerst am stärksten beeinträchtigt müssen, Ihre Remediation-Maßnahmen.

Häufige Ursachen für Anruf Ansätzen:

-   Klicken Sie unter bereitgestellte Netzwerk oder Internet Ausgang

-   Keine QoS auf eingeschränkte Netzwerke konfiguriert ist

-   Ältere Clientversionen

-   Verhalten der Benutzer

Nachdem Sie Hotspot erkennen, können Sie [Analytics aufrufen,](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) um Benutzer in das Gebäude für bestimmte Probleme an weiteren Überprüfung nutzen. Anruf Analytics PII-Daten enthält und kann deshalb hilfreich, um weitere mögliche Gründe für den Anruf setzt.

Unabhängig von der nächste Schritt ist es ratsam, dem Helpdesk benachrichtigen, dass es sich bei Auftreten eines Problems mit einem bestimmten Gebäude oder Subnetzen. Auf diese Weise können schnell reagieren auf eingehende Anrufe und Benutzer effizienter selektieren. Gekennzeichnete Benutzer können dann wieder an das Entwicklungsteam zur weiteren Untersuchung gemeldet werden.

Die folgende Tabelle enthält einige allgemeinen Methoden zum Verwalten und Warten von Anruf setzt.

_Tabelle 9: nächste Schritte für Anruf drop-Wartung_

| Wartung                              | Anleitung     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Netzwerk/internet                         | Nun, dass Sie wissen, welche Building betroffen ist, arbeiten Sie mit Ihrem Netzwerkteam Bandbreite an das Gebäude, um festzustellen, ob Probleme mit übermäßiger überwachen. Wenn das Problem in Bezug auf Überlastung des Netzwerks ermittelt werden, sollten Sie die zunehmende Bandbreite für das Gebäude. <br><br>**QoS:** Wenn einer steigenden Bandbreite unmöglich oder kostspielig ist, sollten Sie die Implementierung der QoS. Dadurch wird sichergestellt, dass Media-Pakete im verwalteten Netzwerk oben nicht Mediendatenverkehr priorisiert werden. Auch wenn es gibt keine klare Hinweise, dass die Bandbreite Ursache ist, sollten Sie diese Lösungen:<br><ul><li>[Microsoft-Teams QoS-Anweisungen](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype für Business QoS-Anweisungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Führen Sie eine Netzwerk-Bereitschaft:** Eine Netzwerk-Bewertung enthält Details zur Nutzung der erwarteten Bandbreite, wie bewältigen Bandbreite und Netzwerk ändert, und Netzwerke Methoden für Teams und Skype für Unternehmen empfohlen. Verwenden der obigen Tabelle als Quelle, müssen Sie eine Liste von Gebäude oder Subnetze, die eignen sich für eine Bewertung sind. <br><ul><li>[Microsoft-Teams, Netzwerk-Bereitschaft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype für Business Netzwerk Bereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Tool zur Bewertung der Microsoft Network:** Verwenden Sie dieses Tool für einen einfachen Test der Leistung des Netzwerks, um zu bestimmen, wie gut das Netzwerk für eine Teams ausführen würden oder Skype für Business Online Anruf. Das Tool können Sie die Leistung eines Subnetzes bewerten und überprüfen die Bereitschaft des Netzwerks gegen Microsoft Leistung [Anforderungen](https://aka.ms/performancerequirements).<ul><li>[Laden Sie das Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Clients (Skype für Unternehmen nur Online) | Einige ältere Clients wissen müssen, werden Probleme mit der Zuverlässigkeit Media dokumentiert. Überprüfen Sie die aufrufen Analytics-Berichte aus mehreren betroffenen Benutzer, oder erstellen Sie einen benutzerdefinierten Bericht der Clientversion-Tabelle in CQD in bestimmten Gebäude oder Subnetze mit Fehler insgesamt aufrufen abgelegten % Measure gefiltert. Diese Informationen helfen Ihnen beim verstehen, ob eine Beziehung zwischen Anruf setzt in dieser bestimmten Gebäude und eine bestimmte Version des Clients vorhanden ist.                                                                                                                                                              |
| Geräte                                  | Die meisten Gerätefehler sind aufgrund der Geräte, die für Teams oder Skype für Unternehmen ausgewiesen werden nicht verwenden. Fehler verwenden normalerweise das Format der integrierten Lautsprecher oder Mikrofone, die verwendet werden, oder Earbud/Mikrofon Kombinationen, die mit dem audio 3,5 mm-Anschluss auf einem Gerät verbunden sind. Aktuelle Empfehlung von Microsoft besteht darin, dass alle Benutzer, die auftreten, setzt aufrufen – oder schlecht Anrufe im Allgemeinen – und werden mithilfe von integrierten Geräte oder Treiber werden sollte eine [certified Kopfhörer oder eines Freisprechtelefons](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)bereitgestellt. |
| Verhalten der Benutzer                            | Wenn Sie feststellen, dass weder Netzwerk, Geräte oder Clients behoben werden, sollten Sie ansprechender [Meine Advisor](https://aka.ms/myadvisor) Anleitung bei der Entwicklung einer Strategie für die Einführung, um Benutzer informieren, wie Sie bewährte beitreten und Besprechungen zu beenden. Ein intelligenter Teams und Skype-Benutzer haben eine höhere benutzerfreundlichkeit für alle Teilnehmer in der Besprechung zur Folge. Ein Benutzer, der ihren Laptop in den Energiesparmodus (von der Abdeckung schließen) versetzt, ohne zu verlassen der Besprechung werden als ein unerwarteter Aufruf Drop klassifiziert werden.     |

## <a name="quality-investigations"></a>Qualität Untersuchungen

Im nächste Schritt den Zustand der Audioqualität über die Bereitstellung bewerten ist Audio schlechter aufrufen Verhältnis (PCR), TCP und Proxy Verwendung untersuchen. Es ist wichtig, denken Sie daran, dass CQD Daten bestimmte Ursache nicht enthalten, aber Sie stattdessen wahrscheinlich Problembereiche zu Beginn einer gemeinsame Unterhaltung mit der entsprechenden Teams für Abhilfemaßnahmen bietet.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt. Die Beschreibung der einzelnen Berichts Weitere Informationen finden. 


### <a name="investigate-call-quality"></a>Überprüfen der Anrufqualität

Der Gesamtprozentsatz PCR wird hauptsächlich verwendet, um anzugeben, ob die Organisation definierten audio metrischen Ziele erreicht. Es ist wichtig, beachten Sie, dass, auch wenn der Gesamtprozentsatz im Ziel ist, einige Subnetze oder Gebäuden möglicherweise nicht die definierten Ziele erfüllen und daher weiteren Untersuchung erfordern. Beispielsweise ist der Organisationseinheit audio PCR Prozentsatz 3 Prozent in möglicherweise Dezember, die erfüllt die Beispiel-Ziel, die bestimmte Gebäude weiterhin schlechte Erfahrungen, je nach der Verteilung dieser 3 Prozent haben.

#### <a name="overall-organizational-poor-call-percentage"></a>Insgesamt Organisationseinheit Anrufe schlechter Qualität Prozentsatz

Informationen zum Bewerten der Gesamtprozentsatz schlechter Anrufe für die Organisation verwenden Sie die allgemeine Qualität Analysediagrammbericht.

![Screenshot des ein Diagramm mit Prozentsatz der Anrufe schlechter Qualität](media/quality-of-experience-review-guide-image20.png)

_Abbildung 20 – Audioqualität - insgesamt_

##### <a name="investigation"></a>Untersuchung

Der Diagrammbericht zeigt die Verwendung und PCR Ihrer Organisation über einen Zeitraum. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist der gesamte PCR für den aktuellen Monat?

2.  Ist die PCR unterhalb der definierten Ziel Metrik?

3.  Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Ausfall Trend erhöhen, steady, oder verringern?

Antworten auf die obigen Fragen unabhängig Zeit in Anspruch nehmen die mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die weiteren Untersuchung möglicherweise untersuchen. Zwar die allgemeine PCR unterhalb der Ziel-Metrik häufig die PCR für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und weiteren Untersuchung benötigt.

#### <a name="audio-quality-overall"></a>Allgemeine Audioqualität

Es gibt zwei Bericht Strukturen in die Vorlagen für Audioqualität, einen für Untersuchen von Konferenz- und das andere für Anrufe mit zwei Teilnehmern enthalten. Für die Zwecke der Qualität Behebung versteht genauer identisch, damit wir hier auf Live Meeting konzentrieren können. Verbesserungen bei der Konferenz Qualität wirkt sich auch positiv auf zwei Teilnehmern die Anrufqualität aus. Berichte sind auch anzeigen, die Audioqualität für Konferenzen und zwei Teilnehmern von verkabelt und Wi-Fi enthalten.

> [!NOTE]
> Untersuchen von schlechter Gesprächen mit zwei Teilnehmern ähnelt dem Untersuchen von Telefonkonferenzen. Die Aufgabe wird zum Identifizieren von Gebäude oder Subnetze, die niedrigste Qualität überprüfen, ob es ein Muster schlechter Anrufe mit einem anderen Gebäude oder Subnetz liegt. 

![Screenshot der die Audioqualität - Webkonferenz-Bericht im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image21.png)

_Abbildung 21 – Audioqualität - Konferenzen_

##### <a name="investigation"></a>Untersuchung

Der Diagrammbericht zeigt Konferenzen oder Usage mit zwei Teilnehmern und PCR in Ihrer Organisation über einen Zeitraum. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist der gesamte PCR für den aktuellen Monat?

2.  Ist die PCR unterhalb der definierten Ziel Metrik?

3.  Ist PCR schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Trend PCR erhöhen, steady, oder verringern?

Antworten auf die obigen Fragen unabhängig Zeit in Anspruch nehmen die mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Untersuchung untersuchen. Zwar die allgemeine PCR unterhalb der Ziel-Metrik oft die PCR für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und-Wartung benötigt.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Schlechte Audiostream durch Erstellen und Subnetz

In diesem Tabellenbericht finden Sie zusätzliche Einblick in was beigetragen an, das die Anrufe als schlecht klassifiziert und trägt dazu bei, um Hotspot im verwalteten Netzwerk zu isolieren.

Details der Verbindung unterscheidet zwischen verkabelt und Wi-Fi und Jitter und Paketverlust Round-Trip Zeitmaßeinheiten (Zeit) enthält. Ein ähnlichen Bericht auch unter der zwei Teilnehmern Berichte vorhanden ist, und wird verwendet, um zwei Teilnehmern Anrufe in Ihrem verwalteten Netzwerk zu isolieren.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern. 

> [!TIP]
> Allgemeine Heimnetzwerken sind schwieriger zu Ursachenanalyse aufgrund der weit verbreitete Verwendung. Ein separater Bericht, der die IP-Adresse Firewall verwendet wurde hinzugefügt, um die Vorlage alle Netzwerke mit Korrigieren von Büros unterstützen, die gängigen Netzwerke verwenden.

![Bericht, der Verbindungstypen, Transporttypen und PCR größer als 3 % zusammen mit verschiedenen Gründen schlechter Qualität erstellen, Netzwerk und Subnetz pro Monat geordnet aufgeführt sind.](media/quality-of-experience-review-guide-image22.png)

_Abbildung 22 - Zusammenfassung durch Erstellen von schlechter Audiostream- und Subnetz Konferenzen_

##### <a name="remediation"></a>Wartung

Netzwerke mit der größten Menge der Audiostreams, da dies Auswirkungen maximieren und zur Verbesserung des Benutzers Hilfe schnell Erfahrung oder Kenntnisse konzentrieren Ihre Remediation auf Gebäude. Verwenden Sie die Jitter, Paketverlust und Maßangaben von Zeit um zu verstehen, was die Qualität der Anrufe schlechter Qualität beitragen wird. Es ist möglich, mehr als ein Problem sein:

-   **Jitter:** Media-Pakete eingeht mit einen Lautsprecher an automatischen klingen, wodurch andere Geschwindigkeit.

-   **Paketverlust:** Media-Pakete werden verworfen wird, erstellt die Auswirkung der fehlenden Wörter oder Silbenschrift verwenden.

-   **Zeit:** Media-Pakete sind sehr lange dauert, an das Ziel abgerufen werden, das einen Effekt Walkie-talkie erstellt.

Zwar keine zentrale Quelle Wahrheit Benutzerkonten für was Anruf schlechter Qualität führen kann, können mehrere allgemeine Methoden Umgang mit Netzwerkanomalien Ihnen ein.

Um Ihre Untersuchung Qualitätsprobleme rechten zu unterstützen, können Sie [Rufen Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)nutzen.
Mit Analysen aufrufen können Sie einer bestimmten Konferenz oder Benutzer detaillierte Anruf Bericht anzeigen. Dieser Bericht enthält PII-Daten und ist nützlich, wenn Sie versuchen, einen Grund für Fehler zu erkennen. Wenn Sie wissen, welche erstellen, die Verfolgung von Benutzern, Erstellen von unkompliziert sein sollte betroffen ist.

Vergessen Sie nicht, lassen Sie das Helpdesk wissen, dass diese Netzwerke Qualität, Probleme haben, sodass sie schnell selektieren und eingehende Anrufe beantworten können.

_Tabelle 9: Allgemeine Beiträge zu hohe PCR_

| Wartung                              | Anleitung       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Netzwerke                                 | Ein Netzwerk Überbelastung oder unter bereitgestellte kann zu Problemen mit Medienqualität führen. Arbeiten mit dem Netzwerkteam, um festzustellen, ob die Netzwerkverbindungen aus der Benutzer auf das Internet Ausgang zeigen hat genügend Bandbreite für Medien unterstützen. **Führen Sie eine Netzwerk-Bereitschaft:** Eine Netzwerk-Bewertung enthält Details zur Nutzung der erwarteten Bandbreite, wie bewältigen Bandbreite und Netzwerk ändert, und Netzwerke Methoden für Teams und Skype für Unternehmen empfohlen. Verwenden der obigen Tabelle als Quelle, müssen Sie eine Liste von Gebäude oder Subnetze, die eignen sich für eine Bewertung sind.<br><ul><li>[Microsoft-Teams, Netzwerk-Bereitschaft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype für Business Netzwerk Bereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Tool zur Bewertung der Microsoft Network:** Verwenden Sie dieses Tool für einen einfachen Test der Leistung des Netzwerks, um zu bestimmen, wie gut das Netzwerk für eine Teams ausführen würden oder Skype für Business Online Anruf. Mit diesem Tool können Sie bewerten die Leistung eines Subnetzes und überprüfen die Bereitschaft des Netzwerks gegen die Microsoft Performance [Requirements](https://aka.ms/performancerequirements).<br><ul><li>[Laden Sie das Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Quality of Service (QoS)                 | QoS ist eine bewährte Methode, um Pakete in einem Netzwerk, um sicherzustellen, dass sie am Ziel intakt eingehen und priorisieren. Berücksichtigen Sie die Implementierung der QoS in Ihrer Organisation, die die Qualität des Benutzererlebnisses maximieren, wenn die Bandbreite begrenzt oder eingeschränkt ist. QoS helfen, Probleme, die in der Regel mit hoher Paketverlust, lösen und – in geringerem Maße – Jitter und Round-Trip Zeiten. <br><ul><li>[Microsoft-Teams QoS-Anweisungen](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype für Business QoS-Anweisungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi kann eine erhebliche Auswirkungen auf die Anrufqualität haben. Wi-Fi-Design nicht in der Regel berücksichtigen Sie die netzwerkanforderungen für die VoIP-Dienste und sind häufig die Ursache von schlechter Qualität. **QoS:** Moderne drahtlose Netzwerke müssen vielen Geräten unterstützen. Diese Geräte konkurrieren für Bandbreiten- und können dazu führen, dass Qualitätsprobleme für VoIP-Dienste, in denen besitzen Geschwindigkeit und Wartezeit wichtiger. Wenden Sie sich an den Hersteller Ihres drahtlosen Einzelheiten, und implementieren Sie QoS für Ihr Drahtlosnetzwerk Skype für Geschäfts- und Teams Medien priorisieren. **AP-Dichte:** Zugriffspunkte (APs) möglicherweise zu weit auseinander oder nicht in eine ideale Speicherort. Um Probleme zu minimieren, setzen Sie zusätzliche APs in Konferenzräumen und Standorte, die von den Wänden oder sonstigen Objekte verdeckt werden nicht. **Mit 2,4 GHz im Vergleich zu 5 GHz:** 5 GHz enthält weniger Störungen im Hintergrund und einer höheren Geschwindigkeit und bei der Bereitstellung von VoIP über Wi-Fi priorisiert werden sollte. Jedoch 5 GHz ist nicht so stark wie mit 2,4 GHz nicht zugelassen und Walls so einfach. Überprüfen Sie vom Layout erstellen, um die Häufigkeit bestimmen Sie für die optimale Verbindung verwenden können. **Signalstärke:** Bisher gemessen in dBm (Power Verhältnis in DB), misst das die Stärke des drahtlosen Signals. Nachdem ein Gerät mit einem Zugriffspunkt verbunden ist, möchten nicht es können auf einfache Weise wechseln. Wenn das Gerät außerhalb der Zugriffspunkt verschoben wird, fällt die Signalstärke einen Punkt erreicht, die verursacht eine schlechte Verbindung, auch wenn ein anderes, je näher AP verfügbar ist. Wenn möglich, arbeiten Sie mit Ihrem AP-Hersteller, um sicherzustellen, dass die Zugriffspunkte konfiguriert wurden, um ein Gerät zu löschen, wenn ein akzeptables Maß Signalstärke unterschreitet. Dadurch wird sichergestellt, dass das Gerät an eine schwache Zugriffspunkt reagiert nicht. Dies ist eine gute Lösung, wenn Sie auf einfache Weise Weitere Zugriffspunkte hinzugefügt werden können. **WLAN-Treiber:** Wenn das Problem weiterhin besteht, stellen Sie sicher, dass wireless-Treiber auf dem aktuellen Stand sind. Dadurch wird eine beliebige benutzerfreundlich im Zusammenhang mit einer veralteten Treiber zu mindern. |
| Netzwerkgerät                           | In größeren Organisationen möglicherweise Hunderte von Geräten, die über das Netzwerk verteilt. Arbeiten mit Ihrem Netzwerkteam, um die Netzwerkgeräte vom Benutzer mit dem Internet sicherzustellen aufbewahrt werden und auf dem aktuellen Stand.     |
| VPN                                      | Es wurde gut dokumentiert, dass VPN-Geräte, Real-Time Media Arbeitslasten behandeln traditionell ausgelegt sind. Einige VPN-Konfigurationen verhindern die Verwendung von UDP (Dies ist das bevorzugte Protokoll für Audio) und stützen sich nur auf TCP. Berücksichtigen Sie die Implementierung einer [VPN-Split-Tunnel Lösung](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) zur Verringerung der VPN als Quelle von schlechter Qualität.        |
| Clients (Skype für Unternehmen nur Online) | Ältere Clients wurden als verursacht Probleme mit Medien. Stellen Sie sicher, dass Clients innerhalb von sechs Monaten nach Veröffentlichung gepatcht werden. [MyAdvisor](https://aka.ms/myadvisor) Hinweise zum Entwickeln einer Strategie für die Client-Bereitschaft nutzen und Bereitstellen von [Klick-und-Los](https://technet.microsoft.com/library/jj219427.aspx).      |
| Geräte                                  | Die Verwendung der [Geräte optimiert](https://partnersolutions.skypeforbusiness.com/solutionscatalog) , damit die Benutzeroberfläche wesentlich verbessert. Alles gleich sind optimierte Geräte so konzipiert, die Benutzeroberfläche mit Teams und Skype für Unternehmen zu maximieren und Erzeugen von höchster Qualität. Nutzen Sie [MyAdvisor](https://aka.ms/myadvisor) Anleitungen zum Entwickeln einer Strategie für die Bereitschaft Gerät.   |


### <a name="investigate-tcp-audio-sessions"></a>Untersuchen Sie die TCP-audiositzungen

TCP gilt ein Failback Transport- und nicht den primären Transport für Real-Time Media gewünschte. Der Grund dafür, dass sie ein Failback Transport ist besteht aufgrund der dynamische TCP. Beispielsweise, wenn ein Anruf erfolgt in einem Netzwerk latente und Medien Pakete verzögert werden klicken Sie dann Pakete von ein paar Sekunden vor – die eignen sich nicht mehr – konkurrieren für Bandbreite, um an den Empfänger zu abzurufen, die eine ungültige Situation verschlechtern können. Dadurch wird das audio Reparatur zusammenfügen und Dehnen Audio, wodurch hörbaren Artefakte häufig in Form von Jitter.

Die Berichte in diesem Abschnitt tätigen nicht unterschieden zwischen gute und schlechte Anrufe. UDP bevorzugte ist, suchen die Berichte für die Verwendung von TCP für Audio. Dies wird hauptsächlich durch unvollständig Firewallregeln verursacht. Weitere Informationen zu Firewall-Regeln für Teams und Skype für Business Online finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips).

> [!IMPORTANT]
> Mit einer gültigen [Erstellen Sie die Datei](#building-mapping) hochgeladen wird empfohlen, um schnell innerhalb von externen Audiostreams zu unterscheiden bei der Suche unter Verwendung von TCP zu können. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Audioströme, die mit allgemeinen TCP-Verwendung

Dieser Bericht gibt die TCP-Gesamtverwendung für Audio in den letzten sieben Monaten an, wie unten dargestellt.

Alle weiteren Berichte in diesem Abschnitt Schwerpunkt auf Eingrenzung bestimmte Gebäude und Subnetzen, wo TCP am häufigsten verwendet wird. Weitere Unterberichte zerlegen TCP Verwendung von Gesprächen mit zwei Teilnehmern und Konferenzen.

![Screenshot eines Diagramms, das die Anzahl der Audiostreams TCP pro Monat](media/quality-of-experience-review-guide-image23.png)

_Abbildung 23 – Audiostreams mit TCP-Verwendung_

##### <a name="investigation"></a>Untersuchung

Der Diagrammbericht zeigt Ihrer Organisation Gesamtverwendung TCP. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist das Gesamtvolumen des TCP-Anrufe für den aktuellen Monat?

2.  Handelt es sich verschlechtert oder besser als den vorherigen Monat?

3.  Ist die TCP-nutzungstrend erhöhen, steady, oder verringern?

Nehmen Sie Wenn Sie feststellen, dass die TCP-nutzungstrend erhöht wird, oder höher normalen monatlichen Nutzung, die Zeit untersuchen Sie mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Remediation. Idealerweise sollten Sie so wenig TCP-basierte audiositzungen wie möglich im verwalteten Netzwerk.

#### <a name="tcp-vs-udp"></a>TCP und UDP

In diesem Tabellenbericht identifiziert die Lautstärke von TCP und UDP Verwendungsberichten auf den aktuellen Monat für Konferenzen für Audio-, Video- und videobasierte Bildschirmfreigabe (VBSS).

![Bericht mit der Lautstärke des TCP und UDP-Konferenz Datenströmen im Vergleich mit PCR Vergleich dargestellt](media/quality-of-experience-review-guide-image24.png)

_Abbildung 24 – TCP und UDP - Konferenzen_

##### <a name="analysis"></a>Analyse

Obwohl Sie TCP-Nutzung so gering wie möglich sein soll, wird möglicherweise ein Bit der TCP-Verwendung in einer Bereitstellung andernfalls fehlerfrei angezeigt. Zum Vergleichen von UDP zur Verwendung von TCP-Audiostreams TCP durch UDP Audiostreams Prozentsatz bestimmt werden kann. Ein Wert über 1 Prozent muss genauer untersucht werden.

Im obigen Beispiel nehmen wir 1,806 TCP-Datenströme geteilt durch 10,481 UDP-Datenströmen bei einem Wert von 17,2 % eingehen. Dieser Wert ist größer als 1 Prozent und gibt an, dass wir müssen weiterhin die Untersuchung auf um zu bestimmen, wo die Verwendung von TCP auftritt.

Auch in den Bericht einbezogen ist Audio schlechter Prozentsatz. Dies ermöglicht Ihnen eine Ansicht in den Vergleich von Anrufqualität zwischen UDP und TCP zum Visualisieren wie TCP Overcall Anrufqualität auswirkt.

So nun, da Sie bestimmt haben, dass eine hohe Verwendung von TCP-basierte Audio in Ihrer Organisation vorhanden ist, was tun Sie als Nächstes? Wechseln Sie zur **TCP-Datenströme durch Erstellen und Subnetz** Berichte für die TCP-Nutzung durch Erstellen von und Subnetzen zu zerlegen.

#### <a name="tcp-streams-by-building-and-subnet"></a>TCP-Datenströme durch Erstellen und Subnetz

In den bereitgestellten CQD Vorlagen wechseln Sie in die TCP-Streams durch Erstellen und Subnetz-Berichte mithilfe der verwalteten oder Vorlage für alle Netzwerke. Es gibt drei Berichte in der Vorlage, eine für Untersuchen von Konferenzen mit und ohne Microsoft Relay-Informationen und eine für Untersuchen von Gesprächen mit zwei Teilnehmern enthalten. Zum Untersuchen der TCP, ist der Prozess, gleich, damit wir die Diskussion auf Konferenzen nur näher erläutert wird.

> [!IMPORTANT]
> Mit einer gültigen [Erstellen Sie die Datei](#building-mapping) hochgeladen wird empfohlen, um schnell innerhalb von externen Audiostreams zu unterscheiden bei der Suche unter Verwendung von TCP zu können. 

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.                                  |

![Bericht, TCP-Datenströme, erstellen, Netzwerk und Subnetz pro Monat geordnet aufgeführt.](media/quality-of-experience-review-guide-image25.png)

_Abbildung 25 – TCP-Datenströme durch die Erstellung- und Subnetz Konferenzen_

##### <a name="remediation"></a>Wartung

In diesem Bericht identifiziert bestimmte Gebäude und Subnetze abgerufen, die dem Volumen der Verwendung von TCP beitragen. Ein Bericht zusätzlicher ist ebenfalls enthalten, um die IP-Adresse des Microsoft-Relay zu identifizieren, die in den Anruf verwendet wurde, um zu isolieren fehlenden Firewallregeln. Konzentrieren Sie Ihre Remediation auf diese Gebäude, die dem höchsten zu erwartenden der Audiostreams maximieren Auswirkungen haben.

Die häufigste Ursache für die Verwendung von TCP fehlt Ausnahmeregeln in Firewalls oder Proxyserver. Wir sprechen Proxys im nächsten Abschnitt, also für jetzt Ihrer Arbeit Schwerpunkte auf die Firewalls. Über das Erstellen von oder Subnetz bereitgestellt, können Sie bestimmen, welche Firewall aktualisiert werden muss.

_Tabelle 10 - Remediation * Richtlinien für die TCP-Datenströme durch Erstellen und Subnetz_

| Wartung        | Anleitung     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurieren der firewall | Überprüfen Sie, ob [Office 365 IP-Ports und Adressen](https://aka.ms/o365ips) aus Ihrer Firewall ausgeschlossen werden. Obwohl es gibt viele IP-Adressen und Ports, die Media-bezogene TCP Probleme geöffnet werden müssen die folgenden Ihrer anfänglichen sind Schwerpunktthemen: Überprüfen Sie die folgenden [Medien Subnetzen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) befinden sich in Ihrer Firewall-Regeln. Finden Sie in Zeile 4 in der Tabelle, die für bestimmte Medien Subnetzinformationen angezeigt. [UDP-Ports 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): Diese Ports sind die bevorzugten Media-Ports und geöffnet werden müssen, andernfalls der Client wieder auf TCP-Port 443 fehl. |
| Vergewissern Sie sich             | Verwenden Sie das [Tool zur Bewertung der Microsoft Network](https://www.microsoft.com/download/details.aspx?id=53885) um zu prüfen, ob Konnektivitätsprobleme bei bestimmten Office 365-IP-Adressen und Ports aus dem betroffenen Gebäude oder Subnetz.    |

### <a name="investigate-http-proxy-usage"></a>Untersuchen Sie die Verwendung von HTTP-proxy

HTTP-Proxys sind die Bevorzugter Pfad für die Herstellung von mediensitzungen für eine Vielzahl von Gründen nicht. Viele Tiefe Paket Prüfung Features enthalten, die verhindern, dass Verbindungen mit dem Dienst abgeschlossen und Systemausfallzeit einführen können. Darüber hinaus können Proxys TCP erzwingen, im Gegensatz zu zulassen UDP, die für eine optimale Audioqualität empfohlen wird.

Es ist immer Microsofts Empfehlung an den Client für die Verbindung direkt Teams und Skype für BusinessServices konfigurieren. Dies ist besonders wichtig für basierenden Media-Datenverkehr.

> [!IMPORTANT]
> Ein gültiger [Erstellen Sie die Datei](#building-mapping) hochgeladen haben erleichtert es ordnungsgemäß innerhalb von externen Audiostreams zu unterscheiden beim Proxy Analyse. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Audioströme, die mit HTTP-Proxy Verwendung insgesamt

In diesem Bericht werden die Proxy-Nutzung über einen Zeitraum auf einer monatlichen Skala beschrieben. Der HTTP-Proxy Stream-Bericht in diesem Abschnitt der Vorlage ähnelt der TCP-Berichte. Es überprüfen nicht, ob Anrufe schlechter oder eine gute sind, aber gibt an, ob die Verbindung über HTTP hergestellt wurde.

![Screenshot der Audiostreams mit HTTP-Proxy-Verwendungsbericht im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image26.png)

_In Abbildung 26 – Audiostreams mit HTTP-Proxy-Verwendung_

##### <a name="analysis"></a>Analyse

Wenn Sie eine große Menge von HTTP-Verwendung angezeigt wird, finden Sie in Netzwerke Team, um sicherzustellen, dass die erforderlichen Ausnahmen vorhanden sind, damit Clients direkt Teams oder Skype für Business Online Media Subnetze weiterleiten. Idealerweise sollten keine Verwendung von HTTP-hier angezeigten vorhanden sein.

Wenn Sie nur eine Internet-Proxy in Ihrer Organisation haben, überprüfen Sie die ordnungsgemäße [Office 365-URLs und IP-Adresse Bereich Ausschlüsse](https://aka.ms/o365ips). Wenn mehr als ein, die Internet-Proxy in Ihrer Organisation konfiguriert haben, wird die HTTP nutzen Unterseite isolieren, welche Erstellen von Berichten oder Subnetz beeinflusst werden.

Für Organisationen, die den Proxy umgehen können nicht sicherstellen, dass die Skype für Business-Client anmelden ordnungsgemäß Wenn sie einen Proxyserver befindet wie im Artikel [beschrieben konfiguriert ist sollten Skype für Business Proxyserver verwenden, anstatt direkt anzumelden Verbindung](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>HTTP-Proxy-Streams durch Erstellen und Subnetz

In diesem Bericht identifiziert bestimmte Gebäude und Subnetze abgerufen, die zur Verwendung von HTTP-beitragen.

> [!IMPORTANT]
> Ein gültiger [Erstellen Sie die Datei](#building-mapping) hochgeladen haben erleichtert es ordnungsgemäß innerhalb von externen Audiostreams zu unterscheiden beim Proxy Analyse.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.                        |

![Screenshot der HTTP-Proxy Nutzung durch Erstellen und Subnetz Bericht im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image27.png)

_Abbildung 27 – HTTP-Proxy-Nutzung durch die Erstellung und Subnetz_

##### <a name="remediation"></a>Wartung

Konzentrieren Sie Ihre Remediation auf jedem Gebäude oder die Subnetze abgerufen, die Verwendung von HTTP-Proxy aufweisen. Die häufigste Ursache für HTTP-Verwendung fehlt Ausnahmeregeln in Proxys. Über das Erstellen von oder Subnetz bereitgestellt, können Sie bestimmen, welche Proxy aktualisiert werden muss.

Stellen Sie sicher, dass die erforderlichen [Office 365 FQDNs](https://aka.ms/o365ips) vom Proxy ausgeschlossen werden.

## <a name="endpoint-investigations"></a>Endpunkt Untersuchungen

In diesem Abschnitt konzentriert sich auf die Aufgaben für die Berichte zur Skype für Business-spezifischen Client-Versionen und die Verwendung von zertifizierte Geräte.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt. Die Beschreibung der einzelnen Berichts Weitere Informationen finden. 


### <a name="determine-client-versions"></a>Bestimmen der Client-Versionen

In diesem Bericht konzentriert sich auf Skype für Business Clientversionen verwendet und ihren relativen Lautstärke in der Umgebung identifizieren.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt und über die Azure Content Delivery Network (CDN) automatisch aktualisiert werden und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.

Versionsnummern für Skype für Business 2015 und 2016 finden Sie über die folgenden Links:

-   [Office 365-Client-Kanal Updateversionen](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Office 365-Version und Build-Nummern für klicken Sie auf Ausführen](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype für Business-Downloads und-Updates](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.  

> [!IMPORTANT]
> Clientberichte müssen Sie federated Teilnehmer Daten ausgeschlossen werden. Um Verbund Teilnehmer Daten auszuschließen, müssen Sie einen Abfragefilter für **Zweiten Mandanten-ID** in Ihrer Organisation [Mandanten-ID](#tenant-id)festlegen hinzufügen. |

![Screenshot des Berichts-Clients und-Geräten im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image28.png)

_Abbildung 28 - Client-Version-Bericht_

#### <a name="remediation"></a>Wartung

Ein wichtiger Aspekt gesteuerter hochwertigen benutzerumgebungen müssen Sie sicherstellen, dass verwaltete Clients auf dem neuesten Stand Versionen von Skype für Unternehmen ausgeführt werden. Dies bietet verschiedene Vorteile, dazu zählen:

-   Es ist einfacher, einige Versionen im Vergleich zu viele Versionen zu verwalten.

-   Es bietet eine einheitliche Erfahrung.

-   Es erleichtert die Problembehandlung bei Anrufqualität und Verwendbarkeit.

-   Microsoft stellt allgemeine Verbesserungen und Optimierungen ständig über das Produkt. Sicherstellen, dass Benutzer diese Updates erhalten, die ihre Risiken der Ausführung in ein Problem, das bereits behoben ist.

Einschränken des Ihre Bereitstellung Clientversionen, die weniger als sechs Monaten sind wird die gesamten Benutzeroberfläche verbessert und Verbesserung der Verwaltbarkeit im Vergleich zu großen Anzahl von verschiedenen Versionen des Clients in der gleichen Umgebung müssen.

Wenn Sie nur Office Klick-und-Los verwenden, werden Sie automatisch binnen sechs Monaten sein. Es ist keine weitere Aktion erforderlich.

"If"; wie die meisten Unternehmen Sie eine Kombination von Klick-und-Los und Installer-Paket (MSI) verfügen, können Sie den Bericht verwenden, um sicherzustellen, dass die MSI-Clients regelmäßig aktualisiert werden. Konzentrieren Sie auf diesen Clients, auf dem das Volume überdurchschnittlich ist. Wenn Sie, dass Clients feststellen hinter sinkt, arbeiten mit dem Team verantwortlich für die Verwaltung von Office-Updates, und stellen Sie sicher, dass sie genehmigen und Bereitstellen von Client-Patches regelmäßig sind.

### <a name="devices-investigations"></a>Geräte Untersuchungen

So tätigen mithilfe des geräteberichts folgende Punkte sollten Sie das Konzept der Mittelwert Opinion verstanden haben (MOS). MOS ist die Messung Gold-Standard: die wahrgenommene Audioqualität zu ermitteln. Es wird als eine Bewertung ganze Zahl im Bereich von 0 bis 5 dargestellt.

Die Grundlage für alle Maßnahmen der Sprachqualität ist wie eine Person für die Qualität der Speech Verbindungsmodus. Da es von human Wahrnehmung betroffen ist, ist es grundsätzlich subjektive. Es gibt mehrere verschiedene Methoden subjektive testen.
Die meisten VoIP Qualität Measures basieren auf einer absoluten Kategorisierung Bewertungsskala (ACR).

Ein ACR subjektive Test bewerten in eine statistisch signifikante Anzahl von Personen ihre Qualität auf einer Skala von 1 (schlecht) auf 5 (hervorragend). Der Mittelwert der Ergebnisse ist die MOS. Die resultierende MOS hängt von den Bereich der Erfahrungen, die die Gruppe und den Typ des Erfahrung bewertet wird verfügbar gemacht wurden.

Da es nicht sinnvoll, um für ein Kommunikationssystem live subjektive Tests der Sprachqualität auszuführen ist, Teams und Skype für Unternehmen mithilfe von erweiterten Algorithmen eine subjektive Testergebnisse objektive vorhergesagt MOS Werte generieren.

Der verfügbare Satz mit MOS und Metrik eine Ansicht in der Qualität der Zustellung an die Benutzer bereitstellen.

Durch Bereitstellen von Benutzern mit Geräten zertifiziert für Teams und Skype für Unternehmen, verringern Sie die Wahrscheinlichkeit solch negative Erfahrungen aufgrund des Geräts selbst (die wahrscheinlicher, beispielsweise mit integrierten Laptop-Lautsprecher und Mikrofon ist). Weitere Informationen finden Sie unter [Telefone und Geräte für Skype für Unternehmen](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Organisatorische Verwendung der Capture-Geräte (Mikrofone) nach volume

In diesem Bericht wird verwendet, um Mikrofon Usage bewerten und MOS Score und finden Sie in den zugehörigen Vorlagen unter Clients und Geräte *.*

> [!IMPORTANT]
> Gerät Berichte müssen Sie federated Teilnehmer Daten ausgeschlossen werden. Um Verbund Teilnehmer Daten auszuschließen, müssen Sie einen Abfragefilter für **Zweiten Mandanten-ID** in Ihrer Organisation [Mandanten-ID](#tenant-id)festlegen hinzufügen. 

> [!NOTE] 
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.<br><br> Sie möglicherweise feststellen, wenn mehrere Male gemeldet, dass Sie dasselbe Gerät finden Sie unter Bericht anzeigen. Dies liegt daran, die das Gerät gemeldet wird an CQD gemeldet werden. Unterschiede in der Hardware und Betriebssystem-Gebietsschema Berichten Gerätedaten unterschiedlich.

![Screenshot des Berichts Geräte (Mikrofon) im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image29.png)

_Abbildung 29 - – Gerätebericht (Mikrofon)_

##### <a name="remediation"></a>Wartung

Der erste Schritt besteht das Ziel des Vorgangs MOS bestimmen erreichen möchten. MOS bewertet Bereich von 1 bis 5, mit 5 wird das beste. Wählen Sie eine angemessene Ziel basierend auf Ihrer Umgebung und Abfrageergebnisse. Im folgenden Beispiel ist das Ziel ein MOS Bewertung von 3.6 oder höher für alle Geräte, die mehr als 100 Datenströme aufweisen. Sie erzielen die Gerätequalität abzielen, wenn:

-   Die Abfrageergebnisse Gerät zurückgeben MOS \> 3.6 für NumStreams \> 100

In der Regel müssen Sie leistungsschwachen Geräte mit zertifizierte Geräte zu ersetzen. Einige Aspekte beim Überprüfen von Device Report umfassen:

-   Sind die zertifizierte Geräte oder zweifelsfrei funktionierende in Ihrer Umgebung? In der Abfrage mit einem niedrigeren MOS Faktor als des Basisplans ein zertifizierten oder eine gute Gerät zurückgegeben wird, möglicherweise unbekannte Weitere Faktoren (beispielsweise eine schlechte Netzwerk- oder unzureichende pc), die an die niedrigste Punktzahl beiträgt.
    Zusätzliche Untersuchung werden benötigt.

-   Sie können Benutzer eines Geräts über [Analytics aufrufen](#call-analytics-training)identifiziert. Überprüfen Sie, um sicherzustellen, über die neuesten Gerätetreiber verfügen und, dass ihr Gerät über ein USB-Hub verbunden ist.

-   Überprüfen Sie, ob eine Beziehung zwischen fehlerhafte Geräte und stellen Sie ein bestimmtes System und das Modell vorhanden ist. Wenn dies der Fall ist, kann das Gerät nicht kompatibel oder Treiber-Upgrades benötigen.

Die zweite Aufgabe besteht darin, die allgemeine Verwendung nicht zertifizierte Geräte zu bestimmen. Es wird empfohlen, mindestens 80 Prozent der alle Audiostreams zu einem zertifizierten Gerät verwenden.
Dies geschieht am besten durch den Geräte-Bericht nach Excel exportieren und die Verwendung von zertifizierten oder genehmigten Geräten manuell berechnen. Organisationen lassen in der Regel eine Liste mit allen genehmigten Geräten, damit filtern und Sortieren von Daten einfach sein sollte.

## <a name="appendix-a-lync-networking-guide"></a>Anhang a: Lync Netzwerke (engl.)

Für weitere Hintergrund auf der Teams und Skype für Netzwerke Business-Konzepte und Gründe für die Qualität ihrer Wichtigkeit ist der [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) gelten auch weiterhin.

## <a name="appendix-b-network-performance-requirements"></a>Anhang b-Leistung netzwerkanforderungen

Die Qualität von Real-Time-Medien (Audio, Video und Anwendungsfreigabe) Implementation wird durch die Qualität der End-to-End-Netzwerkkonnektivität erheblich beeinträchtigt. Für eine optimale Teams oder Skype für Business Medienqualität muss Ihr Netzwerk die folgenden Leistungsmetriken Netzwerk erfüllen.

_In Tabelle 11 - Netzwerk leistungsanforderungen_

| Metrik                           | Client zu Microsoft Edge           | Kundenedge zu Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Wartezeit (unidirektional)                | \<50 ms                            | \<30 ms                            |
| Wartezeit (Zeit oder Roundtripzeit) | \<100 ms                           | \<60 ms                            |
| Bursts von Paketverlusten                | \<10 % Intervall 200 ms   | \<1 % Intervall 200 ms    |
| Paketverlust                      | \<1 % Intervall 15 s    | \<0,1 % Intervall 15 s  |
| Die Kommunikation zwischen hinzukommen Jitter Paket      | \<während ein Intervall von 15 s 30 ms | \<15 ms Intervall 15 s |
| Paket neu anordnen                   | \<0,05 % außerhalb der Reihenfolge Pakete       | \<0,01 % außerhalb der Reihenfolge Pakete      |

Weitere Informationen finden Sie unter den folgenden Artikel über das [Media Quality und Netzwerk Leistung](https://aka.ms/performancerequirements) für Teams und Skype für Business Online.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Anhang C. Weitere Ressourcen

### <a name="building-data-file"></a>Erstellen von-Datendatei

-   [Aktivieren und Verwenden von CQD in Skype für Business Online](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>CQD-Schulung

-   <https://aka.ms/sof-cqd>

-   Handbuch [Erste Schritte mit CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) und Workshop.

-   [CQD Dimensionen und Measures online-Entwicklerhandbuch](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Rufen Sie Analytics-Schulung

-   [Einführung in Anruf Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Einrichten der Anrufanalyse von Skype for Business](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Wenden Sie Analytics

-   Community: [Skype für Business Preview-Programm](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Wenn Sie Unterstützung erhalten möchten, melden Sie sich unsere Preview Portal [www.skypepreview.com](http://www.skypepreview.com), wählen Sie **Bericht ein Problem**und verwenden Sie die Option **Erstellen eines neuen Fehler** Berichten eines Problems. Bitte beachten Sie, dass Support-Mitarbeiter zur Verfügung, Unterstützung von Montag zwischen 6 Uhr um 9 Uhr EST zurück. Anfragen außerhalb Stunden, werden der folgende Tag selektierender.

### <a name="devices"></a>Geräte

-   [Skype für Business Solutions Catalog Peripheriegeräte & PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Mandanten reporting

-   [Office 365 Annahme Inhaltspaket](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Skype for Business Online-Berichterstellung](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Microsoft-Teams, reporting](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
---
title: Quality of Experience überprüfen Handbuch für Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 'Handbuch für die Analyse der Leistung für Microsoft-Teams, Real-Time Media mithilfe von Anrufen Quality Dashboard (CQD).'
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
  - Microsoft Teams
---

# <a name="quality-of-experience-review-guide"></a>Quality of Experience überprüfen Guide

In diesem Handbuch wird über das Laufwerk Wert Phase für Microsoft-Teams und Skype für Business Online. Sie können dieses Handbuchs [eine Word-Version herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) .

## <a name="introduction"></a>Einführung

Um am stärksten zur Verbesserung der benutzerfreundlichkeit haben, müssen Unternehmen wichtige Bereiche durchsetzen, die in der folgenden Abbildung dargestellt sind.
Weitere Bereiche umfassen, Betriebsaufgaben identifiziert, Zielvorgaben für Qualitätsmetriken, die Metriken zu verwenden, um Erfolg einzuschätzen Punkte und Bereiche der Untersuchung einschränken, je nach Bedarf.

![Wichtige Bereiche für die Qualität des Benutzererlebnisses enthalten, Audio, Zuverlässigkeit, den benutzerumfragen, Geräte und Clients.](media/quality-of-experience-review-guide-image1.png)

_Abbildung 1: Schlüssel betriebliche behandelten im gesamten Dokument_

Ständig bewerten und Korrigieren von den in diesem Dokument beschriebenen Gebieten, können Sie ihre Potenzial, die sich negativ auf die Qualität Ihrer Benutzer-Erfahrung auswirken reduziert. Die meisten Benutzer-Erlebnis Probleme in einer Bereitstellung können in die folgenden Kategorien unterteilt werden:

-   Unvollständige Firewall oder der Proxyserver-Konfiguration

-   Schlechte Wi-Fi-Abdeckung

-   Unzureichende Bandbreite

-   VPN

-   Inkonsistente oder veraltete Clientversionen

-   Nicht optimierte oder integrierte Audiogeräte

-   Problematisch Subnetze oder Netzwerkgeräte

Durch sorgfältige Planung und Entwurf vor der Bereitstellung von Teams oder Skype für Business Online können Sie Aufwand reduzieren, die erforderlich sind, um qualitativ hochwertige guter maintain.

Dieses Handbuch konzentriert sich auf Online aufrufen Quality Dashboard (CQD) als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche mit besonders auf die Annahme und Auswirkungen auf die Maximieren-Audio verwenden. Versucht, das Netzwerk zur Verbesserung der Audioqualität Verbesserungen übersetzt auch direkt in Verbesserungen bei video sowie die Desktopfreigabe.

Um die Bewertung zu beschleunigen, werden zwei curated CQD-Vorlagen zur Verfügung gestellt: eine für alle Netzwerke und der andere verwalten für gefiltert wird verwaltet wird nur Netzwerke (intern). Obwohl der Berichte alle Netzwerke Vorlage zum Erstellen von und Netzwerkinformationen anzeigen konfiguriert sind, kann es bei der Arbeit zu sammeln und Hochladen von Informationen zum Erstellen von dennoch verwendet. Erstellen von Informationen in CQD hochladen ermöglicht dem Dienst durch Hinzufügen von benutzerdefinierten erstellen, Netzwerk und Speicherort Informationen beim Unterscheidung von externen Subnetzen interne reporting optimiert. Weitere Informationen finden Sie unter [Erstellen von Zuordnung](#building-mapping) weiter unten in diesem Dokument.

### <a name="what-is-the-cqd"></a>Was ist die CQD?

Sie verwenden rufen Quality Dashboard (CQD) Einblick in die Qualität der Anrufe mithilfe von Teams und Skype für BusinessServices. CQD soll helfen, Skype für Geschäfts- und Teams-Admins und Netzwerktechniker Optimieren des Netzwerks. CQD untersucht aggregierte Informationen für eine ganze Organisation, auf dem gesamten Muster offensichtlich, werden können Mitarbeiter informiert Bewertung der Anrufqualität zu ermöglichen. CQD bietet Berichte der Anruf-Metriken, die Ihnen Einblick in die allgemeine Anrufqualität, Anruf Zuverlässigkeit und benutzerfreundlichkeit bieten.

> [!NOTE]
> CQD enthalten keine personenbezogene Informationen (PII). PII sind Informationen, die verwendet werden kann allein oder mit anderen Informationen bezeichnen, wenden Sie sich an, oder suchen eine einzelne Person oder um eine einzelne Person im Kontext zu identifizieren. 

### <a name="intended-audience"></a>Zielgruppe

Dieses Dokument ist für die direkte Verwendung von Partnern und Kunden Beteiligten mit Rollen wie leitender/Architekt für die Zusammenarbeit, Berater, Change Management/Annahme Specialist, Unterstützung/Help Desk führen, Netzwerk führen, Desktops führen und IT-Administrator verwendet werden

Dieses Dokument ist auch von der festgelegten Qualität Champion(s) verwendet werden soll.
Weitere Informationen finden Sie unter [der Qualität Champion-Rolle](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie bevor Sie dieses Handbuch verwenden sicher, dass Sie die richtige Mandanten [Rollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) zugewiesen, sodass Sie CQD zugreifen können.

-   **Globalen Administratorrolle von Office 365:** Greift auf alle administrativen Funktionen in Office 365-Suite von Diensten in Ihrem Plan, einschließlich Skype für Unternehmen.

-   **Skype für Business Administratorrolle:** Skype für Unternehmen für Ihre Organisation konfiguriert, und ist berechtigt, die [Berichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Office 365 Administrationscenter anzeigen. Diese Rolle ist erforderlich, auch wenn Sie nur Teams bereitstellen.

Alternativ können Sie ein Office 365-Benutzerkonto den Zugriff auf Berichtsfunktionen nur folgende Rolle zuweisen.

-   **Leser von Berichten:** Können die [Berichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Office 365 Administrationscenter, alle Berichte aus dem [Office 365 Annahme Inhaltspaket](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)und CQD Berichte anzeigen.

Grundlegendes zu den grundlegenden Konzepten von CQD maximieren können die Auswirkung, die Sie bei der Verbesserung Ihrer Benutzer Erfahrung mit Teams oder Skype für Business Online vornehmen können.
Weitere Ressourcen finden Sie im [Anhang](#other-resources).

## <a name="what-is-quality"></a>Was ist die Qualität?

Im Zusammenhang mit Qualität in Teams und Skype für Unternehmen ist es wichtig, definieren Sie den Begriff, um eine allgemeine Grundlegendes zu erreichen. Qualität, ist wie hier definiert eine Kombination von Metriken und benutzerfreundlichkeit Service.

![Service-Metriken bestehen aus der Anrufe schlechter Qualität Verhältnis, Zuverlässigkeit, Endpunkte-Geräte und Client-Versionen. End User Experience Wahrnehmung der Dienstqualität des Benutzers besteht.](media/quality-of-experience-review-guide-image2.png)

_Abbildung 2: Was Qualität ist?_

### <a name="define-your-target-metrics"></a>Definieren Sie die Ziel-Metriken

In diesem Abschnitt werden die Core Service-Metriken, die wir verwenden, um bewerten, wie Dienste Health auftreten. Ständig bewerten und Entwicklung, diese Metriken unter Ziel zu halten, helfen Ihnen, sicherzustellen, dass Ihre Benutzer konsistente, zuverlässige Anrufqualität auftreten. Um Ihnen den Einstieg zu erleichtern, werden die folgenden Ziele bereitgestellt.
Lassen Sie uns kurz den Unterschied zwischen einem verwalteten und nicht verwalteten Netzwerk:

-   Eine *verwaltete* Netzwerk beeinflusst, und von der Organisation gesteuert werden kann.
    Dazu gehören das interne LAN, remote WAN und VPN.

-   Ein *nicht verwalteten* Netzwerk werden nicht beeinflusst oder von der Organisation gesteuert. Ein Beispiel für eine nicht verwaltete Netzwerk ist ein Hotel oder am Flughafen Netzwerk.

_Tabelle 1: Core Ziel Health Assessment Metriken_

|               | Qualität für verwaltete Netzwerke | Zuverlässigkeit für verwaltete Netzwerke |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Metrische name   | Trefferquote % der Audio-Anrufe schlechter Qualität      | Rufen Sie Setup mit Fehlern %            | Rufen Sie die Drop Fehler % |
| Beispiel-Ziel | \<3 %                         | \<1 %                             | \<4 %                 |

Es ist wichtig, zu besprechen und definieren die Ziele Ihrer Organisation, um Ihre Geschäftsziele zu erfüllen. Idealerweise sollten Sie diesen Zielen vor der Bereitstellung identifizieren.

#### <a name="audio-pcr-"></a>Audio PCR % 

Audio schlechter aufrufen Verhältnis (PCR) stellt allgemeine Prozentsatz an anrufen, die Audioqualität Ihres Unternehmens. Diese Metrik dient zum Hervorheben von Bereichen, in Ihrer Organisation Aufwand für die stärksten wirken sich in Richtung verringern diesen Wert und Verbessern der benutzererfahrung, weshalb verwaltete Netzwerken der Schwerpunkt sind beim Betrachten PCR konzentrieren können. Externe Benutzer zu wichtig sind, aber Untersuchungen unterscheidet sich regelmäßig Organisations- und Benutzer.
Erwägen Sie, bewährte Methoden für externe Benutzer, und externe Anrufe unabhängig von der gesamten Organisation betrachten.

#### <a name="call-setup-failures-"></a>Rufen Sie Setup mit Fehlern % 

Dies ist eine beliebige Media-Sitzung, die konnte nicht hergestellt werden. Aufgrund den Schweregrad der Auswirkungen ermittelte Benutzerinteraktion ist das Ziel dieser Wert als erreicht bald wie möglich bei Null zu reduzieren. Ein hoher Wert für diese Metrik ist in neuen Bereitstellungen mit unvollständiger Firewallregeln häufiger als eine über Erfahrungswerte zur Bereitstellung, aber es ist wichtig, die in regelmäßigen Abständen Video. Ihre betriebliche Genehmigungsverfahren Laufe der Zeit können Sie diese Metrik zum Einschließen von Video- und Desktopfreigabe Arbeitslasten erweitern.

#### <a name="call-drop-failures-"></a>Rufen Sie die Drop Fehler % 

Dies gilt für ein audio Arbeitslast, in dem die Sitzung unerwartet beendet. Ihre betriebliche Genehmigungsverfahren Laufe der Zeit können Sie diese Metrik zum Einschließen von Video- und Desktopfreigabe Arbeitslasten erweitern.

### <a name="service-metrics"></a>Service-Metriken

Dienst metrischen Ziele bestehen bestimmte clientbasierte Metriken.

#### <a name="pcr"></a>PCR

Die Grundlage für die Bestimmung, ob ein Anruf schlechter eingestuft ist, wird mithilfe des Anrufe schlechter Qualität-Verhältnis (PCR). PCR besteht aus fünf Netzwerk-Metriken, die in der folgenden Tabelle beschrieben. Für einen Anruf als schlecht klassifiziert werden muss nur eine Metrik den definierten Schwellenwert überschreitet. Weitere Informationen zum Vorgang, Anruf Klassifizierung finden Sie unter [in diesem Blogbeitrag](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tabelle 2: Service-Metriken Anrufe schlechter Qualität_

| Metrik                                           | Beschreibung                                                                                                                                                                                                                                                                                                                                                                  | Benutzererfahrung                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jitter \>30 ms                                   | Dies ist die durchschnittliche Änderung Verzögerung zwischen aufeinander folgende Pakete. Für einige Ebenen von Jitter über Pufferung können Teams und Skype für Unternehmen anpassen. Es ist nur, wenn die Jitter überschreitet die Pufferung, dass ein Teilnehmer die Effekte der Jitter bemerkt.                                                                                                                         | Die Pakete an einem anderen kumulativ dazu führen, dass ein Lautsprecher Stimme zum automatischen auszugeben.                                                                                       |
| Paketverlustrate \>10 % oder 0,1                    | Dies ist häufig als Prozentsatz der Pakete definiert, die verloren gegangen sind. Paketverlust wirkt sich direkt auf die Audioqualität – von kleinen, verloren Person Pakete, die fast keine Auswirkungen auf Back Bursts von Verlusten haben, Ursache Audio vollständig Ausschneiden.                                                                                                                               | Die Pakete werden verworfen und nicht eingehenden an das vorgesehene Ziel verursachen Lücken in den Medien, resultierende in verpassten Silben und Wörter und abgehackte video und Freigabe. |
| Roundtripzeit \>500 ms                         | Dies ist der Zeitaufwand zum Abrufen von ein IP-Paket von Punkt A nach Punkt B und an Punkt A. Diese Netzwerk Verteilung Verzögerung ist mit der physischen Abstand zwischen zwei Punkte und der Lichtgeschwindigkeit verknüpft und enthält zusätzlichen Aufwand, die von den verschiedenen Geräten im Netzwerkpfad übernommen.                                                                                  | Die Pakete braucht zu lange zum am Ziel eingehen dazu führen, dass einen Effekt Walkie-talkie.                                                                                 |
| NMOS-Beeinträchtigung Durchschnitt \> 1.0                  | Eine oder mehrere der folgenden Metriken Netzwerk zwar einzeln waren nicht schlecht, verursacht zusammen um mehr als einen Punkt der Netzwerk- [Mean Opinion Score](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS), zu löschen. Dies bedeutet nicht unbedingt die Netzwerkschnittstelle ist schlecht, aber genügend Probleme aufgetreten sind, während des Anrufs, dass Qualität reduziert wurde. | Hierbei handelt es sich um eine Kombination von Jitter Paketverlust, und – in geringerem Maße – Roundtripzeit erhöht. Der Benutzer kann eine Kombination der folgenden Symptome auftreten.          |
| Durchschnittliches Verhältnis zwischen ausgeblendeten Samples \> 7 % oder 0,07 | Eine oder mehrere der folgenden Metriken Netzwerk zwar einzeln waren nicht schlecht, verursacht dem Client selbst reparieren das Medium. Ein ausgeblendeter audio Beispiel ist ein Verfahren zur abrupten Übergang zu glätten, die in der Regel durch Initiale Netzwerkpaketen verursacht werden würde.                                                                                                                | Hohe Werte anzugeben, dass erhebliche Ebenen der Verlust zum Verbergen angewendet wurden, und ergab Audio verzerrt oder verloren.                                                  |

#### <a name="client-and-device-readiness"></a>Client- und Gerätefunktionen Bereitschaft

Benötigen Sie eine solide Client- und Gerätefunktionen Strategie um sicherzustellen, dass die Benutzer eine konsistente und positive Benutzeroberfläche zur Verfügung haben. Einige wichtige Prinzipien Laufwerk jeweiligen Strategie Readiness.

##### <a name="client-readiness"></a>Client-Bereitschaft

Eine Strategie für die sichere Client Bereitschaft wird sichergestellt, dass Ihre Benutzer die neueste Version des Clients und genießen dabei die bestmögliche Erfahrung ausgeführt werden.
Microsoft-patches routinemäßig die Skype für Business Client; sicherstellen, dass Sie es in Ihrer Umgebung Stand ist entscheidend für Ihre gesamten Erfolg.

Es wird empfohlen, dass Sie nicht in Ihrer Client-Versionen von mehr als sechs Monaten fallen hinter lassen. Wenn Sie Office Klick-und-Los verwenden, sind Sie bereits auf dem aktuellen Stand vom Dienst gespeichert wird. Verwenden Sie enthalten [Kundenbericht](#determine-client-versions)wie weiter unten in diesem Handbuch wird beschrieben, die Sie dabei unterstützen. Sie können auch die Beispielberichte Rate Meine aufrufen zu steigern Ihrer Strategie für die Client-Bereitschaft nutzen.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt sind, und durch die Azure Content Delivery Network automatisch aktualisiert, und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.


##### <a name="device-readiness"></a>Gerät Bereitschaft

Keine einer Strategie für die einzelne kann die Benutzeroberfläche, die mehr als Ihrer Strategie für die Bereitschaft Gerät auswirken. Die meisten Organisationen freuen, entfernen Sie unnötige Geräte von Benutzern (beispielsweise Telefonapparate oder anderen dedizierten Audiogeräte), und dies ist häufig als Rechtfertigung Core für den Wechsel zu Teams oder Skype für Unternehmen. Allerdings zögern gleichen Organisationen manchmal Replacement-Geräte bereitstellen, auch wenn diese Geräte kostengünstigeren wurden. Modernen Laptops und PCs, jedoch mit integrierten Mikrofon und Lautsprecher, ausgestattet sind nicht für die Business-Klasse Voice over IP (VoIP) optimiert. Dadurch wird erstellt oft eine schlechte Erfahrung für alle Teilnehmer, insbesondere dann, wenn der Lautsprecher in einer lauten Umgebung ist. Zertifizierungsprogramm für Microsoft Gerät wird sichergestellt, dass, wenn ein Benutzer einen Telefonanruf gehört mithilfe von jedem Gerät zertifiziert für Teams oder Skype für Unternehmen, eine wünschen erzeugt, die zu einem Gerät nicht zertifizierter überlegen ist.

Wir empfehlen immer Teams und Skype für Unternehmensbenutzer eine zertifizierten Kopfhörer oder Lautsprecher verwenden, wenn einen Anruf durch mithilfe eines Desktopclients teilnehmen.
Weitere Informationen zu Microsoft überprüfen zertifizierte Geräte in diesem [Artikel über das Telefone und Geräte qualifizierten](https://technet.microsoft.com/office/dn788944.aspx). Verwenden Sie den [Device Report](#devices-investigations)Unterstützung bei der Verwaltung Ihrer Geräte weiter unten in diesem Handbuch. Die Beispielberichte Rate Meine aufrufen, können auch um Ihrer Strategie für die Bereitschaft Gerät weiter zu verbessern.

### <a name="user-experience"></a>Benutzererfahrung

Analysieren die Benutzeroberfläche ist mehr Kunst als Science, da hier die Metriken gesammelt nicht immer bedeuten, es ein Problem mit dem Netzwerk oder Service ist, sondern vielmehr sie hinweisen, dass der Benutzer ein Problem wahrnimmt. Microsoft bietet einen Umfragemechanismus integrierten – bekannt als Rate Meine aufrufen (RMC) – Hilfe benutzerfreundlichkeit zu ermitteln. RMC hilft Ihnen die aus Sicht des Benutzers die folgenden Fragen beantworten:

-   Weiß ich, wie Sie die Lösung verwenden können?

-   Ist die Lösung, einfach zu verwendenden und intuitiv, und wird über die alltägliche Kommunikation führe unterstützt?

-   Kann die Lösung mich Meine erledigen?

-   Was ist meine allgemeine Wahrnehmung der Lösung?

-   Kann ich verwenden die Lösung an einer beliebigen Stelle in der Zeit, unabhängig davon, an denen ich bin?

-   Kann ich einrichten und verwalten ein Anrufs?

#### <a name="rmc"></a>RMC

RMC Teams und Skype für Unternehmen integriert und wird automatisch so konfiguriert, dass nach einem in jeder 10 Anrufe oder 10 Prozent aller Anrufe angezeigt werden. In diesem kurzen Umfrage fordert den Benutzer den Anruf bewerten und einen wenig Kontext für warum die Anrufqualität schlechter wurden möglicherweise bereitstellen. Eine Bewertung ein oder zwei schlechter gilt, eignet sich drei bis vier und fünf ist hervorragend. Obwohl es etwas eines Indikators Verzögerung beim ist, ist dies eine nützliche Metrik für Unternehmensdaten Probleme, die Service-Metriken verpassen können.

> [!NOTE]
> Bis der Benutzer aufgefordert werden, durch das Erteilen von guten Feedback zusätzlich zu schlecht, Antworten in der Regel auf RMC Umfragen reagieren zurückkehren Sie als überwältigend negativ. Die meisten Benutzer reagieren nur, wenn die Anrufqualität schlechter befindet. Aus diesem Grund können RMC Berichte auf der Seite schlechter verzerrt angezeigt werden auch dann, wenn der Dienst Metriken gute sind. 


Sie können CQD verwenden, um einen Bericht über RMC Benutzerantworten und Beispielberichte sind in der Vorlage CQD enthalten. Sie sind nicht jedoch in diesem Handbuch ausführlich erläutert. Weitere Informationen zu RMC in Skype für Business Online und Richtlinien für die Schulung von Benutzern zum Vorführen nützliche RMC Antworten finden Sie unter in diesem [Blogbeitrag](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Kategorien von Qualität

Der Erfolg der operationalizing einer hohe Qualität und zuverlässigen bereitstellungs hängt von Ihrer Erstellen von betrieblichen Genehmigungsverfahren ab. Achten Sie insbesondere, besonders auf die drei Kategorien, die in der folgenden Abbildung dargestellt; Hierbei handelt es sich um den Fokus dieses Handbuchs:

-   **Netzwerk:** Audioqualität konzentriert sich auf die PCR Metrik, TCP-Verwendung, verkabelten und drahtlosen Subnetze, und identifizieren die Verwendung von HTTP-Proxys und VPN.

-   **Endpunkte:** Audiogeräte und der Clientversion (Skype für nur Unternehmen).

-   **Dienstverwaltung:** Dieser Kategorie besteht aus zwei Abschnitten:

    -   Zunächst wird Microsofts Verantwortung zu verwalten und Verwalten von Teams und Skype für Business Online-Dienste.

    -   Zweitens sind Aufgaben, die Ihre Organisation verwalten muss, um sicherzustellen, dass zuverlässigen Zugriff auf den Dienst, beispielsweise zum Erstellen von Informationen zu aktualisieren und Verwalten von Firewalls für neue Office 365-IP-Adressen, sobald Infrastruktur mit dem Dienst hinzugefügt wird.

![Die Kategorien von Qualilty in einer Organisation: service-Management, Endpunkte und im Netzwerk.](media/quality-of-experience-review-guide-image3.png)

_Abbildung 3 – wichtige Kategorien für Teams und Skype für Business Online-Bereitstellung_

Die folgende Grafik werden die Aufgaben erläutert, die Sie für jede Kategorie ausführen müssen. Es wird empfohlen, dass Sie diese Aufgaben einmal pro Woche mindestens ausgeführt.

Der ersten dieser Aufgaben Ausführung dauert aufwändiger als nachfolgende Iterationen, da viele dieser Kategorien erfordern, dass Sie Ihre Bereitstellungskonfigurationen auf Gültigkeit überprüfen. Nachdem Sie den Status aus, indem Sie die von die Ihnen definierten Ziele meeting erreicht haben, helfen diese Aufgaben Ihnen bei diesem Zustand verwalten.

#### <a name="service-management-tasks"></a>Service-Management-Aufgaben

In einer Cloud-First-Welt müssen Sie bestimmte Verwaltungsaufgaben Service zum Verwalten von hochwertigen benutzerumgebungen ausführen. Diese Aufgaben im Bereich von sicherstellen, dass ausreichend Bandbreite, um den Dienst zu erreichen, ohne eine Internetlinks, validieren, Dienstqualität (QoS) auf alle verwalteten Netzwerks Bereiche ist und – und schließlich – [Griff Office 365 IP-Bereiche auf Firewalls](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Netzwerkaufgaben

Es gibt zwei Kategorien von Netzwerk-Tasks: Zuverlässigkeit und Qualität. Zuverlässigkeit konzentriert sich auf Messen der Fähigkeit des Benutzers tätigen erfolgreich und in Verbindung bleiben. Qualität konzentriert sich auf die aggregierten Telemetrie vom Client des Benutzers, während und nach Beendigung des Anrufs an Teams und Skype für Business Online gesendet.

Wichtige Auswirkung auf die, Zuverlässigkeit Benutzerinteraktion hat, angegeben, beginnen bewerten und Untersuchen von diese Metriken vor Qualität.

#### <a name="endpoints-tasks"></a>Endpunkte Aufgaben

Die Hauptaufgabe in dieser Kategorie ist wird überprüft, welche Clientversionen Skype für Unternehmen ausgeführt werden, auf dem desktop Builds aus den letzten sechs Monaten, um sicherzustellen, dass Benutzer die Vorteile der kontinuierlichen Optimierungen versucht, der Skype für Business desktop Client abrufen. Darüber hinaus Dies vereinfacht die allgemeinen Verwaltungsaufgaben von Client und stellt ein einheitliches Benutzererlebnis.

Der anderen wichtige Bereich ist monitoring, welche Geräte in Ihrer Bereitstellung betroffen sind und die Verwendung von zertifizierte Geräte bieten die beste benutzerumgebung gesteuerter.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt sind, und durch die Azure Content Delivery Network automatisch aktualisiert, und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.


## <a name="using-the-reports"></a>Verwenden die Berichte

In diesem Abschnitt werden die Grundlagen der Arbeit mit CQD beschrieben. Anleitung erhält für den folgenden Themen:

-   Suchen die Mandanten-ID

-   Berichten über Teams im Vergleich zu Skype für Unternehmen

-   Zuerst im Vergleich zur zweiten Klassifikationen

-   Dimensionen und Measures Filter

-   Datenströme im Vergleich zu Anrufen

-   Gut, schlecht und nicht klassifizierte Anrufe

-   Erste Schritte mit CQD

-   Bearbeiten von Berichten in CQD

-   Filtern von Berichten in CQD

Ausführlicheren Schulungen und Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="tenant-id"></a>Mandanten-ID

Einige Berichte CQD erfordern, dass Sie einen Filter für Ihre Mandanten-ID einschließen Daran CQD Daten aggregiert ist federated Teilnehmer Telemetrie enthalten.
Obwohl dies wertvolle beim Analysieren der Anrufe schlechter Qualität Metriken nachweisen kann, erfordern Client- und Gerätefunktionen Berichte das Filtern von Daten an einen bestimmten Mandanten federated Teilnehmer Telemetrie ausgeschlossen. Wenn Sie Ihre Mandanten-ID nicht kennen, können Sie eine der folgenden Methoden verwenden, sie zu finden sind.

Erforderliche Berechtigungen

-   Globalen Administratorrolle

-   Skype für Business Administratorrolle

#### <a name="azure-ad-portal"></a>Azure AD-Portal

1.  Melden Sie sich bei des Microsoft Azure-Portals an:<https://portal.azure.com>

2.  Wählen Sie **Azure Active Directory**aus.

3.  Wählen Sie unter **Manage** **Eigenschaften**aus. Die Mandanten-ID wird in das **Verzeichnis-ID** angezeigt.

#### <a name="azure-powershell"></a>Azure PowerShell

1.  [Installieren des Microsoft Azure PowerShell Service-Management-Moduls](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Öffnen Sie ein Befehlsfenster Azure PowerShell und führen Sie das folgende Skript, indem Sie bei entsprechender Aufforderung Ihre Office 365-Anmeldeinformationen eingeben:  
    **Anmeldung-AzureRmAccount**

3.  Die Mandanten-ID wird in der Ausgabe aufgeführt.

#### <a name="skype-for-business-online-admin-center"></a>Skype für Business Online Admin Center

1.  Gehe zu<https://portal.office.com>

2.  Melden Sie sich mit Ihrer Organisation Administratorkonto eines Mandanten.

3.  Wählen Sie **Skype für Unternehmen** unter **Admin Center**aus.

4.  Die Mandanten-ID wird als **Organisations-ID** auf der Seite Willkommen aufgelistet.

#### <a name="skype-for-business-online-using-powershell"></a>Skype für Business Online mithilfe von PowerShell

1.  [Verbinden mit Skype für Unternehmen Online über die PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Führen Sie den folgenden Befehl aus:  
    **.Tenantid (Get-Cstenant)**

3.  Die Mandanten-ID wird als GUID angezeigt.

### <a name="teams-vs-skype-for-business"></a>Teams im Vergleich zu Skype für Unternehmen

CQD kann Teams und Skype für Business Telemetrie melden. Möglicherweise gibt es jedoch vorkommen, dass Sie einen Bericht betrachten Teams Telemetrie getrennt von Skype für Unternehmen entwickeln möchten.

#### <a name="summary-reports"></a>Zusammenfassungsberichte

Um die Seite Zusammenfassungsberichte betrachten nur Teams oder Skype für Unternehmen zu ändern, wählen Sie das **Produktfilter** Dropdown-Menü vom oberen Rand des Bildschirms, und wählen Sie dann das gewünschte Produkt aus.

![Screenshot des Dashboards Qualität aufrufen ein Dropdown-Menü die Option zum Filtern nach Arbeitslast mit widerspiegelt.](media/quality-of-experience-review-guide-image4.png)

_Abbildung 4: Auswählen eines Filters Produkt_

#### <a name="detailed-reports"></a>Ausführliche Berichte

Fügen Sie des Filters **Teams ist** mit dem Bericht hinzu, und legen Sie es auf True oder False, um einen detaillierten Bericht zu filtern. Weitere Informationen finden Sie unter [Bearbeiten Berichte](#editing-reports) weiter unten in diesem Abschnitt.

![Screenshot des Dashboards Qualität rufen Sie mit der Dateneinheit, die einen detaillierten Bericht hinzugefügt werden kann.](media/quality-of-experience-review-guide-image5.png)

_Abbildung 5: Hinzufügen eines Microsoft-Teams Filters in einem Bericht_

### <a name="dimensions-measures-and-filters"></a>Dimensionen und Measures Filter

Eine wohlgeformte CQD Abfrage enthält alle drei der folgenden Parameter:

-   **Dimension:** Wie soll ich auf die Daten von PivotTables.

-   **Measure:** Was ich melden möchten.

-   **Filter:** Wie sollen das Dataset zu reduzieren, die, das die Abfrage zurückgibt.

Eine andere Möglichkeit, dies ist eine Dimension ist der Grouping-Funktion, ein Measure befinden sich die Daten, die, denen ich interessant, und ein Filter ist wie ich möchte die Ergebnisse auf diejenigen zu beschränken, die für eine Abfrage relevant sind.

Ein Beispiel für eine Abfrage wohlgeformt ist "meinen Status schlechter Datenströme [Measure] durch Subnetz [Dimension] für das Erstellen von 6 [Filter]."

Weitere Informationen finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm).

Dimensionen, Measures und Filter für die Berichte in den CQD Vorlagen verwendet finden Sie im [Anhang](#CQD-training).

### <a name="first-vs-second"></a>Zuerst im Vergleich zu Sekunde 

Viele der Dimensionen und Measures in CQD werden als erste oder zweite klassifiziert.
CQD nicht Anrufer/angerufenen Felder verwenden – diese Waren umbenannte _ersten_ und _zweiten_ , da sind dazwischenliegende Schritte zwischen dem Anrufer und des angerufenen. Die folgende Logik legt fest, welcher am Datenstrom oder Anruf beteiligte Endpunkt als erster Endpunkt bezeichnet wird:

-   Zuerst wird immer Endpunkt eines Servers (Konferenzserver, Vermittlungsserver usw.), wenn ein Server in der Stream oder Anruf beteiligt ist.

-   Zweitens werden immer ein Clientendpunkt, wenn der Stream zwischen zwei Serverendpunkten ist.

-   Wenn beide Endpunkte den gleichen Typ, sind die Wahl, der zwischen dem ersten ist basiert auf internen Reihenfolge der Benutzer-Agent Kategorie. Damit wird eine konsistente Anordnung sichergestellt.

Weitere Informationen zum Bestimmen des ersten oder zweiten Endpunkts, wenn sie beide identisch sind finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream im Vergleich zu Anrufen

Sie verstehen des Unterschieds zwischen eines Anrufs und einem Stream ordnungsgemäß auswählen, welche Dimensionen oder Measures, die Sie in CQD angezeigt werden sollen.

**Stream:** Ein Datenstrom zwischen nur zwei Endpunkte vorhanden ist. Es ist nur ein Stream-Objekt für jede Richtung und zwei Datenströme sind erforderlich für die Kommunikation. Datenströme eignen sich für die Analyse der Gebäude oder Netzwerke. In einigen Fällen werden Anruf und Stream in den Namen (beispielsweise Anruf Setup Stream oder Anruf verworfen Stream) verwendet.
Diese werden weiterhin als einzelne Datenströme klassifiziert.

**Aufrufen:** Ein Anruf ist eine Gruppierung aller Streams aus allen Teilnehmern. Umfasst ein Anruf – mindestens – zwei Datenströme. Ein einzigen Aufruf müssen zwei Teilnehmern mit mindestens einem Stream-Objekts. Anrufe eignen sich für die Analyse der Trends über einen Zeitraum.

Weitere Anleitungen gibt an, ob die Dimension oder Measure eines Anrufs oder eines Stream-Objekts verweist finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Gut, schlecht und nicht klassifizierte Anrufe

Ein Aufruf ist entweder als gut, schlecht oder nicht klassifizierte kategorisiert. Betrachten wir kurz jeweils ausführlich behandelt.

**Gut oder schlecht:** Gespräch gut oder schlecht besteht aus einem Anruf, der einen kompletten Satz von Kriterien Service, enthält, für die ein vollständiger QoE-Bericht generiert wurde.
Bestimmen, ob ein Anruf gut oder schlecht ist wird beschrieben [Weiter oben in diesem Handbuch](#pcr).

**Nicht klassifizierte:** Ein nicht klassifizierter Anruf enthalten keine umfassende Auswahl an Service Metriken. Dies sind häufig kurze Anrufe – normalerweise weniger als 60 Sekunden – wobei Durchschnittswerte konnte nicht berechnet werden und ein QoE-Bericht wurde nicht generiert.

### <a name="access-cqd-online"></a>Access CQD Online

Sie können auf zwei Arten CQD zugreifen.

-   Wechseln Sie zu <https://cqd.lync.com>.

-   Wechseln Sie zu **Skype für Business Administrationscenter** \> **Extras**, und wählen Sie den Link zur CQD, wie unten dargestellt.

![Screenshot, der zeigt "Tools" in den linken Navigationsbereich und den Link zu "Skype für Business Online aufrufen Qualitätsdashboard" ausgewählt ausgewählt.](media/quality-of-experience-review-guide-image6.png)

_Abbildung 6 – zugreifen auf CQD über die Skype für Business Administrationscenter_

### <a name="getting-started"></a>Erste Schritte

Wenn Sie zuerst CQD durchsuchen, sehen Sie auf der Seite Zusammenfassung Berichte. Die meisten der Berichte in diesem Handbuch beschrieben sind benutzerdefinierte ausführliche Berichte. Erste Schritte mit der ausführliche Berichte, wählen **Zusammenfassung Berichte** am oberen Rand der Seite, und wählen Sie dann **Ausführliche Berichte**.

![Screenshot von der Qualitätsdashboard aufrufen Depcting der verschiedenen Arten von Berichten, die verfügbar sind.](media/quality-of-experience-review-guide-image7.png)

_Abbildung 7: Navigieren zum ausführliche Berichte_

Die ausführliche Berichte Seite in CQD sieht wie in der nachfolgenden Abbildung.

![Screenshot der Seite detaillierten Bericht in CQD und die verschiedenen Elemente, die einen Bericht bilden.](media/quality-of-experience-review-guide-image8.png)

_Abbildung 8: ausführliche Berichtsseite_

1.  Bereich "Zusammenfassung" zeigt Kontext für den Bericht ein, der auf der rechten Seite angezeigt wird.

2.  Sie können **Bearbeiten** im Bereich "Zusammenfassung" auf Bericht-Ebene-Eigenschaften (einschließlich y-Achse Höhe) festlegen auswählen.

3.  Die Breadcrumb-Leiste hilft Benutzern bei ihrer aktuellen Position in der Berichtshierarchie zu identifizieren.

4.  Berichte, die ist der untergeordneten Berichte, werden mit einer blauen Link angezeigt. Wenn Sie den Link auswählen, können Sie nach unten zu den untergeordneten Berichte anzeigen.

Zeigen Sie auf die Balkendiagramme und Trendlinien detaillierte Werte angezeigt. Zeigt der Bericht, den Fokus hat im Aktionsmenü: **Bearbeiten**, **Wenn Sie den Klon**, **Löschen**, **herunterladen**und **Berichtsstruktur exportieren**.

### <a name="editing-reports"></a>Bearbeiten von Berichten

Beim **Bearbeiten** eines Berichts im Menü Aktion auswählen, werden Sie Abfrage-Editor zu öffnen. Jeder Bericht wird durch eine Abfrage unterstützt. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Abfrage-Editor ist eine Benutzeroberfläche zur Bearbeitung diese Abfragen zusätzlich zu den Optionen für die Anzeige für den Bericht, wie in der folgenden Abbildung dargestellt.

![Screenshot der Seite detaillierten Bericht in CQD und die verschiedenen Elemente, die einen Bericht bilden, wenn der Bericht bearbeitet werden.](media/quality-of-experience-review-guide-image9.png)

_Abbildung 9: Bericht-Editors_

1.  Wählen Sie Dimensionen und Measures Filter im linken Bereich. Verweisen auf einen vorhandenen Wert zeigt eine Schaltfläche zum Schließen (**X**) Sie auswählen können, um den Wert zu entfernen.

    1.  Indem Sie die Dimension oder Measure auswählen, können Sie den Titel durch Bearbeiten im Feld **Titel** ändern. Sie können auch die Reihenfolge ändern, indem Sie die blaue nach oben oder nach unten weisenden Pfeil im oberen Bereich auswählen.

    2.  Auswählen (**+**) neben einer Überschrift Öffnet das Dialogfeld für eine neue Dimension, Measure oder Filter hinzufügen.

    3.  Geben Sie die ersten Buchstaben der Dimension, Measure oder Filter in der **Hier finden Sie eine** zum Filtern der Liste für die Suche einfacher dar.

2.  Der obere Ausschnitt zeigt Optionen zur Anpassung des Diagramms.

3.  Der Abfrage-Editor zeigt eine Vorschau des Berichts.

4.  Verwenden Sie das **Bearbeiten** am unteren Rand des Bildschirms zum Erstellen oder bearbeiten eine detaillierte Beschreibung des Berichts.

### <a name="filtering-reports"></a>Filtern von Berichten

Die bereitgestellten Vorlagen umfasst mehrere integrierte Abfragen und Filter im Bericht. In den folgenden Abschnitten wird beschrieben, die am häufigsten verwendeten Filter in allen Vorlagen verwendet.

#### <a name="cqd-filter"></a>CQD filter

Sie können die CQD Filter oder URL-Filter verwenden, um jedes Berichtsabfrage vorübergehend zu filtern. Der am häufigsten verwendete CQD Filter, den Sie verwenden ist zum Filtern von Berichten auszuschließende federated Teilnehmer Telemetrie. Es wird empfohlen, dass Sie diesen Filter Lesezeichen, damit es die Standardansicht zu. Ausschließen von föderierten Data aus CQD Berichte ist nützlich, wenn Sie sind Korrigieren von verwalteten Gebäude oder Netzwerken, in dem zusammengestellten Daten Ihres Berichts beeinflussen können.

Um einen Filter CQD in der Adressleiste des Browsers zu implementieren, fügen Sie die folgenden am Ende der URL:

/Filter/ [AllStreams]. [Zweiten Mandanten-Id] \|[IHRE MANDANTEN-ID hier]

**Beispiel:**  
https://cqd.lync.com/cqd/\#/1234567/2018-02/filter/[AllStreams]. [Zweiten Mandanten-Id] \|[TENANTID] & Mandanten = TENANTID

> [!NOTE]
> URL-Beispiel oben wird nur die visuelle Darstellung. Verwenden Sie die standardmäßige CQD Verknüpfung von <https://cqd.lync.com>.

#### <a name="query-filters"></a>Abfragefiltern

Abfragefiltern werden mithilfe des Bericht-Editors implementiert. Diese Filter werden verwendet, um die Anzahl von Datensätzen zurückgegebene CQD, daher minimieren Gesamtgröße des Berichts zu verringern. Dies ist insbesondere dann sinnvoll für nicht verwalteten Netzwerken herausfiltern.
Die unten aufgeführten Filter verwenden regulärer Ausdrücke (RegEx).

_Tabelle 3 - Abfragefilter_

| Filter               | Beschreibung          | Filter-Abfragebeispiel CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Leere Werte         | Einige Filter haben nicht die Option zum Filtern von leere Werte. Um leere Werte manuell zu filtern, verwenden Sie den Ausdruck leeren, und setzen Sie den Filter auf gleich oder ungleich, je nach Ihren Anforderungen.                                                                                                                             | Erstellen von Sekunde Name \< \> \^ \\s\*\$                       |
| Beliebte home Subnetze | Ohne eine Datei gültige Erstellen von verwalteten von nicht verwalteten Netzwerken trennen werden Heimnetzwerken in den Berichten einbezogen werden. Diese private Subnetze sind außerhalb des Bereichs des Steuerelements die und schnell aus einem Bericht ausgeschlossen werden. Beliebte home Subnetze, sind gemäß Definition in diesem Handbuch 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweite Subnetz \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Innerhalb im Vergleich zu außen   | Zum Filtern von Berichten für (inside) verwaltetem oder nicht verwaltetem (externe) verwendet. Die verwaltete CQD-Vorlage ist bereits vorkonfigurierten mit diesen filtern.                                                                                                                                                                                | Sekunde innerhalb Corp = innerhalb                               |

#### <a name="report-filters"></a>Filter im Bericht

Filter im Bericht werden durch einen Filter hinzufügen, mit dem gerenderten Bericht entweder im Bericht-Editor oder direkt mit dem Bericht implementiert. Die folgenden Berichte Filter werden in der Vorlage verwendet.

_Tabelle 4 – Filter melden_

| Filter     | Beschreibung                            | Beispiel für einen Filter CQD Bericht         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Beginnen Sie mit der Jahr zuerst, dann Monat. | 2017-10                           |
| Alphabetische | Filter für alle alphabetischen Zeichen. | [a-Z]                             |
| Numerische    | Filter für eine beliebige numerischen Zeichen.    | [0-9]                             |
| Prozentsatz | Filtert nach Prozentsatz.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importieren Sie die CQD-Vorlagen

Dieses Handbuch umfasst [zwei curated CQD Vorlagen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Diese Vorlagen die Verwendung von CQD beschleunigen und bieten Ihnen die Möglichkeit, schnell nutzen CQDs-Funktionen zu einer Beeinträchtigung der Benutzer Teams oder Skype Business wünschen. Die Vorlage alle Netzwerke optimiert gegenüber einem Gebäude entwickelt Datendatei, kann verwendet werden, während der Arbeit in Richtung sammeln und Hochladen von Erstellen von Informationen in CQD, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (. CQDX) in CQD Online**

1.  Wechseln Sie zu <https://cqd.lync.com>.

2.  Authentifizieren Sie mithilfe Ihrer Office 365-Administratoranmeldeinformationen ein.

> [!NOTE]
> Sie benötigen die Office 365 globaler Administrator Skype für Business Administrator oder Berichtleser-Rolle auf CQD zuzugreifen. 


3.  Wählen Sie im Menü **Zusammenfassung Berichte** am oberen Rand der Seite aus, und wählen Sie dann **Ausführliche Berichte**.

4.  Wählen Sie im Bereich "Zusammenfassung" **Importieren**aus. Besuchen Sie die CQDX Speicherort gespeichert, wählen Sie die Vorlage CQDX, und wählen Sie dann auf **Öffnen**.

5.  Nachdem die Vorlage hochgeladen wurde, wird ein Popup-Fenster Anzeigen der Meldung "Bericht Importvorgang war erfolgreich." Wählen Sie **OK.**

![Screenshot des ein Popup-Fenster, das dem Benutzer benachrichtigt, dass die Vorlage erfolgreich importiert wurde.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Wiederholen Sie die Schritte 4 und 5 für die zweite CQD-Vorlage.

> [!NOTE]
> Die Vorlagen CQD werden pro Benutzer importiert. Wenn weitere Benutzer den Bericht verwenden müssen, müssen sie anmelden und die Vorlagen in ihrer Instanz CQD importieren. 


## <a name="building-mapping"></a>Erstellen von Zuordnung

In einer Teams oder Skype für Business Online-Bereitstellung, sind alle Clients extern.
Die hat der Auswirkung, dass alle Clients sind standardmäßig gemeldeten als außerhalb in CQD Online, unabhängig davon, ob der Client eine interne Unternehmensnetzwerk verbunden wurde.

Wenn Sie die Anrufqualität verwenden, müssen Sie den Speicherort eines Clients kennen und, ob eine Verbindung mit einem zur Verwaltung oder ein Netzwerk hergestellt wurde Sie nicht verwalten – der Annahme, dass Sie nur Netzwerke verbessert werden können, können Sie verwalten.
Hochladen von Netzwerk- und Erstellen von Informationen zu CQD Online, können Sie CQD, um zu bestimmen, ob ein Client zu einem internen Netzwerk im Unternehmen/verwaltet oder mit einem externen/nicht verwaltete Netzwerk verbunden wurde.

### <a name="building-data-file-structure"></a>Erstellen von Daten-Dateistruktur

Das Format der Datei, die Sie hochladen muss die folgenden Anforderungen, übergeben die Überprüfung vor dem Hochladen erfüllen.

-   Die Datei muss eine TSV-Datei, was bedeutet, dass für jede Zeile jeder Spalte durch ein Tabstoppzeichen getrennt ist, oder eine CSV-Datei, in der jede Spalte durch ein Komma getrennt ist.

-   Die Datei darf nicht größer als 50 MB sein.

-   Der Inhalt der Daten Datei *Tabellenüberschriften nicht berücksichtigt*. Die erste Zeile der Datendatei muss mit anderen Worten, realen Daten, nicht Spaltenüberschriften wie "Netzwerk." sein.

-   In jeder Spalte kann der Datentyp nur eine Zeichenfolge, eine Zahl oder der boolesche Datentyp sein. Wenn der Datentyp Zahl ist, muss der Wert einen numerischen Wert; Wenn es Bool ist, muss der Wert 0 oder 1.

-   Für jede Spalte ist der Datentyp String, die Daten können leer sein (jedoch weiterhin durch eine entsprechende Trennzeichen, die ein Tabulatorzeichen oder ein Komma getrennt werden müssen). Dadurch wird dem Feld eine leere Zeichenfolge zugewiesen.

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

Supernetting, so genannte Classless Inter-Domain Routing (CIDR), können Sie anstelle der einzelnen Subnetze definieren. Eine *Supernetting* ist eine Kombination von mehrere Subnetze, die ein routing Präfix freigeben. Anstatt einen Eintrag für jedes Subnetz, können Sie die Supernetz/CIDR-Adresse verwenden. Supernetting wird unterstützt, aber es wird nicht empfohlen, dessen Verwendung.

Beispielsweise Contoso marketing erstellen die folgenden Subnetze besteht:

-   10.1.0.0/24 – Erdgeschoss

-   10.1.1.0/24 – zweiter Stock

-   10.1.2.0/24 – Dritter Stock

-   10.1.3.0/24 – vierten floor

Anstatt einen Eintrag für jedes Subnetz, können die Supernetz/CIDR-Adresse – in diesem Beispiel 10.1.0.0/22.

-   Netzwerk = 10.1.0.0

-   Netzwerk-Bereich = 22

Hier sind einige Punkte zu berücksichtigen sind vor der Implementierung von Supernetting:

-   Supernetting weniger Zeit voraus, aber es geht aber vom Umfang der Daten zu reduzieren. Nehmen wir an, dass ein Qualität Problem büroumzüge Subnetz 200.1.2.0 vorhanden ist. Wenn Sie Supernetting implementiert, werden nicht Sie wissen, wo sich das Subnetz im Gebäude befindet oder welche Art von Netzwerk (beispielsweise eine Übungseinheit) ist. Wenn Sie hatte definiert alle Subnetze für ein Gebäude und Floor Standortinformationen hochgeladen, würden Sie diese Unterscheidung finden Sie unter sein.

-   Es ist wichtig, um sicherzustellen, dass die Supernetz/CIDR-Adresse richtig ist und unerwünschte Subnetze abfangen nicht zur Verfügung.

-   Supernetting kann in einer Zuordnung erstellen von mit 8-Bit-Version auf 28-Bit-Maske verwendet werden.

-   Es ist häufig 192.168.0.0 in Daten suchen. Für viele Organisationen bedeutet dies, dass der Benutzer zu Hause ist. Für andere ist dies das IP-Adressschema für eine Zweigstelle. Wenn Ihre Organisation Büros, die diese Konfiguration verwenden verfügt, fügen Sie keine es in der Datei zum Erstellen von unverändert schwierig home und internen Netzwerken mithilfe von gemeinsamen Subnetze unterscheiden.

> [!IMPORTANT]
> Der Netzwerkbereich kann verwendet werden, um eine Supernetting darzustellen. Erstellen alle neuen Daten Dateiuploads wird für überlappenden Bereiche überprüft werden soll. Wenn Sie eine Datei zum Erstellen von zuvor hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und Hochladen erneut aus, um alle überlappt identifizieren und beheben Sie das Problem. Alle Überlappung in zuvor hochgeladenen Dateien möglicherweise falschen Zuordnungen von Subnetzen zu Gebäude in den Berichten. 


#### <a name="vpn"></a>VPN

Die Daten Quality of Experience (QoE), die Clients zu Office 365 senden – wobei stammende CQD Daten aus ist also – ein VPN-Flag enthält. Dieses Kennzeichen nutzt VPN-Anbieter reporting Windows, dass die VPN-Netzwerkadapter registriert einen RAS-Adapter ist jedoch. Nicht alle VPN-Anbieter registrieren ordnungsgemäß RAS-Adapter. Aus diesem Grund können Sie nicht die integrierte VPN-Abfragefilter verwenden können. Es gibt zwei Ansätze für die Einbindung der VPN-Subnetze im Gebäude Informationsdatei.

-   Definieren Sie einen **Netzwerkname** , indem Sie mit dem Text "VPN" in diesem Feld für VPN-Subnetze.

![Screenshot eines Berichts in der aufrufen Qualität-Dashboard, das zum Erstellen einer VPN-Subnetz definiert](media/quality-of-experience-review-guide-image10.png)

_Abbildung 10: Netzwerkname mit VPN_

-   Definieren Sie einen **Namen erstellen** , indem Sie mit dem Text "VPN" in diesem Feld für VPN-Subnetze.

![Screenshot eines Berichts im Aufrufen Qualität-Dashboard, die definiert, wie eine Definition Erstellen von erstellen, die ein VPN-Subnetz umfasst.](media/quality-of-experience-review-guide-image11.png)

_Abbildung 11: VPN verwenden Sie zum Erstellen von Namen_

> [!IMPORTANT]
> Bestimmte VPN-Implementierungen meldet nicht genau Subnetzinformationen. In diesem Fall in Ihre Berichte, empfehlen wir, wenn Sie die Datei zum Erstellen von anstelle eines Eintrags für das Subnetz ein VPN Subnetz hinzufügen fügen Sie separate Einträge für jede Adresse als ein separates 32-Bit-Netzwerk im VPN-Subnetz hinzu. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Beispielsweise müssen Sie anstelle einer Zeile für 172.16.18.0/24, 253 Zeilen, mit einer Zeile für jede Adresse aus 172.16.18.1/32 über 172.16.18.254/32, inklusive.


> [!NOTE]
> VPN-Verbindungen bekanntermaßen die Netzwerkschnittstelle unter Umständen nicht richtig wie verkabelt, wenn die zugrunde liegende Verbindung Internet ist kabellos. Beim Betrachten der Qualität über VPN-Verbindungen können nicht vorausgesetzt, dass der Verbindungstyp genau identifiziert wurde.

### <a name="uploading-building-information"></a>Informationen zum Erstellen von hochladen

Das Dashboard CQD Zusammenfassung Berichte umfasst eine Seite **Mandanten Daten hochladen** , durch Auswählen des **Mandanten Datenupload** Link-Tags in der oberen rechten Ecke (Design für das Zahnradsymbol) zugegriffen. Auf dieser Seite wird für Administratoren ihre eigenen Informationen wie die Zuordnung von IP-Adresse und geografische Informationen, zuordnen jeder drahtlosen Zugriffspunkt und die MAC-Adresse, hochladen und so weiter.

1.  Wechseln Sie zu Online CQD, indem Sie auf <https://cqd.lync.com>.

2.  Wählen Sie in der oberen rechten Ecke der Zahnradsymbol aus, und wählen Sie auf der Seite **Zusammenfassung Berichte** **Mandanten Hochladen von Daten** .

![Screenshot eines Dialogfelds im Dashboard angezeigt wird, während Daten hochgeladen werden Qualität aufrufen.](media/quality-of-experience-review-guide-image12.png)

_Abbildung 12 - Menü Mandanten Daten hochladen_

1.  Alternativ ist dies Ihre zum ersten Mal CQD besuchen, werden Sie aufgefordert, Erstellen von Daten hochzuladen. Sie können **Jetzt hochladen** , navigieren zur Seite **Mandanten Datenupload** schnell auswählen.

![Screenshot des Banner in das Aufrufen Qualität-Dashboard, das einen Benutzer das Erstellen von Datenupload benachrichtigt.](media/quality-of-experience-review-guide-image13.png)

_Abbildung 13: Erstellen von Daten hochladen banner_

1.  Wählen Sie **Durchsuchen** , um eine Datendatei auszuwählen, auf der Seite **Mandanten Hochladen von Daten** .

2.  **Startdatum** Geben Sie an, nach dem Auswählen einer Datendatei, und geben Sie optional ein Enddatum.

3.  Nach dem **Startdatum**auswählen, wählen Sie auf die Datei in die CQD hoch **Hochladen** . <br><br>Bevor Sie die Datei hochgeladen wurde, wird es überprüft. Wenn die Überprüfung fehlschlägt, wird eine Fehlermeldung angezeigt anfordern, dass Sie die Datei zu korrigieren. Die folgende Abbildung zeigt einen Fehler auftritt, wenn die Anzahl der Spalten in der Datendatei nicht korrekt ist.

![Screenshot eines Dialogfelds in das Aufrufen Qualität-Dashboard, das eine Fehlermeldung beim Importieren von Daten zum Erstellen von beschreibt.](media/quality-of-experience-review-guide-image14.png)

_Abbildung 14: Building Fehler beim Upload von Daten_

4.  Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.

> [!NOTE]
> Es kann zum Abschließen der Verarbeitung der Datei zum Erstellen von bis zu vier Stunden dauern. <br><br> Wenn Sie eine Datei zum Erstellen von bereits hochgeladen haben und müssen Subnetze hinzu, die möglicherweise entgangene oder ausgeschlossen werden, wurden die ursprüngliche Datei ändern, indem Sie die neue Subnetze hinzufügen, entfernen Sie die aktuelle Datei und wieder neu bearbeitete Datei hochladen. Es kann nur eine aktive Erstellen von CQD-Datendatei. 

### <a name="missing-subnets"></a>Fehlende Subnetze

Nach dem Erstellen von Informationen für verwaltete Netzwerke hochladen, sollte jeder verwalteten Netzwerks eine Zuordnung erstellen. Jedoch nicht immer die Groß-/Kleinschreibung; in der Regel werden einige Subnetze nicht eingehalten. In diesem Abschnitt wird das Überprüfen dieser fehlenden Netzwerke behandelt.

Wechseln Sie zur Seite **Ausführliche Berichte** in CQD Online, und navigieren Sie zu der **Fehlende Subnetz Bericht** in die CQD Vorlagen enthalten. Dies stellt alle Subnetze mit 10 oder mehr audio-Streams, die nicht im Gebäude definiert sind-Datendatei. Stellen Sie sicher, dass es keine verwalteten Netzwerke in dieser Liste sind. Wenn Subnetze nicht vorhanden sind, aktualisieren Sie die ursprünglichen Erstellen von Daten Datei und erneutes Hochladen auf CQD.

> [!IMPORTANT]
> Sie müssen Ihre Mandanten-ID als Abfragefilter für die **Zweite Mandanten-ID** für diesen Bericht Filtern des Berichts, um nur die Daten des Unternehmen Mandanten anzuzeigen hinzufügen. Andernfalls wird der Bericht federated Subnetze anzeigen.

> [!NOTE] 
> Achten Sie darauf, dass Berichtsfilter Monat-Jahr mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den Filter **Monat-Jahr** -Bericht, um den neuen Standardmonat zu speichern.                                                  |

![Bericht mit Subnetze in der Datei CQD Erstellen von nicht enthalten, die Verwendung anzeigen.](media/quality-of-experience-review-guide-image15.png)

_Abbildung 15: Erstellen von Bericht fehlt_

## <a name="reliability-investigations"></a>Zuverlässigkeit Untersuchungen

Der erste Schritt zum Verbessern der Qualität ist den Status der audiozuverlässigkeit in der gesamten Organisation bewerten. Da audiozuverlässigkeit entscheidend für eine positive Benutzeroberfläche zur Verfügung steht, starten wir mit den zwei Komponenten, die Zuverlässigkeit messen:

1.  **Aufrufen Setupfehler:** Sitzung konnte nicht hergestellt werden.

2.  **Rufen Sie die Drop-Fehler:** Sitzung wurde eingerichtet und unerwartet beendet

In diesem Abschnitt werden Methoden zum Untersuchen Sie beide Bereiche behandelt.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt. Die Beschreibung der einzelnen Berichts Weitere Informationen finden.


### <a name="call-setup"></a>Verbindungsaufbau

Priorisieren Sie korrigieren von Setup anruffehlern in diesem Bereich zuerst, da diese Fehler erhebliche negative Auswirkungen auf die Benutzeroberfläche vorhanden ist.

Zunächst die Bewertung des Prozentsatz der gesamten Anruf Setupfehler für die Organisation der Überprüfung, und klicken Sie dann priorisieren Bereiche der Untersuchung basierend auf den höchsten Prozentsatz von erstellen oder im Netzwerk.

#### <a name="call-setup-failures-overall"></a>Rufen Sie allgemeine Setupfehler

In diesem Diagrammbericht zeigt die Gesamtsumme der erfolgreichen Aufruf einrichten, und rufen Setupfehler über einen Zeitraum. Zeigen Sie auf eine der Spalten auf die einzelnen Werte, anzuzeigen, wie in der folgenden Abbildung dargestellt.

![Screenshot eines Diagramms, das zeigt, Prozentsatz der Audio aufrufen Stream Fehler bei der Installation](media/quality-of-experience-review-guide-image16.png)

_Abbildung 16 - Audiozuverlässigkeit - Anruffehlern Stream Setup_

##### <a name="analysis"></a>Analyse

In diesem Bericht werden Ihrer Organisation Audioanruf-Setup-Syntax und Fehler über einen Zeitraum angezeigt. Mithilfe dieses Berichts können Sie die folgenden Fragen beantworten und Ihre weitere Vorgehensweise bestimmen:

1.  Was ist der Prozentsatz der gesamten Anruf Setup Fehler für den aktuellen Monat?

2.  Ist insgesamt Anruf Setup Fehler Prozentsatz unter oder über die Metrik definierten Ziel?

3.  Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Ausfall Trend erhöhen, steady, oder verringern?

Die Informationen in diesem Bericht informiert die Geschichte des wie oft Ihrer gesamten Anruf Installationen in Ihrer Organisation ein Fehler auftritt.

Selbst wenn der vorherigen Antworten Zeit in Anspruch nehmen die untersuchen Weitere mithilfe der enthaltenen untergeordneten Berichte für einzelne Gebäude oder Netzwerke, die möglicherweise Remediation gesucht. Zwar die Fehlerrate insgesamt unterhalb der Ziel-Metrik oft die Fehlerraten für eine oder mehrere Gebäude oder Netzwerke befinden sich über die Metrik und-Wartung benötigen.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Rufen Sie Fehler bei der Installation auf, indem Sie erstellen und Subnetz 

Dieser Tabellenbericht wird verwendet, zu ermitteln und isolieren alle Gebäude oder Netzwerke, die Remediation benötigen.

> [!NOTE]
> Achten Sie darauf, dass Berichtsfilter Monat-Jahr mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den Filter **Monat-Jahr** -Bericht, um den neuen Standardmonat zu speichern.


![Meldet, dass die Listen Anruf Setup Gründe, erstellen, Netzwerk und Subnetz pro Monat organisiert.](media/quality-of-experience-review-guide-image17.png)

_Abbildung 17: Audio Setupfehler durch die Erstellung oder Subnetz_

##### <a name="remediation"></a>Wartung 

Konzentrieren Sie Ihre Remediation auf Gebäude oder Subnetze abgerufen, die die größte Lautstärke der Fehler Sie zuerst haben, da dies Auswirkungen auf die Benutzeroberfläche maximieren und Ihnen dabei helfen, um schnell die Organisationseinheit anruffehlern Setup zu reduzieren.
Die folgende Tabelle enthält die zwei Gründe für die Setup-Fehler beim Aufrufen von CQD gemeldet.

_Tabelle 6 – Gründe für Setup Anruffehlern_

| Rufen Sie die Ursache für Fehler bei der Installation                       | Typische Ursache                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fehlende Firmware Tiefe Paket Prüfung Ausnahmeregel | Gibt an, dass Netzwerkgeräte entlang des Pfads der Medienpfad daran gehindert, aufgrund von Tiefe Paket Prüfung Regeln hergestellt wird. Dies ist wahrscheinlich durch die Firewall-Regeln wird nicht ordnungsgemäß konfiguriert. In diesem Fall der TCP-Handshake war erfolgreich, aber der SSL-Handshake nicht.               |
| Fehlende Firmware IP-Block Ausnahme-Regel               | Gibt an, dass Netzwerkgeräte entlang des Pfads der Medienpfad daran gehindert, mit dem Office 365-Netzwerk hergestellt wird. Dies kann aufgrund von Proxy oder der Firewall-Regeln wird nicht Gewährung des Zugriffs für IP-Adressen und Ports für Teams und Skype für Business-Datenverkehr verwendet, um ordnungsgemäß konfiguriert sein. |

Nun, wie Sie Ihre Remediation beginnen, können Sie sich in einem bestimmten Gebäude oder Subnetz konzentrieren. Wie in die obigen Tabelle gezeigt wird, werden diese Probleme aufgrund der Firewall oder der Proxyserver Konfigurationen. Überprüfen Sie die Optionen in der folgenden Tabelle für Remediation Aktionen.

_Tabelle 7: nächste Schritte für Anruf Setup Fehler-Wartung_

| Wartung           | Anleitung     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurieren von firewall(s) | Arbeiten mit Ihrem Netzwerkteam, und überprüfen Sie Ihre Konfiguration Firewall(s) anhand [der Liste der Office 365-IP-Adresse](https://aka.ms/o365ips). Stellen Sie sicher, dass die [Medien Subnetze](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) und Ports in der Firewall-Regeln enthalten sind. Stellen Sie sicher, dass die erforderlichen TCP- und UDP-Ports in der Firewall geöffnet werden. Media bevorzugt UDP über TCP an. TCP gilt ein Failback-Protokoll.<br><ul><li>**TCP:** -port 443</li><li>**UDP:** 3478 – 3481 ports</li><ul> |
| Vergewissern Sie sich                | Nutzen Sie die [Microsoft Network Assessment-Tool](https://www.microsoft.com/download/details.aspx?id=53885) aus, um die Konnektivität von der betroffenen Gebäude oder Subnetz mithilfe der Konnektivität Kontrollkästchen-Funktion zu überprüfen.    |


### <a name="call-drop"></a>Rufen Sie die drop

Im Gegensatz zu anruffehlern-Setup, ist kein Code Grund an, warum Fehler abgebrochen aufgetreten ist, die einer bestimmten Problemursachen isolieren erschwert. Verworfene Anrufe, um eine bessere Ursachenanalyse einen abgeleiteten Ansatz bereitzustellen. Korrigieren von Bereichen des Zinsen für Audio und fördern der Verwendung von zertifizierte Geräte für Teams und Skype für Business Patchen von Clients, würden Sie abgelegten anruffehlern so lehnen Sie erwarten.

#### <a name="call-drop-failures-overall"></a>Rufen Sie die Drop-Fehler insgesamt

In diesem Diagrammbericht zeigt die Gesamtsumme der Audiostreams insgesamt Audiostreams gelöscht, und insgesamt Stream getrennt Prozentsatz. Zeigen Sie auf eine der Spalten zur Anzeige der Werte wie in der folgenden Abbildung dargestellt.

![Screenshot des ein Diagramm mit Prozentsatz der Audio aufrufen Datenströme gelöscht.](media/quality-of-experience-review-guide-image18.png)

_Prozentsatz der Abbildung 18 - insgesamt Anruf abgelegten Fehler_

##### <a name="analysis"></a>Analyse

Der Diagrammbericht zeigt Verwendung und Fehlern Ihrer Organisation über einen Zeitraum im Zusammenhang mit setzt aufrufen. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist der aktuelle Anruf insgesamt abgelegten Prozentsatz?

2.  Ist der Prozentsatz insgesamt Drop unterhalb der definierten Ziel Metrik?

3.  Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Ausfall Trend erhöhen, steady, oder verringern?

Die Informationen in diesem Bericht kann anweisen, die Geschichte des wie oft Ihrer gesamten Anruf setzt in Ihrer Organisation ausgeführt werden.

Antworten auf die obigen Fragen unabhängig nehmen die Zeit, überprüfen Sie die Verwendung der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Remediation. Zwar die Drop Gesamtrate unterhalb der Ziel-Metrik oft die Drop-Rate für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und-Wartung benötigt.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Rufen Sie Drop-Fehlern auf, indem Sie erstellen oder Subnetz

Fehler in dieser Tabellenbericht anzugeben, dass der Anruf wurde unerwartet gelöscht und eine negative Benutzeroberfläche zur Verfügung führte. Es gibt zwei-Berichte in der Vorlage, eine für Untersuchen von Konferenz- und das andere für zwei Teilnehmern enthalten.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.


![Meldet, dass die Anzahl von Listen und Prozentsatz Initiale Anrufe erstellen, Netzwerk und Subnetz pro Monat organisiert.](media/quality-of-experience-review-guide-image19.png)

_Abbildung 19 – Audio Anruf abgelegten Fehler durch Erstellen oder Subnetz_

##### <a name="remediation"></a>Wartung

Mit der vorstehenden Tabellenbericht können Sie jetzt "Hotspot" im verwalteten Netzwerk isolieren, in dem Anruf über die definierten Ziel Metrik vorkommen. Konzentrieren Sie sich auf Gebäude oder Netzwerken, in denen die Anzahl der höchste insgesamt Stream Sie zuerst am stärksten beeinträchtigt müssen, Ihre Remediation-Maßnahmen.

Häufige Ursachen für Anruf Ansätzen:

-   Klicken Sie unter bereitgestellte Netzwerk oder Internet Ausgang

-   Keine QoS auf eingeschränkte Netzwerke konfiguriert ist

-   Ältere Clientversionen

-   Verhalten der Benutzer

Nachdem Sie Hotspot erkennen, können Sie [Analytics aufrufen,](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) um Benutzer in das Gebäude für bestimmte Probleme an weiteren Überprüfung nutzen. Anruf Analytics PII-Daten enthält und kann deshalb hilfreich, um weitere mögliche Gründe für den Anruf setzt.

Unabhängig von der nächste Schritt ist es ratsam, dem Helpdesk benachrichtigen, dass es sich bei Auftreten eines Problems mit einem bestimmten Gebäude oder Subnetzen. Auf diese Weise können schnell reagieren auf eingehende Anrufe und Benutzer effizienter selektieren. Gekennzeichnete Benutzer können dann wieder an das Entwicklungsteam zur weiteren Untersuchung gemeldet werden.

Die folgende Tabelle enthält einige allgemeinen Methoden zum Verwalten und Warten von Anruf setzt.

_Tabelle 9: nächste Schritte für Anruf drop-Wartung_

| Wartung                              | Anleitung     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Netzwerk/internet                         | Nun, dass Sie wissen, welche Building betroffen ist, arbeiten Sie mit Ihrem Netzwerkteam Bandbreite an das Gebäude, um festzustellen, ob Probleme mit übermäßiger überwachen. Wenn das Problem in Bezug auf Überlastung des Netzwerks ermittelt werden, sollten Sie die zunehmende Bandbreite für das Gebäude. <br><br>**QoS:** Wenn einer steigenden Bandbreite unmöglich oder kostspielig ist, sollten Sie die Implementierung der QoS. Dadurch wird sichergestellt, dass Media-Pakete im verwalteten Netzwerk oben nicht Mediendatenverkehr priorisiert werden. Auch wenn es gibt keine klare Hinweise, dass die Bandbreite Ursache ist, sollten Sie diese Lösungen:<br><ul><li>[Microsoft-Teams QoS-Anweisungen](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype für Business QoS-Anweisungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Führen Sie eine Netzwerk-Bereitschaft:** Eine Netzwerk-Bewertung enthält Details zur Nutzung der erwarteten Bandbreite, wie bewältigen Bandbreite und Netzwerk ändert, und Netzwerke Methoden für Teams und Skype für Unternehmen empfohlen. Verwenden der obigen Tabelle als Quelle, müssen Sie eine Liste von Gebäude oder Subnetze, die eignen sich für eine Bewertung sind. <br><ul><li>[Microsoft-Teams, Netzwerk-Bereitschaft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype für Business Netzwerk Bereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Tool zur Bewertung der Microsoft Network:** Verwenden Sie dieses Tool für einen einfachen Test der Leistung des Netzwerks, um zu bestimmen, wie gut das Netzwerk für eine Teams ausführen würden oder Skype für Business Online Anruf. Das Tool können Sie die Leistung eines Subnetzes bewerten und überprüfen die Bereitschaft des Netzwerks gegen Microsoft Leistung [Anforderungen](https://aka.ms/performancerequirements).<ul><li>[Laden Sie das Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Clients (Skype für Unternehmen nur Online) | Einige ältere Clients wissen müssen, werden Probleme mit der Zuverlässigkeit Media dokumentiert. Überprüfen Sie die aufrufen Analytics-Berichte aus mehreren betroffenen Benutzer, oder erstellen Sie einen benutzerdefinierten Bericht der Clientversion-Tabelle in CQD in bestimmten Gebäude oder Subnetze mit Fehler insgesamt aufrufen abgelegten % Measure gefiltert. Diese Informationen helfen Ihnen beim verstehen, ob eine Beziehung zwischen Anruf setzt in dieser bestimmten Gebäude und eine bestimmte Version des Clients vorhanden ist.                                                                                                                                                              |
| Geräte                                  | Die meisten Gerätefehler sind aufgrund der Geräte, die für Teams oder Skype für Unternehmen ausgewiesen werden nicht verwenden. Fehler verwenden normalerweise das Format der integrierten Lautsprecher oder Mikrofone, die verwendet werden, oder Earbud/Mikrofon Kombinationen, die mit dem audio 3,5 mm-Anschluss auf einem Gerät verbunden sind. Aktuelle Empfehlung von Microsoft besteht darin, dass alle Benutzer, die auftreten, setzt aufrufen – oder schlecht Anrufe im Allgemeinen – und werden mithilfe von integrierten Geräte oder Treiber werden sollte eine [certified Kopfhörer oder eines Freisprechtelefons](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)bereitgestellt. |
| Verhalten der Benutzer                            | Wenn Sie feststellen, dass weder Netzwerk, Geräte oder Clients behoben werden, sollten Sie ansprechender [Meine Advisor](https://aka.ms/myadvisor) Anleitung bei der Entwicklung einer Strategie für die Einführung, um Benutzer informieren, wie Sie bewährte beitreten und Besprechungen zu beenden. Ein intelligenter Teams und Skype-Benutzer haben eine höhere benutzerfreundlichkeit für alle Teilnehmer in der Besprechung zur Folge. Ein Benutzer, der ihren Laptop in den Energiesparmodus (von der Abdeckung schließen) versetzt, ohne zu verlassen der Besprechung werden als ein unerwarteter Aufruf Drop klassifiziert werden.     |

## <a name="quality-investigations"></a>Qualität Untersuchungen

Im nächste Schritt den Zustand der Audioqualität über die Bereitstellung bewerten ist Audio schlechter aufrufen Verhältnis (PCR), TCP und Proxy Verwendung untersuchen. Es ist wichtig, denken Sie daran, dass CQD Daten bestimmte Ursache nicht enthalten, aber Sie stattdessen wahrscheinlich Problembereiche zu Beginn einer gemeinsame Unterhaltung mit der entsprechenden Teams für Abhilfemaßnahmen bietet.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt. Die Beschreibung der einzelnen Berichts Weitere Informationen finden. 


### <a name="investigate-call-quality"></a>Überprüfen der Anrufqualität

Der Gesamtprozentsatz PCR wird hauptsächlich verwendet, um anzugeben, ob die Organisation definierten audio metrischen Ziele erreicht. Es ist wichtig, beachten Sie, dass, auch wenn der Gesamtprozentsatz im Ziel ist, einige Subnetze oder Gebäuden möglicherweise nicht die definierten Ziele erfüllen und daher weiteren Untersuchung erfordern. Beispielsweise ist der Organisationseinheit audio PCR Prozentsatz 3 Prozent in möglicherweise Dezember, die erfüllt die Beispiel-Ziel, die bestimmte Gebäude weiterhin schlechte Erfahrungen, je nach der Verteilung dieser 3 Prozent haben.

#### <a name="overall-organizational-poor-call-percentage"></a>Insgesamt Organisationseinheit Anrufe schlechter Qualität Prozentsatz

Informationen zum Bewerten der Gesamtprozentsatz schlechter Anrufe für die Organisation verwenden Sie die allgemeine Qualität Analysediagrammbericht.

![Screenshot des ein Diagramm mit Prozentsatz der Anrufe schlechter Qualität](media/quality-of-experience-review-guide-image20.png)

_Abbildung 20 – Audioqualität - insgesamt_

##### <a name="investigation"></a>Untersuchung

Der Diagrammbericht zeigt die Verwendung und PCR Ihrer Organisation über einen Zeitraum. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist der gesamte PCR für den aktuellen Monat?

2.  Ist die PCR unterhalb der definierten Ziel Metrik?

3.  Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Ausfall Trend erhöhen, steady, oder verringern?

Antworten auf die obigen Fragen unabhängig Zeit in Anspruch nehmen die mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die weiteren Untersuchung möglicherweise untersuchen. Zwar die allgemeine PCR unterhalb der Ziel-Metrik häufig die PCR für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und weiteren Untersuchung benötigt.

#### <a name="audio-quality-overall"></a>Allgemeine Audioqualität

Es gibt zwei Bericht Strukturen in die Vorlagen für Audioqualität, einen für Untersuchen von Konferenz- und das andere für Anrufe mit zwei Teilnehmern enthalten. Für die Zwecke der Qualität Behebung versteht genauer identisch, damit wir hier auf Live Meeting konzentrieren können. Verbesserungen bei der Konferenz Qualität wirkt sich auch positiv auf zwei Teilnehmern die Anrufqualität aus. Berichte sind auch anzeigen, die Audioqualität für Konferenzen und zwei Teilnehmern von verkabelt und Wi-Fi enthalten.

> [!NOTE]
> Untersuchen von schlechter Gesprächen mit zwei Teilnehmern ähnelt dem Untersuchen von Telefonkonferenzen. Die Aufgabe wird zum Identifizieren von Gebäude oder Subnetze, die niedrigste Qualität überprüfen, ob es ein Muster schlechter Anrufe mit einem anderen Gebäude oder Subnetz liegt. 

![Screenshot der die Audioqualität - Webkonferenz-Bericht im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image21.png)

_Abbildung 21 – Audioqualität - Konferenzen_

##### <a name="investigation"></a>Untersuchung

Der Diagrammbericht zeigt Konferenzen oder Usage mit zwei Teilnehmern und PCR in Ihrer Organisation über einen Zeitraum. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist der gesamte PCR für den aktuellen Monat?

2.  Ist die PCR unterhalb der definierten Ziel Metrik?

3.  Ist PCR schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Trend PCR erhöhen, steady, oder verringern?

Antworten auf die obigen Fragen unabhängig Zeit in Anspruch nehmen die mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Untersuchung untersuchen. Zwar die allgemeine PCR unterhalb der Ziel-Metrik oft die PCR für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und-Wartung benötigt.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Schlechte Audiostream durch Erstellen und Subnetz

In diesem Tabellenbericht finden Sie zusätzliche Einblick in was beigetragen an, das die Anrufe als schlecht klassifiziert und trägt dazu bei, um Hotspot im verwalteten Netzwerk zu isolieren.

Details der Verbindung unterscheidet zwischen verkabelt und Wi-Fi und Jitter und Paketverlust Round-Trip Zeitmaßeinheiten (Zeit) enthält. Ein ähnlichen Bericht auch unter der zwei Teilnehmern Berichte vorhanden ist, und wird verwendet, um zwei Teilnehmern Anrufe in Ihrem verwalteten Netzwerk zu isolieren.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern. 

> [!TIP]
> Allgemeine Heimnetzwerken sind schwieriger zu Ursachenanalyse aufgrund der weit verbreitete Verwendung. Ein separater Bericht, der die IP-Adresse Firewall verwendet wurde hinzugefügt, um die Vorlage alle Netzwerke mit Korrigieren von Büros unterstützen, die gängigen Netzwerke verwenden.

![Bericht, der Verbindungstypen, Transporttypen und PCR größer als 3 % zusammen mit verschiedenen Gründen schlechter Qualität erstellen, Netzwerk und Subnetz pro Monat geordnet aufgeführt sind.](media/quality-of-experience-review-guide-image22.png)

_Abbildung 22 - Zusammenfassung durch Erstellen von schlechter Audiostream- und Subnetz Konferenzen_

##### <a name="remediation"></a>Wartung

Netzwerke mit der größten Menge der Audiostreams, da dies Auswirkungen maximieren und zur Verbesserung des Benutzers Hilfe schnell Erfahrung oder Kenntnisse konzentrieren Ihre Remediation auf Gebäude. Verwenden Sie die Jitter, Paketverlust und Maßangaben von Zeit um zu verstehen, was die Qualität der Anrufe schlechter Qualität beitragen wird. Es ist möglich, mehr als ein Problem sein:

-   **Jitter:** Media-Pakete eingeht mit einen Lautsprecher an automatischen klingen, wodurch andere Geschwindigkeit.

-   **Paketverlust:** Media-Pakete werden verworfen wird, erstellt die Auswirkung der fehlenden Wörter oder Silbenschrift verwenden.

-   **Zeit:** Media-Pakete sind sehr lange dauert, an das Ziel abgerufen werden, das einen Effekt Walkie-talkie erstellt.

Zwar keine zentrale Quelle Wahrheit Benutzerkonten für was Anruf schlechter Qualität führen kann, können mehrere allgemeine Methoden Umgang mit Netzwerkanomalien Ihnen ein.

Um Ihre Untersuchung Qualitätsprobleme rechten zu unterstützen, können Sie [Rufen Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)nutzen.
Mit Analysen aufrufen können Sie einer bestimmten Konferenz oder Benutzer detaillierte Anruf Bericht anzeigen. Dieser Bericht enthält PII-Daten und ist nützlich, wenn Sie versuchen, einen Grund für Fehler zu erkennen. Wenn Sie wissen, welche erstellen, die Verfolgung von Benutzern, Erstellen von unkompliziert sein sollte betroffen ist.

Vergessen Sie nicht, lassen Sie das Helpdesk wissen, dass diese Netzwerke Qualität, Probleme haben, sodass sie schnell selektieren und eingehende Anrufe beantworten können.

_Tabelle 9: Allgemeine Beiträge zu hohe PCR_

| Wartung                              | Anleitung       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Netzwerke                                 | Ein Netzwerk Überbelastung oder unter bereitgestellte kann zu Problemen mit Medienqualität führen. Arbeiten mit dem Netzwerkteam, um festzustellen, ob die Netzwerkverbindungen aus der Benutzer auf das Internet Ausgang zeigen hat genügend Bandbreite für Medien unterstützen. **Führen Sie eine Netzwerk-Bereitschaft:** Eine Netzwerk-Bewertung enthält Details zur Nutzung der erwarteten Bandbreite, wie bewältigen Bandbreite und Netzwerk ändert, und Netzwerke Methoden für Teams und Skype für Unternehmen empfohlen. Verwenden der obigen Tabelle als Quelle, müssen Sie eine Liste von Gebäude oder Subnetze, die eignen sich für eine Bewertung sind.<br><ul><li>[Microsoft-Teams, Netzwerk-Bereitschaft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype für Business Netzwerk Bereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Tool zur Bewertung der Microsoft Network:** Verwenden Sie dieses Tool für einen einfachen Test der Leistung des Netzwerks, um zu bestimmen, wie gut das Netzwerk für eine Teams ausführen würden oder Skype für Business Online Anruf. Mit diesem Tool können Sie bewerten die Leistung eines Subnetzes und überprüfen die Bereitschaft des Netzwerks gegen die Microsoft Performance [Requirements](https://aka.ms/performancerequirements).<br><ul><li>[Laden Sie das Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Quality of Service (QoS)                 | QoS ist eine bewährte Methode, um Pakete in einem Netzwerk, um sicherzustellen, dass sie am Ziel intakt eingehen und priorisieren. Berücksichtigen Sie die Implementierung der QoS in Ihrer Organisation, die die Qualität des Benutzererlebnisses maximieren, wenn die Bandbreite begrenzt oder eingeschränkt ist. QoS helfen, Probleme, die in der Regel mit hoher Paketverlust, lösen und – in geringerem Maße – Jitter und Round-Trip Zeiten. <br><ul><li>[Microsoft-Teams QoS-Anweisungen](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype für Business QoS-Anweisungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi kann eine erhebliche Auswirkungen auf die Anrufqualität haben. Wi-Fi-Design nicht in der Regel berücksichtigen Sie die netzwerkanforderungen für die VoIP-Dienste und sind häufig die Ursache von schlechter Qualität. **QoS:** Moderne drahtlose Netzwerke müssen vielen Geräten unterstützen. Diese Geräte konkurrieren für Bandbreiten- und können dazu führen, dass Qualitätsprobleme für VoIP-Dienste, in denen besitzen Geschwindigkeit und Wartezeit wichtiger. Wenden Sie sich an den Hersteller Ihres drahtlosen Einzelheiten, und implementieren Sie QoS für Ihr Drahtlosnetzwerk Skype für Geschäfts- und Teams Medien priorisieren. **AP-Dichte:** Zugriffspunkte (APs) möglicherweise zu weit auseinander oder nicht in eine ideale Speicherort. Um Probleme zu minimieren, setzen Sie zusätzliche APs in Konferenzräumen und Standorte, die von den Wänden oder sonstigen Objekte verdeckt werden nicht. **Mit 2,4 GHz im Vergleich zu 5 GHz:** 5 GHz enthält weniger Störungen im Hintergrund und einer höheren Geschwindigkeit und bei der Bereitstellung von VoIP über Wi-Fi priorisiert werden sollte. Jedoch 5 GHz ist nicht so stark wie mit 2,4 GHz nicht zugelassen und Walls so einfach. Überprüfen Sie vom Layout erstellen, um die Häufigkeit bestimmen Sie für die optimale Verbindung verwenden können. **Signalstärke:** Bisher gemessen in dBm (Power Verhältnis in DB), misst das die Stärke des drahtlosen Signals. Nachdem ein Gerät mit einem Zugriffspunkt verbunden ist, möchten nicht es können auf einfache Weise wechseln. Wenn das Gerät außerhalb der Zugriffspunkt verschoben wird, fällt die Signalstärke einen Punkt erreicht, die verursacht eine schlechte Verbindung, auch wenn ein anderes, je näher AP verfügbar ist. Wenn möglich, arbeiten Sie mit Ihrem AP-Hersteller, um sicherzustellen, dass die Zugriffspunkte konfiguriert wurden, um ein Gerät zu löschen, wenn ein akzeptables Maß Signalstärke unterschreitet. Dadurch wird sichergestellt, dass das Gerät an eine schwache Zugriffspunkt reagiert nicht. Dies ist eine gute Lösung, wenn Sie auf einfache Weise Weitere Zugriffspunkte hinzugefügt werden können. **WLAN-Treiber:** Wenn das Problem weiterhin besteht, stellen Sie sicher, dass wireless-Treiber auf dem aktuellen Stand sind. Dadurch wird eine beliebige benutzerfreundlich im Zusammenhang mit einer veralteten Treiber zu mindern. |
| Netzwerkgerät                           | In größeren Organisationen möglicherweise Hunderte von Geräten, die über das Netzwerk verteilt. Arbeiten mit Ihrem Netzwerkteam, um die Netzwerkgeräte vom Benutzer mit dem Internet sicherzustellen aufbewahrt werden und auf dem aktuellen Stand.     |
| VPN                                      | Es wurde gut dokumentiert, dass VPN-Geräte, Real-Time Media Arbeitslasten behandeln traditionell ausgelegt sind. Einige VPN-Konfigurationen verhindern die Verwendung von UDP (Dies ist das bevorzugte Protokoll für Audio) und stützen sich nur auf TCP. Berücksichtigen Sie die Implementierung einer [VPN-Split-Tunnel Lösung](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) zur Verringerung der VPN als Quelle von schlechter Qualität.        |
| Clients (Skype für Unternehmen nur Online) | Ältere Clients wurden als verursacht Probleme mit Medien. Stellen Sie sicher, dass Clients innerhalb von sechs Monaten nach Veröffentlichung gepatcht werden. [MyAdvisor](https://aka.ms/myadvisor) Hinweise zum Entwickeln einer Strategie für die Client-Bereitschaft nutzen und Bereitstellen von [Klick-und-Los](https://technet.microsoft.com/library/jj219427.aspx).      |
| Geräte                                  | Die Verwendung der [Geräte optimiert](https://partnersolutions.skypeforbusiness.com/solutionscatalog) , damit die Benutzeroberfläche wesentlich verbessert. Alles gleich sind optimierte Geräte so konzipiert, die Benutzeroberfläche mit Teams und Skype für Unternehmen zu maximieren und Erzeugen von höchster Qualität. Nutzen Sie [MyAdvisor](https://aka.ms/myadvisor) Anleitungen zum Entwickeln einer Strategie für die Bereitschaft Gerät.   |


### <a name="investigate-tcp-audio-sessions"></a>Untersuchen Sie die TCP-audiositzungen

TCP gilt ein Failback Transport- und nicht den primären Transport für Real-Time Media gewünschte. Der Grund dafür, dass sie ein Failback Transport ist besteht aufgrund der dynamische TCP. Beispielsweise, wenn ein Anruf erfolgt in einem Netzwerk latente und Medien Pakete verzögert werden klicken Sie dann Pakete von ein paar Sekunden vor – die eignen sich nicht mehr – konkurrieren für Bandbreite, um an den Empfänger zu abzurufen, die eine ungültige Situation verschlechtern können. Dadurch wird das audio Reparatur zusammenfügen und Dehnen Audio, wodurch hörbaren Artefakte häufig in Form von Jitter.

Die Berichte in diesem Abschnitt tätigen nicht unterschieden zwischen gute und schlechte Anrufe. UDP bevorzugte ist, suchen die Berichte für die Verwendung von TCP für Audio. Dies wird hauptsächlich durch unvollständig Firewallregeln verursacht. Weitere Informationen zu Firewall-Regeln für Teams und Skype für Business Online finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips).

> [!IMPORTANT]
> Mit einer gültigen [Erstellen Sie die Datei](#building-mapping) hochgeladen wird empfohlen, um schnell innerhalb von externen Audiostreams zu unterscheiden bei der Suche unter Verwendung von TCP zu können. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Audioströme, die mit allgemeinen TCP-Verwendung

Dieser Bericht gibt die TCP-Gesamtverwendung für Audio in den letzten sieben Monaten an, wie unten dargestellt.

Alle weiteren Berichte in diesem Abschnitt Schwerpunkt auf Eingrenzung bestimmte Gebäude und Subnetzen, wo TCP am häufigsten verwendet wird. Weitere Unterberichte zerlegen TCP Verwendung von Gesprächen mit zwei Teilnehmern und Konferenzen.

![Screenshot eines Diagramms, das die Anzahl der Audiostreams TCP pro Monat](media/quality-of-experience-review-guide-image23.png)

_Abbildung 23 – Audiostreams mit TCP-Verwendung_

##### <a name="investigation"></a>Untersuchung

Der Diagrammbericht zeigt Ihrer Organisation Gesamtverwendung TCP. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist das Gesamtvolumen des TCP-Anrufe für den aktuellen Monat?

2.  Handelt es sich verschlechtert oder besser als den vorherigen Monat?

3.  Ist die TCP-nutzungstrend erhöhen, steady, oder verringern?

Nehmen Sie Wenn Sie feststellen, dass die TCP-nutzungstrend erhöht wird, oder höher normalen monatlichen Nutzung, die Zeit untersuchen Sie mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Remediation. Idealerweise sollten Sie so wenig TCP-basierte audiositzungen wie möglich im verwalteten Netzwerk.

#### <a name="tcp-vs-udp"></a>TCP und UDP

In diesem Tabellenbericht identifiziert die Lautstärke von TCP und UDP Verwendungsberichten auf den aktuellen Monat für Konferenzen für Audio-, Video- und videobasierte Bildschirmfreigabe (VBSS).

![Bericht mit der Lautstärke des TCP und UDP-Konferenz Datenströmen im Vergleich mit PCR Vergleich dargestellt](media/quality-of-experience-review-guide-image24.png)

_Abbildung 24 – TCP und UDP - Konferenzen_

##### <a name="analysis"></a>Analyse

Obwohl Sie TCP-Nutzung so gering wie möglich sein soll, wird möglicherweise ein Bit der TCP-Verwendung in einer Bereitstellung andernfalls fehlerfrei angezeigt. Zum Vergleichen von UDP zur Verwendung von TCP-Audiostreams TCP durch UDP Audiostreams Prozentsatz bestimmt werden kann. Ein Wert über 1 Prozent muss genauer untersucht werden.

Im obigen Beispiel nehmen wir 1,806 TCP-Datenströme geteilt durch 10,481 UDP-Datenströmen bei einem Wert von 17,2 % eingehen. Dieser Wert ist größer als 1 Prozent und gibt an, dass wir müssen weiterhin die Untersuchung auf um zu bestimmen, wo die Verwendung von TCP auftritt.

Auch in den Bericht einbezogen ist Audio schlechter Prozentsatz. Dies ermöglicht Ihnen eine Ansicht in den Vergleich von Anrufqualität zwischen UDP und TCP zum Visualisieren wie TCP Overcall Anrufqualität auswirkt.

So nun, da Sie bestimmt haben, dass eine hohe Verwendung von TCP-basierte Audio in Ihrer Organisation vorhanden ist, was tun Sie als Nächstes? Wechseln Sie zur **TCP-Datenströme durch Erstellen und Subnetz** Berichte für die TCP-Nutzung durch Erstellen von und Subnetzen zu zerlegen.

#### <a name="tcp-streams-by-building-and-subnet"></a>TCP-Datenströme durch Erstellen und Subnetz

In den bereitgestellten CQD Vorlagen wechseln Sie in die TCP-Streams durch Erstellen und Subnetz-Berichte mithilfe der verwalteten oder Vorlage für alle Netzwerke. Es gibt drei Berichte in der Vorlage, eine für Untersuchen von Konferenzen mit und ohne Microsoft Relay-Informationen und eine für Untersuchen von Gesprächen mit zwei Teilnehmern enthalten. Zum Untersuchen der TCP, ist der Prozess, gleich, damit wir die Diskussion auf Konferenzen nur näher erläutert wird.

> [!IMPORTANT]
> Mit einer gültigen [Erstellen Sie die Datei](#building-mapping) hochgeladen wird empfohlen, um schnell innerhalb von externen Audiostreams zu unterscheiden bei der Suche unter Verwendung von TCP zu können. 

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.                                  |

![Bericht, TCP-Datenströme, erstellen, Netzwerk und Subnetz pro Monat geordnet aufgeführt.](media/quality-of-experience-review-guide-image25.png)

_Abbildung 25 – TCP-Datenströme durch die Erstellung- und Subnetz Konferenzen_

##### <a name="remediation"></a>Wartung

In diesem Bericht identifiziert bestimmte Gebäude und Subnetze abgerufen, die dem Volumen der Verwendung von TCP beitragen. Ein Bericht zusätzlicher ist ebenfalls enthalten, um die IP-Adresse des Microsoft-Relay zu identifizieren, die in den Anruf verwendet wurde, um zu isolieren fehlenden Firewallregeln. Konzentrieren Sie Ihre Remediation auf diese Gebäude, die dem höchsten zu erwartenden der Audiostreams maximieren Auswirkungen haben.

Die häufigste Ursache für die Verwendung von TCP fehlt Ausnahmeregeln in Firewalls oder Proxyserver. Wir sprechen Proxys im nächsten Abschnitt, also für jetzt Ihrer Arbeit Schwerpunkte auf die Firewalls. Über das Erstellen von oder Subnetz bereitgestellt, können Sie bestimmen, welche Firewall aktualisiert werden muss.

_Tabelle 10 - Remediation * Richtlinien für die TCP-Datenströme durch Erstellen und Subnetz_

| Wartung        | Anleitung     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurieren der firewall | Überprüfen Sie, ob [Office 365 IP-Ports und Adressen](https://aka.ms/o365ips) aus Ihrer Firewall ausgeschlossen werden. Obwohl es gibt viele IP-Adressen und Ports, die Media-bezogene TCP Probleme geöffnet werden müssen die folgenden Ihrer anfänglichen sind Schwerpunktthemen: Überprüfen Sie die folgenden [Medien Subnetzen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) befinden sich in Ihrer Firewall-Regeln. Finden Sie in Zeile 4 in der Tabelle, die für bestimmte Medien Subnetzinformationen angezeigt. [UDP-Ports 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): Diese Ports sind die bevorzugten Media-Ports und geöffnet werden müssen, andernfalls der Client wieder auf TCP-Port 443 fehl. |
| Vergewissern Sie sich             | Verwenden Sie das [Tool zur Bewertung der Microsoft Network](https://www.microsoft.com/download/details.aspx?id=53885) um zu prüfen, ob Konnektivitätsprobleme bei bestimmten Office 365-IP-Adressen und Ports aus dem betroffenen Gebäude oder Subnetz.    |

### <a name="investigate-http-proxy-usage"></a>Untersuchen Sie die Verwendung von HTTP-proxy

HTTP-Proxys sind die Bevorzugter Pfad für die Herstellung von mediensitzungen für eine Vielzahl von Gründen nicht. Viele Tiefe Paket Prüfung Features enthalten, die verhindern, dass Verbindungen mit dem Dienst abgeschlossen und Systemausfallzeit einführen können. Darüber hinaus können Proxys TCP erzwingen, im Gegensatz zu zulassen UDP, die für eine optimale Audioqualität empfohlen wird.

Es ist immer Microsofts Empfehlung an den Client für die Verbindung direkt Teams und Skype für BusinessServices konfigurieren. Dies ist besonders wichtig für basierenden Media-Datenverkehr.

> [!IMPORTANT]
> Ein gültiger [Erstellen Sie die Datei](#building-mapping) hochgeladen haben erleichtert es ordnungsgemäß innerhalb von externen Audiostreams zu unterscheiden beim Proxy Analyse. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Audioströme, die mit HTTP-Proxy Verwendung insgesamt

In diesem Bericht werden die Proxy-Nutzung über einen Zeitraum auf einer monatlichen Skala beschrieben. Der HTTP-Proxy Stream-Bericht in diesem Abschnitt der Vorlage ähnelt der TCP-Berichte. Es überprüfen nicht, ob Anrufe schlechter oder eine gute sind, aber gibt an, ob die Verbindung über HTTP hergestellt wurde.

![Screenshot der Audiostreams mit HTTP-Proxy-Verwendungsbericht im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image26.png)

_In Abbildung 26 – Audiostreams mit HTTP-Proxy-Verwendung_

##### <a name="analysis"></a>Analyse

Wenn Sie eine große Menge von HTTP-Verwendung angezeigt wird, finden Sie in Netzwerke Team, um sicherzustellen, dass die erforderlichen Ausnahmen vorhanden sind, damit Clients direkt Teams oder Skype für Business Online Media Subnetze weiterleiten. Idealerweise sollten keine Verwendung von HTTP-hier angezeigten vorhanden sein.

Wenn Sie nur eine Internet-Proxy in Ihrer Organisation haben, überprüfen Sie die ordnungsgemäße [Office 365-URLs und IP-Adresse Bereich Ausschlüsse](https://aka.ms/o365ips). Wenn mehr als ein, die Internet-Proxy in Ihrer Organisation konfiguriert haben, wird die HTTP nutzen Unterseite isolieren, welche Erstellen von Berichten oder Subnetz beeinflusst werden.

Für Organisationen, die den Proxy umgehen können nicht sicherstellen, dass die Skype für Business-Client anmelden ordnungsgemäß Wenn sie einen Proxyserver befindet wie im Artikel [beschrieben konfiguriert ist sollten Skype für Business Proxyserver verwenden, anstatt direkt anzumelden Verbindung](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>HTTP-Proxy-Streams durch Erstellen und Subnetz

In diesem Bericht identifiziert bestimmte Gebäude und Subnetze abgerufen, die zur Verwendung von HTTP-beitragen.

> [!IMPORTANT]
> Ein gültiger [Erstellen Sie die Datei](#building-mapping) hochgeladen haben erleichtert es ordnungsgemäß innerhalb von externen Audiostreams zu unterscheiden beim Proxy Analyse.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.                        |

![Screenshot der HTTP-Proxy Nutzung durch Erstellen und Subnetz Bericht im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image27.png)

_Abbildung 27 – HTTP-Proxy-Nutzung durch die Erstellung und Subnetz_

##### <a name="remediation"></a>Wartung

Konzentrieren Sie Ihre Remediation auf jedem Gebäude oder die Subnetze abgerufen, die Verwendung von HTTP-Proxy aufweisen. Die häufigste Ursache für HTTP-Verwendung fehlt Ausnahmeregeln in Proxys. Über das Erstellen von oder Subnetz bereitgestellt, können Sie bestimmen, welche Proxy aktualisiert werden muss.

Stellen Sie sicher, dass die erforderlichen [Office 365 FQDNs](https://aka.ms/o365ips) vom Proxy ausgeschlossen werden.

## <a name="endpoint-investigations"></a>Endpunkt Untersuchungen

In diesem Abschnitt konzentriert sich auf die Aufgaben für die Berichte zur Skype für Business-spezifischen Client-Versionen und die Verwendung von zertifizierte Geräte.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt. Die Beschreibung der einzelnen Berichts Weitere Informationen finden. 


### <a name="determine-client-versions"></a>Bestimmen der Client-Versionen

In diesem Bericht konzentriert sich auf Skype für Business Clientversionen verwendet und ihren relativen Lautstärke in der Umgebung identifizieren.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt und über die Azure Content Delivery Network (CDN) automatisch aktualisiert werden und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.

Versionsnummern für Skype für Business 2015 und 2016 finden Sie über die folgenden Links:

-   [Office 365-Client-Kanal Updateversionen](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Office 365-Version und Build-Nummern für klicken Sie auf Ausführen](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype für Business-Downloads und-Updates](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.  

> [!IMPORTANT]
> Clientberichte müssen Sie federated Teilnehmer Daten ausgeschlossen werden. Um Verbund Teilnehmer Daten auszuschließen, müssen Sie einen Abfragefilter für **Zweiten Mandanten-ID** in Ihrer Organisation [Mandanten-ID](#tenant-id)festlegen hinzufügen. |

![Screenshot des Berichts-Clients und-Geräten im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image28.png)

_Abbildung 28 - Client-Version-Bericht_

#### <a name="remediation"></a>Wartung

Ein wichtiger Aspekt gesteuerter hochwertigen benutzerumgebungen müssen Sie sicherstellen, dass verwaltete Clients auf dem neuesten Stand Versionen von Skype für Unternehmen ausgeführt werden. Dies bietet verschiedene Vorteile, dazu zählen:

-   Es ist einfacher, einige Versionen im Vergleich zu viele Versionen zu verwalten.

-   Es bietet eine einheitliche Erfahrung.

-   Es erleichtert die Problembehandlung bei Anrufqualität und Verwendbarkeit.

-   Microsoft stellt allgemeine Verbesserungen und Optimierungen ständig über das Produkt. Sicherstellen, dass Benutzer diese Updates erhalten, die ihre Risiken der Ausführung in ein Problem, das bereits behoben ist.

Einschränken des Ihre Bereitstellung Clientversionen, die weniger als sechs Monaten sind wird die gesamten Benutzeroberfläche verbessert und Verbesserung der Verwaltbarkeit im Vergleich zu großen Anzahl von verschiedenen Versionen des Clients in der gleichen Umgebung müssen.

Wenn Sie nur Office Klick-und-Los verwenden, werden Sie automatisch binnen sechs Monaten sein. Es ist keine weitere Aktion erforderlich.

"If"; wie die meisten Unternehmen Sie eine Kombination von Klick-und-Los und Installer-Paket (MSI) verfügen, können Sie den Bericht verwenden, um sicherzustellen, dass die MSI-Clients regelmäßig aktualisiert werden. Konzentrieren Sie auf diesen Clients, auf dem das Volume überdurchschnittlich ist. Wenn Sie, dass Clients feststellen hinter sinkt, arbeiten mit dem Team verantwortlich für die Verwaltung von Office-Updates, und stellen Sie sicher, dass sie genehmigen und Bereitstellen von Client-Patches regelmäßig sind.

### <a name="devices-investigations"></a>Geräte Untersuchungen

So tätigen mithilfe des geräteberichts folgende Punkte sollten Sie das Konzept der Mittelwert Opinion verstanden haben (MOS). MOS ist die Messung Gold-Standard: die wahrgenommene Audioqualität zu ermitteln. Es wird als eine Bewertung ganze Zahl im Bereich von 0 bis 5 dargestellt.

Die Grundlage für alle Maßnahmen der Sprachqualität ist wie eine Person für die Qualität der Speech Verbindungsmodus. Da es von human Wahrnehmung betroffen ist, ist es grundsätzlich subjektive. Es gibt mehrere verschiedene Methoden subjektive testen.
Die meisten VoIP Qualität Measures basieren auf einer absoluten Kategorisierung Bewertungsskala (ACR).

Ein ACR subjektive Test bewerten in eine statistisch signifikante Anzahl von Personen ihre Qualität auf einer Skala von 1 (schlecht) auf 5 (hervorragend). Der Mittelwert der Ergebnisse ist die MOS. Die resultierende MOS hängt von den Bereich der Erfahrungen, die die Gruppe und den Typ des Erfahrung bewertet wird verfügbar gemacht wurden.

Da es nicht sinnvoll, um für ein Kommunikationssystem live subjektive Tests der Sprachqualität auszuführen ist, Teams und Skype für Unternehmen mithilfe von erweiterten Algorithmen eine subjektive Testergebnisse objektive vorhergesagt MOS Werte generieren.

Der verfügbare Satz mit MOS und Metrik eine Ansicht in der Qualität der Zustellung an die Benutzer bereitstellen.

Durch Bereitstellen von Benutzern mit Geräten zertifiziert für Teams und Skype für Unternehmen, verringern Sie die Wahrscheinlichkeit solch negative Erfahrungen aufgrund des Geräts selbst (die wahrscheinlicher, beispielsweise mit integrierten Laptop-Lautsprecher und Mikrofon ist). Weitere Informationen finden Sie unter [Telefone und Geräte für Skype für Unternehmen](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Organisatorische Verwendung der Capture-Geräte (Mikrofone) nach volume

In diesem Bericht wird verwendet, um Mikrofon Usage bewerten und MOS Score und finden Sie in den zugehörigen Vorlagen unter Clients und Geräte *.*

> [!IMPORTANT]
> Gerät Berichte müssen Sie federated Teilnehmer Daten ausgeschlossen werden. Um Verbund Teilnehmer Daten auszuschließen, müssen Sie einen Abfragefilter für **Zweiten Mandanten-ID** in Ihrer Organisation [Mandanten-ID](#tenant-id)festlegen hinzufügen. 

> [!NOTE] 
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.<br><br> Sie möglicherweise feststellen, wenn mehrere Male gemeldet, dass Sie dasselbe Gerät finden Sie unter Bericht anzeigen. Dies liegt daran, die das Gerät gemeldet wird an CQD gemeldet werden. Unterschiede in der Hardware und Betriebssystem-Gebietsschema Berichten Gerätedaten unterschiedlich.

![Screenshot des Berichts Geräte (Mikrofon) im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image29.png)

_Abbildung 29 - – Gerätebericht (Mikrofon)_

##### <a name="remediation"></a>Wartung

Der erste Schritt besteht das Ziel des Vorgangs MOS bestimmen erreichen möchten. MOS bewertet Bereich von 1 bis 5, mit 5 wird das beste. Wählen Sie eine angemessene Ziel basierend auf Ihrer Umgebung und Abfrageergebnisse. Im folgenden Beispiel ist das Ziel ein MOS Bewertung von 3.6 oder höher für alle Geräte, die mehr als 100 Datenströme aufweisen. Sie erzielen die Gerätequalität abzielen, wenn:

-   Die Abfrageergebnisse Gerät zurückgeben MOS \> 3.6 für NumStreams \> 100

In der Regel müssen Sie leistungsschwachen Geräte mit zertifizierte Geräte zu ersetzen. Einige Aspekte beim Überprüfen von Device Report umfassen:

-   Sind die zertifizierte Geräte oder zweifelsfrei funktionierende in Ihrer Umgebung? In der Abfrage mit einem niedrigeren MOS Faktor als des Basisplans ein zertifizierten oder eine gute Gerät zurückgegeben wird, möglicherweise unbekannte Weitere Faktoren (beispielsweise eine schlechte Netzwerk- oder unzureichende pc), die an die niedrigste Punktzahl beiträgt.
    Zusätzliche Untersuchung werden benötigt.

-   Sie können Benutzer eines Geräts über [Analytics aufrufen](#call-analytics-training)identifiziert. Überprüfen Sie, um sicherzustellen, über die neuesten Gerätetreiber verfügen und, dass ihr Gerät über ein USB-Hub verbunden ist.

-   Überprüfen Sie, ob eine Beziehung zwischen fehlerhafte Geräte und stellen Sie ein bestimmtes System und das Modell vorhanden ist. Wenn dies der Fall ist, kann das Gerät nicht kompatibel oder Treiber-Upgrades benötigen.

Die zweite Aufgabe besteht darin, die allgemeine Verwendung nicht zertifizierte Geräte zu bestimmen. Es wird empfohlen, mindestens 80 Prozent der alle Audiostreams zu einem zertifizierten Gerät verwenden.
Dies geschieht am besten durch den Geräte-Bericht nach Excel exportieren und die Verwendung von zertifizierten oder genehmigten Geräten manuell berechnen. Organisationen lassen in der Regel eine Liste mit allen genehmigten Geräten, damit filtern und Sortieren von Daten einfach sein sollte.

## <a name="appendix-a-lync-networking-guide"></a>Anhang a: Lync Netzwerke (engl.)

Für weitere Hintergrund auf der Teams und Skype für Netzwerke Business-Konzepte und Gründe für die Qualität ihrer Wichtigkeit ist der [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) gelten auch weiterhin.

## <a name="appendix-b-network-performance-requirements"></a>Anhang b-Leistung netzwerkanforderungen

Die Qualität von Real-Time-Medien (Audio, Video und Anwendungsfreigabe) Implementation wird durch die Qualität der End-to-End-Netzwerkkonnektivität erheblich beeinträchtigt. Für eine optimale Teams oder Skype für Business Medienqualität muss Ihr Netzwerk die folgenden Leistungsmetriken Netzwerk erfüllen.

_In Tabelle 11 - Netzwerk leistungsanforderungen_

| Metrik                           | Client zu Microsoft Edge           | Kundenedge zu Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Wartezeit (unidirektional)                | \<50 ms                            | \<30 ms                            |
| Wartezeit (Zeit oder Roundtripzeit) | \<100 ms                           | \<60 ms                            |
| Bursts von Paketverlusten                | \<10 % Intervall 200 ms   | \<1 % Intervall 200 ms    |
| Paketverlust                      | \<1 % Intervall 15 s    | \<0,1 % Intervall 15 s  |
| Die Kommunikation zwischen hinzukommen Jitter Paket      | \<während ein Intervall von 15 s 30 ms | \<15 ms Intervall 15 s |
| Paket neu anordnen                   | \<0,05 % außerhalb der Reihenfolge Pakete       | \<0,01 % außerhalb der Reihenfolge Pakete      |

Weitere Informationen finden Sie unter den folgenden Artikel über das [Media Quality und Netzwerk Leistung](https://aka.ms/performancerequirements) für Teams und Skype für Business Online.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Anhang C. Weitere Ressourcen

### <a name="building-data-file"></a>Erstellen von-Datendatei

-   [Aktivieren und Verwenden von CQD in Skype für Business Online](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>CQD-Schulung

-   <https://aka.ms/sof-cqd>

-   Handbuch [Erste Schritte mit CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) und Workshop.

-   [CQD Dimensionen und Measures online-Entwicklerhandbuch](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Rufen Sie Analytics-Schulung

-   [Einführung in Anruf Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Einrichten der Anrufanalyse von Skype for Business](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Wenden Sie Analytics

-   Community: [Skype für Business Preview-Programm](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Wenn Sie Unterstützung erhalten möchten, melden Sie sich unsere Preview Portal [www.skypepreview.com](http://www.skypepreview.com), wählen Sie **Bericht ein Problem**und verwenden Sie die Option **Erstellen eines neuen Fehler** Berichten eines Problems. Bitte beachten Sie, dass Support-Mitarbeiter zur Verfügung, Unterstützung von Montag zwischen 6 Uhr um 9 Uhr EST zurück. Anfragen außerhalb Stunden, werden der folgende Tag selektierender.

### <a name="devices"></a>Geräte

-   [Skype für Business Solutions Catalog Peripheriegeräte & PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Mandanten reporting

-   [Office 365 Annahme Inhaltspaket](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Skype for Business Online-Berichterstellung](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Microsoft-Teams, reporting](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
    =======
---
title: Quality of Experience überprüfen Handbuch für Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 'Handbuch für die Analyse der Leistung für Microsoft-Teams, Real-Time Media mithilfe von Anrufen Quality Dashboard (CQD).'
MS.collection: Strat_MT_TeamsAdmin
appliesto:
  - Microsoft Teams
---

# <a name="quality-of-experience-review-guide"></a>Quality of Experience überprüfen Guide

In diesem Handbuch wird über das Laufwerk Wert Phase für Microsoft-Teams und Skype für Business Online. Sie können dieses Handbuchs [eine Word-Version herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) .

## <a name="introduction"></a>Einführung

Um am stärksten zur Verbesserung der benutzerfreundlichkeit haben, müssen Unternehmen wichtige Bereiche durchsetzen, die in der folgenden Abbildung dargestellt sind.
Weitere Bereiche umfassen, Betriebsaufgaben identifiziert, Zielvorgaben für Qualitätsmetriken, die Metriken zu verwenden, um Erfolg einzuschätzen Punkte und Bereiche der Untersuchung einschränken, je nach Bedarf.

![Wichtige Bereiche für die Qualität des Benutzererlebnisses enthalten, Audio, Zuverlässigkeit, den benutzerumfragen, Geräte und Clients.](media/quality-of-experience-review-guide-image1.png)

_Abbildung 1: Schlüssel betriebliche behandelten im gesamten Dokument_

Ständig bewerten und Korrigieren von den in diesem Dokument beschriebenen Gebieten, können Sie ihre Potenzial, die sich negativ auf die Qualität Ihrer Benutzer-Erfahrung auswirken reduziert. Die meisten Benutzer-Erlebnis Probleme in einer Bereitstellung können in die folgenden Kategorien unterteilt werden:

-   Unvollständige Firewall oder der Proxyserver-Konfiguration

-   Schlechte Wi-Fi-Abdeckung

-   Unzureichende Bandbreite

-   VPN

-   Inkonsistente oder veraltete Clientversionen

-   Nicht optimierte oder integrierte Audiogeräte

-   Problematisch Subnetze oder Netzwerkgeräte

Durch sorgfältige Planung und Entwurf vor der Bereitstellung von Teams oder Skype für Business Online können Sie Aufwand reduzieren, die erforderlich sind, um qualitativ hochwertige guter maintain.

Dieses Handbuch konzentriert sich auf Online aufrufen Quality Dashboard (CQD) als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche mit besonders auf die Annahme und Auswirkungen auf die Maximieren-Audio verwenden. Versucht, das Netzwerk zur Verbesserung der Audioqualität Verbesserungen übersetzt auch direkt in Verbesserungen bei video sowie die Desktopfreigabe.

Um die Bewertung zu beschleunigen, werden zwei curated CQD-Vorlagen zur Verfügung gestellt: eine für alle Netzwerke und der andere verwalten für gefiltert wird verwaltet wird nur Netzwerke (intern). Obwohl der Berichte alle Netzwerke Vorlage zum Erstellen von und Netzwerkinformationen anzeigen konfiguriert sind, kann es bei der Arbeit zu sammeln und Hochladen von Informationen zum Erstellen von dennoch verwendet. Erstellen von Informationen in CQD hochladen ermöglicht dem Dienst durch Hinzufügen von benutzerdefinierten erstellen, Netzwerk und Speicherort Informationen beim Unterscheidung von externen Subnetzen interne reporting optimiert. Weitere Informationen finden Sie unter [Erstellen von Zuordnung](#building-mapping) weiter unten in diesem Dokument.

### <a name="what-is-the-cqd"></a>Was ist die CQD?

Sie verwenden rufen Quality Dashboard (CQD) Einblick in die Qualität der Anrufe mithilfe von Teams und Skype für BusinessServices. CQD soll helfen, Skype für Geschäfts- und Teams-Admins und Netzwerktechniker Optimieren des Netzwerks. CQD untersucht aggregierte Informationen für eine ganze Organisation, auf dem gesamten Muster offensichtlich, werden können Mitarbeiter informiert Bewertung der Anrufqualität zu ermöglichen. CQD bietet Berichte der Anruf-Metriken, die Ihnen Einblick in die allgemeine Anrufqualität, Anruf Zuverlässigkeit und benutzerfreundlichkeit bieten.

> [!NOTE]
> CQD enthalten keine personenbezogene Informationen (PII). PII sind Informationen, die verwendet werden kann allein oder mit anderen Informationen bezeichnen, wenden Sie sich an, oder suchen eine einzelne Person oder um eine einzelne Person im Kontext zu identifizieren. 

### <a name="intended-audience"></a>Zielgruppe

Dieses Dokument ist für die direkte Verwendung von Partnern und Kunden Beteiligten mit Rollen wie leitender/Architekt für die Zusammenarbeit, Berater, Change Management/Annahme Specialist, Unterstützung/Help Desk führen, Netzwerk führen, Desktops führen und IT-Administrator verwendet werden

Dieses Dokument ist auch von der festgelegten Qualität Champion(s) verwendet werden soll.
Weitere Informationen finden Sie unter [der Qualität Champion-Rolle](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie bevor Sie dieses Handbuch verwenden sicher, dass Sie die richtige Mandanten [Rollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) zugewiesen, sodass Sie CQD zugreifen können.

-   **Globalen Administratorrolle von Office 365:** Greift auf alle administrativen Funktionen in Office 365-Suite von Diensten in Ihrem Plan, einschließlich Skype für Unternehmen.

-   **Skype für Business Administratorrolle:** Skype für Unternehmen für Ihre Organisation konfiguriert, und ist berechtigt, die [Berichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Office 365 Administrationscenter anzeigen. Diese Rolle ist erforderlich, auch wenn Sie nur Teams bereitstellen.

Alternativ können Sie ein Office 365-Benutzerkonto den Zugriff auf Berichtsfunktionen nur folgende Rolle zuweisen.

-   **Leser von Berichten:** Können die [Berichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Office 365 Administrationscenter, alle Berichte aus dem [Office 365 Annahme Inhaltspaket](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)und CQD Berichte anzeigen.

Grundlegendes zu den grundlegenden Konzepten von CQD maximieren können die Auswirkung, die Sie bei der Verbesserung Ihrer Benutzer Erfahrung mit Teams oder Skype für Business Online vornehmen können.
Weitere Ressourcen finden Sie im [Anhang](#other-resources).

## <a name="what-is-quality"></a>Was ist die Qualität?

Im Zusammenhang mit Qualität in Teams und Skype für Unternehmen ist es wichtig, definieren Sie den Begriff, um eine allgemeine Grundlegendes zu erreichen. Qualität, ist wie hier definiert eine Kombination von Metriken und benutzerfreundlichkeit Service.

![Service-Metriken bestehen aus der Anrufe schlechter Qualität Verhältnis, Zuverlässigkeit, Endpunkte-Geräte und Client-Versionen. End User Experience Wahrnehmung der Dienstqualität des Benutzers besteht.](media/quality-of-experience-review-guide-image2.png)

_Abbildung 2: Was Qualität ist?_

### <a name="define-your-target-metrics"></a>Definieren Sie die Ziel-Metriken

In diesem Abschnitt werden die Core Service-Metriken, die wir verwenden, um bewerten, wie Dienste Health auftreten. Ständig bewerten und Entwicklung, diese Metriken unter Ziel zu halten, helfen Ihnen, sicherzustellen, dass Ihre Benutzer konsistente, zuverlässige Anrufqualität auftreten. Um Ihnen den Einstieg zu erleichtern, werden die folgenden Ziele bereitgestellt.
Lassen Sie uns kurz den Unterschied zwischen einem verwalteten und nicht verwalteten Netzwerk:

-   Eine *verwaltete* Netzwerk beeinflusst, und von der Organisation gesteuert werden kann.
    Dazu gehören das interne LAN, remote WAN und VPN.

-   Ein *nicht verwalteten* Netzwerk werden nicht beeinflusst oder von der Organisation gesteuert. Ein Beispiel für eine nicht verwaltete Netzwerk ist ein Hotel oder am Flughafen Netzwerk.

_Tabelle 1: Core Ziel Health Assessment Metriken_

|               | Qualität für verwaltete Netzwerke | Zuverlässigkeit für verwaltete Netzwerke |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Metrische name   | Trefferquote % der Audio-Anrufe schlechter Qualität      | Rufen Sie Setup mit Fehlern %            | Rufen Sie die Drop Fehler % |
| Beispiel-Ziel | \<3 %                         | \<1 %                             | \<4 %                 |

Es ist wichtig, zu besprechen und definieren die Ziele Ihrer Organisation, um Ihre Geschäftsziele zu erfüllen. Idealerweise sollten Sie diesen Zielen vor der Bereitstellung identifizieren.

#### <a name="audio-pcr-"></a>Audio PCR % 

Audio schlechter aufrufen Verhältnis (PCR) stellt allgemeine Prozentsatz an anrufen, die Audioqualität Ihres Unternehmens. Diese Metrik dient zum Hervorheben von Bereichen, in Ihrer Organisation Aufwand für die stärksten wirken sich in Richtung verringern diesen Wert und Verbessern der benutzererfahrung, weshalb verwaltete Netzwerken der Schwerpunkt sind beim Betrachten PCR konzentrieren können. Externe Benutzer zu wichtig sind, aber Untersuchungen unterscheidet sich regelmäßig Organisations- und Benutzer.
Erwägen Sie, bewährte Methoden für externe Benutzer, und externe Anrufe unabhängig von der gesamten Organisation betrachten.

#### <a name="call-setup-failures-"></a>Rufen Sie Setup mit Fehlern % 

Dies ist eine beliebige Media-Sitzung, die konnte nicht hergestellt werden. Aufgrund den Schweregrad der Auswirkungen ermittelte Benutzerinteraktion ist das Ziel dieser Wert als erreicht bald wie möglich bei Null zu reduzieren. Ein hoher Wert für diese Metrik ist in neuen Bereitstellungen mit unvollständiger Firewallregeln häufiger als eine über Erfahrungswerte zur Bereitstellung, aber es ist wichtig, die in regelmäßigen Abständen Video. Ihre betriebliche Genehmigungsverfahren Laufe der Zeit können Sie diese Metrik zum Einschließen von Video- und Desktopfreigabe Arbeitslasten erweitern.

#### <a name="call-drop-failures-"></a>Rufen Sie die Drop Fehler % 

Dies gilt für ein audio Arbeitslast, in dem die Sitzung unerwartet beendet. Ihre betriebliche Genehmigungsverfahren Laufe der Zeit können Sie diese Metrik zum Einschließen von Video- und Desktopfreigabe Arbeitslasten erweitern.

### <a name="service-metrics"></a>Service-Metriken

Dienst metrischen Ziele bestehen bestimmte clientbasierte Metriken.

#### <a name="pcr"></a>PCR

Die Grundlage für die Bestimmung, ob ein Anruf schlechter eingestuft ist, wird mithilfe des Anrufe schlechter Qualität-Verhältnis (PCR). PCR besteht aus fünf Netzwerk-Metriken, die in der folgenden Tabelle beschrieben. Für einen Anruf als schlecht klassifiziert werden muss nur eine Metrik den definierten Schwellenwert überschreitet. Weitere Informationen zum Vorgang, Anruf Klassifizierung finden Sie unter [in diesem Blogbeitrag](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tabelle 2: Service-Metriken Anrufe schlechter Qualität_

| Metrik                                           | Beschreibung                                                                                                                                                                                                                                                                                                                                                                  | Benutzererfahrung                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jitter \>30 ms                                   | Dies ist die durchschnittliche Änderung Verzögerung zwischen aufeinander folgende Pakete. Für einige Ebenen von Jitter über Pufferung können Teams und Skype für Unternehmen anpassen. Es ist nur, wenn die Jitter überschreitet die Pufferung, dass ein Teilnehmer die Effekte der Jitter bemerkt.                                                                                                                         | Die Pakete an einem anderen kumulativ dazu führen, dass ein Lautsprecher Stimme zum automatischen auszugeben.                                                                                       |
| Paketverlustrate \>10 % oder 0,1                    | Dies ist häufig als Prozentsatz der Pakete definiert, die verloren gegangen sind. Paketverlust wirkt sich direkt auf die Audioqualität – von kleinen, verloren Person Pakete, die fast keine Auswirkungen auf Back Bursts von Verlusten haben, Ursache Audio vollständig Ausschneiden.                                                                                                                               | Die Pakete werden verworfen und nicht eingehenden an das vorgesehene Ziel verursachen Lücken in den Medien, resultierende in verpassten Silben und Wörter und abgehackte video und Freigabe. |
| Roundtripzeit \>500 ms                         | Dies ist der Zeitaufwand zum Abrufen von ein IP-Paket von Punkt A nach Punkt B und an Punkt A. Diese Netzwerk Verteilung Verzögerung ist mit der physischen Abstand zwischen zwei Punkte und der Lichtgeschwindigkeit verknüpft und enthält zusätzlichen Aufwand, die von den verschiedenen Geräten im Netzwerkpfad übernommen.                                                                                  | Die Pakete braucht zu lange zum am Ziel eingehen dazu führen, dass einen Effekt Walkie-talkie.                                                                                 |
| NMOS-Beeinträchtigung Durchschnitt \> 1.0                  | Eine oder mehrere der folgenden Metriken Netzwerk zwar einzeln waren nicht schlecht, verursacht zusammen um mehr als einen Punkt der Netzwerk- [Mean Opinion Score](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS), zu löschen. Dies bedeutet nicht unbedingt die Netzwerkschnittstelle ist schlecht, aber genügend Probleme aufgetreten sind, während des Anrufs, dass Qualität reduziert wurde. | Hierbei handelt es sich um eine Kombination von Jitter Paketverlust, und – in geringerem Maße – Roundtripzeit erhöht. Der Benutzer kann eine Kombination der folgenden Symptome auftreten.          |
| Durchschnittliches Verhältnis zwischen ausgeblendeten Samples \> 7 % oder 0,07 | Eine oder mehrere der folgenden Metriken Netzwerk zwar einzeln waren nicht schlecht, verursacht dem Client selbst reparieren das Medium. Ein ausgeblendeter audio Beispiel ist ein Verfahren zur abrupten Übergang zu glätten, die in der Regel durch Initiale Netzwerkpaketen verursacht werden würde.                                                                                                                | Hohe Werte anzugeben, dass erhebliche Ebenen der Verlust zum Verbergen angewendet wurden, und ergab Audio verzerrt oder verloren.                                                  |

#### <a name="client-and-device-readiness"></a>Client- und Gerätefunktionen Bereitschaft

Benötigen Sie eine solide Client- und Gerätefunktionen Strategie um sicherzustellen, dass die Benutzer eine konsistente und positive Benutzeroberfläche zur Verfügung haben. Einige wichtige Prinzipien Laufwerk jeweiligen Strategie Readiness.

##### <a name="client-readiness"></a>Client-Bereitschaft

Eine Strategie für die sichere Client Bereitschaft wird sichergestellt, dass Ihre Benutzer die neueste Version des Clients und genießen dabei die bestmögliche Erfahrung ausgeführt werden.
Microsoft-patches routinemäßig die Skype für Business Client; sicherstellen, dass Sie es in Ihrer Umgebung Stand ist entscheidend für Ihre gesamten Erfolg.

Es wird empfohlen, dass Sie nicht in Ihrer Client-Versionen von mehr als sechs Monaten fallen hinter lassen. Wenn Sie Office Klick-und-Los verwenden, sind Sie bereits auf dem aktuellen Stand vom Dienst gespeichert wird. Verwenden Sie enthalten [Kundenbericht](#determine-client-versions)wie weiter unten in diesem Handbuch wird beschrieben, die Sie dabei unterstützen. Sie können auch die Beispielberichte Rate Meine aufrufen zu steigern Ihrer Strategie für die Client-Bereitschaft nutzen.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt sind, und durch die Azure Content Delivery Network automatisch aktualisiert, und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.


##### <a name="device-readiness"></a>Gerät Bereitschaft

Keine einer Strategie für die einzelne kann die Benutzeroberfläche, die mehr als Ihrer Strategie für die Bereitschaft Gerät auswirken. Die meisten Organisationen freuen, entfernen Sie unnötige Geräte von Benutzern (beispielsweise Telefonapparate oder anderen dedizierten Audiogeräte), und dies ist häufig als Rechtfertigung Core für den Wechsel zu Teams oder Skype für Unternehmen. Allerdings zögern gleichen Organisationen manchmal Replacement-Geräte bereitstellen, auch wenn diese Geräte kostengünstigeren wurden. Modernen Laptops und PCs, jedoch mit integrierten Mikrofon und Lautsprecher, ausgestattet sind nicht für die Business-Klasse Voice over IP (VoIP) optimiert. Dadurch wird erstellt oft eine schlechte Erfahrung für alle Teilnehmer, insbesondere dann, wenn der Lautsprecher in einer lauten Umgebung ist. Zertifizierungsprogramm für Microsoft Gerät wird sichergestellt, dass, wenn ein Benutzer einen Telefonanruf gehört mithilfe von jedem Gerät zertifiziert für Teams oder Skype für Unternehmen, eine wünschen erzeugt, die zu einem Gerät nicht zertifizierter überlegen ist.

Wir empfehlen immer Teams und Skype für Unternehmensbenutzer eine zertifizierten Kopfhörer oder Lautsprecher verwenden, wenn einen Anruf durch mithilfe eines Desktopclients teilnehmen.
Weitere Informationen zu Microsoft überprüfen zertifizierte Geräte in diesem [Artikel über das Telefone und Geräte qualifizierten](https://technet.microsoft.com/office/dn788944.aspx). Verwenden Sie den [Device Report](#devices-investigations)Unterstützung bei der Verwaltung Ihrer Geräte weiter unten in diesem Handbuch. Die Beispielberichte Rate Meine aufrufen, können auch um Ihrer Strategie für die Bereitschaft Gerät weiter zu verbessern.

### <a name="user-experience"></a>Benutzererfahrung

Analysieren die Benutzeroberfläche ist mehr Kunst als Science, da hier die Metriken gesammelt nicht immer bedeuten, es ein Problem mit dem Netzwerk oder Service ist, sondern vielmehr sie hinweisen, dass der Benutzer ein Problem wahrnimmt. Microsoft bietet einen Umfragemechanismus integrierten – bekannt als Rate Meine aufrufen (RMC) – Hilfe benutzerfreundlichkeit zu ermitteln. RMC hilft Ihnen die aus Sicht des Benutzers die folgenden Fragen beantworten:

-   Weiß ich, wie Sie die Lösung verwenden können?

-   Ist die Lösung, einfach zu verwendenden und intuitiv, und wird über die alltägliche Kommunikation führe unterstützt?

-   Kann die Lösung mich Meine erledigen?

-   Was ist meine allgemeine Wahrnehmung der Lösung?

-   Kann ich verwenden die Lösung an einer beliebigen Stelle in der Zeit, unabhängig davon, an denen ich bin?

-   Kann ich einrichten und verwalten ein Anrufs?

#### <a name="rmc"></a>RMC

RMC Teams und Skype für Unternehmen integriert und wird automatisch so konfiguriert, dass nach einem in jeder 10 Anrufe oder 10 Prozent aller Anrufe angezeigt werden. In diesem kurzen Umfrage fordert den Benutzer den Anruf bewerten und einen wenig Kontext für warum die Anrufqualität schlechter wurden möglicherweise bereitstellen. Eine Bewertung ein oder zwei schlechter gilt, eignet sich drei bis vier und fünf ist hervorragend. Obwohl es etwas eines Indikators Verzögerung beim ist, ist dies eine nützliche Metrik für Unternehmensdaten Probleme, die Service-Metriken verpassen können.

> [!NOTE]
> Bis der Benutzer aufgefordert werden, durch das Erteilen von guten Feedback zusätzlich zu schlecht, Antworten in der Regel auf RMC Umfragen reagieren zurückkehren Sie als überwältigend negativ. Die meisten Benutzer reagieren nur, wenn die Anrufqualität schlechter befindet. Aus diesem Grund können RMC Berichte auf der Seite schlechter verzerrt angezeigt werden auch dann, wenn der Dienst Metriken gute sind. 


Sie können CQD verwenden, um einen Bericht über RMC Benutzerantworten und Beispielberichte sind in der Vorlage CQD enthalten. Sie sind nicht jedoch in diesem Handbuch ausführlich erläutert. Weitere Informationen zu RMC in Skype für Business Online und Richtlinien für die Schulung von Benutzern zum Vorführen nützliche RMC Antworten finden Sie unter in diesem [Blogbeitrag](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Kategorien von Qualität

Der Erfolg der operationalizing einer hohe Qualität und zuverlässigen bereitstellungs hängt von Ihrer Erstellen von betrieblichen Genehmigungsverfahren ab. Achten Sie insbesondere, besonders auf die drei Kategorien, die in der folgenden Abbildung dargestellt; Hierbei handelt es sich um den Fokus dieses Handbuchs:

-   **Netzwerk:** Audioqualität konzentriert sich auf die PCR Metrik, TCP-Verwendung, verkabelten und drahtlosen Subnetze, und identifizieren die Verwendung von HTTP-Proxys und VPN.

-   **Endpunkte:** Audiogeräte und der Clientversion (Skype für nur Unternehmen).

-   **Dienstverwaltung:** Dieser Kategorie besteht aus zwei Abschnitten:

    -   Zunächst wird Microsofts Verantwortung zu verwalten und Verwalten von Teams und Skype für Business Online-Dienste.

    -   Zweitens sind Aufgaben, die Ihre Organisation verwalten muss, um sicherzustellen, dass zuverlässigen Zugriff auf den Dienst, beispielsweise zum Erstellen von Informationen zu aktualisieren und Verwalten von Firewalls für neue Office 365-IP-Adressen, sobald Infrastruktur mit dem Dienst hinzugefügt wird.

![Die Kategorien von Qualilty in einer Organisation: service-Management, Endpunkte und im Netzwerk.](media/quality-of-experience-review-guide-image3.png)

_Abbildung 3 – wichtige Kategorien für Teams und Skype für Business Online-Bereitstellung_

Die folgende Grafik werden die Aufgaben erläutert, die Sie für jede Kategorie ausführen müssen. Es wird empfohlen, dass Sie diese Aufgaben einmal pro Woche mindestens ausgeführt.

Der ersten dieser Aufgaben Ausführung dauert aufwändiger als nachfolgende Iterationen, da viele dieser Kategorien erfordern, dass Sie Ihre Bereitstellungskonfigurationen auf Gültigkeit überprüfen. Nachdem Sie den Status aus, indem Sie die von die Ihnen definierten Ziele meeting erreicht haben, helfen diese Aufgaben Ihnen bei diesem Zustand verwalten.

#### <a name="service-management-tasks"></a>Service-Management-Aufgaben

In einer Cloud-First-Welt müssen Sie bestimmte Verwaltungsaufgaben Service zum Verwalten von hochwertigen benutzerumgebungen ausführen. Diese Aufgaben im Bereich von sicherstellen, dass ausreichend Bandbreite, um den Dienst zu erreichen, ohne eine Internetlinks, validieren, Dienstqualität (QoS) auf alle verwalteten Netzwerks Bereiche ist und – und schließlich – [Griff Office 365 IP-Bereiche auf Firewalls](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Netzwerkaufgaben

Es gibt zwei Kategorien von Netzwerk-Tasks: Zuverlässigkeit und Qualität. Zuverlässigkeit konzentriert sich auf Messen der Fähigkeit des Benutzers tätigen erfolgreich und in Verbindung bleiben. Qualität konzentriert sich auf die aggregierten Telemetrie vom Client des Benutzers, während und nach Beendigung des Anrufs an Teams und Skype für Business Online gesendet.

Wichtige Auswirkung auf die, Zuverlässigkeit Benutzerinteraktion hat, angegeben, beginnen bewerten und Untersuchen von diese Metriken vor Qualität.

#### <a name="endpoints-tasks"></a>Endpunkte Aufgaben

Die Hauptaufgabe in dieser Kategorie ist wird überprüft, welche Clientversionen Skype für Unternehmen ausgeführt werden, auf dem desktop Builds aus den letzten sechs Monaten, um sicherzustellen, dass Benutzer die Vorteile der kontinuierlichen Optimierungen versucht, der Skype für Business desktop Client abrufen. Darüber hinaus Dies vereinfacht die allgemeinen Verwaltungsaufgaben von Client und stellt ein einheitliches Benutzererlebnis.

Der anderen wichtige Bereich ist monitoring, welche Geräte in Ihrer Bereitstellung betroffen sind und die Verwendung von zertifizierte Geräte bieten die beste benutzerumgebung gesteuerter.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt sind, und durch die Azure Content Delivery Network automatisch aktualisiert, und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.


## <a name="using-the-reports"></a>Verwenden die Berichte

In diesem Abschnitt werden die Grundlagen der Arbeit mit CQD beschrieben. Anleitung erhält für den folgenden Themen:

-   Suchen die Mandanten-ID

-   Berichten über Teams im Vergleich zu Skype für Unternehmen

-   Zuerst im Vergleich zur zweiten Klassifikationen

-   Dimensionen und Measures Filter

-   Datenströme im Vergleich zu Anrufen

-   Gut, schlecht und nicht klassifizierte Anrufe

-   Erste Schritte mit CQD

-   Bearbeiten von Berichten in CQD

-   Filtern von Berichten in CQD

Ausführlicheren Schulungen und Ressourcen finden Sie im [Anhang](#other-resources).

### <a name="tenant-id"></a>Mandanten-ID

Einige Berichte CQD erfordern, dass Sie einen Filter für Ihre Mandanten-ID einschließen Daran CQD Daten aggregiert ist federated Teilnehmer Telemetrie enthalten.
Obwohl dies wertvolle beim Analysieren der Anrufe schlechter Qualität Metriken nachweisen kann, erfordern Client- und Gerätefunktionen Berichte das Filtern von Daten an einen bestimmten Mandanten federated Teilnehmer Telemetrie ausgeschlossen. Wenn Sie Ihre Mandanten-ID nicht kennen, können Sie eine der folgenden Methoden verwenden, sie zu finden sind.

Erforderliche Berechtigungen

-   Globalen Administratorrolle

-   Skype für Business Administratorrolle

#### <a name="azure-ad-portal"></a>Azure AD-Portal

1.  Melden Sie sich bei des Microsoft Azure-Portals an:<https://portal.azure.com>

2.  Wählen Sie **Azure Active Directory**aus.

3.  Wählen Sie unter **Manage** **Eigenschaften**aus. Die Mandanten-ID wird in das **Verzeichnis-ID** angezeigt.

#### <a name="azure-powershell"></a>Azure PowerShell

1.  [Installieren des Microsoft Azure PowerShell Service-Management-Moduls](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Öffnen Sie ein Befehlsfenster Azure PowerShell und führen Sie das folgende Skript, indem Sie bei entsprechender Aufforderung Ihre Office 365-Anmeldeinformationen eingeben:  
    **Anmeldung-AzureRmAccount**

3.  Die Mandanten-ID wird in der Ausgabe aufgeführt.

#### <a name="skype-for-business-online-admin-center"></a>Skype für Business Online Admin Center

1.  Gehe zu<https://portal.office.com>

2.  Melden Sie sich mit Ihrer Organisation Administratorkonto eines Mandanten.

3.  Wählen Sie **Skype für Unternehmen** unter **Admin Center**aus.

4.  Die Mandanten-ID wird als **Organisations-ID** auf der Seite Willkommen aufgelistet.

#### <a name="skype-for-business-online-using-powershell"></a>Skype für Business Online mithilfe von PowerShell

1.  [Verbinden mit Skype für Unternehmen Online über die PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Führen Sie den folgenden Befehl aus:  
    **.Tenantid (Get-Cstenant)**

3.  Die Mandanten-ID wird als GUID angezeigt.

### <a name="teams-vs-skype-for-business"></a>Teams im Vergleich zu Skype für Unternehmen

CQD kann Teams und Skype für Business Telemetrie melden. Möglicherweise gibt es jedoch vorkommen, dass Sie einen Bericht betrachten Teams Telemetrie getrennt von Skype für Unternehmen entwickeln möchten.

#### <a name="summary-reports"></a>Zusammenfassungsberichte

Um die Seite Zusammenfassungsberichte betrachten nur Teams oder Skype für Unternehmen zu ändern, wählen Sie das **Produktfilter** Dropdown-Menü vom oberen Rand des Bildschirms, und wählen Sie dann das gewünschte Produkt aus.

![Screenshot des Dashboards Qualität aufrufen ein Dropdown-Menü die Option zum Filtern nach Arbeitslast mit widerspiegelt.](media/quality-of-experience-review-guide-image4.png)

_Abbildung 4: Auswählen eines Filters Produkt_

#### <a name="detailed-reports"></a>Ausführliche Berichte

Fügen Sie des Filters **Teams ist** mit dem Bericht hinzu, und legen Sie es auf True oder False, um einen detaillierten Bericht zu filtern. Weitere Informationen finden Sie unter [Bearbeiten Berichte](#editing-reports) weiter unten in diesem Abschnitt.

![Screenshot des Dashboards Qualität rufen Sie mit der Dateneinheit, die einen detaillierten Bericht hinzugefügt werden kann.](media/quality-of-experience-review-guide-image5.png)

_Abbildung 5: Hinzufügen eines Microsoft-Teams Filters in einem Bericht_

### <a name="dimensions-measures-and-filters"></a>Dimensionen und Measures Filter

Eine wohlgeformte CQD Abfrage enthält alle drei der folgenden Parameter:

-   **Dimension:** Wie soll ich auf die Daten von PivotTables.

-   **Measure:** Was ich melden möchten.

-   **Filter:** Wie sollen das Dataset zu reduzieren, die, das die Abfrage zurückgibt.

Eine andere Möglichkeit, dies ist eine Dimension ist der Grouping-Funktion, ein Measure befinden sich die Daten, die, denen ich interessant, und ein Filter ist wie ich möchte die Ergebnisse auf diejenigen zu beschränken, die für eine Abfrage relevant sind.

Ein Beispiel für eine Abfrage wohlgeformt ist "meinen Status schlechter Datenströme [Measure] durch Subnetz [Dimension] für das Erstellen von 6 [Filter]."

Weitere Informationen finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm).

Dimensionen, Measures und Filter für die Berichte in den CQD Vorlagen verwendet finden Sie im [Anhang](#CQD-training).

### <a name="first-vs-second"></a>Zuerst im Vergleich zu Sekunde 

Viele der Dimensionen und Measures in CQD werden als erste oder zweite klassifiziert.
CQD nicht Anrufer/angerufenen Felder verwenden – diese Waren umbenannte _ersten_ und _zweiten_ , da sind dazwischenliegende Schritte zwischen dem Anrufer und des angerufenen. Die folgende Logik legt fest, welcher am Datenstrom oder Anruf beteiligte Endpunkt als erster Endpunkt bezeichnet wird:

-   Zuerst wird immer Endpunkt eines Servers (Konferenzserver, Vermittlungsserver usw.), wenn ein Server in der Stream oder Anruf beteiligt ist.

-   Zweitens werden immer ein Clientendpunkt, wenn der Stream zwischen zwei Serverendpunkten ist.

-   Wenn beide Endpunkte den gleichen Typ, sind die Wahl, der zwischen dem ersten ist basiert auf internen Reihenfolge der Benutzer-Agent Kategorie. Damit wird eine konsistente Anordnung sichergestellt.

Weitere Informationen zum Bestimmen des ersten oder zweiten Endpunkts, wenn sie beide identisch sind finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream im Vergleich zu Anrufen

Sie verstehen des Unterschieds zwischen eines Anrufs und einem Stream ordnungsgemäß auswählen, welche Dimensionen oder Measures, die Sie in CQD angezeigt werden sollen.

**Stream:** Ein Datenstrom zwischen nur zwei Endpunkte vorhanden ist. Es ist nur ein Stream-Objekt für jede Richtung und zwei Datenströme sind erforderlich für die Kommunikation. Datenströme eignen sich für die Analyse der Gebäude oder Netzwerke. In einigen Fällen werden Anruf und Stream in den Namen (beispielsweise Anruf Setup Stream oder Anruf verworfen Stream) verwendet.
Diese werden weiterhin als einzelne Datenströme klassifiziert.

**Aufrufen:** Ein Anruf ist eine Gruppierung aller Streams aus allen Teilnehmern. Umfasst ein Anruf – mindestens – zwei Datenströme. Ein einzigen Aufruf müssen zwei Teilnehmern mit mindestens einem Stream-Objekts. Anrufe eignen sich für die Analyse der Trends über einen Zeitraum.

Weitere Anleitungen gibt an, ob die Dimension oder Measure eines Anrufs oder eines Stream-Objekts verweist finden Sie unter [Dimensionen und Measures in CQD verfügbar](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Gut, schlecht und nicht klassifizierte Anrufe

Ein Aufruf ist entweder als gut, schlecht oder nicht klassifizierte kategorisiert. Betrachten wir kurz jeweils ausführlich behandelt.

**Gut oder schlecht:** Gespräch gut oder schlecht besteht aus einem Anruf, der einen kompletten Satz von Kriterien Service, enthält, für die ein vollständiger QoE-Bericht generiert wurde.
Bestimmen, ob ein Anruf gut oder schlecht ist wird beschrieben [Weiter oben in diesem Handbuch](#pcr).

**Nicht klassifizierte:** Ein nicht klassifizierter Anruf enthalten keine umfassende Auswahl an Service Metriken. Dies sind häufig kurze Anrufe – normalerweise weniger als 60 Sekunden – wobei Durchschnittswerte konnte nicht berechnet werden und ein QoE-Bericht wurde nicht generiert.

### <a name="access-cqd-online"></a>Access CQD Online

Sie können auf zwei Arten CQD zugreifen.

-   Wechseln Sie zu <https://cqd.lync.com>.

-   Wechseln Sie zu **Skype für Business Administrationscenter** \> **Extras**, und wählen Sie den Link zur CQD, wie unten dargestellt.

![Screenshot, der zeigt "Tools" in den linken Navigationsbereich und den Link zu "Skype für Business Online aufrufen Qualitätsdashboard" ausgewählt ausgewählt.](media/quality-of-experience-review-guide-image6.png)

_Abbildung 6 – zugreifen auf CQD über die Skype für Business Administrationscenter_

### <a name="getting-started"></a>Erste Schritte

Wenn Sie zuerst CQD durchsuchen, sehen Sie auf der Seite Zusammenfassung Berichte. Die meisten der Berichte in diesem Handbuch beschrieben sind benutzerdefinierte ausführliche Berichte. Erste Schritte mit der ausführliche Berichte, wählen **Zusammenfassung Berichte** am oberen Rand der Seite, und wählen Sie dann **Ausführliche Berichte**.

![Screenshot von der Qualitätsdashboard aufrufen Depcting der verschiedenen Arten von Berichten, die verfügbar sind.](media/quality-of-experience-review-guide-image7.png)

_Abbildung 7: Navigieren zum ausführliche Berichte_

Die ausführliche Berichte Seite in CQD sieht wie in der nachfolgenden Abbildung.

![Screenshot der Seite detaillierten Bericht in CQD und die verschiedenen Elemente, die einen Bericht bilden.](media/quality-of-experience-review-guide-image8.png)

_Abbildung 8: ausführliche Berichtsseite_

1.  Bereich "Zusammenfassung" zeigt Kontext für den Bericht ein, der auf der rechten Seite angezeigt wird.

2.  Sie können **Bearbeiten** im Bereich "Zusammenfassung" auf Bericht-Ebene-Eigenschaften (einschließlich y-Achse Höhe) festlegen auswählen.

3.  Die Breadcrumb-Leiste hilft Benutzern bei ihrer aktuellen Position in der Berichtshierarchie zu identifizieren.

4.  Berichte, die ist der untergeordneten Berichte, werden mit einer blauen Link angezeigt. Wenn Sie den Link auswählen, können Sie nach unten zu den untergeordneten Berichte anzeigen.

Zeigen Sie auf die Balkendiagramme und Trendlinien detaillierte Werte angezeigt. Zeigt der Bericht, den Fokus hat im Aktionsmenü: **Bearbeiten**, **Wenn Sie den Klon**, **Löschen**, **herunterladen**und **Berichtsstruktur exportieren**.

### <a name="editing-reports"></a>Bearbeiten von Berichten

Beim **Bearbeiten** eines Berichts im Menü Aktion auswählen, werden Sie Abfrage-Editor zu öffnen. Jeder Bericht wird durch eine Abfrage unterstützt. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Abfrage-Editor ist eine Benutzeroberfläche zur Bearbeitung diese Abfragen zusätzlich zu den Optionen für die Anzeige für den Bericht, wie in der folgenden Abbildung dargestellt.

![Screenshot der Seite detaillierten Bericht in CQD und die verschiedenen Elemente, die einen Bericht bilden, wenn der Bericht bearbeitet werden.](media/quality-of-experience-review-guide-image9.png)

_Abbildung 9: Bericht-Editors_

1.  Wählen Sie Dimensionen und Measures Filter im linken Bereich. Verweisen auf einen vorhandenen Wert zeigt eine Schaltfläche zum Schließen (**X**) Sie auswählen können, um den Wert zu entfernen.

    1.  Indem Sie die Dimension oder Measure auswählen, können Sie den Titel durch Bearbeiten im Feld **Titel** ändern. Sie können auch die Reihenfolge ändern, indem Sie die blaue nach oben oder nach unten weisenden Pfeil im oberen Bereich auswählen.

    2.  Auswählen (**+**) neben einer Überschrift Öffnet das Dialogfeld für eine neue Dimension, Measure oder Filter hinzufügen.

    3.  Geben Sie die ersten Buchstaben der Dimension, Measure oder Filter in der **Hier finden Sie eine** zum Filtern der Liste für die Suche einfacher dar.

2.  Der obere Ausschnitt zeigt Optionen zur Anpassung des Diagramms.

3.  Der Abfrage-Editor zeigt eine Vorschau des Berichts.

4.  Verwenden Sie das **Bearbeiten** am unteren Rand des Bildschirms zum Erstellen oder bearbeiten eine detaillierte Beschreibung des Berichts.

### <a name="filtering-reports"></a>Filtern von Berichten

Die bereitgestellten Vorlagen umfasst mehrere integrierte Abfragen und Filter im Bericht. In den folgenden Abschnitten wird beschrieben, die am häufigsten verwendeten Filter in allen Vorlagen verwendet.

#### <a name="cqd-filter"></a>CQD filter

Sie können die CQD Filter oder URL-Filter verwenden, um jedes Berichtsabfrage vorübergehend zu filtern. Der am häufigsten verwendete CQD Filter, den Sie verwenden ist zum Filtern von Berichten auszuschließende federated Teilnehmer Telemetrie. Es wird empfohlen, dass Sie diesen Filter Lesezeichen, damit es die Standardansicht zu. Ausschließen von föderierten Data aus CQD Berichte ist nützlich, wenn Sie sind Korrigieren von verwalteten Gebäude oder Netzwerken, in dem zusammengestellten Daten Ihres Berichts beeinflussen können.

Um einen Filter CQD in der Adressleiste des Browsers zu implementieren, fügen Sie die folgenden am Ende der URL:

/Filter/ [AllStreams]. [Zweiten Mandanten-Id] \|[IHRE MANDANTEN-ID hier]

**Beispiel:**  
https://cqd.lync.com/cqd/\#/1234567/2018-02/filter/[AllStreams]. [Zweiten Mandanten-Id] \|[TENANTID] & Mandanten = TENANTID

> [!NOTE]
> URL-Beispiel oben wird nur die visuelle Darstellung. Verwenden Sie die standardmäßige CQD Verknüpfung von <https://cqd.lync.com>.

#### <a name="query-filters"></a>Abfragefiltern

Abfragefiltern werden mithilfe des Bericht-Editors implementiert. Diese Filter werden verwendet, um die Anzahl von Datensätzen zurückgegebene CQD, daher minimieren Gesamtgröße des Berichts zu verringern. Dies ist insbesondere dann sinnvoll für nicht verwalteten Netzwerken herausfiltern.
Die unten aufgeführten Filter verwenden regulärer Ausdrücke (RegEx).

_Tabelle 3 - Abfragefilter_

| Filter               | Beschreibung          | Filter-Abfragebeispiel CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Leere Werte         | Einige Filter haben nicht die Option zum Filtern von leere Werte. Um leere Werte manuell zu filtern, verwenden Sie den Ausdruck leeren, und setzen Sie den Filter auf gleich oder ungleich, je nach Ihren Anforderungen.                                                                                                                             | Erstellen von Sekunde Name \< \> \^ \\s\*\$                       |
| Beliebte home Subnetze | Ohne eine Datei gültige Erstellen von verwalteten von nicht verwalteten Netzwerken trennen werden Heimnetzwerken in den Berichten einbezogen werden. Diese private Subnetze sind außerhalb des Bereichs des Steuerelements die und schnell aus einem Bericht ausgeschlossen werden. Beliebte home Subnetze, sind gemäß Definition in diesem Handbuch 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweite Subnetz \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Innerhalb im Vergleich zu außen   | Zum Filtern von Berichten für (inside) verwaltetem oder nicht verwaltetem (externe) verwendet. Die verwaltete CQD-Vorlage ist bereits vorkonfigurierten mit diesen filtern.                                                                                                                                                                                | Sekunde innerhalb Corp = innerhalb                               |

#### <a name="report-filters"></a>Filter im Bericht

Filter im Bericht werden durch einen Filter hinzufügen, mit dem gerenderten Bericht entweder im Bericht-Editor oder direkt mit dem Bericht implementiert. Die folgenden Berichte Filter werden in der Vorlage verwendet.

_Tabelle 4 – Filter melden_

| Filter     | Beschreibung                            | Beispiel für einen Filter CQD Bericht         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Beginnen Sie mit der Jahr zuerst, dann Monat. | 2017-10                           |
| Alphabetische | Filter für alle alphabetischen Zeichen. | [a-Z]                             |
| Numerische    | Filter für eine beliebige numerischen Zeichen.    | [0-9]                             |
| Prozentsatz | Filtert nach Prozentsatz.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importieren Sie die CQD-Vorlagen

Dieses Handbuch umfasst [zwei curated CQD Vorlagen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Diese Vorlagen die Verwendung von CQD beschleunigen und bieten Ihnen die Möglichkeit, schnell nutzen CQDs-Funktionen zu einer Beeinträchtigung der Benutzer Teams oder Skype Business wünschen. Die Vorlage alle Netzwerke optimiert gegenüber einem Gebäude entwickelt Datendatei, kann verwendet werden, während der Arbeit in Richtung sammeln und Hochladen von Erstellen von Informationen in CQD, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (. CQDX) in CQD Online**

1.  Wechseln Sie zu <https://cqd.lync.com>.

2.  Authentifizieren Sie mithilfe Ihrer Office 365-Administratoranmeldeinformationen ein.

> [!NOTE]
> Sie benötigen die Office 365 globaler Administrator Skype für Business Administrator oder Berichtleser-Rolle auf CQD zuzugreifen. 


3.  Wählen Sie im Menü **Zusammenfassung Berichte** am oberen Rand der Seite aus, und wählen Sie dann **Ausführliche Berichte**.

4.  Wählen Sie im Bereich "Zusammenfassung" **Importieren**aus. Besuchen Sie die CQDX Speicherort gespeichert, wählen Sie die Vorlage CQDX, und wählen Sie dann auf **Öffnen**.

5.  Nachdem die Vorlage hochgeladen wurde, wird ein Popup-Fenster Anzeigen der Meldung "Bericht Importvorgang war erfolgreich." Wählen Sie **OK.**

![Screenshot des ein Popup-Fenster, das dem Benutzer benachrichtigt, dass die Vorlage erfolgreich importiert wurde.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Wiederholen Sie die Schritte 4 und 5 für die zweite CQD-Vorlage.

> [!NOTE]
> Die Vorlagen CQD werden pro Benutzer importiert. Wenn weitere Benutzer den Bericht verwenden müssen, müssen sie anmelden und die Vorlagen in ihrer Instanz CQD importieren. 


## <a name="building-mapping"></a>Erstellen von Zuordnung

In einer Teams oder Skype für Business Online-Bereitstellung, sind alle Clients extern.
Die hat der Auswirkung, dass alle Clients sind standardmäßig gemeldeten als außerhalb in CQD Online, unabhängig davon, ob der Client eine interne Unternehmensnetzwerk verbunden wurde.

Wenn Sie die Anrufqualität verwenden, müssen Sie den Speicherort eines Clients kennen und, ob eine Verbindung mit einem zur Verwaltung oder ein Netzwerk hergestellt wurde Sie nicht verwalten – der Annahme, dass Sie nur Netzwerke verbessert werden können, können Sie verwalten.
Hochladen von Netzwerk- und Erstellen von Informationen zu CQD Online, können Sie CQD, um zu bestimmen, ob ein Client zu einem internen Netzwerk im Unternehmen/verwaltet oder mit einem externen/nicht verwaltete Netzwerk verbunden wurde.

### <a name="building-data-file-structure"></a>Erstellen von Daten-Dateistruktur

Das Format der Datei, die Sie hochladen muss die folgenden Anforderungen, übergeben die Überprüfung vor dem Hochladen erfüllen.

-   Die Datei muss eine TSV-Datei, was bedeutet, dass für jede Zeile jeder Spalte durch ein Tabstoppzeichen getrennt ist, oder eine CSV-Datei, in der jede Spalte durch ein Komma getrennt ist.

-   Die Datei darf nicht größer als 50 MB sein.

-   Der Inhalt der Daten Datei *Tabellenüberschriften nicht berücksichtigt*. Die erste Zeile der Datendatei muss mit anderen Worten, realen Daten, nicht Spaltenüberschriften wie "Netzwerk." sein.

-   In jeder Spalte kann der Datentyp nur eine Zeichenfolge, eine Zahl oder der boolesche Datentyp sein. Wenn der Datentyp Zahl ist, muss der Wert einen numerischen Wert; Wenn es Bool ist, muss der Wert 0 oder 1.

-   Für jede Spalte ist der Datentyp String, die Daten können leer sein (jedoch weiterhin durch eine entsprechende Trennzeichen, die ein Tabulatorzeichen oder ein Komma getrennt werden müssen). Dadurch wird dem Feld eine leere Zeichenfolge zugewiesen.

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

Supernetting, so genannte Classless Inter-Domain Routing (CIDR), können Sie anstelle der einzelnen Subnetze definieren. Eine *Supernetting* ist eine Kombination von mehrere Subnetze, die ein routing Präfix freigeben. Anstatt einen Eintrag für jedes Subnetz, können Sie die Supernetz/CIDR-Adresse verwenden. Supernetting wird unterstützt, aber es wird nicht empfohlen, dessen Verwendung.

Beispielsweise Contoso marketing erstellen die folgenden Subnetze besteht:

-   10.1.0.0/24 – Erdgeschoss

-   10.1.1.0/24 – zweiter Stock

-   10.1.2.0/24 – Dritter Stock

-   10.1.3.0/24 – vierten floor

Anstatt einen Eintrag für jedes Subnetz, können die Supernetz/CIDR-Adresse – in diesem Beispiel 10.1.0.0/22.

-   Netzwerk = 10.1.0.0

-   Netzwerk-Bereich = 22

Hier sind einige Punkte zu berücksichtigen sind vor der Implementierung von Supernetting:

-   Supernetting weniger Zeit voraus, aber es geht aber vom Umfang der Daten zu reduzieren. Nehmen wir an, dass ein Qualität Problem büroumzüge Subnetz 200.1.2.0 vorhanden ist. Wenn Sie Supernetting implementiert, werden nicht Sie wissen, wo sich das Subnetz im Gebäude befindet oder welche Art von Netzwerk (beispielsweise eine Übungseinheit) ist. Wenn Sie hatte definiert alle Subnetze für ein Gebäude und Floor Standortinformationen hochgeladen, würden Sie diese Unterscheidung finden Sie unter sein.

-   Es ist wichtig, um sicherzustellen, dass die Supernetz/CIDR-Adresse richtig ist und unerwünschte Subnetze abfangen nicht zur Verfügung.

-   Supernetting kann in einer Zuordnung erstellen von mit 8-Bit-Version auf 28-Bit-Maske verwendet werden.

-   Es ist häufig 192.168.0.0 in Daten suchen. Für viele Organisationen bedeutet dies, dass der Benutzer zu Hause ist. Für andere ist dies das IP-Adressschema für eine Zweigstelle. Wenn Ihre Organisation Büros, die diese Konfiguration verwenden verfügt, fügen Sie keine es in der Datei zum Erstellen von unverändert schwierig home und internen Netzwerken mithilfe von gemeinsamen Subnetze unterscheiden.

> [!IMPORTANT]
> Der Netzwerkbereich kann verwendet werden, um eine Supernetting darzustellen. Erstellen alle neuen Daten Dateiuploads wird für überlappenden Bereiche überprüft werden soll. Wenn Sie eine Datei zum Erstellen von zuvor hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und Hochladen erneut aus, um alle überlappt identifizieren und beheben Sie das Problem. Alle Überlappung in zuvor hochgeladenen Dateien möglicherweise falschen Zuordnungen von Subnetzen zu Gebäude in den Berichten. 


#### <a name="vpn"></a>VPN

Die Daten Quality of Experience (QoE), die Clients zu Office 365 senden – wobei stammende CQD Daten aus ist also – ein VPN-Flag enthält. Dieses Kennzeichen nutzt VPN-Anbieter reporting Windows, dass die VPN-Netzwerkadapter registriert einen RAS-Adapter ist jedoch. Nicht alle VPN-Anbieter registrieren ordnungsgemäß RAS-Adapter. Aus diesem Grund können Sie nicht die integrierte VPN-Abfragefilter verwenden können. Es gibt zwei Ansätze für die Einbindung der VPN-Subnetze im Gebäude Informationsdatei.

-   Definieren Sie einen **Netzwerkname** , indem Sie mit dem Text "VPN" in diesem Feld für VPN-Subnetze.

![Screenshot eines Berichts in der aufrufen Qualität-Dashboard, das zum Erstellen einer VPN-Subnetz definiert](media/quality-of-experience-review-guide-image10.png)

_Abbildung 10: Netzwerkname mit VPN_

-   Definieren Sie einen **Namen erstellen** , indem Sie mit dem Text "VPN" in diesem Feld für VPN-Subnetze.

![Screenshot eines Berichts im Aufrufen Qualität-Dashboard, die definiert, wie eine Definition Erstellen von erstellen, die ein VPN-Subnetz umfasst.](media/quality-of-experience-review-guide-image11.png)

_Abbildung 11: VPN verwenden Sie zum Erstellen von Namen_

> [!IMPORTANT]
> Bestimmte VPN-Implementierungen meldet nicht genau Subnetzinformationen. In diesem Fall in Ihre Berichte, empfehlen wir, wenn Sie die Datei zum Erstellen von anstelle eines Eintrags für das Subnetz ein VPN Subnetz hinzufügen fügen Sie separate Einträge für jede Adresse als ein separates 32-Bit-Netzwerk im VPN-Subnetz hinzu. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Beispielsweise müssen Sie anstelle einer Zeile für 172.16.18.0/24, 253 Zeilen, mit einer Zeile für jede Adresse aus 172.16.18.1/32 über 172.16.18.254/32, inklusive.


> [!NOTE]
> VPN-Verbindungen bekanntermaßen die Netzwerkschnittstelle unter Umständen nicht richtig wie verkabelt, wenn die zugrunde liegende Verbindung Internet ist kabellos. Beim Betrachten der Qualität über VPN-Verbindungen können nicht vorausgesetzt, dass der Verbindungstyp genau identifiziert wurde.

### <a name="uploading-building-information"></a>Informationen zum Erstellen von hochladen

Das Dashboard CQD Zusammenfassung Berichte umfasst eine Seite **Mandanten Daten hochladen** , durch Auswählen des **Mandanten Datenupload** Link-Tags in der oberen rechten Ecke (Design für das Zahnradsymbol) zugegriffen. Auf dieser Seite wird für Administratoren ihre eigenen Informationen wie die Zuordnung von IP-Adresse und geografische Informationen, zuordnen jeder drahtlosen Zugriffspunkt und die MAC-Adresse, hochladen und so weiter.

1.  Wechseln Sie zu Online CQD, indem Sie auf <https://cqd.lync.com>.

2.  Wählen Sie in der oberen rechten Ecke der Zahnradsymbol aus, und wählen Sie auf der Seite **Zusammenfassung Berichte** **Mandanten Hochladen von Daten** .

![Screenshot eines Dialogfelds im Dashboard angezeigt wird, während Daten hochgeladen werden Qualität aufrufen.](media/quality-of-experience-review-guide-image12.png)

_Abbildung 12 - Menü Mandanten Daten hochladen_

1.  Alternativ ist dies Ihre zum ersten Mal CQD besuchen, werden Sie aufgefordert, Erstellen von Daten hochzuladen. Sie können **Jetzt hochladen** , navigieren zur Seite **Mandanten Datenupload** schnell auswählen.

![Screenshot des Banner in das Aufrufen Qualität-Dashboard, das einen Benutzer das Erstellen von Datenupload benachrichtigt.](media/quality-of-experience-review-guide-image13.png)

_Abbildung 13: Erstellen von Daten hochladen banner_

1.  Wählen Sie **Durchsuchen** , um eine Datendatei auszuwählen, auf der Seite **Mandanten Hochladen von Daten** .

2.  **Startdatum** Geben Sie an, nach dem Auswählen einer Datendatei, und geben Sie optional ein Enddatum.

3.  Nach dem **Startdatum**auswählen, wählen Sie auf die Datei in die CQD hoch **Hochladen** . <br><br>Bevor Sie die Datei hochgeladen wurde, wird es überprüft. Wenn die Überprüfung fehlschlägt, wird eine Fehlermeldung angezeigt anfordern, dass Sie die Datei zu korrigieren. Die folgende Abbildung zeigt einen Fehler auftritt, wenn die Anzahl der Spalten in der Datendatei nicht korrekt ist.

![Screenshot eines Dialogfelds in das Aufrufen Qualität-Dashboard, das eine Fehlermeldung beim Importieren von Daten zum Erstellen von beschreibt.](media/quality-of-experience-review-guide-image14.png)

_Abbildung 14: Building Fehler beim Upload von Daten_

4.  Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.

> [!NOTE]
> Es kann zum Abschließen der Verarbeitung der Datei zum Erstellen von bis zu vier Stunden dauern. <br><br> Wenn Sie eine Datei zum Erstellen von bereits hochgeladen haben und müssen Subnetze hinzu, die möglicherweise entgangene oder ausgeschlossen werden, wurden die ursprüngliche Datei ändern, indem Sie die neue Subnetze hinzufügen, entfernen Sie die aktuelle Datei und wieder neu bearbeitete Datei hochladen. Es kann nur eine aktive Erstellen von CQD-Datendatei. 

### <a name="missing-subnets"></a>Fehlende Subnetze

Nach dem Erstellen von Informationen für verwaltete Netzwerke hochladen, sollte jeder verwalteten Netzwerks eine Zuordnung erstellen. Jedoch nicht immer die Groß-/Kleinschreibung; in der Regel werden einige Subnetze nicht eingehalten. In diesem Abschnitt wird das Überprüfen dieser fehlenden Netzwerke behandelt.

Wechseln Sie zur Seite **Ausführliche Berichte** in CQD Online, und navigieren Sie zu der **Fehlende Subnetz Bericht** in die CQD Vorlagen enthalten. Dies stellt alle Subnetze mit 10 oder mehr audio-Streams, die nicht im Gebäude definiert sind-Datendatei. Stellen Sie sicher, dass es keine verwalteten Netzwerke in dieser Liste sind. Wenn Subnetze nicht vorhanden sind, aktualisieren Sie die ursprünglichen Erstellen von Daten Datei und erneutes Hochladen auf CQD.

> [!IMPORTANT]
> Sie müssen Ihre Mandanten-ID als Abfragefilter für die **Zweite Mandanten-ID** für diesen Bericht Filtern des Berichts, um nur die Daten des Unternehmen Mandanten anzuzeigen hinzufügen. Andernfalls wird der Bericht federated Subnetze anzeigen.

> [!NOTE] 
> Achten Sie darauf, dass Berichtsfilter Monat-Jahr mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den Filter **Monat-Jahr** -Bericht, um den neuen Standardmonat zu speichern.                                                  |

![Bericht mit Subnetze in der Datei CQD Erstellen von nicht enthalten, die Verwendung anzeigen.](media/quality-of-experience-review-guide-image15.png)

_Abbildung 15: Erstellen von Bericht fehlt_

## <a name="reliability-investigations"></a>Zuverlässigkeit Untersuchungen

Der erste Schritt zum Verbessern der Qualität ist den Status der audiozuverlässigkeit in der gesamten Organisation bewerten. Da audiozuverlässigkeit entscheidend für eine positive Benutzeroberfläche zur Verfügung steht, starten wir mit den zwei Komponenten, die Zuverlässigkeit messen:

1.  **Aufrufen Setupfehler:** Sitzung konnte nicht hergestellt werden.

2.  **Rufen Sie die Drop-Fehler:** Sitzung wurde eingerichtet und unerwartet beendet

In diesem Abschnitt werden Methoden zum Untersuchen Sie beide Bereiche behandelt.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt. Die Beschreibung der einzelnen Berichts Weitere Informationen finden.


### <a name="call-setup"></a>Verbindungsaufbau

Priorisieren Sie korrigieren von Setup anruffehlern in diesem Bereich zuerst, da diese Fehler erhebliche negative Auswirkungen auf die Benutzeroberfläche vorhanden ist.

Zunächst die Bewertung des Prozentsatz der gesamten Anruf Setupfehler für die Organisation der Überprüfung, und klicken Sie dann priorisieren Bereiche der Untersuchung basierend auf den höchsten Prozentsatz von erstellen oder im Netzwerk.

#### <a name="call-setup-failures-overall"></a>Rufen Sie allgemeine Setupfehler

In diesem Diagrammbericht zeigt die Gesamtsumme der erfolgreichen Aufruf einrichten, und rufen Setupfehler über einen Zeitraum. Zeigen Sie auf eine der Spalten auf die einzelnen Werte, anzuzeigen, wie in der folgenden Abbildung dargestellt.

![Screenshot eines Diagramms, das zeigt, Prozentsatz der Audio aufrufen Stream Fehler bei der Installation](media/quality-of-experience-review-guide-image16.png)

_Abbildung 16 - Audiozuverlässigkeit - Anruffehlern Stream Setup_

##### <a name="analysis"></a>Analyse

In diesem Bericht werden Ihrer Organisation Audioanruf-Setup-Syntax und Fehler über einen Zeitraum angezeigt. Mithilfe dieses Berichts können Sie die folgenden Fragen beantworten und Ihre weitere Vorgehensweise bestimmen:

1.  Was ist der Prozentsatz der gesamten Anruf Setup Fehler für den aktuellen Monat?

2.  Ist insgesamt Anruf Setup Fehler Prozentsatz unter oder über die Metrik definierten Ziel?

3.  Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Ausfall Trend erhöhen, steady, oder verringern?

Die Informationen in diesem Bericht informiert die Geschichte des wie oft Ihrer gesamten Anruf Installationen in Ihrer Organisation ein Fehler auftritt.

Selbst wenn der vorherigen Antworten Zeit in Anspruch nehmen die untersuchen Weitere mithilfe der enthaltenen untergeordneten Berichte für einzelne Gebäude oder Netzwerke, die möglicherweise Remediation gesucht. Zwar die Fehlerrate insgesamt unterhalb der Ziel-Metrik oft die Fehlerraten für eine oder mehrere Gebäude oder Netzwerke befinden sich über die Metrik und-Wartung benötigen.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Rufen Sie Fehler bei der Installation auf, indem Sie erstellen und Subnetz 

Dieser Tabellenbericht wird verwendet, zu ermitteln und isolieren alle Gebäude oder Netzwerke, die Remediation benötigen.

> [!NOTE]
> Achten Sie darauf, dass Berichtsfilter Monat-Jahr mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie den Filter **Monat-Jahr** -Bericht, um den neuen Standardmonat zu speichern.


![Meldet, dass die Listen Anruf Setup Gründe, erstellen, Netzwerk und Subnetz pro Monat organisiert.](media/quality-of-experience-review-guide-image17.png)

_Abbildung 17: Audio Setupfehler durch die Erstellung oder Subnetz_

##### <a name="remediation"></a>Wartung 

Konzentrieren Sie Ihre Remediation auf Gebäude oder Subnetze abgerufen, die die größte Lautstärke der Fehler Sie zuerst haben, da dies Auswirkungen auf die Benutzeroberfläche maximieren und Ihnen dabei helfen, um schnell die Organisationseinheit anruffehlern Setup zu reduzieren.
Die folgende Tabelle enthält die zwei Gründe für die Setup-Fehler beim Aufrufen von CQD gemeldet.

_Tabelle 6 – Gründe für Setup Anruffehlern_

| Rufen Sie die Ursache für Fehler bei der Installation                       | Typische Ursache                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fehlende Firmware Tiefe Paket Prüfung Ausnahmeregel | Gibt an, dass Netzwerkgeräte entlang des Pfads der Medienpfad daran gehindert, aufgrund von Tiefe Paket Prüfung Regeln hergestellt wird. Dies ist wahrscheinlich durch die Firewall-Regeln wird nicht ordnungsgemäß konfiguriert. In diesem Fall der TCP-Handshake war erfolgreich, aber der SSL-Handshake nicht.               |
| Fehlende Firmware IP-Block Ausnahme-Regel               | Gibt an, dass Netzwerkgeräte entlang des Pfads der Medienpfad daran gehindert, mit dem Office 365-Netzwerk hergestellt wird. Dies kann aufgrund von Proxy oder der Firewall-Regeln wird nicht Gewährung des Zugriffs für IP-Adressen und Ports für Teams und Skype für Business-Datenverkehr verwendet, um ordnungsgemäß konfiguriert sein. |

Nun, wie Sie Ihre Remediation beginnen, können Sie sich in einem bestimmten Gebäude oder Subnetz konzentrieren. Wie in die obigen Tabelle gezeigt wird, werden diese Probleme aufgrund der Firewall oder der Proxyserver Konfigurationen. Überprüfen Sie die Optionen in der folgenden Tabelle für Remediation Aktionen.

_Tabelle 7: nächste Schritte für Anruf Setup Fehler-Wartung_

| Wartung           | Anleitung     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurieren von firewall(s) | Arbeiten mit Ihrem Netzwerkteam, und überprüfen Sie Ihre Konfiguration Firewall(s) anhand [der Liste der Office 365-IP-Adresse](https://aka.ms/o365ips). Stellen Sie sicher, dass die [Medien Subnetze](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) und Ports in der Firewall-Regeln enthalten sind. Stellen Sie sicher, dass die erforderlichen TCP- und UDP-Ports in der Firewall geöffnet werden. Media bevorzugt UDP über TCP an. TCP gilt ein Failback-Protokoll.<br><ul><li>**TCP:** -port 443</li><li>**UDP:** 3478 – 3481 ports</li><ul> |
| Vergewissern Sie sich                | Nutzen Sie die [Microsoft Network Assessment-Tool](https://www.microsoft.com/download/details.aspx?id=53885) aus, um die Konnektivität von der betroffenen Gebäude oder Subnetz mithilfe der Konnektivität Kontrollkästchen-Funktion zu überprüfen.    |


### <a name="call-drop"></a>Rufen Sie die drop

Im Gegensatz zu anruffehlern-Setup, ist kein Code Grund an, warum Fehler abgebrochen aufgetreten ist, die einer bestimmten Problemursachen isolieren erschwert. Verworfene Anrufe, um eine bessere Ursachenanalyse einen abgeleiteten Ansatz bereitzustellen. Korrigieren von Bereichen des Zinsen für Audio und fördern der Verwendung von zertifizierte Geräte für Teams und Skype für Business Patchen von Clients, würden Sie abgelegten anruffehlern so lehnen Sie erwarten.

#### <a name="call-drop-failures-overall"></a>Rufen Sie die Drop-Fehler insgesamt

In diesem Diagrammbericht zeigt die Gesamtsumme der Audiostreams insgesamt Audiostreams gelöscht, und insgesamt Stream getrennt Prozentsatz. Zeigen Sie auf eine der Spalten zur Anzeige der Werte wie in der folgenden Abbildung dargestellt.

![Screenshot des ein Diagramm mit Prozentsatz der Audio aufrufen Datenströme gelöscht.](media/quality-of-experience-review-guide-image18.png)

_Prozentsatz der Abbildung 18 - insgesamt Anruf abgelegten Fehler_

##### <a name="analysis"></a>Analyse

Der Diagrammbericht zeigt Verwendung und Fehlern Ihrer Organisation über einen Zeitraum im Zusammenhang mit setzt aufrufen. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist der aktuelle Anruf insgesamt abgelegten Prozentsatz?

2.  Ist der Prozentsatz insgesamt Drop unterhalb der definierten Ziel Metrik?

3.  Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Ausfall Trend erhöhen, steady, oder verringern?

Die Informationen in diesem Bericht kann anweisen, die Geschichte des wie oft Ihrer gesamten Anruf setzt in Ihrer Organisation ausgeführt werden.

Antworten auf die obigen Fragen unabhängig nehmen die Zeit, überprüfen Sie die Verwendung der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Remediation. Zwar die Drop Gesamtrate unterhalb der Ziel-Metrik oft die Drop-Rate für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und-Wartung benötigt.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Rufen Sie Drop-Fehlern auf, indem Sie erstellen oder Subnetz

Fehler in dieser Tabellenbericht anzugeben, dass der Anruf wurde unerwartet gelöscht und eine negative Benutzeroberfläche zur Verfügung führte. Es gibt zwei-Berichte in der Vorlage, eine für Untersuchen von Konferenz- und das andere für zwei Teilnehmern enthalten.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.


![Meldet, dass die Anzahl von Listen und Prozentsatz Initiale Anrufe erstellen, Netzwerk und Subnetz pro Monat organisiert.](media/quality-of-experience-review-guide-image19.png)

_Abbildung 19 – Audio Anruf abgelegten Fehler durch Erstellen oder Subnetz_

##### <a name="remediation"></a>Wartung

Mit der vorstehenden Tabellenbericht können Sie jetzt "Hotspot" im verwalteten Netzwerk isolieren, in dem Anruf über die definierten Ziel Metrik vorkommen. Konzentrieren Sie sich auf Gebäude oder Netzwerken, in denen die Anzahl der höchste insgesamt Stream Sie zuerst am stärksten beeinträchtigt müssen, Ihre Remediation-Maßnahmen.

Häufige Ursachen für Anruf Ansätzen:

-   Klicken Sie unter bereitgestellte Netzwerk oder Internet Ausgang

-   Keine QoS auf eingeschränkte Netzwerke konfiguriert ist

-   Ältere Clientversionen

-   Verhalten der Benutzer

Nachdem Sie Hotspot erkennen, können Sie [Analytics aufrufen,](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) um Benutzer in das Gebäude für bestimmte Probleme an weiteren Überprüfung nutzen. Anruf Analytics PII-Daten enthält und kann deshalb hilfreich, um weitere mögliche Gründe für den Anruf setzt.

Unabhängig von der nächste Schritt ist es ratsam, dem Helpdesk benachrichtigen, dass es sich bei Auftreten eines Problems mit einem bestimmten Gebäude oder Subnetzen. Auf diese Weise können schnell reagieren auf eingehende Anrufe und Benutzer effizienter selektieren. Gekennzeichnete Benutzer können dann wieder an das Entwicklungsteam zur weiteren Untersuchung gemeldet werden.

Die folgende Tabelle enthält einige allgemeinen Methoden zum Verwalten und Warten von Anruf setzt.

_Tabelle 9: nächste Schritte für Anruf drop-Wartung_

| Wartung                              | Anleitung     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Netzwerk/internet                         | Nun, dass Sie wissen, welche Building betroffen ist, arbeiten Sie mit Ihrem Netzwerkteam Bandbreite an das Gebäude, um festzustellen, ob Probleme mit übermäßiger überwachen. Wenn das Problem in Bezug auf Überlastung des Netzwerks ermittelt werden, sollten Sie die zunehmende Bandbreite für das Gebäude. <br><br>**QoS:** Wenn einer steigenden Bandbreite unmöglich oder kostspielig ist, sollten Sie die Implementierung der QoS. Dadurch wird sichergestellt, dass Media-Pakete im verwalteten Netzwerk oben nicht Mediendatenverkehr priorisiert werden. Auch wenn es gibt keine klare Hinweise, dass die Bandbreite Ursache ist, sollten Sie diese Lösungen:<br><ul><li>[Microsoft-Teams QoS-Anweisungen](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype für Business QoS-Anweisungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Führen Sie eine Netzwerk-Bereitschaft:** Eine Netzwerk-Bewertung enthält Details zur Nutzung der erwarteten Bandbreite, wie bewältigen Bandbreite und Netzwerk ändert, und Netzwerke Methoden für Teams und Skype für Unternehmen empfohlen. Verwenden der obigen Tabelle als Quelle, müssen Sie eine Liste von Gebäude oder Subnetze, die eignen sich für eine Bewertung sind. <br><ul><li>[Microsoft-Teams, Netzwerk-Bereitschaft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype für Business Netzwerk Bereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Tool zur Bewertung der Microsoft Network:** Verwenden Sie dieses Tool für einen einfachen Test der Leistung des Netzwerks, um zu bestimmen, wie gut das Netzwerk für eine Teams ausführen würden oder Skype für Business Online Anruf. Das Tool können Sie die Leistung eines Subnetzes bewerten und überprüfen die Bereitschaft des Netzwerks gegen Microsoft Leistung [Anforderungen](https://aka.ms/performancerequirements).<ul><li>[Laden Sie das Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Clients (Skype für Unternehmen nur Online) | Einige ältere Clients wissen müssen, werden Probleme mit der Zuverlässigkeit Media dokumentiert. Überprüfen Sie die aufrufen Analytics-Berichte aus mehreren betroffenen Benutzer, oder erstellen Sie einen benutzerdefinierten Bericht der Clientversion-Tabelle in CQD in bestimmten Gebäude oder Subnetze mit Fehler insgesamt aufrufen abgelegten % Measure gefiltert. Diese Informationen helfen Ihnen beim verstehen, ob eine Beziehung zwischen Anruf setzt in dieser bestimmten Gebäude und eine bestimmte Version des Clients vorhanden ist.                                                                                                                                                              |
| Geräte                                  | Die meisten Gerätefehler sind aufgrund der Geräte, die für Teams oder Skype für Unternehmen ausgewiesen werden nicht verwenden. Fehler verwenden normalerweise das Format der integrierten Lautsprecher oder Mikrofone, die verwendet werden, oder Earbud/Mikrofon Kombinationen, die mit dem audio 3,5 mm-Anschluss auf einem Gerät verbunden sind. Aktuelle Empfehlung von Microsoft besteht darin, dass alle Benutzer, die auftreten, setzt aufrufen – oder schlecht Anrufe im Allgemeinen – und werden mithilfe von integrierten Geräte oder Treiber werden sollte eine [certified Kopfhörer oder eines Freisprechtelefons](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)bereitgestellt. |
| Verhalten der Benutzer                            | Wenn Sie feststellen, dass weder Netzwerk, Geräte oder Clients behoben werden, sollten Sie ansprechender [Meine Advisor](https://aka.ms/myadvisor) Anleitung bei der Entwicklung einer Strategie für die Einführung, um Benutzer informieren, wie Sie bewährte beitreten und Besprechungen zu beenden. Ein intelligenter Teams und Skype-Benutzer haben eine höhere benutzerfreundlichkeit für alle Teilnehmer in der Besprechung zur Folge. Ein Benutzer, der ihren Laptop in den Energiesparmodus (von der Abdeckung schließen) versetzt, ohne zu verlassen der Besprechung werden als ein unerwarteter Aufruf Drop klassifiziert werden.     |

## <a name="quality-investigations"></a>Qualität Untersuchungen

Im nächste Schritt den Zustand der Audioqualität über die Bereitstellung bewerten ist Audio schlechter aufrufen Verhältnis (PCR), TCP und Proxy Verwendung untersuchen. Es ist wichtig, denken Sie daran, dass CQD Daten bestimmte Ursache nicht enthalten, aber Sie stattdessen wahrscheinlich Problembereiche zu Beginn einer gemeinsame Unterhaltung mit der entsprechenden Teams für Abhilfemaßnahmen bietet.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt. Die Beschreibung der einzelnen Berichts Weitere Informationen finden. 


### <a name="investigate-call-quality"></a>Überprüfen der Anrufqualität

Der Gesamtprozentsatz PCR wird hauptsächlich verwendet, um anzugeben, ob die Organisation definierten audio metrischen Ziele erreicht. Es ist wichtig, beachten Sie, dass, auch wenn der Gesamtprozentsatz im Ziel ist, einige Subnetze oder Gebäuden möglicherweise nicht die definierten Ziele erfüllen und daher weiteren Untersuchung erfordern. Beispielsweise ist der Organisationseinheit audio PCR Prozentsatz 3 Prozent in möglicherweise Dezember, die erfüllt die Beispiel-Ziel, die bestimmte Gebäude weiterhin schlechte Erfahrungen, je nach der Verteilung dieser 3 Prozent haben.

#### <a name="overall-organizational-poor-call-percentage"></a>Insgesamt Organisationseinheit Anrufe schlechter Qualität Prozentsatz

Informationen zum Bewerten der Gesamtprozentsatz schlechter Anrufe für die Organisation verwenden Sie die allgemeine Qualität Analysediagrammbericht.

![Screenshot des ein Diagramm mit Prozentsatz der Anrufe schlechter Qualität](media/quality-of-experience-review-guide-image20.png)

_Abbildung 20 – Audioqualität - insgesamt_

##### <a name="investigation"></a>Untersuchung

Der Diagrammbericht zeigt die Verwendung und PCR Ihrer Organisation über einen Zeitraum. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist der gesamte PCR für den aktuellen Monat?

2.  Ist die PCR unterhalb der definierten Ziel Metrik?

3.  Ist der Ausfall Trend schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Ausfall Trend erhöhen, steady, oder verringern?

Antworten auf die obigen Fragen unabhängig Zeit in Anspruch nehmen die mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die weiteren Untersuchung möglicherweise untersuchen. Zwar die allgemeine PCR unterhalb der Ziel-Metrik häufig die PCR für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und weiteren Untersuchung benötigt.

#### <a name="audio-quality-overall"></a>Allgemeine Audioqualität

Es gibt zwei Bericht Strukturen in die Vorlagen für Audioqualität, einen für Untersuchen von Konferenz- und das andere für Anrufe mit zwei Teilnehmern enthalten. Für die Zwecke der Qualität Behebung versteht genauer identisch, damit wir hier auf Live Meeting konzentrieren können. Verbesserungen bei der Konferenz Qualität wirkt sich auch positiv auf zwei Teilnehmern die Anrufqualität aus. Berichte sind auch anzeigen, die Audioqualität für Konferenzen und zwei Teilnehmern von verkabelt und Wi-Fi enthalten.

> [!NOTE]
> Untersuchen von schlechter Gesprächen mit zwei Teilnehmern ähnelt dem Untersuchen von Telefonkonferenzen. Die Aufgabe wird zum Identifizieren von Gebäude oder Subnetze, die niedrigste Qualität überprüfen, ob es ein Muster schlechter Anrufe mit einem anderen Gebäude oder Subnetz liegt. 

![Screenshot der die Audioqualität - Webkonferenz-Bericht im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image21.png)

_Abbildung 21 – Audioqualität - Konferenzen_

##### <a name="investigation"></a>Untersuchung

Der Diagrammbericht zeigt Konferenzen oder Usage mit zwei Teilnehmern und PCR in Ihrer Organisation über einen Zeitraum. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist der gesamte PCR für den aktuellen Monat?

2.  Ist die PCR unterhalb der definierten Ziel Metrik?

3.  Ist PCR schlechter oder höherer Leistung als den vorherigen Monat?

4.  Ist der Trend PCR erhöhen, steady, oder verringern?

Antworten auf die obigen Fragen unabhängig Zeit in Anspruch nehmen die mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Untersuchung untersuchen. Zwar die allgemeine PCR unterhalb der Ziel-Metrik oft die PCR für eine oder mehrere Gebäude oder Netzwerke ist oben die Metrik und-Wartung benötigt.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Schlechte Audiostream durch Erstellen und Subnetz

In diesem Tabellenbericht finden Sie zusätzliche Einblick in was beigetragen an, das die Anrufe als schlecht klassifiziert und trägt dazu bei, um Hotspot im verwalteten Netzwerk zu isolieren.

Details der Verbindung unterscheidet zwischen verkabelt und Wi-Fi und Jitter und Paketverlust Round-Trip Zeitmaßeinheiten (Zeit) enthält. Ein ähnlichen Bericht auch unter der zwei Teilnehmern Berichte vorhanden ist, und wird verwendet, um zwei Teilnehmern Anrufe in Ihrem verwalteten Netzwerk zu isolieren.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern. 

> [!TIP]
> Allgemeine Heimnetzwerken sind schwieriger zu Ursachenanalyse aufgrund der weit verbreitete Verwendung. Ein separater Bericht, der die IP-Adresse Firewall verwendet wurde hinzugefügt, um die Vorlage alle Netzwerke mit Korrigieren von Büros unterstützen, die gängigen Netzwerke verwenden.

![Bericht, der Verbindungstypen, Transporttypen und PCR größer als 3 % zusammen mit verschiedenen Gründen schlechter Qualität erstellen, Netzwerk und Subnetz pro Monat geordnet aufgeführt sind.](media/quality-of-experience-review-guide-image22.png)

_Abbildung 22 - Zusammenfassung durch Erstellen von schlechter Audiostream- und Subnetz Konferenzen_

##### <a name="remediation"></a>Wartung

Netzwerke mit der größten Menge der Audiostreams, da dies Auswirkungen maximieren und zur Verbesserung des Benutzers Hilfe schnell Erfahrung oder Kenntnisse konzentrieren Ihre Remediation auf Gebäude. Verwenden Sie die Jitter, Paketverlust und Maßangaben von Zeit um zu verstehen, was die Qualität der Anrufe schlechter Qualität beitragen wird. Es ist möglich, mehr als ein Problem sein:

-   **Jitter:** Media-Pakete eingeht mit einen Lautsprecher an automatischen klingen, wodurch andere Geschwindigkeit.

-   **Paketverlust:** Media-Pakete werden verworfen wird, erstellt die Auswirkung der fehlenden Wörter oder Silbenschrift verwenden.

-   **Zeit:** Media-Pakete sind sehr lange dauert, an das Ziel abgerufen werden, das einen Effekt Walkie-talkie erstellt.

Zwar keine zentrale Quelle Wahrheit Benutzerkonten für was Anruf schlechter Qualität führen kann, können mehrere allgemeine Methoden Umgang mit Netzwerkanomalien Ihnen ein.

Um Ihre Untersuchung Qualitätsprobleme rechten zu unterstützen, können Sie [Rufen Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)nutzen.
Mit Analysen aufrufen können Sie einer bestimmten Konferenz oder Benutzer detaillierte Anruf Bericht anzeigen. Dieser Bericht enthält PII-Daten und ist nützlich, wenn Sie versuchen, einen Grund für Fehler zu erkennen. Wenn Sie wissen, welche erstellen, die Verfolgung von Benutzern, Erstellen von unkompliziert sein sollte betroffen ist.

Vergessen Sie nicht, lassen Sie das Helpdesk wissen, dass diese Netzwerke Qualität, Probleme haben, sodass sie schnell selektieren und eingehende Anrufe beantworten können.

_Tabelle 9: Allgemeine Beiträge zu hohe PCR_

| Wartung                              | Anleitung       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Netzwerke                                 | Ein Netzwerk Überbelastung oder unter bereitgestellte kann zu Problemen mit Medienqualität führen. Arbeiten mit dem Netzwerkteam, um festzustellen, ob die Netzwerkverbindungen aus der Benutzer auf das Internet Ausgang zeigen hat genügend Bandbreite für Medien unterstützen. **Führen Sie eine Netzwerk-Bereitschaft:** Eine Netzwerk-Bewertung enthält Details zur Nutzung der erwarteten Bandbreite, wie bewältigen Bandbreite und Netzwerk ändert, und Netzwerke Methoden für Teams und Skype für Unternehmen empfohlen. Verwenden der obigen Tabelle als Quelle, müssen Sie eine Liste von Gebäude oder Subnetze, die eignen sich für eine Bewertung sind.<br><ul><li>[Microsoft-Teams, Netzwerk-Bereitschaft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype für Business Netzwerk Bereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Tool zur Bewertung der Microsoft Network:** Verwenden Sie dieses Tool für einen einfachen Test der Leistung des Netzwerks, um zu bestimmen, wie gut das Netzwerk für eine Teams ausführen würden oder Skype für Business Online Anruf. Mit diesem Tool können Sie bewerten die Leistung eines Subnetzes und überprüfen die Bereitschaft des Netzwerks gegen die Microsoft Performance [Requirements](https://aka.ms/performancerequirements).<br><ul><li>[Laden Sie das Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Quality of Service (QoS)                 | QoS ist eine bewährte Methode, um Pakete in einem Netzwerk, um sicherzustellen, dass sie am Ziel intakt eingehen und priorisieren. Berücksichtigen Sie die Implementierung der QoS in Ihrer Organisation, die die Qualität des Benutzererlebnisses maximieren, wenn die Bandbreite begrenzt oder eingeschränkt ist. QoS helfen, Probleme, die in der Regel mit hoher Paketverlust, lösen und – in geringerem Maße – Jitter und Round-Trip Zeiten. <br><ul><li>[Microsoft-Teams QoS-Anweisungen](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype für Business QoS-Anweisungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi kann eine erhebliche Auswirkungen auf die Anrufqualität haben. Wi-Fi-Design nicht in der Regel berücksichtigen Sie die netzwerkanforderungen für die VoIP-Dienste und sind häufig die Ursache von schlechter Qualität. **QoS:** Moderne drahtlose Netzwerke müssen vielen Geräten unterstützen. Diese Geräte konkurrieren für Bandbreiten- und können dazu führen, dass Qualitätsprobleme für VoIP-Dienste, in denen besitzen Geschwindigkeit und Wartezeit wichtiger. Wenden Sie sich an den Hersteller Ihres drahtlosen Einzelheiten, und implementieren Sie QoS für Ihr Drahtlosnetzwerk Skype für Geschäfts- und Teams Medien priorisieren. **AP-Dichte:** Zugriffspunkte (APs) möglicherweise zu weit auseinander oder nicht in eine ideale Speicherort. Um Probleme zu minimieren, setzen Sie zusätzliche APs in Konferenzräumen und Standorte, die von den Wänden oder sonstigen Objekte verdeckt werden nicht. **Mit 2,4 GHz im Vergleich zu 5 GHz:** 5 GHz enthält weniger Störungen im Hintergrund und einer höheren Geschwindigkeit und bei der Bereitstellung von VoIP über Wi-Fi priorisiert werden sollte. Jedoch 5 GHz ist nicht so stark wie mit 2,4 GHz nicht zugelassen und Walls so einfach. Überprüfen Sie vom Layout erstellen, um die Häufigkeit bestimmen Sie für die optimale Verbindung verwenden können. **Signalstärke:** Bisher gemessen in dBm (Power Verhältnis in DB), misst das die Stärke des drahtlosen Signals. Nachdem ein Gerät mit einem Zugriffspunkt verbunden ist, möchten nicht es können auf einfache Weise wechseln. Wenn das Gerät außerhalb der Zugriffspunkt verschoben wird, fällt die Signalstärke einen Punkt erreicht, die verursacht eine schlechte Verbindung, auch wenn ein anderes, je näher AP verfügbar ist. Wenn möglich, arbeiten Sie mit Ihrem AP-Hersteller, um sicherzustellen, dass die Zugriffspunkte konfiguriert wurden, um ein Gerät zu löschen, wenn ein akzeptables Maß Signalstärke unterschreitet. Dadurch wird sichergestellt, dass das Gerät an eine schwache Zugriffspunkt reagiert nicht. Dies ist eine gute Lösung, wenn Sie auf einfache Weise Weitere Zugriffspunkte hinzugefügt werden können. **WLAN-Treiber:** Wenn das Problem weiterhin besteht, stellen Sie sicher, dass wireless-Treiber auf dem aktuellen Stand sind. Dadurch wird eine beliebige benutzerfreundlich im Zusammenhang mit einer veralteten Treiber zu mindern. |
| Netzwerkgerät                           | In größeren Organisationen möglicherweise Hunderte von Geräten, die über das Netzwerk verteilt. Arbeiten mit Ihrem Netzwerkteam, um die Netzwerkgeräte vom Benutzer mit dem Internet sicherzustellen aufbewahrt werden und auf dem aktuellen Stand.     |
| VPN                                      | Es wurde gut dokumentiert, dass VPN-Geräte, Real-Time Media Arbeitslasten behandeln traditionell ausgelegt sind. Einige VPN-Konfigurationen verhindern die Verwendung von UDP (Dies ist das bevorzugte Protokoll für Audio) und stützen sich nur auf TCP. Berücksichtigen Sie die Implementierung einer [VPN-Split-Tunnel Lösung](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) zur Verringerung der VPN als Quelle von schlechter Qualität.        |
| Clients (Skype für Unternehmen nur Online) | Ältere Clients wurden als verursacht Probleme mit Medien. Stellen Sie sicher, dass Clients innerhalb von sechs Monaten nach Veröffentlichung gepatcht werden. [MyAdvisor](https://aka.ms/myadvisor) Hinweise zum Entwickeln einer Strategie für die Client-Bereitschaft nutzen und Bereitstellen von [Klick-und-Los](https://technet.microsoft.com/library/jj219427.aspx).      |
| Geräte                                  | Die Verwendung der [Geräte optimiert](https://partnersolutions.skypeforbusiness.com/solutionscatalog) , damit die Benutzeroberfläche wesentlich verbessert. Alles gleich sind optimierte Geräte so konzipiert, die Benutzeroberfläche mit Teams und Skype für Unternehmen zu maximieren und Erzeugen von höchster Qualität. Nutzen Sie [MyAdvisor](https://aka.ms/myadvisor) Anleitungen zum Entwickeln einer Strategie für die Bereitschaft Gerät.   |


### <a name="investigate-tcp-audio-sessions"></a>Untersuchen Sie die TCP-audiositzungen

TCP gilt ein Failback Transport- und nicht den primären Transport für Real-Time Media gewünschte. Der Grund dafür, dass sie ein Failback Transport ist besteht aufgrund der dynamische TCP. Beispielsweise, wenn ein Anruf erfolgt in einem Netzwerk latente und Medien Pakete verzögert werden klicken Sie dann Pakete von ein paar Sekunden vor – die eignen sich nicht mehr – konkurrieren für Bandbreite, um an den Empfänger zu abzurufen, die eine ungültige Situation verschlechtern können. Dadurch wird das audio Reparatur zusammenfügen und Dehnen Audio, wodurch hörbaren Artefakte häufig in Form von Jitter.

Die Berichte in diesem Abschnitt tätigen nicht unterschieden zwischen gute und schlechte Anrufe. UDP bevorzugte ist, suchen die Berichte für die Verwendung von TCP für Audio. Dies wird hauptsächlich durch unvollständig Firewallregeln verursacht. Weitere Informationen zu Firewall-Regeln für Teams und Skype für Business Online finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips).

> [!IMPORTANT]
> Mit einer gültigen [Erstellen Sie die Datei](#building-mapping) hochgeladen wird empfohlen, um schnell innerhalb von externen Audiostreams zu unterscheiden bei der Suche unter Verwendung von TCP zu können. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Audioströme, die mit allgemeinen TCP-Verwendung

Dieser Bericht gibt die TCP-Gesamtverwendung für Audio in den letzten sieben Monaten an, wie unten dargestellt.

Alle weiteren Berichte in diesem Abschnitt Schwerpunkt auf Eingrenzung bestimmte Gebäude und Subnetzen, wo TCP am häufigsten verwendet wird. Weitere Unterberichte zerlegen TCP Verwendung von Gesprächen mit zwei Teilnehmern und Konferenzen.

![Screenshot eines Diagramms, das die Anzahl der Audiostreams TCP pro Monat](media/quality-of-experience-review-guide-image23.png)

_Abbildung 23 – Audiostreams mit TCP-Verwendung_

##### <a name="investigation"></a>Untersuchung

Der Diagrammbericht zeigt Ihrer Organisation Gesamtverwendung TCP. Mit diesem Bericht können Sie die folgenden Fragen beantworten:

1.  Was ist das Gesamtvolumen des TCP-Anrufe für den aktuellen Monat?

2.  Handelt es sich verschlechtert oder besser als den vorherigen Monat?

3.  Ist die TCP-nutzungstrend erhöhen, steady, oder verringern?

Nehmen Sie Wenn Sie feststellen, dass die TCP-nutzungstrend erhöht wird, oder höher normalen monatlichen Nutzung, die Zeit untersuchen Sie mithilfe der Unterberichte, suchen Sie nach Gebäude oder Netzwerke, die möglicherweise Remediation. Idealerweise sollten Sie so wenig TCP-basierte audiositzungen wie möglich im verwalteten Netzwerk.

#### <a name="tcp-vs-udp"></a>TCP und UDP

In diesem Tabellenbericht identifiziert die Lautstärke von TCP und UDP Verwendungsberichten auf den aktuellen Monat für Konferenzen für Audio-, Video- und videobasierte Bildschirmfreigabe (VBSS).

![Bericht mit der Lautstärke des TCP und UDP-Konferenz Datenströmen im Vergleich mit PCR Vergleich dargestellt](media/quality-of-experience-review-guide-image24.png)

_Abbildung 24 – TCP und UDP - Konferenzen_

##### <a name="analysis"></a>Analyse

Obwohl Sie TCP-Nutzung so gering wie möglich sein soll, wird möglicherweise ein Bit der TCP-Verwendung in einer Bereitstellung andernfalls fehlerfrei angezeigt. Zum Vergleichen von UDP zur Verwendung von TCP-Audiostreams TCP durch UDP Audiostreams Prozentsatz bestimmt werden kann. Ein Wert über 1 Prozent muss genauer untersucht werden.

Im obigen Beispiel nehmen wir 1,806 TCP-Datenströme geteilt durch 10,481 UDP-Datenströmen bei einem Wert von 17,2 % eingehen. Dieser Wert ist größer als 1 Prozent und gibt an, dass wir müssen weiterhin die Untersuchung auf um zu bestimmen, wo die Verwendung von TCP auftritt.

Auch in den Bericht einbezogen ist Audio schlechter Prozentsatz. Dies ermöglicht Ihnen eine Ansicht in den Vergleich von Anrufqualität zwischen UDP und TCP zum Visualisieren wie TCP Overcall Anrufqualität auswirkt.

So nun, da Sie bestimmt haben, dass eine hohe Verwendung von TCP-basierte Audio in Ihrer Organisation vorhanden ist, was tun Sie als Nächstes? Wechseln Sie zur **TCP-Datenströme durch Erstellen und Subnetz** Berichte für die TCP-Nutzung durch Erstellen von und Subnetzen zu zerlegen.

#### <a name="tcp-streams-by-building-and-subnet"></a>TCP-Datenströme durch Erstellen und Subnetz

In den bereitgestellten CQD Vorlagen wechseln Sie in die TCP-Streams durch Erstellen und Subnetz-Berichte mithilfe der verwalteten oder Vorlage für alle Netzwerke. Es gibt drei Berichte in der Vorlage, eine für Untersuchen von Konferenzen mit und ohne Microsoft Relay-Informationen und eine für Untersuchen von Gesprächen mit zwei Teilnehmern enthalten. Zum Untersuchen der TCP, ist der Prozess, gleich, damit wir die Diskussion auf Konferenzen nur näher erläutert wird.

> [!IMPORTANT]
> Mit einer gültigen [Erstellen Sie die Datei](#building-mapping) hochgeladen wird empfohlen, um schnell innerhalb von externen Audiostreams zu unterscheiden bei der Suche unter Verwendung von TCP zu können. 

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.                                  |

![Bericht, TCP-Datenströme, erstellen, Netzwerk und Subnetz pro Monat geordnet aufgeführt.](media/quality-of-experience-review-guide-image25.png)

_Abbildung 25 – TCP-Datenströme durch die Erstellung- und Subnetz Konferenzen_

##### <a name="remediation"></a>Wartung

In diesem Bericht identifiziert bestimmte Gebäude und Subnetze abgerufen, die dem Volumen der Verwendung von TCP beitragen. Ein Bericht zusätzlicher ist ebenfalls enthalten, um die IP-Adresse des Microsoft-Relay zu identifizieren, die in den Anruf verwendet wurde, um zu isolieren fehlenden Firewallregeln. Konzentrieren Sie Ihre Remediation auf diese Gebäude, die dem höchsten zu erwartenden der Audiostreams maximieren Auswirkungen haben.

Die häufigste Ursache für die Verwendung von TCP fehlt Ausnahmeregeln in Firewalls oder Proxyserver. Wir sprechen Proxys im nächsten Abschnitt, also für jetzt Ihrer Arbeit Schwerpunkte auf die Firewalls. Über das Erstellen von oder Subnetz bereitgestellt, können Sie bestimmen, welche Firewall aktualisiert werden muss.

_Tabelle 10 - Remediation * Richtlinien für die TCP-Datenströme durch Erstellen und Subnetz_

| Wartung        | Anleitung     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurieren der firewall | Überprüfen Sie, ob [Office 365 IP-Ports und Adressen](https://aka.ms/o365ips) aus Ihrer Firewall ausgeschlossen werden. Obwohl es gibt viele IP-Adressen und Ports, die Media-bezogene TCP Probleme geöffnet werden müssen die folgenden Ihrer anfänglichen sind Schwerpunktthemen: Überprüfen Sie die folgenden [Medien Subnetzen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) befinden sich in Ihrer Firewall-Regeln. Finden Sie in Zeile 4 in der Tabelle, die für bestimmte Medien Subnetzinformationen angezeigt. [UDP-Ports 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): Diese Ports sind die bevorzugten Media-Ports und geöffnet werden müssen, andernfalls der Client wieder auf TCP-Port 443 fehl. |
| Vergewissern Sie sich             | Verwenden Sie das [Tool zur Bewertung der Microsoft Network](https://www.microsoft.com/download/details.aspx?id=53885) um zu prüfen, ob Konnektivitätsprobleme bei bestimmten Office 365-IP-Adressen und Ports aus dem betroffenen Gebäude oder Subnetz.    |

### <a name="investigate-http-proxy-usage"></a>Untersuchen Sie die Verwendung von HTTP-proxy

HTTP-Proxys sind die Bevorzugter Pfad für die Herstellung von mediensitzungen für eine Vielzahl von Gründen nicht. Viele Tiefe Paket Prüfung Features enthalten, die verhindern, dass Verbindungen mit dem Dienst abgeschlossen und Systemausfallzeit einführen können. Darüber hinaus können Proxys TCP erzwingen, im Gegensatz zu zulassen UDP, die für eine optimale Audioqualität empfohlen wird.

Es ist immer Microsofts Empfehlung an den Client für die Verbindung direkt Teams und Skype für BusinessServices konfigurieren. Dies ist besonders wichtig für basierenden Media-Datenverkehr.

> [!IMPORTANT]
> Ein gültiger [Erstellen Sie die Datei](#building-mapping) hochgeladen haben erleichtert es ordnungsgemäß innerhalb von externen Audiostreams zu unterscheiden beim Proxy Analyse. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Audioströme, die mit HTTP-Proxy Verwendung insgesamt

In diesem Bericht werden die Proxy-Nutzung über einen Zeitraum auf einer monatlichen Skala beschrieben. Der HTTP-Proxy Stream-Bericht in diesem Abschnitt der Vorlage ähnelt der TCP-Berichte. Es überprüfen nicht, ob Anrufe schlechter oder eine gute sind, aber gibt an, ob die Verbindung über HTTP hergestellt wurde.

![Screenshot der Audiostreams mit HTTP-Proxy-Verwendungsbericht im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image26.png)

_In Abbildung 26 – Audiostreams mit HTTP-Proxy-Verwendung_

##### <a name="analysis"></a>Analyse

Wenn Sie eine große Menge von HTTP-Verwendung angezeigt wird, finden Sie in Netzwerke Team, um sicherzustellen, dass die erforderlichen Ausnahmen vorhanden sind, damit Clients direkt Teams oder Skype für Business Online Media Subnetze weiterleiten. Idealerweise sollten keine Verwendung von HTTP-hier angezeigten vorhanden sein.

Wenn Sie nur eine Internet-Proxy in Ihrer Organisation haben, überprüfen Sie die ordnungsgemäße [Office 365-URLs und IP-Adresse Bereich Ausschlüsse](https://aka.ms/o365ips). Wenn mehr als ein, die Internet-Proxy in Ihrer Organisation konfiguriert haben, wird die HTTP nutzen Unterseite isolieren, welche Erstellen von Berichten oder Subnetz beeinflusst werden.

Für Organisationen, die den Proxy umgehen können nicht sicherstellen, dass die Skype für Business-Client anmelden ordnungsgemäß Wenn sie einen Proxyserver befindet wie im Artikel [beschrieben konfiguriert ist sollten Skype für Business Proxyserver verwenden, anstatt direkt anzumelden Verbindung](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>HTTP-Proxy-Streams durch Erstellen und Subnetz

In diesem Bericht identifiziert bestimmte Gebäude und Subnetze abgerufen, die zur Verwendung von HTTP-beitragen.

> [!IMPORTANT]
> Ein gültiger [Erstellen Sie die Datei](#building-mapping) hochgeladen haben erleichtert es ordnungsgemäß innerhalb von externen Audiostreams zu unterscheiden beim Proxy Analyse.

> [!NOTE]
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.                        |

![Screenshot der HTTP-Proxy Nutzung durch Erstellen und Subnetz Bericht im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image27.png)

_Abbildung 27 – HTTP-Proxy-Nutzung durch die Erstellung und Subnetz_

##### <a name="remediation"></a>Wartung

Konzentrieren Sie Ihre Remediation auf jedem Gebäude oder die Subnetze abgerufen, die Verwendung von HTTP-Proxy aufweisen. Die häufigste Ursache für HTTP-Verwendung fehlt Ausnahmeregeln in Proxys. Über das Erstellen von oder Subnetz bereitgestellt, können Sie bestimmen, welche Proxy aktualisiert werden muss.

Stellen Sie sicher, dass die erforderlichen [Office 365 FQDNs](https://aka.ms/o365ips) vom Proxy ausgeschlossen werden.

## <a name="endpoint-investigations"></a>Endpunkt Untersuchungen

In diesem Abschnitt konzentriert sich auf die Aufgaben für die Berichte zur Skype für Business-spezifischen Client-Versionen und die Verwendung von zertifizierte Geräte.

> [!NOTE]
> In diesem Handbuch werden nicht alle Berichte in den Vorlagen enthalten behandelt. Die Beschreibung der einzelnen Berichts Weitere Informationen finden. 


### <a name="determine-client-versions"></a>Bestimmen der Client-Versionen

In diesem Bericht konzentriert sich auf Skype für Business Clientversionen verwendet und ihren relativen Lautstärke in der Umgebung identifizieren.

> [!IMPORTANT]
> Derzeit Teams Clients verteilt und über die Azure Content Delivery Network (CDN) automatisch aktualisiert werden und wird von der Dienst auf dem aktuellen Stand gehalten werden. Client-Bereitschaft und genauer Aktivitäten nicht für Teams gelten.

Versionsnummern für Skype für Business 2015 und 2016 finden Sie über die folgenden Links:

-   [Office 365-Client-Kanal Updateversionen](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Office 365-Version und Build-Nummern für klicken Sie auf Ausführen](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype für Business-Downloads und-Updates](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.  

> [!IMPORTANT]
> Clientberichte müssen Sie federated Teilnehmer Daten ausgeschlossen werden. Um Verbund Teilnehmer Daten auszuschließen, müssen Sie einen Abfragefilter für **Zweiten Mandanten-ID** in Ihrer Organisation [Mandanten-ID](#tenant-id)festlegen hinzufügen. |

![Screenshot des Berichts-Clients und-Geräten im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image28.png)

_Abbildung 28 - Client-Version-Bericht_

#### <a name="remediation"></a>Wartung

Ein wichtiger Aspekt gesteuerter hochwertigen benutzerumgebungen müssen Sie sicherstellen, dass verwaltete Clients auf dem neuesten Stand Versionen von Skype für Unternehmen ausgeführt werden. Dies bietet verschiedene Vorteile, dazu zählen:

-   Es ist einfacher, einige Versionen im Vergleich zu viele Versionen zu verwalten.

-   Es bietet eine einheitliche Erfahrung.

-   Es erleichtert die Problembehandlung bei Anrufqualität und Verwendbarkeit.

-   Microsoft stellt allgemeine Verbesserungen und Optimierungen ständig über das Produkt. Sicherstellen, dass Benutzer diese Updates erhalten, die ihre Risiken der Ausführung in ein Problem, das bereits behoben ist.

Einschränken des Ihre Bereitstellung Clientversionen, die weniger als sechs Monaten sind wird die gesamten Benutzeroberfläche verbessert und Verbesserung der Verwaltbarkeit im Vergleich zu großen Anzahl von verschiedenen Versionen des Clients in der gleichen Umgebung müssen.

Wenn Sie nur Office Klick-und-Los verwenden, werden Sie automatisch binnen sechs Monaten sein. Es ist keine weitere Aktion erforderlich.

"If"; wie die meisten Unternehmen Sie eine Kombination von Klick-und-Los und Installer-Paket (MSI) verfügen, können Sie den Bericht verwenden, um sicherzustellen, dass die MSI-Clients regelmäßig aktualisiert werden. Konzentrieren Sie auf diesen Clients, auf dem das Volume überdurchschnittlich ist. Wenn Sie, dass Clients feststellen hinter sinkt, arbeiten mit dem Team verantwortlich für die Verwaltung von Office-Updates, und stellen Sie sicher, dass sie genehmigen und Bereitstellen von Client-Patches regelmäßig sind.

### <a name="devices-investigations"></a>Geräte Untersuchungen

So tätigen mithilfe des geräteberichts folgende Punkte sollten Sie das Konzept der Mittelwert Opinion verstanden haben (MOS). MOS ist die Messung Gold-Standard: die wahrgenommene Audioqualität zu ermitteln. Es wird als eine Bewertung ganze Zahl im Bereich von 0 bis 5 dargestellt.

Die Grundlage für alle Maßnahmen der Sprachqualität ist wie eine Person für die Qualität der Speech Verbindungsmodus. Da es von human Wahrnehmung betroffen ist, ist es grundsätzlich subjektive. Es gibt mehrere verschiedene Methoden subjektive testen.
Die meisten VoIP Qualität Measures basieren auf einer absoluten Kategorisierung Bewertungsskala (ACR).

Ein ACR subjektive Test bewerten in eine statistisch signifikante Anzahl von Personen ihre Qualität auf einer Skala von 1 (schlecht) auf 5 (hervorragend). Der Mittelwert der Ergebnisse ist die MOS. Die resultierende MOS hängt von den Bereich der Erfahrungen, die die Gruppe und den Typ des Erfahrung bewertet wird verfügbar gemacht wurden.

Da es nicht sinnvoll, um für ein Kommunikationssystem live subjektive Tests der Sprachqualität auszuführen ist, Teams und Skype für Unternehmen mithilfe von erweiterten Algorithmen eine subjektive Testergebnisse objektive vorhergesagt MOS Werte generieren.

Der verfügbare Satz mit MOS und Metrik eine Ansicht in der Qualität der Zustellung an die Benutzer bereitstellen.

Durch Bereitstellen von Benutzern mit Geräten zertifiziert für Teams und Skype für Unternehmen, verringern Sie die Wahrscheinlichkeit solch negative Erfahrungen aufgrund des Geräts selbst (die wahrscheinlicher, beispielsweise mit integrierten Laptop-Lautsprecher und Mikrofon ist). Weitere Informationen finden Sie unter [Telefone und Geräte für Skype für Unternehmen](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Organisatorische Verwendung der Capture-Geräte (Mikrofone) nach volume

In diesem Bericht wird verwendet, um Mikrofon Usage bewerten und MOS Score und finden Sie in den zugehörigen Vorlagen unter Clients und Geräte *.*

> [!IMPORTANT]
> Gerät Berichte müssen Sie federated Teilnehmer Daten ausgeschlossen werden. Um Verbund Teilnehmer Daten auszuschließen, müssen Sie einen Abfragefilter für **Zweiten Mandanten-ID** in Ihrer Organisation [Mandanten-ID](#tenant-id)festlegen hinzufügen. 

> [!NOTE] 
> Achten Sie darauf, dass Sie den Monat-Jahr-Filter mit dem aktuellen Monat anpassen. Wählen Sie **Bearbeiten**aus, und passen Sie **Monat-Jahr** , um den neuen Standardmonat zu speichern.<br><br> Sie möglicherweise feststellen, wenn mehrere Male gemeldet, dass Sie dasselbe Gerät finden Sie unter Bericht anzeigen. Dies liegt daran, die das Gerät gemeldet wird an CQD gemeldet werden. Unterschiede in der Hardware und Betriebssystem-Gebietsschema Berichten Gerätedaten unterschiedlich.

![Screenshot des Berichts Geräte (Mikrofon) im Dashboard Qualität aufrufen.](media/quality-of-experience-review-guide-image29.png)

_Abbildung 29 - – Gerätebericht (Mikrofon)_

##### <a name="remediation"></a>Wartung

Der erste Schritt besteht das Ziel des Vorgangs MOS bestimmen erreichen möchten. MOS bewertet Bereich von 1 bis 5, mit 5 wird das beste. Wählen Sie eine angemessene Ziel basierend auf Ihrer Umgebung und Abfrageergebnisse. Im folgenden Beispiel ist das Ziel ein MOS Bewertung von 3.6 oder höher für alle Geräte, die mehr als 100 Datenströme aufweisen. Sie erzielen die Gerätequalität abzielen, wenn:

-   Die Abfrageergebnisse Gerät zurückgeben MOS \> 3.6 für NumStreams \> 100

In der Regel müssen Sie leistungsschwachen Geräte mit zertifizierte Geräte zu ersetzen. Einige Aspekte beim Überprüfen von Device Report umfassen:

-   Sind die zertifizierte Geräte oder zweifelsfrei funktionierende in Ihrer Umgebung? In der Abfrage mit einem niedrigeren MOS Faktor als des Basisplans ein zertifizierten oder eine gute Gerät zurückgegeben wird, möglicherweise unbekannte Weitere Faktoren (beispielsweise eine schlechte Netzwerk- oder unzureichende pc), die an die niedrigste Punktzahl beiträgt.
    Zusätzliche Untersuchung werden benötigt.

-   Sie können Benutzer eines Geräts über [Analytics aufrufen](#call-analytics-training)identifiziert. Überprüfen Sie, um sicherzustellen, über die neuesten Gerätetreiber verfügen und, dass ihr Gerät über ein USB-Hub verbunden ist.

-   Überprüfen Sie, ob eine Beziehung zwischen fehlerhafte Geräte und stellen Sie ein bestimmtes System und das Modell vorhanden ist. Wenn dies der Fall ist, kann das Gerät nicht kompatibel oder Treiber-Upgrades benötigen.

Die zweite Aufgabe besteht darin, die allgemeine Verwendung nicht zertifizierte Geräte zu bestimmen. Es wird empfohlen, mindestens 80 Prozent der alle Audiostreams zu einem zertifizierten Gerät verwenden.
Dies geschieht am besten durch den Geräte-Bericht nach Excel exportieren und die Verwendung von zertifizierten oder genehmigten Geräten manuell berechnen. Organisationen lassen in der Regel eine Liste mit allen genehmigten Geräten, damit filtern und Sortieren von Daten einfach sein sollte.

## <a name="appendix-a-lync-networking-guide"></a>Anhang a: Lync Netzwerke (engl.)

Für weitere Hintergrund auf der Teams und Skype für Netzwerke Business-Konzepte und Gründe für die Qualität ihrer Wichtigkeit ist der [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) gelten auch weiterhin.

## <a name="appendix-b-network-performance-requirements"></a>Anhang b-Leistung netzwerkanforderungen

Die Qualität von Real-Time-Medien (Audio, Video und Anwendungsfreigabe) Implementation wird durch die Qualität der End-to-End-Netzwerkkonnektivität erheblich beeinträchtigt. Für eine optimale Teams oder Skype für Business Medienqualität muss Ihr Netzwerk die folgenden Leistungsmetriken Netzwerk erfüllen.

_In Tabelle 11 - Netzwerk leistungsanforderungen_

| Metrik                           | Client zu Microsoft Edge           | Kundenedge zu Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Wartezeit (unidirektional)                | \<50 ms                            | \<30 ms                            |
| Wartezeit (Zeit oder Roundtripzeit) | \<100 ms                           | \<60 ms                            |
| Bursts von Paketverlusten                | \<10 % Intervall 200 ms   | \<1 % Intervall 200 ms    |
| Paketverlust                      | \<1 % Intervall 15 s    | \<0,1 % Intervall 15 s  |
| Die Kommunikation zwischen hinzukommen Jitter Paket      | \<während ein Intervall von 15 s 30 ms | \<15 ms Intervall 15 s |
| Paket neu anordnen                   | \<0,05 % außerhalb der Reihenfolge Pakete       | \<0,01 % außerhalb der Reihenfolge Pakete      |

Weitere Informationen finden Sie unter den folgenden Artikel über das [Media Quality und Netzwerk Leistung](https://aka.ms/performancerequirements) für Teams und Skype für Business Online.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Anhang C. Weitere Ressourcen

### <a name="building-data-file"></a>Erstellen von-Datendatei

-   [Aktivieren und Verwenden von CQD in Skype für Business Online](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>CQD-Schulung

-   <https://aka.ms/sof-cqd>

-   Handbuch [Erste Schritte mit CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) und Workshop.

-   [CQD Dimensionen und Measures online-Entwicklerhandbuch](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Rufen Sie Analytics-Schulung

-   [Einführung in Anruf Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Einrichten der Anrufanalyse von Skype for Business](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Wenden Sie Analytics

-   Community: [Skype für Business Preview-Programm](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Wenn Sie Unterstützung erhalten möchten, melden Sie sich unsere Preview Portal [www.skypepreview.com](http://www.skypepreview.com), wählen Sie **Bericht ein Problem**und verwenden Sie die Option **Erstellen eines neuen Fehler** Berichten eines Problems. Bitte beachten Sie, dass Support-Mitarbeiter zur Verfügung, Unterstützung von Montag zwischen 6 Uhr um 9 Uhr EST zurück. Anfragen außerhalb Stunden, werden der folgende Tag selektierender.

### <a name="devices"></a>Geräte

-   [Skype für Business Solutions Catalog Peripheriegeräte & PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Mandanten reporting

-   [Office 365 Annahme Inhaltspaket](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Skype for Business Online-Berichterstellung](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Microsoft-Teams, reporting](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
