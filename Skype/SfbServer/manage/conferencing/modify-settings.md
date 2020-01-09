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
ms.openlocfilehash: 2e9d8a737a2bfc48cdcbe39540a22e4c236003b3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992852"
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
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Weitere Informationen, einschließlich einer vollständigen Liste der Parameter, finden Sie unter [Satz-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

