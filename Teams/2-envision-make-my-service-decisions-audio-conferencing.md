---
title: Treffe Audiokonferenzen Service - Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Erfahren Sie mehr über Besprechungen, Lizenzierung und Verfügbarkeit, Konferenz Bridge Einstellungen konfigurieren, erwerben oder Übertragen von Rufnummern, wählen Sie Mandanten-Wählpläne.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e17632977816261b99e4c2ae22a70c8961a040e
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854053"
---
# <a name="make-my-service-decisions"></a>Meine Service treffe

Um die technischen Implementierung der Audiokonferenz planen, müssen Sie eine Reihe von Dienst Entscheidungen vorausschauendes besser Vorbereiten Ihrer Organisation zum Implementieren einer Lösung, die Ihren definierten geschäftlichen Anforderungen erfüllt vornehmen.

## <a name="audio-conferencing-in-teams"></a>Audiokonferenzen in Teams

Als Teil des erforderlichen Audiokonferenzen-Features in Microsoft-Teams definieren wird einer der ersten Schritte für die neuesten öffentlichen Roadmap bestimmen ausgewertet werden soll:

-   Welche Audiokonferenzen Features in Teams, die für Benutzer im Gültigkeitsbereich bereitgestellt werden.

-   Anforderungen an die Benutzer Funktionen für Audiokonferenzen in Teams erwartet.

-   Bestätigung, dass Audio Konferenzfunktionen in die neuesten öffentlichen Roadmap beschriebenen Teams Ihre Benutzer, Funktionen und bereichsanforderungen innerhalb der Zeitachse Ihrer Bereitstellung erfüllt.

> [!NOTE]
> Die neueste Teams-Roadmap für die Identifizierung von Teams Audiokonferenzen Features im Bereich für die Bereitstellung Sie unter finden <https://aka.ms/skype2teamsroadmap>.

## <a name="meetings-in-teams"></a>Besprechungen in Microsoft Teams

Teams können Benutzer die Möglichkeit zum Planen und teilnehmen an onlinebesprechungen mithilfe von HD-Video, voice over IP (VoIP) und PSTN-einwahlkonferenzen Optionen.

Besprechungen geplant werden können, als private Konferenzen (nur eingeladene Teilnehmer können aufgenommen werden) oder DDE-Kanal Besprechungen (für alle Benutzer mit Zugriff auf den DDE-Kanal öffnen), und die Benutzer können auch in den Kanälen, spontane Besprechungen starten.

> [!NOTE]
> Weitere Informationen zu den Funktionen von Besprechungen in Teams finden Sie unter [Skype für Unternehmen zu Microsoft-Teams Funktionen Roadmap] https://aka.ms/skype2teamsroadmap).

Besprechungsteilnehmer kann Ihre Teams Besprechungen beitreten, indem Sie Telefonnummern die gebührenpflichtige oder gebührenfreie Zugriffsnummer für Einwahl Konferenzbrücke über Landlines oder Mobiltelefonen. Darüber hinaus können Benutzer den Audio-Konferenzdienst die Funktion "Anruf an mich" initiieren, damit die Konferenzbrücke, rufen Sie ihre Telefone (nützlich, wenn die Datenverbindung nicht zuverlässig ist), oder Let Besprechung in einer Besprechung teilnehmen können Organisatoren Besprechung einladen Teilnehmer durch ihre Telefone anwählen einer.

> [!IMPORTANT]
> Audiokonferenzen in Teams unterstützt keine Drittanbieter-Audiokonferenzanbieter (ACPs).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Verfügbarkeit von Audiokonferenzen

Bevor Sie die Implementierung der Audiokonferenzen in Teams planen, müssen Sie überprüfen Sie die Verfügbarkeit des Diensts Audiokonferenzen wie in [Ländern und Regionen Verfügbarkeit für Audiokonferenzen und plant aufrufen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> Aufgrund der rechtlichen Nebenbedingungen für Audiokonferenzen für internationale Unternehmen verfügbar sein muss der Vertrag für Office 365-Abonnements stammen aus Ländern und Regionen, in dem der Audio-Konferenzdienst im Handel erhältliche ist.

Nach Bestätigung, dass Ihre Organisation berechtigt ist auf der Grundlage den Audiokonferenz-Dienst zu erhalten, kompilieren Sie die Liste der Standorte oder Büros, in dem Sie den Dienst Audiokonferenzen implementieren werden, der Liste der verfügbaren Ländern und Regionen.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, an welchen Benutzerstandorten oder in welchen Niederlassungen der Audiokonferenzdienst implementiert wird.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzerstandorte oder Niederlassungen, die für den Audiokonferenzdienst aktiviert werden.</li></ul>|

> [!TIP]
> Es folgt ein Beispiel einer Audiokonferenz-Aktivierung-Liste Websitevorlage:
>|Niederlassung   |Standort |PSTN-Konferenzdienst  |
>|---------|---------|---------|
>|One Epping Road|Australien|Audiokonferenzen|
>|100 Cyberport Road|Hong Kong SAR (香港特別行政區)|Legacy-PSTN-Konferenz|
>|One Marina Boulevard|Singapur|Audiokonferenzen|
>|32 London Bridge Street|Großbritannien|Audiokonferenzen|
>|39 quai du Président Roosevelt|Frankreich|Audiokonferenzen|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Lizenzierung für Audiokonferenzen

Eine [Audiokonferenz Lizenz](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) steht als Teil der Office 365 E5 Abonnementpläne oder als Add-on-Dienst auf Office 365 E1 oder E3 für Office 365-abonnementtarife.

> [!NOTE]
> Drittanbieter-Audiokonferenzanbieter (ACPs) unterstützt keine PSTN oder Dial-in Conferencing in Teams.
> <br>Wenn Sie den PSTN-Konferenzdienst für Skype for Business bereits verwenden, können Sie unmittelbar die Vorteile des Audiokonferenzdiensts in Teams nutzen.

Anzugebende gebührenfreie Konferenz Bridge Telefonnummern und zur Unterstützung von Konferenzen Anwahl auf internationale Telefonnummern, müssen Sie für Ihre Organisation [Communications haben](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) einrichten.

> [!IMPORTANT]
> In einigen Ländern sind von nur Telefonnummern der gebührenfreie Konferenz-Brücke bedient. Zur Unterstützung der Zugriffsnummer für Einwahl in diesen Ländern müssen Sie Communications haben verwenden.

Der erste Aspekt beim Implementieren von Kommunikation haben entscheiden, die Anfangsgröße des Mittel ist, die Sie kaufen möchten. Wenn Ihre Organisation entscheidet, Auto-Ladeleuchte verwenden, müssen Sie die Trigger Menge (niedrigste Betrag der Mittel) und den Auto-Ladeleuchte entscheiden. Nutzung von tatsächlichen wird die automatische Ladeleuchte bestimmen. Überwachen der Nutzung von Communications haben über einen Zeitraum, und passen Sie den Betrag Ladeleuchte nach Bedarf.

Weitere Informationen finden Sie Informationen zu Communications haben [hier](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Wenn Ihr Unternehmen bereits die erforderlichen Audiokonferenzen Lizenzierung erworben wurde nicht, entscheiden Sie, ob Sie vorhandenen Office 365-Abonnements umsteigen oder Audiokonferenzen Add-On-Lizenzen erwerben Audiokonferenzen Lizenzen erwerben können.</li><li>Entscheiden Sie, ob Communications haben für die Audiokonferenz Implementierung erforderlich sind. Wenn ja, legen Sie den anfänglichen Auffüllungsbetrag fest. Legen Sie zudem fest, wie hoch der niedrigste Betrag sein sollte, bei dem die automatische Auffüllung ausgelöst wird.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer, die Audiokonferenz Lizenzen zugewiesen werden.</li><li>Dokumentieren Sie den Plan Communications haben (Anfangsgröße, Trigger Betrag, Auto-Ladeleuchte Betrag)</li></ul>|

> [!TIP]
> Sie können mithilfe der im folgenden Beispiel wird die Liste der Lizenz-Zuordnung für Audiokonferenzen Benutzer dokumentieren.
>|Benutzer  |Niederlassung  |Office 365-Lizenz  |
>|---------|---------|---------|
>|Adele Vance|One Epping Road|Office 365 E5|
>|Alex Wilber|One Epping Road|Office 365 E3, Add-On für Audiokonferenzen|
>|Ben Walters|One Epping Road|Office 365 E3, Add-On für Audiokonferenzen|
>|Christie Cline|One Marina Boulevard|Office 365 E3, Add-On für Audiokonferenzen|
>|Debra Berger|One Marina Boulevard|Office 365 E5|
>|Lee Gu|One Marina Boulevard|Office 365 E5|
>|Emily Braun|32 London Bridge Street|Office 365 E5|
>|Lidia Holloway|32 London Bridge Street|Office 365 E5|
>|Louis Lahr|32 London Bridge Street|Office 365 E5|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, Add-On für Audiokonferenzen|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, Add-On für Audiokonferenzen|

<br>
> [!TIP]
> Sie können Ihre Zahlen für die Planung des Guthabens für Kommunikationen so dokumentieren:
>|         |         |
>|---------|---------|
>|Anfangsbetrag|1.000 US-Dollar|
>|Betrag für die Auslösung der Auffüllung|400 US-Dollar|
>|Höhe des Betrags für die automatische Auffüllung|TBA|

<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>Telefonnummern für Konferenzbrücken

Der Audiokonferenzdienst in Office 365 umfasst:

-   Mehrere Authentifizierungstypen Konferenz Brücke Rufnummern (gebührenpflichtige und gebührenfreie)

-   Mehrere Kategorien der Konferenzbrücke Telefonnummern (dedizierte und gemeinsame)

-   Unterstützung für mehrere Sprachen für die Konferenzbrücke (primär oder sekundär)

-   Eine Standard-Rufnummer für den Mandanten

> [!NOTE]
> Dedizierte Bridge Telefon Zahlen konferenzanzahl in der Begrenzung von Rufnummern, die pro Mandant, basierend auf der Anzahl der entsprechenden Lizenzen erworben werden können. Für gebührenfreie Telefonnummern für Konferenzbrücken ist Kommunikationsguthaben erforderlich.

Wenn Sie vorhandene Konferenz Bridge Telefonnummern an den Audio-Konferenzdienst übertragen müssen – vorausgesetzt, sie erfüllen länderspezifisch – Sie können diese Rufnummern der vorhandenen Konferenz Bridge an Microsoft übertragen.

> [!NOTE]
Die Komplexität der Rufnummern an Microsoft übertragen variiert stark je nach Land oder Region, Netzbetreiber, Anzahl der beteiligten Circuits und viele andere Faktoren beitragen. Arbeiten mit Ihren aktuellen Anbieter untersuchen, wie lange dies ist voraussichtlich durchführen, um sicherzustellen, dass Sie den zu einem frühen Zeitpunkt starten genug sind, um die Zeitachsen erfüllen.

Lesen Sie mehr über die Konferenz Bridge Rufnummern finden Sie in den folgenden Artikeln:

-   [Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

-   [Telefonnummern für Audiokonferenzen](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Anfordern von Servicenummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

-   [Übertragen von Telefonnummern zu Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Ihre Organisation dedizierten Konferenz Bridge Telefonnummern benötigt.</li><li>Entscheiden Sie, wie die dedizierte Konferenz Bridge Telefonnummern für Standorte oder Büros erhalten werden im Bereich für die Implementierung von Audiokonferenzen (die von Microsoft oder Übertragung vorhandenen Telefonnummern erhalten wird,).</li><li>Wenn Sie diese von Microsoft erhalten möchten, entscheiden, die zu verwendende Methode (Formular zum Absenden oder automatisierte) für Standorte oder Büros Bereich für die Implementierung von Audiokonferenzen.</li><li>Entscheiden Sie, die spracheinstellungen für jede Telefonnummer für dedizierte Konferenz Bridge einrichten.</li><li>Entscheiden Sie Mandanten Konferenz Bridge Standardrufnummer.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Master-Shape für Erwerb von Telefon aus, mit ausführlichen Informationen zu wie Telefonnummern für jeden Benutzerstandort oder Office im Bereich für die Audiokonferenz Implementierung erhalten werden.</li><li>Füllen Sie das Formular neues Telefon anfordern – ein Formular für jeden Standort oder Office.</li><li>Dokument die detaillierte Konferenzbrücke phone Number Konfigurationen (shared und dedizierte Konferenz Bridge Telefonnummern, spracheinstellungen für jede dedizierten Bridge Konferenztelefonnummer, Mandanten Standard-Brücke Konferenztelefonnummer).</li></ul>|

Es folgt ein Beispiel für eine Vorlage, die Sie zur Konferenz Bridge Details Erfassung verwenden können.

> [!TIP]
> Das folgende Beispiel zeigt eine Vorlage zum Erfassen der Details von Konferenzbrücken:
>|Niederlassung   |Anschaffung der Brückennummer und Brückentyp |Brückennummer  |Brückensprache|
>|---------|---------|---------|---------|
>|One Epping Road|Neu anschaffen, dediziert|TBA|Englisch (Australien)|
>|One Marina Boulevard|Neu anschaffen, freigegeben|TBA|Englisch (Vereinigte Staaten), Chinesisch (vereinfacht)|
>|32 London Bridge Street|Port vorhanden, dediziert|+44 20 7946 0001|Englisch (Vereinigtes Königreich)|
>|39 quai du Président Roosevelt|Neu anschaffen, dediziert|TBA|Französisch (Frankreich), Englisch (Vereinigtes Königreich)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>Einstellungen der Konferenzbrücke

Um die Benutzeroberfläche weiter anpassen möchten, können Sie organisationsweiten Optionen für die Teilnahme an Audiokonferenzen Besprechungen (meeting Beitritts- und Benachrichtigung und Anrufer Namen Aufzeichnung), der Besprechungsorganisator PIN-Länge und e-Mail-Benachrichtigung konfigurieren:

-   Benachrichtigungen über Zu- und Abgänge in Besprechungen sind in Form eines aufgezeichneten Namens, einer Telefonnummer und Signaltönen verfügbar.

-   Die PIN-Länge ist mit 4 bis zwölf Ziffern konfigurierbar, wobei eine PIN standardmäßig aus 5 Ziffern besteht.

-   Benachrichtigung, dass auf die Aktivierung der Lizenz Audiokonferenzen oder andere Administratorgesteuert Änderung gesendete e-Mails standardmäßig aktiviert sind. Sie können dieses Feature deaktivieren und Übernehmen der Steuerung Ihres Unternehmens Benutzerkommunikation.

Für Benutzer, die eine Audiokonferenz-Lizenz zugewiesen sind, können die Standardeinstellung gebührenpflichtige/toll-free Zahlen, in die Koordinaten Audiokonferenzen angezeigt konfiguriert werden:

-   Der Standardwert ist auf Mandantenebene.

-   Die Telefonnummern der automatisch zugewiesene Konferenz-Brücke.

-   Eine Konferenz Bridge Rufnummern für jeden Benutzer manuell konfiguriert.

Benutzerspezifische Konferenz Brücke Telefonnummern Zahlen eignen sich in der Regel in der globalen oder landesweit Organisationen, in dem Benutzer verteilt werden und müssen Ortsgespräche als Standard-Konferenz Bridge Rufnummern in ihrer besprechungseinladungen angeben.

Teilnehmer aus verschiedenen Städten oder Übersee können Nachschlagen zusätzliche Nummern, die Ebene des Mandanten konfiguriert, aber diese Nummern nicht direkt in den besprechungseinladungen angezeigt. Die besprechungseinladungen enthalten einen Link Teilnehmer zur Seite **Teams Konferenz einwählen Zahlen** für sie die Brücke Konferenztelefonnummer am nächsten zu ihrem Standort nachzuschlagen.

Sie können auch konfigurieren, wie nicht authentifizierter Anrufer werden von jedem einzelnen Besprechungsorganisator behandelt –, ob erzwungen Organisator der Besprechung die Besprechung starten, bevor nicht authentifizierter Anrufer zugelassen werden können, oder lassen Sie nicht authentifizierte Aufrufer zum Starten einer Besprechung .

Sie können auch zusätzliche Konfigurationen für jeden Benutzer die Verwendung von gebührenfreie Konferenz Bridge Rufnummern steuern und Anwahl von einer Konferenz anwenden.

> [!NOTE]
> Diese mit Kosten verbundenen Steuerelemente sind derzeit nur für Preview-Kunden verfügbar. Sie können registrieren Sie Ihre Organisation in der Vorschau-Anwendung aus https://www.skypepreview.com.

Mit diesen Steuerelementen können Sie entscheiden, ob Besprechungsorganisatoren gebührenfreie Konferenz Bridge Rufnummern für von ihnen organisierte Besprechungen bereitstellen können, und gibt an, ob Teilnehmer aus Besprechungen anwählen können Organisation. Die Ebene der Dial-Out-Steuerelement umfasst vollständig verhindert ein-, nur zulassen Client-nationalen Nummern, bis zum Zulassen von Client-nationalen und internationalen Zahlen werden kann.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden, ob Ihre Organisation Beitritts- und Benachrichtigungen erfordert und – wenn dies der Fall ist – die Art der Benachrichtigung implementiert werden (Töne, Telefonnummer oder aufgezeichneten Namen).</li><li>Entscheiden Sie, die Audio-Konferenzen PIN-Mindestlänge, die den Anforderungen der Sicherheit in der Organisation entspricht.</li><li>Entscheiden Sie, ob Ihre Organisation möchte Benutzerkommunikation im Zusammenhang mit der Audiokonferenz Dienst steuern.</li><li>Wählen Sie die Telefonnummern für Konferenzbrücken aus, die jedem Besprechungsorganisator zugewiesen werden.</li><li>Entscheiden Sie, ob einige Besprechungsorganisatoren gebührenfreie Konferenz Bridge Rufnummern für ihre Besprechungen verwenden müssen.</li><li>Entscheiden Sie, ob einige Besprechungsorganisatoren nicht authentifizierter Anrufer an eine Besprechung starten zu ermöglichen müssen.</li><li>Entscheiden Sie, ob einige Besprechungsorganisatoren Konferenz Anwahl gesteuert werden benötigen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die detaillierten Konferenzbrückeneinstellungen (Benachrichtigungen über Zu- und Abgänge, PIN-Länge, E-Mail-Benachrichtigung über Konfigurationsänderungen).</li><li>Dokumentieren der Konferenz Bridge Rufnummern zugewiesen an jedem Organisator der Besprechung und die entsprechende Einstellung zum Steuern der Richtlinie für nicht authentifizierter Anrufer und gebührenfreie und Kontrollen einwählen.</li></ul>|

> [!TIP]
> Wie im folgenden Beispiel können die Konferenz Bridge Einstellungen dokumentiert werden.
>|         |         |
>|---------|---------|
>|Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren|Aktiviert|
>|Ankündigungstyp für Zu- und Abgänge|Signaltöne|
>|Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen|Deaktiviert|
>|PIN-Länge|5|
>|Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert.|Deaktiviert|

<br>
> [!TIP]
> Sie können mithilfe der im folgenden Beispiel wird die Liste Konferenz Bridge Settings Zuordnung für Audiokonferenzen Benutzer dokumentieren.
>|Benutzer  |Niederlassung  |Gebührenpflichtige Standardnummer  |Gebührenfreie Standardnummer  |Gebührenfreie Nummer zulassen  |Nicht authentifizierte Anrufer umgehen Wartebereich  |Konferenzauswahl  |
>|---------|---------|---------|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|TBA|TBA|Ja|Aktiviert|In- und Auslandsanrufe|
>|Alex Wilber|One Epping Road|TBA|TBA|Nein|Deaktiviert|Nicht zulässig|
>|Ben Walters|One Epping Road|TBA|TBA|Nein|Deaktiviert|Nicht zulässig|
>|Christie Cline|One Marina Boulevard|TBA|TBA|Ja|Deaktiviert|Inlandsanruf|
>|Debra Berger|One Marina Boulevard|TBA|TBA|Ja|Aktiviert|Inlandsanruf|
>|Lee Gu|One Marina Boulevard|TBA|TBA|Ja|Aktiviert|Inlandsanruf|
>|Emily Braun|32 London Bridge Street|+44 20 7946 0001|TBA|Ja|Aktiviert|Nicht zulässig|
>|Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|TBA|Ja|Deaktiviert|Nicht zulässig|
>|Louis Lahr|32 London Bridge Street|+44 20 7946 0001|TBA|Ja|Deaktiviert|Nicht zulässig|
>|Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|Nein|Deaktiviert|Inlandsanruf|
>|Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|Ja|Aktiviert|In- und Auslandsanrufe|
>|Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|Nein|Deaktiviert|Inlandsanruf|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Verwalten von Cloud-VoIP-Telefonnummern

Für Audiokonferenzen Implementierung können Sie neue Telefonnummern zu erwerben oder Übertragung/Port vorhandenen Telefonnummern.

Ermöglicht den Benutzern so Telefonnummern wählen Sie wie gewohnt sind – wie Vorwahlen für Ortsgespräche auslassen, Ländercode für Gespräche auslassen oder sogar mit kurzen Ziffer, die beim Ausführen einer Konferenz einwählen ausgehende Anrufe – Sie können einen benutzerdefinierten Wählplan konfigurieren und Benutzern zuweisen.

## <a name="acquire-new-telephone-numbers"></a>Erwerben Sie neue Telefonnummern

Die zwei Arten von Telefonnummern in Microsoft Cloud VoIP-Lösungen sind:

-   Zahlen Abonnenten (Benutzer), die für Benutzer in Ihrer Organisation zugewiesen werden können.

-   Service, verfügbare Nummern als gebührenpflichtige oder gebührenfreie Service Zahlen, die höheren Kapazität für gleichzeitige Anrufe als Abonnenten Zahlen und Diensten wie etwa Audiokonferenzen, automatischen Telefonzentralen oder rufen Sie Warteschlangen zugewiesen werden können.

Weitere Informationen über diese Art von Telefonnummern finden Sie unter [verschiedenen Arten von Telefonnummern für den Aufruf von plant verwendet](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Die Gesamtzahl der Telefonnummer, die Zahlen, die Sie erhalten können, welche Telefonnummer und die Anzahl der Lizenzen abhängen haben Sie erworben und Ihren Benutzern zugewiesen.

Wenn es sich um Service Zahlen geht, müssen Sie die Audiokonferenz Implementierung sorgfältig planen. Überprüfen Sie, ob Ihr Unternehmen dedizierten Konferenz Bridge Telefonnummern benötigt; Wenn dies nicht der Fall ist, Ihrer Organisation kann optional freigegebenen Konferenz Bridge Telefonnummern verwenden.

Weitere Informationen über die Gesamtzahl der Telefonnummern, die Sie herunterladen können, finden Sie unter [wie viele Rufnummern erhalten Sie?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie die Standorte oder Büros, in dem neue Telefonnummern von Microsoft erfasst wird.</li><li>Legen Sie die Art der Telefonnummern von Microsoft erworben werden.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Standorte oder Büros, in dem neue Telefonnummern von Microsoft erfasst wird.</li><li>Dokumentieren Sie den Typ der Telefonnummern von Microsoft erworben werden.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Übertragen der vorhandenen Telefonnummern

Wenn Ihre Organisation für die Übertragung (oder Port) einer vorhandenen Telefonnummern an Microsoft möchte, können Sie dazu Port Reihenfolge Microsoft eine Anforderung einreichen.

Sie können alle Ihre vorhandenen Telefonnummern gleichzeitig (vollständige Port) übertragen und – in einigen Märkten – Sie können eine Teilmenge der vorhandenen Telefonnummern (teilweise Port) übertragen. Ein partieller Port kann in Fällen nützlich sein, auf dem Sie einfach Ihre Einwahl Konferenzbrücke Audiokonferenzen Dienst verschieben möchten.

Eine einzelnen Port Reihenfolge kann nur die Telefonnummern an ein einzelnes Telefon übertragen. Wenn Sie einige Ihrer Telefonnummern als Abonnenten Zahlen und einige als Dienst Zahlen übertragen müssen, wird empfohlen, dass Sie zuerst die Weiterleitung an Microsoft abgeschlossen, und Sie dann die Konvertierung führen, sobald die Zahlen in der Kontrolle von Microsoft sind.

Als Alternative wenn partielle Port unterstützt wird, können Sie mehrere Port-Anfragen, einen Port Anforderung zu einem Zeitpunkt senden. Diese alternative Ansatz wird jedoch Ihrem Vertrag mit Ihren vorhandenen Telekommunikation Dienstanbieter verlängert.

Telefon Nummer Portieren ist ein komplexes Thema und erfordert gründliche Planung, Koordination und angemessen verwalten beteiligten erwartet. Finden Sie weitere Informationen finden Sie in den folgenden Artikeln:

-   [Übertragen von Telefonnummern zu Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Allgemeine Fragen zum Übertragen von Telefonnummern](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie die Standorte oder Büros, auf dem vorhandenen Telefonnummern an Microsoft übertragen wird.</li><li>Legen Sie die Art der Telefonnummern an Microsoft übertragen werden.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Standorte oder Büros, auf dem vorhandenen Telefonnummern an Microsoft übertragen wird.</li><li>Dokumentieren Sie den Typ der Telefonnummern an Microsoft übertragen werden.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Wählpläne

A Dial Plan im Telefonsystem Feature von Office 365 handelt es sich um eine Gruppe von Normalisierungsregeln, die übersetzt Rufnummern für Anrufberechtigungen und Anrufrouting in ein anderes Format (normalerweise e. 164-Format) gewählt. Der Audio-Konferenzdienst nutzt die gleichen Funktionen von Telefonsystem verwendet, um die gewählte Rufnummern in Konferenz Dial-Out-Szenarien (z. B. Teilnehmer einladen über PSTN und Rückruf, Feature "Rückruf") übersetzen.

In das Telefonsystem Feature von Office 365 gibt es zwei Arten von Wählplänen:

-   **Service-Wählplan:** Dies ist die Standardeinstellung Wählplan, die auf Benutzer angewendet wird basierend auf deren Speicherort der Office 365-Verwendung und kann nicht geändert werden.

-   **Mandanten Wählplan:** Dies ist eine anpassbare Wählplan innerhalb eines Mandanten liegen weiter in zwei Typen unterteilt werden:

    -   **Mandanten globale Wählplan:** Die Wähleinstellungen, die für alle Benutzer in den Mandanten gilt.

    -   **Mandanten benutzerwähleinstellungen:** Die Wähleinstellungen, die nur auf bestimmte Benutzer gilt.

Die effektive Wähleinstellungen, die Benutzern zugewiesen ist eine Kombination aus dem Dienst Wählplan (basierend auf den Standort eines Benutzers Office 365 Verwendung) und Mandanten Wählplan (können Mandanten globale Wählplan oder Mandanten benutzerwähleinstellungen sein).

![Tabelle werden die drei Kombinationen Quality of Service und Mandanten Wählplänen.] (media/audio_conferencing_image8.png "Tabelle werden die drei Kombinationen Quality of Service und Mandanten Wählplänen.")

> [!Important]
> In jeder Mandant Wähleinstellungen kann bis zu 25 Normalisierungsregeln sein. Daher ist es wichtig, zu vermeiden, Duplizierung von Normalisierungsregeln, die bereits verfügbar sind als Teil des Diensts Wählplan.

Weitere Informationen zu Wählplänen finden Sie unter [Was Wählpläne sind?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Ihre Organisation angepasste Wählpläne (geschäftlichen Anforderungen, Annahme Anforderungen usw.) erforderlich sind.</li><li>Legen Sie (falls anwendbar) den Gültigkeitsbereich für den Mandantenwählplan (globaler Wählplan für Mandanten oder Wählplan für Mandantenbenutzer) fest, um die Anforderungen für angepasste Wählpläne zu erfüllen.</li><li>Gegebenenfalls entscheiden, die Mandanten-Wählpläne, die Sie erstellen, um Standorte oder Büros unterstützt im Gültigkeitsbereich für die Cloud VoIP-Implementierung.</li><li>Gegebenenfalls entscheiden Sie, welche Benutzer benötigen, eine angepasste Wählplan und die Wähleinstellungen Mandanten für jeden Benutzer zugewiesen werden soll.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie angepasste Wählpläne und die zugehörigen Normalisierungsregeln als Teil der Cloud VoIP-Implementierung konfiguriert werden soll.</li><li>Dokumentieren Sie die Benutzer um einen benutzerdefinierten Wählplan und die Mandanten-Wähleinstellungen für jeden Benutzer zugewiesen werden zugewiesen werden.</li></ul>|

> [!TIP]
> Wenn sie für Ihr Projekt gilt, können Sie die folgende Vorlage verwenden, um die Konfigurationen für den Mandanten Dial Plan zu dokumentieren.
>|Name des Mandantenwählplans<br>_Beschreibung_  |Name der Normalisierungsregeln<br>_Beschreibung_  |Muster<br>Übersetzung<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, Wählplan für Australien_|**AU-NSW-NorthRyde-OER-Internal**<br>_Interne Nummer (x7000 - x7999) für One Epping Road-Niederlassung, North Ryde, NSW, Australien_|^(7\d{3})$<br>+6125550$1<br>Wahr|
>||**AU-NSW-Local**<br>_Normalisierung für lokale Nummern für NSW, Australien_|^ ([2-9] \d{7}) $<br>+612$1<br>Falsch|
>||**AU-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Australien_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>Falsch|
>||**AU-Service**<br>_Normalisierung für Servicenummern für Australien_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>Falsch|
>|**SG-Singapore-OMB**<br>_OMB Singapore, Wählplan für Singapur_|**SG-OMB-Internal**<br>_Interne Nummer (X8000 Â €"x 8999) für Office OMB, Singapur_|^(8\d{3})$<br>+656888$1<br>Wahr|
>||**SG-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Singapur_|^(1?800\d{7}) \d*$<br>+65$1<br>Falsch|
>||**SG-Service**<br>_Normalisierung für Servicenummern für Singapur_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>Falsch|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, Wählplan für Frankreich_|**FR-39qdPR-Internal**<br>_Interne Nummer (X7000 Â €"x 7999) für 39 Quai du Président Roosevelt Office, Issy-Les-Moulineaux, Frankreich_|^(7\d{3})$<br>+3319999$1<br>Wahr|
>||**FR-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Frankreich_|^ 0?(80\d{7}) \d*$<br>+33$1<br>Falsch|
>||**FR-Service**<br>_Normalisierung für Servicenummern für Frankreich_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>Falsch|

<br>
> [!TIP]
> Sie können die folgende Beispielvorlage nutzen, um Wählplanzuweisungen für Ihr Projekt zu dokumentieren:
>|Benutzer  |Niederlassung  |Typ des Wählplans  |Name des Wählplans  |
>|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
>|Alex Wilber|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
>|Ben Walters|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
>|Christie Cline|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
>|Debra Berger|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
>|Lee Gu|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
>|Emily Braun|32 London Bridge Street|Dienstwählplan|n/v|
>|Lidia Holloway|32 London Bridge Street|Dienstwählplan|n/v|
>|Louis Lahr|32 London Bridge Street|Dienstwählplan|n/v|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Dokument Service Entscheidungen 

Verwenden Sie die Informationen aus den vorherigen Abschnitten dieses Artikels, um Ihre Entscheidungen Service zu dokumentieren. Im Allgemeinen enthält diese Dokumentation die folgenden Hauptabschnitte:

-   Aktivierungsliste für Audiokonferenzdienst-Standorte

-   Lizenzzuweisungsliste für Besprechungsorganisatoren von Audiokonferenzen

-   Zahlen für die Planung des Kommunikationsguthabens

-   Details zur Konferenzbrücke

-   Einstellungen der Konferenzbrücke

-   Zuweisungen der Einstellungen für die Konferenzbrücke

-   Telefonnummern Erwerb Pläne

-   Mandantenwählpläne

-   Wählplanzuweisungen

<!--ENDOFSECTION-->