---
title: Löschen von Konferenzrichtlinien in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Summary: Learn how to delete conferencing policies in Skype for Business Server 2015.'
ms.openlocfilehash: 783e2ef4c1bc0732fd93949427cea21c5ca165ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="delete-conferencing-policies-in-skype-for-business-server-2015"></a>Löschen von Konferenzrichtlinien in Skype for Business Server 2015
 
**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.
  
You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Delete conferencing policies by using Skype for Business Server Control Panel

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Open Skype for Business Server Control Panel.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
4. Klicken Sie in der Liste der Konferenzrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Delete conferencing policies by using Skype for Business Server Management Shell

Verwenden Sie das Cmdlet **Remove-CsConferencingPolicy**, um Konferenzrichtlinien zu löschen.
  
Mit dem folgenden Befehl wird die Konferenzrichtlinie mit dem Identitätswert "RedmondConferencingPolicy" entfernt:
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

Mit dem nächsten Befehl werden alle Konferenzrichtlinien gelöscht, die externen Benutzern das Aufzeichnen der Konferenz erlauben:
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
  

