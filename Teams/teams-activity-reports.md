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
ms.openlocfilehash: 8428135d2d4baa40fd1957f6f5d02eb658732a6c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918671"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Verwenden von Aktivitätsberichten für Microsoft Teams 
========================================

Sie können Aktivitätsberichte im Microsoft 365 Admin Center verwenden, um zu sehen, wie Benutzer in Ihrer Organisation Microsoft Teams verwenden. Wenn beispielsweise einige Microsoft Teams noch nicht verwenden, wissen sie möglicherweise nicht, wie sie beginnen oder verstehen, wie sie Teams verwenden können, um produktiver und zusammenarbeitlicher zu sein. Ihre Organisation kann mithilfe der Aktivitätsberichte entscheiden, wo Schulungs- und Kommunikationsinitiativen priorisiert ansetzen sollen.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Anzeigen der Berichte in Teams im Dashboard "Berichte"

1. Wählen Sie im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)die Option **"Berichtnutzung"**  >  **aus.**
 
2. Wählen Sie **auf der** Seite "Verwendung" **die** Option "Bericht auswählen" aus, und wählen Sie dann in der Liste der Berichte unter **"Microsoft Teams"** den Bericht aus, den Sie anzeigen möchten.

## <a name="teams-activity-reports-that-are-available"></a>Verfügbare Teams-Aktivitätsberichte

Zurzeit gibt es zwei Aktivitätsberichte, die Sie anzeigen können:

- [Microsoft Teams – Benutzeraktivitätsbericht](#microsoft-teams-user-activity-report) 
- [Microsoft Teams – Gerätenutzungsbericht](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Der Bericht "Teams-Benutzeraktivität" bietet Ihnen eine Ansicht der am häufigsten verwendeten Aktivitäten, die Ihre Benutzer in Teams ausführen. Dazu gehört, wie viele Personen an einem Chat in einem Kanal teilnehmen, wie viele personen per privater Chatnachricht kommunizieren und wie viele Personen an Anrufen oder Besprechungen teilnehmen. Sie können diese Informationen für Ihre gesamte Organisation sowie für jeden einzelnen Benutzer sehen.

![Screenshot des Benutzeraktivitätsberichts im Admin Center.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretieren des Berichts "Microsoft Teams-Benutzeraktivität"

Sie können einen Einblick in die Benutzeraktivitäten von Teams erhalten, indem Sie sich die Diagramme **"Aktivität"** und **"Benutzer"** ansehen.

![Screenshot des Benutzeraktivitätsberichts mit nummerierten Callouts.](media/teams-user-activity-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht "Teams-Benutzeraktivität" werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie jedoch in einen bestimmten Zeitraum im Bericht klicken, werden in der Tabelle (7) Daten für 30 Tage bis zum Datum (2) angezeigt, an dem der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |In **der Ansicht** "Aktivität" wird die Anzahl der Microsoft Teams-Aktivitäten nach Aktivitätstyp angezeigt. Bei den Aktivitätstypen handelt es sich um die Anzahl von Teamchatnachrichten, privaten Chatnachrichten, Anrufen und Besprechungen. |
|**4**   |In **der Ansicht** "Benutzer" wird die Anzahl der Benutzer nach Aktivitätstyp angezeigt. Die Aktivitätstypen sind anzahl der Teamchatnachrichten, privaten Chatnachrichten, Anrufe und Besprechungen. |
|**5**   |Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht. <ul><li>Im **Aktivitätsdiagramm** ist die Y-Achse die Anzahl der angegebenen Aktivität.</ul></li> <ul><li>Im Diagramm **"Benutzer"** gibt die Y-Achse die Anzahl der Benutzer an Teamchats, privaten Chats, Anrufen oder Besprechungen an.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Klicken oder tippen  Sie beispielsweise im Aktivitätsdiagramm auf Kanalnachrichten,  **Chatnachrichten,** Anrufe oder Besprechungen, um nur die jeweils zugehörigen Informationen zu sehen.  Durch das Ändern dieser Auswahl werden die Informationen in der Rastertabelle nicht geändert. |
|**7**   |Die Liste der aktiven Teams für den breiten Berichtszeitraum (180 Tage).  Die Anzahl der Aktivitäten variiert entsprechend der Datumsauswahl. <br><br> Um die folgenden Informationen in der Tabelle anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die Spalten hinzufügen. <ul><li>**"Benutzername"** ist die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonym machen.</ul></li> <ul><li>**Das Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Microsoft Teams-Aktivität teilgenommen hat.</ul></li> <ul><li>**Bei Kanalnachrichten** handelt es sich um die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.</ul></li> <ul><li>**Chatnachrichten** sind die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.</ul></li> <ul><li>**"Anrufe"** ist die Anzahl der Anrufe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</ul></li> <ul><li>**Bei Besprechungen** handelt es sich um die Anzahl der Onlinebesprechungen, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</ul></li> <ul><li>**Andere** Aktivitäten sind die Anzahl anderer Teamaktivitäten des Benutzers, von denen einige umfassen und nicht darauf beschränkt sind: Nachrichten mit "Gefallen", "Apps", "An Dateien arbeiten", "Suchen", "Teams folgen" und "Kanal" sowie "Favorisieren".</ul></li> <ul><li>**"Gelöscht"** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wurde, aber im Berichtszeitraum Aktivitäten hatten, wird es im Raster angezeigt, und "Gelöscht" ist auf "true" festgelegt.</ul></li> <ul><li>**"Gelöscht am"** ist das Datum, an dem der Benutzer gelöscht wurde.</ul></li> <ul><li>**"Zugewiesenes** Produkt" ist die Liste der Produkte, die dem Benutzer zugewiesen sind.</ul></li>Wenn die Richtlinien Ihrer Organisation verhindern, dass Sie Berichte anzeigen, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Schauen Sie sich den Abschnitt **"Wie kann ich Details** auf Benutzerebene ausblenden?" in den Aktivitätsberichten in der Microsoft [365 Admin Center Preview an.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Klicken oder tippen Sie **auf "Spalten",** um Spalten in der Tabelle hinzuzufügen oder zu entfernen. |
|**9**   |Klicken oder tippen Sie **auf "Exportieren",** um Berichtsdaten in eine Excel-CSV-Datei zu exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten exportieren, um den Bericht zu filtern und zu sortieren. 

### <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Der Bericht zur Gerätenutzung in Teams enthält Informationen darüber, wie Ihre Benutzer eine Verbindung mit Teams herstellen, einschließlich mobiler Apps. Der Bericht hilft Ihnen zu verstehen, welche Geräte in Ihrer Organisation beliebt sind und wie viele Benutzer unterwegs arbeiten.

![Screenshot des Berichts "Teams-Gerätenutzung".](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretieren des Berichts zur Gerätenutzung in Microsoft Teams

Sie erhalten einen Einblick in die Nutzung von Teams-Geräten, indem Sie sich die Diagramme **"Benutzer"** und **"Verteilung"** ansehen.

![Screenshot des Teams-Gerätenutzungsberichts mit nummerierten Callouts.](media/teams-device-usage-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Gerätebericht zu Teams werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie jedoch in einen bestimmten Zeitraum im Bericht klicken, werden in der Tabelle (7) Daten für 30 Tage bis zum Datum (2) angezeigt, an dem der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |In **der Ansicht** "Benutzer" wird die Anzahl der täglichen Benutzer nach Gerätetyp angezeigt. |
|**4**   |In **der Ansicht** "Verteilung" wird die Anzahl der Benutzer nach Gerät im ausgewählten Zeitraum angezeigt.  |
|**5**   | <ul><li>Im Diagramm **"Benutzer"** ist die X-Achse der ausgewählte Datumsbereich für den Bericht, und die Y-Achse gibt die Anzahl der Benutzer nach Gerätetyp an.</ul></li> <ul><li>Im Diagramm **"Verteilung"** zeigt die X-Achse die verschiedenen Geräte, die zum Herstellen einer Verbindung mit Teams verwendet werden, und die Y-Achse gibt die Anzahl der Benutzer an, die das Gerät verwenden.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Klicken oder tippen Sie beispielsweise im Diagramm **"Verteilung"** auf **"Windows",** **"Mac",** **"Linux",** **"Web",** **"iOS"** oder **"Android",** um nur die jeweils zugehörigen Informationen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Rastertabelle nicht geändert. |
|**7**   |Die Liste der aktiven Teams für den breiten Berichtszeitraum (180 Tage).  Die Anzahl der Aktivitäten variiert entsprechend der Datumsauswahl. <br><br> Um die folgenden Informationen in der Tabelle anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die Spalten hinzufügen. <ul><li>**"Benutzername"** ist die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonym machen.</ul></li> <ul><li>**Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Teamaktivität teilgenommen hat.</ul></li> <ul><li>**"Gelöscht"** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wurde, aber im Berichtszeitraum Aktivitäten hatten, wird es im Raster angezeigt, und "Gelöscht" ist auf "true" festgelegt.</ul></li><ul><li>**"Gelöscht am"** ist das Datum, an dem der Benutzer gelöscht wurde.</ul></li> <ul><li>**Windows**  ist ausgewählt, wenn der Benutzer auf einem Windows-basierten Computer im Teams-Desktopclient aktiv war.</ul></li> <ul><li>**Mac** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem macOS-Computer aktiv war.</ul></li>  <ul><li>**Linux** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem Linux-Computer aktiv war.</ul></li>   <ul><li>**Das Web** ist ausgewählt, wenn der Benutzer im Webclient von Teams aktiv war.</ul></li> <ul><li>**iOS** ist ausgewählt, wenn der Benutzer im mobilen Client von Teams für iOS aktiv war.</ul></li> <ul><li>**Android Phone ist**  ausgewählt, wenn der Benutzer auf dem mobilen Client von Teams für Android aktiv war.</ul></li></li> <ui>Wenn die Richtlinien Ihrer Organisation verhindern, dass Sie Berichte anzeigen, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Schauen Sie sich den Abschnitt **"Wie kann ich Details** auf Benutzerebene ausblenden?" in den Aktivitätsberichten in der Microsoft [365 Admin Center Preview an.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Klicken oder tippen Sie **auf "Spalten",** um Spalten in der Tabelle hinzuzufügen oder zu entfernen. |
|**9**   |Klicken oder tippen Sie **auf "Exportieren",** um Berichtsdaten in eine Excel-CSV-Datei zu exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten exportieren, um den Bericht zu filtern und zu sortieren. 

## <a name="who-can-access-the-teams-activity-reports"></a>Wer auf die Aktivitätsberichte von Teams zugreifen kann

Auf die Aktivitätsberichte können Benutzer zugreifen, denen dies zugewiesen ist:

- Rolle des globalen Administrator
- Produktspezifische Administratorrolle (Exchange, Skype for Business oder SharePoint)
- Leserrolle für Berichte

### <a name="reports-reader-role"></a>Leserrolle für Berichte

Sie können die Rolle des Lesers für Berichte Personen zuweisen, die nicht über Administratorrechte verfügen, aber dafür verantwortlich sind, die Einführung von Oder die Nutzung von Lizenzen von Teams nachverfolgung zu verfolgen. Informationen zum Zuweisen von Rollen finden Sie unter "Zuweisen von Administrator- und Administratorrollen zu Benutzern [mit Azure Active Directory".](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="other-information-on-the-reports-dashboard"></a>Weitere Informationen auf dem Dashboard "Berichte"

### <a name="at-a-glance-activity-widget"></a>Widget "Aktivität auf einen Blick"

Das Dashboard "Berichte" enthält die Nutzungsdaten von Teams im Widget "Aktivität auf einen Blick", das Ihnen eine produktübergreifende Ansicht der Kommunikation und Zusammenarbeit von Benutzern mithilfe der anderen verschiedenen Dienste in Microsoft 365 oder Office 365 bietet.

![Screenshot des Teams-Aktivitäts-Widgets auf einen Blick.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Teams-Aktivitätskarte

Die Aktivitätskarte "Teams" im Dashboard "Berichte" gibt Ihnen einen Überblick über die Aktivitäten in Teams, einschließlich der Anzahl der aktiven Benutzer, damit Sie schnell verstehen können, wie viele Benutzer den Dienst nutzen. Wenn Sie auf die Aktivitätskarte im Dashboard klicken, werden Sie zum Bericht "Teams-Benutzeraktivität" angezeigt. 

![Screenshot der Teams-Aktivitätskarte.](media/teams-activity-card.png)
