---
title: Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Verwenden Sie PowerShell, um den Gastzugriff auf Teams in Microsoft Teams zuzulassen oder zu blockieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0efb3a8054008d179b9d2e7e674b3482fe62a32c
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865090"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="41fd4-103">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="41fd4-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="41fd4-104">Windows PowerShell können Sie zusätzlich zur Verwendung der Microsoft-365-Verwaltungskonsole und Azure Active Directory-Portal, um Gastzugriff zu steuern.</span><span class="sxs-lookup"><span data-stu-id="41fd4-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="41fd4-105">Mit PowerShell können Sie folgende Aktionen durchführen:</span><span class="sxs-lookup"><span data-stu-id="41fd4-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="41fd4-106">Zulassen und Blockieren von Gastzugriff auf alle Teams in Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="41fd4-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="41fd4-107">Zulassen, dass Gäste zu allen Teams und Office 365-Gruppen hinzugefügt werden können</span><span class="sxs-lookup"><span data-stu-id="41fd4-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="41fd4-108">Zulassen oder Blockieren von Gastbenutzern für ein bestimmtes Team oder eine bestimmte Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="41fd4-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="41fd4-109">Weitere Informationen hierzu finden Sie im Abschnitt "Verwenden von PowerShell zur Steuerung des Zugriffs Gast" auf der Registerkarte Verwalten von [Gast Access in Office 365-Gruppen](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="41fd4-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="41fd4-110">Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="41fd4-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="41fd4-111">Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="41fd4-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="41fd4-112">Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="41fd4-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="41fd4-113">Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="41fd4-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="41fd4-114">Wenn Sie möchten Gäste in Teams blockieren und trotzdem auf SharePoint-Websites zugreifen zu können, können Azure Active Directory-Powershell-Cmdlets Sie zum Deaktivieren des AllowGuestsToAccessGroups-Parameters für das Unternehmen-Objekt unter der Voraussetzung, dass externe Freigabe für eingeschaltet ist SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="41fd4-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="41fd4-115">Gastzugriff im Vergleich zum externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="41fd4-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
