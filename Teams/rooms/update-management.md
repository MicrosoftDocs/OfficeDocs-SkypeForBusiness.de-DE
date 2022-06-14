---
title: Microsoft Teams-Räume Updateverwaltung
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: proaktive Überwachung Ihrer Besprechungsräume.
f1keywords: ''
ms.openlocfilehash: 2311d17c5d60b7c9eb845570ce24c5f6db507717
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057065"
---
# <a name="update-management"></a>Updateverwaltung 
Ein moderner Besprechungsraum ist mit einem Microsoft Teams-Räume Gerät und anderen Peripheriegeräten wie einer Kamera, einem Mikrofon oder einem Lautsprecher und potenziell mehr Geräten ausgestattet, um eine inklusive und effektive Besprechungserfahrung zu schaffen. Geräte aus verschiedenen Arten von OEMs bieten genau die gewünschte Organisationserfahrung; Sie müssen jedoch kontinuierlich mit Software und Firmware verwaltet werden.  

Managed Services für Microsoft Teams-Räume bietet die Sicherheit, dass jeder Raum in Ihrer Organisation auf empfohlenen Ebenen verwaltet wird, um einen Raum bereitzustellen, der immer bereit und ordnungsgemäß funktioniert. Das Ziel von Microsoft ist es, die Komplexität und Vorarbeit für Ihre operativen Mitarbeiter mit Intelligenz und Automatisierung zu reduzieren. Problembehandlung oder Diagnose wird so schnell wie möglich durchgeführt. 

## <a name="transitioning-a-device-to-managed-services"></a>Übergang eines Geräts zu verwalteten Diensten 
Das Onboarding von Raumgeräten in verwaltete Dienste weist in der Regel einen Änderungsverwaltungsverlauf auf, der sich von unserem Leitfaden unterscheidet.  

- Um von verwalteten Diensten zu profitieren, müssen Sie die Änderungsverwaltung für alle Updates im Managed Services-Portfolio wechseln.
- Mehrere Quellen von SlAs für das Änderungsmanagement wirken sich auf Vorfalls-SLAs aus, da es eine Ermittlung und Behebung gibt, die neu gestartet wird, wenn ein Vorfall im Raum auftritt.
- Microsoft hat Steuerelemente und Prüfungen implementiert, um Richtlinien zu implementieren, die sich von Organisation zu Organisation unterscheiden können, und die Fähigkeit, in Ausnahmesituationen einzugreifen.
- Schließlich werden die Raumgeräte auf allgemeine Standards aktualisiert, mit Ausnahme von Ausnahmen aufgrund von Problemen mit einer bestimmten Hardwareinstallation.  

## <a name="transitioning-devices-basic-readiness-checks"></a>Übergangsgeräte: Grundlegende Bereitschaftsprüfungen 
Die meisten unerwarteten Fehler ergeben sich aus Änderungen im Basisimage mit unsicherem Verlauf des Änderungsmanagements. 

Es wird empfohlen, die folgenden einfachen Bereitschaftsprüfungen durchzuführen:  

- **Basisimage**: Das Basisimage muss vom jeweiligen OEM stammen. Wenn das Gerät in der Vergangenheit neu erstellt wurde und unerwartete Fehler oder Verhaltensweisen bei allgemeinen Aufgaben anzeigt, muss das Basisimage wiederhergestellt werden. Wir können Unterstützung leisten, aber das Raumgerät nicht remote neu erstellen, daher benötigen Sie einen lokalen Techniker.  
- **Basisbetriebssystem, Edition:** Das Basisbetriebssystem und die Basisedition müssen den Anforderungen Microsoft Teams-Räume Geräten entsprechen. Wenn dies nicht der Fällen entspricht, muss sie im Rahmen des Onboardings korrigiert werden. Microsoft Teams-Räume erfordert die Windows 10 IoT Enterprise oder Windows 10 Enterprise SKUs unter Semi-Annual Channel-Wartungsoptionen. Weitere Informationen finden Sie in den offiziellen [MTR-Anleitungen](rooms-lifecycle-support.md#windows-10-release-support) .

## <a name="readiness-checks"></a>Bereitschaftsprüfungen

Es gibt einige Voraussetzungen für den Empfang von Updates für verwaltete Dienste: 

|Software |Anleitung |
|:- |:- |
|Logitech-Synchronisierungsdienste  |Sollte auf den Logitech-Besprechungsraumgeräten installiert und ausgeführt werden. Erforderliche Synchronisierungsdienste werden automatisch von Windows Updates installiert, sofern nicht blockiert. Das vollständige Synchronisierungspaket kann auch installiert werden. |
|Windows Betriebssystemupdates |Sollte aktiviert und weder an WSUS umgeleitet noch aus Netzwerksicht blockiert werden. Weder GPO- noch MDM-Richtlinien sollten zum Verwalten von Betriebssystemupdates verwendet werden. |
|Microsoft Store Updates   |Sollte deaktiviert sein. Verwaltete Dienste deaktivieren Store Updates, wenn sie aktiviert sind. |
|Antivirensoftware |Wenn Sie AV-Software auf diesen Geräten ausführen, sollten Sie sicherstellen, dass AV Ausschlüsse für Teams und Skype DLL-Dateien aufweist. Weitere Informationen finden Sie hier. |
|Zusätzliche Software |Zusätzliche Software wie die Remotedesktopanzeige von Drittanbietern usw. sollte mit verwalteten Diensten überprüft werden, um Nebenwirkungen auszuschließen. |
|Zusätzliche Änderungsverwaltung|Kann die abgedeckten Updates stören und sollte nicht eingeführt werden. |

## <a name="managed-updates--how-it-works"></a>Verwaltete Updates – Funktionsweise 
Es gibt zwei Hauptmethoden, wie Updates verwaltet werden:  

- **Automatisch verwaltet**: Updates werden auf Ihrem Raumgerät basierend auf der Bewertung verwalteter Dienste installiert. Für die in unserem Portfolio verwalteten Updates ist kein Eingriff erforderlich.
- **Ring überprüft**: Richten Sie ein Ringsystem ein, um Updates auf bestimmten Geräten in der Vorschau anzuzeigen, sodass Sie diese ohne die zugehörige Beinarbeit überwachen können. Das Ringsetup bietet eine zusätzliche Ebene der Due Diligence vor umfassenden Rollouts.  

### <a name="automatically-managed"></a>Automatisch verwaltet

Wenn Sie sich dafür entscheiden, automatisch verwaltet zu werden, ist für die Updates Ihrer Seite keine Aktion erforderlich. Sie sollten jedoch das aktuelle Portfolio der updates überprüfen, die von Managed Services unterstützt werden. Das Portfolio erhält ständig neue Ergänzungen, und es ist unsere Priorität, die häufigsten und wirkungsvollsten Updates abzudecken, um Ihre Raumstabilität zu gewährleisten. Überprüfen Sie die aktuelle Liste (unter dem Abschnitt "Updateverwaltung" in diesem Dokument), um alle für Ihre Organisation erforderlichen zusätzlichen Änderungsverwaltungen zu planen.  

**Empfehlung:** Installieren Sie keine Updates, die von Verwalteten Diensten abgedeckt werden, auf jedem verwalteten Gerät auf Ihrem eigenen Gerät. Wenn Probleme auftreten, melden Sie bitte einen Vorfall im Portal.

### <a name="ring-validation"></a>Ringüberprüfung

Wenn Sie die Ringüberprüfung auswählen, lesen Sie die folgenden Abschnitte zur Funktionsweise von Ringen in verwalteten Diensten und zu den verfügbaren Optionen, um sie für Ihre Organisation anzupassen. Selbst bei der Ringüberprüfung versucht Managed Services sicherzustellen, dass Räume bei empfohlenen Updates nicht überfällig sind. Je nach Situation erhält ein Raum möglicherweise "Nachholupdates", um sicherzustellen, dass er den Empfehlungen für verwaltete Dienste entspricht.  

 Überprüfen Sie auf der Homepage des Portals und in der Dokumentation zu verwalteten Diensten nach Ankündigungen, wenn neue Arten von Software und Firmware im Portfolio verfügbar werden. Da Experten für verwaltete Dienste updateversionen täglich in unserem Portfolio von Geräten überprüfen, behandeln sie spezifische Probleme und zielen auf Updates basierend auf der Notwendigkeit ab.  

### <a name="scheduling"></a>Zeitplanung 
Verwaltete Updates werden für Räume basierend auf dem Gerät im Raum geplant, und wenn sie die Managed Services-Standards für anwendbare Software und Firmware nicht erfüllen. 

- Um unseren Kunden dabei zu helfen, die Anforderungen des Änderungsmanagements zu erfüllen, beginnt die Updatebereitstellung **mittwochs** im Stagingring. Wenn ein kritisches Update erforderlich ist, umgehen wir diesen Zeitplan und veröffentlichen das Update, sobald es verfügbar ist. 

- Updates werden basierend auf der Notwendigkeit in einem bestimmten Raum sequenziert. 
- Wenn Sie Setupringe zum Überprüfen der Updates haben, wird das Update durch die Ringreihenfolge ausgeführt. 
- Ein neues Update kann ein Update ersetzen, das in die Warteschlange gestellt wird, wenn wir feststellen, dass die Raumstabilität basierend auf Ihrer Situation verbessert wird.  
- Updates werden in der Regel während unseres nächtlichen Wartungsfensters angewendet – in der Ortszeit **von 12:00 – 5:00 Uhr** , um Unterbrechungen jeglicher Art zu vermeiden. 

## <a name="microsoft-teams-rooms-app-update-lifecycle-policy"></a>Microsoft Teams-Räume App-Updatelebenszyklusrichtlinie 
Die Supportrichtlinie des MTR-Entwicklungsteams gibt an, dass der gesamte Support nach Ablauf des Zwölfmonatslebenszyklus für eine Version endet oder wenn seitdem mehr als zwei Updates veröffentlicht wurden. Kunden müssen dann eine Aktualisierung auf eine unterstützte Version durchführen. Verweisen Sie auf [Microsoft Teams-Räume App-Versionsunterstützung – Microsoft Teams | Microsoft-Dokumentation](rooms-lifecycle-support.md) für eine detaillierte Dienstbeschreibung.

Um einen einheitlichen Standard in allen unseren verwalteten Räumen beizubehalten und trendige Probleme effizient zu identifizieren, werden wir die beiden neuesten Haupt- oder Nebenversionen (N, N-1) der MTR-App-Software gemäß den Support- und Abonnementdienstbedingungen unterstützen und bereitstellen. Wir werden nicht konforme Räume automatisch auf den neuesten Stand bringen und updateringe bei Bedarf umgehen. 

Die N-1-Richtlinie gilt auch für Software von Drittanbietern.  

## <a name="update-management-experience-walk-through"></a>Schrittweises Durchlaufen der Updateverwaltungsoberfläche  
Um Updates anzuzeigen, melden Sie sich beim Portal für verwaltete Dienste an, und navigieren Sie zur Seite "Updates".

![Screenshot der Updates für verwaltete Dienste](../media/update-management-001.jpg)

Im Bereich "Updates" wird eine allgemeine Übersicht über die Updateverwaltung für Ihre Räume mit den folgenden Registerkarten angezeigt:

- **Updates**: Software- oder Firmwareupdates, die verwaltete Dienste durch Ihre Organisation orchestrieren.  
- **Räume**: Die Registerkarte "Räume" bietet einen Blick auf die Räume und Ringe, zu denen die einzelnen Räume gehören.
- **Ringe**: Auf der Registerkarte "Ringe" werden die Ringe von Räumen für Ihre Organisation angezeigt.

### <a name="updates"></a>Updates  

In dieser Ansicht werden die relevanten Updates für Ihren Mandanten und deren jeweiliger Status angezeigt. Wenn Sie frühere Updates anzeigen möchten, die nicht mehr aktiv sind, wählen Sie die Umschaltfläche " **Vergangene Updates einschließen** " auf "EIN" aus.  

Jedes Update kann sich in einem der folgenden Zustände befinden:

| Status | Beschreibung |
|:- |:- |
| Geplant | Für die Räume in einem bestimmten Ring ist ein Update geplant. Bitte beachten Sie, dass ein Update erst angezeigt wird, nachdem die Progression den Ring erreicht hat, in dem sich der Raum befindet. Wenn sich z. B. ein neues Update im Stagingring befindet, wird nur "Geplant für Räume" im Stagingring angezeigt.<br></br><p> Andere Ringe weisen den Status "Nicht erforderlich" auf, bis das Update auf diesen Ring überläuft.</p> |
| Wird ausgeführt | Ein Update wird ausgeführt, und einzelne Ringe zeigen den Status an. Dieser Status zeigt den Gesamtringstatus an. Wenn also ein Update auf einen einzelnen Raum im Stagingring in Ihrem Mandanten angewendet wird, weist das Update den Status "In Bearbeitung" auf, bis der Executive Ring erreicht ist. |
| Abgeschlossen mit Fehlern | Ein Update hat die Weiterentwicklung aller konfigurierten Ringe abgeschlossen und ist in mindestens einem Raum fehlgeschlagen. |
| Abgeschlossen | Ein Update hat die Entwicklung durch alle konfigurierten Ringe abgeschlossen und erfolgreich in allen anwendbaren Räumen installiert.|
| Veraltet | Ein Update wurde deaktiviert. Die weitere Bereitstellung wird angehalten. Dies ist typisch, da das Update durch eine neue Version ersetzt wurde. |
| Angehalten | Ein Update befindet sich in einem angehaltenen Zustand. |
| Nicht erforderlich | Das Update wird entweder noch nicht für den Raum ausgewertet oder gilt nicht für den Raum. |

### <a name="rooms"></a>Zimmer  

Auf der Registerkarte "Räume" werden alle Räume in Ihrem Mandanten angezeigt und zu welchem Ring sie gehören.  

![Screenshot aller Mandantenringe und deren Räume](../media/update-management-002.jpg)

So konfigurieren Sie, zu welchem Ring ein Raum gehören soll:  

1. Klicken Sie auf den Raum, um die detaillierte Ansicht anzuzeigen.  
1. Klicken Sie unter **"Ring**" auf **"Ändern"**.  
1. Wählen Sie den Ring aus, zu dem der Raum gehören soll.  
1. Klicken Sie auf **"Zuweisen"**.  

In der detaillierten Raumansicht werden die relevanten Updates und deren Status unter dem Knoten **"Updates"** angezeigt.  

![Screenshot relevanter Updates und Änderungen](../media/update-management-003.jpg)

### <a name="rings"></a>Ringe  

Ringe werden verwendet, um das Risiko von Problemen zu verringern, die durch die Bereitstellung der Featureupdates entstehen. Dazu wird das Update schrittweise für die gesamte Website bereitgestellt. Jeder Ring sollte über eine Liste der Microsoft Teams Raumräume und einen entsprechenden Rollout-Zeitplan verfügen. Das Definieren von Ringen ist in der Regel ein einmaliges Ereignis (oder zumindest selten), aber die IT sollte diese Gruppen von Zeit zu Zeit erneut überprüfen, um sicherzustellen, dass die Sequenzierung weiterhin korrekt ist.  

Auf der Registerkarte **"Ringe** " werden alle Ringe in Ihrem Mandanten aufgelistet. Es gibt drei vorkonfigurierte Ringe:  

- **Staging**: Weisen Sie dem Stagingring, dem Testbett, Räume zu. Alle neuen Updates werden zuerst hier bereitgestellt. Im Allgemeinen sollten Sie sicherstellen, dass Ihr Stagingring Räume mit der Vielfalt der Gerätetypen in Ihrer Umgebung darstellt. Wenn es bestimmte Arten von Räumen mit einer ungewöhnlichen Konfiguration oder einem Verlauf von Problemen gibt, sollten Sie sie in Staging darstellen.

- **Allgemein**: Standardmäßig werden alle Räume in diesem Ring platziert. Die meisten Raumgeräte, die im gesamten Unternehmen verwendet werden, fallen in diese Kategorie. 

- **Geschäftsleitung**: Diese Gruppe sollte Ihre profilreichsten Räume enthalten, in denen Sie Unterbrechungen proaktiv minimieren möchten. Ein gutes Beispiel ist ein großer Konferenzraum, der für Besprechungen von Führungskräften oder große Teambesprechungen verwendet wird. 

### <a name="specifying-rollout-timeline"></a>Angeben der Rolloutzeitachse

Updates dürfen nicht länger als 60 Tage dauern, bis sie für alle Ringe abgeschlossen werden.  

|Parameter |Erklärung |
|:- |:- |
|Zurückstellungszeitraum|Sobald ein Update mit dem ersten Ring beginnt, ist der Verzögerungszeitraum die Verzögerung in Tagen, bevor das Update für diesen Ring initiiert wird.|
|Rolloutdauer|<p>Sobald das Update auf diesem Ring beginnt, ist dies der Zeitpunkt für die Bereitstellung in diesem Ring. Wenn die Dauer beispielsweise 5 Tage beträgt, wird sie über 5 Tage in den Räumen in diesem Ring bereitgestellt, sobald das Update auf diesem Ring beginnt.|
|Testzeitraum|Die Anzahl der Tage, um das Update in einem Ring zu testen/zu überprüfen, sobald es auf den Ring angewendet wurde. Der Testzeitraum beginnt nach Abschluss des Rollouts, und nach Abschluss des Updates wechselt das Update zum nächsten Ring.|
|Fertigstellungszeit|Die Spalte "Fertigstellungszeit" gibt die Gesamtanzahl der Tage (Rolloutdauer + Testzeitraum) für diesen Ring an.|
|Gesamtzeit|Unten befindet sich die Zeile "Summe", die angibt, wie lange ein Update vom ersten bis zum letzten Ring dauert.|

### <a name="creating-custom-rings"></a>Erstellen benutzerdefinierter Ringe

1. Navigieren Sie zur Registerkarte **"Ringe** ".  
1. Klicken Sie auf **"Ring hinzufügen"**.  
1. Geben Sie die Reihenfolge an, in der dieser Ring das Update erhält, wobei 1 zuerst und 9 der letzte ist.  
1. Geben Sie diesem Ring einen Namen.  
1. Geben Sie bei Bedarf eine Beschreibung an.  
1. Geben Sie die Anzahl der Tage an, die das Update in diesem Ring bereitstellen soll.  
1. Geben Sie den Testzeitraum an.  
1. Klicken Sie auf **"Absenden**".  

> [!NOTE]
> Die "Tage, die von anderen Ringen festgelegt werden" ist die Gesamtanzahl der Tage, die ein Update für alle Ringe dauert. Die "Verbleibenden Tage" geben die maximalen Tage an, die *für diesen* Ring abgeschlossen werden sollen. Die Summe aus "Rolloutdauer in Tagen" und "Testzeitraum in Tagen" darf diesen Betrag nicht überschreiten.  

**Bearbeiten eines Rings**

1. Navigieren Sie zur Registerkarte **"Ringe** ".
1. Klicken Sie auf den Zu löschenden Ring.  
1. Klicken Sie auf **"Ring bearbeiten"**.  
1. Bearbeiten Sie die Anzahl der Tage für Rollout und Tests nach Bedarf.

**Löschen eines Rings**

1. Navigieren Sie zur Registerkarte **"Ringe** ".  
1. Klicken Sie auf den Zu löschenden Ring.  
1. Klicken Sie auf **"Ring löschen"**.  

> [!NOTE]
> Die Standardringe können nicht gelöscht werden.  

**Verschieben von Räumen**

Das Verschieben von Räumen von einem Ring in einen anderen ist auf zwei Arten möglich:

1. Navigieren Sie zur Registerkarte **"Ringe** ".  
1. Klicken Sie auf den Ring, aus dem Sie Räume verschieben möchten  
1. Klicken Sie auf **"Räume verschieben"**.  
1. Wählen Sie die Räume aus, die Sie in der **Liste der Räume** verschieben möchten.  
1. Wählen Sie den Zielring aus, in den die ausgewählten Räume in der Dropdownliste verschoben werden sollen.  
1. Klicken Sie auf **"Räume verschieben"**.  

**Oder**

1. Öffnen Sie die Raumdetails für den Raum, den Sie verschieben möchten (entweder über Vorfälle, Räume oder Updates – > Räume).
1. Klicken Sie auf die Registerkarte " **Updates** ".  
1. Klicken Sie unter **"Zugewiesener Ring**" auf **"Ändern"**.
1. Wählen Sie in der Dropdownliste den neuen Ring aus.  
1. Klicken Sie auf **"Zuweisen"**.

## <a name="managed-updates-visibility-and-control"></a>Verwaltete Updates: Sichtbarkeit und Kontrolle

Verwaltete Dienste orchestrieren Updates in Der gesamten Organisation. Sie haben jedoch die Sichtbarkeit und Kontrolle, um bei Bedarf einzugreifen. Hier sind die Möglichkeiten: 

- Im Falle eines Updatefehlers wird automatisch ein Ticket mit dem Microsoft Managed Service Operations-Team generiert. Das Operations-Team führt Schritte aus, um den Fehler zu beheben und Sie bei Bedarf zu engagieren.  
- Wenn ein Update Probleme verursacht, können Sie das Update mit der Schaltfläche **"Anhalten** " anhalten. Wenn Sie auf die Schaltfläche "Pause" klicken, wird ein Ticket für das Operations Center erstellt, das untersucht werden soll. Stellen Sie beim Anhalten eines Updates unbedingt Details bereit, um die Reaktion auf Vorfälle zu beschleunigen.  
- Wenn in einem Raum ein Update fehlgeschlagen ist und Sie einen plausibelen Grund wie die Netzwerkverbindungstrennung korrigiert haben, können Sie das Update mit der Schaltfläche " **Alle fehlgeschlagenen** Wiederholen" wiederholen.  
- Möglicherweise gibt es dringende Situationen, in der Sie sich dazu entschließen, ein Update früher zur Verfügung zu stellen. In diesem Fall können Sie die Schaltfläche " **Aktualisierungen erzwingen** " verwenden. Wenn Sie die Option "Aktualisierung erzwingen" verwenden, haben Sie die Möglichkeit, das Update sofort oder wenn der nächste Raum verfügbar ist, zu erzwingen.  

> [!NOTE]
> **Es wird nicht empfohlen, "Updates erzwingen"** als allgemeine Updateverwaltungsstrategie zu verwenden. Wenn Sie ein Update pushen, das sich noch in unserem Gültigkeitsprüfungsdurchlauf befindet, treten möglicherweise Probleme auf, die uns bereits bekannt sind. In solchen Fällen wird die Lösung von Vorfällen für solche Räume auf best-effort-Basis erfolgen.  

- Um eine gute Änderungsverwaltung zu gewährleisten, protokollieren wir jede Erzwungene Aktualisierung intern im Dienst. Wir erwarten, dass wir das auch für Sie sichtbar machen.
