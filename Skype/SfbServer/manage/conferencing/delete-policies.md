---
title: Löschen von Konferenzrichtlinien in Skype for Business Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server löschen.'
ms.openlocfilehash: d77910cb5fe39dcb47564b1b456a314ae03584a5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773695"
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
