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
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Aktivitätsberichte verwenden, um zu sehen, wie Benutzer in Ihrer Organisation Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 128979e3123c443ac746f7dd87a149bbeacb3635
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853829"
---
# <a name="use-activity-reports-for-microsoft-teams"></a>Verwenden von Aktivitätsberichten für Microsoft Teams 

Sie können Aktivitätsberichte im Microsoft 365 Admin Center, um zu sehen, wie Benutzer in Ihrer Organisation Microsoft Teams. Wenn einige Benutzer z. B. Microsoft Teams noch nicht verwenden, wissen sie möglicherweise nicht, wie sie die ersten Schritte unternehmen oder verstehen, wie sie Teams nutzen können, um produktiver und zusammenarbeiten zu können. Ihre Organisation kann mithilfe der Aktivitätsberichte entscheiden, wo Schulungs- und Kommunikationsinitiativen priorisiert ansetzen sollen.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>So zeigen Sie die Teams im Dashboard "Berichte" an

1. Wählen Sie [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) **Berichtnutzung**  >  **aus.**
 
2. Wählen Sie **auf** der Seite Verwendung die **Option** Bericht auswählen aus, und wählen Sie Microsoft Teams **dann** unter Bericht in der Liste der Berichte den Bericht aus, den Sie anzeigen möchten.

## <a name="teams-activity-reports-that-are-available"></a>Teams verfügbaren Aktivitätsberichte

Es gibt derzeit zwei Aktivitätsberichte, die Sie anzeigen können:

- [Microsoft Teams – Benutzeraktivitätsbericht](#microsoft-teams-user-activity-report) 
- [Microsoft Teams – Gerätenutzungsbericht](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams – Benutzeraktivitätsbericht

Im Teams Benutzeraktivitätsbericht finden Sie eine Ansicht der aktivitäten, die Ihre Benutzer am häufigsten in einem Teams. Dies umfasst, wie viele Personen an einem Chat in einem Kanal teilnehmen, wie viele Personen per privater Chatnachricht kommunizieren und wie viele Personen an Anrufen oder Besprechungen teilnehmen. Sie können diese Informationen für Ihre gesamte Organisation sowie für jeden einzelnen Benutzer sehen.

![Screenshot des Benutzeraktivitätsberichts im Admin Center.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretieren des Microsoft Teams Benutzeraktivitätsberichts

Sie erhalten einen Einblick in Teams Benutzeraktivitäten, indem Sie sich die Diagramme **Aktivität und** **Benutzer ansehen.**

![Screenshot des Benutzeraktivitätsberichts mit nummerierten Callouts.](media/teams-user-activity-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im bericht Teams Benutzeraktivität werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch in einen bestimmten Zeitraum klicken, werden in der Tabelle (7) Daten für 30 Tage bis zum Datum (2) angezeigt, an dem der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |In **der Ansicht** Aktivität wird die Anzahl der aktivitäten Microsoft Teams Aktivitätstyp angezeigt. Die Aktivitätstypen sind Anzahl der Teamchatnachrichten, privaten Chatnachrichten, Anrufe und Besprechungen. |
|**4**   |In **der Ansicht** Benutzer wird die Anzahl der Benutzer nach Aktivitätstyp angezeigt. Die Aktivitätstypen sind Anzahl der Teamchatnachrichten, privaten Chatnachrichten, Anrufe und Besprechungen. |
|**5**   |Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht. <ul><li>Im Diagramm **Aktivität** gibt die Y-Achse die Anzahl der angegebenen Aktivität an.</ul></li> <ul><li>Im Diagramm **Benutzer gibt** die Y-Achse die Anzahl der Benutzer an, die an Teamchats, privaten Chats, Anrufen oder Besprechungen teilnehmen.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Klicken oder tippen  Sie beispielsweise im Diagramm Aktivität auf **Kanalnachrichten**, **Chatnachrichten** **,** Anrufe oder Besprechungen, um nur die jeweils zugehörigen Informationen zu sehen.  Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert. |
|**7**   |Die Liste der aktiven Teams über den gesamten Berichtszeitraum (180 Tage).  Die Anzahl der Aktivitäten variiert entsprechend der Datumsauswahl. <br><br> Um die folgenden Informationen in der Tabelle anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die Spalten hinzufügen. <ul><li>**Benutzername ist** die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonym machen.</ul></li> <ul><li>**Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Aktivität Microsoft Teams hat.</ul></li> <ul><li>**Kanalnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem Teamchat gepostet hat.</ul></li> <ul><li>**Chatnachrichten** ist die Anzahl der eindeutigen Nachrichten, die der Benutzer während des angegebenen Zeitraums in einem privaten Chat gepostet hat.</ul></li> <ul><li>**Anrufe** ist die Anzahl der Anrufe, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</ul></li> <ul><li>**Besprechungen** ist die Anzahl der Onlinebesprechungen, an der der Benutzer während des angegebenen Zeitraums teilgenommen hat.</ul></li> <ul><li>**Bei** anderen Aktivitäten handelt es sich um die Anzahl anderer Teamaktivitäten des Benutzers, von denen einige umfassen und nicht darauf beschränkt sind: Nachrichten, Apps, Arbeiten an Dateien, Suchen, Folgen von Teams und Kanälen und Favorisieren von Nachrichten.</ul></li> <ul><li>**Gelöscht** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wurde, aber im Berichtszeitraum Aktivitäten hatten, wird es im Raster angezeigt, und gelöscht wurde auf TRUE festgelegt.</ul></li> <ul><li>**Gelöscht am** ist das Datum, an dem der Benutzer gelöscht wurde.</ul></li> <ul><li>**Zugewiesenes** Produkt ist die Liste der Produkte, die dem Benutzer zugewiesen sind.</ul></li>Wenn die Richtlinien Ihrer Organisation verhindern, dass Sie Berichte anzeigen, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den **Abschnitt Ausblenden von Details auf** Benutzerebene unter Aktivitätsberichte in Microsoft 365 Admin Center [Preview.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Klicken oder tippen Sie **auf Spalten,** um Spalten in der Tabelle hinzuzufügen oder zu entfernen. |
|**9**   |Klicken oder tippen Sie **auf Exportieren,** um Berichtsdaten in eine Excel .csv exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren des Berichts exportieren. 

### <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Der Teams Bericht zur Gerätenutzung enthält Informationen darüber, wie Ihre Benutzer eine Verbindung mit Ihrem Teams, einschließlich mobiler Apps. Der Bericht hilft Ihnen zu verstehen, welche Geräte in Ihrer Organisation beliebt sind und wie viele Benutzer unterwegs arbeiten.

![Screenshot des Berichts Teams Gerätenutzung"](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretieren des Microsoft Teams Geräteverwendungsberichts

Einen Einblick in die Nutzung Teams Geräte erhalten Sie in den Diagrammen Benutzer **und** **Verteilung.**

![Screenshot des Berichts Teams geräteverwendungsberichts mit nummerierten Callouts.](media/teams-device-usage-report-with-callouts.png)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im bericht Teams Werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch in einen bestimmten Zeitraum klicken, werden in der Tabelle (7) Daten für 30 Tage bis zum Datum (2) angezeigt, an dem der Bericht generiert wurde. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |In **der Ansicht** Benutzer wird die Anzahl der täglichen Benutzer nach Gerätetyp angezeigt. |
|**4**   |In **der Ansicht** Verteilung wird die Anzahl der Benutzer nach Gerät im ausgewählten Zeitraum angezeigt.  |
|**5**   | <ul><li>Im Diagramm **Benutzer** ist die X-Achse der ausgewählte Datumsbereich für den Bericht, und die Y-Achse gibt die Anzahl der Benutzer nach Gerätetyp an.</ul></li> <ul><li>Im Diagramm **Verteilung** zeigt die X-Achse die verschiedenen Geräte an, die zum Herstellen einer Verbindung mit Teams verwendet werden, und die Y-Achse gibt die Anzahl der Benutzer an, die das Gerät verwenden.</ul></li> |
|**6**   |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Klicken oder tippen  Sie beispielsweise im Diagramm Verteilung auf **Windows**, **Mac,** **Linux,** **Web,** **iOS** oder **Android,** um nur die jeweils zugehörigen Informationen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert. |
|**7**   |Die Liste der aktiven Teams über den gesamten Berichtszeitraum (180 Tage).  Die Anzahl der Aktivitäten variiert entsprechend der Datumsauswahl. <br><br> Um die folgenden Informationen in der Tabelle anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die Spalten hinzufügen. <ul><li>**Benutzername ist** die E-Mail-Adresse des Benutzers. Sie können die eigentliche E-Mail-Adresse anzeigen oder dieses Feld anonym machen.</ul></li> <ul><li>**Datum der letzten Aktivität (UTC)** bezieht sich auf das letzte Datum, an dem der Benutzer an einer Aktivität Teams hat.</ul></li> <ul><li>**Gelöscht** gibt an, ob das Team gelöscht wurde. Wenn das Team gelöscht wurde, aber im Berichtszeitraum Aktivitäten hatten, wird es im Raster angezeigt, und gelöscht wurde auf TRUE festgelegt.</ul></li><ul><li>**Gelöscht am** ist das Datum, an dem der Benutzer gelöscht wurde.</ul></li> <ul><li>**Windows** wird ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem Windows Computer aktiv war.</ul></li> <ul><li>**Mac** ist ausgewählt, wenn der Benutzer im Desktopclient Teams auf einem macOS-Computer aktiv war.</ul></li>  <ul><li>**Linux** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem Linux-Computer aktiv war.</ul></li>   <ul><li>**Web** ist ausgewählt, wenn der Benutzer auf dem Teams-Client aktiv war.</ul></li> <ul><li>**iOS** ist ausgewählt, wenn der Benutzer auf dem mobilen Teams für iOS aktiv war.</ul></li> <ul><li>**Android-Smartphone** ist ausgewählt, wenn der Benutzer auf dem mobilen Teams für Android aktiv war.</ul></li></li> Wenn die Richtlinien Ihrer Organisation verhindern, dass Sie Berichte anzeigen, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den **Abschnitt Ausblenden von Details auf** Benutzerebene unter Aktivitätsberichte in Microsoft 365 Admin Center [Preview.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Klicken oder tippen Sie **auf Spalten,** um Spalten in der Tabelle hinzuzufügen oder zu entfernen. |
|**9**   |Klicken oder tippen Sie **auf Exportieren,** um Berichtsdaten in eine Excel .csv exportieren. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren des Berichts exportieren. 

## <a name="who-can-access-the-teams-activity-reports"></a>Wer können auf die Teams-Aktivitätsberichte zugreifen

Benutzer, die zugewiesen sind, können auf die Aktivitätsberichte zugreifen:

- Globale Administratorrolle
- Produktspezifische Administratorrolle (Exchange, Skype for Business oder SharePoint)
- Leserrolle "Berichte"

### <a name="reports-reader-role"></a>Leserrolle "Berichte"

Sie können die Leserrolle "Berichte" Personen zuweisen, die nicht über Administratorrechte verfügen, aber dafür verantwortlich sind, die Einführung oder die Nachverfolgung der Lizenznutzung von Teams. Informationen zum Zuweisen von Rollen finden Sie unter Zuweisen von [Administrator- und Nicht-Administratorrollen](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)zu Benutzern mit Azure Active Directory.

## <a name="other-information-on-the-reports-dashboard"></a>Weitere Informationen im Dashboard "Berichte"

### <a name="at-a-glance-activity-widget"></a>Widget "Aktivität auf einen Blick"

Das Dashboard Berichte enthält die Nutzungsdaten von Teams im Widget "Aktivität auf einen Blick", das Ihnen eine produktübergreifende Ansicht der Kommunikation und Zusammenarbeit der Benutzer mithilfe der anderen verschiedenen Dienste in Microsoft 365 oder Office 365 bietet.

![Screenshot des Widgets Teams"-Widget "Aktivität auf einen Blick".](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Teams-Aktivitätskarte

Die Teams-Aktivitätskarte im Dashboard Berichte bietet Ihnen einen Überblick über die Aktivität in Teams, einschließlich der Anzahl der aktiven Benutzer, damit Sie schnell verstehen können, wie viele Benutzer den Dienst nutzen. Wenn Sie auf die Aktivitätskarte im Dashboard klicken, werden Sie zum bericht Teams Benutzeraktivität angezeigt. 

![Screenshot der Teams-Aktivitätskarte.](media/teams-activity-card.png)