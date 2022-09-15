---
title: Microsoft Teams-Räume Portal
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Geben Sie einen Überblick über den Status Ihrer Besprechungsräume.
f1keywords: ''
ms.openlocfilehash: 3587e1ab6e19fa7eac2519ccffe7c8f3bd19f2fc
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67707012"
---
# <a name="microsoft-managed-meeting-rooms-portal"></a>Microsoft Managed Meeting Rooms Portal

## <a name="overview"></a>Übersicht

Das Portal für verwaltete Besprechungsräume ("Chatroomportal") bietet einen Überblick über den Status Ihrer Besprechungsräume. Eine Kundenansicht dieses Portals dient Ihrer Sichtbarkeit und Ihrem Feedback, um Ihre vorhandenen Überwachungstools/-methoden zu vereinfachen.

Der Umfang der Überwachung ist

- Anzeigen von Vorfällen
  - Die wichtigsten Probleme, die Ihre Räume betreffen
  - Erforderliche Aktionen zum Wiederherstellen des fehlerfreien Status von Räumen
  - Probleme, die von Microsoft untersucht werden
- Ansicht der Microsoft Teams-Raumgeräte
  - Momentaufnahme des Status auf Microsoft Teams-Räume (MTR)-Geräteebene
  - Grundlegender Verlauf und Details für jedes Gerät

**Ansicht der Microsoft Teams-Raumgeräte**

- Momentaufnahme des Status auf Microsoft Teams-Räume (MTR)-Geräteebene
- Grundlegender Verlauf und Details für jedes Gerät

> [!Important]
> Lesen [**Sie "Benutzer der Rolle "Verwalteter Dienstadministrator" zuweisen**](enrolling-mtrp-managed-service.md#assign-users-to-the-managed-service-administrator-role) , und stellen Sie sicher, dass der Zugriff auf das Portal basierend auf Ihren Geschäftlichen Anforderungen eingeschränkt ist.

## <a name="terminology"></a>Terminologie

Hier sind häufig verwendete Begriffe im Portal.

|Begriff |Bedeutung |
| :- | :- |
|**Überwachungssoftware** |Überwachungs-Agent, der auf jedem der Microsoft Teams Room-Geräte bereitgestellt wird. |
|**App** |Microsoft Teams Room-System-App (unabhängig davon, ob sie Skype for Business oder Microsoft Teams als Zusammenarbeitsdienst verwendet. |
|**Raum/Gerät** |Das zertifizierte Microsoft Teams Room-Systemgerät. |
|**Nicht überwacht** | Die im Rahmen von verwalteten Diensten bereitgestellte Microsoft-Überwachungssoftware kann keine Verbindung mit den Clouddiensten herstellen. Wir erhalten keine Telemetrie über das Gerät. |
|<p>**Gesund /** </p><p>**Ungesund** </p>|Anomalien im Gerät / Peripheriegerät. |
|**Unterdrückt** |Wenn bekannt ist, dass sich ein Gerät in der Wartung befindet und seine Warnungen ignoriert werden sollten, kann das Gerät absichtlich unterdrückt werden. |
|**Onboarding** |Der Status eines Raumgeräts, während das Setup hinzugefügt wird, ist jedoch nicht als regelmäßig unterstützter Raum bereit. |
|**Vorfall** |Ein Problem, das sich auf Besprechungserfahrungen von Endbenutzern auswirkt, die Maßnahmen benötigen. |
|**Falsch** |Die festgestellte Konfiguration ist nicht korrekt/ wird häufig verwendet. |
|**Supportticket** |Interner Microsoft-Tracking-Bezeichner, der alle Kommunikationen/Aktionen in Bezug auf einen Vorfall nachverfolgt. |

## <a name="incidents-view"></a>Ansicht "Vorfälle"

Diese Ansicht ist eine Übersicht über die Registerkarte "Vorfälle" in Ihrem Portal für verwaltete Räume. Diese Seite ist die Standardstartseite des Portals.

### <a name="top-level-summary"></a>Zusammenfassung auf oberster Ebene 
Die Zusammenfassung auf oberster Ebene zeigt auf einen Blick die Probleme, die Ihre Räume betreffen, was Sie tun müssen und was Microsoft gegen sie tut:

![Screenshot, der eine Zusammenfassung der Probleme auf oberster Ebene zeigt](../media/rooms-monitor-001new.png)

|# |Erklärung |
| :- | :- |
|1 |Arten von Vorfällen, die Ihre Räume betreffen |
|2 |**NEED ACTION**: Items that require your intervention to resolve. |
|3 |**ZUGEWIESEN AN MICROSOFT**: Elemente, die derzeit von Microsoft-Mitarbeitern untersucht werden. |
|4 |**AUSSTEHENDE UNTERSUCHUNG**: Elemente in der Warteschlange, die von Microsoft-Mitarbeitern untersucht werden sollen. |

Vorfälle werden in einem von drei Zuständen erwartet:

- **Aktion erforderlich**: Ihnen zur Aktion zugewiesen
- **Microsoft zugewiesen**: Microsoft für die nächste Aktion zugewiesen
- **Ausstehende Untersuchung**: Wird für die nächsten Schritte untersucht

### <a name="reviewing-incidents"></a>Überprüfen von Vorfällen

In der folgenden Abbildung sind alle Vorfälle aufgeführt, die derzeit in Ihren Räumen aktiv sind. Diejenigen, die Ihnen zugewiesen sind, *befinden sich ganz oben* – dies müssen Sie sich für die nächsten Schritte ansehen. Darüber hinaus verfügen die Microsoft zugewiesenen oder ausstehenden Untersuchungen über Details, die Sie verwenden können, um einzugreifen.

Wenn Sie auf eines der Elemente klicken, die den Status "**Aktion erforderlich**" haben, werden weitere Details zum Vorfall angezeigt.

## <a name="types-of-incidents"></a>Arten von Vorfällen

Vorfälle werden in zwei Arten von schweregraden unterteilt:

- **Wichtig**: Vorfälle, die wahrscheinlich Probleme in Besprechungen verursachen und priorisiert werden sollten.
- **Warnung** – Vorfälle, die Benachrichtigungen zum Planen von Wartungsaktionen sind. Wenn diese nicht erledigt werden, werden die Räume im Laufe der Zeit eher auf ein Problem stoßen. Warnungen sollen Ihnen Zeit geben, die Unterstützung zu planen und zu orchestrieren.

Eine Warnung kann auf "**Wichtig**" umgestellt werden, wenn sie eine Zeit lang nicht beachtet wird.

## <a name="health-status-of-device-and-incidents"></a>Integritätsstatus von Geräten und Vorfällen

Vorfälle, die im Schweregrad als **"Wichtig"** klassifiziert sind, wirken sich auf den Integritätsstatus eines Geräts aus. Wenn mindestens ein Vorfall des **Schweregrads = "Wichtig"** einem Gerät zugeordnet ist, wird es als **_fehlerhaftes_** Gerät klassifiziert.

Vorfälle, die als **Schweregrad "Warnung"** klassifiziert wurden, wirken sich nicht auf den auf einem Gerät gemeldeten Integritätsstatus aus. Wenn einem Gerät jedoch Vorfälle auf Warnstufe zugeordnet sind, wird es wie folgt mit dem Integritätsstatus des Geräts angezeigt.

![Screenshot des Integritätsstatus eines Chatrooms](../media/rooms-monitor-004.jpg)

Im Folgenden finden Sie einige der Arten von Vorfällen, die Möglicherweise angezeigt werden, und die Erläuterungen für jeden Typ. Für jeden Typ ist die dem Vorfall zugeordnete Aktion je nach Problem spezifischer.

**Tabelle 1: Vorfälle mit Schweregrad "Wichtig"**

|Typ |Erklärung |
| :- | :- |
|**Anzeige** |Die mit dem Gerät verbundene Anzeige scheint nicht fehlerfrei zu sein.|
|**Konferenzmikrofon, Konferenzlautsprecher** |Die Audiogeräte (Mikrofon/Lautsprecher) scheinen falsch konfiguriert zu sein. |
|**Kamera** |Die mit dem Gerät verbundene Kamera scheint nicht fehlerfrei zu sein. |
|**HDMI-Aufnahme** |Die HDMI-Aufnahme ist nicht fehlerfrei. |
|**Anmeldung** (Exchange) |Microsoft Teams-Räume App auf Kalenderinformationen aus Exchange zugreift, und jedes Problem mit dem Anmeldeerfolg wird mit einem Anmeldevorfall gemeldet. |
|**Anmeldung** (Teams) |Microsoft Teams-Räume App sich beim Gerät anmeldet und bei diesem Vorfall (wenn der Kunde Teams verwendet) wird eine Anmeldung gemeldet. |
|**Anmeldung** (Skype for Business) |Microsoft Teams-Räume App sich beim Gerät anmeldet, und bei diesem Vorfall wird eine Nichtanmeldung gemeldet (wenn der Kunde Skype for Business verwendet). |
|**Näherungssensor** |Microsoft Teams-Räume App lädt Teilnehmer ein, an einer Besprechung teilzunehmen, wenn sie sich in der Nähe befinden. Fehler in diesem Feature werden im Rahmen dieses Vorfalls gemeldet. |

**Tabelle 2: Vorfälle mit Schweregrad "Warnung"**

|Typ |Erklärung |
| :- | :- |
|**App-Version** |Die Auf dem Gerät ausgeführte Version der Microsoft Teams-Raum-App ist nicht aktuell. Veraltete Versionen sind bekannte Ursachen für Probleme von Benutzern. |
|**Betriebssystemversion** |Die Im Besprechungsraum ausgeführte Version des Windows-Betriebssystems wird nicht mehr empfohlen. |
|**Netzwerk** |Dies wird aufgrund zusätzlicher Arbeit, die nach der Auswertung erforderlich ist, kurzfristig als Warnung entfernt. |

## <a name="responding-to-incidents"></a>Reaktion auf Vorfälle

Vorfälle werden in drei Kategorien unterteilt: "Bedarfsaktion", "Ausstehende Untersuchung" oder "Microsoft zugewiesen".

### <a name="needs-action-incidents"></a>Vorfälle mit "Bedarfsaktion"

Vorfälle, deren Status auf **"Bedarfsaktion"** festgelegt ist, werden Ihnen zugewiesen, um eine Korrekturmaßnahme zu ergreifen.

Jeder solche Vorfall hat ein Aktionsfeld mit einer empfohlenen Aktion von Microsoft wie folgt:

![Screenshot der empfohlenen Vorfallaktion](../media/rooms-monitor-005.jpg)

- Wenn Sie die Aktion ausgeführt haben, können Sie mit Ihren Notizen im Feld "Antworten" auf den Vorfall reagieren und dann vor der Veröffentlichung "Microsoft zuweisen" auswählen.
- Es ist auch möglich, dass die Benachrichtigung basierend auf Ihrer Rezension falsch ist. Geben Sie in diesem Fall bitte dieses Feedback ein, und weisen Sie es Microsoft zurück.
- Wenn Sie schließlich einen Kommentar hinzufügen möchten, um zusätzlichen Kontext für Ihr eigenes Team oder für Microsoft-Team bereitzustellen, posten Sie die Nachricht, ohne "Microsoft zuweisen" zu aktivieren.

>[!NOTE]
>Ihre Korrekturmaßnahme kann das Problem beheben, und die Überwachung verwalteter Räume löscht diesen Vorfall aus Ihrer Liste. In der obigen Situation haben Sie möglicherweise keine Chance, das Problem zu beheben und es wieder Microsoft zuzuweisen. Dieses Problem wird in einer zukünftigen Version behoben.

### <a name="pending-investigation-incidents"></a>Vorfälle "Ausstehende Untersuchung"

Für die untersuchten Vorfälle enthält das Beschreibungsfeld Informationen über den Vorfall, typische Ursachen und Lösungen, die hilfreich sein können, um bestimmte Probleme zu beheben, sodass Sie unverzüglich handeln können.

### <a name="assigned-to-microsoft-incidents"></a>Vorfälle "Microsoft zugewiesen"

Für die Microsoft zugewiesenen Vorfälle enthält das Feld "Aktion" kurze Details zu den geplanten oder fortgeschrittenen Korrekturschritten. Diese Schritte erfordern möglicherweise eine Zusammenarbeit mit Ihrem Team, und die erweiterte Zusammenarbeit erfolgt nach Bedarf per E-Mail/Anruf. Sobald diese Probleme behoben sind, werden sie aus dem Portal verschwinden, und in Zukunft wird es einen Verlauf geben, um solche Vorfälle und ihre Lösung nachzuverfolgen.

![Screenshot der Schritte zur MS-Korrektur](../media/rooms-monitor-006.jpg)

## <a name="rooms-view"></a>Raumansicht

Jedes Gerät ist ein Proxy für einen Raum und seine angeschlossenen Peripheriegeräte. Ein gesundes Gerät stellt einen fehlerfreien Raum dar, und ein fehlerhaftes Gerät stellt einen Raum dar, der während Besprechungen wahrscheinlich Probleme verursacht. Zusätzlich zur Ansicht "Vorfälle" bietet das Portal für verwaltete Räume auch eine Übersicht über die Raumintegrität und hilft Ihnen, Gerätedetails zu beheben und wiederholte Fehler mit dem Vorfallverlauf zu verstehen.

![Screenshot der Übersicht über die Integrität eines Raums](../media/rooms-monitor-007.jpg)

**Fehlerfrei, ungesund, getrennt** Der obere Bereich in der Raumansicht bietet eine schnelle Momentaufnahme, wie viele Ihrer Geräte sich in einem guten Zustand befinden ("Fehlerfrei"), wie viele von Problemen betroffen sind ("Ungesund"), wie viele keine Telemetrie bereitstellen ("Getrennt") und wie viele Geräte von Benachrichtigungen unterdrückt werden (als Außerkraftsetzung). Räume werden anhand von sich entwickelnden Kriterien und Heuristiken auf ihre Gesundheit überwacht. Das Ziel ist es, die Realität der Benutzererfahrung im Raum so genau wie möglich widerzuspiegeln und umsetzbar zu machen.

**Gesunde / ungesunde Räume**:

Geräte/Peripheriegeräte, die keine Vorfälle mit dem Schweregrad "Wichtig" aufweisen, erfüllen die aktuellen Integritätskriterien und werden als fehlerfrei gekennzeichnet. Es bedeutet jedoch nicht, dass es einen Raumausfall für jedes fehlerhafte Gerät im Portal gibt. Der Beschreibungs- und Aktionsteil des Vorfalls enthält spezifischere Details zum Problem und potenziellen Auswirkungen auf die Benutzererfahrung.

**Getrenntes Gerät:**

Der im Rahmen des Managed Rooms-Pilotprojekts bereitgestellte Microsoft-Überwachungs-Agent ist von den Clouddiensten für verwaltete Räume getrennt. Wir erhalten keine Telemetrie über den Raum und haben keinen aktuellen Integritätsstatus. Dies kann auf Netzwerkprobleme, Firewallrichtlinienänderungen oder Änderungen am Geräteimage zurückzuführen sein.

## <a name="room-detail-status-and-changes"></a>Raumdetails: Status und Änderungen

**Raumdetails: Status** Die Registerkarte " *Gerätestatus* " bietet eine konsolidierte Ansicht des Status eines Geräts, aller für das Gerät aktiven Probleme, der Aktionen, die erforderlich sind, um sie zu beheben, oder die fortlaufend sind. Die Registerkarte "Status" enthält auch die Aufschlüsselung der verschiedenen Komponenten der Integrität für das Gerät auf der *Registerkarte "Vorfälle"*. Wenn ein Gerät getrennt ist, sind keine Statusdetails verfügbar.

![Screenshot der konsolidierten Statusansicht](../media/rooms-monitor-008.png)

**Alle Signale anzeigen:** Um alle Signale anzuzeigen, die in einer Signalkategorie enthalten sind, aktivieren Sie die Umschaltfläche "Alle Signale anzeigen". Erweiterungspfeile werden neben Kategorieüberschriften angezeigt, auf die geklickt werden kann, um die Accordion-Ansicht zu erweitern.

![Screenshot mit Signalen in einer Kategorie](../media/rooms-monitor-009.png)

**Suppress/Unsuppress Ticket** Wenn ein Raum registriert ist, geben Sie an, dass Sie Benachrichtigungen zu Änderungen der Raumtelemetrie erhalten möchten. Es gibt Situationen, in denen sich ein bestimmtes Gerät oder Peripheriegerät in einem bekannten Zustand befindet, in dem Sie keine Tickets oder Benachrichtigungen generieren möchten. Wenn Sie die Funktion "Ticket unterdrücken" verwenden, werden alle Benachrichtigungen zu diesem bestimmten Signal stumm geschwenkt. Wenn Sie für den Dienst bereit sind, dieses Signal zu überwachen und Sie darüber zu informieren, heben Sie einfach das einzelne Signal auf.

![Screenshot, der die unterdrückten Tickets des Raums zeigt](../media/rooms-monitor-010.png)

**Erweiterung der Kategorie "Aktives Ticket"** Unter jeder Ticketkategorie werden alle aktiven oder neuesten aufgelösten Tickets zusammen mit dem Schweregrad und dem Zeitpunkt der letzten Aktualisierung des Tickets angezeigt. Durch Klicken auf den Erweiterungspfeil werden alle Tickets mit einem aktiven Link zu den Ticketinformationen angezeigt.

Erweiterung der Kategorie "Aktives Ticket": Unter jeder Ticketkategorie wird jedes aktive oder neueste aufgelöste Ticket zusammen mit dem Schweregrad und dem Zeitpunkt der letzten Aktualisierung des Tickets angezeigt. Durch Klicken auf den Erweiterungspfeil werden alle Tickets mit einem aktiven Link zu den Ticketinformationen angezeigt.

![Screenshot mit aufgelöster Ticketkategorie](../media/rooms-monitor-011.png)

## <a name="active-ticket-overview"></a>Aktives Ticket: Übersicht

Jeder erstellte Vorfall identifiziert das problem, das erkannt wurde, und die Korrekturmaßnahmen, die ergriffen werden müssen, um den Raum in einen fehlerfreien Zustand wiederherzustellen. Das generierte Ticket vermittelt eine Vorfallübersicht mit allen Nachrichten, die von der KI für verwaltete Dienste sowie dem Microsoft-Service engineering-Team generiert werden, das das Problem untersucht. Alle Anlagen, die für die Problembehandlung bei Vorfällen gesammelt wurden, werden aufgelistet. Die Registerkarte "Verlauf" enthält die Datumsangaben, zu denen Probleme identifiziert wurden.

![Screenshot der Übersicht über das aktive Ticket](../media/rooms-monitor-012.png)

Aktives Ticket: Nachrichten Die Nachrichten-UI ist das primäre Kommunikationstool für die Interaktion mit Microsoft-Servicetechnikern, die an der Behebung des identifizierten Problems arbeiten. Es ist wichtig, die Kommunikation von Microsoft zu bestätigen, um sicherzustellen, dass wir Ihnen den bestmöglichen Service bieten. Wenn Sie die empfohlenen Aktionen ausgeführt haben, reagieren Sie auf diesen Vorfall mit Ihren Notizen im Feld "Antworten", und weisen Sie Microsoft zurück, indem Sie vor dem Posten auf "Microsoft zuweisen" klicken.
Es ist auch möglich, dass die Benachrichtigung basierend auf Ihrer Rezension falsch ist. Geben Sie in diesem Fall bitte dieses Feedback ein, und weisen Sie es Microsoft zurück.
Wenn Sie schließlich einen Kommentar hinzufügen möchten, um zusätzlichen Kontext für Ihr eigenes Team oder microsoft-Team bereitzustellen, posten Sie einfach die Nachricht, ohne "Microsoft zuweisen" zu aktivieren.

![Screenshot mit aktiven Ticketmeldungen](../media/rooms-monitor-013.png)


Aktives Ticket: Anlagen Es gibt Situationen, in denen Microsoft-Servicetechniker zusätzliche Informationen benötigen, um ihre Untersuchung des Problems zu erweitern. Die Registerkarte "Anlage" bietet Ihnen die Möglichkeit, bilder, Videos oder Protokolle hochzuladen, die angefordert werden.

![Screenshot mit aktiven Ticketanfügungen](../media/rooms-monitor-014.png)

Aktives Ticket: Verlauf Jedes Raumsignal hat nur eine Ticketnummer, die ihm absichtlich zugewiesen ist. Ein Raumgerät oder Peripheriegerät bleibt in einem Raum erhalten und kann im Laufe der Zeit Probleme haben. Durch die Aufrechterhaltung dieser Informationen unter einer bestimmten eindeutigen Ticket-ID werden alle historischen Informationen beibehalten und können auf Verhaltensmuster analysiert werden. Die Verlaufs-UI bietet eine Ansicht aller Ticketaktionen, die für dieses Signal erstellt und aufgelöst wurden.

![Screenshot des aktiven Ticketverlaufs](../media/rooms-monitor-015.png)

FAQ Wie wirken sich dynamische Tickets auf mich und den Betrieb meiner Räume aus?  
Kunden sehen die Erstellung intelligenterer Tickets und Korrekturen, die über ein binäres Signalticket hinausgehen. Beispielsweise können in einem Besprechungsraum bis zu drei Anzeigen vorhanden sein (Anzeige 1, Anzeige 2 & MTR-Touchpanelanzeige). Es gibt jedoch nur 1 (ein) Anzeigesignal, das entweder fehlerfrei oder fehlerhaft ist. Mit den neuen dynamischen Tickets können wir jetzt Tickets generieren, die für jedes Anzeigesignal eindeutig sind.
