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
ms.reviewer: anach
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Microsoft Teams-Daten aus dem Office 365-Überwachungsprotokoll abrufen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ee0c5175e3712881b1f51b3c98156ba8f179012d
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793381"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="cf3d7-103">Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf3d7-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="cf3d7-104">Mithilfe des Überwachungsprotokolls können Sie bestimmte Aktivitäten in allen Office 365-Diensten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="cf3d7-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="cf3d7-105">Für Microsoft Teams werden unter anderem die folgenden Aktivitäten überwacht:</span><span class="sxs-lookup"><span data-stu-id="cf3d7-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="cf3d7-106">Teamerstellung</span><span class="sxs-lookup"><span data-stu-id="cf3d7-106">Team creation</span></span>

- <span data-ttu-id="cf3d7-107">Löschung von Teams</span><span class="sxs-lookup"><span data-stu-id="cf3d7-107">Team deletion</span></span>

- <span data-ttu-id="cf3d7-108">Hinzufügen von Kanälen</span><span class="sxs-lookup"><span data-stu-id="cf3d7-108">Added channel</span></span>

- <span data-ttu-id="cf3d7-109">Ändern von Einstellungen</span><span class="sxs-lookup"><span data-stu-id="cf3d7-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="cf3d7-110">Überwachungsereignisse von privaten Kanälen werden auch so protokolliert, wie Sie für Teams und Standardkanäle gelten.</span><span class="sxs-lookup"><span data-stu-id="cf3d7-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="cf3d7-111">Eine vollständige Liste der in Office 365 überwachten Aktivitäten finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="cf3d7-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="cf3d7-112">Aktivieren der Überwachung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf3d7-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="cf3d7-113">Bevor Sie sich die Überwachungsdaten ansehen können, müssen Sie zuerst die Überwachung im [Security #a0 Compliance Center](https://protection.office.com)aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cf3d7-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="cf3d7-114">Hilfe zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="cf3d7-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf3d7-115">Überwachungsdaten sind erst ab dem Zeitpunkt verfügbar, an dem Sie die Überwachung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="cf3d7-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="cf3d7-116">Abrufen von Microsoft Teams-Daten aus dem Überwachungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="cf3d7-116">Retrieve Teams data from the audit log</span></span>


1.  <span data-ttu-id="cf3d7-117">Um Überwachungsprotokolle abzurufen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="cf3d7-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="cf3d7-118">Wählen Sie unter **Suchen**die Option **Überwachungsprotokoll Suche**aus.</span><span class="sxs-lookup"><span data-stu-id="cf3d7-118">Under **Search**, select **Audit log search**.</span></span>



2. <span data-ttu-id="cf3d7-119">Verwenden Sie die Option **Suchen**, um nach den Aktivitäten, Datumswerten und Benutzern zu filtern, die Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="cf3d7-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3. <span data-ttu-id="cf3d7-120">Exportieren Sie die Ergebnisse zur weiteren Analyse nach Excel.</span><span class="sxs-lookup"><span data-stu-id="cf3d7-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf3d7-121">Überwachungsdaten sind nur dann im Überwachungsprotokoll sichtbar, wenn die Überwachung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cf3d7-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="cf3d7-122">Video: TechTip: Verwenden der Überwachungsprotokollsuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf3d7-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="cf3d7-123">Ansuman Acharya, Programm-Manager für Microsoft Teams, zeigt, wie Sie im Office 365 Security & Compliance Center eine Überwachungsprotokollsuche für Microsoft Teams durchführen.</span><span class="sxs-lookup"><span data-stu-id="cf3d7-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
