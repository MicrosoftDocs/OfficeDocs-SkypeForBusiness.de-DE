---
title: Ändern der Einstellungen für die besprechungskonfiguration in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Einstellungen für die besprechungskonfiguration in Skype for Business Server ändern.'
ms.openlocfilehash: 6e2566a5bc48e081c1912753586aef2213e1c727
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280397"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Ändern der Einstellungen für die besprechungskonfiguration in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für Besprechungen in Skype for Business Server ändern.
  
Sie können die Einstellungen für die besprechungskonfiguration über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell ändern.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Ändern der Einstellungen für die besprechungskonfiguration mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.
    
4. Klicken Sie in der Liste mit den Besprechungskonfigurationen auf die Konfiguration, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.
    
5. Ändern Sie in **Besprechungskonfiguration bearbeiten** beliebige Konfigurationseinstellungen. Hiervon ausgenommen ist der Konfigurationsname, dieser kann nicht geändert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Ändern der Einstellungen für die besprechungskonfiguration mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie Das Cmdlet **Set-CsMeetingConfiguration**, um die Besprechungskonfigurationseinstellungen anzupassen.
  
Über den Befehl im folgenden Beispiel werden die Konfigurationseinstellungen für Besprechungen geändert, die dem Standort „Redmond“ (-Identity site:Redmond) zugewiesen sind. In diesem Fall wird der Wert der Eigenschaft „DesignateAsPresenter“ auf „Everyone“ festgelegt.
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Weitere Informationen, einschließlich einer vollständigen Liste der Parameter, finden Sie unter [Satz-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

