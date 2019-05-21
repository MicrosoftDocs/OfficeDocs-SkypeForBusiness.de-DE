---
title: Verwalten von Skype for Business Online-Organisationen
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Verwenden Sie Windows PowerShell und die Cmdlets Get-CsTenant und Get-CsTenantLicensingConfiguration, um Informationen zu Ihrem Skype for Business Online-Mandanten zu erhalten.
ms.openlocfilehash: 768ee4e0724bd04d38e9ce77b94372bdad498ecd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284690"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="e0088-103">Verwalten von Skype for Business Online-Organisationen</span><span class="sxs-lookup"><span data-stu-id="e0088-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="e0088-104">Sie können Informationen zu Ihrem Skype for Business Online-Mandanten mithilfe der Cmdlets **Get-CsTenant** und **Get-CsTenantLicensingConfiguration** finden.</span><span class="sxs-lookup"><span data-stu-id="e0088-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="e0088-105">Verwalten von Skype for Business Online-Mandanten</span><span class="sxs-lookup"><span data-stu-id="e0088-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="e0088-106">Wenn Sie Informationen zu Ihrem Skype for Business Online-Mandanten zurückgeben möchten, rufen Sie das Cmdlet " [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) " ohne zusätzliche Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="e0088-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="e0088-107">Wenn Sie nur den Mandantennamen und die ID zurückgeben möchten, verwenden Sie diesen Befehl.</span><span class="sxs-lookup"><span data-stu-id="e0088-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="e0088-108">Der Wert des _Tenant_ -Parameters ist erforderlich, wenn Cmdlets wie " [CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) " und " [CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)" ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e0088-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="e0088-109">Wenn Sie Informationen darüber finden möchten, ob Lizenzierungsinformationen für den angegebenen Mandanten im Skype for Business Online Admin Center zur Verfügung stehen, verwenden Sie das Cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="e0088-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e0088-110">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e0088-110">Related topics</span></span>
[<span data-ttu-id="e0088-111">Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0088-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
