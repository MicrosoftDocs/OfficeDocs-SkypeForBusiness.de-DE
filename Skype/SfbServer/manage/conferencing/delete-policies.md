---
title: Löschen von Konferenzrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server löschen.'
ms.openlocfilehash: 2d02fa580acbc11c1b41643ab25cecba618ed09a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294250"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Löschen von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server löschen.
  
Sie können Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell löschen.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Löschen von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
4. Klicken Sie in der Liste der Konferenzrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Löschen von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie das Cmdlet **Remove-CsConferencingPolicy**, um Konferenzrichtlinien zu löschen.
  
Mit dem folgenden Befehl wird die Konferenzrichtlinie mit dem Identitätswert "RedmondConferencingPolicy" entfernt:
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

Mit dem nächsten Befehl werden alle Konferenzrichtlinien gelöscht, die externen Benutzern das Aufzeichnen der Konferenz erlauben:
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Weitere Informationen, einschließlich der vollständigen Syntax und einer Liste von Parametern, finden Sie unter [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
  

