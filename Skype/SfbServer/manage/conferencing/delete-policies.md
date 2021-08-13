---
title: Löschen von Konferenzrichtlinien in Skype for Business Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server löschen.'
ms.openlocfilehash: 76648fed55f01790e2e81f8683dedde4c24ac0cdfcff956f7813735872c801eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315621"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Löschen von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server löschen.
  
Sie können Konferenzrichtlinien mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell löschen.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Löschen von Konferenzrichtlinien mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Konferenzen"** und dann auf **"Konferenzrichtlinie".**
    
4. Klicken Sie in der Liste der Konferenzrichtlinien auf die Website- oder Benutzerrichtlinie, die Sie löschen möchten, klicken Sie auf **Bearbeiten** und dann auf **"Löschen".**
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Löschen von Konferenzrichtlinien mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie das Cmdlet **"Remove-CsConferencingPolicy",** um Konferenzrichtlinien zu löschen.
  
Mit dem folgenden Befehl wird die Konferenzrichtlinie mit dem Identitätswert "RedmondConferencingPolicy" entfernt:
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

Mit dem nächsten Befehl werden alle Konferenzrichtlinien gelöscht, mit denen externe Benutzer die Konferenz aufzeichnen können:
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Weitere Informationen, einschließlich der vollständigen Syntax und einer Liste von Parametern, finden Sie unter [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
