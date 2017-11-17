---
title: Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: "Aktivieren oder Deaktivieren der Funktion für den Gastzugriff in Microsoft Teams"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a996f7cc9154d04870e4dea00da950d340de16e2
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="c8255-103">Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8255-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================





  



<span data-ttu-id="c8255-104">Als Office 365-Administrator müssen Sie die Gastfunktion aktivieren, bevor Sie oder die Benutzer Ihrer Organisation (vor allem Teambesitzer) Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="c8255-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="c8255-105">Die Gasteinstellungen werden in Azure Active Directory festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c8255-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="c8255-106">Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c8255-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="c8255-107">Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung „Wenden Sie sich an Ihren Administrator“ sehen, ist wahrscheinlich die Gastfunktion nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="c8255-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c8255-108">Um die Nutzung der Gastzugriffsfunktion in vollem Umfang zu ermöglichen, müssen Sie die gegenseitige Abhängigkeit bezüglich der Kernautorisierung von Microsoft Teams, Azure Active Directory und Office 365 verstehen.</span><span class="sxs-lookup"><span data-stu-id="c8255-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="c8255-109">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="c8255-109">For more information, see [Control guest access to Microsoft Teams](Teams-dependencies.md).</span></span>

1. <span data-ttu-id="c8255-110">Melden Sie sich mit Ihrem globalen Office 365-Administratorkonto bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.</span><span class="sxs-lookup"><span data-stu-id="c8255-110">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="c8255-111">Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.</span><span class="sxs-lookup"><span data-stu-id="c8255-111">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Melden Sie sich bei Office 365 an, wechseln Sie zum Office 365 Admin Center, wechseln Sie zu „Einstellungen“, und wählen Sie „Dienste &amp; Add-Ins“ aus.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="c8255-113">Wählen Sie **Microsoft Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="c8255-113">Select **Microsoft Teams**.</span></span>
    
     ![Screenshot, der die im Office 365 Admin Center ausgewählte Option für das Microsoft Teams-Add-In abbildet.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="c8255-115">Wählen Sie unter **Zu konfigurierenden Benutzer-/Lizenztyp auswählen** die Option **Gast** aus.</span><span class="sxs-lookup"><span data-stu-id="c8255-115">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![Screenshot des Microsoft Teams-Add-Ins, der die ausgewählte Gastlizenz und die aktivierte Microsoft Teams-Option abbildet.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="c8255-117">Klicken oder tippen Sie auf die Umschaltfläche neben **Microsoft Teams für alle Benutzer dieses Typs aktivieren oder deaktivieren** auf **Ein**, um Teams und Gastzugriff für Ihre Organisation zu aktivieren, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c8255-117">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  

