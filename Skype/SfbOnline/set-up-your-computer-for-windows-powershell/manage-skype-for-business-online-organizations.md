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
ms.openlocfilehash: 340ef9de0e793cbbed7d471754ebca715eb7eaf7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989230"
---
# <a name="manage-skype-for-business-online-organizations"></a>Verwalten von Skype for Business Online-Organisationen

Sie können Informationen zu Ihrem Skype for Business Online-Mandanten mithilfe der Cmdlets **Get-CsTenant** und **Get-CsTenantLicensingConfiguration** finden.
  
## <a name="manage-skype-for-business-online-tenants"></a>Verwalten von Skype for Business Online-Mandanten

Wenn Sie Informationen zu Ihrem Skype for Business Online-Mandanten zurückgeben möchten, rufen Sie das Cmdlet " [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) " ohne zusätzliche Parameter auf.
  
```PowerShell
Get-CsTenant
```

Wenn Sie nur den Mandantennamen und die ID zurückgeben möchten, verwenden Sie diesen Befehl.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Der Wert des _Tenant_ -Parameters ist erforderlich, wenn Cmdlets wie " [CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) " und " [CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)" ausgeführt werden.
  
Wenn Sie Informationen darüber finden möchten, ob Lizenzierungsinformationen für den angegebenen Mandanten im Skype for Business Online Admin Center zur Verfügung stehen, verwenden Sie das Cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
