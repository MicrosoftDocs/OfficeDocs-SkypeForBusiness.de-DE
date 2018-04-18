---
title: Verwalten von Skype für Business Online-Organisationen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Verwenden von Windows PowerShell und die Cmdlets Get-CsTenant und Get-CsTenantLicensingConfiguration Abrufen von Informationen zu Ihrer Skype für Business Online-Mandanten.
ms.openlocfilehash: 1b58686b2330b43cc5978752ac4f6b4a91f9588e
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="25f79-103">Verwalten von Skype für Business Online-Organisationen</span><span class="sxs-lookup"><span data-stu-id="25f79-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="25f79-104">Sie können Informationen zu Ihrer Skype für Business Online Mandanten mithilfe des Cmdlets **Get-CsTenant** und **Get-CsTenantLicensingConfiguration** finden.</span><span class="sxs-lookup"><span data-stu-id="25f79-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="25f79-105">Verwalten von Skype für Business Online Mandanten</span><span class="sxs-lookup"><span data-stu-id="25f79-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="25f79-106">Zum Zurückgeben von Informationen zu Ihrer Skype für Business Online Mandanten, rufen Sie das Cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) ohne zusätzliche Parameter.</span><span class="sxs-lookup"><span data-stu-id="25f79-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="25f79-107">Verwenden Sie diesen Befehl, um nur den Mandanten Name und die ID zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="25f79-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="25f79-108">Der Wert des Parameters _TenantID_ ist erforderlich, wenn wie [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) und [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)-Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="25f79-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="25f79-109">Um finden Informationen darüber, ob Lizenzinformationen für den angegebenen Mandanten in die Skype für Business Online Administrationscenter verfügbar ist, verwenden Sie das Cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="25f79-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="25f79-110">See Also</span><span class="sxs-lookup"><span data-stu-id="25f79-110">Related topics</span></span>
[<span data-ttu-id="25f79-111">Einrichten des Computers für Skype für das Business online Management mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25f79-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 