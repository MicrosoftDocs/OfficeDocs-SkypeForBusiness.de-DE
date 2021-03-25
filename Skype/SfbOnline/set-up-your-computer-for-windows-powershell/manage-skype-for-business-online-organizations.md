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
description: Verwenden Windows PowerShell- und Get-CsTenant-cmdlets Get-CsTenantLicensingConfiguration, um Informationen zu Ihrem Skype for Business Online-Mandanten zu erhalten.
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113181"
---
# <a name="manage-skype-for-business-online-organizations"></a>Verwalten von Skype for Business Online-Organisationen
> [!NOTE]
> Die neueste version der öffentlichen Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und stellt ein einzelnes Modul für die Verwaltung von Teams PowerShell zur Verfügung.

Informationen zu Ihrem Skype for Business Online-Mandanten finden Sie über die **Cmdlets Get-CsTenant** und **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Verwalten von Skype for Business Online-Mandanten

Um Informationen zu Ihrem Skype for Business Online-Mandanten zurückzukehren, rufen Sie [das Get-CsTenant-Cmdlet](/powershell/module/skype/Get-CsTenant) ohne zusätzliche Parameter auf.
  
```PowerShell
Get-CsTenant
```

Verwenden Sie diesen Befehl, um nur den Namen und die ID des Mandanten zurückzukehren.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Der Wert des _Parameters TenantID_ ist erforderlich, wenn Cmdlets wie [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) und [Set-CsTenantFederationConfiguration ausgeführt werden.](/powershell/module/skype/Set-CsTenantFederationConfiguration)
  
Wenn Sie Informationen dazu finden möchten, ob Lizenzierungsinformationen für den angegebenen Mandanten im Skype for Business Online Admin Center verfügbar sind, verwenden Sie das [Cmdlet Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für skype for business online management mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
