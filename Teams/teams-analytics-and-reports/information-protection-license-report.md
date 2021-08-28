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
ms.openlocfilehash: 1fc9dd7dc39c8803a87f71f9ef80e2a5609603a0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625857"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams information protection license report

Der Teams Information Protection-Lizenzbericht bietet Einblicke [](/graph/api/resources/subscription?view=graph-rest-1.0) in Apps, die Änderungsbenachrichtigungsereignisse abonniert haben, um erstellte, aktualisierte oder gelöschte Nachrichten auf Mandantenebene zu hören (d. h. /teams/getAllMessage oder /chats/getAllMessages). [](/graph/api/resources/webhooks?view=graph-rest-1.0) Eine Änderungsbenachrichtigung, die der Nachricht entspricht, wird nur erfolgreich gesendet, wenn der Benutzer über die [erforderliche Lizenz verfügt.](/graph/teams-licenses)  Sie können sehen, wie viele Änderungsbenachrichtigungen von einem bestimmten Benutzer ausgelöst wurden.


## <a name="view-the-information-protection-license-report"></a>Anzeigen des Information Protection-Lizenzberichts

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](../using-admin-roles.md).

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center die Option **Analyseanalyse**&  >  **Verwendungsberichte aus.** Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **Information Protection-Lizenz aus.**
2. Wählen **Sie unter Datumsbereich** einen Bereich aus.
3. Wählen **Sie unter Apps** eine App und dann Bericht ausführen **aus.**

    ![Screenshot des Teams Information Protection-Lizenzberichts im Teams Admin Center mit Callouts](../media/teams-info-protection-license-report-with-callouts.png "Screenshot des Teams Information Protection-Lizenzberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Lizenzbericht zum Informationsschutz werden die Trends über die letzten 7 Tage, 30 oder 90 Tage angezeigt. |
|**2**   |App-Name zeigt eine Liste aller Apps an, die im Datumsbereich die Änderungsbenachrichtigungsereignisse von Nachrichten in den letzten n Tagen abonniert haben. |
|**3**   |Die Tabelle enthält eine Aufschlüsselung der Nutzung pro Benutzer für die ausgewählte App.<ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Wählen Sie den Anzeigenamen aus, um zur Detailseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**Hat erforderliche Lizenz** ist ja, wenn der Benutzer über eine der erforderlichen Lizenzen wie definiert verfügt (hier)[ https://docs.microsoft.com/en-us/graph/teams-licenses ]. Wenn der Benutzer nicht über die  erforderliche Lizenz verfügt, wird der Link Lizenz zuweisen angezeigt, der zur Seite mit den Lizenzdetails des Benutzers im Microsoft Admin Center navigiert (Benutzer aktive Benutzer > Benutzernamen  >   auswählen).</li><li>**Geschützte Lizenzereignisse ist** die Anzahl der eindeutigen Änderungsbenachrichtigungsereignisse, die für eine Nachricht an die App gesendet werden, die von diesem Benutzer erstellt, aktualisiert oder gelöscht wurde.</li></ul> |
|**4**   |Exportieren Sie den Bericht zur Offlineanalyse in eine CSV-Datei. Wählen **Sie In Excel** Exportieren aus, und klicken Sie dann auf die **Registerkarte** Downloads. Wählen **Sie Herunterladen** aus, um den Bericht herunterzuladen, sobald er bereit ist. |
|**5**   |Exportieren Sie den Bericht zur Offlineanalyse in eine CSV-Datei. Wählen **Sie In Excel** Exportieren aus, und klicken Sie dann auf die **Registerkarte** Downloads. Wählen **Sie Herunterladen** aus, um den Bericht herunterzuladen, sobald er bereit ist. Wenn Sie den Bericht in Excel anzeigen, sehen Sie  auch eine **ID** und eine E-Mail-Spalte, die die Benutzer-ID und E-Mail-Adresse des Benutzers darstellt. |

## <a name="make-the-user-specific-data-anonymous"></a>Anonymisiert benutzerspezifische Daten

Um die Daten im Bericht Teams Benutzeraktivität zu anonym machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail-Adresse und Azure AD-ID in Berichten und deren Exporten ausgeblendet.

1. Wechseln Sie Microsoft 365 Admin Center Der Dienst zu **Einstellungen** Organisation Einstellungen , und wählen Sie auf der Registerkarte Dienste \> die Option **Berichte aus.** 
    
2. Wählen **Sie Berichte** aus, und wählen Sie dann **anonyme Bezeichner anzeigen aus.** Diese Einstellung wird sowohl auf die Verwendungsberichte im Microsoft 365 Admin Center als Teams Admin Center angewendet.
  
3. Wählen Sie **Änderungen speichern aus.**
