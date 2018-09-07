---
title: Ändern des Notfallortes für einen Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: 'Erfahren Sie, wie Sie den Notfallort für Ihre Benutzer ändern können. Mit einer unbegrenzten Anzahl von Standorten können Sie Notfallorte ändern, wenn Mitarbeiter Stockwerke oder Gebäude wechseln. '
ms.openlocfilehash: e3805daa8248da44de84330ea5de694126e9e32c
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863273"
---
# <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="c203a-104">Ändern des Notfallortes für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="c203a-104">Change the emergency location for a user</span></span>

<span data-ttu-id="c203a-105">Jede aktive Telefonnummer muss eine Notfalladresse haben (wird zugeordnet, wenn Sie eine Telefonnummer in Office 365 erhalten oder wenn Sie eine Telefonnummer übertragen), wenn die Telefonnummer dem Benutzer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c203a-105">Each active phone number must have an emergency address (associated when you get a phone number in Office 365 or when you transfer a phone number) when the phone number is assigned to the user.</span></span> <span data-ttu-id="c203a-106">Wenn Sie die Nummer mit einer Notfalladresse verknüpfen, können Sie auch einen Notfallort hinzufügen, um einen genaueren Standort innerhalb eines realen Standorts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c203a-106">When you associate the number with an emergency address, you can also add an emergency location to provide a more exact location within a physical location.</span></span> <span data-ttu-id="c203a-107">Ein Notfallort kann ein Stockwerk, ein Gebäudeflügel oder die Nummer eines Büros sein, in dem sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="c203a-107">An emergency location can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="c203a-108">Sie können eine unbegrenzte Anzahl von Standorten für eine bestimmte Notfalladresse haben, und Sie können den Notfallort ändern, wenn der Benutzer in ein anderes Büro oder Gebäude umzieht - zum Beispiel, wenn der Benutzer von Stockwerk 34 in Stockwerk 35 wechselt.</span><span class="sxs-lookup"><span data-stu-id="c203a-108">You can have an unlimited number of locations for a given emergency address, and you can change the emergency location if the user moves to a different office or building—for example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="c203a-109">Wenn Sie wissen möchten, wie Sie Anrufpläne in Office 365 erhalten und was diese kosten, lesen Sie [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c203a-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="c203a-110">Ändern des Notfallortes für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="c203a-110">Change the emergency location for a user</span></span>

1. <span data-ttu-id="c203a-111">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="c203a-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c203a-112">Gehen Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c203a-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c203a-113">Wechseln Sie im linken Navigationsbereich zu **Sprache** > **Sprachbenutzer**.</span><span class="sxs-lookup"><span data-stu-id="c203a-113">In the Skype for Business admin center, in the left navigation, go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c203a-114">Damit im linken Navigationsbereich des Skype for Business Admin Centers die Option **Voice** angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz**, eine Add-On-Lizenz für das **Telefonsystem** oder eine Add-On-Lizenz für **Audiokonferenzen** erwerben.</span><span class="sxs-lookup"><span data-stu-id="c203a-114">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="c203a-115">Suchen Sie auf der Seite **Sprachbenutzer** den Benutzer, für den Sie den Notfallort ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c203a-115">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="c203a-116">Klicken Sie im Bereich „Aktion" unter **Notfallort** auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="c203a-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="c203a-117">Klicken Sie auf der Seite **Nummer zuweisen** auf **Standort ändern**.</span><span class="sxs-lookup"><span data-stu-id="c203a-117">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="c203a-118">Geben Sie unter **Notfalladresse ändern in** den Namen der Stadt im entsprechenden Feld ein und klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="c203a-118">Under **Change emergency address to** put the name of the city in the Find City box and click **Search**.</span></span>
    
8. <span data-ttu-id="c203a-119">Wählen Sie den Notfallort aus der Liste aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c203a-119">Select the right emergency location from the Select associated location (optional) list, then click **Save**.</span></span>
    
    <span data-ttu-id="c203a-120">Wenn Sie einen neuen Notfallort hinzufügen möchten, siehe [Hinzufügen, Ändern oder Entfernen eines Notfallortes für Ihre Organisation](add-change-or-remove-an-emergency-location-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c203a-120">If you want to add a new emergency location, see [Add, change, or remove an emergency location for your organization](add-change-or-remove-an-emergency-location-for-your-organization.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="c203a-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c203a-121">Related topics</span></span>
[<span data-ttu-id="c203a-122">Hinzufügen oder Löschen einer Notfalladresse für Ihr Unternehmen</span><span class="sxs-lookup"><span data-stu-id="c203a-122">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="c203a-123">Hinzufügen, Ändern oder Entfernen eines Notfallorts für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="c203a-123">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="c203a-124">Was ist Adressvalidierung?</span><span class="sxs-lookup"><span data-stu-id="c203a-124">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="c203a-125">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="c203a-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c203a-126">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="c203a-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c203a-127">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c203a-127">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 