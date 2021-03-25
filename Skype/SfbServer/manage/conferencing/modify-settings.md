---
title: Ändern der Besprechungskonfigurationseinstellungen in Skype for Business Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Zusammenfassung: Informationen zum Ändern von Besprechungskonfigurationseinstellungen in Skype for Business Server.'
ms.openlocfilehash: 2f0d1220312ac810d26fdd4691492133e54db9b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119414"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Ändern der Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server ändern.
  
Sie können Die Konfigurationseinstellungen für Besprechungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell ändern.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Ändern der Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste **auf** Konferenzen und dann auf **Besprechungskonfiguration**.
    
4. Klicken Sie in der Liste der Besprechungskonfigurationen auf die Konfiguration, die Sie ändern möchten, klicken Sie auf **Bearbeiten,** und klicken Sie dann auf **Details anzeigen**.
    
5. Ändern **Sie unter** Besprechungskonfiguration bearbeiten eine der Konfigurationseinstellungen, mit Ausnahme des Konfigurationsnamens, der nicht geändert werden kann.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Ändern der Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Ändern der Besprechungskonfigurationseinstellungen das **Cmdlet Set-CsMeetingConfiguration.**
  
Der Befehl im folgenden Beispiel ändert die Besprechungskonfigurationseinstellungen, die dem Standort "Redmond" zugewiesen sind (-Identity site:Redmond). In diesem Fall ist der Wert der Eigenschaft DesignateAsPresenter auf Everyone festgelegt:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Weitere Informationen, einschließlich einer vollständigen Liste von Parametern, finden Sie unter [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
