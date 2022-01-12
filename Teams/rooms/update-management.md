---
title: Microsoft Teams-Räume der Updateverwaltung
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
ms.openlocfilehash: 763eece92a65aa8ca70728854a1af8970fd13d25
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767501"
---
# <a name="update-management"></a>Updateverwaltung 
Ein moderner Besprechungsraum ist mit einem Microsoft Teams-Räume-Gerät und anderen Peripheriegeräten wie einer Kamera, einem Mikrofon oder einem Lautsprecher ausgestattet und bietet potenziell mehr Geräte, um eine inklusive und effektive Besprechungserfahrung zu schaffen. Geräte von verschiedenen Arten von OEMs bieten genau die gewünschte Organisationserfahrung. müssen jedoch kontinuierlich mit Software und Firmware verwaltet werden.  

Verwaltete Dienste für Microsoft Teams-Räume bietet die Garantie, dass jeder Raum in Ihrer Organisation auf empfohlenen Ebenen verwaltet wird, um einen Raum zu erhalten, der immer bereit ist und ordnungsgemäß funktioniert. Das Ziel von Microsoft ist es, Komplexität und Lesbarkeit für Ihre Mitarbeiter mit Intelligence und Automatisierung zu reduzieren. Die Problembehandlung oder Diagnose erfolgt so schnell wie möglich. 

## <a name="transitioning-a-device-to-managed-services"></a>Umstieg eines Geräts auf verwaltete Dienste 
Raumgeräte, die in verwaltete Dienste integrieren, verfügen in der Regel über einen Änderungsverwaltungsverlauf und eine andere Vorgehensweise als unsere Anleitung.  

- Um von verwalteten Diensten zu profitieren, müssen Sie die Änderungsverwaltung für alle Updates unter Portfolio "Verwaltete Dienste" ändern.
- Mehrere Quellen für SLAs mit Auswirkungen auf das Änderungsmanagement, da es eine Ermittlung und Behebung gibt, die neu gestartet wird, wenn im Raum ein Vorfall geschieht.
- Microsoft hat Steuerelemente und Prüfungen implementiert, um Richtlinien zu implementieren, die von Organisation zu Organisation unterschiedlich sein können, sowie die Möglichkeit, in Ausnahmefällen eingreifen zu können.
- Schließlich werden die Raumgeräte auf allgemeine Standards aktualisiert, mit Ausnahme von Ausnahmen aufgrund von Problemen bei einer bestimmten Hardwareinstallation.  

## <a name="transitioning-devices-basic-readiness-checks"></a>Gerätewechsel: Grundlegende Bereitschaftsüberprüfungen 
Die meisten unerwarteten Fehler entstehen durch Änderungen im Basisbild mit unsicherem Verlauf des Änderungsmanagements. 

Die folgenden einfachen Bereitschaftsüberprüfungen werden empfohlen:  

- **Basisbild:** Das Basisbild muss vom jeweiligen OEM kommen. Wenn das Gerät in der Vergangenheit neu erstellt wurde und unerwartete Fehler oder Verhalten für allgemeine Aufgaben angezeigt wird, muss das Basisbild wiederhergestellt werden. Wir können Unterstützung bieten, aber das Raumgerät nicht remote neu erstellen, daher benötigen Sie einen lokalen Websitetechniker.  
- **Base OS, Edition:** Das Basisbetriebssystem und die Basisversion müssen den Anforderungen der Microsoft Teams-Räume entsprechen. Wenn dies nicht zu tun ist, muss dies im Rahmen des Onboardings korrigiert werden. Microsoft Teams-Räume benötigt die Windows 10 IoT Enterprise oder Windows 10 Enterprise unter Semi-Annual Channel-Wartungsoptionen. Weitere Informationen finden [Sie im offiziellen MTR-Leitfaden.](rooms-lifecycle-support.md#windows-10-release-support)

## <a name="readiness-checks"></a>Bereitschaftsüberprüfungen   
Es gibt einige Voraussetzungen für den Empfang von Updates für verwaltete Dienste: 

|Software |Anleitung |
| :- | :- |
|Logitech Sync Services  |Sollte auf den Geräten des Logitech-Besprechungsraums installiert und ausgeführt werden. Erforderliche Synchronisierungsdienste werden automatisch über Updates Windows installiert, es sei denn, sie sind blockiert. Das vollständige Synchronisierungspaket kann ebenfalls installiert werden. |
|Windows von Betriebssystemupdates |Sollte aktiviert und nicht zu WSUS umgeleitet oder aus Netzwerkperspektive blockiert werden. Weder GPO- noch MDM-Richtlinien sollten zum Verwalten von Betriebssystemupdates verwendet werden. |
|Microsoft Store Updates   |Sollte deaktiviert sein. Verwaltete Dienste deaktivieren alle Store, falls diese installiert sind. |
|Antivirensoftware |Wenn Sie AV-Software auf diesen Geräten ausführen, sollten Sie sicherstellen, dass für AV-Dateien Teams und Skype sind. Weitere Details finden Sie hier. |
|Zusätzliche Software |Zusätzliche Software, z. B. Remotedesktopanzeige von Drittanbietern usw., sollte mit verwalteten Diensten überprüft werden, damit Nebeneffekte ausgeschlossen werden. |
|Zusätzliche Änderungsverwaltung|Dies kann die behandelten Updates beeinträchtigen und sollte nicht eingeführt werden. |

## <a name="managed-updates--how-it-works"></a>Verwaltete Updates – Funktionsweise 
Es gibt zwei Hauptwege, wie Updates verwaltet werden:  

- **Automatisch verwaltet:** Updates werden auf Ihrem Raumgerät basierend auf der Bewertung verwalteter Dienste installiert. Für die in unserem Portfolio verwalteten Updates sind keine Maßnahmen erforderlich.
- **Ring überprüft: Richten Sie** ein Ringsystem ein, um Updates auf bestimmten Geräten in der Vorschau anzuzeigen, damit Sie sie ohne die zugehörigen Leg-Arbeit überwachen können. Das Ring-Setup bietet eine zusätzliche Schicht fälliger Sorgfalt vor dem umfassenden Rollout.  

### <a name="automatically-managed"></a>Automatisch verwaltet

Wenn Sie sich für die automatische Aktualisierung entscheiden, ist für die Aktualisierungen Ihrer Organisation keine Aktion erforderlich. Sie sollten jedoch das aktuelle Portfolio von Updates überprüfen, die von verwalteten Diensten unterstützt werden. Das Portfolio wird ständig um neue Ergänzungen erweitert, und es ist unsere Priorität, die häufigsten und stärksten Updates zu umfassen, um die Stabilität Ihres Platzes sicherzustellen. Überprüfen Sie die aktuelle Liste (im Abschnitt "Updateverwaltung" in diesem Dokument), um weitere für Ihre Organisation benötigte Änderungsverwaltung zu planen.  

**Empfehlung:** Installieren Sie keine Updates, die von verwalteten Diensten abgedeckt werden, auf einem verwalteten Gerät. Wenn Probleme auftreten, melden Sie einen Vorfall im Portal.

### <a name="ring-validation"></a>Ringüberprüfung

Wenn Sie die Ringüberprüfung auswählen, lesen Sie die folgenden Abschnitte zur Funktionsweise von Ringen in Verwalteten Diensten und zu den Optionen, mit denen Sie diese für Ihre Organisation anpassen können. Selbst mit der Ringüberprüfung versucht verwaltete Dienste sicherzustellen, dass die Räume bei empfohlenen Updates nicht fällig sind. Je nach Situation erhält ein Raum möglicherweise Aktualisierungen für auf dem neuesten Stand, um sicherzustellen, dass er den Empfehlungen für verwaltete Dienste entspricht.  

 Überprüfen Sie auf der Startseite des Portals und in der Dokumentation für verwaltete Dienste nach Ankündigungen, da neue Software- und Firmwaretypen im Portfolio verfügbar werden. Da Experten für verwaltete Dienste Updateversionen täglich über unser Geräteportfolio überprüfen, befassen sie sich mit bestimmten Problemen und zielen Updates je nach Bedarf an.  


### <a name="scheduling"></a>Zeitplanung 
Verwaltete Updates werden für Räume basierend auf den Geräten im Raum geplant und entsprechen nicht den Standards der verwalteten Dienste für anwendbare Software und Firmware.  

- Um unsere Kunden dabei zu unterstützen, die **Änderungsverwaltungsanforderungen** zu erfüllen, starten Sie die Bereitstellung am Mittwoch im Staging Ring. Wenn ein kritisches Update erforderlich ist, umgehen wir diesen Zeitplan und geben das Update frei, sobald es verfügbar ist. 

- Aktualisierungen werden basierend auf der Notwendigkeit in einem bestimmten Raum sequenziert. 
- Wenn Sie Setup-Ringe haben, um die Updates zu überprüfen, wird das Update in der Ringreihenfolge ausgeführt. 
- Ein neues Update kann ein Update, das in die Warteschlange eingereiht wird, absprechen, wenn wir feststellen, dass die Raumstabilität basierend auf Ihrer Situation verbessert wird.  
- Updates werden in der Regel während des nächtlichen Wartungsfensters angewendet, d. h. lokal von **12:00 Uhr bis 5:00** Uhr, um Unterbrechungen zu vermeiden. 

## <a name="microsoft-teams-room-app-update-lifecycle-policy"></a>Microsoft Teams Richtlinie zum Aktualisieren von Raum-Apps 
Die Supportrichtlinie des MTR-Entwicklungsteams besagt, dass der Support nach Ablauf des zwölf (12)-Monatslebenszyklus für eine Version abgelaufen ist oder bis jetzt mehr als zwei Updates veröffentlicht wurden. Kunden müssen dann eine Aktualisierung auf eine unterstützte Version durchführen. Bitte referenziert [Microsoft Teams-Räume Support für App-Versionen – Microsoft Teams | Eine detaillierte Dienstbeschreibung ](rooms-lifecycle-support.md)finden Sie unter Microsoft Docs. 

Um für alle verwalteten Räume einen einheitlichen Standard zu erhalten und um Trendprobleme effizient erkennen zu können, werden wir die beiden neuesten Haupt- oder Nebenversionen (N, N-1) der MTR-App-Software nach den Geschäftsbedingungen für Support- und Abonnementdienste unterstützen und bereitstellen. Nicht kompatible Räume werden automatisch auf dem neuesten Stand angezeigt, und die Aktualisierungsringe werden bei Bedarf umgangen. 

Die N-1-Richtlinie gilt auch für Drittanbietersoftware.  

## <a name="update-management-experience-walk-through"></a>Exemplarischen Weg zur Aktualisierungsverwaltung  
Zum Anzeigen von Updates melden Sie sich beim Portal für verwaltete Dienste an, und navigieren Sie zur Seite Updates. 

![Alternativtext1](../media/update-management-001.jpg) 


Im Bereich Updates wird eine Übersicht über die Updateverwaltung für Ihre Räume mit den folgenden Registerkarten angezeigt: 

- **Updates:** Software- oder Firmwareupdates, die Verwaltete Dienste in Ihrer Organisation orchestrieren.  
- **Räume:** Auf der Registerkarte Räume wird eine Ansicht der Räume und Ringe angezeigt, zu denen die einzelnen Räume gehören. 
- **Ringe:** Auf der Registerkarte Ringe werden die Ringe von Räumen für Ihre Organisation angezeigt. 





### <a name="updates"></a>Updates  

In dieser Ansicht werden die relevanten Updates für Ihren Mandanten und deren jeweiligen Status angezeigt. Zum Anzeigen vergangener Updates, die nicht mehr aktiv sind, wählen Sie die Umschalte vergangene Aktualisierungen **mit** EIN aus.  



Jedes Update kann sich in einem der folgenden Zustände begnen: 

|Status |Beschreibung |
| :- | :- |
|Geplant |Für die Räume in einem bestimmten Ring ist eine Aktualisierung geplant. Beachten Sie, dass eine Aktualisierung nur dann Geplant wird, wenn die Entwicklung den Ring erreicht, in dem sich der Raum befindet. Wenn sich z. B. ein neues Update im Staging-Ring befindet, würde nur Für Räume im Staging-Ring geplant anzeigen. Andere Ringe haben den Status "Nicht erforderlich", bis das Update zu diesem Ring fortschreitet.    |
|In Bearbeitung |Eine Aktualisierung wird ausgeführt, und einzelne Ringe zeigen den Status an. Dieser Status zeigt den Gesamtringstatus an. Wenn also ein Update für einen einzelnen Raum im Staging-Ring Ihres Mandanten gilt, weist das Update den Status "In Bearbeitung" auf, bis der Executive Ring erreicht ist.    |
|Abgeschlossen mit Fehlern |Eine Aktualisierung hat die Entwicklung über alle konfigurierten Ringe abgeschlossen und ist in mindestens einem Raum fehlgeschlagen. |
|Abgeschlossen |Ein Update hat die Entwicklung über alle ihre konfigurierten Ringe abgeschlossen und erfolgreich in allen anwendbaren Räumen installiert. |
|Veraltet |Eine Aktualisierung wurde deaktiviert. Die weitere Bereitstellung wird gestoppt. Dies ist typisch, weil das Update durch eine neue Version ersetzt wurde.  |
|Angehalten |Ein Update ist angehalten.  |
|Nicht erforderlich |Die Aktualisierung wird entweder noch nicht für den Raum ausgewertet oder gilt nicht für den Raum.  |

### <a name="rooms"></a>Räume  

Auf der Registerkarte Räume werden alle Räume in Ihrem Mandanten angezeigt und zu welchem Ring sie gehören.  



![Alternativtext2](../media/update-management-002.jpg) 



So konfigurieren Sie, zu welchem Rufton ein Raum gehören soll:  

1. Klicken Sie auf den Raum, um die Detailansicht zu sehen.  
1. Klicken Sie unter "Ring" auf die Schaltfläche "Ändern".  
1. Wählen Sie den Klingelton aus, zu dem der Raum gehören soll.  
1. Klicken Sie auf Zuweisen.  

In der detaillierten Raumansicht werden die relevanten Updates und deren Status unter dem Knoten "Updates" angezeigt.  


![Alternativtext3](../media/update-management-003.jpg) 

### <a name="rings"></a>Ringe  

Ringe werden verwendet, um das Risiko von Problemen zu verringern, die durch die Bereitstellung der Featureupdates abgeleitet werden. Dazu wird das Update schrittweise auf der gesamten Website bereitgestellt. Jeder Ring sollte eine Liste der Microsoft Teams Raumräume und einen entsprechenden Rolloutzeitplan enthalten. Das Definieren von Ringen ist im Allgemeinen ein einmalereignis. 

(oder zumindest selten), doch sollte die IT diese Gruppen von Zeit zu Zeit erneut aufarbeiten, um sicherzustellen, dass die Reihenfolge weiterhin korrekt ist.  

Auf der Registerkarte "Ringe" werden alle Ringe Ihres Mandanten aufgeführt. Es gibt drei vorkonfigurierte Ringe:  

**Staging**  

Weisen Sie dem Staging-Ring, bei dem es sich um Ihr Testbett handelt, Räume zu. Alle neuen Updates werden zuerst hier veröffentlicht. Im Allgemeinen sollten Sie sicherstellen, dass Ihr Stagingring Räume mit der Vielfalt der Gerätetypen in Ihrer Umgebung darstellt. Wenn es bestimmte Typen von Räumen mit einer ungewöhnlichen Konfiguration oder eine Verlaufshistorie von Problemen gibt, sollten Sie sie unter Staging darstellen.

**Allgemein**  

Standardmäßig werden alle Räume in diesem Ring platziert. Die meisten Raumgeräte, die im Unternehmen verwendet werden, fallen in diese Kategorie. 

**Führungskräfte**  

Diese Gruppe sollte Ihre profilreichsten Räume enthalten, in denen Sie Unterbrechungen proaktiv minimieren möchten. Ein gutes Beispiel ist ein großer Konferenzraum, der für Besprechungen von Führungskräften oder große Teambesprechungen verwendet wird. 

### <a name="specifying-rollout-timeline"></a>Angeben der Rolloutzeitachse 

Updates dürfen maximal 60 Tage dauern, bis sie über alle Ringe hinweg abgeschlossen sind.  

|**Parameter** |**Erklärung** |
| :- | :- |
|<p> </p><p>Zeitraum für die Zurückfristung </p>|<p>Sobald ein Update mit dem ersten Ring beginnt, ist der Verzögerungszeitraum die Verzögerung in Tagen, bevor das Update für diesen Ring initiiert wird.  </p><p> </p>|
|<p> </p><p>Rolloutdauer  </p><p> </p>|<p>Sobald das Update in diesem Ring begonnen wird, ist es an der Zeit, die Bereitstellung in diesem Ring zu starten. Wenn die Dauer beispielsweise 5 Tage beträgt, werden mehr als 5 Tage für die Räume in diesem Ring bereitgestellt, sobald das Update in diesem Ring beginnt. </p><p> </p>|
|<p> </p><p>Testzeitraum </p>|<p><p>Die Anzahl der Tage zum Testen/Überprüfen des Updates in einem Ring, nachdem es auf den Ring angewendet wurde. Der Testzeitraum beginnt nach Abschluss des Rollouts, und nach Abschluss des Updates wechselt das Update zum nächsten Ring. </p><p> </p>|
|<p> </p><p>Abschlusszeit </p>|<p> </p><p>In der Spalte "Abschlusszeit" wird die Gesamtzahl der Tage (Rolloutdauer + Testzeitraum) für diesen Ring angegeben.  </p><p> </p>|
|<p> </p><p>Gesamtzeit </p>|<p> </p><p>Am unteren Rand befindet sich die Zeile "Summe", die angibt, wie lange ein Update vom ersten bis zum letzten Ring dauern wird. </p><p> </p><p> </p>|

### <a name="creating-custom-rings"></a>Erstellen von benutzerdefinierten Ringen 



1. Navigieren Sie zur Registerkarte "Ringe".  
1. Klicken Sie auf "Ring hinzufügen".  
1. Geben Sie die Reihenfolge an, in der dieser Ring das Update erhält, wobei 1 der erste und 9 der letzte ist.  
1. Geben Sie diesem Ring einen Namen.  
1. Geben Sie bei Bedarf eine Beschreibung an.  
1. Geben Sie die Anzahl der Tage an, für die das Update in diesem Ring verfügbar sein soll.  
1. Geben Sie den Testzeitraum an.  
1. Klicken Sie auf Absenden.  


> [!NOTE]
> Die Anzahl der Tage, die von anderen Ringen festgelegt werden, ist die Gesamtanzahl der Tage, die ein Update für alle Ringe dauert. Der Wert "Verbleibende Tage" gibt die maximalen Tage bis *zum Abschluss dieses* Rings an. Die Summe von "Rolloutdauer in Tagen" und "Testzeitraum in Tagen" darf diesen Betrag nicht überschreiten.  



**Bearbeiten eines Rings** 


1. Navigieren Sie zur Registerkarte "Ringe".  
1. Klicken Sie auf den Ring, der bearbeitet wird.  
1. Klicken Sie auf "Ring bearbeiten".  
1. Bearbeiten Sie die Anzahl der Tage für die Einführung und die Tests nach Bedarf. 


**Löschen eines Rings** 

1. Navigieren Sie zur Registerkarte "Ringe".  
1. Klicken Sie auf den Ring, der gelöscht wird.  
1. Klicken Sie auf "Ring löschen".  



> [!NOTE]
> Die Standardringe können nicht gelöscht werden.  



**Verschieben von Räumen** 

Das Verschieben von Räumen von einem Ring in einen anderen ist auf zwei Arten möglich: 



1. Navigieren Sie zur Registerkarte "Ringe".  
1. Klicken Sie auf den Ring, aus dem Sie Räume verschieben möchten.  
1. Klicken Sie auf "Räume verschieben".  
1. Wählen Sie in der "Liste der Räume" die Räume aus, die Sie verschieben möchten.  
1. Wählen Sie den Zielring aus, zu dem die ausgewählten Räume in der Dropdownliste wechseln.  
1. Klicken Sie auf "Räume verschieben".  

**Oder**

1. Öffnen Sie die Raumdetails für den Raum, den Sie verschieben möchten (entweder über Vorfälle, Räume oder Updates > Räume).   

1. Klicken Sie auf die Registerkarte "Updates".  
1. Klicken Sie unter "Zugewiesener Ring" auf "Ändern".  
1. Wählen Sie in der Dropdownliste den neuen Ring aus.  
1. Klicken Sie auf "Zuweisen". 


## <a name="managed-updates-visibility-and-control"></a>Verwaltete Updates: Sichtbarkeit und Kontrolle  
Verwaltete Dienste orchestrieren Updates in der gesamten Organisation. Sie verfügen jedoch über die Sichtbarkeit und das Steuerelement, die bei Bedarf eingreifen können. Hier sind die Möglichkeiten: 



- Bei einem Updatefehler wird automatisch ein Ticket mit dem Team für verwaltete Dienste von Microsoft generiert. Das Operations team will take steps to bemediate the failure and engage you if necessary.  
- Wenn ein Update angezeigt wird, das Probleme verursacht, können Sie das Update mit der Schaltfläche **Anhalten** anhalten anhalten. Durch Klicken auf die Schaltfläche Anhalten wird ein Ticket für das Operations Center erstellt, das untersucht werden soll. Geben Sie beim Anhalten eines Updates unbedingt Details an, um die Reaktion auf Vorfälle zu beschleunigen.  
- Wenn Sie sehen, dass ein Update in einem Raum fehlgeschlagen ist, und Sie einen  verständlichen Grund wie die Netzwerkverbindung behoben haben, können Sie das Update mit der Schaltfläche Alle fehlgeschlagen wiederholen.  
- Es kann dringende Situationen geben, in denen Sie sich entscheiden, ein Update früher zur Verfügung zu stellen. In diesem Fall können Sie die Schaltfläche **Updates erzwingen** verwenden. Wenn Sie die Option Update erzwingen verwenden, haben Sie die Möglichkeit, die Aktualisierung sofort oder wenn als Nächstes der Raum verfügbar ist zu erzwingen.  



<!--![alt text4](media/update-management.004.jpg)-->  

> [!NOTE]
> **Wir empfehlen nicht "Updates erzwingen"** als allgemeine Updateverwaltungsstrategie. Wenn Sie eine Aktualisierung pushen, die sich noch im Überprüfungspass befindet, können Probleme auftreten, über die wir bereits wissen. In solchen Fällen wird die Lösung von Vorfällen für solche Räume nach bestem Aufwand durchgeführt.  

- Um bewährte Methoden für die Verwaltung von Änderungen sicherzustellen, protokollieren wir außerdem jede erzwingende interne Aktualisierung im Dienst. In Zukunft wird dies auch für Sie sichtbar sein. 



<!--![alt text5](media/update-management.005.jpg) 


## Managed updates: FAQS 
1. **An update was announced, but I don’t see it on my Updates tab.** 

Updates roll out through our update rings. It won’t display in your tab until the update has passed the staging ring. 



2. **Will my new rooms automatically get updated?** 

Yes. We catch up with any new rooms on the necessary updates. 
**


3. **What if I have an Anti-virus running? Do I need to add exclusions?** 

Suppose you are using an anti-virus or just started using a new anti-virus. In that case, it might cause failures to launch meetings in the room console by interfering with the launch of related software libraries and executables from Teams or Skype for Business. Please contact our support team to get assistance on this issue. 

4. **I reimaged a room. Will the updates automatically get installed?** 

Unfortunately, not at this time. Previous updates need to be manually reinstalled. We are working on a feature to address this scenario. 

5. **I see an update failed. What action should I take to make it successful?** 

Our 24/7 operations team troubleshoot all update failures and will contact you if you need to take any action.  

6. **What updates can we force?** 

Any and all active updates can be forced. 

7. **When is my update starting?** 

Staging rings start on Wednesday. We are making improvements to the portal so you can see what day each of your rings starts depending on your configuration. If a critical update is required, we will bypass this schedule and release the update as soon as it’s available. -->

