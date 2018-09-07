---
title: Praktische Anleitungen für Telefonsysteme mit Anrufplänen in Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Praktische Anleitungen für die Planung, Bereitstellung und Verwaltung von Telefonsystemen mit Anrufplänen in Microsoft Teams mithilfe eines Frameworks, das die Phasen „Konzeptionierung“ (Planung), „Onboarding“ (Bereitstellung) und „Wertschöpfung“ (Einsatz) vorsieht
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
redirect_url: https://docs.microsoft.com/MicrosoftTeams/cloud-voice-deployment
ms.openlocfilehash: 2ce4d09113cc75381379fa6f9481eca2ae27c2ea
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23853655"
---
<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a>Praktische Anleitungen für Telefonsysteme mit Anrufplänen in Microsoft Teams
=========================================================================

Das Telefonsystem ist eine Office 365-Funktion, die das Verwalten von Anrufweiterleitung, Richtlinien und Benutzerbereitstellung ermöglicht. Dazu gehören ein Verwaltungssystem für Telefonanrufe sowie Anrufweiterleitung und Anrufsteuerung.

Office 365-Anrufpläne werden als Add-On-Dienst für die Telefonsystemfunktion über Microsoft Teams und Skype for Business Online bereitgestellt. Mit Anrufplänen erhalten die Mitarbeiter Ihres Unternehmens eine primäre Telefonnummer, über die sie außerhalb der Organisation Telefonanrufe über das Telefonfestnetz (Public Switched Telephone Network, PSTN) tätigen und erhalten können.

Weitere Informationen finden Sie unter [Das bietet Ihnen das Telefonsystem in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) und [Was sind Anrufpläne in Office 365?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365).

Diese praktischen Anleitungen führen Sie durch das Framework der Office 365 FastTrack Customer Journey und seine drei Phasen (Konzeptionierung, Onboarding und Wertschöpfung), damit Sie eine erfolgreiche Implementierung des Telefonsystems mit Anrufplänen planen, bereitstellen und verwenden können.

> [!TIP]
> Sie erhalten hier Beispielergebnisse für die einzelnen Aktivitäten und die wichtigsten Diskussionspunkte. Die Beispiele in diesem Dokument, die Sie als wiederverwendbare Vorlagen nutzen können, finden Sie in den mit „Tipp“ beschrifteten Kästen. Der Hinweis „TBA“ (To Be Added, wird ergänzt) zeigt an, dass Sie hier Informationen als Teil Ihres Planungsprozesses eingeben müssen.

Ausblick <a name="Envision_PhoneSystemWithCallingPlans"> </a>
========

Die Konzeptionierungsphase stellt die Grundlage für die Office 365 Customer Journey dar und kann auf alle Arbeitsauslastungen wie zum Beispiel Telefonsysteme mit Anrufplänen angewendet werden.

In dieser Phase formulieren die jeweiligen Projektbeteiligten die Geschäftsziele und stellen Folgendes bereit:

-   Einen umfassenden Erfolgsplan mit Geschäftsanwendungsfällen, wichtigen Beteiligten, Zielen und wesentlichen Ergebnissen, wichtigen Erfolgsindikatoren, Risiken, einer Bewertung der Umgebung, Einführungsbereitschaft und Einsatzplanung

-   Einen detaillierten Implementierungsplan für das Telefonsystem mit Anrufplänen, mit dem der gewünschte Endzustand erreicht werden soll

<a name="define-business-use-cases-for-phone-system-with-calling-plans"></a>Definieren von Geschäftsanwendungsfällen für das Telefonsystem mit Anrufplänen
-------------------------------------------------------------

Mit einem Telefonsystem mit Anrufplänen können Organisationen ihre Arbeitsplätze modernisieren, indem sie es den Benutzern ermöglichen, geschäftliche Telefonanrufe über ihre Computer und mobilen Geräte zu tätigen.

Die Arbeitsplatzmodernisierung kann im Rahmen der folgenden Aktivitäten vorgenommen werden: tätigkeitsbezogene Arbeitsimplementierung, Büroumzüge, Aktualisierung der Büroausstattung, Außerbetriebnahme von Legacylösungen für Nebenstellenanlagen (PBX), Abschluss eines Vertrags mit einem PSTN-Dienstanbieter usw.

In diesem Schritt definieren die wichtigsten Projektbeteiligten Geschäftsanwendungsfälle, die die Implementierung eines Telefonsystems mit Anrufplänen unterstützen.

Mit Geschäftsanwendungsfällen werden die erwarteten und messbaren Geschäftsergebnisse dokumentiert. Dazu zählen:

-   Beschreibung des aktuellen Geschäftsprozesses
-   Herausforderungen bei den vorhandenen definierten Geschäftsprozessen
-   Wie diese Herausforderungen mithilfe der Technologie bewältigt werden können
-   Die erwarteten messbaren Geschäftsergebnisse, die durch die Bewältigung dieser Herausforderungen erzielt werden können

> [!TIP]
> Das folgende Beispiel zeigt einen abgeschlossenen Geschäftsanwendungsfall:
>|         |
>|---------|
>|**Beschreibung des aktuellen Geschäftsprozesses**<p>Die Standardkonfiguration der Büroarbeitsplätze in Contosos Niederlassung sieht für jeden Schreibtisch ein Festnetztelefon vor. Jeder Mitarbeiter erhält eine Direktwahlnummer. Die Festnetztelefone sind mit einem PBX-System verbunden und über einen SIP-Trunk (Session Initiation-Protokoll) an das PSTN angebunden. Die Mitarbeiter können nur an den ihnen zugewiesenen Festnetztelefonen Telefonanrufe tätigen und empfangen.|
>|**Herausforderungen mit vorhandenen Geschäftsprozessen**<p>Aus der Nutzungsanalyse für die Festnetztelefone geht hervor, dass nur 10 % der Festnetztelefone aktiv verwendet werden. Der Rest ist entweder für die Weiterleitung von Anrufen an Mobiltelefone oder für gleichzeitiges Anrufen bei Mobiltelefonen konfiguriert. Die Wartung des vorhandenen PBX-Systems und der zugehörigen Festnetztelefone macht 20 % der monatlichen Kosten für Telefoniedienste aus.|
>|**Wie diesen Herausforderungen am besten begegnet werden kann**<p>Mit dem Telefonsystem mit Anrufplänen können Endbenutzer auf ihren Personalcomputern Telefonanrufe über ein Datennetzwerk empfangen und tätigen und dazu die native Microsoft Teams-App verwenden. Dadurch entfällt die Notwendigkeit, Festnetztelefone einzuführen und zu warten. Außerdem wird die Möglichkeit eröffnet, das vorhandene PBX-System außer Betrieb zu setzen, da der Telefondienst ohne Abhängigkeit von herkömmlichen Telefonsystemen cloudbasiert über das Netzwerk bereitgestellt werden kann.|
>|**Erwartete, messbare Geschäftsergebnisse**<p>Durch die Beseitigung der Anforderungen für die Wartung und Außerbetriebnahme von bestehenden älteren PBX-Systemen und Festnetztelefonen werden die monatlichen Ausgaben für Telefoniedienste um 20 % gesenkt. Durch das Telefonsystem mit Anrufplänen werden die Büroarbeitsplätze vereinfacht, sodass Contoso seine Geschäftstätigkeit durch die Einrichtung neuer Büros mit minimalen Vorabkosten für Telefonie erweitern kann.|

In der Konzeptionierungsphase sollten Sie nicht nur die Geschäftsanwendungsfälle definieren, sondern sich auch in den folgenden Punkten Klarheit verschaffen:
- Organisatorischer Geltungsbereich
- Projektzeitplan

<a name="identify-key-stakeholders"></a>Identifizieren der wichtigsten Projektbeteiligten
-------------------------

Die im vorherigen Schritt definierten Geschäftsanwendungsfälle umfassen den organisatorischen Geltungsbereich der Implementierung des Telefonsystems mit Anrufplänen. Auf dieser Grundlage können Sie eine umfassende Matrix der Beteiligten erstellen, um die richtigen Personen in das Projekt einzubeziehen.

> [!TIP]
> In der folgenden Beispielvorlage für diese Matrix können Sie die Projektbeteiligten dokumentieren.
>|Rolle  |Beschreibung  |Name, Kontaktinformationen, Standort  |
>|---------|---------|---------|
>|Leitender Projektsponsor|<ul><li>Hat höchste Entscheidungsbefugnis und Rechenschaftspflicht für das Projekt und die Bereitstellung von Projektzielen</li><li>Bietet Unterstützung bei der Lösung der vom Projektleiter eskalierten Probleme</li><li>Bietet Unterstützung bei die Kommunikation innerhalb des Unternehmens</li><li>Ist für wichtige strategische Entscheidungen verantwortlich</li><li>Trägt Verantwortung für die Verfügbarkeit der erforderlichen Ressourcen und das benötigte Budget</li><li>Verfasst vierteljährliche Geschäftsberichte</li><li>Organisiert und unterstützt Sensibilisierungskampagnen</li><li>Ist Projektsponsor für das Programm-Rollout</li></ul>|TBA|
>|Projektleiter|<ul><li>Führt und leitet das Projektteam</li><li>Koordiniert die am Projekt beteiligten Partner und Arbeitsteams</li><li>Ist für das Erstellen und Verwalten von Projektplänen verantwortlich, um die wesentlichen Quartalsergebnisse zu erzielen</li><li>Behebt funktionsübergreifende Probleme</li><li>Erstellt einen regelmäßigen Rechenschaftsbericht für die Projektsponsoren</li><li>Bezieht Übernahmeaspekte in den fertigen Projektplan ein</li><li>Verfasst monatliche Geschäftsberichte als Grundlage für vierteljährliche Geschäftsberichte</li></ul>|TBA|
>|Leiter/Architekt für Zusammenarbeit|<ul><li>Ist für die Ausführung der Zusammenarbeitsstrategie verantwortlich, die von den Führungskräften des Unternehmens definiert wird</li><li>Analysiert und wählt Produkte für die Zusammenarbeit für das Unternehmen aus, das die Geschäftsziele erreicht</li><li>Ist für die operationale Architektur von Produkten für die Zusammenarbeit verantwortlich</li><li>Definiert operative und Support-Modelle</li><li>Liefert Beiträge für die monatlichen und vierteljährlichen Geschäftsberichte</li><ul>|TBA|
>|Berater|<ul><li>Ist für Konfigurationsdienste verantwortlich</li><li>Liefert Beiträge zur Architektur der Gesamtlösung</li></ul>|TBA|
>|Projektmanager|<ul><li>Entwickelt und verwaltet den Projektplan</li><li>Verwaltet die Projektergebnisse in Bezug auf die Einhaltung des Projektplans und des Budgets</li><li>Zeichnet Projektprobleme (zum Beispiel Eskalationen) auf und verwaltet diese</li><li>Tätigt wöchentliche Teamanrufe</li><li>Kontaktiert die leitenden Projektsponsoren und stellt aktuelle Informationen bereit</li><li>Arbeitet mit dem Architekten zusammen, um den Change Management-Ansatz und die Kommunikationspläne zu definieren</li></ul>|TBA|
>|Spezialist für Change Management/Einführung|<ul><li>Liefert Beiträge zu Übernahme- und Schulungsprozessen in der Entdeckungsphase</li><li>Nimmt am Workshop für Übernahmestrategie teil</li><li>Entwickelt die Übernahmestrategie und ist für diese verantwortlich</li><li>Entwickelt Kommunikationspläne und führt diese aus</li><li>Ist verantwortlich für die Bereitstellung von Schulungen für Endbenutzer</li><li>Sammelt Feedback und führt Umfragen durch</li></ul>|TBA|
>|Netzwerkleiter|<ul><li>Liefert Beiträge zum Netzwerkdesign in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Koordiniert die Arbeit des Netzwerkteams während der Projektausführung</li></ul>|TBA|
>|Leiter der Sicherheit|<ul><li>Liefert Beiträge zu Übernahme- und Schulungsprozessen in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Koordiniert die Arbeit des Sicherheitsteams während der Projektausführung</li></ul>|TBA|
>|Telefonieleiter|<ul><li>Liefert Beiträge zum Telefonie-Design in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Koordiniert die Arbeit des Telefonie-Teams während der Projektausführung</li></ul>|TBA|
>|Desktopleiter|<ul><li>Liefert Beiträge zu Client- und Updateprozessen in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Koordiniert die Arbeit des Desktop-Teams während der Projektausführung</li></ul>|TBA|
>|Support-/Helpdeskleiter|<ul><li>Liefert Beiträge zum operativen Modell und zum Support-Modell in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Nimmt an der Planung des Support-Modells teil</li><li>Koordiniert die Arbeit des Support-Teams/der Ressourcen während der Projektausführung</li></ul>|TBA|
>|Vertreter der Betriebseinheiten|<ul><li>Liefern Beiträge zur Endbenutzer-basierten Übernahme von Anleitungen und Begleitmaterialien</li><li>Tragen zu Geschäftsanwendungsfällen bei und überprüfen diese</li></ul>|TBA|
>|Bereitstellungsleiter|<ul><li>Stellt sicher, dass die Systemvoraussetzungen erfüllt sind</li><li>Leitet Kundenressourcen an, sich an der Vorbereitung und Bereitstellung von Aktivitäten in den einzelnen Phasen zu beteiligen</li><li>Nimmt an Besprechungen zur Überprüfung des Vorbereitungs- und Bereitstellungsstatus teil</li></ul>|TBA|
>|IT-Administratoren|<ul><li>IT-Experten, die für die Unterstützung in der Testplanung und -ausführung verantwortlich sind</li></ul>|TBA|
>|Leiter des Kundendiensts|<ul><li>Trägt die Gesamtverantwortung für die reibungslose Funktion des Telefonsystemdiensts mit Anrufplänen</li><li>Besitzer des Telefonsystemdiensts mit Anrufplänen</li></ul>|TBA|
>|Qualitätspioniere|<ul><li>Trägt zur Verbesserung der Qualität, Verlässlichkeit und des Benutzerfeedbacks bei</li><li>Ermittelt Qualitätstrends und schafft Abhilfe bei Problemen mit den jeweiligen Teams</li><li>Ist verantwortlich für die Berichterstattung zwischen dem Lenkungsteam und dem Führungsstab</li><li>Erstellt Berichte über Qualität, Verlässlichkeit und Verbraucherstimmung über „Meinen Anruf bewerten“ und „Net Promoter Score“</li></ul>|TBA|

<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Definieren von Zielen und wesentlichen Ergebnissen, wichtigen Erfolgsindikatoren und Risiken
--------------------------------------------------------------------

Wenn Sie die Projektbeteiligten festgelegt haben, können Geschäftsanwendungsfälle, organisatorische Geltungsbereiche und Projektzeitpläne in Ziele und wesentliche Ergebnisse übersetzt werden, und die Kennzahlen des Projekterfolgs können in einer Liste mit den wichtigen Erfolgsindikatoren definiert werden.

Durch die Teilnahme aller Projektbeteiligten bei der Festlegung der Ziele und wesentlichen Ergebnissen sowie der wichtigen Erfolgsindikatoren wird das Verantwortungsbewusstsein geschärft, und eine Anpassung an die organisatorischen Geschäftsanforderungen wird sichergestellt.

Ziele und wesentliche Ergebnisse enthalten die Liste der Ziele, die zu Projektbeginn festgelegt wurden. Sie enthalten unter anderem messbare Ergebnisse auf Quartalsbasis. Diese Kernergebnisse werden monatlich ausgewertet, um den Status des gesamten Projekts zu verfolgen. Des Weiteren kann basierend auf dem Fortschritt eine Anpassung der Quartalspläne nach Bedarf vorgenommen werden.

> [!TIP]
> Das folgende Beispiel enthält Ziele und wesentliche Ergebnisse, die für die Implementierung eines Telefonsystems mit Anrufplänen relevant sind:
><br>
>
>**Vision: Steigern der Produktivität durch Maximierung der Investition in Office 365**
>|Ziele  |Wesentliche Ergebnisse  |Aufgabe  |
>|---------|---------|---------|
>|Bereitstellen eines Telefonsystems mit Anrufplänen in den europäischen Zweigniederlassungen bis zum Ende des Geschäftsjahrs 2018|3. Quartal des Geschäftsjahrs 2018: Bereitstellung eines Telefonsystems mit Anrufplänen in der Niederlassung in London|Konzeptionierung<ul><li>Erfolgsplan erstellen</li><li>Detaillierten Plan für die technische Implementierung erstellen</li></ul><p>Onboarding<ul><li>Erfolgsplan ausführen</li><li>Plan für die technische Implementierung ausführen</li></ul>|
>|Außerbetriebsetzung des Legacy-PBX-Systems in der Niederlassung in London bis zum Ende des Geschäftsjahrs 2018|4. Quartal des Geschäftsjahrs 2018: Außerbetriebsetzung des Legacy-PBX-Systems in der Niederlassung in London|Höhere Wertschöpfung erzielen<ul><li>Benutzerengagement verstärken und Übernahme vorantreiben</li><li>Veränderungen vorbereiten und verwalten</li><li>Erfolg messen und teilen und Durchlauf beschleunigen</li>|

Mit den wichtigen Erfolgsindikatoren werden die Qualität und der Erfolg der Kernergebnisse gemessen, und sie vervollständigen den binären Charakter von Zielen und wesentlichen Ergebnissen (erreicht oder nicht erreicht) durch detaillierte Aufschlüsselung von guten bzw. schlechten Ergebnissen. Bei der Definition der wichtigen Erfolgsindikatoren empfehlen wir, „spezifische, messbare, zuweisbare, realistische, zeitbezogene“ und INTELLIGENTE Kriterien zugrunde zu legen.

> [!TIP]
> Im folgenden Beispiel sehen Sie für dieses Projekt relevante wichtige Erfolgsindikatoren:
>|Typ  |Fragen und Kriterien im Zusammenhang mit den wichtigen Erfolgsindikatoren  |Messmethode  |Erfolgskriterien  |Bemessungszeitpunkt  |Verantwortlich  |
>|---------|---------|---------|---------|---------|---------|
>|Verwendung/Einführung|Anrufqualität entspricht der vorherigen Lösung oder übertrifft diese|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach der Aktivierung und vierteljährlich|IT-Team|
>|Verwendung/Einführung|Microsoft Teams hat den Kommunikationsprozess vereinfacht.|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach der Aktivierung und vierteljährlich|Change Management-Team|
>|Verwendung/Einführung|Aktive Verwendung der Lösung durch die Benutzer|Office 365-Berichte, Anrufqualitäts-Dashboard|80 % der Benutzer sind täglich aktiv|Täglich|Change Management-Team|
>|Verwendung/Qualität|Prozentsatz der Anrufe/Konferenzen mit schlechter Qualität sollte verringert werden|Anrufqualitäts-Dashboard|< 5 % Anrufe mit schlechter Qualität pro Monat|Täglich|IT-Team|
>|Verwendung/Support|Ich weiß, wo ich technischen Support erhalte|Umfrage|Zustimmung oder starke Zustimmung bei 90% der Benutzer|Nach der Aktivierung und vierteljährlich|Change Management-Team|
>|Verwendung/Support|Ich bin zufrieden mit der Qualität des technischen Supports|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach jedem Vorfall|IT-Team|
>|Finanzen|Senkung der monatlichen Ausgaben für Telefoniedienste|Finanzsystem|Definierte Rendite erzielen|Basierend auf Rendite|Change Management-Team|

Als Teil dieser Übung müssen Sie Geschäftsrisiken sowie einen Risikominderungsplan für jedes erkannte Risiko definieren. Halten Sie diese Informationen in einem Risikoplan fest.

> [!TIP]
> Den Risikoplan können Sie wie im folgenden Beispiel dokumentieren:
>|Risiko  |Wahrscheinlichkeit  |Auswirkungen  |Gesamt  |Risikominderungsplan  |
>|---------|---------|---------|---------|---------|
>|Bei der bevorstehenden Fusion werden bis zu 1.000 Personen dazukommen|Hoch|Hoch|Hoch|<ul><li>Separate Ziele und wesentliche Ergebnisse mit eigenem Prozess (Ausblick, Onboarding und Wertschöpfung) für fusioniertes Unternehmen</li><li>Beziehen Sie diesen Prozess nicht in vorhandene Ziele und wesentliche Ergebnisse ein.</li></ul>|
>|Die Portierung von Telefonnummern verzögert den Projektabschluss.|Hoch|Hoch|Hoch|<ul><li>Bereiten Sie frühzeitig alle erforderlichen Informationen zur Unterstützung der Portierung von Telefonnummern vor (z. B. Kundendiensteintrag, Rechnungsdetails, schriftliche Vollmacht).</li><li>Passen Sie die Zeitschiene für das Projekt an, um die Dauer für die Portierung der Telefonnummern zu berücksichtigen.</li><li>Verwenden Sie vorübergehende Telefonnummern mit Änderung der Anrufer-ID.</li></ul>|
>|Geplante Umgestaltung des Netzwerks|Hoch|Mittel|Mittel|<ul><li>Führen Sie vor der Implementierung von Teams als moderne Plattform für Kommunikation und Zusammenarbeit eine Auswertung der Netzwerkbereitschaft für Websites durch, die im Geltungsbereich des Projekts liegen.</li></ul>|

<a name="assess-environment-and-evaluate-adoption-readiness"></a>Bewerten der Umgebung und Überprüfen der Übernahmebereitschaft
--------------------------------------------------

Um die gewünschten Ziele und wesentlichen Ergebnisse zu erreichen, müssen Sie möglicherweise die allgemeine Architektur der Lösung definieren. Sie müssen Ihre Umgebung sehr gründlich erkunden, um alle Aspekte der IT- und Telefonie-Infrastruktur, des Netzwerks und des Betriebs auswerten zu können.

Die Ermittlung der Umgebung umfasst alle zum Endbenutzercomputing gehörenden Aspekte wie die Bewertung der Bereitschaft der PCs und mobilen Geräte für die Unterstützung von Geschäftsanwendungsfällen für das Telefonsystem mit Anrufplänen – von den Hardwareanforderungen bis zu den Softwareanforderungen.

Die Ermittlung der Umgebung kann auch Aufschluss darüber geben, ob Sie [Telefonnummern zu Microsoft übertragen](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) müssen. Dies hilft Ihrer Organisation, den Projektplan entsprechend anzupassen und die für die Nummernportierung notwendigen Informationen bereitzustellen. Verwenden Sie bei der Ermittlung der Umgebung den [Untersuchungsfragebogen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_3).

Bei der Ermittlung der Umgebung muss die Bereitschaft des Netzwerks bewertet werden, um sicherzustellen, dass das Netzwerk bereit ist, die Implementierung des Telefonsystems mit Anrufplänen zu unterstützen.

Die Netzwerkbereitschaft zur Unterstützung des Telefonsystems mit Anrufplänen kann mithilfe der bei der Ermittlung der Umgebung gesammelten Informationen bestimmt werden. Diese Informationen umfassen Details zur Internetkonnektivität und WAN-Topologie, zu Standortverknüpfungen und zur verfügbaren Bandbreite sowie Persona-Analysedaten, die mit dem [My Advisor Network Planner-Tool](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) in eine erwartete Nutzung der einzelnen Arbeitsauslastungen übersetzt werden können. Um die Netzwerkbereitschaft noch genauer zu ermitteln, können Sie mit den folgenden Lösungen den Mediendatenverkehr in Echtzeit simulieren:
- Von Microsoft: [Skype for Business Network Assessment-Tool](https://www.microsoft.com/download/details.aspx?id=53885)
- Von Partnern: [Partner, die Network Readiness Assessment-Tools anbieten](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Partners?ToolPartners)

Die Ergebnisse der Bewertung der Netzwerkbereitschaft zeichnen ein klares Bild der für eine erfolgreiche Implementierung des Telefonsystems mit Anrufplänen erforderlichen Netzwerkoptimierungs- oder Verbesserungsmaßnahmen.

Die Einführungsbereitschaft kann durch die Ausführung einer Persona-Analyse bewertet werden. Dabei wird eine Liste der Personas in der Organisation erstellt, die für die Implementierung des Telefonsystems mit Anrufplänen infrage kommen. Die Personenanalyse umfasst die Ermittlung weiterer Peripheriegeräte und sonstigen Geräten, die für die Erzielung der gewünschten Geschäftsergebnisse erforderlich sind.

Zur Ausführung einer Personenanalyse können Sie einen Workshop durchführen, indem Sie die jeweiligen Projektbeteiligten einbeziehen und die Workshop-Folie [Persona Alignment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_7) und die [Persona Feature Matrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_8) verwenden. Das Ergebnis des Personenanalyse-Workshops kann mit der Vorlage [Persona Analysis Report](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_9) in einem Bericht zusammengefasst werden.

> [!NOTE]
> Obwohl die Discovery Questionnaire- und die Persona Analysis-Beispiele zunächst für Skype for Business Online geschrieben wurden, sind die meisten Inhalte auch auf Teams übertragbar. Sie können Punkte, die für Ihre Projektziele nicht relevant sind, nach Belieben ändern oder entfernen.

Sie können die technischen Risiken als Teil einer Auswertung der Umgebung und Bewertung der Übernahmebereitschaft ermitteln und einen Plan zur Abhilfe für jedes erkannte Risiko entwickeln. Diese Informationen sollten als Teil des Risikoplans berücksichtigt werden.

<a name="map-operational-roles"></a>Zuordnen von operativen Rollen
---------------------

Die Planung der Ausführung und die Benennung der Teams, die den Telefonsystemdienst mit Anrufplänen ausführen, ist ein wichtiger Schritt, da die Ausführung beginnen muss, wenn die ersten Teilnehmer des Pilotprojekts aktiviert werden. Jedes benannte Team muss die angegebenen Aufgaben und Verantwortlichkeiten überprüfen und diesen zustimmen und mit der Vorbereitung der Ausführung des Telefonsystemdiensts mit Anrufplänen beginnen. Die Vorbereitung kann Schulungen, die Bewertung der Bereitschaft, die Einbeziehung zusätzlicher Mitarbeiter oder die Verpflichtung von externen Anbietern zur Bereitstellung des Diensts umfassen.

> [!TIP]
> In der folgenden Beispielvorlage wird das Ergebnis der Zuordnung der operativen Rollen dokumentiert, die Sie für dieses Projekt vorgenommen haben:
>|Operative Rolle  |Beschreibung  |Team  |Kontaktdetails  |
>|---------|---------|---------|---------|
>|Leiter des Kundendiensts|Diensteigentümer, Schnittstelle zu Geschäftsabteilungen, Strategie|TBA|TBA|
>|Ausführung des Telefonsystems mit Anrufplänen|Tägliche Aufgaben, Verschieben/Hinzufügen/Ändern von Benutzer- und Gerätekonten, Überwachung|TBA|TBA|
>|Mandantenadministrator|Ändern von mandantenweiten Einstellungen, Aktivieren von neuen Funktionen|TBA|TBA|
>|Helpdesk|Support-Schnittstelle für Endbenutzer|TBA|TBA|
>|Netzwerkaufgaben|Ausführung von LAN, WAN, WLAN und Internetzugriff|TBA|TBA|
>|Team für Clients und Endpunkte|Verwalten von Desktopbereitstellungen|TBA|TBA|
>|Ermitteln von Aufgaben|Verwalten der Identitätsinfrastruktur (AD, ADFS, Azure AD)|TBA|TBA|
>|Übernahme/Change Management|Sensibilisierung, Schulung und Übernahme für die Lösung|TBA|TBA|
>|Exchange-Aufgaben|Verwalten der Exchange-Umgebung|TBA|TBA|

Sie können die detailliertere Zuordnung der operativen Rollen (einschließlich der mit jeder operativen Rolle verbundenen Aufgaben) vereinfachen, indem Sie in der [Arbeitsmappe für die Zuordnung von operativen Rollen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16) die Details erfassen, die Ihnen einen Überblick über die Rollen und Verantwortlichkeiten für die Unterstützung des Telefonsystemdiensts mit Anrufplänen geben.

<a name="document-success-plan"></a>Dokumentieren des Erfolgsplans
---------------------

Ein Erfolgsplan ist die in der Phase Ausblick erstellte Dokumentation, die aus dem Geschäftsszenario, der Bereitschaft für den Dienst, dem Übernahme- und Aufgabenplan besteht.

Der Erfolgsplan stattet das Projektteam – zu dem FastTrack oder ein Bereitstellungspartner gehören kann – mit ausreichenden Informationen aus, um die Ziele der Organisation mit dem Telefonsystem mit Anrufplänen zu erreichen.

In der Regel enthält ein Erfolgsplan die folgenden Hauptabschnitte:

-   Geschäftsszenario
-   Bereitschaft für den Dienst
-   Übernahmeplan
-   Aufgabenplan

### <a name="business-case"></a>Geschäftsszenario

Geschäftsanwendungsfälle, Projektbeteiligte, wesentliche Ergebnisse und wichtige Erfolgsindikatoren, Risiken und Projektzeitschienen bilden normalerweise die für ein Geschäftsszenario erforderlichen Informationen. Sie müssen sie als Teil des Erfolgsplans dokumentieren.

### <a name="service-readiness"></a>Bereitschaft für den Dienst

Die Bewertung der Umgebung liefert erste Informationen, die zur Einschätzung der technischen Bereitschaft für die Implementierung des Telefonsystems mit Anrufplänen erforderlich sind.

Enthalten hier ist der Plan zur Adressierung der Bereiche, für die aufgrund der Auswertung der Umgebung Verbesserungsmaßnahmen durchgeführt werden müssen. Sie müssen die Auswertung der Dienstbereitschaft und den Wartungsplan als Teil des Erfolgsplans einbeziehen.

### <a name="adoption-plan"></a>Übernahmeplan

Nach der Auswertung der Übernahmebereitschaft muss das Projektteam eine weitere detaillierte Planung vornehmen. Hierzu zählen umfassende Kommunikationspläne, ein Schulungsplan sowie Übernahmeaktivitäten vor, während und nach der Einführung des Diensts.

Ressourcen zur Unterstützung der Übernahmeaktivitäten wie Flyer, Willkommmens-E-Mails und Schulungsmaterialien sowie alle für die Anforderungen der Organisation notwendigen Anpassungen zählen zu diesem Schritt.

Die Vorlagen für Übernahmeaktivitäten sind [hier](https://www.microsoft.com/download/details.aspx?id=54244) verfügbar.

### <a name="operational-plan"></a>Aufgabenplan

Bei der Zuordnung von operativen Rollen werden Rollen und Verantwortlichkeiten sowie die jeder operativen Rolle zugewiesenen Teams definiert, um die Implementierung des Telefonsystems mit Anrufplänen zu unterstützen.

Sie müssen diesen Schritt abschließen und den operativen Plan als Teil des Erfolgsplans berücksichtigen, um die operative Bereitschaft der Lösung sicherzustellen.

<br>
Technische Planung für das Telefonsystem mit Anrufplänen
------------------------------------------------------

Um die technische Implementierung des Telefonsystems mit Anrufplänen zu planen, müssen Sie frühzeitig eine Reihe von Entscheidungen treffen. Damit bereiten Sie Ihre Organisation besser auf die Implementierung einer Lösung vor, die die Geschäftsanforderungen erfüllt. Diese Entscheidungen werden in einem Plan zur technischen Implementierung dokumentiert.

## <a name="availability-of-calling-plans"></a>Verfügbarkeit von Anrufplänen

Unter [Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](https://docs.microsoft.com/en-uscountry-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) erfahren Sie, wo der Anrufplandienst verfügbar ist.

> [!IMPORTANT]
> Aufgrund von rechtlichen Beschränkungen müssen multinationale Organisationen, die Anrufpläne nutzen möchten, den Vertrag für Office 365-Abonnements in Ländern und Regionen abschließen, die vom Anrufplandienst abgedeckt sind oder in denen dieser kommerziell erhältlich ist.

Nachdem Sie sich vergewissert haben, dass Ihre Organisation berechtigt ist, das Add-On „Anrufpläne“ zu beziehen, erstellen Sie die Liste der Benutzerstandorte oder Niederlassungen, an bzw. in denen der Anrufplandienst implementiert wird. Die Grundlage stellt dabei die Liste der verfügbaren Länder und Regionen dar.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, an welchen Benutzerstandorten oder in welchen Niederlassungen der Anrufplandienst implementiert werden soll.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzerstandorte oder Niederlassungen, die für den Anrufplandienst aktiviert werden sollen.</li></ul>|

> [!TIP]
> Das folgende Beispiel zeigt eine Vorlage für eine Aktivierungsliste für Standorte mit dem Telefonsystem mit Anrufplänen:
>|Niederlassung   |Standort |Telefonsystemdienst  |
>|---------|---------|---------|
>|One Epping Road|Australien|Legacy-PSTN-Dienst|
>|100 Cyberport Road|Hong Kong SAR (香港特別行政區)|Legacy-PSTN-Dienst|
>|One Marina Boulevard|Singapur|Legacy-PSTN-Dienst|
>|32 London Bridge Street|Vereinigtes Königreich|Telefonsystem mit Anrufplänen|
>|39 quai du Président Roosevelt|Frankreich|Telefonsystem mit Anrufplänen|

## <a name="licensing-for-calling-plans"></a>Lizenzierung für Anrufpläne

Da es sich bei Anrufplänen um ein Add-On für die Telefonsystemfunktion in Office 365 handelt, benötigen Sie für die Verwendung von Anrufplänen eine aktivierte Telefonsystemlizenz.

Die [Telefonsystemlizenz](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) ist im Rahmen der Office 365 E5-Abonnementpläne oder als Add-On für Office 365 E1- oder Office 365 E3-Abonnementpläne verfügbar.
Es gibt zwei Arten von [Anrufplanlizenzen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365):

-   Anrufplan für Inland
-   Anrufplan für Ausland und Inland

> [!NOTE]
> Was für einen bestimmten Benutzer als „Inland“ gilt, wird durch den zugewiesenen Office 365-Verwendungsstandort des Benutzers bestimmt.

Jeder Anrufplantyp umfasst ein zugewiesenes Minutenkontingent, das die Benutzer pro Monat für Inlands- oder Auslandsanrufe nutzen können. Der Anrufplan für Inland kostet weniger als der Anrufplan für Ausland und Inland. Wenn Sie wissen möchten, wie viele Minuten für die einzelnen Länder bzw. Regionen verfügbar sind, lesen Sie unter [Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](https://docs.microsoft.com/en-uscountry-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) den Abschnitt „Anrufpläne“.

In der Regel müssen nicht alle Mitarbeiter einer Organisation Auslandsanrufe tätigen können. Da Sie in Ihrer Organisation flexibel den am besten geeigneten Anrufplantyp für die geschäftlichen Anforderungen einzelner Benutzer abonnieren und zuweisen können, behalten Sie die Kontrolle über die Kosten der Implementierung von Anrufplänen.

Alle Minutenkontingente der einzelnen Office 365-Mandanten werden in Pools für Länder bzw. Regionen und Anrufplantypen zusammengefasst. Wenn die Obergrenze des monatlichen Minutenkontingents für den Mandanten erreicht ist, wird der Anrufplandienst (mit Ausnahme von Notrufen) für den Rest des Monats ausgesetzt. Am ersten Tag des nächsten Kalendermonats wird der Anrufplandienst automatisch wieder fortgesetzt.

Sie können Guthaben für Kommunikationen für Ihre Organisation einrichten, damit Benutzer auch dann ausgehende Anrufe tätigen können, wenn das Minutenkontingent aufgebraucht ist. Sie müssen dann nicht bis zum nächsten monatlichen Abrechnungszyklus warten. Außerdem erhalten Benutzer, denen ein Anrufplan für Inland zugewiesen ist, mit [Guthaben für Kommunikationen](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) die Möglichkeit, Auslandsanrufe mit Minutenabrechnung zu tätigen.

Bei der Implementierung von Kommunikationsguthaben müssen Sie zunächst überlegen, wie hoch der anfängliche Betrag für das Guthaben sein soll. Die empfohlenen Einzahlungsbeträge können Sie dem Artikel [Was ist Guthaben für Kommunikationen?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) entnehmen.

Wenn sich Ihre Organisation für automatisches Aufladen entscheidet, finden Sie im Artikel [Was ist Guthaben für Kommunikationen?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) außerdem eine Empfehlung für den niedrigsten Betrag, der das automatische Aufladen auslöst. Der Betrag für die automatische Auffüllung richtet sich nach der tatsächlichen Verwendung. Die Verwendung von Guthaben für Kommunikationen sollte immer überwacht werden, und der Aufladebetrag muss nach Bedarf angepasst werden.

Sie können die Verwendung von Guthaben für Kommunikationen pro Benutzer steuern. Auf diese Weise können Sie sicherstellen, dass diese Möglichkeit den Personen in der Organisation zugewiesen ist, bei denen dies geschäftlich begründet ist.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Wenn Ihre Organisation noch nicht über die erforderliche Telefonsystemlizenz verfügt, entscheiden Sie, ob Sie diese Lizenz durch die Erweiterung vorhandener Office 365-Abonnements oder durch den Kauf von Telefonsystem-Add-Ons erwerben möchten.</li><li>Entscheiden Sie, welche Benutzer eine Lizenz für einen Anrufplan für Inland benötigen und welche Benutzer eine Lizenz für einen Anrufplan für Inland und Ausland benötigen.</li><li>Entscheiden Sie, ob Guthaben für Kommunikationen für die Implementierung von Anrufplänen erforderlich sind. Wenn ja, legen Sie den anfänglichen Auffüllungsbetrag fest. Legen Sie gegebenenfalls den niedrigsten Betrag fest, bei dem das automatische Aufladen ausgelöst wird.</li><li>Entscheiden Sie, welche Benutzer eine Lizenz für Guthaben für Kommunikationen benötigen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie, welchen Benutzern eine Telefonsystemlizenz zusammen mit einer Lizenz für Anrufplan für Inland zugewiesen werden soll und welchen Benutzern eine Telefonsystemlizenz sowie eine Lizenz für einen Anrufplan für Inland und Ausland zugewiesen werden soll.</li><li>Dokumentieren Sie den Plan für Guthaben für Kommunikationen (anfänglicher Betrag und Auslösebetrag für automatisches Aufladen, Höhe des Betrags für automatisches Aufladen).</li><li>Dokumentieren Sie, welche Benutzer für die Lizenz für Guthaben für Kommunikationen aktiviert werden sollen.</li></ul>|

> [!TIP]
> Sie können die Lizenzzuweisungsliste für Benutzer des Telefonsystems mit Anrufplänen anhand des folgenden Beispiels dokumentieren:
>|Benutzer  |Niederlassung  |Office 365-Lizenz  |Guthaben für Kommunikationen  |
>|---------|---------|---------|---------|
>|Emily Braun|32 London Bridge Street|Office 365 E5, Anrufplan für Ausland und Inland|Aktiviert|
>|Lidia Holloway|32 London Bridge Street|Office 365 E5, Anrufplan für Inland|Deaktiviert|
>|Pradeep Gupta|32 London Bridge Street|Office 365 E5, Anrufplan für Inland|Aktiviert|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, Telefonsystem-Add-On, Anrufplan für Inland|Deaktiviert|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5, Anrufplan für Ausland und Inland|Aktiviert|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, Telefonsystem-Add-On, Anrufplan für Inland|Deaktiviert|

<br>
> [!TIP]
> Sie können Ihre Zahlen für die Planung des Guthabens für Kommunikationen so dokumentieren:
>|         |         |
>|---------|---------|
>|Anfangsbetrag|1.000 US-Dollar|
>|Betrag für die Auslösung der Auffüllung|400 US-Dollar|
>|Höhe des Betrags für die automatische Auffüllung|TBA|

## <a name="phone-numbers-and-emergency-locations"></a>Telefonnummern und Notfallstandorte

Für Anrufpläne in Office 365 benötigt jeder Benutzer in der Organisation eine eindeutige Direktwahlnummer und eine entsprechende [validierte Notfalladresse](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).

Telefonnummern können [direkt von Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) bezogen werden. Alternativ können Sie auch vorhandene Telefonnummern [zu Microsoft übertragen (portieren)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).

> [!NOTE]
> Die Komplexität der Portierung von Telefonnummern nach Microsoft richtet sich sehr stark nach den jeweiligen Ländern oder Regionen, Netzbetreibern, der Anzahl der beteiligten Verbindungen und vielen anderen Faktoren. Informationen zur Portierung von Telefonnummern finden Sie im [Handbuch für Nummernportierung](https://go.microsoft.com/fwlink/?linkid=859011).

Wenn Sie Telefonnummern direkt von Microsoft beziehen möchten, haben Sie die folgenden Möglichkeiten:

- [Skype for Business Admin Center](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)
- [Cmdlets für Remote-Windows PowerShell](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
- [Absenden eines Formulars neue Telefon anfordern](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

Das Anforderungsformular für neue Telefonnummern eignet sich am besten, wenn Sie den Erwerb von Telefonnummern planen, da Sie einen zusammenhängenden Nummernblock anfordern können. Es ist nicht in allen Ländern bzw. Regionen möglich, Telefonnummern über das Skype for Business Admin Center oder über Remote-Windows PowerShell zu beziehen.

Die ersten beiden Methoden – Verwendung von Skype for Business Admin Center oder Remote-Windows PowerShell – eignen sich für den einmaligen, sofortigen Erwerb von Telefonnummern und in Fällen, in denen keine zusammenhängenden Nummernblöcke benötigt werden.

> [!NOTE]
> Die [Anzahl der Telefonnummern](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get), die von Microsoft bezogen werden können, ist begrenzt und basiert auf der Anzahl der Anrufplanlizenzen, die Ihre Organisation abonniert hat. Für Telefonnummern für Benutzer (Teilnehmer) gilt die Formel (Anzahl der Lizenzen für Anrufplan für Inland + Anzahl der Lizenzen für Anrufplan für Inland und Ausland) x 1,1 + 10. Wenn Sie beispielsweise 50 Benutzer mit Anrufplanlizenzen haben, können Sie 65 Telefonnummern beziehen ((50 x 1,1) + 10).

Wenn Sie Telefonnummern für Anrufpläne konfigurieren, muss jeder Telefonnummer eine Notfalladresse zugewiesen werden. Dies muss vor der Zuweisung der Telefonnummer zu einem Benutzer geschehen. Dieser Schritt ist für die Unterstützung von Notrufen erforderlich. Die Notfalladresse muss validiert werden, um sicherzustellen, dass sie erkannt wird und im richtigen Format vorliegt, das von Notdiensten verwendet werden kann.

> [!IMPORTANT]
> Anrufe bei Notdiensten funktionieren mit dem Anrufplandienst anders als mit herkömmlichen Telefondiensten. Es ist wichtig, dass Sie diese Unterschiede verstehen und sie allen Benutzern vermitteln. Weitere Details finden Sie unter [Nutzungsbedingungen für Notrufe](https://docs.microsoft.com/SkypeForBusiness/legal-and-regulatory/emergency-calling-terms-and-conditions).

Zusätzlich zu einer validierten Notfalladresse können Notfallstandorte festgelegt und mit einer validierten Notfalladresse verknüpft werden, um den genauen Standort an einer Adresse anzugeben. Ein Notfallstandort ist meist die Gebäudenummer, das Stockwerk, der Gebäudeflügel oder die Nummer des Zimmers, in dem sich der Benutzer befindet.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, wie die Telefonnummern für die jeweiligen Benutzerstandorte oder Niederlassungen für die Implementierung von Anrufplänen bezogen werden sollen (über Microsoft oder durch Übertragung vorhandener Telefonnummern).</li><li>Wenn Sie sich für Microsoft entscheiden, wählen Sie die Methode zum Beziehen von Telefonnummern (durch Formularübermittlung oder automatisch) für die jeweiligen Benutzerstandorte oder Niederlassungen für die Implementierung von Anrufplänen aus.</li><li>Legen Sie fest, wie detailliert die erfassten Informationen zu den Notfallstandorten für die Benutzerstandorte oder Niederlassungen für die Implementierung von Anrufplänen sein sollen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie den Masterplan für den Erwerb von Telefonnummern mit Details dazu, wie die Telefonnummern an jedem einzelnen Benutzerstandort oder in jeder einzelnen Niederlassung für die Implementierung von Anrufplänen bezogen werden.</li><li>Falls anwendbar, füllen Sie für jeden Standort oder jede Niederlassung das Formular <a href="https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization">für die Anforderung neuer Telefonnummern</a> aus.</li><li>Wenn Sie vorhandene Telefonnummern übertragen möchten, können Sie diesen Vorgang mit Unterstützung des <a href="https://go.microsoft.com/fwlink/?linkid=859011">Handbuchs für die Nummernportierung</a> planen und die zeitgerechte Implementierung von Anrufplänen entsprechend anpassen.</li><li>Dokumentieren Sie die detaillierte Notfalladresse und die Notfallstandorte für die einzelnen Benutzerstandorte oder Niederlassungen für die Implementierung von Anrufplänen.</li></ul>

> [!TIP]
> Die Details für den Erwerb der Telefonnummern, die Telefonnummern und die Details für die Notfallstandorte können Sie mithilfe der folgenden Vorlage dokumentieren:
>|Benutzer  |Notfallstandort und -adresse  |Zu erwerbende Telefonnummer  |Telefonnummer  |
>|---------|---------|---------|---------|
>|Emily Braun|1034/32 London Bridge Street, London, SE1, Vereinigtes Königreich|Vorhandene Telefonnummer portieren|+44 20 7946 0034|
>|Lidia Holloway|1023/32 London Bridge Street, London, SE1, Vereinigtes Königreich|Vorhandene Telefonnummer portieren|+44 20 7946 0065|
>|Pradeep Gupta|1023/32 London Bridge Street, London, SE1, Vereinigtes Königreich|Vorhandene Telefonnummer portieren|+44 20 7946 0023|
>|Marcel Beauchamp|07E15D/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Frankreich|Neue Telefonnummer erwerben|TBA|
>|Rachelle Cormier|07E15D/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Frankreich|Neue Telefonnummer erwerben|TBA|
>|Isabell Potvin|07E15D/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Frankreich|Neue Telefonnummer erwerben|TBA|

## <a name="voicemail"></a>Voicemail

Voicemail für Telefonsysteme, unterstützt von Azure Voicemail Services, unterstützt die Ablage von Voicemail nur in Exchange-Postfächern. E-Mail-Systeme von Drittanbietern werden nicht unterstützt.

Voicemail für Telefonsysteme funktioniert standardmäßig mit Exchange Online. Dabei gelten jedoch Mindestanforderungen für die [unterstützte lokale Exchange-Version und das unterstützte Bereitstellungsmodell](https://support.microsoft.com/help/3195158/customer-issues-between-exum-and-azure-voicemail) für die Zustellung von Voicemailnachrichten an Benutzerpostfächer in der lokalen Exchange-Bereitstellung.

Voicemail für Telefonsysteme bietet Voicemailtranskription. Diese Funktion ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert. Möglicherweise muss Ihr Unternehmen in manchen Fällen die Voicemailtranskription für bestimmte Benutzer oder in der gesamten Organisation deaktivieren.

> [!NOTE]
> Als Ausweichmechanismus kann Voicemail für Telefonsysteme Nachrichten über SMTP erneut senden. Das bedeutet, dass Benutzer mit einem Postfach in einem E-Mail-System eines Drittanbieters ihre Voicemailnachrichten erhalten. Dabei gibt es weder eine garantierte Dienstbetriebszeit noch andere Voicemailfunktionen wie beispielsweise Ändern der Ansage und anderer Einstellungen.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Voicemail für Telefonsysteme für die Implementierung von Anrufplänen aktiviert werden soll.</li><li>Wenn Sie Exchange lokal verwenden und die vorhandene Bereitstellung nicht den Anforderungen für die Unterstützung von Voicemail für Telefonsysteme entspricht, treffen Sie eine Entscheidung über die verfügbaren Optionen (Upgrade und Setup für die Unterstützung von Voicemail für Telefonsysteme oder Migration zu Exchange Online, Nutzen des Ausweichmechanismus).</li><li>Entscheiden Sie, ob Voicemailtranskription in der gesamten Organisation oder für bestimmte Benutzer aktiviert bzw. deaktiviert sein soll.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie gegebenenfalls die Entscheidungspunkte bezüglich Exchange und der Unterstützung von Voicemail für Telefonsysteme.</li><li>Wenn Voicemail und Voicemailtranskription nicht für alle Benutzer aktiviert werden sollen, dokumentieren Sie, für welche Benutzer diese Funktionen aktiviert werden sollen.</li></ul>|

> [!TIP]
> Sie können die Details für Voicemail für Telefonsysteme für die Implementierung des Telefonsystems mit Anrufplänen wie folgt dokumentieren:
>|Benutzer  |Exchange-Postfach  |Voicemail aktivieren  |Voicemailtranskription  |
>|---------|---------|---------|---------|
>|Emily Braun|Online|Ja|Aktiviert|
>|Lidia Holloway|Online|Ja|Aktiviert|
>|Pradeep Gupta|Lokal|Ja|Aktiviert|
>|Marcel Beauchamp|Lokal|Ja|Deaktiviert|
>|Rachelle Cormier|Online|Ja|Deaktiviert|
>|Isabell Potvin|Lokal|Ja|Deaktiviert|

## <a name="calling-identity"></a>Anrufer-ID

Standardmäßig wird bei allen ausgehenden Anrufen die zugewiesene Telefonnummer als Anrufer-ID verwendet. Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte. In manchen Fällen muss die Anrufer-ID aus legitimen geschäftlichen Gründen maskiert werden, um die Identität der Anrufer zu schützen. Dazu wird entweder die Haupttelefonnummer der Niederlassung – in der Regel eine von der [automatischen Telefonzentrale](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants) betreute Servicenummer – als Anrufer-ID verwendet, oder die Anzeige der Anrufer-ID wird vollständig blockiert.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob die Änderung der Anrufer-ID für die Implementierung von Anrufplänen erforderlich ist.</li><li>Legen Sie gegebenenfalls fest, welche Arten der Änderung der Anrufer-ID (mit Servicenummer maskieren oder anonymisieren) implementiert werden sollen.</li><li>Legen Sie gegebenenfalls fest, für welche Benutzer die Änderung der Anrufer-ID erforderlich ist und welche Art der Änderung der Anrufer-ID den einzelnen Benutzern zugewiesen werden soll.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer, denen die Änderung der Anrufer-ID zugewiesen werden soll, und welche Art der Änderung der Anrufer-ID für die einzelnen Benutzer gelten soll.</li></ul>|

> [!TIP]
> Hier ist ein Beispiel für eine Vorlage zum Dokumentieren der Maskierungsdetails für die Anrufer-ID:
>|Benutzer  |Maskierung für ausgehende Anrufer-IDs aktivieren  |Art der Anrufer-ID-Maskierung  |Außerkraftsetzung durch Benutzer zulassen  | Maskierung für eingehende Anrufer-IDs aktivieren  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|Nein|n/v|Ja|Nein|
>|Lidia Holloway|Ja|Servicenummer (OrgAA, +44 20 7946 0000)|Nein|Ja|
>|Pradeep Gupta|Nein|n/v|Ja|Nein|
>|Marcel Beauchamp|Ja|Servicenummer (OrgAA, TBA)|Nein|Ja|
>|Rachelle Cormier|Ja|Anonymisieren|Ja|Nein|
>|Isabell Potvin|Ja|Servicenummer (OrgAA, TBA)|Nein|Ja|

## <a name="dial-plans"></a>Wählpläne

Bei einem [Wählplan](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) in der Telefonsystemfunktion von Office 365 handelt es sich um eine Gruppe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise das Format [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) übersetzt, um Anrufe zu autorisieren und weiterzuleiten. 

Mit einem Wählplan können Benutzer Telefonnummern so wählen, wie sie es gewöhnt sind. Zum Beispiel müssen sie bei Ortsgesprächen keine Ortsvorwahl wählen, bei Inlandsanrufen keine Landeskennzahl wählen, und sie können sogar Kurzwahlnummern für ausgehende Anrufe verwenden.

Innerhalb der Telefonsystemfunktion in Office 36 gibt es zwei Arten von Wählplänen:

-   **Dienstwählplan**. Dies ist der Standardwählplan, der auf einem Office 365-Verwendungsstandort basiert und nicht geändert werden kann.
-   **Mandantenwählplan**. Dies ist ein anpassbarer Wählplan innerhalb eines Mandanten, der wiederum zwei Typen umfasst:
    -   **Globaler Wählplan für Mandanten**: Der Wählplan gilt für alle Benutzer innerhalb des Mandanten.
    -   **Wählplan für Mandantenbenutzer**: Der Wählplan gilt nur für bestimmte Benutzer.

> [!NOTE]
> Weitere Details und Beispiele finden Sie unter [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).

Der den Benutzern zugewiesene wirksame Wählplan stellt eine Kombination aus dem Dienstwählplan (basierend auf dem Office 365-Verwendungsstandort des Benutzers) und dem Mandantenwählplan (entweder globaler Wählplan für Mandanten oder Wählplan für Mandantenbenutzer) dar.

![Die Tabelle zeigt drei Kombinationen aus Dienst- und Mandantenwählplänen.](media/audio_conferencing_image8.png)

Normalisierungsregeln können maximal 25 Regeln in jedem Mandantenwählplan enthalten. Eine Duplizierung von bereits als Teil des Dienstwählplans vorhandenen Normalisierungsregeln sollte daher vermieden werden.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Ihre Organisation angepasste Wählpläne benötigt (Geschäftsanforderungen, Einführungsanforderungen usw.).</li><li>Legen Sie gegebenenfalls den Gültigkeitsbereich für den Mandantenwählplan (globaler Mandantenwählplan oder Wählplan für Mandantenbenutzer) fest, um die Anforderungen für angepasste Wählpläne zu erfüllen.</li><li>Legen Sie gegebenenfalls die Mandantenwählpläne fest, die zur Unterstützung von Benutzerstandorten oder Niederlassungen für die Implementierung von Anrufplänen erstellt werden.</li><li>Legen Sie gegebenenfalls fest, für welche Benutzer ein angepasster Wählplan benötigt wird und welcher Mandantenwählplan den einzelnen Benutzern zugewiesen wird.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die angepassten Wählpläne und die zugehörigen Normalisierungsregeln, die als Teil der Implementierung von Anrufplänen konfiguriert werden.</li><li>Dokumentieren Sie, welchen Benutzern ein angepasster Wählplan zugewiesen wird, und welcher Mandantenwählplan den einzelnen Benutzern zugewiesen wird.</li></ul>|

> [!TIP]
> Wenn die entsprechenden Punkte für Ihr Projekt zutreffen, können Sie die Konfigurationen der Mandantenwählpläne in der folgenden Vorlage dokumentieren:
>|Name des Mandantenwählplans<br>Beschreibung  |Name der Normalisierungsregeln<br>_Beschreibung_  |Muster<br>Übersetzung<br>IsInternalExtension  |
>|---------|---------|---------|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, Wählplan für Frankreich_|**FR-39qdPR-Internal**<br>_Interne Nummer (x7000 – x7999) für 39 quai du Président Roosevelt-Niederlassung, Issy-les-Moulineaux, Frankreich_|^(7\d{3})$<br>+3319999$1<br>Wahr|
>||**FR-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Frankreich_|^ 0?(80\d{7}) \d*$<br>+33$1<br>Falsch|
>||**FR-Service**<br>_Normalisierung für Servicenummern für Frankreich_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>Falsch|

<br>
> [!TIP]
> Sie können die folgende Beispielvorlage nutzen, um Wählplanzuweisungen für Ihr Projekt zu dokumentieren:
>|Benutzer  |Niederlassung  |Typ des Wählplans  |Name des Wählplans  |
>|---------|---------|---------|---------|
>|Emily Braun|32 London Bridge Street|Dienstwählplan|n/v|
>|Lidia Holloway|32 London Bridge Street|Dienstwählplan|n/v|
>|Pradeep Gupta|32 London Bridge Street|Dienstwählplan|n/v|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-39qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-39qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-39qdPR|

## <a name="document-technical-implementation-plan"></a>Dokumentieren des Plans für die technische Implementierung

Verwenden Sie die Entscheidungspunkte oben, um Ihren Plan zur technischen Implementierung zu dokumentieren.
Mit diesem Plan erhält das Projektteam (zu dem FastTrack oder ein Bereitstellungspartner gehören kann) die erforderlichen Informationen zur Ausführung des technischen Onboardings für die Implementierung des Telefonsystems mit Anrufplänen.

In der Regel enthält ein Plan zur technischen Implementierung die folgenden Hauptabschnitte:

-   Aktivierungsliste für Standorte mit dem Telefonsystem mit Anrufplänen

-   Lizenzzuweisungen für Benutzer des Telefonsystems mit Anrufplänen

-   Zahlen für die Planung des Kommunikationsguthabens

-   Erwerb von Telefonnummern, Details zu Telefonnummern und Notfallstandorten

-   Details der Voicemailkonfiguration

-   Details der Konfiguration der Anrufer-ID-Maskierung

-   Mandantenwählpläne

-   Wählplanzuweisungen

<br>
Nach Abschluss des Erfolgsplans und des Plans zur technischen Implementierung können Sie Ihrer Organisation jetzt die nächsten Schritte entlang des Office 365 Customer Journey unterbreiten.

<br>
Onboarding =======

*In Kürze verfügbar.*

<br>
Wertschöpfung

*In Kürze verfügbar.*

<br>
## <a name="see-also"></a>Siehe auch

[Einrichten von Anrufplänen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/configuring-teams-calling-quickstartguide)
