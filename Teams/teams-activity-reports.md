---
title: Verwenden Sie Berichte für Microsoft-Teams
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
description: Hier erfahren Sie, wie Sie Berichte, um zu sehen, wie Benutzer in Ihrer Organisation Microsoft-Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9c4c811505d8f5642fe4c0b79b511624a3b07b6
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860279"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Verwenden Sie Berichte für Microsoft-Teams 
========================================

Berichte können Sie sehen, wie Benutzer in Ihrer Organisation Microsoft-Teams verwenden. Beispielsweise wenn einige noch nicht Teams verwenden, können sie nicht wissen, wie steigen oder zu verstehen, wie diese Teams werden produktiver und Zusammenarbeit verwenden können. Die Berichte können Ihre Organisation entscheiden, wo Schulung und Kommunikation Maßnahmen priorisieren möchten.

## <a name="how-to-get-to-the-reports-dashboard"></a>Wie Sie dem Dashboard Berichte abrufen

1. Wählen Sie in der [Office 365 Administrationscenter](https://portal.office.com/adminportal/home) **Berichte**aus > **Usage**.
 
2. Wählen Sie auf der Seite **Usage** Auswahl aus einer Liste der verfügbaren Berichte **Wählen Sie einen Bericht** . 

## <a name="teams-activity-reports-that-are-available"></a>Teams Berichte, die verfügbar sind

Derzeit gibt es zwei Berichte, die Sie anzeigen können:

- Bericht über Benutzeraktivität Microsoft-Teams 
- Bericht zur Verwendung der Microsoft-Teams Gerät 

### <a name="microsoft-teams-user-activity-report"></a>Bericht über Benutzeraktivität Microsoft-Teams

Microsoft-Teams, User Activity Report bietet eine Ansicht der am häufigsten verwendeten Aktionen, die in Microsoft-Teams, die Benutzer ausführen. Dazu gehören, wie viele Personen einen Chat in einem Kanal beteiligen, wie viele über private Chatnachricht kommunizieren und wie viele Anrufe oder Besprechungen teilzunehmen. Sie können diese Informationen auf der Ebene der Mandant sowie für jeden einzelnen Benutzer angezeigt.

![Screenshot des Teams User Activity Report im Office 365 Administrationscenter.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Microsoft-Teams, User Activity Report interpretieren

Betrachten die **Aktivität** , und **Benutzer** Diagramme, um eine Ansicht in Microsoft-Teams Benutzeraktivität zu erhalten.

![Screenshot des Teams User Activity Report im Office 365 Administrationscenter mit nummerierten Beschriftungen.](media/teams-user-activity-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Microsoft-Teams, User Activity Report kann über den letzten sieben Tagen 30 Tage, 90 Tage oder nach 180 Tagen für Trends angezeigt werden. Wenn Sie in einen bestimmten Tag im Bericht klicken, wird jedoch die Tabelle (7) Daten für 30 Tage, bis zu dem Datum (2) für angezeigt, wenn der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die Ansicht **Aktivität** wird die Anzahl der Microsoft-Teams, Aktivitäten nach Aktivitätstyp. Die Aktivität sind Anzahl von teams Chatnachrichten, private Chatnachrichten, anrufen oder Besprechungen. |
|**4**   |Die **Benutzer** -Ansicht zeigt Sie die Anzahl der Benutzer nach Aktivitätstyp. Die Aktivität sind Anzahl von teams Chatnachrichten, private Chatnachrichten, anrufen oder Besprechungen. |
|**5**   |Die x-Achse auf Diagramme ist des ausgewählten Datumsbereichs für den Bericht an. <ul><li>Im Diagramm **Aktivität** ist die y-Achse die Anzahl der angegebenen Aktivität.</ul></li> <ul><li>Im Diagramm **Dateien** ist die y-Achse die Anzahl der Benutzer beteiligt Teams Chats, private Chats, anrufen oder Besprechungen.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Beispielsweise das Diagramm **Aktivität** klicken Sie oder tippen Sie **Channel Nachrichten**, **Nachrichten Chat**, **Anrufen**oder **Besprechungen** , um nur die Informationen im Zusammenhang mit jeweils finden Sie unter. Das Ändern dieser Auswahl ändert nicht die Informationen in der Tabelle Raster. |
|**7**   |Die Liste der angezeigten Gruppen wird bestimmt, durch den Satz aller Gruppen, das vorhanden war (wurden nicht gelöscht) über den längsten (180-tägige) reporting Zeitrahmen.  Die Anzahl der Aktivitäten variiert entsprechend der Auswahl des Datums. <ul><li>**Benutzername** ist die e-Mail-Adresse des Benutzers. Sie können die tatsächliche e-Mail-Adresse anzuzeigen oder dieses Feld anonyme machen.</ul></li> <ul><li>**Letzte Aktivität Datum (UTC)** bezieht sich auf das Datum der letzten, das der Benutzer in einer Microsoft-Teams, Aktivität verwendet wurde.</ul></li> <ul><li>**DDE-Kanal-Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer gebucht in einem Chat Team während des angegebenen Zeitraums.</ul></li> <ul><li>**Chatnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer in einem privaten Chat während des angegebenen Zeitraums veröffentlicht.</ul></li> <ul><li>**Anrufe** ist die Anzahl der Anrufe, die der Benutzer teilgenommen während des angegebenen Zeitraums.</ul></li> <ul><li>**Besprechungen** ist die Anzahl von onlinebesprechungen, die der Benutzer aus der angegebenen Zeitraum verwendet wurde.</ul></li> <ul><li>**Andere Aktivitäten** ist die Anzahl der anderen Teamaktivitäten durch den Benutzer.</ul></li> <ul><li>**Deleted** gibt an, ob das Team gelöscht wird. Wenn das Team wird gelöscht, aber die Aktivität des Berichtszeitraums bot, wird es im Raster mit gelöschten Festlegung auf "true" angezeigt.</ul></li> <ul><li>**Deleted** ist das Datum, das das Team gelöscht wurde.</ul></li> <ul><li>**Produkt zugewiesen** ist die Liste der Produkte, die dem Benutzer zugewiesen sind.</ul></li> <ui>**Hinweis:** Alle Elemente in der Liste unten in den Spalten möglicherweise nicht angezeigt werden, bis Sie diese hinzufügen. </ul><br><br> <ui>Wenn Richtlinien Ihrer Organisation verhindert, dass Sie Berichte anzeigen, in dem Benutzerinformationen erkennbar ist, können Sie die für den Datenschutz für alle diese Berichte ändern. Checken Sie die **wie blenden Sie Ebene Benutzerdetails?** Abschnitt in der [Aktivitätsberichte in Office 365 Admin Center Preview](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Klicken oder tippen Sie auf **Spalten**, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen. |
|**9**   |Sie können auch die Daten des Berichts in eine Excel-CSV-Datei exportieren, durch Klicken oder tippen auf den Link exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Wenn Sie weniger als 2.000 Benutzer verfügen, können Sie zum Sortieren und Filtern in der Tabelle im Bericht selbst. Wenn Sie mehr als 2.000 Benutzer in der Reihenfolge zum Filtern und Sortieren haben, müssen Sie die Daten exportiert werden. |

### <a name="microsoft-teams-device-usage-report"></a>Bericht zur Verwendung der Microsoft-Teams Gerät

Der Microsoft-Teams, app-Verwendungsbericht enthält Informationen, wie die Benutzer mit Microsoft-Teams, einschließlich mobiler apps verbinden. Der Bericht hilft Ihnen zu verstehen, welche Geräte in Ihrer Organisation beliebt sind und wie viele Benutzer unterwegs arbeiten.

![Screenshot des Nutzungsberichts Teams Gerät im Office 365 Administrationscenter.](media/teams-device-usage-report.png)

## <a name="who-can-access-the-teams-activity-reports"></a>Wer kann die Teams Berichte zugreifen

Von Benutzern, die zugewiesen sind, können die Berichte zugegriffen werden:

- Office 365 globalen Administratorrolle
- Produktspezifische Administratorrolle (Exchange, Skype für Geschäftskunden und SharePoint)
- Berichte Reader-Rolle

### <a name="reports-reader-role"></a>Berichte Reader-Rolle

Sie können die Rolle *Leser von Berichten* außer IT-Mitarbeiter zuweisen, die Zugriff auf diese Berichte werden soll. Schulung-Manager oder Projektbeteiligten diese Rolle zuweisen, können Sie sicherstellen, dass die Insights zugreifen kann, die auf Laufwerk und Nachverfolgen Akzeptanz Teams hilfreich sind.

## <a name="other-information-on-the-reports-dashboard"></a>Weitere Informationen auf das Dashboard Berichte

### <a name="at-a-glance-activity-widget"></a>Widget-Aktivität auf einen Blick

Das Dashboard Berichte enthält die Verwendungsdaten in den Microsoft-Teams, in das Widget auf einen Blick Aktivität, das Sie haben eine Ansicht produktübergreifende wie Benutzer kommunizieren und zusammenarbeiten mit anderen verschiedene Dienste in Office 365.

![Screenshot des Widgets Teams Aktivität auf einen Blick auf das Dashboard Berichte.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Teams Aktivität Karte

Das Dashboard Berichte enthält außerdem eine neue Karte für Microsoft-Teams. Die Visitenkarte bietet eine Übersicht über die Aktivität bei Teams, einschließlich der Anzahl von aktiven Benutzern, sodass Sie schnell verstehen, welche die Anzahl der Benutzer den Dienst verwenden.

![Screenshot der Karte Aktivität Teams auf das Dashboard Berichte.](media/teams-activity-card.png)
