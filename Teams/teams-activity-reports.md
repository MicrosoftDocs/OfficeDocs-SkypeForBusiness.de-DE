---
title: Verwenden von Aktivitätsberichten für Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Hier erfahren Sie, wie Sie Berichte, um zu sehen, wie Benutzer in Ihrer Organisation Microsoft-Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34ae95d405e9ab1f35c81db0d61ee48ba18141cf
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463372"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Verwenden von Aktivitätsberichten für Microsoft Teams 
========================================

Können Berichte in der Microsoft-365-Verwaltungskonsole um zu sehen, wie Benutzer in Ihrer Organisation Microsoft-Teams verwenden. Beispielsweise wenn einige noch nicht Microsoft-Teams verwenden, können sie nicht wissen, wie steigen oder zu verstehen, wie diese Teams werden produktiver und Zusammenarbeit verwenden können. Ihre Organisation kann mithilfe der Aktivitätsberichte entscheiden, wo Schulungs- und Kommunikationsinitiativen priorisiert ansetzen sollen.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Die Teams anzeigen von Berichten im Dashboard Berichte

1. Wählen Sie in der [Microsoft 365 Administrationscenter](https://portal.office.com/adminportal/home) **Berichte**aus > **Usage**.
 
2. Klicken Sie auf der Seite **Verwendung** wählen Sie aus, **Wählen Sie einen Bericht**, und klicken Sie dann unter **Microsoft-Teams,** in der Liste der Berichte, wählen Sie den Bericht, den Sie anzeigen möchten.

## <a name="teams-activity-reports-that-are-available"></a>Teams Berichte, die verfügbar sind

Derzeit gibt es zwei Berichte, die Sie anzeigen können:

- [Microsoft Teams – Benutzeraktivitätsbericht](#microsoft-teams-user-activity-report) 
- [Microsoft Teams – Gerätenutzungsbericht](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Teams User Activity Report bietet eine Ansicht der am häufigsten verwendeten Aktionen, die Ihre Benutzer in Teams durchführen. Dazu gehören, wie viele Personen einen Chat in einem Kanal beteiligen, wie viele über private Chatnachricht kommunizieren und wie viele Anrufe oder Besprechungen teilzunehmen. Sie können diese Informationen für die gesamte Organisation sowie für jeden einzelnen Benutzer angezeigt.

![Screenshot des Teams User Activity Report im Office 365 Administrationscenter.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Microsoft-Teams, User Activity Report interpretieren

Betrachten die **Aktivität** , und **Benutzer** Diagramme, um eine Ansicht in Teams Benutzeraktivität zu erhalten.

![Screenshot des Teams User Activity Report im Office 365 Administrationscenter mit nummerierten Beschriftungen.](media/teams-user-activity-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |User Activity Report Teams kann für Trends über den letzten sieben Tagen 30 Tage, 90 Tage oder nach 180 Tagen angezeigt werden. Wenn Sie in einem bestimmten Zeitbereich im Bericht klicken, wird jedoch die Tabelle (7) Daten für 30 Tage, bis zu dem Datum (2) für angezeigt, wenn der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die Ansicht **Aktivität** wird die Anzahl der Microsoft-Teams, Aktivitäten nach Aktivitätstyp. Die Aktivität sind Anzahl von Chatnachrichten Team, private Chatnachrichten, Anrufe und Besprechungen. |
|**4**   |Die **Benutzer** -Ansicht zeigt Sie die Anzahl der Benutzer nach Aktivitätstyp. Die Aktivität sind Anzahl von Chatnachrichten Team, private Chatnachrichten, Anrufe und Besprechungen. |
|**5**   |Die x-Achse auf Diagramme ist des ausgewählten Datumsbereichs für den Bericht an. <ul><li>Im Diagramm **Aktivität** ist die y-Achse die Anzahl der angegebenen Aktivität.</ul></li> <ul><li>Im Diagramm **Benutzer** ist die y-Achse die Anzahl der Benutzer beteiligt Teams Chats, private Chats, anrufen oder Besprechungen.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie auf ein Element in der Legende klicken. Beispielsweise das Diagramm **Aktivität** klicken Sie oder tippen Sie **Channel Nachrichten**, **Nachrichten Chat**, **Anrufen**oder **Besprechungen** , um nur die Informationen im Zusammenhang mit jeweils finden Sie unter. Das Ändern dieser Auswahl ändert nicht die Informationen in der Tabelle Raster. |
|**7**   |Die Liste der aktiven Teams innerhalb des breitesten (180-tägige) reporting Zeitrahmens.  Die Anzahl der Aktivitäten variiert entsprechend der Auswahl des Datums. <br><br> Wenn Sie die folgende Informationen der Tabelle angezeigt wird, stellen Sie sicher, dass Sie die Spalten der Tabelle hinzufügen. <ul><li>**Benutzername** ist die e-Mail-Adresse des Benutzers. Sie können die tatsächliche e-Mail-Adresse anzuzeigen oder dieses Feld anonyme machen.</ul></li> <ul><li>**Letzte Aktivität Datum (UTC)** bezieht sich auf das Datum der letzten, das der Benutzer in einer Microsoft-Teams, Aktivität verwendet wurde.</ul></li> <ul><li>**DDE-Kanal-Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer gebucht in einem Chat Team während des angegebenen Zeitraums.</ul></li> <ul><li>**Chatnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer in einem privaten Chat während des angegebenen Zeitraums veröffentlicht.</ul></li> <ul><li>**Anrufe** ist die Anzahl der Anrufe, die der Benutzer teilgenommen während des angegebenen Zeitraums.</ul></li> <ul><li>**Besprechungen** ist die Anzahl von onlinebesprechungen, die der Benutzer aus der angegebenen Zeitraum verwendet wurde.</ul></li> <ul><li>**Andere Aktivitäten** ist die Anzahl der vom Benutzer, von denen einige umfassen und nicht beschränkt auf, andere Teamaktivitäten: Nachrichten wünschen, apps, für Dateien, suchen Sie nach Teams und Channel und Favoriting sie arbeiten.</ul></li> <ul><li>**Deleted** gibt an, ob das Team gelöscht wird. Wenn das Team wird gelöscht, aber die Aktivität des Berichtszeitraums bot, wird es im Raster mit gelöschten Festlegung auf "true" angezeigt.</ul></li> <ul><li>**Deleted** ist das Datum, das der Benutzer gelöscht wurde.</ul></li> <ul><li>**Produkt zugewiesen** ist die Liste der Produkte, die dem Benutzer zugewiesen sind.</ul></li>Wenn Richtlinien Ihrer Organisation verhindert, dass Sie Berichte anzeigen, in dem Benutzerinformationen erkennbar ist, können Sie die für den Datenschutz für alle diese Berichte ändern. Checken Sie die **wie blenden Sie Ebene Benutzerdetails?** Abschnitt in der [Aktivitätsberichte in Office 365 Admin Center Preview](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Klicken Sie oder tippen Sie auf **Spalten** hinzufügen oder Entfernen von Spalten in der Tabelle. |
|**9**   |Klicken Sie oder tippen Sie auf **Exportieren** , um Report-Daten in einer Excel-CSV-Datei zu exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Wenn Sie weniger als 2.000 Benutzer verfügen, können Sie zum Sortieren und Filtern in der Tabelle im Bericht selbst. Wenn Sie mehr als 2.000 Benutzer vorhanden sind, müssen Sie Exportieren der Daten, um den Bericht filtern und sortieren. 

### <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Teams Device Usage Report enthält Informationen, wie die Benutzer mit Teams, einschließlich mobiler apps verbinden. Der Bericht hilft Ihnen zu verstehen, welche Geräte in Ihrer Organisation beliebt sind und wie viele Benutzer unterwegs arbeiten.

![Screenshot des Nutzungsberichts Teams Gerät im Office 365 Administrationscenter.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretieren Sie den Microsoft-Teams Gerät Verwendungsbericht

Die **Benutzer** und **Verteilung** Diagramme betrachten, um eine Ansicht in Teams Gerät Nutzung zu erhalten.

![Screenshot des Nutzungsberichts Teams Gerät im Office 365 Administrationscenter mit nummerierten Beschriftungen.](media/teams-device-usage-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Device Report Teams kann über den letzten sieben Tagen 30 Tage, 90 Tage oder nach 180 Tagen für Trends angezeigt werden. Wenn Sie in einem bestimmten Zeitbereich im Bericht klicken, wird jedoch die Tabelle (7) Daten für 30 Tage, bis zu dem Datum (2) für angezeigt, wenn der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die **Benutzer** -Ansicht zeigt Sie die Anzahl der Benutzer pro Tag nach Gerätetyp. |
|**4**   |Die **Verteilung** Ansicht zeigt Sie die Anzahl der Benutzer vom Gerät über den ausgewählten Zeitraum an.  |
|**5**   | <ul><li>Im Diagramm **Benutzer** die x-Achse des ausgewählten Datumsbereichs für den Bericht ist und die y-Achse ist die Anzahl der Benutzer nach Gerätetyp.</ul></li> <ul><li>Im Diagramm **Verteilung** zeigt die x-Achse, die verschiedene Geräte, die zum Verbinden mit Teams und die y-Achse ist die Anzahl der Benutzer des Geräts.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie auf ein Element in der Legende klicken. Beispielsweise das Diagramm **Verteilung** klicken Sie oder tippen Sie auf **Windows**, **Mac**, **Web**, **iOS**und **Android** , um nur die Informationen im Zusammenhang mit jeweils finden Sie unter. Das Ändern dieser Auswahl ändert nicht die Informationen in der Tabelle Raster. |
|**7**   |Die Liste der aktiven Teams innerhalb des breitesten (180-tägige) reporting Zeitrahmens.  Die Anzahl der Aktivitäten variiert entsprechend der Auswahl des Datums. <br><br> Wenn Sie die folgende Informationen in der Tabelle angezeigt wird, stellen Sie sicher, dass Sie die Spalten der Tabelle hinzufügen. <ul><li>**Benutzername** ist die e-Mail-Adresse des Benutzers. Sie können die tatsächliche e-Mail-Adresse anzuzeigen oder dieses Feld anonyme machen.</ul></li> <ul><li>**Letzte Aktivität Datum (UTC)** bezieht sich auf das Datum der letzten, das der Benutzer in einer Aktivität Teams verwendet wurde.</ul></li> <ul><li>**Deleted** gibt an, ob das Team gelöscht wird. Wenn das Team wird gelöscht, aber die Aktivität des Berichtszeitraums bot, wird es im Raster mit gelöschten Festlegung auf "true" angezeigt.</ul></li><ul><li>**Deleted** ist das Datum, das der Benutzer gelöscht wurde.</ul></li> <ul><li>**Windows** ist aktiviert, wenn der Benutzer im Desktopclient Teams auf einem Windows-basierten Computer aktiv war.</ul></li> <ul><li>**Mac** ist aktiviert, wenn der Benutzer im Desktopclient Teams auf einem Mac OS Computer aktiv war.</ul></li>  <ul><li>**Web** ist aktiviert, wenn der Benutzer auf dem Webclient Teams aktiv war.</ul></li> <ul><li>**iOS** ist aktiviert, wenn der Benutzer auf dem Teams mobilen Client für iOS aktiv war.</ul></li> <ul><li>**Android-Telefon** wird ausgewählt, wenn der Benutzer auf dem Teams mobilen Client für Android aktiv war.</ul></li></li> <ui>Wenn Richtlinien Ihrer Organisation verhindert, dass Sie Berichte anzeigen, in dem Benutzerinformationen erkennbar ist, können Sie die für den Datenschutz für alle diese Berichte ändern. Checken Sie die **wie blenden Sie Ebene Benutzerdetails?** Abschnitt in der [Aktivitätsberichte in Office 365 Admin Center Preview](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Klicken Sie oder tippen Sie auf **Spalten** hinzufügen oder Entfernen von Spalten in der Tabelle. |
|**9**   |Klicken Sie oder tippen Sie auf **Exportieren** , um Report-Daten in einer Excel-CSV-Datei zu exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Wenn Sie weniger als 2.000 Benutzer verfügen, können Sie zum Sortieren und Filtern in der Tabelle im Bericht selbst. Wenn Sie mehr als 2.000 Benutzer vorhanden sind, müssen Sie Exportieren der Daten, um den Bericht filtern und sortieren. 

## <a name="who-can-access-the-teams-activity-reports"></a>Wer kann die Teams Berichte zugreifen

Von Benutzern, die zugewiesen sind, können die Berichte zugegriffen werden:

- Office 365 globalen Administratorrolle
- Produktspezifische Administratorrolle (Exchange, Skype für Geschäftskunden und SharePoint)
- Berichte Reader-Rolle

### <a name="reports-reader-role"></a>Berichte Reader-Rolle

Sie können die Rolle *Leser von Berichten* außer IT-Mitarbeiter zuweisen, die Zugriff auf diese Berichte werden soll. Schulung-Manager oder Projektbeteiligten diese Rolle zuweisen, können Sie sicherstellen, dass die Insights zugreifen kann, die auf Laufwerk und Nachverfolgen Akzeptanz Teams hilfreich sind.

## <a name="other-information-on-the-reports-dashboard"></a>Weitere Informationen auf das Dashboard Berichte

### <a name="at-a-glance-activity-widget"></a>Widget-Aktivität auf einen Blick

Das Dashboard Berichte enthält die Verwendungsdaten von Teams im Widget auf einen Blick Aktivität, das Sie haben eine Ansicht produktübergreifende wie Benutzer kommunizieren und zusammenarbeiten mit anderen verschiedene Dienste in Office 365.

![Screenshot des Widgets Teams Aktivität auf einen Blick auf das Dashboard Berichte.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Teams Aktivität Karte

Die Teams Aktivität Karte auf das Dashboard Berichte bietet eine Übersicht über die Aktivität bei Teams, einschließlich der Anzahl von aktiven Benutzern, sodass Sie schnell verstehen, welche die Anzahl der Benutzer den Dienst verwenden. Durch Klicken auf die Aktivität Visitenkarte auf das Dashboard gelangen Sie zu Teams User Activity Report. 

![Screenshot der Karte Aktivität Teams auf das Dashboard Berichte.](media/teams-activity-card.png)
