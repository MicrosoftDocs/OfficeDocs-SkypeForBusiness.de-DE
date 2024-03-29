---
title: Verwalten Skype for Business Online-Organisationen
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Verwenden Windows PowerShell- und Get-CsTenant- und Get-CsTenantLicensingConfiguration-Cmdlets, um Informationen zu Ihrem Skype for Business Online-Mandanten zu erhalten.
ms.openlocfilehash: e45f1bdd2c14aea34e07183dde86031a8c503476
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623087"
---
# <a name="manage-skype-for-business-online-organizations"></a>Verwalten Skype for Business Online-Organisationen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> Die neueste [version Teams PowerShell Public Preview Release](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und stellt ein einzelnes Modul für Teams PowerShell-Verwaltung zur Verfügung.

Sie finden Informationen zu Ihrem Skype for Business Online-Mandanten mithilfe der **Cmdlets Get-CsTenant** und **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Verwalten Skype for Business Online-Mandanten

Rufen Sie das [Cmdlet Get-CsTenant](/powershell/module/skype/Get-CsTenant) ohne zusätzliche Parameter auf, um Informationen zu Ihrem Skype for Business Online-Mandanten zurückzukehren.
  
```PowerShell
Get-CsTenant
```

Wenn Sie nur den Mandantennamen und die Id zurückgeben möchten, verwenden Sie diesen Befehl.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Der Wert des _Parameters TenantID_ ist erforderlich, wenn Sie Cmdlets wie [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) und [Set-CsTenantFederationConfiguration ausführen.](/powershell/module/skype/Set-CsTenantFederationConfiguration)
  
Informationen dazu, ob Lizenzierungsinformationen für den angegebenen Mandanten im Skype for Business Online Admin Center verfügbar sind, finden Sie im [Cmdlet Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Onlineverwaltung in Skype for Business mithilfe Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
