---
title: Praktische Anleitungen für Audiokonferenzen in Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
description: Praktische Anleitungen für die Planung, Bereitstellung und Verwaltung von Audiokonferenzen in Microsoft Teams mithilfe eines Frameworks, das die Phasen „Konzeptionierung“ (Planung), „Onboarding“ (Bereitstellung) und „Wertschöpfung“ (Einsatz) vorsieht
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
redirect_url: https://docs.microsoft.com/MicrosoftTeams/cloud-voice-deployment
ms.openlocfilehash: 516437ac9def60b1c06304429ca3bbe9eca63a3f
ms.sourcegitcommit: 0aa8b07480a68cd589bbb70a5a51c4e177758a80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "25593711"
---
<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a>Praktische Anleitungen für Audiokonferenzen in Microsoft Teams
============================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Mit der Funktion für Audiokonferenzen in Office 365 können Teilnehmer mit einem beliebigen Telefon an Ihren Microsoft Teams-Besprechungen teilnehmen.

Das bekommen Sie mit [Audiokonferenzen](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.

Diese praktischen Anleitungen führen Sie durch das Framework der Office 365 FastTrack Customer Journey und seine drei Phasen (Konzeptionierung, Onboarding und Wertschöpfung), damit Sie eine erfolgreiche Implementierung von Audiokonferenzen planen, bereitstellen und verwenden können, mit der Sie dann positive Geschäftsergebnisse erzielen.

> [!TIP]
> Sie erhalten hier Beispielergebnisse für die einzelnen Aktivitäten und die wichtigsten Diskussionspunkte. Die Beispiele in diesem Dokument, die Sie als wiederverwendbare Vorlagen nutzen können, finden Sie in den mit „Tipp“ beschrifteten Kästen. Der Hinweis „TBA“ (To Be Added, wird ergänzt) zeigt an, dass Sie hier Informationen als Teil Ihres Planungsprozesses eingeben müssen.

Ausblick <a name="Envision_AudioConferencing"> </a>
=========

Die Ausblick-Phase bietet die Grundlage für die Office 365 Customer Journey und kann auf alle Arbeitsauslastungen wie zum Beispiel Audiokonferenzen angewendet werden.

In dieser Phase formulieren die jeweiligen Projektbeteiligten die Geschäftsziele und stellen Folgendes bereit:

-   Einen umfassenden Erfolgsplan mit Geschäftsanwendungsfällen, wichtigen Beteiligten, Zielen und wesentlichen Ergebnissen, wichtigen Erfolgsindikatoren, Risiken, einer Bewertung der Umgebung, Einführungsbereitschaft und Einsatzplanung

-  Einen detaillierten Plan für die technische Implementierung von Audiokonferenzen, mit dem der gewünschte Endzustand erreicht werden soll

<a name="define-business-use-cases-for-audio-conferencing"></a>Definieren von Geschäftsanwendungsfällen für Audiokonferenzen
------------------------------------------------

Mit Audiokonferenzen erhalten Organisationen weitere Einstiegspunkte für Ad-hoc-Besprechungen und geplante Besprechungen. Sie können zulassen, dass Teilnehmer über das Telefonfestnetz (Public Switched Telephone Network, PSTN) an Besprechungen teilnehmen, indem sie sich mit herkömmlichen Festnetz-, Nebenstellen- oder Mobiltelefonen einwählen.

Dies ist hilfreich, wenn der Organisator oder die Teilnehmer nicht vor ihren Computern sitzen oder wenn die Datenverbindungen für VoIP-Kommunikation nicht verfügbar oder nicht zuverlässig sind – zum Beispiel an einem Remotestandort mit schlechter Netzabdeckung, bei Verbindungen über einen gebührenfreien, öffentlichen WLAN-Dienst mit eingeschränkter Bandbreite oder, wenn es Besprechungsteilnehmer bevorzugen, sich über einen ihnen zur Verfügung stehenden Telefonie-Endgeräten einwählen.

In diesem Schritt definieren die wichtigsten Projektbeteiligten Geschäftsanwendungsfälle, die die Implementierung von Audiokonferenzen unterstützen.

Mit Geschäftsanwendungsfällen werden die erwarteten und messbaren Geschäftsergebnisse definiert und dokumentiert. Dazu zählen:

-   Beschreibung des aktuellen Geschäftsprozesses
-   Herausforderungen bei den vorhandenen definierten Geschäftsprozessen
-   Wie diese Herausforderungen mithilfe der Technologie bewältigt werden können
-   Die erwarteten und messbaren Geschäftsergebnisse, die durch die Bewältigung dieser Herausforderungen erzielt werden können

> [!TIP]
> Das folgende Beispiel zeigt einen abgeschlossenen Geschäftsanwendungsfall:
> 
> |         |
> |---------|
> |**Beschreibung des aktuellen Geschäftsprozesses**<br>Für interne Besprechungen und Besprechungen mit Dritten nutzt Contoso derzeit die von etablierten lokalen Telefonanbietern bereitgestellten PSTN-Konferenzdienste, die im Minutentakt abgerechnet werden.|
> |**Herausforderungen mit vorhandenen Geschäftsprozessen**<br>Contoso investiert jährlich rund 1 Million US-Dollar für den aktuellen PSTN-Konferenzdienst, wobei 75 % der Kosten auf interne Besprechungen zurückzuführen sind.<br>Die Verwendung von herkömmlichen Telefonie-Endpunkten für die Teilnahme an durch den PSTN-Konferenzdienst gehosteten Besprechungen ist nicht an das Konzept für die Organisation zur Übernahme von Teams als moderne Plattform für Kommunikation und Zusammenarbeit angepasst.|
> |**Wie diesen Herausforderungen am besten begegnet werden kann**<br>Mit der Übernahme von Microsoft Teams als Plattform für Kommunikation und Zusammenarbeit wird von internen Benutzern erwartet, dass sie primär mit ihren PCs (mit optimierten Headsets und Geräten für Besprechungsräume) an Besprechungen teilnehmen. Der Audiokonferenzdienst dient der Unterstützung von externen Teilnehmern oder der Unterstützung von Situationen, in denen die Verwendung der PC-Audiofunktionen für die internen Teilnehmer nicht vorteilhaft ist.|
> |**Erwartete, messbare Geschäftsergebnisse**<br>Mit dem Wechsel zu Teams als moderne Plattform für Kommunikation und Zusammenarbeit in Kombination mit dem Audiokonferenzdienst werden die Kosten der Bereitstellung des PSTN-Konferenzdiensts erheblich reduziert. Die Einsparungen gehen sogar so weit, dass Contoso lediglich 20 % der jährlichen Kosten im Vergleich zum herkömmlichen PSTN-Konferenzdienst aufwenden muss.|

Im nächsten Schritt der Konzeptionierungsphase sollten Sie nicht nur die Geschäftsanwendungsfälle definieren, sondern sich auch in den folgenden Punkten Klarheit verschaffen:
- Organisatorischer Geltungsbereich
- Projektzeitplan

<a name="identify-key-stakeholders"></a>Identifizieren der wichtigsten Projektbeteiligten
-------------------------

Die im vorherigen Schritte definierten Geschäftsanwendungsfälle enthalten die Implementierung von Audiokonferenzen als organisatorischen Geltungsbereich, und basierend darauf kann eine umfassende Liste mit Projektbeteiligten erstellt werden, um die richtigen Personen in das Projekt einzubeziehen.

> [!TIP]
> In der folgenden Beispielvorlage für diese Matrix können Sie die Projektbeteiligten dokumentieren.
> 
> |                 Rolle                  |                                                                                                                                                                                                                                                                Beschreibung                                                                                                                                                                                                                                                                 | Name, Kontaktinformationen, Standort |
> |---------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|
> |       Leitender Projektsponsor       | <ul><li>Hat höchste Entscheidungsbefugnis und Rechenschaftspflicht für das Projekt und die Bereitstellung von Projektzielen</li><li>Bietet Unterstützung bei der Lösung der vom Projektleiter eskalierten Probleme</li><li>Bietet Unterstützung bei die Kommunikation innerhalb des Unternehmens</li><li>Ist für wichtige strategische Entscheidungen verantwortlich</li><li>Trägt Verantwortung für die Verfügbarkeit der erforderlichen Ressourcen und das benötigte Budget</li><li>Verfasst vierteljährliche Geschäftsberichte</li><li>Organisiert und unterstützt Sensibilisierungskampagnen</li><li>Ist Projektsponsor für das Programm-Rollout</li></ul> |                 TBA                 |
> |             Projektleiter              |                   <ul><li>Führt und leitet das Projektteam</li><li>Koordiniert die am Projekt beteiligten Partner und Arbeitsteams</li><li>Ist für das Erstellen und Verwalten von Projektplänen verantwortlich, um die wesentlichen Quartalsergebnisse zu erzielen</li><li>Behebt funktionsübergreifende Probleme</li><li>Erstellt einen regelmäßigen Rechenschaftsbericht für die Projektsponsoren</li><li>Bezieht Übernahmeaspekte in den fertigen Projektplan ein</li><li>Verfasst monatliche Geschäftsberichte als Grundlage für vierteljährliche Geschäftsberichte</li></ul>                   |                 TBA                 |
> |     Leiter/Architekt für Zusammenarbeit      |                                                                       <ul><li>Ist für die Ausführung der Zusammenarbeitsstrategie verantwortlich, die von den Führungskräften des Unternehmens definiert wird</li><li>Analysiert und wählt Produkte für die Zusammenarbeit für das Unternehmen aus, das die Geschäftsziele erreicht</li><li>Ist für die operationale Architektur von Produkten für die Zusammenarbeit verantwortlich</li><li>Definiert operative und Support-Modelle</li><li>Liefert Beiträge für die monatlichen und vierteljährlichen Geschäftsberichte</li><ul>                                                                        |                 TBA                 |
> |              Berater               |                                                                                                                                                                                                               <ul><li>Ist für Konfigurationsdienste verantwortlich</li><li>Liefert Beiträge zur Architektur der Gesamtlösung</li></ul>                                                                                                                                                                                                                |                 TBA                 |
> |            Projektmanager            |                                                      <ul><li>Entwickelt und verwaltet den Projektplan</li><li>Verwaltet die Projektergebnisse in Bezug auf die Einhaltung des Projektplans und des Budgets</li><li>Zeichnet Projektprobleme (zum Beispiel Eskalationen) auf und verwaltet diese</li><li>Tätigt wöchentliche Teamanrufe</li><li>Kontaktiert die leitenden Projektsponsoren und stellt aktuelle Informationen bereit</li><li>Arbeitet mit dem Architekten zusammen, um den Change Management-Ansatz und die Kommunikationspläne zu definieren</li></ul>                                                       |                 TBA                 |
> | Spezialist für Change Management/Einführung |                                                                                       <ul><li>Liefert Beiträge zu Übernahme- und Schulungsprozessen in der Entdeckungsphase</li><li>Nimmt am Workshop für Übernahmestrategie teil</li><li>Entwickelt die Übernahmestrategie und ist für diese verantwortlich</li><li>Entwickelt Kommunikationspläne und führt diese aus</li><li>Ist verantwortlich für die Bereitstellung von Schulungen für Endbenutzer</li><li>Sammelt Feedback und führt Umfragen durch</li></ul>                                                                                        |                 TBA                 |
> |             Netzwerkleiter              |                                                                                                                                                              <ul><li>Liefert Beiträge zum Netzwerkdesign in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Koordiniert die Arbeit des Netzwerkteams während der Projektausführung</li></ul>                                                                                                                                                               |                 TBA                 |
> |             Leiter der Sicherheit             |                                                                                                                                                        <ul><li>Liefert Beiträge zu Übernahme- und Schulungsprozessen in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Koordiniert die Arbeit des Sicherheitsteams während der Projektausführung</li></ul>                                                                                                                                                        |                 TBA                 |
> |            Telefonieleiter             |                                                                                                                                                              <ul><li>Liefert Beiträge zum Telefonie-Design in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Koordiniert die Arbeit des Telefonie-Teams während der Projektausführung</li></ul>                                                                                                                                                              |                 TBA                 |
> |             Desktopleiter              |                                                                                                                                                          <ul><li>Liefert Beiträge zu Client- und Updateprozessen in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Koordiniert die Arbeit des Desktop-Teams während der Projektausführung</li></ul>                                                                                                                                                          |                 TBA                 |
> |        Support-/Helpdeskleiter         |                                                                                                                          <ul><li>Liefert Beiträge zum operativen Modell und zum Support-Modell in der Entdeckungsphase</li><li>Nimmt an der Planung während des Ausblick-Workshops teil</li><li>Nimmt an der Planung des Support-Modells teil</li><li>Koordiniert die Arbeit des Support-Teams/der Ressourcen während der Projektausführung</li></ul>                                                                                                                          |                 TBA                 |
> |     Vertreter der Betriebseinheiten     |                                                                                                                                                                                                      <ul><li>Liefern Beiträge zur Endbenutzer-basierten Übernahme von Anleitungen und Begleitmaterialien</li><li>Tragen zu Geschäftsanwendungsfällen bei und überprüfen diese</li></ul>                                                                                                                                                                                                      |                 TBA                 |
> |            Bereitstellungsleiter            |                                                                                                                                                           <ul><li>Stellt sicher, dass die Systemvoraussetzungen erfüllt sind</li><li>Leitet Kundenressourcen an, sich an der Vorbereitung und Bereitstellung von Aktivitäten in den einzelnen Phasen zu beteiligen</li><li>Nimmt an Besprechungen zur Überprüfung des Vorbereitungs- und Bereitstellungsstatus teil</li></ul>                                                                                                                                                            |                 TBA                 |
> |               IT-Administratoren               |                                                                                                                                                                                                                           <ul><li>IT-Experten, die für die Unterstützung in der Testplanung und -ausführung verantwortlich sind</li></ul>                                                                                                                                                                                                                            |                 TBA                 |
> |             Leiter des Kundendiensts             |                                                                                                                                                                                                  <ul><li>Ist für den reibungslosen Ablauf des Audiokonferenzdiensts verantwortlich</li><li>Leiter des Audiokonferenzdiensts</li></ul>                                                                                                                                                                                                   |                 TBA                 |
> |           Qualitätspioniere           |                                                                                                      <ul><li>Trägt zur Verbesserung der Qualität, Verlässlichkeit und des Benutzerfeedbacks bei</li><li>Ermittelt Qualitätstrends und schafft Abhilfe bei Problemen mit den jeweiligen Teams</li><li>Ist verantwortlich für die Berichterstattung zwischen dem Lenkungsteam und dem Führungsstab</li><li>Erstellt Berichte über Qualität, Verlässlichkeit und Verbraucherstimmung über „Meinen Anruf bewerten“ und „Net Promoter Score“</li></ul>                                                                                                       |                 TBA                 |

<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Definieren von Zielen und wesentlichen Ergebnissen, wichtigen Erfolgsindikatoren und Risiken
--------------------------------------------------------------------

Bei der Zusammenkunft der Projektbeteiligten können Geschäftsanwendungsfälle, organisatorische Geltungsbereiche und Projektzeitschienen in Ziele und wesentliche Ergebnisse übersetzt werden, und die Kennzahlen des Projekterfolgs können in einer Liste mit den wichtigen Erfolgsindikatoren festgelegt werden.

Durch die Teilnahme aller Projektbeteiligten bei der Festlegung der Ziele und wesentlichen Ergebnissen sowie der wichtigen Erfolgsindikatoren wird das Verantwortungsbewusstsein geschärft, und eine Anpassung an die organisatorischen Geschäftsanforderungen wird sichergestellt.

Ziele und wesentliche Ergebnisse enthalten die Liste der Ziele, die zu Projektbeginn festgelegt wurden. Sie enthalten unter anderem messbare Ergebnisse auf Quartalsbasis. Diese Kernergebnisse werden monatlich ausgewertet, um den Status des gesamten Projekts zu verfolgen. Des Weiteren kann basierend auf dem Fortschritt eine Anpassung der Quartalspläne nach Bedarf vorgenommen werden.

> [!TIP]
> Das folgende Beispiel enthält Ziele und wesentliche Ergebnisse, die für die Implementierung von Audiokonferenzen relevant sind:
> <br>
> 
> **Vision: Steigern der Produktivität durch Maximierung der Investition in Office 365**
> 
> |Ziele  |Wesentliche Ergebnisse  |Aufgabe  |
> |---------|---------|---------|
> |Bereitstellen von Audiokonferenzen in Teams gegen Ende des Geschäftsjahres 2018|1. Quartal des Geschäftsjahres 2018: Globale Bereitstellung von Audiokonferenzen in Teams|Ausblick<ul><li>Erfolgsplan erstellen</li><li>Detaillierten Plan für die technische Implementierung erstellen</li></ul><p>Onboarding<ul><li>Erfolgsplan ausführen</li><li>Plan für die technische Implementierung ausführen</li></ul>|
> |Den Legacy-PSTN-Konferenzdienst zur Mitte des Finanzjahres 2018 deaktivieren|2. Quartal des Finanzjahres 2018: Den Legacy-PSTN-Konferenzdienst deaktivieren|Höhere Wertschöpfung erzielen<ul><li>Benutzerengagement verstärken und Übernahme vorantreiben</li><li>Veränderungen vorbereiten und verwalten</li><li>Erfolg messen und teilen und Durchlauf beschleunigen</li>|

Mit den wichtigen Erfolgsindikatoren werden die Qualität und der Erfolg der Kernergebnisse gemessen, und sie vervollständigen den binären Charakter von Zielen und wesentlichen Ergebnissen (erreicht oder nicht erreicht) durch detaillierte Aufschlüsselung von guten bzw. schlechten Ergebnissen. Bei der Definition der wichtigen Erfolgsindikatoren empfehlen wir, „spezifische, messbare, zuweisbare, realistische, zeitbezogene“ und INTELLIGENTE Kriterien zugrunde zu legen.

> [!TIP]
> Im folgenden Beispiel sehen Sie für dieses Projekt relevante wichtige Erfolgsindikatoren:
> 
> |Typ  |Fragen und Kriterien im Zusammenhang mit den wichtigen Erfolgsindikatoren  |Messmethode  |Erfolgskriterien  |Bemessungszeitpunkt  |Verantwortlich  |
> |---------|---------|---------|---------|---------|---------|
> |Verwendung/Einführung|Anrufqualität entspricht der vorherigen Lösung oder übertrifft diese|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach der Aktivierung und vierteljährlich|IT-Team|
> |Verwendung/Einführung|Microsoft Teams hat den Kommunikationsprozess vereinfacht.|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach der Aktivierung und vierteljährlich|Change Management-Team|
> |Verwendung/Einführung|Aktive Verwendung der Lösung durch die Benutzer|Office 365-Berichte, Anrufqualitäts-Dashboard|80 % der Benutzer sind täglich aktiv|Täglich|Change Management-Team|
> |Verwendung/Qualität|Prozentsatz der Anrufe/Konferenzen mit schlechter Qualität sollte verringert werden|Anrufqualitäts-Dashboard|< 5 % Anrufe mit schlechter Qualität pro Monat|Täglich|IT-Team|
> |Verwendung/Support|Ich weiß, wo ich technischen Support erhalte|Umfrage|Zustimmung oder starke Zustimmung bei 90% der Benutzer|Nach der Aktivierung und vierteljährlich|Change Management-Team|
> |Verwendung/Support|Ich bin zufrieden mit der Qualität des technischen Supports|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach jedem Vorfall|IT-Team|
> |Finanzen|Weniger Minuten mit Legacy-Konferenzlösung|Finanzsystem|Definierte Rendite erzielen|Basierend auf Rendite|Change Management-Team|

Als Teil dieser Übung müssen Sie Geschäftsrisiken sowie einen Risikominderungsplan für jedes erkannte Risiko definieren. Diese Informationen können in einem Risikoplan erfasst werden.

> [!TIP]
> Den Risikoplan können Sie wie im folgenden Beispiel dokumentieren:
> 
> |Risiko  |Wahrscheinlichkeit  |Auswirkungen  |Gesamt  |Risikominderungsplan  |
> |---------|---------|---------|---------|---------|
> |Bei der bevorstehenden Fusion werden bis zu 1.000 Personen dazukommen|Hoch|Hoch|Hoch|<ul><li>Separate Ziele und wesentliche Ergebnisse mit eigenem Prozess (Ausblick, Onboarding und Wertschöpfung) für fusioniertes Unternehmen</li><li>Beziehen Sie diesen Prozess nicht in vorhandene Ziele und wesentliche Ergebnisse ein.</li></ul>|
> |Die Portierung von Telefonnummern verzögert den Projektabschluss.|Hoch|Hoch|Hoch|<ul><li>Bereiten Sie frühzeitig alle erforderlichen Informationen zur Unterstützung der Portierung von Telefonnummern vor (z. B. Kundendiensteintrag, Rechnungsdetails, schriftliche Vollmacht).</li><li>Passen Sie die Zeitschiene für das Projekt an, um die Dauer für die Portierung der Telefonnummern zu berücksichtigen.</li><li>Teilen Sie den externen Teilnehmern die neuen Einwahlkonferenznummern mit.</li></ul>|
> |Geplante Umgestaltung des Netzwerks|Hoch|Mittel|Mittel|<ul><li>Führen Sie vor der Implementierung von Teams als moderne Plattform für Kommunikation und Zusammenarbeit eine Auswertung der Netzwerkbereitschaft für Websites durch, die im Geltungsbereich des Projekts liegen.</li></ul>|

<a name="assess-environment-and-evaluate-adoption-readiness"></a>Bewerten der Umgebung und Überprüfen der Übernahmebereitschaft
--------------------------------------------------

Um die gewünschten Ziele und wesentlichen Ergebnisse zu erreichen, müssen Sie möglicherweise die allgemeine Architektur der Lösung definieren. Sie müssen Ihre Umgebung sehr gründlich erkunden, um alle Aspekte der IT- und Telefonie-Infrastruktur, des Netzwerks und des Betriebs auswerten zu können.

Alle Angelegenheiten bezüglich Endbenutzer-Computing wie die Auswertung der einsatzfähigen PCs und Mobilgeräten zwecks Unterstützung von Audiokonferenz-Geschäftsanwendungsfällen – von Hardwareanforderungen bis Softwareanforderungen – sind Teil der Erkundung der Umgebung.

Bei der Erkundung der Umgebung kann auch festgestellt werden, ob es Anforderungen für die [Portierung von Telefonnummern nach Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) gibt. Dies hilft Ihrer Organisation, den Projektplan entsprechend anzupassen und die für die Nummernportierung notwendigen Informationen bereitzustellen. Sie können die Umgebung erkunden, indem Sie den folgenden [Fragebogen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_3) ausfüllen.

Bei der Erkundung der Umgebung muss die Bereitschaft des Netzwerks bewertet werden, um sicherzustellen, dass das Netzwerk in der Lage ist, die Implementierung des Audiokonferenzdiensts zu unterstützen.

Die Netzwerkbereitschaft zur Unterstützung von Audiokonferenzen kann mithilfe der bei der Ermittlung der Umgebung gesammelten Informationen bestimmt werden. Diese Informationen umfassen Details zur Internetkonnektivität und WAN-Topologie, zu Standortverknüpfungen und zur verfügbaren Bandbreite sowie Persona-Analysedaten, die mit dem [My Advisor Network Planner-Tool](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) in eine erwartete Nutzung der einzelnen Arbeitsauslastungen übersetzt werden können. Um die Netzwerkbereitschaft noch genauer zu ermitteln, kann eine Simulation von Mediendatenverkehr in Echtzeit mit den von [Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) oder [Partnern von Network Readiness Assessment-Tools](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Partners?ToolPartners) bereitgestellten Lösungen durchgeführt werden.

Die Ergebnisse der Auswertung der Netzwerkbereitschaft zeichnen ein klares Bild der für eine erfolgreiche Implementierung der Audiokonferenzlösung erforderlichen Netzwerkoptimierung sowie Verbesserungsmaßnahmen.

Die Übernahmebereitschaft kann anhand der Ausführung einer Personenanalyse durchgeführt werden, um eine Liste der Personen in Ihrer Organisation zu erstellen, die für die Implementierung des Audiokonferenzdiensts in Frage kommen. Die Personenanalyse umfasst die Ermittlung weiterer Peripheriegeräte und sonstigen Geräten, die für die Erzielung der gewünschten Geschäftsergebnisse erforderlich sind.

Zur Ausführung einer Personenanalyse können Sie einen Workshop durchführen, indem Sie die jeweiligen Projektbeteiligten einbeziehen und die Workshop-Folie [Persona Alignment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_7) und die [Persona Feature Matrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_8) verwenden. Das Ergebnis des Personenanalyse-Workshops kann mit der Vorlage [Persona Analysis Report](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_9) in einem Bericht zusammengefasst werden.

> [!NOTE]
> Obwohl die Discovery Questionnaire- und die Persona Analysis-Beispiele zunächst für Skype for Business Online geschrieben wurden, sind die meisten Inhalte auch auf Teams übertragbar. Sie können Punkte, die für Ihre Projektziele nicht relevant sind, nach Belieben ändern oder entfernen.

Sie können die technischen Risiken als Teil einer Auswertung der Umgebung und Bewertung der Übernahmebereitschaft ermitteln und einen Plan zur Abhilfe für jedes erkannte Risiko entwickeln. Diese Informationen sollten als Teil des Risikoplans berücksichtigt werden.

<a name="map-operational-roles"></a>Zuordnen von operativen Rollen
---------------------

Die Planung der Ausführung und die Zusammenstellung des Teams, das den Audiokonferenzdienst ausführt, ist ein wichtiger Schritt, da die Ausführung beginnen muss, wenn die ersten Teilnehmer des Pilotprojekts aktiviert werden. Jedes zusammengestellte Team muss die angegebenen Aufgaben und Verantwortlichkeiten prüfen und diesen zustimmen und mit der Vorbereitung der Ausführung des Audiokonferenzdiensts beginnen. Die Vorbereitung kann Schulungen, die Bewertung der Bereitschaft, die Einbeziehung zusätzlicher Mitarbeiter oder die Verpflichtung von externen Anbietern zur Bereitstellung des Diensts umfassen.

> [!TIP]
> In der folgenden Beispielvorlage wird das Ergebnis der Zuordnung der operativen Rollen dokumentiert, die Sie für dieses Projekt vorgenommen haben:
> 
> |Operative Rolle  |Beschreibung  |Team  |Kontaktdetails  |
> |---------|---------|---------|---------|
> |Leiter des Kundendiensts|Diensteigentümer, Schnittstelle zu Geschäftsabteilungen, Strategie|TBA|TBA|
> |Aufgaben für Audiokonferenzen|Tägliche Aufgaben, Verschieben/Hinzufügen/Ändern von Benutzer- und Gerätekonten, Überwachung|TBA|TBA|
> |Mandantenadministrator|Ändern von mandantenweiten Einstellungen, Aktivieren von neuen Funktionen|TBA|TBA|
> |Helpdesk|Support-Schnittstelle für Endbenutzer|TBA|TBA|
> |Netzwerkaufgaben|Ausführung von LAN, WAN, WLAN und Internetzugriff|TBA|TBA|
> |Team für Clients und Endpunkte|Verwalten von Desktopbereitstellungen|TBA|TBA|
> |Ermitteln von Aufgaben|Verwalten der Identitätsinfrastruktur (AD, ADFS, Azure AD)|TBA|TBA|
> |Übernahme/Change Management|Sensibilisierung, Schulung und Übernahme für die Lösung|TBA|TBA|
> |Exchange-Aufgaben|Verwalten der Exchange-Umgebung|TBA|TBA|

Um die detailliertere Zuordnung der operativen Rollen zu vereinfachen (einschließlich der mit jeder operativen Rolle verbundenen Aufgaben), können Sie das [Operational Role Mapping Workbook](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16) verwenden, um die Details zu erfassen, die Ihnen einen Überblick über die Rollen und Verantwortlichkeiten für die Unterstützung des Audiokonferenzdiensts bieten.

<a name="document-success-plan"></a>Dokumentieren des Erfolgsplans
---------------------

Ein Erfolgsplan ist die in der Phase Ausblick erstellte Dokumentation, die aus dem Geschäftsszenario, der Bereitschaft für den Dienst, dem Übernahme- und Aufgabenplan besteht.

Der Erfolgsplan stattet das Projektteam – das FastTrack oder einen Bereitstellungspartner enthalten kann – mit ausreichend Informationen aus, um die Ziele der Organisation mit dem Audiokonferenzdienst zu erreichen.

In der Regel enthält ein Erfolgsplan die folgenden Hauptabschnitte:

-   Geschäftsszenario
-   Bereitschaft für den Dienst
-   Übernahmeplan
-   Aufgabenplan

### <a name="business-case"></a>Geschäftsszenario

Geschäftsanwendungsfälle, Projektbeteiligte, wesentliche Ergebnisse und wichtige Erfolgsindikatoren, Risiken und Projektzeitschienen bilden normalerweise die für ein Geschäftsszenario erforderlichen Informationen. Sie müssen sie als Teil des Erfolgsplans dokumentieren.

### <a name="service-readiness"></a>Bereitschaft für den Dienst

Die Auswertung der Umgebung bietet erste Informationen, die zur Einschätzung der technischen Bereitschaft für die Implementierung des Audiokonferenzdiensts erforderlich sind.

Enthalten hier ist der Plan zur Adressierung der Bereiche, für die aufgrund der Auswertung der Umgebung Verbesserungsmaßnahmen durchgeführt werden müssen. Sie müssen die Auswertung der Dienstbereitschaft und den Wartungsplan als Teil des Erfolgsplans einbeziehen.

### <a name="adoption-plan"></a>Übernahmeplan

Nach der Auswertung der Übernahmebereitschaft muss das Projektteam eine weitere detaillierte Planung vornehmen. Hierzu zählen umfassende Kommunikationspläne, ein Schulungsplan sowie Übernahmeaktivitäten vor, während und nach der Einführung des Diensts.

Ressourcen zur Unterstützung der Übernahmeaktivitäten wie Flyer, Willkommmens-E-Mails und Schulungsmaterialien sowie alle für die Anforderungen der Organisation notwendigen Anpassungen zählen zu diesem Schritt.

Die Vorlagen für Übernahmeaktivitäten sind [hier](https://www.microsoft.com/download/details.aspx?id=54244) verfügbar.

### <a name="operational-plan"></a>Aufgabenplan

Bei der Zuordnung von operativen Rollen werden Rollen und Verantwortlichkeiten sowie die jeder operativen Rolle zugewiesenen Teams definiert, um die Implementierung des Audiokonferenzdiensts zu unterstützen.

Sie müssen diesen Schritt abschließen und den operativen Plan als Teil des Erfolgsplans berücksichtigen, um die operative Bereitschaft der Lösung sicherzustellen.

<br>
Technische Planung für Audiokonferenzen
-----------------------------------------
<a name="technical-planning-for-audio-conferencing"></a> Um die technischen Implementierung der Audiokonferenz planen, eine Reihe von Entscheidungen erfolgen muss vorausschauendes besser Vorbereiten Ihrer Organisation zum Implementieren einer Lösung, die geschäftlichen Anforderungen erfüllt. Diese Entscheidungen werden in einem Plan zur technischen Implementierung dokumentiert.

## <a name="availability-of-audio-conferencing"></a>Verfügbarkeit von Audiokonferenzen

Audiokonferenzen sind in diesen [Ländern und Regionen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) verfügbar.

> [!IMPORTANT]
> Aufgrund von rechtlichen Beschränkungen müssen multinationale Organisationen, die Audiokonferenzen nutzen möchten, den Vertrag für Office 365-Abonnements in Ländern und Regionen abschließen, die vom Audiokonferenzdienst abgedeckt sind oder in denen dieser kommerziell erhältlich ist.

Wenn die Nutzung des Audiokonferenzdiensts durch Ihre Organisation bestätigt ist, erstellen Sie eine Liste der Benutzerstandorte oder Niederlassungen, in denen der Audiokonferenzdienst basierend auf der in der Liste verfügbaren Ländern und Regionen implementiert wird.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, an welchen Benutzerstandorten oder in welchen Niederlassungen der Audiokonferenzdienst implementiert wird.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzerstandorte oder Niederlassungen, die für den Audiokonferenzdienst aktiviert werden sollen.</li></ul>|

> [!TIP]
> Das folgende Beispiel zeigt eine Vorlage für eine Aktivierungsliste für Standorte mit dem Telefonsystem mit Anrufplänen:
> 
> |Niederlassung   |Standort |PSTN-Konferenzdienst  |
> |---------|---------|---------|
> |One Epping Road|Australien|Audiokonferenzen|
> |100 Cyberport Road|Hong Kong SAR (香港特別行政區)|Legacy-PSTN-Konferenz|
> |One Marina Boulevard|Singapur|Audiokonferenzen|
> |32 London Bridge Street|Vereinigtes Königreich|Audiokonferenzen|
> |39 quai du Président Roosevelt|Frankreich|Audiokonferenzen|

## <a name="licensing-for-audio-conferencing"></a>Lizenzierung für Audiokonferenzen

Die [Audiokonferenzlizenz](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) ist im Rahmen der Office 365 E5-Abonnementpläne oder als Add-On für Office 365 E1- oder Office 365 E3-Abonnementpläne verfügbar.

> [!NOTE]
> PSTN- oder Einwahlkonferenzen in Teams bieten keine Unterstützung für <sup>Drittanbieter</sup> von Audiokonferenzanbieter-Partnern (Audio Conferencing Provider, ACP). <br>Wenn Sie den PSTN-Konferenzdienst für Skype for Business bereits verwenden, können Sie unmittelbar die Vorteile des Audiokonferenzdiensts in Teams nutzen.

Um gebührenfreie Telefonnummern für Konferenzbrücken zur Verfügung zu stellen und ausgehende Konferenzanrufe für internationale Telefonnummern zu unterstützen, müssen Sie [Kommunikationsguthaben](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) für Ihre Organisation einrichten.

> [!IMPORTANT]
> Für einige Länder/Regionen gibt es nur gebührenfreie Telefonnummern für Konferenzbrücken. In diesem Fall ist die Verwendung von Kommunikationsguthaben verpflichtend, um die Einwahl für diese Länder/Regionen zu unterstützen.

Bei der Implementierung von Kommunikationsguthaben müssen Sie zunächst überlegen, wie hoch der anfängliche Betrag für das Guthaben sein soll. Die empfohlenen Einzahlungsbeträge können Sie dem Artikel [Was ist Guthaben für Kommunikationen?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) entnehmen.

Wenn sich Ihre Organisation für automatisches Aufladen entscheidet, finden Sie im Artikel [Was ist Guthaben für Kommunikationen?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) außerdem eine Empfehlung für den niedrigsten Betrag, der das automatische Aufladen auslöst. Der Betrag für die automatische Auffüllung richtet sich nach der tatsächlichen Verwendung. Die Verwendung von Guthaben für Kommunikationen sollte immer überwacht werden, und der Aufladebetrag muss nach Bedarf angepasst werden.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Wenn Ihre Organisation die erforderlichen Audiokonferenzlizenzen noch nicht erworben hat, entscheiden Sie, ob Sie diese Lizenzen durch die Erweiterung vorhandener Office 365-Abonnements oder durch den Kauf von Audiokonferenz-Add-Ons erwerben möchten.</li><li>Entscheiden Sie, ob Kommunikationsguthaben für die Implementierung von Audiokonferenzen erforderlich sind. Wenn ja, legen Sie den anfänglichen Auffüllungsbetrag fest. Legen Sie zudem fest, wie hoch der niedrigste Betrag sein sollte, bei dem die automatische Auffüllung ausgelöst wird.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie, welchen Benutzern eine Audiokonferenzlizenz zugewiesen wird.</li><li>Dokumentieren Sie den Plan für Guthaben für Kommunikationen (anfänglicher Betrag und Auslösebetrag für automatisches Aufladen, Höhe des Betrags für automatisches Aufladen).</li></ul>|

> [!TIP]
> Sie können die Lizenzzuweisungsliste für Benutzer von Audiokonferenzen anhand des folgenden Beispiels dokumentieren:
> 
> |Benutzer  |Niederlassung  |Office 365-Lizenz  |
> |---------|---------|---------|
> |Adele Vance|One Epping Road|Office 365 E5|
> |Alex Wilber|One Epping Road|Office 365 E3, Add-On für Audiokonferenzen|
> |Ben Walters|One Epping Road|Office 365 E3, Add-On für Audiokonferenzen|
> |Christie Cline|One Marina Boulevard|Office 365 E3, Add-On für Audiokonferenzen|
> |Debra Berger|One Marina Boulevard|Office 365 E5|
> |Lee Gu|One Marina Boulevard|Office 365 E5|
> |Emily Braun|32 London Bridge Street|Office 365 E5|
> |Lidia Holloway|32 London Bridge Street|Office 365 E5|
> |Pradeep Gupta|32 London Bridge Street|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, Add-On für Audiokonferenzen|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, Add-On für Audiokonferenzen|

<br>
> [!TIP]
> Sie können Ihre Zahlen für die Planung des Guthabens für Kommunikationen so dokumentieren:
> |         |         |
> |---------|---------|
> |Anfangsbetrag|1.000 US-Dollar|
> |Betrag für die Auslösung der Auffüllung|400 US-Dollar|
> |Höhe des Betrags für die automatische Auffüllung|TBA|
> 

## <a name="conference-bridge-phone-numbers"></a>Telefonnummern für Konferenzbrücken

Der Audiokonferenzdienst in Office 365 umfasst:

-   Mehrere Typen von Telefonnummern für Konferenzbrücken (gebührenpflichtig und gebührenfrei)
-   Mehrere Kategorien der Telefonnummer (dediziert oder freigegeben)
-   Unterstützung für mehrere Sprachen für die Konferenzbrücke (primär oder sekundär)
-   Eine Standardtelefonnummer für den Mandanten.

Eine vollständige Beschreibung der enthaltenen Funktionen finden Sie unter [Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) und [Telefonnummern für Audiokonferenzen](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing).

> [!NOTE]
> Dedizierte Telefonnummern für Konferenzbrücken werden basierend auf der Anzahl der anwendbaren Lizenzen auf die Telefonnummern angerechnet, die pro Mandant angefordert werden können. Erläuterungen hierzu finden Sie unter [Erhalten von Servicenummern für Skype for Business und Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers). Für gebührenfreie Telefonnummern für Konferenzbrücken ist Kommunikationsguthaben erforderlich.

Vorhandene Telefonnummern für Konferenzbrücken, die in den Audiokonferenzdienst übertragen werden müssen, und unter der Voraussetzung, dass diese die landespezifischen Anforderungen erfüllen, können nach Microsoft portiert werden.

> [!NOTE]
> Die Komplexität der Portierung von Telefonnummern nach Microsoft richtet sich sehr stark nach den jeweiligen Ländern oder Regionen, Netzbetreibern, der Anzahl der beteiligten Verbindungen und vielen anderen Faktoren. Informationen zur Portierung von Telefonnummern finden Sie im [Handbuch zur Portierung von Telefonnummern](https://go.microsoft.com/fwlink/?linkid=859011).

Weitere Details zum Übertragen von Telefonnummern zum Audiokonferenzdienst finden Sie unter [Übertragen von Telefonnummern zu Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Wählen Sie aus, ob Ihre Organisation dedizierte Telefonnummern für Konferenzbrücken benötigt.</li><li>Entscheiden Sie, wie die dedizierten Telefonnummern für Konferenzbrücken für die jeweiligen Benutzerstandorte oder Niederlassungen für die Implementierung von Audiokonferenzen abgerufen werden sollen (über Microsoft oder anhand der Portierung von vorhandenen Telefonnummern).</li><li>Wenn Sie sich für Microsoft entscheiden, wählen Sie die Methode zum Abrufen von Telefonnummern (Formulareingabe oder automatisch) für die jeweiligen Benutzerstandorte oder Niederlassungen für die Implementierung von Audiokonferenzen aus.</li><li>Wählen Sie die Spracheinstellungen für alle dedizierten Telefonnummern für Konferenzbrücken aus.</li><li>Wählen Sie die Standardtelefonnummer für Konferenzbrücken für den Mandanten aus.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie den Masterplan für den Erwerb von Telefonnummern mit Details darüber, wie die Telefonnummern an jedem einzelnen Benutzerstandort oder jeder einzelnen Niederlassung für die Implementierung von Audiokonferenzen abgerufen werden.</li><li>Falls anwendbar, füllen Sie für jeden Standort oder jede Niederlassung das Formular <a href="https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization">für die Anforderung neuer Telefonnummern</a> aus.</li><li>Wenn Sie vorhandene Telefonnummern übertragen möchten, können Sie diesen Vorgang mit Unterstützung des <a href="https://go.microsoft.com/fwlink/?linkid=859011">Handbuchs für die Nummernportierung</a> planen und den Zeitplan für die Implementierung von Audiokonferenzen entsprechend anpassen.</li><li>Dokumentieren Sie die detaillierten Konfigurationen der Telefonnummern für Konferenzbrücken (freigegebene und dedizierte Telefonnummern für Konferenzbrücken, Spracheinstellungen für jede dedizierte Telefonnummer für Konferenzbrücken, standardmäßige Telefonnummer für Konferenzbrücken für den Mandanten).</li></ul>|

> [!TIP]
> Das folgende Beispiel zeigt eine Vorlage zum Erfassen der Details von Konferenzbrücken:
> 
> |Niederlassung   |Anschaffung der Brückennummer und Brückentyp |Brückennummer  |Brückensprache|
> |---------|---------|---------|---------|
> |One Epping Road|Neu anschaffen, dediziert|TBA|Englisch (Australien)|
> |One Marina Boulevard|Neu anschaffen, freigegeben|TBA|Englisch (Vereinigte Staaten), Chinesisch (vereinfacht)|
> |32 London Bridge Street|Port vorhanden, dediziert|+44 20 7946 0001|Englisch (Vereinigtes Königreich)|
> |39 quai du Président Roosevelt|Neu anschaffen, dediziert|TBA|Französisch (Frankreich), Englisch (Vereinigtes Königreich)|

## <a name="conference-bridge-settings"></a>Einstellungen der Konferenzbrücke

Organisationsweite Konfigurationsoptionen für die Teilnahme an Audiokonferenzbesprechungen (Benachrichtigung über Zu- und Abgänge der Besprechung sowie die Aufzeichnung des Anrufernamens), PIN-Länge des Besprechungsorganisators und E-Mail-Benachrichtigung sind zur weiteren Anpassung der Endbenutzerfunktionen verfügbar.

-   Benachrichtigungen über Zu- und Abgänge in Besprechungen sind in Form eines aufgezeichneten Namens, einer Telefonnummer und Signaltönen verfügbar.
-   Die PIN-Länge ist mit 4 bis zwölf Ziffern konfigurierbar, wobei eine PIN standardmäßig aus 5 Ziffern besteht.
-   Benachrichtigungs-E-Mails werden bei der Aktivierung der Lizenz für Audiokonferenzen oder durch andere vom Administrator vorgenommenen Änderungen standardmäßig aktiviert. Sie können diese Funktion deaktivieren und die Kontrolle über die Kommunikation Ihrer Endbenutzer übernehmen.

Für Benutzer, denen eine Lizenz für Audiokonferenzen zugewiesen ist, können die gebührenpflichtigen bzw. gebührenfreien Nummern (wie in den Koordinaten für Audiokonferenzen gezeigt) so konfiguriert werden, dass sie Folgendes verwenden können:

-   die standardmäßigen Telefonnummern für Konferenzbrücken auf der Ebene des Mandanten
-   die automatisch zugewiesenen Telefonnummern für Konferenzbrücken
-   die für jeden Benutzer manuell definierten Telefonnummern für Konferenzbrücken

Benutzerspezifische Telefonnummern für Konferenzbrücken sind in der Regel in globalen oder überregionalen Organisationen sinnvoll, in denen Benutzer verteilt sind und lokale Nummern als Standardtelefonnummern für Konferenzbrücken in den Besprechungseinladungen angeben müssen.

Teilnehmer aus anderen Städten oder aus dem Ausland können weitere auf der Mandantenebene konfigurierte Nummern nachschlagen, diese Nummern werden jedoch nicht direkt in den Besprechungseinladungen angezeigt. Die Besprechungseinladungen enthalten einen Link, über den die Teilnehmer zu der Seite mit den Einwahlnummern für Teams-Konferenzen gelangen. Dort können die Teilnehmer die für Ihren Standort geltenden Telefonnummern für Konferenzbrücken in Erfahrung bringen.

Sie können auch konfigurieren, wie nicht authentifizierte Anrufer von jedem einzelnen Besprechungsorganisator gehandhabt werden. Dabei können Sie festlegen, ob der Besprechungsorganisator die Besprechung starten muss, bevor nicht authentifizierte Benutzer zugelassen werden, oder ob nicht authentifizierte Anrufer eine Besprechung starten können.

Zusätzliche für jeden Benutzer anwendbare Konfigurationen sind verfügbar, um die Verwendung von gebührenfreien Telefonnummern für Konferenzbrücken sowie das Anrufen aus einer Konferenz heraus zu steuern.

> [!NOTE]
> Diese mit Kosten verbundenen Steuerelemente sind derzeit nur für Preview-Kunden verfügbar. Sie können registrieren Sie Ihre Organisation in der Vorschau-Anwendung aus [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).

Mit diesen Steuerelementen können Sie entscheiden, ob Besprechungsorganisatoren gebührenfreie Telefonnummern für Konferenzbrücken für die von ihnen organisierten Besprechungen zur Verfügung stellen können, und ob sie steuern können, ob Teilnehmer Anrufe aus den von ihnen organisierten Besprechungen heraus tätigen können. Die Steuerungsebene rangiert hierbei vom Nichtzulassen von ausgehenden Anrufen, Zulassen von ausgehenden Anrufen an Inlandsnummern bis zum Zulassen von ausgehenden Anrufen an Inlands- und Auslandsnummern.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob die Organisation Benachrichtigungen über Zu- und Abgänge benötigt. Wenn ja, wählen Sie den zu implementierenden Benachrichtigungstyp (Signalton, Telefonnummer oder aufgezeichneter Name) aus.</li><li>Legen Sie die Länge der PIN für Audiokonferenzen gemäß den Sicherheitsanforderungen der Organisation fest.</li><li>Legen Sie fest, ob die Organisation die mit dem Audiokonferenzdienst verbundene Kommunikation der Endbenutzer steuern möchte.</li><li>Wählen Sie die Telefonnummern für Konferenzbrücken aus, die den einzelnen Besprechungsorganisatoren zugewiesen werden.</li><li>Legen Sie fest, ob einige Besprechungsorganisatoren in die Lage versetzt werden sollen, gebührenfreie Telefonnummern für Konferenzbrücken in Ihren Besprechungen zu verwenden.</li><li>Entscheiden Sie, ob es einigen Besprechungsorganisatoren möglich sein soll, nicht authentifizierten Anrufern das Starten einer Besprechung zu erlauben.</li><li>Entscheiden Sie, ob für einige Besprechungsorganisatoren ausgehende Anrufe in der Konferenz gesteuert werden sollen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die detaillierten Konferenzbrückeneinstellungen (Benachrichtigungen über Zu- und Abgänge, PIN-Länge, E-Mail-Benachrichtigung über Konfigurationsänderungen).</li><li>Dokumentieren Sie die Telefonnummern für Konferenzbrücken, die den einzelnen Besprechungsorganisatoren zugewiesen werden, und die entsprechende Einstellung zum Steuern der Richtlinie für nicht authentifizierte Anrufer sowie Steuerelemente für gebührenfreie und ausgehende Anrufe.</li></ul>|

> [!TIP]
> Sie können die Einstellungen der Konferenzbrücke so dokumentieren:
> 
> |         |         |
> |---------|---------|
> |Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren|Aktiviert|
> |Ankündigungstyp für Zu- und Abgänge|Signaltöne|
> |Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen|Deaktiviert|
> |PIN-Länge|5|
> |Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert.|Deaktiviert|

<br>
> [!TIP]
> Sie können die Zuweisungsliste für die Einstellungen der Konferenzbrücken für Benutzer von Audiokonferenzen anhand des folgenden Beispiels dokumentieren:
>
> |Benutzer  |Niederlassung  |Gebührenpflichtige Standardnummer  |Gebührenfreie Standardnummer  |Gebührenfreie Nummer zulassen  |Nicht authentifizierte Anrufer umgehen Wartebereich  |Konferenzauswahl  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|One Epping Road|TBA|TBA|Ja|Aktiviert|In- und Auslandsanrufe|
> |Alex Wilber|One Epping Road|TBA|TBA|Nein|Deaktiviert|Nicht zulässig|
> |Ben Walters|One Epping Road|TBA|TBA|Nein|Deaktiviert|Nicht zulässig|
> |Christie Cline|One Marina Boulevard|TBA|TBA|Ja|Deaktiviert|Inlandsanruf|
> |Debra Berger|One Marina Boulevard|TBA|TBA|Ja|Aktiviert|Inlandsanruf|
> |Lee Gu|One Marina Boulevard|TBA|TBA|Ja|Aktiviert|Inlandsanruf|
> |Emily Braun|32 London Bridge Street|+44 20 7946 0001|TBA|Ja|Aktiviert|Nicht zulässig|
> |Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|TBA|Ja|Deaktiviert|Nicht zulässig|
> |Pradeep Gupta|32 London Bridge Street|+44 20 7946 0001|TBA|Ja|Deaktiviert|Nicht zulässig|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|Nein|Deaktiviert|Inlandsanruf|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|Ja|Aktiviert|In- und Auslandsanrufe|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|Nein|Deaktiviert|Inlandsanruf|

## <a name="dial-plans"></a>Wählpläne

Bei einem [Wählplan](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) in der Telefonsystemfunktion von Office 365 handelt es sich um eine Gruppe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise das Format [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) übersetzt, um Anrufe zu autorisieren und weiterzuleiten. Der Audiokonferenzdienst nutzt die gleichen Funktionen wie das Telefonsystem, um in Szenarien für die Konferenzauswahl gewählte Telefonnummern zu übersetzen.

Mit einem Wählplan können Benutzer Telefonnummern so wählen, wie sie es gewöhnt sind. Zum Beispiel müssen sie bei Ortsgesprächen keine Vorwahl wählen, bei Inlandsanrufen keine Landeskennzahl wählen, und sie können sogar Kurzwahlnummern für ausgehende Anrufe in Konferenzen verwenden.

Innerhalb der Telefonsystemfunktion in Office 36 gibt es zwei Arten von Wählplänen:

-   **Dienstwählplan**. Dies ist der Standardwählplan, der auf einem Office 365-Verwendungsstandort basiert und nicht geändert werden kann.
-   **Mandantenwählplan**. Dies ist ein anpassbarer Wählplan innerhalb eines Mandanten, der wiederum zwei Typen umfasst:
    -   **Globaler Wählplan für Mandanten**: Der Wählplan gilt für alle Benutzer innerhalb des Mandanten.
    -   **Wählplan für Mandantenbenutzer**: Der Wählplan gilt nur für bestimmte Benutzer.

> [!NOTE]
> Weitere Details und Beispiele finden Sie in der Dokumentation [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).

Der den Benutzern zugewiesene wirksame Wählplan stellt eine Kombination aus dem Dienstwählplan (basierend auf dem Office 365-Verwendungsstandort des Benutzers) und dem Mandantenwählplan (entweder globaler Wählplan für Mandanten oder Wählplan für Mandantenbenutzer) dar.

![Die Tabelle zeigt drei Kombinationen aus Dienst- und Mandantenwählplänen.](media/audio_conferencing_image8.png)

Normalisierungsregeln können maximal 25 Regeln in jedem Mandantenwählplan enthalten. Eine Duplizierung von bereits als Teil des Dienstwählplans vorhandenen Normalisierungsregeln sollte daher vermieden werden.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Ihre Organisation angepasste Wählpläne benötigt (Geschäftsanforderungen, Einführungsanforderungen usw.).</li><li>Legen Sie gegebenenfalls den Gültigkeitsbereich für den Mandantenwählplan (globaler Mandantenwählplan oder Wählplan für Mandantenbenutzer) fest, um die Anforderungen für angepasste Wählpläne zu erfüllen.</li><li>Legen Sie gegebenenfalls die Mandantenwählpläne fest, die zur Unterstützung von Benutzerstandorten oder Niederlassungen für die Implementierung von Audiokonferenzen erstellt werden.</li><li>Legen Sie gegebenenfalls fest, für welche Benutzer ein angepasster Wählplan benötigt wird und welcher Mandantenwählplan den einzelnen Benutzern zugewiesen wird.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die angepassten Wählpläne und die zugehörigen Normalisierungsregeln, die als Teil der Implementierung von Audiokonferenzen konfiguriert werden.</li><li>Dokumentieren Sie, welchen Benutzern ein angepasster Wählplan zugewiesen wird, und welcher Mandantenwählplan den einzelnen Benutzern zugewiesen wird.</li></ul>|

> [!TIP]
> Wenn die entsprechenden Punkte für Ihr Projekt zutreffen, können Sie die Konfigurationen der Mandantenwählpläne in der folgenden Vorlage dokumentieren:
> 
> |Name des Mandantenwählplans<br>_Beschreibung_  |Name der Normalisierungsregeln<br>_Beschreibung_  |Muster<br>Übersetzung<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, Wählplan für Australien_|**AU-NSW-NorthRyde-OER-Internal**<br>_Interne Nummer (x7000 - x7999) für One Epping Road-Niederlassung, North Ryde, NSW, Australien_|^(7\d{3})$<br>+6125550$1<br>Wahr|
> ||**AU-NSW-Local**<br>_Normalisierung für lokale Nummern für NSW, Australien_|^ ([2-9] \d{7}) $<br>+612$1<br>Falsch|
> ||**AU-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Australien_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>Falsch|
> ||**AU-Service**<br>_Normalisierung für Servicenummern für Australien_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>Falsch|
> |**SG-Singapore-OMB**<br>_OMB Singapore, Wählplan für Singapur_|**SG-OMB-Internal**<br>_Interne Nummer (x8000 – x8999) für OMB-Niederlassung, Singapur_|^(8\d{3})$<br>+656888$1<br>Wahr|
> ||**SG-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Singapur_|^(1?800\d{7}) \d*$<br>+65$1<br>Falsch|
> ||**SG-Service**<br>_Normalisierung für Servicenummern für Singapur_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>Falsch|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, Wählplan für Frankreich_|**FR-39qdPR-Internal**<br>_Interne Nummer (x7000 – x7999) für 39 quai du Président Roosevelt-Niederlassung, Issy-les-Moulineaux, Frankreich_|^(7\d{3})$<br>+3319999$1<br>Wahr|
> ||**FR-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Frankreich_|^ 0?(80\d{7}) \d*$<br>+33$1<br>Falsch|
> ||**FR-Service**<br>_Normalisierung für Servicenummern für Frankreich_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>Falsch|

<br>

> [!TIP]
> Sie können die folgende Beispielvorlage nutzen, um Wählplanzuweisungen für Ihr Projekt zu dokumentieren:
>
> |Benutzer  |Niederlassung  |Typ des Wählplans  |Name des Wählplans  |
> |---------|---------|---------|---------|
> |Adele Vance|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
> |Alex Wilber|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
> |Ben Walters|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
> |Christie Cline|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
> |Debra Berger|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
> |Lee Gu|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Dienstwählplan|n/v|
> |Lidia Holloway|32 London Bridge Street|Dienstwählplan|n/v|
> |Pradeep Gupta|32 London Bridge Street|Dienstwählplan|n/v|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|

## <a name="microsoft-teams-configurations"></a>Microsoft Teams-Konfigurationen

Audiokonferenzen werden in Ad-hoc-Besprechungen und geplanten Besprechungen unterstützt. Für geplante Besprechungen müssen Konfigurationen auf Mandantenebene aktiviert werden, die die Planung von Besprechungen (private Besprechungen und Kanalbesprechungen) steuern.

> [!NOTE]
> Wenn Ihre Organisation Compliance-Anforderungen erfüllen muss, um sicherzustellen, dass alle Besprechungsdiskussionen gefunden werden können, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.<br>
> Wenn in einem anderen Anwendungsfall alle Besprechungen in der Organisation nur für **eingeladene Benutzer** sichtbar sein müssen, empfehlen wir Ihnen, die Funktion zum Planen von Besprechungen in **Kanälen** zu deaktivieren, um die Offenlegung von Informationen für nicht eingeladene Benutzer zu vermeiden.

Die als Konfigurationen auf Mandantenebene verfügbaren Einstellungen sind auf alle Benutzer in der Organisation anwendbar und wirken sich auf die gesamte Besprechungsplanung in Teams und nicht nur auf Teams-Besprechungen **mit** Audiokonferenzen aus.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob das Planen von privaten Besprechungen in der Organisation aktiviert oder deaktiviert werden soll.</li><li>Entscheiden Sie, ob das Planen von Kanalbesprechungen in der Organisation aktiviert oder deaktiviert werden soll.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Konfigurationen für die Besprechungsplanung für Microsoft Teams.</li></ul>|

> [!TIP]
> Sie können die Konfigurationen für Microsoft Teams-Besprechungen so dokumentieren:
> 
> |         |         |
> |---------|---------|
> |„Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen)|Aktiviert|
> |„Allow scheduling for channel meetings“ (Planen von Kanalbesprechungen zulassen)|Deaktiviert|

## <a name="document-technical-implementation-plan"></a>Dokumentieren des Plans für die technische Implementierung

Verwenden Sie die Entscheidungspunkte oben, um Ihren Plan zur technischen Implementierung zu dokumentieren.
Mit diesem Plan wird das Projektteam (mit FastTrack oder einem Bereitstellungspartner) mit Informationen zur Ausführung des technischen Onboardings für die Implementierung von Audiokonferenzen versorgt.

In der Regel enthält ein Plan zur technischen Implementierung die folgenden Hauptabschnitte:

-   Aktivierungsliste für Audiokonferenzdienst-Standorte

-   Lizenzzuweisungsliste für Besprechungsorganisatoren von Audiokonferenzen

-   Zahlen für die Planung des Kommunikationsguthabens

-   Details zur Konferenzbrücke

-   Einstellungen der Konferenzbrücke

-   Zuweisungen der Einstellungen für die Konferenzbrücke

-   Mandantenwählpläne

-   Wählplanzuweisungen

-   Microsoft Teams-Besprechungskonfigurationen

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

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)