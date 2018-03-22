---
title: Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Aktivieren oder Deaktivieren der Funktion für den Gastzugriff in Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddf9f3b2597300ca872a5ab4135538e9cc6cc5ed
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="8eef9-103">Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8eef9-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]



  



<span data-ttu-id="8eef9-104">Als Office 365-Administrator müssen Sie die Gastfunktion aktivieren, bevor Sie oder die Benutzer Ihrer Organisation (vor allem Teambesitzer) Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="8eef9-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="8eef9-105">Die Gasteinstellungen werden in Azure Active Directory festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8eef9-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="8eef9-106">Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="8eef9-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="8eef9-107">Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung „Wenden Sie sich an Ihren Administrator“ sehen, ist wahrscheinlich die Gastfunktion nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="8eef9-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8eef9-108">Um die Nutzung der Gastzugriffsfunktion in vollem Umfang zu ermöglichen, müssen Sie die gegenseitige Abhängigkeit bezüglich der Kernautorisierung von Microsoft Teams, Azure Active Directory und Office 365 verstehen.</span><span class="sxs-lookup"><span data-stu-id="8eef9-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="8eef9-109">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="8eef9-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

1. <span data-ttu-id="8eef9-110">Melden Sie sich mit dem Konto Globaler Office 365-Administrator bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.</span><span class="sxs-lookup"><span data-stu-id="8eef9-110">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="8eef9-111">Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.</span><span class="sxs-lookup"><span data-stu-id="8eef9-111">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Melden Sie sich bei Office 365 an, wechseln Sie zum Office 365 Admin Center, wechseln Sie zu „Einstellungen“, und wählen Sie „Dienste &amp; Add-Ins“ aus.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="8eef9-113">Wählen Sie **Microsoft Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="8eef9-113">Select **Microsoft Teams**.</span></span>
    
     ![Screenshot, der die im Office 365 Admin Center ausgewählte Option für das Microsoft Teams-Add-In abbildet.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="8eef9-115">Wählen Sie unter **Zu konfigurierenden Benutzer-/Lizenztyp auswählen** die Option **Gast** aus.</span><span class="sxs-lookup"><span data-stu-id="8eef9-115">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![Screenshot des Microsoft Teams-Add-Ins, der die ausgewählte Gastlizenz und die aktivierte Microsoft Teams-Option abbildet.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="8eef9-117">Klicken oder tippen Sie auf die Umschaltfläche neben **Microsoft Teams für alle Benutzer dieses Typs aktivieren oder deaktivieren** auf **Ein**, um Teams und Gastzugriff für Ihre Organisation zu aktivieren, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="8eef9-117">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
 <span data-ttu-id="8eef9-118">In den folgenden Videos erfahren Sie mehr über den Gastzugriff:</span><span class="sxs-lookup"><span data-stu-id="8eef9-118">Watch the following videos for more details about guest access:</span></span>  

|  |  |
|---------|---------|
| <span data-ttu-id="8eef9-119">Aktivieren des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8eef9-119">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/g21Hcqdl5tI" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="8eef9-120">Hinzufügen von Gästen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8eef9-120">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 