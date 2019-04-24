---
title: Verwalten von Skype für Business Online-Organisationen
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Verwenden von Windows PowerShell und die Cmdlets Get-CsTenant und Get-CsTenantLicensingConfiguration Abrufen von Informationen zu Ihrer Skype für Business Online-Mandanten.
ms.openlocfilehash: b71c89967ab34909fa461f71fc5f67c1cf99a408
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224445"
---
# <a name="manage-skype-for-business-online-organizations"></a>Verwalten von Skype für Business Online-Organisationen

Sie können Informationen zu Ihrer Skype für Business Online Mandanten mithilfe des Cmdlets **Get-CsTenant** und **Get-CsTenantLicensingConfiguration** finden.
  
## <a name="manage-skype-for-business-online-tenants"></a>Verwalten von Skype für Business Online Mandanten

Zum Zurückgeben von Informationen zu Ihrer Skype für Business Online Mandanten, rufen Sie das Cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) ohne zusätzliche Parameter.
  
```
Get-CsTenant
```

Verwenden Sie diesen Befehl, um nur den Mandanten Name und die ID zurückzugeben.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

Der Wert des Parameters _TenantID_ ist erforderlich, wenn wie [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) und [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)-Cmdlets ausführen.
  
Um finden Informationen darüber, ob Lizenzinformationen für den angegebenen Mandanten in die Skype für Business Online Administrationscenter verfügbar ist, verwenden Sie das Cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten des Computers für Skype für das Business online Management mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
