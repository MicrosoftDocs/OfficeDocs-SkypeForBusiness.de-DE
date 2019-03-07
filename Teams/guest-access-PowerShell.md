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
ms.openlocfilehash: a9215cdbc360f1bda1d9d0ea75c1a9fe6ab0f458
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464588"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="95674-103">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="95674-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="95674-104">Zusätzlich zur Verwendung des Office 365 Admin Center und des Azure Active Directory-Portals können Sie Windows PowerShell verwenden, um den Gastzugriff zu steuern.</span><span class="sxs-lookup"><span data-stu-id="95674-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="95674-105">Mit PowerShell können Sie folgende Aktionen durchführen:</span><span class="sxs-lookup"><span data-stu-id="95674-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="95674-106">Zulassen und Blockieren von Gastzugriff auf alle Teams in Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="95674-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="95674-107">Zulassen, dass Gäste zu allen Teams und Office 365-Gruppen hinzugefügt werden können</span><span class="sxs-lookup"><span data-stu-id="95674-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="95674-108">Zulassen oder Blockieren von Gastbenutzern für ein bestimmtes Team oder eine bestimmte Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="95674-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="95674-109">Weitere Informationen hierzu finden Sie im Abschnitt "Verwenden von PowerShell zur Steuerung des Zugriffs Gast" auf der Registerkarte Verwalten von [Gast Access in Office 365-Gruppen](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="95674-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="95674-110">Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="95674-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="95674-111">Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="95674-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="95674-112">Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="95674-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="95674-113">Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="95674-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="95674-114">Wenn Sie Gäste in Teams blockieren möchten und den Gästen dennoch den Zugriff auf SharePoint-Websites ermöglichen möchten, können Sie mithilfe von PowerShell-Cmdlets für Azure Active Directory den Parameter „AllowGuestAccessToGroups“ für das Objekt „Company“ deaktivieren. Dabei wird angenommen, dass externe Freigaben für SharePoint-Websites aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="95674-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="95674-115">Gastzugriff im Vergleich zum externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="95674-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]