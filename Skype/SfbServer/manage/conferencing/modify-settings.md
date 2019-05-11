---
title: Ändern von besprechungskonfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Zusammenfassung: Informationen zum Ändern von besprechungskonfigurationseinstellungen in Skype für Business Server.'
ms.openlocfilehash: 0562758b16418ab79349a27d8eadb509a9f5f6ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884996"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Ändern von besprechungskonfigurationseinstellungen in Skype für Business Server
 
**Zusammenfassung:** Informationen zum Ändern von besprechungskonfigurationseinstellungen in Skype für Business Server.
  
Sie können ändern besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Ändern von besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.
    
4. Klicken Sie in der Liste mit den Besprechungskonfigurationen auf die Konfiguration, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.
    
5. Ändern Sie in **Besprechungskonfiguration bearbeiten** beliebige Konfigurationseinstellungen. Hiervon ausgenommen ist der Konfigurationsname, dieser kann nicht geändert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Ändern von besprechungskonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie Das Cmdlet **Set-CsMeetingConfiguration**, um die Besprechungskonfigurationseinstellungen anzupassen.
  
Über den Befehl im folgenden Beispiel werden die Konfigurationseinstellungen für Besprechungen geändert, die dem Standort „Redmond“ (-Identity site:Redmond) zugewiesen sind. In diesem Fall wird der Wert der Eigenschaft „DesignateAsPresenter“ auf „Everyone“ festgelegt.
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Weitere Informationen sowie eine vollständige Liste der Parameter finden Sie unter [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

