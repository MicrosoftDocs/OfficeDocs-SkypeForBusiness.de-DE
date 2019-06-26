---
title: Bearbeiten von Microsoft Teams-Benutzereinstellungen in Sammeleinheiten
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Microsoft Teams-Benutzereinstellungen im Microsoft Teams Admin Center massenhaft verwalten.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a80b39513fe86e0c49cd88988cb3f245129b2d0
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221356"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="e32f3-103">Bearbeiten von Microsoft Teams-Benutzereinstellungen in Massen</span><span class="sxs-lookup"><span data-stu-id="e32f3-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="e32f3-104">Als Administrator verwalten Sie die Benutzereinstellungen für Teams im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="e32f3-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e32f3-105">Auf der Seite " **Benutzer** " können Sie Informationen wie Konto-und lizenzierungsdetails anzeigen sowie Richtlinien und andere Einstellungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e32f3-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="e32f3-106">Sie können die Einstellungen für Benutzer einzeln oder für mehrere Benutzer gleichzeitig bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e32f3-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="e32f3-107">Bearbeiten von Benutzereinstellungen in Massen</span><span class="sxs-lookup"><span data-stu-id="e32f3-107">Edit user settings in bulk</span></span>

<span data-ttu-id="e32f3-108">Verwenden Sie das Microsoft Teams Admin Center, um die Einstellungen für mehrere Benutzer gleichzeitig zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e32f3-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="e32f3-109">Wir empfehlen, Einstellungen für 20 Benutzer gleichzeitig zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e32f3-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="e32f3-110">Verwenden Sie PowerShell, um die Einstellungen für eine große Anzahl von Benutzern zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e32f3-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="e32f3-111">Weitere Informationen finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e32f3-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="e32f3-112">Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center die Option **Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="e32f3-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="e32f3-113">Suchen Sie nach den Benutzern, die Sie bearbeiten oder filtern möchten, um die Benutzer anzuzeigen, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e32f3-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="e32f3-114">Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Option Benutzer aus, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e32f3-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="e32f3-115">Wählen Sie Benutzer einzeln aus.</span><span class="sxs-lookup"><span data-stu-id="e32f3-115">Select users one at a time.</span></span> <span data-ttu-id="e32f3-116">Neben jedem ausgewählten Benutzer wird ein **&#x2713;** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e32f3-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="e32f3-117">Wenn Sie mehr als 20 Benutzer auswählen, werden Sie nicht blockiert, aber denken Sie daran, dass je mehr Benutzer Sie auswählen, desto länger dauert die Ausführung des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="e32f3-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the longer the operation will take to complete.</span></span>

        ![Screenshot der Seite "Benutzer" mit Benutzerauswahl](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="e32f3-119">Klicken Sie oben in der Tabelle auf das #a0 (Häkchen), um alle Benutzer (bis maximal 20 Benutzer) auszuwählen, und klicken Sie dann im Dialogfeld **Auswahlgrenze** auf **Alle auswählen** , um die Auswahl abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e32f3-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="e32f3-120">![Screenshot der Seite "Benutzer" mit der Auswahlgrenze](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="e32f3-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="e32f3-121">Neben den ausgewählten Benutzern wird ein **&#x2713;** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e32f3-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Screenshot der Seite "Benutzer" mit 20 ausgewählten Benutzern](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="e32f3-123">Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e32f3-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Screenshot des Bereichs "Einstellungen bearbeiten"](media/bulk-edit-user-settings-edit-settings.png)
