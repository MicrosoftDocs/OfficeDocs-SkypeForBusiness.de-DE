---
title: Löschen von Besprechungskonfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Zusammenfassung: Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server löschen.'
ms.openlocfilehash: 44b1808c5e5d27bb7dd8aef7ebcef9e26923bb6c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737831"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Löschen von Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server löschen.
  
Sie können Besprechungskonfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell löschen.
  
Sie können eine Standort- oder Benutzerkonfiguration löschen, die globale Konfiguration jedoch nicht. Wenn Sie versuchen, die globale Konfiguration zu löschen, wird sie automatisch auf die Standardwerte zurückgesetzt.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Löschen von Besprechungskonfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Konferenzen",** und klicken Sie dann auf **"Besprechungskonfiguration".**
    
4. Klicken Sie in der Liste der Besprechungskonfigurationen auf die Zu löschende Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten** und dann auf **"Löschen".**
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Löschen von Besprechungskonfigurationseinstellungen mithilfe Skype for Business Server Verwaltungsshell

Um Besprechungseinstellungen zu löschen, verwenden Sie das Cmdlet **"Remove-CsMeetingConfiguration".**
  
Mit dem folgenden Befehl werden die Besprechungskonfigurationseinstellungen entfernt, die auf den Standort Redmond angewendet wurden:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Mit dem nächsten Befehl werden alle Besprechungskonfigurationseinstellungen entfernt, die auf den Standortbereich angewendet werden:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Weitere Informationen, einschließlich einer vollständigen Liste von Parametern, finden Sie unter [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
