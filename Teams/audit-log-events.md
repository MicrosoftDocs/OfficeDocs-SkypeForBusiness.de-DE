---
title: Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Microsoft Teams-Daten aus dem Office 365-Überwachungsprotokoll abrufen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5207007b3855f5fa093050ac0ff8c885fd333af
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464052"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Mithilfe des Überwachungsprotokolls können Sie bestimmte Aktivitäten in allen Office 365-Diensten untersuchen. Für Microsoft Teams werden unter anderem die folgenden Aktivitäten überwacht:

-   Teamerstellung

-   Löschung von Teams

-   Hinzufügen von Kanälen

-   Ändern von Einstellungen

Eine vollständige Liste der in Office 365 überwachten Aktivitäten finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="turn-on-auditing-in-teams"></a>Aktivieren der Überwachung in Microsoft Teams

Bevor Überwachungsdaten angezeigt werden können, müssen Sie Überwachung in der **Sicherheit & Compliance Center**zum ersten Mal einschalten (https://protection.office.com). Hilfe zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).


> [!IMPORTANT]
> Überwachungsdaten sind erst ab dem Zeitpunkt verfügbar, an dem Sie die Überwachung aktiviert haben.



## <a name="retrieve-teams-data-from-the-audit-log"></a>Abrufen von Microsoft Teams-Daten aus dem Überwachungsprotokoll

1.  Um Überwachungsprotokolle abzurufen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775). Wählen Sie unter **Search & Investigation** (Suche und Untersuchung) die Option **Audit log search** (Überwachungsprotokollsuche) aus.![Screenshot der Seite „Audit log search“ (Überwachungsprotokollsuche) im Security & Compliance Center](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)



2.  Verwenden Sie die Option **Suchen**, um nach den Aktivitäten, Datumswerten und Benutzern zu filtern, die Sie überwachen möchten.

3.  Exportieren Sie die Ergebnisse zur weiteren Analyse nach Excel.


> [!IMPORTANT]
> Überwachungsdaten sind nur dann im Überwachungsprotokoll sichtbar, wenn die Überwachung aktiviert ist.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Video: TechTip: Verwenden der Überwachungsprotokollsuche in Microsoft Teams

Ansuman Acharya, Programm-Manager für Microsoft Teams, zeigt, wie Sie im Office 365 Security & Compliance Center eine Überwachungsprotokollsuche für Microsoft Teams durchführen. 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






