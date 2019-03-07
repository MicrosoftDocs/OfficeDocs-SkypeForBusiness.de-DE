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
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="d435f-103">Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d435f-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="d435f-104">Mithilfe des Überwachungsprotokolls können Sie bestimmte Aktivitäten in allen Office 365-Diensten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="d435f-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="d435f-105">Für Microsoft Teams werden unter anderem die folgenden Aktivitäten überwacht:</span><span class="sxs-lookup"><span data-stu-id="d435f-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="d435f-106">Teamerstellung</span><span class="sxs-lookup"><span data-stu-id="d435f-106">Team creation</span></span>

-   <span data-ttu-id="d435f-107">Löschung von Teams</span><span class="sxs-lookup"><span data-stu-id="d435f-107">Team deletion</span></span>

-   <span data-ttu-id="d435f-108">Hinzufügen von Kanälen</span><span class="sxs-lookup"><span data-stu-id="d435f-108">Added channel</span></span>

-   <span data-ttu-id="d435f-109">Ändern von Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d435f-109">Changed setting</span></span>

<span data-ttu-id="d435f-110">Eine vollständige Liste der in Office 365 überwachten Aktivitäten finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="d435f-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="d435f-111">Aktivieren der Überwachung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d435f-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="d435f-112">Bevor Überwachungsdaten angezeigt werden können, müssen Sie Überwachung in der **Sicherheit & Compliance Center**zum ersten Mal einschalten (https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="d435f-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="d435f-113">Hilfe zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="d435f-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d435f-114">Überwachungsdaten sind erst ab dem Zeitpunkt verfügbar, an dem Sie die Überwachung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="d435f-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="d435f-115">Abrufen von Microsoft Teams-Daten aus dem Überwachungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="d435f-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="d435f-116">Um Überwachungsprotokolle abzurufen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="d435f-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="d435f-117">Wählen Sie unter **Search & Investigation** (Suche und Untersuchung) die Option **Audit log search** (Überwachungsprotokollsuche) aus.![Screenshot der Seite „Audit log search“ (Überwachungsprotokollsuche) im Security & Compliance Center](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="d435f-117">Under **Search & Investigation**, select **Audit log search**.![Screenshot of the Audit log search page of the Security & Compliance Center.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span></span>



2.  <span data-ttu-id="d435f-118">Verwenden Sie die Option **Suchen**, um nach den Aktivitäten, Datumswerten und Benutzern zu filtern, die Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="d435f-118">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="d435f-119">Exportieren Sie die Ergebnisse zur weiteren Analyse nach Excel.</span><span class="sxs-lookup"><span data-stu-id="d435f-119">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d435f-120">Überwachungsdaten sind nur dann im Überwachungsprotokoll sichtbar, wenn die Überwachung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d435f-120">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="d435f-121">Video: TechTip: Verwenden der Überwachungsprotokollsuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d435f-121">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="d435f-122">Ansuman Acharya, Programm-Manager für Microsoft Teams, zeigt, wie Sie im Office 365 Security & Compliance Center eine Überwachungsprotokollsuche für Microsoft Teams durchführen.</span><span class="sxs-lookup"><span data-stu-id="d435f-122">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






