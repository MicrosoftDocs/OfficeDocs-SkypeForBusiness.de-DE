---
title: Verwenden von Aktivitätsberichten für Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie mithilfe von Aktivitätsberichten sehen können, wie Benutzer in Ihrer Organisation Microsoft Teams verwenden.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f1eb02b7755ecfaa78b3b5ad511f45052a7807b5
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256390"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Verwenden von Aktivitätsberichten für Microsoft Teams 
========================================

Sie können Aktivitätsberichte im Microsoft 365 Admin Center verwenden, um zu sehen, wie Benutzer in Ihrer Organisation Microsoft Teams verwenden. Wenn beispielsweise einige Microsoft Teams noch nicht verwenden, wissen Sie möglicherweise nicht, wie Sie beginnen oder verstehen, wie Sie Teams produktiver und kollaborativer nutzen können. Ihre Organisation kann mithilfe der Aktivitätsberichte entscheiden, wo Schulungs- und Kommunikationsinitiativen priorisiert ansetzen sollen.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Anzeigen der Teams-Berichte im Dashboard "Berichte"

1. Wählen Sie im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)die Option **Berichte**-  >  **Nutzung**aus.
 
2. Wählen Sie auf der Seite **Verwendung** den **Eintrag Bericht auswählen**aus, und wählen Sie dann unter **Microsoft Teams** in der Liste der Berichte den Bericht aus, den Sie anzeigen möchten.

## <a name="teams-activity-reports-that-are-available"></a>Verfügbare Teams-Aktivitätsberichte

Es gibt derzeit zwei Aktivitätsberichte, die Sie anzeigen können:

- [Microsoft Teams – Benutzeraktivitätsbericht](#microsoft-teams-user-activity-report) 
- [Microsoft Teams – Gerätenutzungsbericht](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Der Bericht "Team-Benutzeraktivität" bietet eine Ansicht der am häufigsten vorkommenden Aktivitäten, die Ihre Benutzer in Teams ausführen. Dazu gehört, wie viele Personen an einem Chat in einem Kanal teilnehmen, wie viele Personen per privater Chatnachricht kommunizieren und wie viele an anrufen oder Besprechungen teilnehmen. Sie können diese Informationen für Ihre gesamte Organisation sowie für jeden einzelnen Benutzer anzeigen.

![Screenshot des Benutzer Aktivitätsberichts im Admin Center](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretieren des Berichts "Microsoft Teams-Benutzeraktivität"

Sie können einen Einblick in die Benutzeraktivitäten von Teams erhalten, indem Sie sich die Diagramme **Aktivität** und **Benutzer** ansehen.

![Screenshot des Benutzer Aktivitätsberichts mit nummerierten Beschriftungen](media/teams-user-activity-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht "Teams-Benutzeraktivität" kann für Trends in den letzten 7 Tagen, 30 Tage, 90 Tage oder 180 Tage angezeigt werden. Wenn Sie jedoch in einen bestimmten Zeitraum im Bericht klicken, werden in der Tabelle (7) Daten für 30 Tage angezeigt, bis zu dem Datum (2) für den Zeitpunkt, zu dem der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |In der Ansicht **Aktivität** wird die Anzahl der Aktivitäten von Microsoft Teams nach Aktivitätstyp angezeigt. Die Aktivitätstypen sind die Anzahl der Team-Chat-Nachrichten, private Chatnachrichten, Anrufe und Besprechungen. |
|**4**   |In der Ansicht **Benutzer** wird die Anzahl der Benutzer nach Aktivitätstyp angezeigt. Die Aktivitätstypen sind die Anzahl der Team-Chat-Nachrichten, private Chatnachrichten, Anrufe und Besprechungen. |
|**5**   |Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht. <ul><li>Im Diagramm **Aktivität** stellt die Y-Achse die Anzahl der angegebenen Aktivität dar.</ul></li> <ul><li>Im Diagramm **Benutzer** stellt die Y-Achse die Anzahl der Benutzer dar, die an Teams-Chats, privaten Chats, anrufen oder Besprechungen teilnehmen.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Klicken oder tippen Sie beispielsweise im **Aktivitäts** Diagramm auf **Kanal Nachrichten**, **Chat Nachrichten**, **Anrufe**oder **Besprechungen** , um nur die Informationen anzuzeigen, die sich auf die jeweilige Person beziehen. Wenn Sie diese Auswahl ändern, werden die Informationen in der Raster Tabelle nicht geändert. |
|**7**   |Die Liste der aktiven Teams über den breitesten (180-tägigen) Berichterstellungszeitraum.  Die Anzahl der Aktivitäten variiert entsprechend der Datumsauswahl. <br><br> Wenn Sie die folgenden Informationen in der Tabelle anzeigen möchten, stellen Sie sicher, dass Sie die Spalten zur Tabelle hinzufügen. <ul><li>**Username** ist die e-Mail-Adresse des Benutzers. Sie können die tatsächliche e-Mail-Adresse anzeigen oder dieses Feld anonym machen.</ul></li> <ul><li>**Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Microsoft Teams-Aktivität teilgenommen hat.</ul></li> <ul><li>**Kanal Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.</ul></li> <ul><li>**Chat Nachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.</ul></li> <ul><li>**Anrufe** ist die Anzahl von anrufen, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.</ul></li> <ul><li>**Besprechungen** ist die Anzahl von Onlinebesprechungen, an denen der Benutzer während des angegebenen Zeitraums teilgenommen hat.</ul></li> <ul><li>Bei **anderen Aktivitäten** handelt es sich um die Anzahl der anderen Teamaktivitäten des Benutzers, von denen einige, und nicht nur: Nachrichten, apps, arbeiten an Dateien, suchen, nach Teams und Kanal und bevorzugte Nutzung von Personen gehören.</ul></li> <ul><li>**Gelöscht** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wird, aber im Berichtszeitraum Aktivitäten ausgeführt wurde, wird es im Raster angezeigt, wobei Deleted auf true festgelegt ist.</ul></li> <ul><li>**Gelöscht** am ist das Datum, an dem der Benutzer gelöscht wurde.</ul></li> <ul><li>Das **Produkt** ist eine Liste der Produkte, die dem Benutzer zugewiesen sind.</ul></li>Wenn Sie von den Richtlinien Ihrer Organisation verhindert werden, dass Berichte angezeigt werden, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt **wie kann ich Details zu Benutzerebene ausblenden?** in den [Aktivitätsberichten in der Microsoft 365 Admin Center Preview](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Klicken oder tippen Sie auf **Spalten** , um Spalten in der Tabelle hinzuzufügen oder daraus zu entfernen. |
|**9**   |Klicken oder tippen Sie auf **exportieren** , um die Berichtsdaten in eine Excel-CSV-Datei zu exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Wenn Sie weniger als 2.000-Benutzer haben, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie mehr als 2.000-Benutzer haben, müssen Sie die Daten exportieren, um den Bericht zu filtern und zu sortieren. 

### <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Im Bericht "Teams-Gerätenutzung" finden Sie Informationen dazu, wie Ihre Benutzer eine Verbindung mit Teams herstellen, einschließlich mobiler apps. Der Bericht hilft Ihnen zu verstehen, welche Geräte in Ihrer Organisation beliebt sind und wie viele Benutzer unterwegs arbeiten.

![Screenshot des Teams-Geräte Verwendungsberichts](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretieren des Berichts zur Gerätenutzung in Microsoft Teams

Sie können sich einen Überblick über die Geräteverwendung von Teams verschaffen, indem Sie sich die Diagramme **Benutzer** und **Verteilung** ansehen.

![Screenshot des Teams-Geräte Verwendungsberichts mit nummerierten Beschriftungen](media/teams-device-usage-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht "Teams-Geräte" kann für Trends in den letzten 7 Tagen, 30 Tage, 90 Tage oder 180 Tage angezeigt werden. Wenn Sie jedoch in einen bestimmten Zeitraum im Bericht klicken, werden in der Tabelle (7) Daten für 30 Tage angezeigt, bis zu dem Datum (2) für den Zeitpunkt, zu dem der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |In der Ansicht **Benutzer** wird die Anzahl der täglichen Benutzer nach Gerätetyp angezeigt. |
|**4**   |In der Ansicht " **Verteilung** " wird die Anzahl der Benutzer nach Gerät für den ausgewählten Zeitraum angezeigt.  |
|**5**   | <ul><li>Im Diagramm **Benutzer** stellt die X-Achse den ausgewählten Datumsbereich für den Bericht und die Y-Achse die Anzahl der Benutzer nach Gerätetyp dar.</ul></li> <ul><li>Im **Verteilungs** Diagramm zeigt die X-Achse die verschiedenen Geräte an, die zum Herstellen der Verbindung mit Teams verwendet werden, und die Y-Achse entspricht der Anzahl der Benutzer, die das Gerät verwenden.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Klicken oder tippen Sie beispielsweise im **Verteilungs** Diagramm auf **Windows**-, **Mac**-, **Linux**-, **Web**-, **IOS**-oder **Android** -Daten, um nur die Informationen anzuzeigen, die sich auf die jeweilige Person beziehen. Wenn Sie diese Auswahl ändern, werden die Informationen in der Raster Tabelle nicht geändert. |
|**7**   |Die Liste der aktiven Teams über den breitesten (180-tägigen) Berichterstellungszeitraum.  Die Anzahl der Aktivitäten variiert entsprechend der Datumsauswahl. <br><br> Wenn Sie die folgenden Informationen in der Tabelle anzeigen möchten, stellen Sie sicher, dass Sie die Spalten zur Tabelle hinzufügen. <ul><li>**Username** ist die e-Mail-Adresse des Benutzers. Sie können die tatsächliche e-Mail-Adresse anzeigen oder dieses Feld anonym machen.</ul></li> <ul><li>**Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Team Aktivität teilgenommen hat.</ul></li> <ul><li>**Gelöscht** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wird, aber im Berichtszeitraum Aktivitäten ausgeführt wurde, wird es im Raster angezeigt, wobei Deleted auf true festgelegt ist.</ul></li><ul><li>**Gelöscht** am ist das Datum, an dem der Benutzer gelöscht wurde.</ul></li> <ul><li>**Windows** ist ausgewählt, wenn der Benutzer im Desktop Client von Teams auf einem Windows-basierten Computer aktiv war.</ul></li> <ul><li>**Mac** ist ausgewählt, wenn der Benutzer im Desktop Client von Teams auf einem macOS-Computer aktiv war.</ul></li>  <ul><li>**Linux** ist ausgewählt, wenn der Benutzer im Team-Desktop Client auf einem Linux-Computer aktiv war.</ul></li>   <ul><li>**Web** ist ausgewählt, wenn der Benutzer im Team-WebClient aktiv war.</ul></li> <ul><li>**IOS** ist ausgewählt, wenn der Benutzer auf dem mobilen Team-Client für IOS aktiv war.</ul></li> <ul><li>**Android-Telefon** ist ausgewählt, wenn der Benutzer auf dem mobilen Team-Client für Android aktiv war.</ul></li></li> <ui>Wenn Sie von den Richtlinien Ihrer Organisation verhindert werden, dass Berichte angezeigt werden, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt **wie kann ich Details zu Benutzerebene ausblenden?** in den [Aktivitätsberichten in der Microsoft 365 Admin Center Preview](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Klicken oder tippen Sie auf **Spalten** , um Spalten in der Tabelle hinzuzufügen oder daraus zu entfernen. |
|**9**   |Klicken oder tippen Sie auf **exportieren** , um die Berichtsdaten in eine Excel-CSV-Datei zu exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Wenn Sie weniger als 2.000-Benutzer haben, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie mehr als 2.000-Benutzer haben, müssen Sie die Daten exportieren, um den Bericht zu filtern und zu sortieren. 

## <a name="who-can-access-the-teams-activity-reports"></a>Personen, die auf die Team Aktivitätsberichte zugreifen können

Auf die Aktivitätsberichte kann von Benutzern zugegriffen werden, denen Sie zugewiesen sind:

- Rolle des globalen Administrators
- Produktspezifische Administratorrolle (Exchange, Skype for Business oder SharePoint)
- Rolle des Berichts Lesers

### <a name="reports-reader-role"></a>Rolle des Berichts Lesers

Sie können die Rolle " *berichtsleser* " den nicht-IT-Mitarbeitern zuweisen, auf die Sie Zugriff auf diese Berichte haben möchten. Durch Zuweisen dieser Rolle zu Schulungsleitern oder Unternehmens Beteiligten können Sie sicherstellen, dass Sie Zugriff auf die Einsichten haben, die hilfreich sind, um die Einführung von Teams zu steuern und zu überwachen. Informationen zum Zuweisen von Rollen finden Sie unter [Zuweisen von Administrator-und Administratorrollen zu Benutzern mit Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="other-information-on-the-reports-dashboard"></a>Weitere Informationen im Dashboard "Berichte"

### <a name="at-a-glance-activity-widget"></a>Widget "auf einen Blick"-Aktivität

Das Dashboard "Berichte" enthält die Nutzungsdaten von Teams im Widget "auf einen Blick", das Ihnen eine produktübergreifende Ansicht zeigt, wie Benutzer mit den anderen verschiedenen Diensten in Office 365 kommunizieren und zusammenarbeiten.

![Screenshot des Animations Widget "Teams auf einen Blick"](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Teams-Aktivitäts Karte

Die Team Aktivitäts Karte im Dashboard "Berichte" gibt Ihnen einen Überblick über die Aktivitäten in Teams, einschließlich der Anzahl der aktiven Benutzer, damit Sie schnell verstehen können, wie viele Benutzer den Dienst verwenden. Wenn Sie im Dashboard auf die Aktivitäts Karte klicken, gelangen Sie zum Berichtbenutzer Aktivität für Teams. 

![Screenshot der Team Aktivitäts Karte](media/teams-activity-card.png)
