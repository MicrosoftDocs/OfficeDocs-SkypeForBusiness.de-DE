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
description: Erfahren Sie, wie Sie Aktivitätsberichte verwenden, um zu sehen, wie Benutzer in Ihrer Organisation Microsoft Teams verwenden.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9c975bf4a3f2253dbc99230f85b48a9ae9cd0d65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107191"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Verwenden von Aktivitätsberichten für Microsoft Teams 
========================================

Sie können Aktivitätsberichte im Microsoft 365 Admin Center verwenden, um zu sehen, wie Benutzer in Ihrer Organisation Microsoft Teams verwenden. Wenn einige Microsoft Teams beispielsweise noch nicht verwenden, wissen sie möglicherweise nicht, wie sie beginnen oder verstehen können, wie Teams produktiver und kollaborativer sein kann. Ihre Organisation kann mithilfe der Aktivitätsberichte entscheiden, wo Schulungs- und Kommunikationsinitiativen priorisiert ansetzen sollen.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Anzeigen der Teams-Berichte im Dashboard "Berichte"

1. Wählen Sie [im Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)die Option Verwendung **berichte**  >  **aus.**
 
2. Wählen Sie **auf** der Seite Verwendung die Option Bericht **auswählen** aus, und wählen Sie dann unter **Microsoft Teams** in der Liste der Berichte den Bericht aus, den Sie anzeigen möchten.

## <a name="teams-activity-reports-that-are-available"></a>Verfügbare Teams-Aktivitätsberichte

Es gibt derzeit zwei Aktivitätsberichte, die Sie anzeigen können:

- [Microsoft Teams – Benutzeraktivitätsbericht](#microsoft-teams-user-activity-report) 
- [Microsoft Teams – Gerätenutzungsbericht](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Im Bericht "Teams-Benutzeraktivität" erhalten Sie eine Ansicht der am häufigsten verwendeten Aktivitäten, die Ihre Benutzer in Teams ausführen. Dies umfasst, wie viele Personen in einem Kanal an einem Chat teilnehmen, wie viele Personen über private Chatnachrichten kommunizieren und wie viele Personen an Anrufen oder Besprechungen teilnehmen. Sie können diese Informationen für Ihre gesamte Organisation sowie für jeden einzelnen Benutzer sehen.

![Screenshot des Berichts "Benutzeraktivität" im Admin Center.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretieren des Microsoft Teams-Benutzeraktivitätsberichts

Sie können einen Einblick in die Benutzeraktivitäten von Teams erhalten, indem Sie sich die Diagramme **Aktivität** und **Benutzer** ansehen.

![Screenshot des Berichts "Benutzeraktivität" mit nummerierten Callouts.](media/teams-user-activity-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht "Teams-Benutzeraktivität" kann für Trends während der letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt werden. Wenn Sie jedoch in einen bestimmten Zeitraum im Bericht klicken, werden in der Tabelle (7) Daten für 30 Tage bis zum Datum (2) angezeigt, an dem der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |In **der Ansicht** Aktivität wird die Anzahl der Microsoft Teams-Aktivitäten nach Aktivitätstyp angezeigt. Die Aktivitätstypen sind die Anzahl der Teamchatnachrichten, privaten Chatnachrichten, Anrufe und Besprechungen. |
|**4**   |In **der Ansicht** Benutzer wird die Anzahl der Benutzer nach Aktivitätstyp angezeigt. Die Aktivitätstypen sind die Anzahl der Teamchatnachrichten, privaten Chatnachrichten, Anrufe und Besprechungen. |
|**5**   |Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht. <ul><li>Im Diagramm **Aktivität** ist die Y-Achse die Anzahl der angegebenen Aktivität.</ul></li> <ul><li>Im Diagramm **Benutzer ist** die Y-Achse die Anzahl der Benutzer, die an Teamschats, privaten Chats, Anrufen oder Besprechungen teilnehmen.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Klicken oder tippen  Sie beispielsweise im Diagramm Aktivität auf Kanalnachrichten,  **Chatnachrichten,** Anrufe oder Besprechungen, um nur die jeweils zugehörigen Informationen zu sehen.  Durch das Ändern dieser Auswahl werden die Informationen in der Rastertabelle nicht geändert. |
|**7**   |Die Liste der aktiven Teams im breitesten (180-Tage)-Berichtszeitrahmen.  Die Aktivitätsanzahl variiert je nach Datumsauswahl. <br><br> Um die folgenden Informationen in der Tabelle anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die Spalten hinzufügen. <ul><li>**Benutzername** ist die E-Mail-Adresse des Benutzers. Sie können die tatsächliche E-Mail-Adresse anzeigen oder dieses Feld anonym machen.</ul></li> <ul><li>**Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Microsoft Teams-Aktivität teilgenommen hat.</ul></li> <ul><li>**Kanalnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.</ul></li> <ul><li>**Chatnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer in einem privaten Chat während des angegebenen Zeitraums gepostet hat.</ul></li> <ul><li>**Anrufe** ist die Anzahl der Anrufe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</ul></li> <ul><li>**Besprechungen** sind die Anzahl der Onlinebesprechungen, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</ul></li> <ul><li>**Andere** Aktivitäten sind die Anzahl anderer Teamaktivitäten des Benutzers, zu denen einige gehören und nicht darauf beschränkt sind: "Gefallen an Nachrichten", "Apps", "An Dateien arbeiten", "Suchen", "Teams folgen" und "Kanal" folgen und diese bevorzugen.</ul></li> <ul><li>**Gelöscht** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wurde, aber im Berichtszeitraum Aktivitäten hatte, wird es im Raster angezeigt, und gelöscht ist auf "true" festgelegt.</ul></li> <ul><li>**Das Gelöschte** Datum ist das Datum, an dem der Benutzer gelöscht wurde.</ul></li> <ul><li>**Dem Benutzer** zugewiesenes Produkt ist die Liste der Produkte, die dem Benutzer zugewiesen sind.</ul></li>Wenn die Richtlinien Ihrer Organisation verhindern, dass Sie Berichte anzeigen, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt **Wie blende ich Details auf Benutzerebene aus?** im Abschnitt [Aktivitätsberichte in der Microsoft 365 Admin Center Preview aus.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Klicken oder tippen Sie **auf Spalten,** um Spalten in der Tabelle hinzuzufügen oder zu entfernen. |
|**9**   |Klicken oder tippen Sie **auf Exportieren,** um Berichtsdaten in eine Excel-CSV-Datei zu exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Wenn Sie weniger als 2.000 Benutzer haben, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie mehr als 2.000 Benutzer haben, müssen Sie die Daten exportieren, um den Bericht zu filtern und zu sortieren. 

### <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Der Bericht zur Gerätenutzung von Teams enthält Informationen dazu, wie Ihre Benutzer eine Verbindung mit Teams herstellen, einschließlich mobiler Apps. Der Bericht hilft Ihnen zu verstehen, welche Geräte in Ihrer Organisation beliebt sind und wie viele Benutzer unterwegs arbeiten.

![Screenshot des Teams-Gerätenutzungsberichts.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretieren des Microsoft Teams-Gerätenutzungsberichts

Sie können einen Einblick in die Gerätenutzung von Teams erhalten, indem Sie sich die Diagramme **Benutzer** und **Verteilung** ansehen.

![Screenshot des Teams-Gerätenutzungsberichts mit nummerierten Callouts.](media/teams-device-usage-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Gerätebericht von Teams kann für Trends der letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt werden. Wenn Sie jedoch in einen bestimmten Zeitraum im Bericht klicken, werden in der Tabelle (7) Daten für 30 Tage bis zum Datum (2) angezeigt, an dem der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |In **der Ansicht** Benutzer wird die Anzahl der täglichen Benutzer nach Gerätetyp angezeigt. |
|**4**   |In **der Ansicht** Verteilung wird die Anzahl der Benutzer nach Gerät im ausgewählten Zeitraum angezeigt.  |
|**5**   | <ul><li>Im Diagramm **Benutzer** ist die X-Achse der ausgewählte Datumsbereich für den Bericht, und die Y-Achse ist die Anzahl der Benutzer nach Gerätetyp.</ul></li> <ul><li>Im **Diagramm Verteilung** zeigt die X-Achse die verschiedenen Geräte an, die zum Herstellen einer Verbindung mit Teams verwendet werden, und die Y-Achse ist die Anzahl der Benutzer, die das Gerät verwenden.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Klicken oder tippen  Sie beispielsweise im Diagramm Verteilung auf **Windows,** **Mac,** **Linux,** **Web,** **iOS** oder **Android,** um nur die jeweils zugehörigen Informationen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Rastertabelle nicht geändert. |
|**7**   |Die Liste der aktiven Teams im breitesten (180-Tage)-Berichtszeitrahmen.  Die Aktivitätsanzahl variiert je nach Datumsauswahl. <br><br> Um die folgenden Informationen in der Tabelle anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die Spalten hinzufügen. <ul><li>**Benutzername** ist die E-Mail-Adresse des Benutzers. Sie können die tatsächliche E-Mail-Adresse anzeigen oder dieses Feld anonym machen.</ul></li> <ul><li>**Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Teams-Aktivität teilgenommen hat.</ul></li> <ul><li>**Gelöscht** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wurde, aber im Berichtszeitraum Aktivitäten hatte, wird es im Raster angezeigt, und gelöscht ist auf "true" festgelegt.</ul></li><ul><li>**Das Gelöschte** Datum ist das Datum, an dem der Benutzer gelöscht wurde.</ul></li> <ul><li>**Windows**  ist ausgewählt, wenn der Benutzer im Desktopclient von Teams auf einem Windows-basierten Computer aktiv war.</ul></li> <ul><li>**Mac** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem macOS-Computer aktiv war.</ul></li>  <ul><li>**Linux** ist ausgewählt, wenn der Benutzer im Desktopclient von Teams auf einem Linux-Computer aktiv war.</ul></li>   <ul><li>**Das Web** ist ausgewählt, wenn der Benutzer im Teams-Webclient aktiv war.</ul></li> <ul><li>**iOS** ist ausgewählt, wenn der Benutzer auf dem mobilen Teams-Client für iOS aktiv war.</ul></li> <ul><li>**Android Phone**  ist ausgewählt, wenn der Benutzer auf dem mobilen Teams-Client für Android aktiv war.</ul></li></li> <ui>Wenn die Richtlinien Ihrer Organisation verhindern, dass Sie Berichte anzeigen, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt **Wie blende ich Details auf Benutzerebene aus?** im Abschnitt [Aktivitätsberichte in der Microsoft 365 Admin Center Preview aus.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Klicken oder tippen Sie **auf Spalten,** um Spalten in der Tabelle hinzuzufügen oder zu entfernen. |
|**9**   |Klicken oder tippen Sie **auf Exportieren,** um Berichtsdaten in eine Excel-CSV-Datei zu exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Wenn Sie weniger als 2.000 Benutzer haben, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie mehr als 2.000 Benutzer haben, müssen Sie die Daten exportieren, um den Bericht zu filtern und zu sortieren. 

## <a name="who-can-access-the-teams-activity-reports"></a>Wer kann auf die Aktivitätsberichte von Teams zugreifen?

Auf die Aktivitätsberichte können Benutzer zugreifen, die zugewiesen sind:

- Rolle des globalen Administrators
- Produktspezifische Administratorrolle (Exchange, Skype for Business oder SharePoint)
- Leserrolle "Berichte"

### <a name="reports-reader-role"></a>Leserrolle "Berichte"

Sie können die Rolle des Lesers Berichte Personen zuweisen, die nicht über Administratorrechte verfügen, aber für die Einführung oder Nachverfolgung der Lizenznutzung von Teams verantwortlich sind. Informationen zum Zuweisen von Rollen finden Sie unter Zuweisen von Administrator- und [Nichtadministratorrollen zu Benutzern mit Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="other-information-on-the-reports-dashboard"></a>Weitere Informationen im Dashboard "Berichte"

### <a name="at-a-glance-activity-widget"></a>Aktivitäts-Widget auf einen Blick

Das Dashboard Berichte enthält die Nutzungsdaten von Teams im Aktivitäts-Widget auf einen Blick, das Ihnen eine produktübergreifende Ansicht bietet, wie Benutzer mit den anderen verschiedenen Diensten in Microsoft 365 oder Office 365 kommunizieren und zusammenarbeiten.

![Screenshot des Aktivitäts-Widgets "Teams auf einen Blick".](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Aktivitätskarte von Teams

Die Team-Aktivitätskarte im Dashboard Berichte bietet ihnen einen Überblick über die Aktivitäten in Teams, einschließlich der Anzahl aktiver Benutzer, damit Sie schnell verstehen können, wie viele Benutzer den Dienst verwenden. Durch Klicken auf die Aktivitätskarte im Dashboard werden Sie zum Bericht "Teams-Benutzeraktivität" angezeigt. 

![Screenshot der Teams-Aktivitätskarte.](media/teams-activity-card.png)