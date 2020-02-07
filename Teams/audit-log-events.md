---
title: Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Microsoft Teams-Daten aus dem Office 365-Überwachungsprotokoll abrufen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c1f82a7688e3fdde7be85004c717293cc5777fa
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826273"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Mithilfe des Überwachungsprotokolls können Sie bestimmte Aktivitäten in allen Office 365-Diensten untersuchen. Für Microsoft Teams werden unter anderem die folgenden Aktivitäten überwacht:

- Teamerstellung

- Löschung von Teams

- Hinzufügen von Kanälen

- Ändern von Einstellungen

> [!NOTE]
> Überwachungsereignisse von privaten Kanälen werden auch so protokolliert, wie Sie für Teams und Standardkanäle gelten.

Eine vollständige Liste der in Office 365 überwachten Aktivitäten finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="turn-on-auditing-in-teams"></a>Aktivieren der Überwachung in Microsoft Teams

Bevor Sie sich die Überwachungsdaten ansehen können, müssen Sie zuerst die Überwachung im [Security #a0 Compliance Center](https://protection.office.com)aktivieren. Hilfe zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> Überwachungsdaten sind erst ab dem Zeitpunkt verfügbar, an dem Sie die Überwachung aktiviert haben.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Abrufen von Microsoft Teams-Daten aus dem Überwachungsprotokoll


1.  Um Überwachungsprotokolle abzurufen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775). Wählen Sie unter **Suchen**die Option **Überwachungsprotokoll Suche**aus.



2. Verwenden Sie die Option **Suchen**, um nach den Aktivitäten, Datumswerten und Benutzern zu filtern, die Sie überwachen möchten.

3. Exportieren Sie die Ergebnisse zur weiteren Analyse nach Excel.

> [!IMPORTANT]
> Überwachungsdaten sind nur dann im Überwachungsprotokoll sichtbar, wenn die Überwachung aktiviert ist.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Video: TechTip: Verwenden der Überwachungsprotokollsuche in Microsoft Teams

Ansuman Acharya, Programm-Manager für Microsoft Teams, zeigt, wie Sie im Office 365 Security & Compliance Center eine Überwachungsprotokollsuche für Microsoft Teams durchführen. 

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
