---
title: Ändern von Besprechungskonfigurationseinstellungen in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Zusammenfassung: Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server ändern.'
---

# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Ändern von Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server ändern.
  
Sie können Besprechungskonfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell ändern.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Ändern der Besprechungskonfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Konferenzen**", und klicken Sie dann auf **"Besprechungskonfiguration"**.
    
4. Klicken Sie in der Liste der Besprechungskonfigurationen auf die Konfiguration, die Sie ändern möchten, klicken Sie auf **"Bearbeiten**" und dann auf " **Details anzeigen"**.
    
5. Ändern Sie in " **Besprechungskonfiguration bearbeiten**" eine der Konfigurationseinstellungen, mit Ausnahme des Konfigurationsnamens, der nicht geändert werden kann.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Ändern von Besprechungskonfigurationseinstellungen mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie zum Ändern der Besprechungskonfigurationseinstellungen das Cmdlet **"Set-CsMeetingConfiguration** ".
  
Der Befehl im folgenden Beispiel ändert die Besprechungskonfigurationseinstellungen, die dem Standort Redmond (-Identity site:Redmond) zugewiesen sind. In diesem Fall wird der Wert der DesignateAsPresenter-Eigenschaft auf "Jeder" festgelegt:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Weitere Informationen, einschließlich einer vollständigen Liste von Parametern, finden Sie unter ["Set-CsMeetingConfiguration"](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
