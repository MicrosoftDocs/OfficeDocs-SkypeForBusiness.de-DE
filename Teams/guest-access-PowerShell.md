---
title: Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Verwenden Sie PowerShell, um den Gastzugriff auf Teams in Microsoft Teams zuzulassen oder zu blockieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e106dc56f56b5e26dd56384931deeecdd889305
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235522"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="91465-103">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="91465-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="91465-104">Neben der Verwendung des Microsoft 365 admin Centers und des Azure Active Directory (Azure AD)-Portals können Sie Windows PowerShell zum Steuern des Gastzugriffs verwenden.</span><span class="sxs-lookup"><span data-stu-id="91465-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="91465-105">Mit PowerShell können Sie folgende Aktionen durchführen:</span><span class="sxs-lookup"><span data-stu-id="91465-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="91465-106">Zulassen oder Blockieren des Gastzugriffs auf alle Teams und Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="91465-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="91465-107">Zulassen, dass Gäste allen Teams und Office 365-Gruppen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="91465-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="91465-108">Zulassen oder Blockieren von Gastbenutzern für ein bestimmtes Team oder eine bestimmte Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="91465-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="91465-109">Ausführliche Informationen finden Sie unter "Verwenden von PowerShell zum Steuern des Gastzugriffs" in [Verwalten des Gastzugriffs in Office 365-Gruppen](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span><span class="sxs-lookup"><span data-stu-id="91465-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>
  
<span data-ttu-id="91465-110">Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="91465-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="91465-111">Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="91465-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="91465-112">Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="91465-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="91465-113">Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="91465-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="91465-114">Wenn Sie die Gäste in Teams blockieren und Ihnen weiterhin den Zugriff auf SharePoint-Websites gestatten möchten, können Sie Azure AD PowerShell-Cmdlets verwenden, um den AllowGuestsToAccessGroups-Parameter für das Unternehmensobjekt zu deaktivieren, vorausgesetzt, die externe Freigabe ist für SharePoint-Websites aktiviert. .</span><span class="sxs-lookup"><span data-stu-id="91465-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="91465-115">Gastzugriff vs. externer Zugriff</span><span class="sxs-lookup"><span data-stu-id="91465-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
