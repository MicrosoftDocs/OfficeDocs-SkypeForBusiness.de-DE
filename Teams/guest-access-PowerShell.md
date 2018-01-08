---
title: Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: Verwenden Sie PowerShell, um den Gastzugriff auf Teams in Microsoft Teams zuzulassen oder zu blockieren.
ms.openlocfilehash: d75bbbce689b5b0799c7d2ec806977f6d23ee906
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="4d4e2-103">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="4d4e2-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="4d4e2-104">Zusätzlich zur Verwendung des Office 365 Admin Center und des Azure Active Directory-Portals können Sie Windows PowerShell verwenden, um den Gastzugriff zu steuern.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="4d4e2-105">Mit PowerShell können Sie folgende Aktionen durchführen:</span><span class="sxs-lookup"><span data-stu-id="4d4e2-105">With PowerShell, you can do the following:</span></span>
  
  
   

- <span data-ttu-id="4d4e2-106">Zulassen und Blockieren von Gastzugriff auf alle Teams in Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="4d4e2-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="4d4e2-107">Zulassen, dass Gäste zu allen Teams und Office 365-Gruppen hinzugefügt werden können</span><span class="sxs-lookup"><span data-stu-id="4d4e2-107">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="4d4e2-108">Zulassen oder Blockieren von Gastbenutzern für ein bestimmtes Team oder eine bestimmte Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="4d4e2-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="4d4e2-109">Weitere Details finden Sie unter [Gastzugriff in Office 365-Gruppen](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell) im Abschnitt „Verwenden von PowerShell zum Steuern des Gastzugriffs“ auf der Registerkarte „Verwalten“.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-109">For more details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="4d4e2-110">Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="4d4e2-111">Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="4d4e2-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="4d4e2-112">Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="4d4e2-113">Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="4d4e2-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
 
<span data-ttu-id="4d4e2-114">Wenn Sie Gäste in Teams blockieren möchten und den Gästen dennoch den Zugriff auf SharePoint-Websites ermöglichen möchten, können Sie mithilfe von PowerShell-Cmdlets für Azure Active Directory den Parameter „AllowGuestAccessToGroups“ für das Objekt „Company“ deaktivieren. Dabei wird angenommen, dass externe Freigaben für SharePoint-Websites aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

