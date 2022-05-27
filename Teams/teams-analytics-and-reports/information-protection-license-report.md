---
title: Microsoft Teams Information Protection-Lizenzbericht
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie den Lizenzbericht Teams Information Protection im Microsoft Teams Admin Center verwenden, um zu sehen, wie Apps in Ihrer Organisation Abonnement-APIs für Änderungsbenachrichtigungsereignisse verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fade7b4d5d89061cdc1dd5eb231a80d5ee9e8938
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681536"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams Information Protection-Lizenzbericht


Teams Lizenzbericht zum Informationsschutz bietet EINBLICKE in die API-Nutzung von [Microsoft Graph-APIs, die Lizenz- und Zahlungsanforderungen haben](/graph/teams-licenses). In diesem Bericht werden alle Apps hervorgehoben, die diese APIs in [Model=A](/graph/teams-licenses#modela-requirements) verwenden. Die Verwendung wird nicht angezeigt, wenn APIs im [Model=B](/graph/teams-licenses#modelb-requirements) - oder [Auswertungsmodus](/graph/teams-licenses#evaluation-mode-default-requirements) verwendet werden. 


## <a name="view-the-information-protection-license-report"></a>Anzeigen des Lizenzberichts zum Informationsschutz

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](../using-admin-roles.md).

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **Die Option "Analyse" & Berichte** > **"Nutzungsberichte"** aus. Wählen Sie auf der Registerkarte "**Berichte anzeigen**" unter **"Bericht**" **Information Protection Lizenz** aus.
2. Wählen Sie unter **"Datumsbereich**" einen Bereich aus.
3. Wählen Sie unter **"Apps**" eine App und dann " **Bericht ausführen" aus**.

    ![Screenshot der Dropdownliste Teams Lizenzberichts zum Informationsschutz im Teams Admin Center mit Popups.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Screenshot der Dropdownliste Teams Lizenzberichts zum Informationsschutz im Teams Admin Center mit Popups.")

4. Für jede Kategorie können Metriken für Benutzer mit Lizenz, Benutzer ohne Lizenz, Seedingkapazität und genutzte Kapazität angezeigt werden. 

    ![Screenshot des Zusammenfassungsdiagramms Teams Lizenzberichts zum Informationsschutz im Teams Admin Center der Änderungsbenachrichtigung mit Beschriftungen.](../media/teams-info-protection-license-report-chart-with-callouts.png "Screenshot des Zusammenfassungsdiagramms Teams Lizenzberichts zum Informationsschutz im Teams Admin Center der Änderungsbenachrichtigung mit Beschriftungen.")

5. Die Daten können durch Klicken auf die Schaltfläche "Exportieren" exportiert werden. Die Tabellendaten können durch Klicken auf die Registerkarten für Teams Änderungsbenachrichtigungs-API, Teams Patch-API, Teams Export-APIs (Chat) und Teams Export-APIs (Teams) gewechselt werden. 

    ![Screenshot der verschiedenen Registerkarten des Lizenzberichts Teams Information Protection im Teams Admin Center von Registerkarten mit Beschriftungen.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Screenshot der verschiedenen Registerkarten des Lizenzberichts Teams Information Protection im Teams Admin Center von Registerkarten mit Beschriftungen.")

    ![Screenshot der Registerkarte "Änderungsbenachrichtigung" Teams Lizenzberichts zum Informationsschutz im Teams Admin Center mit Popups.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Screenshot der Registerkarte &quot;Änderungsbenachrichtigung&quot; Teams Lizenzberichts zum Informationsschutz im Teams Admin Center mit Popups.")


## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Information Protection-Lizenzbericht kann nach Trends in den letzten drei Monaten angezeigt werden.The information protection license report can be viewed for trends over the last three months. |
|**2**   |Der App-Name zeigt eine Liste aller Apps an, die Microsoft Graph-API verwendet haben, für die im ausgewählten Zeitraum [Lizenz- und Zahlungsanforderungen gelten](/graph/teams-licenses).|
|**3**   |Anzahl der Benutzer, die über gültige [Lizenzen verfügen](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |Anzahl der Benutzer, die nicht über eine gültige [Lizenz verfügen](/graph/teams-licenses#required-licenses-for-modela).  |
|**5**   |Das gesamte für eine App zulässige API-Anrufvolumen, über das der App eine Verbrauchsgebühr pro API-Aufruf in Rechnung gestellt wird. |
|**6**   |Gesamtanzahl der API-Aufrufe, die von der App für den angegebenen Datumsbereich verwendet wird. |
|**7**   |Exportieren Sie den Bericht zur Offlineanalyse in eine CSV-Datei. Wählen Sie **"In Excel exportieren**" und dann die Registerkarte "**Downloads**" aus. Wählen Sie "**Herunterladen**" aus, um den Bericht herunterzuladen, wenn er bereit ist. Bei diesem Export wird nur die aktuell ausgewählte Registerkarte exportiert.|
|**8**   |Wählen Sie eine bestimmte Beschriftung aus, um sie in einem Diagramm ein- oder auszublenden. |
|**9**   |Auf jeder Registerkarte wird die Verwendung einer bestimmten Gruppe von APIs angezeigt, nämlich [Änderungsbenachrichtigungen](/graph/api/resources/webhooks), [Export-API](/microsoftteams/export-teams-content) und [Updatenachrichten-API](/graph/api/message-update). Wählen Sie eine Registerkarte aus, um Nutzungsdetails dieser API anzuzeigen. |
|**10**   |**Verwendung der Änderungsbenachrichtigungs-API**<li>**Anzeigename** – Anzeigename des Benutzers, für den eine Änderungsbenachrichtigung ausgelöst wurde.</li><li>**Erforderliche Lizenz** – Gibt an, ob der angegebene Benutzer über die erforderliche Lizenz verfügt, um erfolgreich eine Änderungsbenachrichtigung an die App zu senden.</li><li>**Anzahl versucht** : Gesamtzahl der Änderungsbenachrichtigungen, die aufgrund dieses Benutzers ausgelöst wurden.</li><li>**Änderungsbenachrichtigung gesendet** – Gesamtanzahl der Änderungsbenachrichtigungen, die an die App gesendet wurden. Dies ist kleiner als die Gesamtzahl der ausgelösten Änderungsbenachrichtigungen, wenn der Benutzer nicht über eine gültige Lizenz verfügt.</li>|
|**11**|**Patch-API**<li>**Anzeigename** – Anzeigename des Benutzers, bei dem versucht wurde, die Nachricht zu aktualisieren.</li> <li>**Erforderliche Lizenz** – Gibt an, ob der angegebene Benutzer über die erforderliche Lizenz verfügt, damit die Nachricht erfolgreich aktualisiert wird.</li><li>**Anzahl der Versuchten** – Gesamtzahl der Versuche, Nachrichten zu aktualisieren.</li><li>**Nachricht gepatcht** – Gesamtanzahl der Nachrichten, die erfolgreich aktualisiert wurden.</li>|
|**12**|**Verwendung der Chatexport-API**<li>**Anzeigename** – Anzeigename des Benutzers, bei dem versucht wurde, die Chatnachricht des Benutzers zu exportieren.</li><li>**Erforderliche Lizenz** – Gibt an, ob der angegebene Benutzer über die erforderliche Lizenz verfügt, damit die Nachricht erfolgreich exportiert wird.</li><li>**Anzahl der Versuchten** – Gesamtanzahl der Versuche, Chatnachrichten zu exportieren.</li><li>**Nachricht exportiert** – Gesamtanzahl der Versuche, bei denen die Chatnachricht erfolgreich exportiert wurde.</li> |
|**13**|**Verwendung der Teamexport-API**<li>**Anzeigename** – Anzeigename des Teams, in dem ein Exportversuch für die Nachricht dieses Teams durchgeführt wurde.</li><li>**Anzahl der Versuche** – Gesamtanzahl der Versuche, Teamnachrichten zu exportieren.</li><li>**Nachricht exportiert** – Gesamtanzahl der Versuche, bei denen die Teamnachricht erfolgreich exportiert wurde.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Anonymisieren der benutzerspezifischen Daten

Um die Daten im Bericht über Teams Benutzeraktivität anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail und Azure AD-ID in Berichten und deren Exporten ausgeblendet.

1. Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** \> **Organisations-Einstellungen**, und wählen Sie unter der Registerkarte "**Dienste**" die Option "**Berichte**" aus.
    
2. Wählen Sie **"Berichte**" und dann " **Anonyme Bezeichner anzeigen" aus**. Diese Einstellung wird sowohl auf die Verwendungsberichte im Microsoft 365 Admin Center als auch auf das Teams Admin Center angewendet.
  
3. Wählen Sie **"Änderungen speichern" aus**.