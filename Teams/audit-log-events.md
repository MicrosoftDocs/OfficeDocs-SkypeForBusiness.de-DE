---
title: "Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: "Hier erfahren Sie, wie Sie Microsoft Teams-Daten aus dem Office 365-Überwachungsprotokoll abrufen."
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f0fa9f55e10d3f2f9b29287b292878c3c2b5b4a
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="c45bf-103">Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c45bf-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="c45bf-104">Mithilfe des Überwachungsprotokolls können Sie bestimmte Aktivitäten in allen Office 365-Diensten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="c45bf-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="c45bf-105">Für Microsoft Teams werden unter anderem die folgenden Aktivitäten überwacht:</span><span class="sxs-lookup"><span data-stu-id="c45bf-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="c45bf-106">Teamerstellung</span><span class="sxs-lookup"><span data-stu-id="c45bf-106">Team creation</span></span>

-   <span data-ttu-id="c45bf-107">Löschung von Teams</span><span class="sxs-lookup"><span data-stu-id="c45bf-107">Team deletion</span></span>

-   <span data-ttu-id="c45bf-108">Hinzufügen von Kanälen</span><span class="sxs-lookup"><span data-stu-id="c45bf-108">Added channel</span></span>

-   <span data-ttu-id="c45bf-109">Ändern von Einstellungen</span><span class="sxs-lookup"><span data-stu-id="c45bf-109">Changed setting</span></span>

<span data-ttu-id="c45bf-110">Eine vollständige Liste der in Office 365 überwachten Aktivitäten finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span><span class="sxs-lookup"><span data-stu-id="c45bf-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="c45bf-111">Aktivieren der Überwachung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c45bf-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="c45bf-112">Damit Sie Überwachungsdaten untersuchen können, müssen Sie zuerst im **Security & Compliance Center** (https://protection.office.com) die Überwachung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c45bf-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="c45bf-113">Hilfe zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="c45bf-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c45bf-114">Überwachungsdaten sind erst ab dem Zeitpunkt verfügbar, an dem Sie die Überwachung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c45bf-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="c45bf-115">Abrufen von Microsoft Teams-Daten aus dem Überwachungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="c45bf-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="c45bf-116">Um Überwachungsprotokolle abzurufen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="c45bf-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="c45bf-117">Wählen Sie unter **Search & Investigation** (Suche und Untersuchung) die Option **Audit log search** (Überwachungsprotokollsuche) aus.![Screenshot der Seite „Audit log search“ (Überwachungsprotokollsuche) im Security & Compliance Center](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="c45bf-117">Under **Search & Investigation**, select **Audit log search**.![Screenshot of the Audit log search page of the Security & Compliance Center.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span></span>



2.  <span data-ttu-id="c45bf-118">Verwenden Sie die Option **Suchen**, um nach den Aktivitäten, Datumswerten und Benutzern zu filtern, die Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="c45bf-118">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="c45bf-119">Exportieren Sie die Ergebnisse zur weiteren Analyse nach Excel.</span><span class="sxs-lookup"><span data-stu-id="c45bf-119">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c45bf-120">Überwachungsdaten sind nur dann im Überwachungsprotokoll sichtbar, wenn die Überwachung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c45bf-120">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="c45bf-121">Video: TechTip: Verwenden der Überwachungsprotokollsuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c45bf-121">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="c45bf-122">Ansuman Acharya, Programm-Manager für Microsoft Teams, zeigt, wie Sie im Office 365 Security & Compliance Center eine Überwachungsprotokollsuche für Microsoft Teams durchführen.</span><span class="sxs-lookup"><span data-stu-id="c45bf-122">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






