---
title: Audiokonferenzen in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Praktische Anleitungen zur Bereitstellung von Cloud Voice in Microsoft Teams.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: c6791646b58111a9785430b6541c57972a15ab20
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a>Audiokonferenzen in Microsoft Teams
=====================================

> [!IMPORTANT]
> Die Funktion „Audiokonferenzen“ ist als Public Preview-Funktion verfügbar. Early Adopters (EA) und Preview-Kunden können auf diese Funktion zugreifen und sie nach der Veröffentlichung oder Aktualisierung ändern.

Mit der Funktion „Audiokonferenzen“ in Office 365 (ehemals als PSTN-Konferenzen bezeichnet) können Teilnehmer mit einem beliebigen Telefon an Ihren Besprechungen teilnehmen. Diese Funktion ist jetzt auch in Microsoft Teams als Public Preview verfügbar – Benutzer können über ihre Telefone an Teams-Besprechungen teilnehmen. Die praktischen Anleitungen in diesem Artikel begleiten Sie schrittweise auf Ihrer Office 365 FastTrack-Customer Journey für Audiokonferenzen. Die Themen lauten: Ausblick, Onboarding und Wertschöpfung.

Das bekommen Sie mit [Audiokonferenzen](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.

> [!NOTE]
> Audiokonferenzen werden sowohl in Teams als auch in Skype for Business Online unterstützt. Das Skype for Business Admin Center und die PowerShell bieten Verwaltungsschnittstellen zur Verwaltung von Audiokonferenzen.


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

Ausblick <a name="Envision_AudioConferencing"> </a>
=========

Die Ausblick-Phase bietet die Grundlage für die Office 365 Customer Journey und kann auf alle Arbeitsauslastungen wie zum Beispiel Audiokonferenzen angewendet werden.

In dieser Phase formulieren die jeweiligen Projektbeteiligten die Geschäftsziele und stellen Folgendes bereit:

-   Ein umfassendes Erfolgskonzept mit Geschäftsanwendungsfällen, wichtigen Projektbeteiligen, Zielen und wesentlichen Ergebnissen, wichtigen Erfolgsindikatoren, Risiken, einer Einschätzung der Umgebung, Übernahmebereitschaft und Einsatzplanung.

-   Ein detaillierter Plan für die technische Implementierung der Audiokonferenzfunktion, um den gewünschten Endzustand zu erreichen.

<a name="define-business-use-cases-for-audio-conferencing"></a>Definieren von Geschäftsanwendungsfällen für Audiokonferenzen
------------------------------------------------

Mit Audiokonferenzen erhalten Organisationen weitere Einstiegspunkte zu geplanten Besprechungen, indem Teilnehmer über PSTN an Besprechungen teilnehmen können, wenn sie sich mit einem herkömmlichen Festnetz, PBX oder Mobiltelefonen einwählen.

Dies ist hilfreich, wenn der Organisator oder die Teilnehmer nicht vor ihren Computern sitzen oder wenn die Datenverbindungen für VoIP-Kommunikation nicht verfügbar oder nicht zuverlässig sind – zum Beispiel an einem Remotestandort mit schlechter Netzabdeckung, bei Verbindungen über einen gebührenfreien, öffentlichen WLAN-Dienst mit eingeschränkter Bandbreite oder, wenn es Besprechungsteilnehmer bevorzugen, sich über einen ihnen zur Verfügung stehenden Telefonie-Endgeräten einwählen.

In diesem Schritt definieren die wichtigsten Projektbeteiligten Geschäftsanwendungsfälle, die die Implementierung von Audiokonferenzen unterstützen.

Mit Geschäftsanwendungsfällen werden die erwarteten und messbaren Geschäftsergebnisse definiert und dokumentiert. Dazu zählen:

-   Beschreibung des aktuellen Geschäftsprozesses

-   Herausforderungen mit vorhandenen bereits definierten Geschäftsprozessen

-   Wie diesen Herausforderungen am besten begegnet werden kann

-   Die erwarteten und messbaren Geschäftsergebnisse, wenn diese Herausforderungen gemeistert wurden

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><strong>Beschreibung des aktuellen Geschäftsprozesses</strong></p>
<p>Für interne Besprechungen und Besprechungen mit Dritten nutzt Contoso derzeit die von etablierten lokalen Telefonanbietern bereitgestellten PSTN-Konferenzdienste, die im Minutentakt abgerechnet werden.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><strong>Herausforderungen mit vorhandenen Geschäftsprozessen</strong></p>
<p>Contoso investiert jährlich rund 1 Million US-Dollar für den aktuellen PSTN-Konferenzdienst, wobei 75 % der Kosten auf interne Besprechungen zurückzuführen sind.</p>
<p>Die Verwendung von herkömmlichen Telefonie-Endpunkten für die Teilnahme an durch den PSTN-Konferenzdienst gehosteten Besprechungen ist nicht an das Konzept für die Organisation zur Übernahme von Teams als moderne Plattform für Kommunikation und Zusammenarbeit angepasst.</p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><strong>Wie diesen Herausforderungen am besten begegnet werden kann</strong></p>
<p>Mit der Übernahme von Microsoft Teams als Plattform für Kommunikation und Zusammenarbeit wird von internen Benutzern erwartet, dass sie primär mit ihren PCs (mit optimierten Headsets und Geräten für Besprechungsräume) an Besprechungen teilnehmen. Der Audiokonferenzdienst dient der Unterstützung von externen Teilnehmern oder der Unterstützung von Situationen, in denen die Verwendung der PC-Audiofunktionen für die internen Teilnehmer nicht vorteilhaft ist.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><strong>Erwartete, messbare Geschäftsergebnisse</strong></p>
<p>Mit dem Wechsel zu Teams als moderne Plattform für Kommunikation und Zusammenarbeit in Kombination mit dem Audiokonferenzdienst werden die Kosten der Bereitstellung des PSTN-Konferenzdiensts erheblich reduziert. Die Einsparungen gehen sogar so weit, dass Contoso lediglich 20 % der jährlichen Kosten im Vergleich zum herkömmlichen PSTN-Konferenzdienst aufwenden muss.</p></td>
</tr>
</tbody>
</table>

_Tabelle 1: Geschäftsanwendungsfall – Beispiel_


Zusätzlich zum Definieren von Geschäftsanwendungsfällen hilft eine Klarheit in Bezug auf den organisatorischen Geltungsbereich und die Projektzeitschiene in diesem Schritt, zum nächsten Schritt der Ausblick-Phase zu wechseln.

<a name="identify-key-stakeholders"></a>Identifizieren der wichtigsten Projektbeteiligten
-------------------------

Die im vorherigen Schritte definierten Geschäftsanwendungsfälle enthalten die Implementierung von Audiokonferenzen als organisatorischen Geltungsbereich, und basierend darauf kann eine umfassende Liste mit Projektbeteiligten erstellt werden, um die richtigen Personen in das Projekt einzubeziehen.

<table>
<thead>
<tr class="header">
<th align="left">Rolle</th>
<th align="left">Beschreibung</th>
<th align="left">Name, Kontaktinformationen, Standort</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Leitender Projektsponsor</strong></td>
<td align="left"><ul><li>Hat höchste Entscheidungsbefugnis und Rechenschaftspflicht für das Projekt und die Bereitstellung von Projektzielen</li>
<li>Bietet Unterstützung bei der Lösung der vom Projektleiter eskalierten Probleme</li>
<li>Bietet Unterstützung bei die Kommunikation innerhalb des Unternehmens</li>
<li>Ist für wichtige strategische Entscheidungen verantwortlich</li>
<li>Trägt Verantwortung für die Verfügbarkeit der erforderlichen Ressourcen und das benötigte Budget</p>
<li>Verfasst vierteljährliche Geschäftsberichte</li>
<li>Organisiert und unterstützt Sensibilisierungskampagnen</li>
<li>Ist Projektsponsor für das Programm-Rollout</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Projektleiter</strong></td>
<td align="left"><ul><li>Führt und leitet das Projektteam</li>
<li>Koordiniert die am Projekt beteiligten Partner und Arbeitsteams</li>
<li>Ist für das Erstellen und Verwalten von Projektplänen verantwortlich, um die wesentlichen Quartalsergebnisse zu erzielen</li>
<li>Behebt funktionsübergreifende Probleme</li>
<li>Erstellt einen regelmäßigen Rechenschaftsbericht für die Projektsponsoren</li>
<li>Bezieht Übernahmeaspekte in den fertigen Projektplan ein</li>
<li>Verfasst monatliche Geschäftsberichte als Grundlage für vierteljährliche Geschäftsberichte</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Leiter/Architekt für Zusammenarbeit</strong></td>
<td align="left"><ul><li>Ist für die Ausführung der Zusammenarbeitsstrategie verantwortlich, die von den Führungskräften des Unternehmens definiert wird</li>
<li>Analysiert und wählt Produkte für die Zusammenarbeit für das Unternehmen aus, das die Geschäftsziele erreicht</li>
<li>Ist für die operationale Architektur von Produkten für die Zusammenarbeit verantwortlich</li>
<li>Definiert operative und Support-Modelle</li>
<li>Liefert Beiträge für die monatlichen und vierteljährlichen Geschäftsberichte</li><ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Berater</strong></td>
<td align="left"><ul><li>Ist für Konfigurationsdienste verantwortlich</li>
<li>Liefert Beiträge zur Architektur der Gesamtlösung</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Projektmanager</strong></td>
<td align="left"><ul><li>Entwickelt und verwaltet den Projektplan</li>
<li>Verwaltet die Projektergebnisse in Bezug auf die Einhaltung des Projektplans und des Budgets</li>
<li>Zeichnet Projektprobleme (zum Beispiel Eskalationen) auf und verwaltet diese</li>
<li>Tätigt wöchentliche Teamanrufe</li>
<li>Kontaktiert die leitenden Projektsponsoren und stellt aktuelle Informationen bereit</li>
<li>Arbeitet mit dem Architekten zusammen, um den Change Management-Ansatz und die Kommunikationspläne zu definieren</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Experte für Change Management/Übernahme</strong></td>
<td align="left"><ul><li>Liefert Beiträge zu Übernahme- und Schulungsprozessen in der Entdeckungsphase</li>
<li>Nimmt am Workshop für Übernahmestrategie teil</li>
<li>Entwickelt die Übernahmestrategie und ist für diese verantwortlich</li>
<li>Entwickelt Kommunikationspläne und führt diese aus</li>
<li>Ist verantwortlich für die Bereitstellung von Schulungen für Endbenutzer</li>
<li>Sammelt Feedback und führt Umfragen durch</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Netzwerkleiter</strong></td>
<td align="left"><ul><li>Liefert Beiträge zum Netzwerkdesign in der Entdeckungsphase</li>
<li>Nimmt an der Planung während des Ausblick-Workshops teil</li>
<li>Koordiniert die Arbeit des Netzwerkteams während der Projektausführung</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Leiter der Sicherheit</strong></td>
<td align="left"><ul><li>Liefert Beiträge zu Übernahme- und Schulungsprozessen in der Entdeckungsphase</li>
<li>Nimmt an der Planung während des Ausblick-Workshops teil</li>
<li>Koordiniert die Arbeit des Sicherheitsteams während der Projektausführung</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Telefonie-Leiter</strong></td>
<td align="left"><ul><li>Liefert Beiträge zum Telefonie-Design in der Entdeckungsphase</li>
<li>Nimmt an der Planung während des Ausblick-Workshops teil</li>
<li>Koordiniert die Arbeit des Telefonie-Teams während der Projektausführung</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Desktop-Leiter</strong></td>
<td align="left"><ul><li>Liefert Beiträge zu Client- und Updateprozessen in der Entdeckungsphase</li>
<li>Nimmt an der Planung während des Ausblick-Workshops teil</li>
<li>Koordiniert die Arbeit des Desktop-Teams während der Projektausführung</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Support-/Helpdesk-Leiter</strong></td>
<td align="left"><ul><li>Liefert Beiträge zum operativen Modell und zum Support-Modell in der Entdeckungsphase</li>
<li>Nimmt an der Planung während des Ausblick-Workshops teil</li>
<li>Nimmt an der Planung des Support-Modells teil</li>
<li>Koordiniert die Arbeit des Support-Teams/der Ressourcen während der Projektausführung</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Repräsentanten der Geschäftseinheiten</strong></td>
<td align="left"><ul><li>Liefern Beiträge zur Endbenutzer-basierten Übernahme von Anleitungen und Begleitmaterialien</li>
<li>Tragen zu Geschäftsanwendungsfällen bei und überprüfen diese</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Bereitstellungsleiter</strong></td>
<td align="left"><ul><li>Stellt sicher, dass die Systemvoraussetzungen erfüllt sind</li>
<li>Leitet Kundenressourcen an, sich an der Vorbereitung und Bereitstellung von Aktivitäten in den einzelnen Phasen zu beteiligen</li>
<li>Nimmt an Besprechungen zur Überprüfung des Vorbereitungs- und Bereitstellungsstatus teil</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>IT-Administratoren</strong></td>
<td align="left"><ul><li>IT-Experten, die für die Unterstützung in der Testplanung und -ausführung verantwortlich sind</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Leiter des Kundendiensts</strong></td>
<td align="left"><ul><li>Ist für den reibungslosen Ablauf des Audiokonferenzdiensts verantwortlich</li>
<li>Leiter des Audiokonferenzdiensts</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Qualitätspionier</strong></td>
<td align="left"><ul><li>Trägt zur Verbesserung der Qualität, Verlässlichkeit und des Benutzerfeedbacks bei</li>
<li>Ermittelt Qualitätstrends und schafft Abhilfe bei Problemen mit den jeweiligen Teams</li>
<li>Ist verantwortlich für die Berichterstattung zwischen dem Lenkungsteam und dem Führungsstab</li>
<li>Erstellt Berichte über Qualität, Verlässlichkeit und Verbraucherstimmung über „Meinen Anruf bewerten“ und „Net Promoter Score“</li></ul></td>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_Tabelle 2: Matrixvorlage für Projektbeteiligte – Beispiel_


> [!NOTE]
> Die Beispieltabelle oben und nachfolgende Tabellen in diesem Dokument dienen als Vorlage. Der Hinweis „TBA“ (To Be Added, wird ergänzt) zeigt an, dass Sie hier Informationen als Teil Ihres Planungsprozesses eingeben müssen.



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Definieren von Zielen und wesentlichen Ergebnissen, wichtigen Erfolgsindikatoren und Risiken
--------------------------------------------------------------------

Bei der Zusammenkunft der Projektbeteiligten können Geschäftsanwendungsfälle, organisatorische Geltungsbereiche und Projektzeitschienen in Ziele und wesentliche Ergebnisse übersetzt werden, und die Kennzahlen des Projekterfolgs können in einer Liste mit den wichtigen Erfolgsindikatoren festgelegt werden.

Durch die Teilnahme aller Projektbeteiligten bei der Festlegung der Ziele und wesentlichen Ergebnissen sowie der wichtigen Erfolgsindikatoren wird das Verantwortungsbewusstsein geschärft, und eine Anpassung an die organisatorischen Geschäftsanforderungen wird sichergestellt.

Ziele und wesentliche Ergebnisse enthalten die Liste der Ziele, die zu Projektbeginn festgelegt wurden. Sie enthalten unter anderem messbare Ergebnisse auf Quartalsbasis. Diese Kernergebnisse werden monatlich ausgewertet, um den Status des gesamten Projekts zu verfolgen. Des Weiteren kann basierend auf dem Fortschritt eine Anpassung der Quartalspläne nach Bedarf vorgenommen werden.

<table>
<thead>
<tr class="header">
<th align="left"><p><strong>Vision</strong>: Steigern der Produktivität durch Erhöhung der Office 365-Ausgaben</p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Ziele</strong></td>
<td align="left"><strong>Wesentliche Resultate</strong></td>
<td align="left"><strong>Aufgabe</strong></td>
</tr>
<tr class="even">
<td align="left">Bereitstellen von Audiokonferenzen in Teams gegen Ende des Geschäftsjahres 2018</td>
<td align="left">1. Quartal des Geschäftsjahres 2018: Globale Bereitstellung von Audiokonferenzen in Teams</td>
<td align="left"><p>Ausblick</p>
<ul><li>Erfolgsplan erstellen</li>
<li>Detaillierten Plan für die technische Implementierung erstellen</li></ul>
<p>Onboarding</p>
<ul><li>Erfolgsplan ausführen</li>
<li>Plan für die technische Implementierung ausführen</li></ul></td>
</tr>
<tr class="odd">
<td align="left">Den Legacy-PSTN-Konferenzdienst zur Mitte des Finanzjahres 2018 deaktivieren</td>
<td align="left">2. Quartal des Finanzjahres 2018: Den Legacy-PSTN-Konferenzdienst deaktivieren</td>
<td align="left"><p>Höhere Wertschöpfung erzielen</p>
<ul><li>Benutzerengagement verstärken und Übernahme vorantreiben</li>
<li>Veränderungen vorbereiten und verwalten</li>
<li>Erfolg messen und teilen und Durchlauf beschleunigen</li></ul></td>
</tr>
</tbody>
</table>

_Tabelle 3: Ziele und wesentliche Ergebnisse – Beispiel_


Mit den wichtigen Erfolgsindikatoren werden die Qualität und der Erfolg der Kernergebnisse gemessen, und sie vervollständigen den binären Charakter von Zielen und wesentlichen Ergebnissen (erreicht oder nicht erreicht) durch detaillierte Aufschlüsselung von guten bzw. schlechten Ergebnissen. Bei der Definition der wichtigen Erfolgsindikatoren empfehlen wir, „spezifische, messbare, zuweisbare, realistische, zeitbezogene“ und INTELLIGENTE Kriterien zugrunde zu legen.

<table>
<thead>
<tr class="header">
<th align="left">Typ</th>
<th align="left"><p>Fragen zu den wichtigen Erfolgsindikatoren &amp;</p>
<p>Kriterien</p></th>
<th align="left">Messmethode</th>
<th align="left">Erfolgskriterien</th>
<th align="left">Bemessungszeitpunkt</th>
<th align="left">Verantwortlich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Verwendung/Übernahme</strong></td>
<td align="left">Anrufqualität entspricht der vorherigen Lösung oder übertrifft diese</td>
<td align="left">Umfrage</td>
<td align="left">Zustimmung oder starke Zustimmung bei 80 % der Benutzer</td>
<td align="left">Nach der Aktivierung und vierteljährlich</td>
<td align="left">IT-Team</td>
</tr>
<tr class="even">
<td align="left"><strong>Verwendung/Übernahme</strong></td>
<td align="left">Teams hat den Kommunikationsprozess vereinfacht</td>
<td align="left">Umfrage</td>
<td align="left">Zustimmung oder starke Zustimmung bei 80 % der Benutzer</td>
<td align="left">Nach der Aktivierung und vierteljährlich</td>
<td align="left">Change Management-Team</td>
</tr>
<tr class="odd">
<td align="left"><strong>Verwendung/Übernahme</strong></td>
<td align="left">Aktive Verwendung der Lösung durch die Benutzer</td>
<td align="left">Office 365-Berichte, Anrufqualitäts-Dashboard</td>
<td align="left">80 % der Benutzer sind täglich aktiv</td>
<td align="left">Täglich</td>
<td align="left">Change Management-Team</td>
</tr>
<tr class="even">
<td align="left"><strong>Nutzung/Qualität</strong></td>
<td align="left">Prozentsatz der Anrufe/Konferenzen mit schlechter Qualität sollte verringert werden</td>
<td align="left">Anrufqualitäts-Dashboard</td>
<td align="left">&lt; 5 % Anrufe mit schlechter Qualität pro Monat</td>
<td align="left">Täglich</td>
<td align="left">IT-Team</td>
</tr>
<tr class="odd">
<td align="left"><strong>Nutzung/Support</strong></td>
<td align="left">Ich weiß, wo ich technischen Support erhalte</td>
<td align="left">Umfrage</td>
<td align="left">Zustimmung oder starke Zustimmung bei 90% der Benutzer</td>
<td align="left">Nach der Aktivierung und vierteljährlich</td>
<td align="left">Change Management-Team</td>
</tr>
<tr class="even">
<td align="left"><strong>Nutzung/Support</strong></td>
<td align="left">Ich bin zufrieden mit der Qualität des technischen Supports</td>
<td align="left">Umfrage</td>
<td align="left">Zustimmung oder starke Zustimmung bei 80 % der Benutzer</td>
<td align="left">Nach jedem Vorfall</td>
<td align="left">IT-Team</td>
</tr>
<tr class="odd">
<td align="left"><strong>Finanzen</strong></td>
<td align="left">Weniger Minuten mit Legacy-Konferenzlösung</td>
<td align="left">Finanzsystem</td>
<td align="left">Definierte Rendite erzielen</td>
<td align="left">Basierend auf Rendite</td>
<td align="left">Change Management-Team</td>
</tr>
</tbody>
</table>

_Tabelle 4: Wichtige Erfolgsindikatoren – Beispiel_


Als Teil dieser Übung müssen Sie Geschäftsrisiken sowie einen Risikominderungsplan für jedes erkannte Risiko definieren. Diese Informationen können in einem Risikoplan erfasst werden.

<table>
<thead>
<tr class="header">
<th align="left">Risiko</th>
<th align="left">Wahrscheinlichkeit</th>
<th align="left">Auswirkungen</th>
<th align="left">Gesamt</th>
<th align="left">Risikominderungsplan</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Bei der bevorstehenden Fusion werden bis zu 1.000 Personen dazukommen</td>
<td align="left">Hoch</td>
<td align="left">Hoch</td>
<td align="left">Hoch</td>
<td align="left"><p>Separate Ziele und wesentliche Ergebnisse mit eigenem Prozess (Ausblick, Onboarding und Wertschöpfung) für fusioniertes Unternehmen</p>
<p>Beziehen Sie diesen Prozess nicht in vorhandene Ziele und wesentliche Ergebnisse ein.</p></td>
</tr>
<tr class="even">
<td align="left">Die Portierung von Telefonnummern verzögert den Projektabschluss.</td>
<td align="left">Hoch</td>
<td align="left">Hoch</td>
<td align="left">Hoch</td>
<td align="left"><p>Bereiten Sie frühzeitig alle erforderlichen Informationen zur Unterstützung der Portierung von Telefonnummern vor (z. B. Kundendiensteintrag, Rechnungsdetails, schriftliche Vollmacht).</p>
<p>Passen Sie die Zeitschiene für das Projekt an, um die Dauer für die Portierung der Telefonnummern zu berücksichtigen.</p>
<p>Teilen Sie den externen Teilnehmern die neuen Einwahlkonferenznummern mit.</p></td>
</tr>
<tr class="odd">
<td align="left">Geplante Umgestaltung des Netzwerks</td>
<td align="left">Hoch</td>
<td align="left">Mittel</td>
<td align="left">Mittel</td>
<td align="left">Führen Sie vor der Implementierung von Teams als moderne Plattform für Kommunikation und Zusammenarbeit eine Auswertung der Netzwerkbereitschaft für Websites durch, die im Geltungsbereich des Projekts liegen.</td>
</tr>
</tbody>
</table>

_Tabelle 5: Risikoplan – Beispiel_


<a name="assess-environment-and-evaluate-adoption-readiness"></a>Bewerten der Umgebung und Überprüfen der Übernahmebereitschaft
--------------------------------------------------

Um die gewünschten Ziele und wesentlichen Ergebnisse zu erreichen, müssen Sie möglicherweise die allgemeine Architektur der Lösung definieren. Sie müssen Ihre Umgebung sehr gründlich erkunden, um alle Aspekte der IT- und Telefonie-Infrastruktur, des Netzwerks und des Betriebs auswerten zu können.

Alle Angelegenheiten bezüglich Endbenutzer-Computing wie die Auswertung der einsatzfähigen PCs und Mobilgeräten zwecks Unterstützung von Audiokonferenz-Geschäftsanwendungsfällen – von Hardwareanforderungen bis Softwareanforderungen – sind Teil der Erkundung der Umgebung.

Bei der Erkundung der Umgebung kann auch festgestellt werden, ob es Anforderungen für die [Portierung von Telefonnummern nach Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e) gibt. Dies hilft Ihrer Organisation, den Projektplan entsprechend anzupassen und die für die Nummernportierung notwendigen Informationen bereitzustellen. Sie können die Umgebung erkunden, indem Sie den folgenden [Fragebogen](https://go.microsoft.com/fwlink/?linkid=858995) ausfüllen.

Bei der Erkundung der Umgebung muss die Bereitschaft des Netzwerks bewertet werden, um sicherzustellen, dass das Netzwerk in der Lage ist, die Implementierung des Audiokonferenzdiensts zu unterstützen.

Die Netzwerkbereitschaft zur Unterstützung des Audiokonferenzdiensts kann durch die durch die Erkundung des Netzwerks gesammelten Informationen ermittelt werden. Diese Informationen umfassen Details zur Internetkonnektivität und WAN-Topologie, Websitelinks, verfügbare Bandbreite und Personenanalysedaten, die mit dem [My Advisor Network Planner-Tool](https://go.microsoft.com/fwlink/?linkid=858999) in eine erwartete Nutzung der einzelnen Arbeitsauslastungen übersetzt werden können. Um die Netzwerkbereitschaft noch genauer zu ermitteln, kann eine Simulation von Mediendatenverkehr in Echtzeit mit den von [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) oder [Partnern von Network Readiness Assessment-Tools](https://go.microsoft.com/fwlink/?linkid=859003) bereitgestellten Lösungen durchgeführt werden.

Die Ergebnisse der Auswertung der Netzwerkbereitschaft zeichnen ein klares Bild der für eine erfolgreiche Implementierung der Audiokonferenzlösung erforderlichen Netzwerkoptimierung sowie Verbesserungsmaßnahmen.

Die Übernahmebereitschaft kann anhand der Ausführung einer Personenanalyse durchgeführt werden, um eine Liste der Personen in Ihrer Organisation zu erstellen, die für die Implementierung des Audiokonferenzdiensts in Frage kommen. Die Personenanalyse umfasst die Ermittlung weiterer Peripheriegeräte und sonstigen Geräten, die für die Erzielung der gewünschten Geschäftsergebnisse erforderlich sind.

Zur Ausführung einer Personenanalyse können Sie einen Workshop durchführen, indem Sie die jeweiligen Projektbeteiligten einbeziehen und die Workshop-Folie [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) und die [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006) verwenden. Das Ergebnis des Personenanalyse-Workshops kann mit der Vorlage [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007) in einem Bericht zusammengefasst werden.


> [!NOTE]
> Obwohl die Discovery Questionnaire- und die Persona Analysis-Beispiele zunächst für Skype for Business Online geschrieben wurden, sind die meisten Inhalte auch auf Teams übertragbar. Sie können Punkte, die für Ihre Projektziele nicht relevant sind, gerne ändern oder entfernen.


Sie können die technischen Risiken als Teil einer Auswertung der Umgebung und Bewertung der Übernahmebereitschaft ermitteln und einen Plan zur Abhilfe für jedes erkannte Risiko entwickeln. Diese Informationen sollten als Teil des Risikoplans berücksichtigt werden.

<a name="map-operational-roles"></a>Zuordnen von operativen Rollen
---------------------

Die Planung der Ausführung und die Zusammenstellung des Teams, das den Audiokonferenzdienst ausführt, ist ein wichtiger Schritt, da die Ausführung beginnen muss, wenn die ersten Teilnehmer des Pilotprojekts aktiviert werden. Jedes zusammengestellte Team muss die angegebenen Aufgaben und Verantwortlichkeiten prüfen und diesen zustimmen und mit der Vorbereitung der Ausführung des Audiokonferenzdiensts beginnen. Die Vorbereitung kann Schulungen, die Bewertung der Bereitschaft, die Einbeziehung zusätzlicher Mitarbeiter oder die Verpflichtung von externen Anbietern zur Bereitstellung des Diensts umfassen.

<table>
<thead>
<tr class="header">
<th align="left">Operative Rolle</th>
<th align="left">Beschreibung</th>
<th align="left">Team</th>
<th align="left">Kontaktdetails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Leiter des Kundendiensts</td>
<td align="left">Diensteigentümer, Schnittstelle zu Geschäftsabteilungen, Strategie</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Aufgaben für Audiokonferenzen</td>
<td align="left">Tägliche Aufgaben, Verschieben/Hinzufügen/Ändern von Benutzer- und Gerätekonten, Überwachung</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Mandantenadministrator</td>
<td align="left">Ändern von mandantenweiten Einstellungen, Aktivieren von neuen Funktionen</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Helpdesk</td>
<td align="left">Support-Schnittstelle für Endbenutzer</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Netzwerkaufgaben</td>
<td align="left">Ausführung von LAN, WAN, WLAN und Internetzugriff</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Client- &amp; Endgeräte-Team</td>
<td align="left">Verwalten von Desktopbereitstellungen</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Ermitteln von Aufgaben</td>
<td align="left">Verwalten der Identitätsinfrastruktur (AD, ADFS, Azure AD)</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Übernahme/Change Management</td>
<td align="left">Sensibilisierung, Schulung und Übernahme für die Lösung</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Exchange-Aufgaben</td>
<td align="left">Verwalten der Exchange-Umgebung</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_Tabelle 6: Zuordnung der operativen Rolle – Beispiel_


Um die detailliertere Zuordnung der operativen Rollen zu vereinfachen (einschließlich der mit jeder operativen Rolle verbundenen Aufgaben), können Sie das [Operational Role Mapping Workbook](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) verwenden, um die Details zu erfassen, die Ihnen einen Überblick über die Rollen und Verantwortlichkeiten für die Unterstützung des Audiokonferenzdiensts bieten.

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

Planen von Audiokonferenzen in Teams  <a name="Planning_AudioConferencing"> </a>
========================================

Um die Implementierung von Audiokonferenzen in Teams zu planen, müssen Sie frühzeitig eine Reihe von Entscheidungen treffen, um Ihre Organisation auf die Implementierung einer Lösung besser vorzubereiten, die die Geschäfsanforderungen erfüllen muss. Diese Entscheidungen werden in einem Plan zur technischen Implementierung dokumentiert.

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a>Verfügbarkeit von Audiokonferenzen

Audiokonferenzen sind in diesen [Ländern und Regionen](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US) verfügbar.


> [!IMPORTANT]
> Aufgrund von rechtlichen Beschränkungen muss der Vertrag für Office 365-Abonnements aus den Ländern und Regionen stammen, die vom Audiokonferenzdienst abgedeckt werden, damit Audiokonferenzen in multinationalen Organisationen verfügbar sind.

Wenn die Nutzung des Audiokonferenzdiensts durch Ihre Organisation bestätigt ist, erstellen Sie eine Liste der Benutzerstandorte oder Niederlassungen, in denen der Audiokonferenzdienst basierend auf der in der Liste verfügbaren Ländern und Regionen implementiert wird.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Entscheidungspunkte</td>
<td align="left"><p>Entscheiden Sie, an welchen Benutzerstandorten oder in welchen Niederlassungen der Audiokonferenzdienst implementiert wird.</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Nächste Schritte</td>
<td align="left"><p>Dokumentieren Sie die Benutzerstandorte oder Niederlassungen, die für den Audiokonferenzdienst aktiviert werden.</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Niederlassung</th>
<th align="left">Standort</th>
<th align="left">PSTN-Konferenzdienst</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">One Epping Road</td>
<td align="left">Australien</td>
<td align="left">Audiokonferenzen</td>
</tr>
<tr class="even">
<td align="left">100 Cyberport Road</td>
<td align="left">Hong Kong SAR (香港特別行政區)</td>
<td align="left">Legacy-PSTN-Konferenz</td>
</tr>
<tr class="odd">
<td align="left">One Marina Boulevard</td>
<td align="left">Singapur</td>
<td align="left">Audiokonferenzen</td>
</tr>
<tr class="even">
<td align="left">32 London Bridge Street</td>
<td align="left">Vereinigtes Königreich</td>
<td align="left">Audiokonferenzen</td>
</tr>
<tr class="odd">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Frankreich</td>
<td align="left">Audiokonferenzen</td>
</tr>
</tbody>
</table>

_Tabelle 7: Aktivierungsliste für Audiokonferenzdienst-Standorte – Beispiel_


## <a name="licensing-for-audio-conferencing"></a>Lizenzierung für Audiokonferenzen

[Audiokonferenzlizenz](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US) (vormals Skype for Business PSTN-Konferenzlizenz) ist als Teil der Office 365 E5-Abonnementpläne oder als Add-On für 365 E1- oder Office 365 E3-Abonnementpläne verfügbar.

> [!NOTE]
> PSTN- oder Einwahlkonferenzen in Teams bieten keine Unterstützung für <sup>Drittanbieter</sup> von Audiokonferenzanbieter-Partnern (Audio Conferencing Provider, ACP). <br>Wenn Sie den PSTN-Konferenzdienst für Skype for Business bereits verwenden, können Sie unmittelbar die Vorteile des Audiokonferenzdiensts in Teams nutzen.

Um gebührenfreie Telefonnummern für Konferenzbrücken zur Verfügung zu stellen und ausgehende Konferenzanrufe für internationale Telefonnummern zu unterstützen, müssen Sie [Kommunikationsguthaben](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) für Ihre Organisation einrichten.


> [!IMPORTANT]
> Für einige Länder/Regionen gibt es nur gebührenfreie Telefonnummern für Konferenzbrücken. In diesem Fall ist die Verwendung von Kommunikationsguthaben verpflichtend, um die Einwahl für diese Länder/Regionen zu unterstützen.

Bei der Implementierung von Kommunikationsguthaben müssen Sie zunächst überlegen, wie hoch der anfängliche Betrag für das Guthaben sein soll. In der Dokumentation [Communications Credits](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) finden Sie eine Auflistung der empfohlenen Beträge.

Wenn sich Ihre Organisation für das automatische Auffüllen des Betrags entscheidet, finden Sie in der Dokumentation [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) ebenfalls eine Empfehlung dafür, wie hoch der niedrigste Betrag sein sollte, ab dem die automatische Auffüllung ausgelöst wird. Der Betrag für die automatische Auffüllung richtet sich nach der tatsächlichen Verwendung. Die Verwendung von Kommunikationsguthaben sollte immer überwacht werden, und der Auffüllungsbetrag muss dynamisch angepasst werden.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Entscheidungspunkte</td>
<td align="left"><ul><li>Wenn Ihre Organisation die erforderliche Lizenzen für Audiokonferenzen noch nicht erworben hat, können Sie überlegen, ob Sie vorhandene Office 365-Abonnements erweitern oder Add-Ons für Audiokonferenzen anschaffen möchten.</li>
<li>Entscheiden Sie, ob Kommunikationsguthaben für die Implementierung von Audiokonferenzen erforderlich sind. Wenn ja, legen Sie den anfänglichen Auffüllungsbetrag fest. Legen Sie zudem fest, wie hoch der niedrigste Betrag sein sollte, bei dem die automatische Auffüllung ausgelöst wird.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Nächste Schritte</td>
<td align="left"><ul><li>Listen Sie die Benutzer auf, denen eine Lizenz für Audiokonferenzen zugewiesen wird.</li>
<li>Dokumentieren Sie den Plan für Kommunikationsguthaben (anfänglicher Betrag und Betrag für die Auslösung der Auffüllung, Höhe des Betrags für die automatische Auffüllung).</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Benutzer</th>
<th align="left">Niederlassung</th>
<th align="left">Office 365-Lizenz</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E3, Add-On für Audiokonferenzen</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E3, Add-On für Audiokonferenzen</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E3, Add-On für Audiokonferenzen</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3, Add-On für Audiokonferenzen</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3, Add-On für Audiokonferenzen</td>
</tr>
</tbody>
</table>

_Tabelle 8: Lizenzzuweisungsliste für Besprechungsorganisatoren von Audiokonferenzen – Beispiel_

<table>
<thead>
<tr class="header">
<th align="left">Anfangsbetrag</th>
<td align="left">1.000 US-Dollar</td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left">Betrag für die Auslösung der Auffüllung</th>
<td align="left">400 US-Dollar</td>
</tr>
<tr class="header">
<th align="left">Höhe des Betrags für die automatische Auffüllung</th>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_Tabelle 9: Zahlen für die Planung von Kommunikationsguthaben – Beispiel_


## <a name="conference-bridge-phone-numbers"></a>Telefonnummern für Konferenzbrücken

Der Audiokonferenzdienst in Office 365 umfasst:

-   Mehrere Typen von Telefonnummern für Konferenzbrücken (gebührenpflichtig und gebührenfrei)

-   Mehrere Kategorien der Telefonnummer (dediziert oder freigegeben)

-   Unterstützung für mehrere Sprachen für die Konferenzbrücke (primär oder sekundär)

-   Eine Standardtelefonnummer für den Mandanten.

Eine vollständige Beschreibung der enthaltenen Funktionen finden Sie unter [Einrichten von Einwahl- oder PSTN-Konferenzen für Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) und [Telefonnummern für Einwahlkonferenzen](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**

> [!NOTE]
> Dedizierte Telefonnummern für Konferenzbrücken werden basierend auf der Anzahl der anwendbaren Lizenzen auf die Telefonnummern angerechnet, die pro Mandant angefordert werden können. Erläuterungen hierzu erhalten Sie unter [Erste Schritte mit Skype for Business-Servicenummern](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734). Für gebührenfreie Telefonnummern für Konferenzbrücken ist Kommunikationsguthaben erforderlich.

Vorhandene Telefonnummern für Konferenzbrücken, die in den Audiokonferenzdienst übertragen werden müssen, und unter der Voraussetzung, dass diese die landespezifischen Anforderungen erfüllen, können nach Microsoft portiert werden.


> [!NOTE]
> Die Komplexität der Portierung von Telefonnummern nach Microsoft richtet sich sehr stark nach den jeweiligen Ländern oder Regionen, Netzbetreibern, der Anzahl der beteiligten Verbindungen und vielen anderen Faktoren. Informationen zur Portierung von Telefonnummern finden Sie im [Handbuch zur Portierung von Telefonnummern](https://go.microsoft.com/fwlink/?linkid=859011).

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

Weitere Details zur Portierung von Telefonnummern zum Audiokonferenzdienst finden Sie unter [Portierung von Telefonnummern nach Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Entscheidungspunkte</td>
<td align="left"><ul><li>Wählen Sie aus, ob Ihre Organisation dedizierte Telefonnummern für Konferenzbrücken benötigt.</li>
<li>Entscheiden Sie, wie die dedizierten Telefonnummern für Konferenzbrücken für die jeweiligen Benutzerstandorte oder Niederlassungen für die Implementierung von Audiokonferenzen abgerufen werden sollen (über Microsoft oder anhand der Portierung von vorhandenen Telefonnummern).</li>
<li>Wenn Sie sich für Microsoft entscheiden, wählen Sie die Methode zum Abrufen von Telefonnummern (Formulareingabe oder automatisch) für die jeweiligen Benutzerstandorte oder Niederlassungen für die Implementierung von Audiokonferenzen aus.</li>
<li>Wählen Sie die Spracheinstellungen für alle dedizierten Telefonnummern für Konferenzbrücken aus.</li>
<li>Wählen Sie die Standardtelefonnummer für Konferenzbrücken für den Mandanten aus.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Nächste Schritte</td>
<td align="left"><ul><li>Dokumentieren Sie den Masterplan für den Erwerb von Telefonnummern mit Details darüber, wie die Telefonnummern an jedem einzelnen Benutzerstandort oder jeder einzelnen Niederlassung für die Implementierung von Audiokonferenzen abgerufen werden.</li>
<li>Falls anwendbar, füllen Sie für jeden Standort oder jede Niederlassung das Formular <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">für die Anforderung neuer Telefonnummern</a> aus.</li>
<li>Wenn Sie vorhandene Telefonnummern portieren möchten, können Sie diesen Vorgang mit Unterstützung des <a href="https://go.microsoft.com/fwlink/?linkid=859011">Handbuchs zur Portierung von Telefonnummern</a> planen und die zeitgerechte Implementierung des Audiokonferenzdiensts entsprechend anpassen.</li>
<li>Dokumentieren Sie die detaillierten Konfigurationen der Telefonnummern für Konferenzbrücken (freigegebene und dedizierte Telefonnummern für Konferenzbrücken, Spracheinstellungen für jede dedizierte Telefonnummer für Konferenzbrücken, standardmäßige Telefonnummer für Konferenzbrücken für den Mandanten).</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Niederlassung</th>
<th align="left">Anschaffung der Brückennummer und Brückentyp</th>
<th align="left">Brückennummer</th>
<th align="left">Brückensprache</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">One Epping Road</td>
<td align="left">Neu anschaffen, dediziert</td>
<td align="left">TBA</td>
<td align="left">Englisch (Australien)</td>
</tr>
<tr class="even">
<td align="left">One Marina Boulevard</td>
<td align="left">Neu anschaffen, freigegeben</td>
<td align="left">TBA</td>
<td align="left">Englisch (Vereinigte Staaten), Chinesisch (vereinfacht)</td>
</tr>
<tr class="odd">
<td align="left">32 London Bridge Street</td>
<td align="left">Port vorhanden, dediziert</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">Englisch (Vereinigtes Königreich)</td>
</tr>
<tr class="even">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Neu anschaffen, dediziert</td>
<td align="left">TBA</td>
<td align="left">Französisch (Frankreich), Englisch (Vereinigtes Königreich)</td>
</tr>
</tbody>
</table>

_Tabelle 10: Beispiel der Details einer Konferenzbrücke_


> [!NOTE]
> Die Beispieltabelle oben und nachfolgende Tabellen in diesem Dokument dienen als Vorlage. Der Hinweis „TBA“ (To Be Added, wird ergänzt) zeigt an, dass Sie hier Informationen als Teil Ihres Planungsprozesses eingeben müssen.

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
> Diese mit Kosten verbundenen Steuerelemente sind derzeit nur für Preview-Kunden verfügbar. Über die Seite [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013) können Sie Ihre Organisation für das Preview-Programm registrieren.

Mit diesen Steuerelementen können Sie entscheiden, ob Besprechungsorganisatoren gebührenfreie Telefonnummern für Konferenzbrücken für die von ihnen organisierten Besprechungen zur Verfügung stellen können, und ob sie steuern können, ob Teilnehmer Anrufe aus den von ihnen organisierten Besprechungen heraus tätigen können. Die Steuerungsebene rangiert hierbei vom Nichtzulassen von ausgehenden Anrufen, Zulassen von ausgehenden Anrufen an Inlandsnummern bis zum Zulassen von ausgehenden Anrufen an Inlands- und Auslandsnummern.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Entscheidungspunkte</td>
<td align="left"><ul><li>Entscheiden Sie, ob die Organisation Benachrichtigungen über Zu- und Abgänge benötigt. Wenn ja, wählen Sie den zu implementierenden Benachrichtigungstyp (Signaltöne, Telefonnummer, aufgezeichneter Name) aus.</li>
<li>Legen Sie die PIN-Länge für Audiokonferenzen in Übereinstimmung mit den Sicherheitsanforderungen Ihrer Organisation fest.</li>
<li>Legen Sie fest, ob die Organisation die mit dem Audiokonferenzdienst verbundene Kommunikation der Endbenutzer steuern möchte.</li>
<li>Wählen Sie die Telefonnummern für Konferenzbrücken aus, die jedem Besprechungsorganisator zugewiesen werden.</li>
<li>Legen Sie fest, ob einige Besprechungsorganisatoren in die Lage versetzt werden sollen, gebührenfreie Telefonnummern für Konferenzbrücken in Ihren Besprechungen zu verwenden.</li>
<li>Legen Sie fest, ob einige Besprechungsorganisatoren in die Lage versetzt werden sollen, nicht authentifizierten Anrufern zu erlauben, eine Besprechung zu starten.</li>
<li>Legen Sie fest, ob für einige Besprechungsorganisatoren die ausgehenden Anrufe gesteuert werden sollen.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Nächste Schritte</td>
<td align="left"><ul><li>Dokumentieren Sie die detaillierten Konferenzbrückeneinstellungen (Benachrichtigungen über Zu- und Abgänge, PIN-Länge, E-Mail-Benachrichtigung über Konfigurationsänderungen).</li>
<li>Dokumentieren Sie die Telefonnummern für Konferenzbrücken, die jedem Besprechungsorganisator zugewiesen werden, und die entsprechende Einstellung, um die Richtlinie für nicht authentifizierte Anrufer zu steuern, sowie Steuerelemente für gebührenfreie und ausgehende Anrufe.</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>Benachrichtigungen über Zu- und Abgänge in Besprechungen aktivieren</strong></td>
<td align="left">Aktiviert</td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><strong>Ankündigungstyp für Zu- und Abgänge</strong></td>
<td align="left">Signaltöne</td>
</tr>
<tr class="header">
<td align="left"><strong>Anrufer fragen, ob ihr Name vor der Teilnahme an der Besprechung aufgezeichnet werden kann</strong></td>
<td align="left">Deaktiviert</td>
</tr>
<tr class="header">
<td align="left"><strong>PIN-Länge</strong></td>
<td align="left">5</td>
</tr>
<tr class="header">
<td align="left"><strong>Es werden automatisch E-Mails an den Benutzer gesendet, wenn sich die Einwahleinstellungen ändern</strong></td>
<td align="left">Deaktiviert</td>
</tr>
</tbody>
</table>

_Tabelle 11: Einstellungen einer Konferenzbrücke – Beispiel_


<table>
<thead>
<tr class="header">
<th align="left">Benutzer</th>
<th align="left">Niederlassung</th>
<th align="left">Gebührenpflichtige Standardnummer</th>
<th align="left">Gebührenfreie Standardnummer</th>
<th align="left">Gebührenfreie Nummer zulassen</th>
<th align="left">Nicht authentifizierte Anrufer umgehen Wartebereich</th>
<th align="left">Konferenzauswahl</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Ja</td>
<td align="left">Aktiviert</td>
<td align="left">In- und Auslandsanrufe</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Nein</td>
<td align="left">Deaktiviert</td>
<td align="left">Nicht zulässig</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Nein</td>
<td align="left">Deaktiviert</td>
<td align="left">Nicht zulässig</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Ja</td>
<td align="left">Deaktiviert</td>
<td align="left">Inlandsanruf</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Ja</td>
<td align="left">Aktiviert</td>
<td align="left">Inlandsanruf</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Ja</td>
<td align="left">Aktiviert</td>
<td align="left">Inlandsanruf</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">Ja</td>
<td align="left">Aktiviert</td>
<td align="left">Nicht zulässig</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">Ja</td>
<td align="left">Deaktiviert</td>
<td align="left">Nicht zulässig</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">Ja</td>
<td align="left">Deaktiviert</td>
<td align="left">Nicht zulässig</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Nein</td>
<td align="left">Deaktiviert</td>
<td align="left">Inlandsanruf</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Ja</td>
<td align="left">Aktiviert</td>
<td align="left">In- und Auslandsanrufe</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Nein</td>
<td align="left">Deaktiviert</td>
<td align="left">Inlandsanruf</td>
</tr>
</tbody>
</table>

_Tabelle 12: Zuweisungen der Einstellungen für Konferenzbrücke – Beispiel_


## <a name="dial-plans"></a>Wählpläne

Ein [Wählplan](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) (eine Telefonsystemfunktion von Office 365) ist eine Gruppe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise das Format [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) übersetzt, um Anrufe zu autorisieren und weiterzuleiten. Der Audiokonferenzdienst nutzt dieselben Funktionen wie das Telefonsystem, um gewählte Telefonnummern in Szenarien für die Konferenzauswahl zu übersetzen.

Mit einem Wählplan können Benutzer Telefonnummern so wählen, wie sie es gewöhnt sind. Zum Beispiel müssen sie bei Ortsgesprächen keine Vorwahl wählen, bei Inlandsanrufen keine Landeskennzahl wählen, und sie können sogar Kurzwahlnummern für ausgehende Anrufe in Konferenzen verwenden.

Innerhalb der Telefonsystemfunktion in Office 36 gibt es zwei Arten von Wählplänen:

-   **Dienstwählplan**. Dies ist der Standardwählplan, der auf einem Office 365-Verwendungsstandort basiert und nicht geändert werden kann.

<!-- -->

-   **Mandantenwählplan**. Dies ist ein anpassbarer Wählplan innerhalb eines Mandanten, der wiederum zwei Typen umfasst:

    -   **Globaler Wählplan für Mandanten**: Der Wählplan gilt für alle Benutzer innerhalb des Mandanten.

    -   **Wählplan für Mandantenbenutzer**: Der Wählplan gilt nur für bestimmte Benutzer.


> [!NOTE]
> Weitere Details und Beispiele finden Sie in der Dokumentation [Office 365 Calling Plan dial plans](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) (Office 365-Wählpläne).

Der den Benutzern zugewiesene wirksame Wählplan stellt eine Kombination aus dem Dienstwählplan (basierend auf dem Office 365-Verwendungsstandort des Benutzers) und dem Mandantenwählplan (entweder globaler Wählplan für Mandanten oder Wählplan für Mandantenbenutzer) dar.

![Die Tabelle zeigt drei Kombinationen aus Dienst- und Mandantenwählplänen.](media/audio_conferencing_image8.png)

Normalisierungsregeln können maximal 25 Regeln in jedem Mandantenwählplan enthalten. Eine Duplizierung von bereits als Teil des Dienstwählplans vorhandenen Normalisierungsregeln sollte daher vermieden werden.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Entscheidungspunkte</td>
<td align="left"><ul><li>Legen Sie fest, ob Ihre Organisation angepasste Wählpläne (Geschäftsanforderungen, Übernahmeanforderungen usw.) benötigt.</li>
<li>Legen Sie (falls anwendbar) den Gültigkeitsbereich für den Mandantenwählplan (globaler Wählplan für Mandanten oder Wählplan für Mandantenbenutzer) fest, um die Anforderungen für angepasste Wählpläne zu erfüllen.</li>
<li>Legen Sie (falls anwendbar) die Mandantenwählpläne fest, die zur Unterstützung von Benutzerstandorten oder Niederlassungen für die Implementierung von Audiokonferenzen erstellt wird.</li>
<li>Legen Sie (falls anwendbar) fest, welche Benutzer einen angepassten Wählplan erfordern, und wählen Sie den jedem Benutzer zuzuweisenden Mandantenwählplan aus.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Nächste Schritte</td>
<td align="left"><ul><li>Dokumentieren Sie die angepassten Wählpläne und die zugehörigen Normalisierungsregeln, die als Teil der Implementierung von Audiokonferenzen konfiguriert werden.</li>
<li>Dokumentieren Sie die Benutzer, denen ein angepasster Wählplan zugewiesen wird, und die den Mandantenwählplan für jeden einzelnen Benutzer.</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Name/Beschreibung des Mandantenwählplans</th>
<th align="left">Name/Beschreibung der Normalisierungsregeln</th>
<th align="left">Muster</th>
<th align="left">Übersetzung</th>
<th align="left">IsInternalExtension</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AU-NSW-NorthRyde-OER</strong></p>
<p><em>One Epping Road North Ryde, NSW, Wählplan für Australien</em></p></td>
<td align="left"><p><strong>AU-NSW-NorthRyde-OER-Internal</strong></p>
<p><em>Interne Nummer (x7000 - x7999) für One Epping Road-Niederlassung, North Ryde, NSW, Australien</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+6125550$1</td>
<td align="left">Wahr</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-NSW-Local</strong></p>
<p><em>Normalisierung für lokale Nummern für NSW, Australien</em></p></td>
<td align="left">^([2-9]\d{7})$</td>
<td align="left">+612$1</td>
<td align="left">Falsch</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>AU-TollFree</strong></p>
<p><em>Normalisierung für gebührenfreie Nummern für Australien</em></p></td>
<td align="left">^(1[38]\d{4,8})\d*$</td>
<td align="left">+61$1</td>
<td align="left">Falsch</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-Service</strong></p>
<p><em>Normalisierung für Servicenummern für Australien</em></p></td>
<td align="left">^(000|1[0125]\d{1,8})$</td>
<td align="left">$1</td>
<td align="left">Falsch</td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SG-Singapore-OMB</strong></p>
<p><em>OMB Singapore, Wählplan für Singapur</em></p></td>
<td align="left"><p><strong>SG-OMB-Internal</strong></p>
<p><em>Interne Nummer (x8000 – x8999) für OMB-Niederlassung, Singapur</em></p></td>
<td align="left">^(8\d{3})$</td>
<td align="left">+656888$1</td>
<td align="left">Wahr</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>SG-TollFree</strong></p>
<p><em>Normalisierung für gebührenfreie Nummern für Singapur</em></p></td>
<td align="left">^(1?800\d{7})\d*$</td>
<td align="left">+65$1</td>
<td align="left">Falsch</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>SG-Service</strong></p>
<p><em>Normalisierung für Servicenummern für Singapur</em></p></td>
<td align="left">^(1\d{3,4}|9\d{2})$</td>
<td align="left">$1</td>
<td align="left">Falsch</td>
</tr>
<tr class="even">
<td align="left"><p><strong>FR-Paris-Issy-39qdPR</strong></p>
<p><em>39 quai du Président Roosevelt Issy-les-Moulineaux, Wählplan für Frankreich</em></p></td>
<td align="left"><p><strong>FR-39qdPR-Internal</strong></p>
<p><em>Interne Nummer (x7000 – x7999) für 39 quai du Président Roosevelt-Niederlassung, Issy-les-Moulineaux, Frankreich</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+3319999$1</td>
<td align="left">Wahr</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>FR-TollFree</strong></p>
<p><em>Normalisierung für gebührenfreie Nummern für Frankreich</em></p></td>
<td align="left">^0?(80\d{7})\d*$</td>
<td align="left">+33$1</td>
<td align="left">Falsch</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>FR-Service</strong></p>
<p><em>Normalisierung für Servicenummern für Frankreich</em></p></td>
<td align="left"><p>^(1\d{1,2}|11[68]\d{3}|</p>
<p>10\d{2}|3\d{3})$</p></td>
<td align="left">$1</td>
<td align="left">Falsch</td>
</tr>
</tbody>
</table>

_Tabelle 13: Mandantenwählpläne – Beispiel_


<table>
<thead>
<tr class="header">
<th align="left">Benutzer</th>
<th align="left">Niederlassung</th>
<th align="left">Typ des Wählplans</th>
<th align="left">Name des Wählplans</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">Mandantenwählplan</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">Mandantenwählplan</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">Mandantenwählplan</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Mandantenwählplan</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Mandantenwählplan</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Mandantenwählplan</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Dienstwählplan</td>
<td align="left">n/v</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Dienstwählplan</td>
<td align="left">n/v</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Dienstwählplan</td>
<td align="left">n/v</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Mandantenwählplan</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Mandantenwählplan</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Mandantenwählplan</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
</tbody>
</table>

_Tabelle 14: Wählplanzuweisungen – Beispiel_


## <a name="microsoft-teams-configurations"></a>Microsoft Teams-Konfigurationen

Da der Audiokonferenzdienst nur für geplante Besprechungen verfügbar ist, müssen Konfigurationen auf Mandantenebene aktiviert werden, die die Planung von Besprechungen (private und Kanalbesprechungen) steuern.


> [!NOTE]
> Wenn Ihre Organisation Compliance-Anforderungen erfüllen muss, um sicherzustellen, dass alle Besprechungsdiskussionen gefunden werden können, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.<br><br>
> Wenn in einem anderen Anwendungsfall alle Besprechungen in der Organisation nur für <strong>eingeladene Benutzer</strong> sichtbar sein müssen, empfehlen wir Ihnen, die Funktion zum Planen von Besprechungen in <strong>Kanälen</strong> zu deaktivieren, um die Offenlegung von Informationen für nicht eingeladene Benutzer zu vermeiden.

Die als Konfigurationen auf Mandantenebene verfügbaren Einstellungen sind auf alle Benutzer in der Organisation anwendbar und wirken sich auf die gesamte Besprechungsplanung in Teams und nicht nur auf Teams-Besprechungen **mit** Audiokonferenzen aus.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Entscheidungspunkt</td>
<td align="left"><p>Legen Sie fest, ob es für die Organisation erforderlich ist, das Planen von privaten Besprechungen zu aktivieren oder zu deaktivieren.</p>
<p>Legen Sie fest, ob es für die Organisation erforderlich ist, das Planen von Kanalbesprechungen zu aktivieren oder zu deaktivieren.</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Nächste Schritte</td>
<td align="left"><p>Dokumentieren Sie die Konfigurationen für die Besprechungsplanung für Teams.</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>Lassen Sie das Planen von privaten Besprechungen zu</strong></td>
<td align="left">Aktiviert</td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><strong>Lassen Sie das Planen von Kanalbesprechungen zu</strong></td>
<td align="left">Deaktiviert</td>
</tr>
</tbody>
</table>

_Tabelle 15: Microsoft Teams-Besprechungskonfigurationen – Beispiel_


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

Nach Abschluss des Erfolgsplans und des Plans zur technischen Implementierung können Sie Ihrer Organisation jetzt die nächsten Schritte entlang des Office 365 Customer Journey unterbreiten.

<a name="onboard"></a>Onboarding
=======

*In Kürze verfügbar.*

<a name="drive-value"></a>Höhere Wertschöpfung erzielen
===========

*In Kürze verfügbar.*



### <a name="see-also"></a>Siehe auch
[Konfigurieren von Einwahl- oder PSTN-Konferenzen für Skype for Business](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
