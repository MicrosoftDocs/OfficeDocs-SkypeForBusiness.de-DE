---
title: Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll im Microsoft Teams Admin Center
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre Richtlinien Zuordnungs Aktivitäten im Aktivitätsprotokoll im Microsoft Teams Admin Center anzeigen.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a363d934ffd66d04bc3eb778380613e33e460a9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350079"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="6c1e1-103">Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll</span><span class="sxs-lookup"><span data-stu-id="6c1e1-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="6c1e1-104">Wenn Sie Benutzern im Microsoft Teams Admin Center Richtlinien zuweisen, können Sie den Status dieser Richtlinienzuweisungen im Aktivitätsprotokoll anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="6c1e1-105">Das Aktivitätsprotokoll zeigt Richtlinienzuweisungen für Stapel von mehr als 20 Benutzern über das Microsoft Teams Admin Center der letzten 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="6c1e1-106">Beachten Sie, dass im Aktivitätsprotokoll keine Richtlinienpaket Zuweisungen, Richtlinienzuweisungen für Batches mit weniger als 20 Benutzern über das Microsoft Teams Admin Center oder Richtlinienzuweisungen über PowerShell angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Screenshot der Seite "Aktivitätsprotokoll"](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="6c1e1-108">Anzeigen Ihrer Richtlinien Zuordnungs Aktivitäten im Aktivitätsprotokoll</span><span class="sxs-lookup"><span data-stu-id="6c1e1-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="6c1e1-109">So zeigen Sie Ihre Richtlinienzuweisungen im Aktivitätsprotokoll an:</span><span class="sxs-lookup"><span data-stu-id="6c1e1-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="6c1e1-110">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Dashboard**, und wählen Sie dann unter **Aktivitätsprotokoll**die Option **Details anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="6c1e1-111">Sie können alle Richtlinienzuweisungen anzeigen oder die Liste nach Status filtern, um nur Zuordnungen anzuzeigen, die **nicht gestartet**, **in Bearbeitung**oder **abgeschlossen**sind.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="6c1e1-112">Für jede Aufgabe werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6c1e1-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="6c1e1-113">**Name**: der Name der Richtlinienzuordnung.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="6c1e1-114">Klicken Sie auf den Link, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-114">Click the link to view more details.</span></span> <span data-ttu-id="6c1e1-115">Dies umfasst die Anzahl der Benutzer, denen die Richtlinie zugewiesen wurde, und die Anzahl der Aufgaben, die abgeschlossen, in Bearbeitung und nicht gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="6c1e1-116">Außerdem sehen Sie die Liste der Benutzer im Batch sowie den Status und das Ergebnis für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="6c1e1-117">Nachfolgend ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6c1e1-117">Here's an example:</span></span>

        ![Screenshot des](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="6c1e1-119">Über **mittelt**: Datum und Uhrzeit, an dem die Richtlinienzuweisung übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="6c1e1-120">**Fertigstellungszeit**: Datum und Uhrzeit, zu der die Richtlinien Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="6c1e1-121">**Auswirkung auf**: Anzahl der Benutzer im Batch.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="6c1e1-122">**Gesamtstatus**: Status der Richtlinienzuordnung.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="6c1e1-123">Sie können auch auf der Seite " **Benutzer** " auf das Aktivitätsprotokoll gelangen.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="6c1e1-124">Nachdem Sie auf über **nehmen** klicken, um eine Massen Richtlinienzuweisung zu übermitteln, wird oben auf der Seite ein Banner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c1e1-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="6c1e1-125">Klicken Sie im Banner auf den Link **Aktivitätsprotokoll** .</span><span class="sxs-lookup"><span data-stu-id="6c1e1-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6c1e1-126">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6c1e1-126">Related topics</span></span>

- [<span data-ttu-id="6c1e1-127">Zuweisen von Richtlinien zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="6c1e1-127">Assign policies to users</span></span>](assign-policies.md)
