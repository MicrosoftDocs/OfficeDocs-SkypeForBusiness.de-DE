---
title: Ändern der Notfalladresse für einen Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 5412636c-ad0e-48a5-b199-5925156abee4
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
description: 'Siehe die Schritte zur Änderung der Notfalladressen für einen Benutzer der mit dem Telefonfestnetz (PSTN) in den USA und Europa arbeitet. '
ms.openlocfilehash: 62deeae8624ad0eb6b85c25a39c475b0d1d0b198
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779045"
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="e6c8b-103">Ändern der Notfalladresse für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="e6c8b-103">Change the emergency address for a user</span></span>

<span data-ttu-id="e6c8b-104">Wenn Sie in Office 365 Anrufpläne einrichten, müssen Sie jeder Telefonnummer oder jedem Benutzer eine Notfalladresse zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="e6c8b-105">In europäischen Ländern ist die Notfalladresse der Telefonnummer zugeordnet, wenn Sie sie über Office 365 abrufen oder eine Telefonnummer an Office 365 übertragen.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="e6c8b-106">In den USA ist die Notfalladresse der Telefonnummer zugeordnet, sobald Sie einem Benutzer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="e6c8b-107">Die Notfalladresse kann geändert werden, wenn der Benutzer, dem sie zugewiesen wurde, an einen neuen Speicherort verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="e6c8b-108">Weitere Informationen zu Notfalladressen und Notfallstandorten finden Sie unter [Was sind Notfallstandorte, Notfalladressen und Anrufweiterleitung?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="e6c8b-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for details.</span></span>
  
<span data-ttu-id="e6c8b-109">Wenn Sie wissen möchten, wie Sie Anrufpläne in Office 365 erhalten und was diese kosten, lesen Sie [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e6c8b-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="e6c8b-110">Ändern der Notfalladresse für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="e6c8b-110">Change the emergency address for a user</span></span>

<span data-ttu-id="e6c8b-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="e6c8b-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="e6c8b-112">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e6c8b-113">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="e6c8b-114">Wechseln Sie im linken Navigationsbereich auf **Voice** > **VoIP-Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-114">In the Skype for Business admin center, in the left navigation, go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e6c8b-115">Damit im linken Navigationsbereich des Skype for Business Admin Centers die Option **Voice** angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz**, eine Add-On-Lizenz für das **Telefonsystem** oder eine Add-On-Lizenz für **Audiokonferenzen** erwerben.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-115">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="e6c8b-116">Suchen Sie auf der Seite **VoIP-Benutzer** nach dem Benutzer, dessen Notfalladresse Sie ändern möchten und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-116">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="e6c8b-117">Klicken Sie im Bereich „Aktion" unter **Notfallstandort** auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-117">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="e6c8b-118">Klicken Sie auf der Seite **Nummer zuweisen** auf **Standort ändern**.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-118">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="e6c8b-119">Geben Sie unter **Notfalladresse ändern in** den Namen der Stadt im entsprechenden Feld ein und klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-119">Under **Change emergency address to** put the name of the city in the Find City box and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e6c8b-120">Sie können nur eine bereits überprüfte Notfalladresse ändern.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-120">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="e6c8b-121">Wenn Sie eine nicht überprüfte Notfalladresse ändern möchten, löschen Sie die Adresse und erstellen Sie eine neue Notfalladresse.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-121">To change an emergency address that hasn't been validated, delete it and recreate another emergency address.</span></span> 
  
8. <span data-ttu-id="e6c8b-122">Wählen Sie eine neue Notfalladresse aus der Liste aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e6c8b-122">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e6c8b-123">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e6c8b-123">Related topics</span></span>
[<span data-ttu-id="e6c8b-124">Hinzufügen oder Löschen einer Notfalladresse für Ihr Unternehmen</span><span class="sxs-lookup"><span data-stu-id="e6c8b-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="e6c8b-125">Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="e6c8b-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="e6c8b-126">Was ist Adressvalidierung?</span><span class="sxs-lookup"><span data-stu-id="e6c8b-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="e6c8b-127">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="e6c8b-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="e6c8b-128">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="e6c8b-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="e6c8b-129">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="e6c8b-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 