---
title: Upgrade Reise und Koexistenz von Skype für Unternehmen und die Microsoft-Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/04/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Details der Skype für Geschäfts- und Microsoft-Teams Koexistenz Optionen Modi und Upgrade Fahrten Teams von Skype für Unternehmen mit Beispielszenarien.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46967004ec571e593ea3f73e213c3d0e5b801f86
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2018
---
# <a name="upgrade-journey-and-coexistence-of-skype-for-business-and-microsoft-teams"></a>Upgrade Reise und Koexistenz von Skype für Unternehmen und die Microsoft-Teams

Als eine vorhandene Skype für Unternehmenskunden kann Ihre vollständige Übergang zu Teams einige Zeit dauern. Jedoch können Sie beginnen, stellen Sie den Wert des Teams heute werden, da die Benutzer verwenden Teams zusammen mit Skype für Unternehmen fest. Es ist einige überlappende Funktionalität zwischen zwei apps, wird empfohlen, überprüfen Sie die verfügbaren Upgrade Modi, um zu bestimmen, welcher Pfad für Ihr Unternehmen geeignet ist. Beispielsweise können Sie optional alle Arbeitslasten auf beide Lösungen ohne Interoperabilität aktivieren. Oder Sie können die Benutzeroberfläche verwalten, entweder durch schrittweise Einführung von Teams Funktionen oder durch Zielgruppenadressierung Gruppen von Benutzern für die select-Funktionen, bis jeder Teams upgrade Ihrer Organisation werden.

Wie bei jeder Bereitstellung empfehlen wir dringend Ihnen auf [den vorgesehenen Plan evaluieren](pilot-essentials.md) mit einer ausgewählten Gruppe von Benutzern vor der Einführung der Teams bei Ihrer größeren Organisation. Denken Sie daran: Einführung in die neue Technologie für Benutzer abgebrochen werden kann. Ermitteln Sie die benutzerbereitschaft und dauert Implementieren einer Kommunikations- und Schulungsplan stellen den Benutzern auf dem laufenden und beschleunigt die Zustimmung des Teams. 

> [!IMPORTANT]
> Die Skype für Unternehmen Teams Upgrade Reise weiterentwickelt wird. In diesem Artikel helfen Ihnen beim verstehen, des in Kürze verfügbare Teams Upgrades, aber es nicht End-to-End-Upgradeanweisungen einschließen. Ein erfolgreiches Upgrade von Skype für Business enthält technische und User Readiness-Experten Aktivitäten. Wir in dieser Anleitung jetzt arbeiten, und wir werden werden Veröffentlichung bald.
 
## <a name="upgrade-and-coexistence-modes-defined"></a>Upgrade und Koexistenz Modi definiert
Um Ihren Entscheidungsprozess zu unterstützen, machen Sie sich mit den verschiedenen Modi, Konzepte und Terminologie relevant für ein Upgrade von Skype für Unternehmen, die Teams.

### <a name="skype-for-business-with-teams-collaborationndashonly-mode"></a>Skype für Unternehmen mit Zusammenarbeit für Teams&ndash;nur Kopfzeilen herunterladen

In diesem Modus Teams zur Unterstützung von Teams und Unterhaltungen Kanäle-basierte nur mit privaten Chats, Anrufe und Besprechungen deaktiviert konfiguriert.

Dieser Modus ist eine hervorragende Möglichkeit zum einführen Teams in Ihrer Umgebung laufendem nutzen Ihre vorhandenen Investitionen in Skype für Unternehmen. 

### <a name="skype-for-business-with-teams-collaboration-and-meetings-mode"></a>Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen Modus
Starten Sie zusammen mit Teams für Teams und Kanäle-basierte Unterhaltungen in diesem Modus verwenden, Benutzer verwenden von Teams zum Planen und Durchführen einer Besprechung. Private Chats und VoIP und video-Anruf, bleiben auf Skype für Unternehmen.

Wenn Ihre Organisation benötigt die Funktionen, die Teams für Besprechungen bereitstellt, aber Business die Enterprise Voice-Funktionen in Skype für Unternehmen lassen müssen muss, können Sie Teams zum Übermitteln von Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen konfigurieren. Funktionen, die die gesamte Organisation (oder Teile davon).

### <a name="islands-mode"></a>Inseln-Modus
Dies ist der Standardmodus. Sie können damit Teams unabhängig von Skype für Unternehmen bereitstellen. 

In diesem Modus können Teams Benutzer sofort Teams mit alle Funktionen mit anderen Benutzern Teams, während andere Benutzer weiterhin verwenden Skype für Unternehmen und produktiv ohne Auswirkung bleiben auf, wie Sie ihre Skype für Unternehmen heute verwenden können.

> [!NOTE]
> Inseln-Modus im Lieferumfang von unidirektionalen temporäre Interoperabilität, die Chat Interoperabilität Teams zu Skype für Unternehmen ermöglicht, wenn folgenden Bedingungen erfüllt sind:
> - Der Benutzer Teams ist am verwaltet und für Skype für Business Online aktiviert.
> - Die Skype für Geschäftsbenutzer Teams wurde noch nie verwendet (oder ist nicht für Teams lizenziert).
>
> Dieser Modus ist hilfreich, wenn Sie möchten, dass Benutzer, die in erster Linie Teams Verbindung mit anderen Benutzern in der Organisation, die noch Skype nur für Unternehmen verwenden möchten, verwenden.
>
> Nach dem start der Benutzer, die zuvor nur Skype für Unternehmen verwendet, Teams verwenden, werden alle ihre Chats von anderen Benutzern Teams in Teams eingehen. Microsoft Office Project diese Benutzer auf den Inseln-Modus. Ab diesem Zeitpunkt müssen sie weiterhin ausgeführt Teams, um sicherzustellen, dass sie mit den anderen Teams-Benutzern in der Organisation bleiben.

### <a name="teams-only-mode"></a>Nur Teams-Modus
In diesem Modus aktualisierten bietet die Skype für Business-Client nicht mehr grundlegende Funktion von Sofortnachrichten, Anwesenheit Indikatoren, Chat, aufrufen oder Meeting-Funktionen. Benutzer, die in aktualisierten Modus arbeiten müssen Teams als primäres Tool Kommunikation und Zusammenarbeit verwenden.

Benutzer, die als primäre Kommunikation und Zusammenarbeit Tool Teams verwenden möchten, können als Teams nur Benutzer aktualisiert werden.

Ein aktualisierter Benutzer können nur die Skype für Business-Client an vorhandenen Skype für Business Besprechungen oder Skype für Unternehmen, die vom Benutzer nicht aktualisiert oder externen Parteien organisierte Besprechungen teilnehmen. Ein aktualisierter Benutzer kann weiterhin mit anderen Benutzern in der Organisation zu kommunizieren, die noch Skype für Unternehmen mithilfe der Funktionen Interoperabilität zwischen Teams und Skype für Unternehmen.

### <a name="skype-for-businessndashonly-mode"></a>Skype für Unternehmen&ndash;nur Kopfzeilen herunterladen
Benutzer benötigen in Skype bleiben for Business als Skype für Unternehmen konfiguriert werden kann&ndash;nur Benutzer. Benutzer, die in diesem Modus konfiguriert werden verhindert mithilfe von Teams und zur Kommunikation mit Benutzern, die nur für Teams mithilfe der Funktionen Interoperabilität zwischen Teams und Skype für Business kann.

## <a name="upgrade-and-coexistence-building-blocks"></a>Upgrade und Koexistenz Bausteine
Um Ihre Organisation für die Reise Teams formell vorzubereiten, müssen Sie zum Starten der Planung für die Upgradeszenarien, mit denen schließlich Ihrer Organisation Teams vollständig als einzige Kommunikations- und Collaboration-Lösung zu übernehmen.

Wenn einige Ihrer Benutzer bereit sind, muss nur Teams für ihre über die alltägliche Kommunikation und Zusammenarbeit verwenden, können Sie beginnen, aktualisieren diese Benutzer auf Teams werden, da nur Teams-Modus für diese.

Wenn es nicht möglich, für die gesamte Organisation verschieben, Teams ist, können Sie mit der vollständig Einführung Teams als Lösung für die Zusammenarbeit Gruppe zuerst Beibehaltung Skype für Unternehmen als unified Communications-Lösung für Ihre Organisation starten. Eine weitere Option werden gestartet soll Besprechungen Teams zusätzlich zur Einführung in Teams Gruppe Zusammenarbeitsfunktionen, wobei den Rest der unified Communications-Funktionen in Skype für Business verschieben.

![Ein Screenshot des Upgrade Bausteine Skype für Unternehmen, Teams, bestehend aus Skype für Unternehmen mit Zusammenarbeit für Teams&ndash;Modus, Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen Modus, Inseln Modus, nur Teams-Modus und Skype für Business&ndash;nur Kopfzeilen herunterladen.](media/upgrade_and_coexistence_building_block.png)

Die folgende Tabelle vergleicht Upgrade und Koexistenz Modi.

|Modus  |Situation  |Kurzfristige Ziele  |Vorteile  |Warnhinweise  |
|---------|---------|---------|---------|---------|
|Skype für Unternehmen mit nur Teams für die Zusammenarbeit |Skype für die Business-Bereitstellung mit Anforderungen, die von Teams (beispielsweise erweiterte Compliance) noch nicht erfüllt ist<br><br>Langfristige Notwendigkeit und/oder Engagement Skype für Unternehmen|Starten Sie Teams Annahme schnell, zuerst Konzentration auf die Zusammenarbeit von Gruppen<br><br> Alle unified Communications-Arbeitslasten auf Skype für Unternehmen für jetzt gespeichert werden sollen|Keine überlappenden Funktionen zwischen Teams und Skype für Unternehmen<br><br>Instant messaging und Chat werden in Skype für Unternehmen (dem Aufruf von eingebunden) befinden.<br><br>|
|Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen |Skype für Business-Bereitstellung mit erhebliche Verwendung von Enterprise-VoIP und Anforderungen, die durch Aufrufen von Teams noch nicht erfüllt ist<br><br>Langfristige Notwendigkeit und/oder Engagement Skype für Unternehmen<br><br>Möglicherweise von einem Drittanbieter-Meeting-Dienst verwendet|Starten Sie Teams Annahme schnell jenseits für die Gruppenzusammenarbeit<br><br>Verbessern der Benutzer Besprechungen Betrieb|Keine sich überschneidenden Funktionen<br><br>Hochwertige Besprechungen auf Teams (WebRTC, Cloud besprechungsaufzeichnungen usw.)|Instant messaging und Chat werden in Skype für Unternehmen (dem Aufruf von eingebunden) befinden.|
|Inseln |Kleinere oder einfacher Skype für die Business-Bereitstellung<br><br>Möglichkeit und Bereitschaft zur einige kurzfristige Komplexität verwalten Teams schneller zu verschieben |Wechseln Sie zu der vollständigen Teams Erfahrung so schnell wie möglich<br><br>Durchführen einer Machbarkeitsstudie (PoC) des Teams |Einfach zu bedienen, keine Interoperabilität<br><br>Erleben Sie die besten Teams im Vorfeld für alle Funktionen |Erfordert eine gute Benutzerkommunikation um Verwechslungen zu vermeiden und zur Verwendung in Richtung Teams Laufwerk<br><br>Exit-Strategie erfordert, dass Benutzer für Business außer Betrieb genommen wird vollständig jeweils Skype Teams eingeführt haben|
|Nur Teams |Einige Benutzer müssen in der Skype für Unternehmen bleiben<br><br>Sie führen ein Upgrade Ihrer Skype für Business Online-Benutzer während nachhaltiger Schutz von Skype für Unternehmen Benutzern Skype für Business Server lokale-Teams<br><br>Sie können Benutzer in Inseln Modus bereits bereitgestellt haben und bereit sind, Stilllegung der Skype für Unternehmen für Gruppen von Benutzern |Senken der Variable auf Skype für Unternehmen (lokale Servervorgänge, Outsourcing Vertrag usw.)<br><br>Wechseln Sie zu der vollständigen Teams Erfahrung so schnell wie möglich, für mindestens einige Benutzer|Grenzwerte für Benutzer Verwirrung durch die Bereitstellung nur einen einzigen Client entwickelt|Interoperabilität unterstützt nur grundlegende Chat und Aufrufen von zwischen Skype für Unternehmen und Teams|
|Skype für Unternehmen nur |Einige Benutzer müssen in der Skype für Unternehmen bleiben<br><br>|Grenzwerte für Benutzer Verwirrung durch die Bereitstellung nur einen einzigen Client entwickelt|Fahren Sie mit den unternehmensanforderungen zu erfüllen, die derzeit nur von Skype für Unternehmen erfüllt werden können|Interoperabilität unterstützt nur grundlegende Chat und Aufrufen von zwischen Skype für Unternehmen und Teams|

> [!NOTE]
> Damit Sie jede der oben beschriebenen Modi aktivieren können, müssen wir veröffentlichen Quick Start Guide dazu, wie Sie Ihre Reise Skype für Business Teams ausführen, wenn die Richtlinien zu einem späteren Zeitpunkt zur Verfügung stehen. Demnächst!

## <a name="upgrade-journeys"></a>Upgrade Fahrten
Sie können mehrere Ansätze für ein Upgrade von Skype für Unternehmen, die entweder online schalten oder lokal, Teams:
- In einer einfachen Upgrade Weg Sie zuerst Teams in Skype für Unternehmen mit Teams für die Zusammenarbeit bereitstellen&ndash;nur Modus als Teil der Auswertung und frühe Anpassung, und klicken Sie dann implementieren Teams nur Modus mit dem Ziel schließlich abschließen Skype für Unternehmen aus der Umgebung für alle Benutzer in der Organisation.
- Ein schrittweises Upgrade Weg übermittelt eine bestimmte Aktualisierungsmodus an eine bestimmte Gruppe von Benutzern (auch als eine *Kohorte*bezeichnet), je nach ihrer Kommunikation und die Anforderungen an die Zusammenarbeit. Im Laufe der Zeit kann die gesamte Organisation konvergieren Teams nur die Nutzung und schließlich ersetzen Skype für Unternehmen. Allerdings hat Ihre Organisation überzeugende geschäftliche Gründe, Skype für Unternehmen zu halten – wie etwa eine Abhängigkeit von einer Unified Communications Managed API UCMA-basierte Lösung, die mit Line-of-Business Applications integriert oder eine "chinesische Mauer"-Lösung derzeit für Skype für Unternehmen nur – Sie können nur Teams-Modus Mehrheit der Benutzer aktualisieren, Beibehaltung Skype für eines der Skype für Business Modi für einen Teil des Benutzersegmente Geschäftsbenutzer.

> [!IMPORTANT]
> Für beide Arten von Upgrade Weg Wenn Ihre Organisation einen Skype für Business lokale Bereitstellung nur derzeit ist müssen Sie zum Starten der Planung Skype vor der Aktualisierung auf nur Teams-Modus für hybride Business implementieren möchten. Dadurch können auch Interoperabilität mit Teams zu vereinfachen.
> Verwenden Sie [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) Ihrer Skype für Business Hybrid-Implementierung, leiten lassen.

> [!NOTE]
> Nur Teams-Modus erfordert, dass die Benutzer, die Teil der Kohorten sind in Skype für Business Online verwaltet werden, und eine hybride Beziehung zwischen Ihrer Skype für die lokale Bereitstellung Business und Ihre Skype für Business Online Mandanten ist erforderlich, um das Upgrade zu erleichtern und Interoperabilität zwischen Skype für Unternehmen und Teams. Für Benutzer, die Teil der Kohorten sind, bevor sie auf nur Teams-Modus aktualisiert haben, muss der Wechsel zu Skype für Business Online abgeschlossen werden. Planen der Skype für Business Server 2019 sowie einem zukünftigen kumulativen Update für Skype für Business Server 2015 vereinfachen die Abläufe bei der Aktualisierung von lokalen Benutzern auf Teams durch die Migration zu Skype für Business Online verwalten und Aktualisieren der Benutzer nur-Teams Modus in einem Schritt.

Günstigsten Weg, die Sie auswählen, wird Microsoft hier unterstützt Sie durch den Aktualisierungsvorgang. Von technischen Vorschriften Ressourcen zur benutzerbereitschaft werden wir Leitfäden und bewährte Methoden zur Sicherstellung einer erfolgreichen Übergangsphase von Skype für Unternehmen, die Teams freigeben. Detaillierte Hilfe beim Upgrade wird bald bereit sein, daher sicher, dass Sie für die Weitere Informationen zu überprüfen.

### <a name="simple-upgrade-journey"></a>Einfaches Upgrade Reise
Der einfachen Upgrade Weg ist in der folgenden Abbildung dargestellt.

![Ein Screenshot des der einfachen Upgrade Weg. Alle Benutzer anfänglich Teams in Skype für Unternehmen mit Zusammenarbeit für Teams&ndash;nur Modus und dann den Umstieg von Teams nur im Modus, mit der Endzustand der gesamten Organisation auf Teams aktualisiert wurden.](media/upgrade_and_coexistence_simple_upgrade_journey.png)

Teams ist für alle Benutzer in der Organisation bereitgestellt und konfiguriert in Skype für Unternehmen mit Teams für die Zusammenarbeit&ndash;nur Kopfzeilen herunterladen. Ihre Organisation fest, dass Teams ist bereit zur aller Kommunikation und Zusammenarbeit Anforderungen erfüllen, werden alle Benutzer auf nur Teams-Modus aktualisiert. An dieser Stelle kann Skype für Unternehmen aus der Umgebung zurückgezogen werden.

### <a name="gradual-upgrade-journey"></a>Schrittweises Upgrade Reise
Ein Beispiel für ein schrittweises Upgrade Weg ist in der folgenden Abbildung dargestellt.

![In der schrittweisen Aktualisierung Weg verwenden Kohorten der Benutzer anfänglich Teams in einer Vielzahl von Upgrade ausgeführt werden: Anzeigemodus Skype für Unternehmen. Einige Kohorten Übergang auf Teams-only-Modus, während eine Gruppe von Benutzern mit Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen Modus bleibt.](media/upgrade_and_coexistence_gradual_upgrade_journey.png)

Teams wird mithilfe der verschiedenen Upgrade Modi für verschiedene Gruppen von Benutzern oder Kohorten in der Organisation bereitgestellt. Beispielsweise kann eine Gruppe von Benutzern für Inseln-Modus aktiviert werden, eine andere aktiviert für Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen Modus, während eine dritte Gruppe von Benutzern für Skype für Unternehmen mit Teams für die Zusammenarbeit zunächst aktiviert werden kann&ndash;nur Modus.

Im Laufe der Zeit können Gruppen von Benutzern, Teams-only-Modus, gefolgt von der restlichen Organisation aktualisiert werden. Schließlich wird die gesamte Organisation bereit für die Stilllegung der Skype für Unternehmen und verwenden nur Teams für Kommunikation und Zusammenarbeit, sein oder – wenn die geschäftlichen Abläufe, dass Skype für Unternehmen für eine bestimmte Gruppe beibehalten werden – die Mehrzahl der Benutzer in der Teams kann nur Organisation verwendet werden. <br><br>
<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul> Welche Upgrade Weg ist geeignet ist, geschäftlichen Anforderungen Ihrer Organisation?<br><br></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul> Identifizieren Ihrer aktuellen Bereitstellungsmodell, verwenden Sie Groß-/Kleinschreibung Szenarien und wichtige Überlegungen für Ihre Organisation informieren der Reise Teams, die für Ihre Organisation am besten geeignet ist.<br><br></ul></td></tr>
</table>

## <a name="upgrade-scenarios"></a>Upgradeszenarien
Basierend auf dem Upgrade weiter oben in diesem Artikel beschriebenen Fahrten, wird die folgenden Leitfäden für bestimmte Skype für Business Bereitstellungsmodelle bereitgestellt, die Ihrer aktuellen Bereitstellungsmodell zugeordnet werden kann. 

|Bereitstellungsmodell  |Ausgangspunkt  |Aspekte  |Reise  |
|---------|---------|---------|---------|
|Skype für Unternehmen – nur Online mit dem Aufrufen der Pläne |Office 365-Mandanten mit Azure Active Directory verbinden, SharePoint Online, Exchange Online und Skype für Business Online<br><br> Telefonsystem mit Aufrufen Plans mit Skype für Business Online für alle Benutzer implementiert |Alle Benutzer nutzen zertifizierten headsets<br><br> Besprechungen erfordern interne und anonyme externe VoIP-Teilnehmer<br><br> Messaging umfasst interne und externe Kontakte |**Wegweiser für Messaging**: Verbund-Feature für eine Version Q2 von 2018 vorgesehen sind<br><br> **Wegweiser für Besprechungen**: Funktionen sind bereits verfügbar<br><br> **Aufrufen von Roadmap**: Funktionen sind bereits verfügbar<br><br> Bausteine:<ul><li> Skype für Unternehmen mit Zusammenarbeit für Teams&ndash;nur Kopfzeilen herunterladen</li><li> Nur Teams-Modus</li></ul>|
|Skype für Unternehmen Online mit Cloud Connector Edition (CCE) |Office 365-Mandanten mit Azure Active Directory verbinden, SharePoint Online, Exchange Online und Skype für Business Online<br><br> Telefonsystem mit Hybrid-VoIP über CCE implementiert mithilfe von Skype für Business Online an mehreren Standorten<br><br> 1.000 Benutzer verwenden messaging und Voicemail-Arbeitslasten|80 % des Benutzers nutzt Telefonsystem mit Hybrid-VoIP über CCE<br><br> Alle messaging ist innerhalb des Unternehmens enthalten.<br><br> Besprechungen derzeit nicht verwendet werden, es gibt aber Interesse an Audiokonferenzen in Zukunft aktivieren|**Wegweiser für Messaging**: Funktionen stehen.<br><br> **Wegweiser für Besprechungen**: Zukunft Anforderungen erfüllt werden können<br><br> **Aufrufen von Roadmap**: Direktes routing zu Teams-Feature für eine Version Q2 von 2018 vorgesehen sind <br><br> Bausteine:<ul><li> Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen Modus</li><li> Nur Teams-Modus</li></ul> |
|Skype für hybride Business |Office 365-Mandanten mit Azure Active Directory verbinden, SharePoint Online, Exchange Online und Skype für Business Online<br><br> Skype für Business Server 2015 bereitgestellt und Hybrid wird mit Skype für Business Online konfiguriert.|Eine Anzahl von Benutzern erfordern die Funktion zum Aufzeichnen von Besprechungen<br><br> Es gibt 10 Konferenzräume, die derzeit nutzen Skype Raum Systemen v2<br><br> Die Organisation möchte Teams als Tool für die Zusammenarbeit so schnell wie möglich nutzen|**Wegweiser für Messaging**: Funktionen stehen.<br><br> **Wegweiser für Besprechungen**: Cloud besprechungsaufzeichnung, meeting Raum Geräte-Feature für eine Version Q2 von 2018 vorgesehen sind<br><br> **Aufrufen von Roadmap**: Funktionen stehen.<br><br> Bausteine:<ul><li>Skype für Unternehmen mit Zusammenarbeit für Teams&ndash;nur Kopfzeilen herunterladen</li><li> Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen Modus</li><li>Inseln-Modus</li><li>Nur Teams-Modus</li></ul> |
|Skype für Business Server (lokal) |Office 365-Mandanten mit Azure Active Directory verbinden und Exchange Online<br><br> SharePoint- und Skype für Unternehmen werden lokal bereitgestellt|Vollständige Enterprise-VoIP-Funktion (Skype für Business Server 2015) derzeit verwendeten festlegen<br><br> Kontakt Center bereitgestellt<br><br> Besprechungen werden mit internen und externen Verbundbenutzer mit VoIP und einwahlkonferenzen durchgeführt<br><br> Messaging mit internen und externen Benutzern|Bereitstellen von SharePoint Online<br><br> Konfigurieren von Skype für Business Hybrid (getrennte Domäne)<br><br>**Wegweiser für Messaging**: Verbund-Feature für eine Version Q2 von 2018 vorgesehen sind<br><br> **Wegweiser für Besprechungen**: Federated Teilnahme an einer Besprechung, PSTN Lobby-Feature für eine Version Q2 von 2018 vorgesehen sind<br><br> **Aufrufen von Roadmap**: Feature für die Version Q4 2018 und danach vorgesehen sind<br><br>Bausteine:<ul><li>Inseln Modus (Pilotphase)</li><li>Skype für Unternehmen mit Zusammenarbeit für Teams&ndash;nur Kopfzeilen herunterladen</li><li>Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen Modus</li><li>Nur Teams-Modus und Skype für Unternehmen&ndash;nur Kopfzeilen herunterladen</li></ul><br>Überprüfen des Upgrades zu Skype für Business Server 2019|

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul> Welche Upgradeszenario gilt für Ihre Organisation?<br><br></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul> Entscheiden Sie den Zeitplan Ihrer Organisation Upgrade Reise basierend auf messaging, Besprechungen und Aufrufen von geschäftsanforderungen.<br><br> Entscheiden Sie zusätzlichen Aufwand für die Durchführung Ihrer Reise Upgrade erforderlichen.<br><br></ul></td></tr>
</table>

## <a name="see-also"></a>Siehe auch
[Verwalten von Teams während des Übergangs auf die neuen Microsoft-Teams und Skype für Business Admin Center](manage-teams-skypeforbusiness-admin-center.md)
