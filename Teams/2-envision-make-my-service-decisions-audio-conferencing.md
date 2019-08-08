---
title: Treffen von Entscheidungen für den Audio-Konferenzdienst – Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Informieren Sie sich über Besprechungen, Lizenzierung und Verfügbarkeit, Konfigurieren von Einstellungen für Konferenz Brücken, erwerben oder übertragen von Telefonnummern und Auswählen von Mandanten Wählplänen.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0155788ef4ba99a350be0043847edd5e705b75b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240575"
---
# <a name="make-my-service-decisions"></a>Meine Dienst Entscheidungen treffen

Wenn Sie die technische Implementierung von Audiokonferenzen planen möchten, müssen Sie eine Reihe von Dienst Entscheidungen vorzeitig treffen, um Ihre Organisation besser auf die Implementierung einer Lösung vorzubereiten, die ihre definierten geschäftlichen Anforderungen erfüllt.

## <a name="audio-conferencing-in-teams"></a>Audiokonferenzen in Teams

Als Teil der Definition erforderlicher Audiokonferenzfunktionen in Microsoft Teams besteht einer der ersten Schritte darin, die aktuelle öffentliche Roadmap zu evaluieren, um Folgendes zu ermitteln:

-   Welche Audiokonferenz Features in Teams, die für Benutzer im Bereich bereitgestellt werden.

-   Voraussetzungen für die Benutzerfunktionalität für Audiokonferenzen in Teams.

-   Bestätigung, dass Audiokonferenzfunktionen in Teams, die in der neuesten öffentlichen Roadmap beschrieben sind, Ihre Benutzer-, Funktionalitäts-und Bereichsanforderungen innerhalb der Zeitachse Ihrer Bereitstellung erfüllen.

> [!NOTE]
> Die aktuelle Roadmap für Teams zur Identifizierung von Teams für Audiokonferenz-Features im Bereich für Ihre bereit <https://aka.ms/O365Roadmap>Stellung finden Sie unter.

## <a name="meetings-in-teams"></a>Besprechungen in Microsoft Teams

Teams bietet ihren Benutzern die Möglichkeit zum Planen und teilnehmen an Onlinebesprechungen mithilfe von HD-Video, VoIP (Voice over IP) und Optionen für PSTN-Einwahlkonferenzen.

Besprechungen können als private Besprechungen (nur eingeladene Parteien können teilnehmen) oder Kanal Besprechungen (für alle Benutzer, die Zugriff auf den Kanal haben) geplant werden, und Ihre Benutzer können auch spontane Besprechungen in Kanälen starten.

> [!NOTE]
> Weitere Informationen zu den Features von Besprechungen in Teams finden Sie in der [Microsoft 365-Roadmap](https://aka.ms/O365Roadmap).

Besprechungsteilnehmer können an Ihren Teambesprechungen teilnehmen, indem Sie sich über Festnetz-oder Mobilfunkanschlüsse in die gebührenpflichtige oder gebührenfreie Einwahlkonferenz Brücke einwählen. Darüber hinaus können Benutzer vom Audiokonferenzdienst die Funktion "anrufen" initiieren, damit Sie an einer Besprechung teilnehmen können, indem Sie die Konferenzbrücke anrufen lassen (nützlich, wenn die Datenverbindung nicht zuverlässig ist) oder Besprechungsorganisatoren eine Besprechung einladen lassen. Teilnehmer, indem Sie Ihre Telefone anrufen.

> [!IMPORTANT]
> Audiokonferenzen in Teams unterstützen keine Audiokonferenz-Anbieter von Drittanbietern (ACPS).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Verfügbarkeit von Audiokonferenzen

Bevor Sie die Implementierung von Audiokonferenzen in Teams planen, müssen Sie die Verfügbarkeit des Audiokonferenzdienst überprüfen, wie in der [Verfügbarkeit für Audiokonferenz-und Anrufpläne in Land und Region](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)beschrieben.

> [!IMPORTANT]
> Aufgrund rechtlicher Einschränkungen müssen Audiokonferenzen für multinationale Organisationen verfügbar sein, da der Vertrag für Office 365-Abonnements aus Ländern und Regionen stammen muss, in denen der Audiokonferenzdienst kommerziell verfügbar ist.

Nachdem Sie bestätigt haben, dass Ihre Organisation für den Audiokonferenzdienst berechtigt ist, kompilieren Sie die Liste der Benutzer Standorte oder-Büros, in denen Sie den Audiokonferenzdienst implementieren, basierend auf der Liste der verfügbaren Länder und Regionen.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Benutzer Standorte oder Offices den Audiokonferenzdienst implementieren sollen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer Standorte oder-Büros, die für den Audiokonferenzdienst aktiviert werden sollen.</li></ul>|

> [!TIP]
> Nachfolgend finden Sie ein Beispiel für eine Vorlage für eine Audiokonferenz-Website Aktivierung:
> 
> |Office   |Standort |PSTN-Konferenzdienst  |
> |---------|---------|---------|
> |One Epping Road|Australien|Audiokonferenzen|
> |100 Cyberport Road|Hong Kong SAR (香港特別行政區)|Legacy-PSTN-Konferenz|
> |One Marina Boulevard|Singapur|Audiokonferenzen|
> |32 London Bridge Street|Vereinigtes Königreich|Audiokonferenzen|
> |39 quai du Président Roosevelt|Frankreich|Audiokonferenzen|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Lizenzierung für Audiokonferenzen

Eine [Audiokonferenz-Lizenz](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) steht im Rahmen von Office 365 E5-Abonnement Plänen oder als Add-on-Service für Office 365 E1-oder Office 365 E3-Abonnement Pläne zur Verfügung.

> [!NOTE]
> PSTN-oder Einwahlkonferenzen in Teams unterstützen keine Audiokonferenz-Anbieter von Drittanbietern (ACPS).
> <br>Wenn Sie den PSTN-Konferenzdienst für Skype for Business bereits verwenden, können Sie unmittelbar die Vorteile des Audiokonferenzdiensts in Teams nutzen.

Wenn Sie gebührenfreie Konferenz Brücken-Telefonnummern bereitstellen und Konferenzanrufe an internationale Telefonnummern unterstützen möchten, müssen Sie für Ihre Organisation [Kommunikationsguthaben](what-are-communications-credits.md) einrichten.

> [!IMPORTANT]
> Einige Länder werden nur über gebührenfreie Telefonnummern für Konferenz Brücken gewartet. Zur Unterstützung der Einwahl in diesen Ländern müssen Sie Kommunikationsguthaben verwenden.

Die erste Überlegung bei der Implementierung von Kommunikationsguthaben ist die Entscheidung über die anfängliche Höhe des Guthabens, das Sie kaufen möchten. Wenn Ihre Organisation die Verwendung der automatischen Aufladefunktion auswählt, müssen Sie den Abzugsbetrag (niedrigster Betrag) und den Betrag für das automatische aufladen entscheiden. Ihre tatsächliche Nutzung bestimmt den Betrag für das automatische aufladen. Sie sollten die Nutzung ihrer Kommunikationsguthaben über einen Zeitraum überwachen und den aufladbaren Betrag nach Bedarf anpassen.

Weitere Informationen zu Kommunikationsguthaben finden Sie [hier](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Wenn Ihre Organisation die erforderliche Lizenzierung für Audiokonferenzen noch nicht erworben hat, entscheiden Sie, ob Sie Audiokonferenz-Lizenzen erwerben möchten, indem Sie vorhandene Office 365-Abonnements verstärken oder Audiokonferenz-Add-on-Lizenzen erwerben.</li><li>Entscheiden Sie, ob für Ihre Audiokonferenz-Implementierung Kommunikationsguthaben erforderlich sind. Wenn ja, legen Sie den anfänglichen Auffüllungsbetrag fest. Legen Sie zudem fest, wie hoch der niedrigste Betrag sein sollte, bei dem die automatische Auffüllung ausgelöst wird.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer, denen Audiokonferenz-Lizenzen zugewiesen werden sollen.</li><li>Dokumentieren des Plans für Kommunikations Kredite (Anfangsbetrag, Auslöse Betrag, Betrag für das automatische aufladen)</li></ul>|

> [!TIP]
> Mit dem folgenden Beispiel können Sie die Liste der Lizenz Aufgaben für Audiokonferenz-Benutzer dokumentieren.
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
> |Louis Lahr|32 London Bridge Street|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, Add-On für Audiokonferenzen|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, Add-On für Audiokonferenzen|

<br>

> [!TIP]
> Sie können Ihre Zahlen für die Planung des Guthabens für Kommunikationen so dokumentieren:
>
> |         |         |
> |---------|---------|
> |Anfangsbetrag|1.000 US-Dollar|
> |Betrag für die Auslösung der Auffüllung|400 US-Dollar|
> |Höhe des Betrags für die automatische Auffüllung|TBA|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>Telefonnummern für Konferenzbrücken

Der Audiokonferenzdienst in Office 365 umfasst:

-   Mehrere Arten von Telefonnummern für Konferenz Brücken (gebührenpflichtig und gebührenfrei)

-   Mehrere Kategorien von Telefonnummern für Konferenz Brücken (dediziert und freigegeben)

-   Unterstützung für mehrere Sprachen für die Konferenzbrücke (primär oder sekundär)

-   Eine Standardtelefonnummer für den Mandanten

> [!NOTE]
> Dedizierte Telefonnummern für Konferenz Brücken zählen auf die Grenze von Telefonnummern, die pro Mandant abhängig von der Anzahl der anwendbaren Lizenzen erworben werden können. Für gebührenfreie Telefonnummern für Konferenzbrücken ist Kommunikationsguthaben erforderlich.

Wenn Sie vorhandene Konferenz Brücken-Telefonnummern an den Audiokonferenzdienst übertragen müssen, vorausgesetzt, Sie erfüllen länderspezifische Anforderungen, können Sie diese vorhandenen Konferenz Brücken-Telefonnummern an Microsoft übertragen.

> [!NOTE]
> Die Komplexität der Übertragung von Telefonnummern an Microsoft variiert stark je nach Land oder Region, Netzbetreiber, Anzahl der beteiligten Schaltkreise und vielen anderen Faktoren, die dazu beitragen. Arbeiten Sie mit Ihrem aktuellen Anbieter zusammen, um zu untersuchen, wie lange dies wahrscheinlich dauert, um sicherzustellen, dass Sie den Prozess früh genug starten, um ihre Zeitpläne zu erfüllen.

Wenn Sie mehr über Telefonnummern für Konferenz Brücken erfahren möchten, lesen Sie die folgenden Artikel:

-   [Einrichten von Audiokonferenzen für Microsoft Teams](set-up-audio-conferencing-in-teams.md)

-   [Telefonnummern für Audiokonferenzen](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Abrufen von Diensttelefonnummern](getting-service-phone-numbers.md)

-   [Übertragen von Telefonnummern an Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Ihre Organisation dedizierte Telefonnummern für Konferenz Brücken benötigt.</li><li>Entscheiden Sie, wie die dedizierten Konferenz Brücken-Telefonnummern für die Benutzer Standorte oder Offices im Bereich der Audiokonferenz-Implementierung abgerufen werden (also von Microsoft beziehen oder vorhandene Telefonnummern übertragen).</li><li>Wenn Sie Sie von Microsoft erhalten möchten, entscheiden Sie sich für die Methode zur Verwendung (Formularübermittlung oder automatisiert) für Benutzer Standorte oder Offices, die für die Implementierung von Audiokonferenzen im Bereich der Audiokonferenz verwendet werden.</li><li>Entscheiden Sie, welche Spracheinstellungen für jede dedizierte Konferenzbrücke-Telefonnummer eingerichtet werden sollen.</li><li>Entscheiden Sie sich für die Telefonnummer des Mandanten als Standard Konferenzbrücke.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie den Masterplan für die Telefonnummern Akquisition, und erläutern Sie, wie Telefonnummern für die einzelnen Benutzer Standorte oder Office im Bereich der Audiokonferenz-Implementierung abgerufen werden.</li><li>Falls zutreffend, füllen Sie das neue Telefonnummern-Anforderungsformular aus – ein Formular für jeden Standort oder jede Niederlassung.</li><li>Dokumentieren Sie die detaillierten Telefonnummern Konfigurationen für Konferenz Brücken (freigegebene und dedizierte Konferenz Brücken-Telefonnummern, Spracheinstellungen für jede dedizierte Telefonnummer der Konferenzbrücke, Telefonnummer des Mandanten, Standard-Konferenzbrücke).</li></ul>|

Nachfolgend finden Sie ein Beispiel für eine Vorlage, die Sie zum Aufzeichnen von Details zur Konferenzbrücke verwenden können.

> [!TIP]
> Das folgende Beispiel zeigt eine Vorlage zum Erfassen der Details von Konferenzbrücken:
> 
> |Niederlassung   |Anschaffung der Brückennummer und Brückentyp |Brückennummer  |Brückensprache|
> |---------|---------|---------|---------|
> |One Epping Road|Neu anschaffen, dediziert|TBA|Englisch (Australien)|
> |One Marina Boulevard|Neu anschaffen, freigegeben|TBA|Englisch (Vereinigte Staaten), Chinesisch (vereinfacht)|
> |32 London Bridge Street|Port vorhanden, dediziert|+44 20 7946 0001|Englisch (Vereinigtes Königreich)|
> |39 quai du Président Roosevelt|Neu anschaffen, dediziert|TBA|Französisch (Frankreich), Englisch (Vereinigtes Königreich)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>Einstellungen der Konferenzbrücke

Wenn Sie die Benutzerfreundlichkeit weiter anpassen möchten, können Sie organisationsweite Optionen für die Teilnahme an Audiokonferenz-Besprechungen (Besprechungs-und Exit-Benachrichtigung und Aufzeichnung der Rufnummernanzeige), die PIN-Länge des Besprechungsorganisators und die e-Mail-Benachrichtigung konfigurieren:

-   Benachrichtigungen über Zu- und Abgänge in Besprechungen sind in Form eines aufgezeichneten Namens, einer Telefonnummer und Signaltönen verfügbar.

-   Die PIN-Länge ist mit 4 bis zwölf Ziffern konfigurierbar, wobei eine PIN standardmäßig aus 5 Ziffern besteht.

-   Benachrichtigungs-e-Mails, die bei der Aktivierung der Audiokonferenz-Lizenz oder einer anderen vom Administrator gesteuerten Änderung gesendet wurden, sind standardmäßig aktiviert. Sie können dieses Feature deaktivieren und die Benutzerkommunikation in Ihrer Organisation übernehmen.

Für Benutzer, denen eine Audiokonferenz-Lizenz zugewiesen ist, können die Standardgebühren/gebührenfreien Nummern, die in den Audiokonferenz-Koordinaten angezeigt werden, so konfiguriert werden, dass Sie Folgendes verwenden:

-   Die Standardeinstellung auf Mandantenebene.

-   Die automatisch zugewiesenen Telefonnummern für Konferenz Brücken.

-   Eine Konferenzbrücke Telefonnummern, die für jeden Benutzer manuell konfiguriert werden.

Benutzerspezifische Telefonnummern für Konferenz Brücken sind in der Regel in globalen oder bundesweiten Organisationen hilfreich, in denen Benutzer verteilt sind, und Sie müssen in ihren Besprechungseinladungen Ortsnummern als Standardtelefon Nummern für Konferenz Brücken angeben.

Teilnehmer, die aus unterschiedlichen Städten oder Übersee beitreten, können zusätzliche Nummern nachschlagen, die auf Mandantenebene konfiguriert sind, diese Zahlen werden aber nicht direkt in den Besprechungseinladungen angezeigt. Die Besprechungseinladungen stellen einen Link zur Verfügung, der Teilnehmer zur Seite " **Einwahlnummern für Teams** " führt, damit Sie die Telefonnummer der Konferenzbrücke nachschlagen können, die Ihrem Standort am nächsten ist.

Sie können auch konfigurieren, wie nicht authentifizierte Aufrufer von den einzelnen Besprechungsorganisatoren behandelt werden, und zwar unabhängig davon, ob der Besprechungsorganisator die Besprechung starten soll, bevor nicht authentifizierte Anrufer zugelassen werden können, oder nicht authentifizierten Anrufern das Starten einer Besprechung gestatten. .

Sie können auch zusätzliche Konfigurationen für jeden Benutzer anwenden, um die Verwendung von gebührenfreien Konferenz Brücken-Telefonnummern und die Einwahl aus einer Konferenz zu steuern.

> [!NOTE]
> Diese mit Kosten verbundenen Steuerelemente sind derzeit nur für Preview-Kunden verfügbar. Sie können Ihre Organisation im Vorschau Programm von https://www.skypepreview.comregistrieren.

Mit diesen Steuerelementen können Sie entscheiden, ob Besprechungsorganisatoren gebührenfreie Telefonnummern für Konferenz Brücken für Besprechungen bereitstellen können, die von Ihnen organisiert werden, und ob Teilnehmer die von Ihnen organisierten Besprechungen anrufen können. Die Anzahl der Wähl Steuerungen reicht davon ab, die Rufnummernanzeige vollständig zu verhindern, um nur Anrufe an inländische Rufnummern zu ermöglichen, um Anrufe an inländische und internationale Rufnummern zu ermöglichen.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Ihre Organisation Eingabe-und Exit-Benachrichtigungen erfordert, und – wenn ja – die Art der zu implementierenden Benachrichtigung (Töne, Telefonnummer oder aufgezeichneter Name).</li><li>Entscheiden Sie sich für die PIN-Länge der Audiokonferenz, die Ihren organisatorischen Sicherheitsanforderungen entspricht.</li><li>Entscheiden Sie, ob Ihre Organisation die Benutzerkommunikation in Verbindung mit dem Audio-Konferenzdienst übernehmen möchte.</li><li>Entscheiden Sie, welche Telefonnummern der Konferenzbrücke jedem Besprechungsorganisator zugewiesen werden sollen.</li><li>Entscheiden Sie, ob einige Besprechungsorganisatoren gebührenfreie Telefonnummern für Konferenz Brücken für Ihre Besprechungen verwenden müssen.</li><li>Entscheiden Sie, ob einige Besprechungsorganisatoren nicht authentifizierten Anrufern das Starten einer Besprechung gestatten müssen.</li><li>Entscheiden Sie, ob einige Besprechungsorganisatoren die Kontrolle über Konferenz Auswahlen benötigen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die detaillierten Konferenzbrückeneinstellungen (Benachrichtigungen über Zu- und Abgänge, PIN-Länge, E-Mail-Benachrichtigung über Konfigurationsänderungen).</li><li>Dokumentieren Sie die Telefonnummern der Konferenzbrücke, die jedem Besprechungsorganisator zugewiesen werden sollen, und die entsprechende Einstellung, um die Richtlinie für nicht authentifizierte Anrufer zu steuern, sowie gebührenfreie und Wahl Steuerelemente.</li></ul>|

> [!TIP]
> Ihre Einstellungen für die Konferenzbrücke können wie im folgenden Beispiel dokumentiert werden.
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
> Mithilfe des folgenden Beispiels können Sie die Zuordnungsliste der Konferenz Brücken Einstellungen für Audiokonferenz-Benutzer dokumentieren.
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
> |Louis Lahr|32 London Bridge Street|+44 20 7946 0001|TBA|Ja|Deaktiviert|Nicht zulässig|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|Nein|Deaktiviert|Inlandsanruf|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|Ja|Aktiviert|In- und Auslandsanrufe|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|Nein|Deaktiviert|Inlandsanruf|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Verwalten von Cloud-VoIP-Telefonnummern

Für die Implementierung von Audiokonferenzen können Sie wählen, ob Sie neue Telefonnummern erwerben oder vorhandene Telefonnummern übertragen/portieren möchten.

Wenn Sie es Benutzern ermöglichen möchten, Telefonnummern so zu wählen, wie Sie es gewohnt sind, beispielsweise das Auslassen von Ortsnetzen für Ortsgespräche, das Weglassen von Landesvorwahl für Inlandsanrufe oder die Verwendung von Kurzwahlnummern bei der Durchführung einer Konferenz Wahl, können Sie einen benutzerdefinierten Wählplan konfigurieren. und weisen Sie Sie Benutzern zu.

## <a name="acquire-new-telephone-numbers"></a>Neue Telefonnummern erwerben

Die beiden Arten von Telefonnummern in Microsoft Cloud Voice Solutions sind:

-   Abonnenten Nummern (Benutzer), die Benutzern in Ihrer Organisation zugewiesen werden können.

-   Dienstnummern, die als gebührenpflichtige und gebührenfreie Servicenummern zur Verfügung stehen, die eine höhere gleichzeitige Anrufkapazität als Teilnehmer Nummern aufweisen und Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden können.

Weitere Informationen zu diesen Arten von Telefonnummern finden Sie unter [verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Die Gesamtanzahl der Telefonnummern, die Sie erhalten können, hängt von den Telefonnummern Typen und der Anzahl der Lizenzen ab, die Sie Ihren Benutzern gekauft und zugewiesen haben.

Wenn es um Servicenummern geht, müssen Sie Ihre Audiokonferenz-Implementierung sorgfältig planen. Überprüfen Sie, ob Ihr Unternehmen dedizierte Telefonnummern für Konferenz Brücken benötigt. Wenn dies nicht der Fall ist, kann Ihre Organisation für die Verwendung von freigegebenen Konferenz Brücken-Telefonnummern entscheiden.

Weitere Informationen zur Gesamtanzahl der Telefonnummern, die Sie erhalten können, finden Sie unter [wie viele Telefonnummern können Sie erhalten?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Benutzer Standorte oder Büros neue Telefonnummern von Microsoft erwerben sollen.</li><li>Entscheiden Sie, welche Telefonnummern von Microsoft erworben werden sollen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer Standorte oder Niederlassungen, in denen neue Telefonnummern von Microsoft erworben werden.</li><li>Dokumentieren Sie die Art der Telefonnummern, die von Microsoft erworben werden sollen.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Übertragen vorhandener Telefonnummern

Wenn Ihre Organisation vorhandene Telefonnummern an Microsoft übertragen (oder portieren) möchte, können Sie dies tun, indem Sie eine Portierungs Auftragsanforderung an Microsoft übermitteln.

Sie können alle Ihre vorhandenen Telefonnummern gleichzeitig übertragen (Vollständiger Port) und – in einigen Märkten – eine Teilmenge ihrer vorhandenen Telefonnummern (teilweiser Port) übertragen. Ein partieller Port kann hilfreich sein, wenn Sie Ihre Einwahlkonferenz Brücke nur in den Audiokonferenzdienst verschieben möchten.

Eine einzelne Portierungs Reihenfolge kann die Telefonnummern nur an einen einzigen Telefonnummerntyp übertragen. Wenn Sie einige ihrer Telefonnummern als Teilnehmer Nummern und einige als Servicenummern übertragen müssen, empfehlen wir, dass Sie zuerst die Übertragung an Microsoft durchführen und dann die Konvertierung durchführen, sobald die Nummern innerhalb der Microsoft-Steuerung sind.

Wenn partieller Port unterstützt wird, können Sie alternativ mehrere Portanforderungen senden, eine Port Anforderung gleichzeitig. Dieser Alternative Ansatz verlängert jedoch ihren Vertrag mit Ihrem bestehenden Telekommunikationsdienstanbieter.

Das Portieren von Telefonnummern ist ein komplexes Thema und erfordert eine gründliche Planung, Koordination und angemessene Verwaltung der Erwartungen ihrer Stakeholder. Weitere Informationen finden Sie in den folgenden Artikeln:

-   [Übertragen von Telefonnummern an Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Übertragen von Telefonnummern – häufig gestellte Fragen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie sich für die Benutzer Standorte oder Offices, in denen vorhandene Telefonnummern an Microsoft übertragen werden.</li><li>Entscheiden Sie, welche Telefonnummern an Microsoft übertragen werden sollen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer Standorte oder Niederlassungen, an denen vorhandene Telefonnummern an Microsoft übertragen werden.</li><li>Dokumentieren Sie die Art der Telefonnummern, die an Microsoft übertragen werden sollen.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Wählpläne

Ein Wählplan in der Telefon System Funktion von Office 365 ist eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (in der Regel E. 164-Format) für die Anruf Autorisierung und das Anrufrouting übersetzt. Der Audiokonferenzdienst nutzt dieselben Funktionen, die vom Telefon System verwendet werden, um gewählte Telefonnummern in Szenarien für die Konferenz Auswahl zu übersetzen (zum Beispiel: einladen von Teilnehmern über PSTN und zurück wählen, "Anruf"-Funktion).

In der Telefon System Funktion von Office 365 gibt es zwei Arten von Wählplänen:

-   **Dienst Wähl Plan:** Dies ist der Standard-Wählplan, der auf Benutzer basierend auf dem Standort der Office 365-Nutzung angewendet wird und nicht geändert werden kann.

-   **Mandanten Wähl Plan:** Hierbei handelt es sich um einen anpassbaren Wählplan innerhalb eines Mandanten, der in zwei Arten unterteilt ist:

    -   **Mandanten – globaler Wählplan:** Die Wähleinstellungen, die für alle Benutzer im Mandanten gelten.

    -   **Mandanten-Benutzerwähleinstellungen:** Die Wähleinstellungen, die nur für bestimmte Benutzer gelten.

Der effektive Wählplan, der Benutzern zugewiesen ist, ist die Kombination aus dem Dienst Wählplan (basierend auf dem Office 365-Verwendungsstandort eines Benutzers) und dem Mandanten Wählplan (kann entweder Mandanten-globaler Wählplan oder Mandanten Wähl Plan sein).

![Tabelle zeigt drei Kombinationen von Wählplänen für Dienst-und Mandanten.] (media/audio_conferencing_image8.png "Tabelle zeigt drei Kombinationen von Wählplänen für Dienst-und Mandanten.")

> [!Important]
> In jedem Mandanten-Wählplan können maximal 25 Normalisierungsregeln vorhanden sein. Daher ist es wichtig, zu vermeiden, dass Normalisierungsregeln dupliziert werden, die bereits im Rahmen des Dienst Wählplans verfügbar sind.

Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Ihre Organisation angepasste Wählpläne erfordert (Geschäftsanforderungen, Adoptions Anforderungen usw.).</li><li>Falls zutreffend, entscheiden Sie über den Bereich der Mandanten Wähleinstellungen (Mandanten-Global oder Mandanten Benutzer), um die Anforderungen für angepasste Wählpläne zu unterstützen.</li><li>Falls zutreffend, entscheiden Sie die Mandanten-Wählpläne, die Sie erstellen, um die Benutzer Standorte oder Offices zu unterstützen, die im Bereich der Cloud-VoIP-Implementierung liegen.</li><li>Falls zutreffend, entscheiden Sie, für welche Benutzer ein benutzerdefinierter Wählplan erforderlich ist und welcher Mandanten-Wählplan für jeden Benutzer zugewiesen werden soll.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die angepassten Wählpläne und die zugehörigen Normalisierungsregeln, die als Teil der Cloud-VoIP-Implementierung konfiguriert werden sollen.</li><li>Dokumentieren Sie die Benutzer, denen ein benutzerdefinierter Wählplan zugewiesen werden soll, und den Mandanten Wähl Plan, der für jeden Benutzer zugewiesen werden soll.</li></ul>|

> [!TIP]
> Wenn Sie für Ihr Projekt gültig ist, können Sie die folgenden Vorlagen verwenden, um die Konfigurationen des Mandanten Wähl Plans zu dokumentieren.
> 
> |Name des Mandantenwählplans<br>_Beschreibung_  |Name der Normalisierungsregeln<br>_Beschreibung_  |Muster<br>Übersetzung<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, Wählplan für Australien_|**AU-NSW-NorthRyde-OER-Internal**<br>_Interne Nummer (x7000 - x7999) für One Epping Road-Niederlassung, North Ryde, NSW, Australien_|^ (7 \ d{3}) $<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalisierung für lokale Nummern für NSW, Australien_|^ ([2-9] \d{7}) $<br>+612$1<br>Falsch|
> ||**AU-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Australien_|^ (1 [38] \d{4,8}) \d * $<br>+61$1<br>Falsch|
> ||**AU-Service**<br>_Normalisierung für Servicenummern für Australien_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>Falsch|
> |**SG-Singapore-OMB**<br>_OMB Singapore, Wählplan für Singapur_|**SG-OMB-Internal**<br>_Interne Nummer (x8000 â € "x8999) für OMB Office, Singapur_|^ (8 \ d{3}) $<br>+656888$1<br>Wahr|
> ||**SG-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Singapur_|^ (1? 800 \ d{7}) \d * $<br>+65$1<br>Falsch|
> ||**SG-Service**<br>_Normalisierung für Servicenummern für Singapur_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>$1<br>Falsch|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, Wählplan für Frankreich_|**FR-39qdPR-Internal**<br>_Interne Nummer (x7000 â € "x7999) für 39 Quai du President Roosevelt Office, Issy-les-Moulineaux, Frankreich_|^ (7 \ d{3}) $<br>+3319999$1<br>Wahr|
> ||**FR-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Frankreich_|^ 0? (80 \ d{7}) \d * $<br>+33$1<br>Falsch|
> ||**FR-Service**<br>_Normalisierung für Servicenummern für Frankreich_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>Falsch|

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
> |Louis Lahr|32 London Bridge Street|Dienstwählplan|n/v|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Dokumentdienst Entscheidungen 

Verwenden Sie die Informationen aus den vorherigen Abschnitten dieses Artikels, um Ihre Dienst Entscheidungen zu dokumentieren. Diese Dokumentation enthält im Allgemeinen die folgenden Hauptabschnitte:

-   Aktivierungsliste für Audiokonferenzdienst-Standorte

-   Lizenzzuweisungsliste für Besprechungsorganisatoren von Audiokonferenzen

-   Zahlen für die Planung des Kommunikationsguthabens

-   Details zur Konferenzbrücke

-   Einstellungen der Konferenzbrücke

-   Zuweisungen der Einstellungen für die Konferenzbrücke

-   Telefonnummern-akquisitionspläne

-   Mandantenwählpläne

-   Wählplanzuweisungen

<!--ENDOFSECTION-->