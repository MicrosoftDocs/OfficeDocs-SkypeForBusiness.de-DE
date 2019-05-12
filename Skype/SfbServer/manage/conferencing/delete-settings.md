---
title: Löschen von besprechungskonfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Zusammenfassung: Informationen zum Löschen von besprechungskonfigurationseinstellungen in Skype für Business Server.'
ms.openlocfilehash: 2fbb278745eba392016b163be8f59a3abb07b47d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919381"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Löschen von besprechungskonfigurationseinstellungen in Skype für Business Server
 
**Zusammenfassung:** Informationen zum Löschen von besprechungskonfigurationseinstellungen in Skype für Business Server.
  
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
  

