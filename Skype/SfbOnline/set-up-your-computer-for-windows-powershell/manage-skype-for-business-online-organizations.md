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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Verwenden Sie Windows PowerShell und die Cmdlets Get-CsTenant und Get-CsTenantLicensingConfiguration, um Informationen zu Ihrem Skype for Business Online-Mandanten zu erhalten.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085691"
---
# <a name="manage-skype-for-business-online-organizations"></a>Verwalten von Skype for Business Online-Organisationen
> [!NOTE]
> Die neueste [Version von Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und bietet ein einzelnes Modul für die PowerShell-Verwaltung von Teams.

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

Der Wert des _Tenant_ -Parameters ist erforderlich, wenn Cmdlets wie " [CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) " und " [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx)" ausgeführt werden.
  
Wenn Sie Informationen darüber finden möchten, ob Lizenzierungsinformationen für den angegebenen Mandanten im Skype for Business Online Admin Center zur Verfügung stehen, verwenden Sie das Cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
