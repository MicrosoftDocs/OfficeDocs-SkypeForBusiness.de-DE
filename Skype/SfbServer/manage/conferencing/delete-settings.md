---
title: Löschen der Konfigurationseinstellungen für Besprechungen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Zusammenfassung: Informationen zum Löschen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.'
ms.openlocfilehash: dec2e51dfe6ae0b9983515d849bc9fc416e9bcc4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Löschen der Konfigurationseinstellungen für Besprechungen in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen zum Löschen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.
  
Sie können löschen besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell.
  
Eine Standort- oder Benutzerkonfiguration kann gelöscht werden. Die globale Konfiguration kann jedoch nicht gelöscht werden. Wenn Sie die globale Konfiguration löschen, werden die Standardwerte automatisch wiederhergestellt.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Löschen von besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.
    
4. Klicken Sie in der Liste der Besprechungskonfigurationen auf die Standort- oder Poolkonfiguration, die Sie löschen möchten, klicken Sie dann auf **Bearbeiten** und anschließend auf **Löschen**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Löschen von besprechungskonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie das Cmdlet **Remove-CsMeetingConfiguration**, um Besprechungseinstellungen zu löschen.
  
Der folgende Befehl löscht die Besprechungskonfigurationseinstellungen des Standorts Redmond:
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Der nächste Befehl löscht alle Besprechungskonfigurationseinstellungen des Standortbereichs:
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Weitere Informationen sowie eine vollständige Liste der Parameter finden Sie unter [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

