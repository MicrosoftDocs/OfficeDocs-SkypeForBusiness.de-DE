---
title: "Wechseln zu Microsoft als Audiokonferenzanbieter für einen Benutzer"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Change your Skype for Business users from third-party audio conferencing providers (ACP) to a Microsoft dial-in conferencing provider. '
ms.openlocfilehash: 8df53a27f3dc0934411284c373206fc4b6dcf41a
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="94834-103">Wechseln zu Microsoft als Audiokonferenzanbieter für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="94834-103">Moving a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="94834-104">Um Audiokonferenzen in Office 365 mit Skype für Unternehmen und die Microsoft-Teams verwenden, müssen Benutzer in Ihrer Organisation muss eine **Audiokonferenz** -Lizenz für sie und ihre Audiokonferenzanbieter zugewiesen an Microsoft festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="94834-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an **Audio Conferencing** license assigned to them and their audio conferencing provider must be set to Microsoft.</span></span> <span data-ttu-id="94834-105">Um weitere Informationen zur Lizenzierung und Kosten finden Sie unter [Testen oder erwerben Audiokonferenzen in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="94834-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="94834-106">So verschieben Sie einen Benutzer für Audiokonferenzen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="94834-106">To move a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="94834-107">Wenn eine **Audiokonferenz** -Lizenz zu einem Benutzer, die einen audio Conferencing Provider nicht haben zugewiesen ist, vom Anbieter des Benutzers automatisch an Microsoft festgelegt, und Sie müssen keine weiteren Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="94834-107">If an **Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to Microsoft and you don't have to do anything else.</span></span> <span data-ttu-id="94834-108">Wenn der Benutzer bereits einen Anbieter von Audiokonferenzen hatten, müssen Sie Anbieter des Benutzers an Microsoft ändern, nach einer **Audiokonferenz** -Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="94834-108">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an **Audio Conferencing** license.</span></span>
  
<span data-ttu-id="94834-109">Um Microsoft festzulegen, wie der Anbieter von Audiokonferenzen für einen Benutzer mit einer **Audiokonferenz** -Lizenz zugewiesen, aber einen anderen Anbieter von Audiokonferenzen verwendet, folgendermaßen Sie vor:</span><span class="sxs-lookup"><span data-stu-id="94834-109">To set Microsoft as the audio conferencing provider for a user that has an **Audio Conferencing** license assigned but is using another audio conferencing provider, do this:</span></span>
  
1. <span data-ttu-id="94834-110">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="94834-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="94834-111">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="94834-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="94834-112">Navigieren Sie in der **Skype für Business Administrationscenter**zu **Audiokonferenzen**.</span><span class="sxs-lookup"><span data-stu-id="94834-112">In the **Skype for Business admin center**, go to **Audio conferencing**.</span></span>
    
4. <span data-ttu-id="94834-113">Wenn Sie ein Banner finden Sie unter aufgefordert werden, dass Benutzer, die eine **Audiokonferenz** haben Lizenz zugewiesen jedoch nicht, dass Microsoft legen Sie als Anbieter von Audiokonferenzen noch auf **Klicken Sie hier, um sie zu verschieben**.</span><span class="sxs-lookup"><span data-stu-id="94834-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="94834-114">Wenn das Banner nicht angezeigt wird, in der **Skype für Business Administrationscenter** klicken Sie auf **Benutzer**, und wählen Sie dann den Filter für **Benutzer bereit, in der Audiokonferenz verschoben werden soll** .</span><span class="sxs-lookup"><span data-stu-id="94834-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
5. <span data-ttu-id="94834-115">Wählen Sie die Benutzer, den, die Sie verschieben möchten, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="94834-115">Select the users you want to move, and then in the Action pane, click **Edit**.</span></span>
    
6. <span data-ttu-id="94834-116">Wählen Sie in der Liste **Name des Anbieters** **Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="94834-116">Select **Microsoft** in the **Provider name** list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="94834-117">Wenn der Anbieter von Audiokonferenzen eines Benutzers in Microsoft geändert wird, ändert sich der Audiokonferenzinformationen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="94834-117">When the audio conferencing provider of a user is changed to Microsoft, the audio conferencing information of the user will change.</span></span> <span data-ttu-id="94834-118">Wenn Sie diese Informationen müssen, notieren Sie es irgendwo vor dem Ändern des Anbieters von einem Benutzer.</span><span class="sxs-lookup"><span data-stu-id="94834-118">If you need to keep this information, please record it somewhere before changing the provider of any of the users.</span></span> 
  
7. <span data-ttu-id="94834-119">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="94834-119">Click **Save**.</span></span>
    
## <a name="what-else-should-i-know"></a><span data-ttu-id="94834-120">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="94834-120">What else should I know?</span></span>

- <span data-ttu-id="94834-121">Wenn Sie den Benutzer in der Liste auswählen, können Sie die Standardinformationen für die Audiokonferenz des Benutzers anzeigen, aber nicht möglich, der Audiokonferenzen PIN finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="94834-121">If you select the user in the list, you can view the default audio conferencing information of the user but you won't be able to see the audio conferencing PIN.</span></span> <span data-ttu-id="94834-122">Sie können die Audiokonferenz PIN eines Benutzers zurücksetzen, indem Sie auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="94834-122">You can reset the audio conferencing PIN of a user by clicking **Reset**.</span></span>
    
- <span data-ttu-id="94834-123">Wenn Sie Audiokonferenzen Einstellungen für einen Benutzer ändern möchten, können Sie wählen Sie den Benutzer aus der Liste und dann klicken Sie auf **Bearbeiten** und auf nehmen Sie auf der Seite **Eigenschaften** die Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="94834-123">If you want to change audio conferencing settings for a user, you can select the user from the list and then click **Edit** and make your changes on the **Properties** page.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="94834-124">See Also</span><span class="sxs-lookup"><span data-stu-id="94834-124">Related topics</span></span>

[<span data-ttu-id="94834-125">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94834-125">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

