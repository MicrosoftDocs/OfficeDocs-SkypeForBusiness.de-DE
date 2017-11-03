---
title: Einrichten des Gastzugriffs auf Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Aktivieren Sie die Funktion für den Gastzugriff in Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a><span data-ttu-id="96a64-103">Einrichten des Gastzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96a64-103">Set up guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="96a64-104">Microsoft Teams basiert auf Office 365-Gruppen und nutzt außerdem SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="96a64-104">Microsoft Teams is built upon Office 365 Groups, and it also relies on SharePoint Online.</span></span> <span data-ttu-id="96a64-105">Daher müssen bestimmte Einstellungen in Office 365-Gruppen und in SharePoint Online aktiviert werden, um die Funktion für den Gastzugriff in Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="96a64-105">That’s why specific settings must be enabled in Office 365 Groups and SharePoint Online in addition to turning on the guest access feature in Teams.</span></span>


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a><span data-ttu-id="96a64-106">Zulassen, dass Gäste hinzugefügt werden in Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="96a64-106">Allow the addition of guests in Office 365 Groups</span></span>
<span data-ttu-id="96a64-107"><a name="bkmk_ControlAddingGuestUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="96a64-107"></span></span>


1. <span data-ttu-id="96a64-108">Melden Sie sich mit Ihrem globalen Office 365-Administrator bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.</span><span class="sxs-lookup"><span data-stu-id="96a64-108">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="96a64-109">Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.</span><span class="sxs-lookup"><span data-stu-id="96a64-109">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="96a64-110">Wählen Sie **Office 365-Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="96a64-110">Select **Office 365 Groups**.</span></span>
    
     ![Office 365-Gruppen](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="96a64-112">Je nachdem, ob Sie den Zugriff für Team- oder Gruppenbesitzer außerhalb Ihres Unternehmens auf Office 365-Gruppen gewähren möchten, legen Sie die Umschaltfläche auf der Seite „Office 365-Gruppen“ auf **Ein** oder **Aus** fest.</span><span class="sxs-lookup"><span data-stu-id="96a64-112">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="96a64-113">Klicken oder tippen Sie neben **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen** auf die Umschaltfläche, um sie in **Ein** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="96a64-113">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span>


![Dieser Screenshot bildet den Office 365 Groups-Bereich mit den aktivierten Optionen für den Zugriff von Gruppenmitgliedern außerhalb der Organisation auf Gruppeninhalte sowie für das Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer ab.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a><span data-ttu-id="96a64-115">Aktivieren der Freigabe in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="96a64-115">Enable sharing in SharePoint Online</span></span>

<span data-ttu-id="96a64-116">Mit der Freigabeoption in SharePoint Online können Gäste zu Ihrer Organisation hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="96a64-116">The Sharing option allows guests to be added to your organization.</span></span> <span data-ttu-id="96a64-117">Standardmäßig ist die Freigabeoption aktiviert.</span><span class="sxs-lookup"><span data-stu-id="96a64-117">By default, the Sharing option is enabled.</span></span> <span data-ttu-id="96a64-118">Weitere Informationen zur Deaktivierung der Freigabeoption finden Sie unter [Aktivieren oder Deaktivieren der Freigabeoption](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span><span class="sxs-lookup"><span data-stu-id="96a64-118">For information about how to turn off the Sharing option, see [Turn on or off the Sharing option](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span></span>
  
   <span data-ttu-id="96a64-119">Administratoren können Gastkonten in Azure Active Directory unabhängig von den Einstellungen für die externe Freigabe erstellen.</span><span class="sxs-lookup"><span data-stu-id="96a64-119">Admins can create guest accounts in Azure Active Directory, independent from external sharing settings.</span></span> <span data-ttu-id="96a64-120">Wenn die externe Freigabe deaktiviert ist, können Gastkonten nur von einem Administrator erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="96a64-120">If external sharing is off, only an admin can create guest accounts.</span></span> 
    

> [!IMPORTANT]
> <span data-ttu-id="96a64-121">Wenn Sie die Freigabeoption deaktivieren, ist kein Gastzugriff verfügbar.</span><span class="sxs-lookup"><span data-stu-id="96a64-121">If you turn off the Sharing option, guest access isn't available.</span></span> 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="96a64-122">Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96a64-122">Turn on or off guest access for Microsoft Teams</span></span>
<span data-ttu-id="96a64-123"><a name="bkmk_TurnonOrTurnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="96a64-123"></span></span>

<span data-ttu-id="96a64-124">Als Office 365-Administrator müssen Sie die Gastfunktion aktivieren, bevor Sie oder die Benutzer Ihrer Organisation (vor allem Teambesitzer) Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="96a64-124">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="96a64-125">Die Gasteinstellungen werden in Azure Active Directory festgelegt.</span><span class="sxs-lookup"><span data-stu-id="96a64-125">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="96a64-126">Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="96a64-126">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="96a64-127">Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung „Wenden Sie sich an Ihren Administrator“ sehen, ist wahrscheinlich die Gastfunktion nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="96a64-127">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>



1. <span data-ttu-id="96a64-128">Melden Sie sich mit Ihrem globalen Office 365-Administratorkonto bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.</span><span class="sxs-lookup"><span data-stu-id="96a64-128">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="96a64-129">Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.</span><span class="sxs-lookup"><span data-stu-id="96a64-129">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Melden Sie sich bei Office 365 an, wechseln Sie zum Office 365 Admin Center, wechseln Sie zu „Einstellungen“, und wählen Sie „Dienste &amp; Add-Ins“ aus.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="96a64-131">Wählen Sie **Microsoft Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="96a64-131">Select **Microsoft Teams**.</span></span>
    
     ![Screenshot, der die im Office 365 Admin Center ausgewählte Option für das Microsoft Teams-Add-In abbildet.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="96a64-133">Wählen Sie unter **Zu konfigurierenden Benutzer-/Lizenztyp auswählen** die Option **Gast** aus.</span><span class="sxs-lookup"><span data-stu-id="96a64-133">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![Screenshot des Microsoft Teams-Add-Ins, der die ausgewählte Gastlizenz und die aktivierte Microsoft Teams-Option abbildet.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="96a64-135">Klicken oder tippen Sie auf die Umschaltfläche neben **Microsoft Teams für alle Benutzer dieses Typs aktivieren oder deaktivieren** auf **Ein**, um Teams und Gastzugriff für Ihre Organisation zu aktivieren, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="96a64-135">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  

