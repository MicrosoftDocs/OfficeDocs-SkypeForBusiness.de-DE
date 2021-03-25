---
title: Löschen von Besprechungskonfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Zusammenfassung: Informationen zum Löschen von Besprechungskonfigurationseinstellungen in Skype for Business Server.'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119494"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Löschen von Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server löschen.
  
Sie können Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell löschen.
  
Sie können eine Website- oder Benutzerkonfiguration löschen, aber die globale Konfiguration nicht löschen. Wenn Sie versuchen, die globale Konfiguration zu löschen, wird sie automatisch auf die Standardwerte zurückgesetzt.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Löschen von Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste **auf** Konferenzen und dann auf **Besprechungskonfiguration**.
    
4. Klicken Sie in der Liste der Besprechungskonfigurationen auf die Website- oder Poolkonfiguration, die Sie löschen möchten, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Löschen von Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Löschen von Besprechungseinstellungen das **Cmdlet Remove-CsMeetingConfiguration.**
  
Mit dem folgenden Befehl werden die auf den Standort "Redmond" angewendeten Besprechungskonfigurationseinstellungen entfernt:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Mit dem nächsten Befehl werden alle Besprechungskonfigurationseinstellungen entfernt, die auf den Standortbereich angewendet wurden:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Weitere Informationen, einschließlich einer vollständigen Liste von Parametern, finden Sie unter [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
