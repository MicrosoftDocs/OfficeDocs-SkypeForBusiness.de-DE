---
title: Ändern von Konferenzrichtlinien in Skype for Business Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server ändern.'
ms.openlocfilehash: e7976cfd41be223aa0766f7a34d58563a21cb08e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773655"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Ändern von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server ändern.
  
Sie können Konferenzrichtlinien mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell ändern.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Ändern von Konferenzrichtlinien mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Konferenzen"** und dann auf **"Konferenzrichtlinie".**
    
4. Klicken Sie in der Liste mit den Konferenzrichtlinien auf die Richtlinie, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.
    
5. Ändern Sie im Abschnitt **Konferenzrichtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Ändern von Konferenzrichtlinien mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie zum Ändern von Konferenzrichtlinien das Cmdlet **"Set-CsConferencingPolicy".**
  
Im folgenden Beispiel wird ein Eigenschaftswert der Konferenzrichtlinie SalesConferencingPolicy geändert. Der Befehl legt den Wert der AllowConferenceRecording-Eigenschaft auf "False" fest:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Weitere Informationen, einschließlich der vollständigen Syntax und einer Liste von Parametern, finden Sie unter ["Set-CsConferencingPolicy".](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
