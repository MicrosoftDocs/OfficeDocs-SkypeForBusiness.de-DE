---
title: Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Erfahren Sie, wie Sie Ihren Skype for Business-Benutzern eine berufliche Telefonnummer zuweisen oder sie ändern oder entfernen können, damit Unternehmen und Kunden von außerhalb anrufen können.
ms.openlocfilehash: 8c80bf9da5471f1a7293a01ed9e2d56f6e1aa15b
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780939"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="3e5ce-103">Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="3e5ce-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="3e5ce-104">Beim Einrichten von Anrufplänen in Office 365 weisen Sie Ihren Benutzern Telefonnummern zu.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-104">When you set up Calling Plans in Office 365, you assign phone numbers to your users.</span></span> 

<span data-ttu-id="3e5ce-105">Im Microsoft-Teams-Client wird die Telefonnummer, die Sie zuweisen, beim Klicken auf **Anrufe** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Telefonnummer des Benutzers, der in Microsoft Teams angezeigt wird.](../images/teams-phone-number.png)

<span data-ttu-id="3e5ce-107">Im Skype for Business-Client wird die Telefonnummer, die Sie zuweisen, im Feld **Telefon (geschäftlich)** aufgelistet und kann nicht von einem Benutzer geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-107">The phone number you assign will be listed in the **Work Phone** box in their Skype for Business client and can't be changed by a user.</span></span>
  
![Die geschäftliche Rufnummer is ausgegraut.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="3e5ce-109">Wenn ein Benutzer seine oder ihre [Telefonnummer für Skype for Business ändern](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) möchte und die Telefonnummer in der Skype for Business-App nicht geändert werden kann oder ausgegraut ist, wurde die Telefonnummer von einem Administrator festgelegt und kann nicht vom Benutzer geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-109">If a user wants to [Change my phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) \*\* and the phone number in the Skype for Business app can't be changed or is grayed out\*\*, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="3e5ce-110">Wenn Sie für Benutzer das Tätigen und Annehmen von Telefonanrufen einrichten, müssen Sie zuerst im Skype for Business Admin Center eine Telefonnummer zuweisen. Sie können die Nummer jedoch bei Bedarf ändern oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin centerand assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="3e5ce-111">Wenn Sie wissen möchten, wie Sie Anrufpläne in Office 365 erhalten und was diese kosten, lesen Sie [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="3e5ce-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3e5ce-p101">Eine Möglichkeit, zu überprüfen, ob einem Benutzer eine Lizenz zugewiesen ist: Wechseln Sie zu **Skype for Business Admin Center** > **VoIP** > **VoIP-Benutzer**, und wählen Sie den Benutzer aus. Wenn eine Lizenz zugewiesen ist, wird sie unter **Zugewiesene Lizenz** angezeigt. Sie können auch das Office 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="3e5ce-115">Zuweisen einer Telefonnummer zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="3e5ce-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="3e5ce-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="3e5ce-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="3e5ce-117">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="3e5ce-118">Navigieren Sie zu **Office 365 Admin Center** > **Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-118">Go to **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="3e5ce-119">Klicken Sie in der linken Navigationsleiste auf **VoIP** > **VoIP-Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
 <span data-ttu-id="3e5ce-120">Damit im linken Navigationsbereich des Skype for Business Admin Centers die Option **VoiP** angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz**, eine Add-On-Lizenz für das **Telefonsystem** oder eine Add-On-Lizenz für **Audiokonferenzen** erwerben.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-120">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="3e5ce-121">Wählen Sie auf der Seite **VoIP-Benutzer** die Benutzer aus, denen Sie eine Telefonnummer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="3e5ce-122">Klicken Sie im Bereich „Aktion" auf die Option zum **Zuweisen von Nummern**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="3e5ce-123">Wählen Sie auf der Seite **Nummer zuweisen** in der Dropdown-Liste **Zuzuweisende Nummer auswählen** die Telefonnummer für den Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-123">On the **Assign number** page in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3e5ce-p102">Wenn keine Telefonnummern aufgeführt sind, müssen Sie zuerst [Reservieren von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md). Alternativ können Sie, wenn Sie die Seite **Skype for Business Admin Center** > **VoIP** > **Telefonnummern** verwenden, auf **Hinzufügen** und dann auf **Neue Nutzernummern** klicken.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-p102">If you don't see any phone numbers listed, you need to [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md) first. Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="3e5ce-126">Um die zugeordnete Notfalladresse zuzuweisen oder zu ändern, wählen Sie unter **Auswählen des gültigen Notfallorts** den Standort aus der Liste aus. Wenn viele Standorte definiert sind, können Sie alternativ den Namen der Stadt in das Suchfeld eingeben und auf **Suchen** klicken.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="3e5ce-127">Nachdem Sie die Telefonnummer und den Notfallstandort ausgewählt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3e5ce-p103">Aufgrund der Latenz zwischen Office 365 und Skype for Business Online kann die Aktivierung von Benutzern bis zu 24 Stunden dauern. Wenn die Telefonnummer nach 24 Stunden noch nicht richtig zugewiesen ist, [Kontaktieren des Office 365 Business-Supports - Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Wir helfen gern!</span><span class="sxs-lookup"><span data-stu-id="3e5ce-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="3e5ce-131">So ändern Sie die Telefonnummer eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="3e5ce-131">To change a phone number for a user</span></span>
 
<span data-ttu-id="3e5ce-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="3e5ce-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="3e5ce-133">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="3e5ce-134">Navigieren Sie zu **Office 365 Admin Center** > **Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-134">Go to **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="3e5ce-135">Klicken Sie in der linken Navigationsleiste auf **VoIP** > **VoIP-Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="3e5ce-136">Wählen Sie auf der Seite **VoIP-Benutzer** die Benutzer aus, deren Telefonnummer Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="3e5ce-137">Klicken Sie im Aktionsbereich unter **Zugewiesene Nummer** auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-137">In the Action pane, under **Assigned number**, click **Change**.</span></span> 
    
6. <span data-ttu-id="3e5ce-138">Klicken Sie auf der Seite **Nummer zuweisen** auf **Nummer ändern**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="3e5ce-139">Verwenden Sie auf der Seite **Nummer zuweisen** unter **Zuzuweisende Nummer auswählen** die Dropdown-Liste, um die neue Telefonnummer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="3e5ce-140">Um die zugeordnete Notfalladresse zu ändern, klicken Sie auf **Standort ändern**. Wählen Sie dann unter **Notfalladresse ändern in** den Standort aus der Liste aus. Wenn viele Standorte definiert sind, geben Sie alternativ den Namen der Stadt in das Suchfeld ein, und klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="3e5ce-141">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="3e5ce-142">So entfernen Sie die Telefonnummer eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="3e5ce-142">To remove a phone number from a user</span></span>
 
<span data-ttu-id="3e5ce-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="3e5ce-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="3e5ce-144">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="3e5ce-145">Navigieren Sie zu **Office 365 Admin Center** > **Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-145">Go to **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="3e5ce-146">Klicken Sie in der linken Navigationsleiste auf **VoIP** > **VoIP-Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="3e5ce-147">Wählen Sie auf der Seite **VoIP-Benutzer** die Benutzer aus, deren Telefonnummer Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="3e5ce-148">Klicken Sie im Aktionsbereich unter **Zugewiesene Nummer** auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-148">In the Action pane, under **Assigned number**, click **Remove**.</span></span> 
    
6. <span data-ttu-id="3e5ce-149">Klicken Sie auf der Seite **Remove selected assigned number?** (Ausgewählte zugewiesene Nummer entfernen?) auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3e5ce-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="3e5ce-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3e5ce-150">Related topics</span></span>
[<span data-ttu-id="3e5ce-151">Was ist Adressvalidierung?</span><span class="sxs-lookup"><span data-stu-id="3e5ce-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="3e5ce-152">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="3e5ce-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="3e5ce-153">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="3e5ce-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="3e5ce-154">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="3e5ce-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 