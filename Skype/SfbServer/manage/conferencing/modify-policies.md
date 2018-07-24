---
title: Ändern von konferenzrichtlinien in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Zusammenfassung: Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server ändern.'
ms.openlocfilehash: 5883af04310f671e536460dbd466ce583cb52ebd
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970240"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Ändern von konferenzrichtlinien in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server ändern.
  
Sie können konferenzrichtlinien mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell ändern.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Ändern von konferenzrichtlinien mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie auf der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
4. Klicken Sie in der Liste mit den Konferenzrichtlinien auf die Richtlinie, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.
    
5. Ändern Sie im Abschnitt **Konferenzrichtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Ändern von konferenzrichtlinien mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie das **Set-CsConferencingPolicy** -Cmdlet, um konferenzrichtlinien zu ändern.
  
Das folgende Beispiel ändert den Wert einer Eigenschaft der konferenzrichtlinie "salesconferencingpolicy" zu. Der Befehl wird den Wert der AllowConferenceRecording-Eigenschaft auf false festgelegt:
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Weitere Informationen sowie die vollständige Syntax und eine Liste der Parameter finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

