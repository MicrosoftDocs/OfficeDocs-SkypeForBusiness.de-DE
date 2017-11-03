---
title: Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: Verwenden Sie PowerShell, um den Gastzugriff auf Teams in Microsoft Teams zuzulassen oder zu blockieren.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: fd9844d0a72932cb28dca97d8bb8c1c05d0ddfe5
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="a5de1-103">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="a5de1-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="a5de1-104">Zusätzlich zur Verwendung des Office 365 Admin Center und des Azure Active Directory-Portals können Sie Windows PowerShell verwenden, um den Gastzugriff zu steuern.</span><span class="sxs-lookup"><span data-stu-id="a5de1-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="a5de1-105">Mit PowerShell können Sie folgende Aktionen durchführen:</span><span class="sxs-lookup"><span data-stu-id="a5de1-105">With PowerShell, you can do the following:</span></span>
  
  
   

- <span data-ttu-id="a5de1-106">Zulassen und Blockieren von Gastzugriff auf alle Teams in Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="a5de1-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="a5de1-107">Zulassen, dass Gäste zu allen Teams und Office 365-Gruppen hinzugefügt werden können</span><span class="sxs-lookup"><span data-stu-id="a5de1-107">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="a5de1-108">Zulassen oder Blockieren von Gastbenutzern für ein bestimmtes Team oder eine bestimmte Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="a5de1-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="a5de1-109">Weitere Einzelheiten finden Sie unter [Verwenden von PowerShell zum Steuern von Gastzugriff](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="a5de1-109">For more details, see [Use PowerShell to control guest access](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="a5de1-110">Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5de1-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="a5de1-111">Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="a5de1-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="a5de1-112">Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="a5de1-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="a5de1-113">Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="a5de1-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
 
<span data-ttu-id="a5de1-114">Wenn Sie Gäste in Teams blockieren möchten und den Gästen dennoch den Zugriff auf SharePoint-Websites ermöglichen möchten, können Sie mithilfe von PowerShell-Cmdlets für Azure Active Directory den Parameter „AllowGuestAccessToGroups“ für das Objekt „Company“ deaktivieren. Dabei wird angenommen, dass externe Freigaben für SharePoint-Websites aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="a5de1-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   