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
description: Informationen Sie zum Verwalten von Einstellungen für Microsoft-Teams, Benutzer in einer Sammeloperation in der Microsoft-Teams-Verwaltungskonsole.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245070"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="e7ece-103">Bearbeiten von benutzereinstellungen in einer Sammeloperation Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="e7ece-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="e7ece-104">Als Administrator können Sie benutzereinstellungen in der Verwaltungskonsole von Microsoft-Teams, Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="e7ece-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e7ece-105">Auf der Seite **Benutzer** können Sie Informationen wie Konto- und lizenzierungsdetails anzeigen und Bearbeiten von Richtlinien und andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e7ece-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="e7ece-106">Sie können Einstellungen für Benutzer einzeln oder für mehrere Benutzer gleichzeitig bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7ece-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="e7ece-107">Bearbeiten von benutzereinstellungen in einer Sammeloperation</span><span class="sxs-lookup"><span data-stu-id="e7ece-107">Edit user settings in bulk</span></span>

<span data-ttu-id="e7ece-108">Verwenden Sie das Microsoft-Teams, Administrationscenter, um Einstellungen für mehrere Benutzer gleichzeitig zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7ece-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="e7ece-109">Es wird empfohlen, Einstellungen für 20 Benutzer gleichzeitig bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7ece-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="e7ece-110">Verwenden von PowerShell, um Einstellungen für eine große Anzahl von Benutzern zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7ece-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="e7ece-111">Weitere Informationen finden Sie unter [Übersicht über die PowerShell Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e7ece-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="e7ece-112">Wählen Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="e7ece-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="e7ece-113">Suchen Sie nach dem Benutzer, den, die Sie verwenden möchten, bearbeiten oder Filtern der Ansicht, um die Benutzer anzuzeigen, dass Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e7ece-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="e7ece-114">In der **& #x 2713;** Spalte (Häkchen), wählen Sie Benutzer, indem Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="e7ece-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="e7ece-115">Wählen Sie Benutzer zu einem Zeitpunkt aus.</span><span class="sxs-lookup"><span data-stu-id="e7ece-115">Select users one at a time.</span></span> <span data-ttu-id="e7ece-116">Ein **& #x 2713;** wird neben jedem Benutzer angezeigt, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="e7ece-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="e7ece-117">Wenn Sie mehr als 20 Benutzer auswählen, Sie werden nicht blockiert werden, aber Bedenken Sie, dass mehr Benutzer Sie auswählen, der Vorgang wird für die Durchführung länger dauern.</span><span class="sxs-lookup"><span data-stu-id="e7ece-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the operation will take longer to complete.</span></span>

        ![Screenshot der Seite Benutzer mit der Auswahl des Benutzers](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="e7ece-119">Klicken Sie auf die & #x 2713. (Häkchen) am oberen Rand der Tabelle, wählen Sie alle Benutzer (bis zu maximal 20 Benutzer), und klicken Sie dann im Dialogfeld **Auswahl beschränken** auf **Weiter wählen Sie alle** , um die Auswahl abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e7ece-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="e7ece-120">![Screenshot der Seite Benutzer, die den Grenzwert für die Auswahl anzeigen](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="e7ece-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="e7ece-121">Ein **& #x 2713;** wird neben den ausgewählten Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7ece-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Screenshot der Seite Benutzer, 20 ausgewählten Benutzer anzeigen](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="e7ece-123">Klicken Sie auf **Einstellungen bearbeiten**, stellen Sie die gewünschten Änderungen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e7ece-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Screenshot der Bereich Einstellungen bearbeiten](media/bulk-edit-user-settings-edit-settings.png)
