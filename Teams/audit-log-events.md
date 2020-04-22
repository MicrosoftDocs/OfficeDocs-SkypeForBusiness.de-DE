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
description: Hier erfahren Sie, wie Sie Microsoft Teams-Daten aus dem Überwachungsprotokoll abrufen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b1235dcd1a33800185eb005f5e309204790c5b1
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778891"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="8a47c-103">Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a47c-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8a47c-104">Mithilfe des Überwachungsprotokolls können Sie bestimmte Aktivitäten in allen Office 365-Diensten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="8a47c-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="8a47c-105">Für Microsoft Teams werden unter anderem die folgenden Aktivitäten überwacht:</span><span class="sxs-lookup"><span data-stu-id="8a47c-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="8a47c-106">Teamerstellung</span><span class="sxs-lookup"><span data-stu-id="8a47c-106">Team creation</span></span>

- <span data-ttu-id="8a47c-107">Löschung von Teams</span><span class="sxs-lookup"><span data-stu-id="8a47c-107">Team deletion</span></span>

- <span data-ttu-id="8a47c-108">Hinzufügen von Kanälen</span><span class="sxs-lookup"><span data-stu-id="8a47c-108">Added channel</span></span>

- <span data-ttu-id="8a47c-109">Ändern von Einstellungen</span><span class="sxs-lookup"><span data-stu-id="8a47c-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="8a47c-110">Überwachungsereignisse von privaten Kanälen werden auch so protokolliert, wie Sie für Teams und Standardkanäle gelten.</span><span class="sxs-lookup"><span data-stu-id="8a47c-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="8a47c-111">Die vollständige Liste der Aktivitäten, die in Microsoft 365 überwacht werden, finden Sie unter [Durchsuchen des Überwachungsprotokolls im Microsoft 365 Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="8a47c-111">To see the complete list of activities that are audited in Microsoft 365, read [Search the audit log in the Microsoft 365 Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="8a47c-112">Aktivieren der Überwachung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a47c-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="8a47c-113">Bevor Sie sich die Überwachungsdaten ansehen können, müssen Sie zuerst die Überwachung im [Security & Compliance Center](https://protection.office.com)aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8a47c-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="8a47c-114">Wenn Sie Hilfe beim Aktivieren der Überwachung benötigen, lesen Sie [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="8a47c-114">For help turning on auditing, read [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a47c-115">Überwachungsdaten sind erst ab dem Zeitpunkt verfügbar, an dem Sie die Überwachung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="8a47c-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="8a47c-116">Abrufen von Microsoft Teams-Daten aus dem Überwachungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="8a47c-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="8a47c-117">Um Überwachungsprotokolle abzurufen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="8a47c-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="8a47c-118">Wählen Sie unter **Suchen**die Option **Überwachungsprotokoll Suche**aus.</span><span class="sxs-lookup"><span data-stu-id="8a47c-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="8a47c-119">Verwenden Sie die Option **Suchen**, um nach den Aktivitäten, Datumswerten und Benutzern zu filtern, die Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="8a47c-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="8a47c-120">Exportieren Sie die Ergebnisse zur weiteren Analyse nach Excel.</span><span class="sxs-lookup"><span data-stu-id="8a47c-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a47c-121">Überwachungsdaten sind nur dann im Überwachungsprotokoll sichtbar, wenn die Überwachung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8a47c-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="8a47c-122">Szenario eines externen Benutzers</span><span class="sxs-lookup"><span data-stu-id="8a47c-122">External user scenario</span></span>

<span data-ttu-id="8a47c-123">Ein Szenario, auf das Sie möglicherweise im geschäftlichen Bereich achten sollten, ist das Hinzufügen externer Benutzer zu ihrer Teamumgebung.</span><span class="sxs-lookup"><span data-stu-id="8a47c-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="8a47c-124">Wenn externe Benutzer aktiviert sind, ist es ratsam, deren Anwesenheit zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="8a47c-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![Screenshot einer Liste von Ereignissen, die durch Massenlöschungen ausgelöst werden](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="8a47c-126">Der Screenshot dieser Richtlinie zum Überwachen externer Benutzer Adds ermöglicht Ihnen, die Richtlinie zu benennen, den Schweregrad entsprechend Ihren geschäftlichen Anforderungen festzulegen, ihn als (in diesem Fall) eine einzelne Aktivität festzulegen und dann die Parameter festzulegen, die speziell nur das Hinzufügen nicht interner Benutzer überwachen und diese Aktivität auf Microsoft Teams beschränken.</span><span class="sxs-lookup"><span data-stu-id="8a47c-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="8a47c-127">Dann können Ergebnisse dieser Richtlinie im Aktivitätsprotokoll angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="8a47c-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![Screenshot einer Liste von Ereignissen, die durch Massenlöschungen ausgelöst werden](media/TeamsExternalUserList.png)

<span data-ttu-id="8a47c-129">Hier können Sie die Übereinstimmungen mit der von Ihnen eingerichteten Richtlinie überprüfen und nach Bedarf Anpassungen vornehmen oder die Ergebnisse exportieren, um Sie anderweitig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a47c-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="8a47c-130">Massen Lösch Szenario</span><span class="sxs-lookup"><span data-stu-id="8a47c-130">Mass delete scenario</span></span>

<span data-ttu-id="8a47c-131">Wie bereits erwähnt, können Sie Lösch Szenarien überwachen.</span><span class="sxs-lookup"><span data-stu-id="8a47c-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="8a47c-132">Es ist möglich, eine Richtlinie zu erstellen, die das Massenlöschen von Teams-Websites überwacht:</span><span class="sxs-lookup"><span data-stu-id="8a47c-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![Screenshot der Seite "Richtlinie erstellen" mit der Einrichtung einer Richtlinie für die Löschung von Massen Teams](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="8a47c-134">Wie der Screenshot zeigt, können Sie für diese Richtlinie viele verschiedene Parameter festlegen, um die Löschungen von Teams zu überwachen, einschließlich Schweregrad, einzelne oder wiederholte Aktionen und Parameter, die dies auf Teams und das Löschen von Websites einschränken.</span><span class="sxs-lookup"><span data-stu-id="8a47c-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="8a47c-135">Dies kann unabhängig von einer Vorlage erfolgen, oder es kann eine Vorlage erstellt werden, um diese Richtlinie abhängig von Ihren organisatorischen Anforderungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8a47c-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="8a47c-136">Nachdem Sie eine Richtlinie eingerichtet haben, die für Ihr Unternehmen funktionieren wird, können Sie die Ergebnisse im Aktivitätsprotokoll überprüfen, wenn Ereignisse ausgelöst werden:</span><span class="sxs-lookup"><span data-stu-id="8a47c-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![Screenshot einer Liste von Ereignissen, die durch Massenlöschungen ausgelöst werden](media/TeamsMassDeleteList.png)

<span data-ttu-id="8a47c-138">Sie können nach unten auf die Richtlinie filtern, die Sie festgelegt haben, um die Ergebnisse dieser Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a47c-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="8a47c-139">Wenn die Ergebnisse, die Sie im Aktivitätsprotokoll erhalten, nicht zufrieden stellend sind (möglicherweise sehen Sie vielleicht viele Ergebnisse oder gar nichts), kann dies Ihnen helfen, die Abfrage zu optimieren, damit Sie für das, was Sie benötigen, relevanter ist.</span><span class="sxs-lookup"><span data-stu-id="8a47c-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="8a47c-140">Video: TechTip: Verwenden der Überwachungsprotokollsuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a47c-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="8a47c-141">Ansuman Acharya, Programm-Manager für Microsoft Teams, zeigt, wie Sie im Office 365 Security & Compliance Center eine Überwachungsprotokollsuche für Microsoft Teams durchführen.</span><span class="sxs-lookup"><span data-stu-id="8a47c-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
