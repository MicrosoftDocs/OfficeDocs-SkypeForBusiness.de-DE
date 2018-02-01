---
title: "Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/22/2018
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Sie Microsoft Teams-Daten aus dem Office 365-Überwachungsprotokoll abrufen."
ms.openlocfilehash: 229ddc5fb1e8a775524564c27ffeecce96483fe1
ms.sourcegitcommit: 9f185be910855f6312344ea906e96e5e6449cf4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2018
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="01c31-103">Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01c31-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="01c31-104">Mithilfe des Überwachungsprotokolls können Sie bestimmte Aktivitäten in allen Office 365-Diensten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="01c31-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="01c31-105">Für Microsoft Teams werden unter anderem die folgenden Aktivitäten überwacht:</span><span class="sxs-lookup"><span data-stu-id="01c31-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="01c31-106">Teamerstellung</span><span class="sxs-lookup"><span data-stu-id="01c31-106">Team Creation</span></span>

-   <span data-ttu-id="01c31-107">Löschung von Teams</span><span class="sxs-lookup"><span data-stu-id="01c31-107">Team Deletion</span></span>

-   <span data-ttu-id="01c31-108">Hinzufügen von Kanälen</span><span class="sxs-lookup"><span data-stu-id="01c31-108">Added Channel</span></span>

-   <span data-ttu-id="01c31-109">Ändern von Einstellungen</span><span class="sxs-lookup"><span data-stu-id="01c31-109">Changed Setting</span></span>

<span data-ttu-id="01c31-110">Eine vollständige Liste der in Office 365 überwachten Aktivitäten finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span><span class="sxs-lookup"><span data-stu-id="01c31-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="01c31-111">Aktivieren der Überwachung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01c31-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="01c31-112">Damit Sie Überwachungsdaten untersuchen können, müssen Sie zuerst im **Security & Compliance Center** (https://protection.office.com) die Überwachung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="01c31-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="01c31-113">Hilfe zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="01c31-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="01c31-114">Überwachungsdaten sind erst ab dem Zeitpunkt verfügbar, an dem Sie die Überwachung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="01c31-114">Audit data is only available from the point at which Auditing was enabled.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="01c31-115">Abrufen von Microsoft Teams-Daten aus dem Überwachungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="01c31-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="01c31-116">Um Überwachungsprotokolle abzurufen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="01c31-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="01c31-117">Wählen Sie unter **Suche und Untersuchung** die Option **Überwachungsprotokollsuche** aus.</span><span class="sxs-lookup"><span data-stu-id="01c31-117">Under **Search & Investigation**, select **Audit log search**.</span></span>

![Screenshot der Seite „Überwachungsprotokollsuche“ im Security & Compliance Center](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="01c31-119">Verwenden Sie die Option **Suchen**, um nach den Aktivitäten, Datumswerten und Benutzern zu filtern, die Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="01c31-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="01c31-120">Exportieren Sie die Ergebnisse zur weiteren Analyse nach Excel.</span><span class="sxs-lookup"><span data-stu-id="01c31-120">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="01c31-121">Überwachungsdaten sind nur dann im Überwachungsprotokoll sichtbar, wenn die Überwachung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="01c31-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="01c31-122">Video: TechTip: Verwenden der Überwachungsprotokollsuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01c31-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="01c31-123">Ansuman Acharya, Programm-Manager für Microsoft Teams, zeigt, wie Sie im Office 365 Security & Compliance Center eine Überwachungsprotokollsuche für Microsoft Teams durchführen.</span><span class="sxs-lookup"><span data-stu-id="01c31-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






