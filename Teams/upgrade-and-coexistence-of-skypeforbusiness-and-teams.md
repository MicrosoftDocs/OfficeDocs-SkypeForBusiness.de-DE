---
title: Microsoft Teams-Upgrade von Skype for Business | Modi, Koexistenz
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen, bjwhalen
description: Details zu den Optionen und Modi von Skype for Business und Microsoft Teams für Koexistenz sowie zum Upgrade von Reisen zu Teams von Skype for Business mit Beispielszenarien.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d662dfd98aa4706d32a7e9ba3bec06d5e32ae975
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934399"
---
![Diagramm zum Upgrade von Fahrten mit Hervorhebung der Bereitstellung und Implementierung] (media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")

Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ihre Projekt Beteiligten wurden eingetragen](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Verständliche Koexistenz und Interoperabilität von Skype for Business und Teams](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Wählen Sie Ihre Upgrade-Reise von Skype for Business zu Teams aus.

Als vorhandener Skype for Business-Kunde kann es einige Zeit dauern, bis Ihr vollständiger Wechsel zu Teams stattfinden kann. Allerdings können Sie den Wert von Teams heute erkennen, indem Sie es Ihren Benutzern ermöglichen, Teams neben Skype for Business zu verwenden. Da es zwischen den beiden apps einige überlappende Funktionen gibt, empfehlen wir, dass Sie die verfügbaren Koexistenz-und Aktualisierungsmodi überprüfen, um zu ermitteln, welcher Pfad für Ihre Organisation richtig ist. So können Sie beispielsweise alle Arbeitsauslastungen für beide Lösungen ohne Interoperabilität aktivieren. Oder Sie entscheiden sich möglicherweise für die Verwaltung der Benutzeroberfläche, indem Sie schrittweise die Teamfunktionen einführen oder Benutzergruppen auf ausgewählte Funktionen ausrichten, bis Ihre Organisation bereit ist, alle Personen auf Teams zu aktualisieren. Mithilfe des Ergebnisses Ihres Pilotprojekts können Sie die richtige Upgrade-Reise für Ihre Organisation bewerten.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, danach wird es nicht mehr barrierefrei oder unterstützt. Um die Leistung zu maximieren und sicherzustellen, dass Ihre Organisation die richtige Zeit für die Implementierung Ihres Upgrades hat, empfehlen wir Ihnen, Ihre Reise zu Microsoft Teams heute zu beginnen.

In diesem Artikel werden die verschiedenen Modi erläutert, mit denen Sie verwalten können, welche Modalitäten in Skype for Business und Teams für Ihre Benutzer zur Verfügung stehen. Wie bei jeder Bereitstellung empfehlen wir Ihnen dringend, [ihren beabsichtigten Plan](pilot-essentials.md) mit einer ausgewählten Gruppe von Benutzern zu pilotieren, bevor Sie Ihre Organisation auf Teams aktualisieren. Denken Sie daran, dass die Einführung neuer Technologien für Benutzer störend sein kann. Nehmen Sie sich Zeit, um die Benutzer Bereitschaft zu bewerten und einen Kommunikations-und Schulungsplan zu implementieren, bevor Sie einen der hierin beschriebenen Modi implementieren.

> [!TIP]
> Begleiten Sie uns in interaktiven, interaktiven Workshops, in denen wir Anleitungen, bewährte Methoden und Ressourcen austauschen, die für die Planung und Implementierung von Upgrades entwickelt wurden.
>
>Nehmen Sie zuerst an der [Planung Ihrer Upgrade](https://aka.ms/SkypeToTeamsPlanning) -Sitzung Teil, bevor Sie beginnen.


## <a name="upgrade-journey-building-blocks"></a>Bausteine für Upgrade-Fahrten

Wenn Sie Ihre Organisation formell für Ihre Reise in Teams vorbereiten möchten, müssen Sie mit der Planung für die Upgrade-Szenarien beginnen, die es Ihrem Unternehmen ermöglichen, Teams als ihre einzige Lösung für Kommunikation und Zusammenarbeit umfassend zu integrieren.

Um ihre Entscheidungsfindung zu erleichtern, sollten Sie sich mit den verschiedenen Modi, Konzepten und Terminologie vertraut machen, die für das Upgrade von Skype for Business auf Teams relevant sind. Weitere Informationen finden Sie unter [Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](https://aka.ms/SkypeToTeams-Coexist) .

Wenn einige Ihrer Benutzer bereit sind, nur Teams für Ihre täglichen Kommunikations-und Zusammenarbeitsanforderungen zu verwenden, können Sie mit dem Upgrade dieser Benutzer auf Teams beginnen, indem Sie den Modus **nur für Teams** aktivieren.

Wenn es für Ihr gesamtes Unternehmen nicht möglich ist, zu Teams zu wechseln, können Sie mit der Pilotfunktion von Teams zusammen mit Skype for Business im Koexistenzmodus für **Inseln** beginnen. Da die zusätzlichen Koexistenzmodus (also **Skype for Business mit Teamzusammenarbeit** und **Skype for Business mit Teamzusammenarbeit und**-Besprechungen) in den nächsten Monaten schrittweise vollständig zur Verfügung stehen, können Sie auch mit vollständiger die Einführung von Teams als Lösung für die Gruppenzusammenarbeit, wobei Skype for Business die Unified Communications-Lösung Ihrer Organisation bleibt. Dies ist der empfohlene Weg von Microsoft für Kunden, die Skype for Business Server (lokal oder Hybrid) verwenden, und Kunden mit erheblicher Komplexität, deren Flugbahn zu Teams einen längeren Zeitraum für die Koexistenz umfasst.

![Screenshot der Upgrade-Bausteine von Skype for Business in Teams] (media/upgrade_journeys_building_block.png "Ein Screenshot der Upgrade-Bausteine von Skype for Business in Teams, bestehend aus Skype for&ndash;Business mit Teamarbeits Modus für Teams, Skype for Business mit Teamarbeits-und Besprechungs Modus, Inseln-Modus, nur für Teams und Skype für Nur&ndash;Business-Modus.")

In der folgenden Tabelle werden die Koexistenz-und Aktualisierungsmodi verglichen.

|Modus |Situation |Empfohlene Verwendung |Advantages |Vorbehalte |
|---|---|---|---|---|
|Inseln |Kleinere oder einfachere Bereitstellung von Skype for Business<br><br>Fähigkeit und Bereitschaft, kurzfristige Komplexität zu verwalten, um schneller zu Teams zu wechseln |So schnell wie möglich zur vollständigen Team Erfahrung wechseln<br><br>Durchführen eines Machbarkeitsstudie für Teams<br><br>Empfohlener Upgrade-Pfad für Organisationen, die Skype for Business Online angenommen haben |Einfache Bedienung<br><br>Reichhaltige Teams für alle Funktionen im Vordergrund |Erfordert eine gute Benutzerkommunikation, um Verwirrung zu vermeiden und die Nutzung für Teams zu steuern<br><br>Die Exit-Strategie setzt voraus, dass die Benutzer vollständige Teams angenommen haben, bevor Sie das Upgrade nur in die Teams-Phase starten<br><br>Keine Interop für Benutzer im Modus "Inseln"; auch keine Föderation aus Teams, wenn das Skype for Business-Konto des Benutzers lokal gehostet wird|
|Skype for Business mit Zusammenarbeit in Teams |Bereitstellung von Skype for Business mit Anforderungen, die von Teams noch nicht erfüllt wurden (beispielsweise erweiterte Kompatibilität)<br><br>Langfristiger Bedarf an und/oder Engagement für Skype for Business|Starten Sie die Einführung von Teams schnell und konzentrieren Sie sich zunächst auf die Zusammenarbeit in Gruppen<br><br>Sie möchten alle Unified Communications-Arbeitslasten in Skype for Business für heute beibehalten<br><br>Empfohlene Verwendung als Ausgangspunkt für die Organisation, die Ihre Reise von lokal (oder Hybrid) aus in Skype for Business beginnt|Keine überlappenden Funktionen zwischen Teams und Skype for Business<br><br>Instant Messaging-Chats und Besprechungen werden in Skype for Business (mit anrufen verbunden) verbleibt<br><br>Interoperabilität mit Benutzern nur in Teams|
|Skype for Business mit Zusammenarbeit und Besprechungen in Teams |Bereitstellung von Skype for Business mit signifikanter Nutzung von Enterprise-VoIP und Anforderungen, die von Teams, die nicht anrufen, noch nicht erfüllt<br><br>Langfristiger Bedarf an und/oder Engagement für Skype for Business<br><br>Möglicherweise wird ein Besprechungs Dienst eines Drittanbieters verwendet|Schnelleres Starten von Teams, die über die Gruppenzusammenarbeit hinausgehen<br><br>Verbessern der Benutzer Besprechungen<br><br>Empfohlene Verwendung für lokale Organisationen, die die Vorteile von Teams-Besprechungen nutzen möchten, bevor Sie für ein vollständiges Upgrade bereit sind (in der Regel aufgrund von Enterprise-VoIP lokal). |Keine überlappenden Funktionen<br><br>Überlegene Besprechungen in Teams. Funktionen Roadmap, UX und plattformübergreifend, Qualität und Zuverlässigkeit<br><br>"Besser zusammen"-Erfahrungen zwischen Skype for Business und Teams<br><br>Nur Interoperabilitäts Benutzer in Teams.|Sofortnachrichten und Chats befinden sich in Skype for Business (mit anrufen verbunden)|
|Nur für Teams |Nur Teams ist letztendlich das endgültige Ziel für alle Benutzer.<br><br>Einige Benutzer müssen in Skype for Business bleiben<br><br>Sie aktualisieren Ihre Skype for Business Online-Benutzer auf Teams, während Skype for Business lokale Benutzer in Skype for Business Server unterhalten.<br><br>Möglicherweise haben Sie Benutzer bereits im Modus "Inseln" bereitgestellt und sind bereit, Skype for Business für Gruppen von Benutzern zurückzuziehen. |Reduzieren von Variablen Kosten in Skype for Business (lokale Server Vorgänge, Outsourcing-Vertrag usw.)<br><br>Gehen Sie so schnell wie möglich zur vollständigen Teams-Erfahrung, für mindestens einige Benutzer|Schränkt die Verwirrung von Benutzern ein, indem nur ein Client für die Interoperabilität mit Benutzern in Skype for Business nur bereitgestellt wird, Skype for Business mit Teamzusammenarbeit, Skype for Business mit Teamzusammenarbeit und Besprechungen|Interoperabilität unterstützt nur grundlegende Chats und Anrufe zwischen Skype for Business und Teams sowie Interop-Eskalationsszenarien für die Desktopfreigabe sowie für Chats und Anrufe mit mehreren Teilnehmern|
|Nur Skype for Business |Einige Benutzer müssen in Skype for Business bleiben<br><br>|Schränkt die Verwirrung von Benutzern ein, indem nur ein Client zum Arbeiten bereitgestellt wird.<br><br>Der Benutzer kann weiterhin an Teambesprechungen teilnehmen, zu denen er eingeladen wurde.|Erfüllen Sie weiterhin die geschäftlichen Anforderungen, die derzeit nur von Skype for Business erfüllt werden können.<br><br>Interoperabilität mit Benutzern nur in Teams|Interoperabilität unterstützt nur grundlegende Chats und Anrufe zwischen Skype for Business und Teams sowie Interop-Eskalationsszenarien für die Desktopfreigabe sowie für Chats und Anrufe mit mehreren Teilnehmern|

> [!TIP]
> Wenn Sie den empfohlenen Aktualisierungsmodus basierend auf den Funktionen ermitteln möchten, die Sie in Microsoft Teams aktivieren möchten, während Skype for Business noch verwendet wird, nutzen Sie den [Upgrade-Assistenten von Skype to Teams](https://aka.ms/SkypeToTeamsWizard).

## <a name="upgrade-journeys"></a>Upgrade-Fahrten

Sie können mehrere Ansätze für das Upgrade von Skype for Business, entweder online oder lokal, auf Teams übernehmen:

- Bei einer direkten Upgrade-Reise stellen Sie zunächst Teams zusammen mit Skype for Business im **Inseln** -Modus im Rahmen der Evaluierung und vorzeitigen Einführung bereit, und aktualisieren Sie dann Ihre Benutzer in den Modus **nur für Teams** mit dem Ziel, Skype for Business schnell aus dem Umgebung für alle Benutzer in der Organisation Dies ist die empfohlene Reise für Skype Business Online-Kunden, es sei denn, dass Ihre Nutzer verwirrt sind, dass Sie über zwei Tools verfügen, mit denen Sie die gleiche Aktion durchführen können (Chat, anrufen, Besprechung planen).
- Eine schrittweise Aktualisierung bietet eine bestimmte Koexistenz und einen Upgrademodus für eine bestimmte Gruppe von Benutzern (auch als *Kohorte*bezeichnet), abhängig von den Anforderungen für Kommunikation und Zusammenarbeit. Im Laufe der Zeit kann sich die gesamte Organisation in die Verwendung von Teams einbringen und schließlich Skype for Business ersetzen. Wenn Ihre Organisation jedoch über zwingende geschäftliche Gründe verfügt, Skype für Unternehmen zu behalten, beispielsweise eine Abhängigkeit von einer UCMA-basierten Lösung (Unified Communications Managed API), die in Branchenanwendungen integriert ist, oder eine ethische Wandlösung derzeit nur für Skype for Business oder eine komplexe Enterprise-VoIP-Bereitstellung verfügbar, die nur Zeit für ein Upgrade auf **Teams**benötigen, können Sie einen Teil der Benutzer auf den **nur für Teams** verfügbaren Modus aktualisieren, während Sie Skype for Business-Benutzer in einem der Koexistenzmodus für einen Teil der Benutzerpopulation. Schrittweises Upgrade ist die empfohlene Vorgehensweise für lokale (und hybride) Kunden, die mit Skype for Business mit teamkoexistenzmodus für Teams zusammenarbeiten und von dort aus in den Modus nur für Teams wechseln, wenn die Anforderung für die Benutzer erfüllt ist (möglicherweise über die Skype for Business mit der Zusammenarbeit in Teams und dem Koexistenzmodus "Besprechungen").

> [!IMPORTANT]
> Wenn es sich bei beiden Arten von Upgrade-Reisen um eine zurzeit nur für Skype for Business lokale Bereitstellung handelt, müssen Sie mit der Planung der Implementierung von Skype for Business-Hybriden beginnen, bevor Sie Ihre Benutzer auf **nur für Teams** aktualisieren. Dadurch wird auch die Interoperabilität mit Teams vereinfacht.

> [!NOTE]
> Der Modus " **nur für Teams** " setzt voraus, dass die Benutzer, die zu Kohorten gehören, in Skype for Business Online verwaltet werden und eine Hybrid Beziehung zwischen Ihrer lokalen Bereitstellung von Skype for Business und Ihrem Skype for Business Online-Mandanten erforderlich ist, um die Interoperabilität zwischen Skype for Business und Teams. Der Wechsel zu Skype for Business Online muss für Benutzer abgeschlossen sein, die zu den Kohorten gehören, bevor Sie in den Modus " **nur für Teams** " aktualisiert werden. Skype for Business Server 2019 und Skype for Business Server 2015 mit CU8-Update können die Mechanik des Upgrades von lokalen Benutzern auf Teams vereinfachen, indem Sie die Migration zu Skype for Business online verwalten und die Benutzer nur in einem Schritt in den Modus " **nur für Teams** " aktualisieren. .

### <a name="direct-upgrade-journey"></a>Direkte Upgrade-Reise

Die direkte Upgrade-Reise wird im folgenden Diagramm veranschaulicht.

![Screenshot der direkten Upgrade-Reise] (media/upgrade_journey_direct_upgrade.png "Ein Screenshot der direkten Upgrade-Reise. Alle Benutzer verwenden zunächst Teams im Inseln-Modus und wechseln dann in den Modus nur für Teams, wobei der Endstatus der gesamten Organisation auf Teams aktualisiert wurde.")

Teams wird für alle Benutzer in der Organisation bereitgestellt und im Modus " **Inseln** " konfiguriert. Wenn Ihre Organisation feststellt, dass Teams bereit sind, alle ihre Kommunikations-und Zusammenarbeitsanforderungen zu erfüllen, informieren Sie die Benutzer, und aktualisieren Sie Sie auf den Modus **nur für Teams** . Zu diesem Zeitpunkt kann Skype for Business aus der Umgebung zurückgezogen werden.

### <a name="gradual-upgrade-journey"></a>Schrittweises Upgrade

Ein Beispiel für eine schrittweise Aktualisierung ist im folgenden Diagramm dargestellt.

![Illustriertes Beispiel für die schrittweise Aktualisierung] (media/upgrade_journey_gradual_upgrade.png "In der schrittweisen Upgrade-Reise verwenden Kohorten von Benutzern zunächst Teams im Inseln-Modus zur Evaluierung und dann in einer Reihe von Upgrade-Modi zur vorzeitigen Einführung parallel zu Skype for Business. Einige Kohorten wechseln in den Modus \"nur für Teams\", während eine Gruppe von Benutzern in Skype for Business mit Teamarbeits-und Besprechungs Modus bleibt.")

Teams wird in der Organisation im Modus " **Inseln** " zur Evaluierung bereitgestellt und wechselt dann zu anderen Koexistenz-und Aktualisierungsmodi für verschiedene Benutzergruppen. Beispielsweise kann eine Gruppe von Benutzern für den Modus " **Inseln** " aktiviert werden, ein weiteres für **Skype for Business mit Teamarbeits-und Besprechungs** Modus aktiviert, während eine dritte Gruppe von Benutzern zunächst für **Skype for Business mit Teams aktiviert ist. nur** Zusammenarbeitsmodus.

Im Laufe der Zeit können Gruppen von Benutzern in den Modus " **nur Teams** ", gefolgt von der restlichen Organisation, aktualisiert werden. Schließlich ist die gesamte Organisation bereit, Skype for Business zurückzuziehen und nur Teams für die Kommunikation und Zusammenarbeit zu verwenden, oder – wenn die Geschäftsanforderungen festlegen, dass Skype for Business für eine bestimmte Gruppe aufbewahrt werden soll – die Mehrheit der Benutzer in der Organisation kann nur Teams verwenden. <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul> Welche Upgrade-Reise eignet sich für die geschäftlichen Anforderungen Ihrer Organisation?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Nächster Schritt</td><td><ul> Wenn Sie Ihr aktuelles Bereitstellungsmodell, Anwendungsfall Szenarien und wichtige Überlegungen für Ihre Organisation identifizieren, werden Sie die Reise zu Teams informieren, die für Ihre Organisation am besten geeignet sind.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul> Welches Upgrade-Szenario ist für Ihre Organisation anwendbar?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul> Entscheiden Sie die Zeitachse der Upgrade-Reise Ihrer Organisation auf der Grundlage von Nachrichten, Besprechungen und geschäftlichen Anforderungen für Anrufe.<br><br> Entscheiden Sie, welche zusätzlichen Aufgaben erforderlich sind, um die Upgrade-Reise abzuschließen.<br><br></ul></td></tr>
</table>

Nachdem Sie die beste Upgrade-Reise für Ihre Organisation ausgewählt haben, führen Sie das [Upgrade auf Teams durch](https://aka.ms/SkypeToTeams-Upgrade).
