---
title: Microsoft Teams information protection license report
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
description: Erfahren Sie, wie Sie den Teams Information Protection-Lizenzbericht im Microsoft Teams Admin Center verwenden, um zu sehen, wie Apps in Ihrer Organisation Abonnement-APIs für Änderungsbenachrichtigungsereignisse verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73ce4b5720c42cdb4e468182d6290912baf95d7e
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435859"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams information protection license report


Teams Information Protection-Lizenzbericht bietet API-Nutzungsinformationen zu [Microsoft Graph-APIs, für die Lizenz- und Zahlungsanforderungen gelten](/graph/teams-licenses). In diesem Bericht werden alle Apps hervorgehoben, die diese APIs in [model=A verwenden](/graph/teams-licenses#modela-requirements). Es wird keine Verwendung angezeigt, wenn APIs im [Modell=B](/graph/teams-licenses#modelb-requirements) oder im [Auswertungsmodus verwendet werden](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>Anzeigen des Information Protection-Lizenzberichts

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](../using-admin-roles.md).

1. Wählen Sie in der linken Navigationsleiste Microsoft Teams Admin Center die Option **Analytics &** >  **Berichte verwenden aus**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **Information Protection License aus**.
2. Wählen **Sie unter Datumsbereich** einen Bereich aus.
3. Wählen **Sie** unter Apps eine App und dann Bericht **ausführen aus**.

    ![Screenshot des Dropdownberichts Teams Information Protection-Lizenzberichts im Teams Admin Center mit Callouts.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Screenshot des Dropdownberichts Teams Information Protection-Lizenzberichts im Teams Admin Center mit Callouts.")

4. Für jede Kategorie können Metriken zu Benutzern mit Lizenz, Benutzern ohne Lizenz, Startkapazität und ausgelasteter Kapazität angezeigt werden. 

    ![Screenshot of the summary chart of Teams information protection license report in the Teams admin center of change notification with callouts.](../media/teams-info-protection-license-report-chart-with-callouts.png "Screenshot of the summary chart of Teams information protection license report in the Teams admin center of change notification with callouts.")

5. Die Daten können exportiert werden, indem Sie auf die Schaltfläche "Exportieren" klicken. Die Tabellendaten können durch Klicken auf die Registerkarten für Teams-API für Änderungsbenachrichtigungen, Teams-Patch-API, Teams Export-APIs (Chat) und Teams-Export-APIs (Teams) gewechselt werden. 

    ![Screenshot der verschiedenen Registerkarten Teams Information Protection-Lizenzberichts im Teams Admin Center mit Callouts.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Screenshot der verschiedenen Registerkarten Teams Information Protection-Lizenzberichts im Teams Admin Center mit Callouts.")

    ![Screenshot der Registerkarte "Änderungsbenachrichtigung" Teams Information Protection-Lizenzberichts im Teams Admin Center mit Callouts.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Screenshot der Registerkarte &quot;Änderungsbenachrichtigung&quot; Teams Information Protection-Lizenzberichts im Teams Admin Center mit Callouts.")


## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht information protection license (Lizenz zum Schutz von Informationen) werden die Trends in den letzten drei Monaten angezeigt. |
|**2**   |Der App-Name zeigt eine Liste aller Apps an, die [die Microsoft Graph-API verwendet](/graph/teams-licenses) haben und für die während des ausgewählten Zeitraums Lizenz- und Zahlungsanforderungen gelten.|
|**3**   |Die Anzahl der Benutzer, die über gültige Lizenzen [verfügen](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |Die Anzahl der Benutzer, die nicht über eine gültige Lizenz [verfügen](/graph/teams-licenses#required-licenses-for-modela).  |
|**5**   |Das gesamte für eine App zulässige API-Aufrufvolumen, über das hinaus eine Nutzungsgebühr pro API-Aufruf an die App berechnet wird. |
|**6**   |Gesamtvolumen für API-Aufrufe, die von der App für den angegebenen Datumsbereich verwendet werden. |
|**7**   |Exportieren Sie den Bericht zur Offlineanalyse in eine CSV-Datei. Wählen **Sie In Excel** Exportieren und dann die **Registerkarte Downloads** aus. Wählen Sie **Herunterladen** aus, um den Bericht herunterzuladen, wenn er bereit ist. Bei diesem Export wird nur die aktuell ausgewählte Registerkarte exportiert.|
|**8**   |Wählen Sie eine bestimmte Beschriftung aus, um sie in einem Diagramm ein- oder auszublenden. |
|**9**   |Auf jeder Registerkarte wird die Verwendung einer bestimmten Gruppe von APIs angezeigt: Änderungsbenachrichtigung [,](/graph/api/resources/webhooks) [Export-API](/microsoftteams/export-teams-content) und [API für Aktualisierungsmeldungen](/graph/api/message-update). Wählen Sie eine Registerkarte aus, um die Verwendungsdetails dieser API anzuzeigen. |
|**10**   |**Verwendung der Änderungsbenachrichtigungs-API**<li>**Anzeigename** – Der Anzeigename des Benutzers, für den eine Änderungsbenachrichtigung ausgelöst wurde.</li><li>**Erforderliche Lizenz** : Gibt an, ob der angegebene Benutzer über die erforderliche Lizenz zum erfolgreichen Senden einer Änderungsbenachrichtigung an die App verfügt.</li><li>**Attempted Count** – Gesamtzahl der Änderungsbenachrichtigungen, die aufgrund dieses Benutzers ausgelöst wurden.</li><li>**Änderungsbenachrichtigung gesendet** – Die Gesamtzahl der Änderungsbenachrichtigungen, die an die App gesendet wurden. Dies ist kleiner als die Insgesamt ausgelösten Änderungsbenachrichtigungen, wenn der Benutzer keine gültige Lizenz besitzt.</li>|
|**11**|**Patch-API**<li>**Anzeigename** – Der Anzeigename des Benutzers, der versucht hat, die Nachricht zu aktualisieren.</li> <li>**Erforderliche Lizenz** : Gibt an, ob der angegebene Benutzer über die erforderliche Lizenz für die Nachricht verfügt, um erfolgreich aktualisiert zu werden.</li><li>**Attempted Count** – Gesamtzahl der Versuche, Nachrichten zu aktualisieren.</li><li>**Nachricht mit Patch-** – Gesamtzahl der Nachrichten, die erfolgreich aktualisiert wurden.</li>|
|**12**|**Verwendung der Chatexport-API**<li>**Anzeigename** – Der Anzeigename des Benutzers, bei dem der Versuch ausgeführt wurde, die Chatnachricht des Benutzers zu exportieren.</li><li>**Erforderliche Lizenz** : Gibt an, ob der angegebene Benutzer über die erforderliche Lizenz für den erfolgreichen Export der Nachricht verfügt.</li><li>**Attempted Count** – Alle Versuche zum Exportieren von Chatnachrichten.</li><li>**Nachricht exportiert:** Gesamtzahl der Versuche, bei denen die Chatnachricht erfolgreich exportiert wurde.</li> |
|**13**|**Verwendung der Teamexport-API**<li>**Anzeigename** – Der Anzeigename des Teams, bei dem der Versuch ausgeführt wurde, die Nachricht dieses Teams zu exportieren.</li><li>**Attempted Count** – Gesamtzahl der Versuche zum Exportieren von Teamnachrichten.</li><li>**Nachricht exportiert:** Gesamtzahl der Versuche, bei denen die Teamnachricht erfolgreich exportiert wurde.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Anonymisiert benutzerspezifische Daten

Um die Daten im Bericht Teams Benutzeraktivität anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail-Adresse und Azure AD-ID in Berichten und deren Exporten ausgeblendet.

1. Wechseln Sie Microsoft 365 Admin Center Der Bericht zu  \> Einstellungen **Organisations-Einstellungen**, und wählen Sie auf der Registerkarte Dienste die Option  Berichte **aus**.
    
2. Wählen **Sie Berichte** und dann **anonyme Bezeichner anzeigen aus**. Diese Einstellung wird sowohl auf die Verwendungsberichte im Microsoft 365 Admin Center als Teams Admin Center angewendet.
  
3. Wählen Sie **Änderungen speichern aus**.