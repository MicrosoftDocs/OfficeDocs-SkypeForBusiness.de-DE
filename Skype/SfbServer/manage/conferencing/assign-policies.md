---
title: Zuweisen von Konferenzrichtlinien in Skype for Business Server
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
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server zuweisen.'
ms.openlocfilehash: d13710d2cc4f6edf1cee16cbc9aa77799ceec8a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806475"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Zuweisen von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server zuweisen.
  
Sie können Benutzern Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell und des **Cmdlets "Grant-CsConferencingPolicy"** zuweisen.
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Zuweisen von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell

Im folgenden Beispiel wird die Richtlinie "SalesConferencingPolicy" dem Benutzer mit der Identität "Ken Myer" zugewiesen:
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Im nächsten Beispiel wird die Konferenzrichtlinie "FinanceConferencingPolicy" allen Benutzern zugewiesen, die über Konten in der Organisationseinheit "Finance" verfügen. Damit allen Benutzern einer Organisationseinheit (OU) die gleiche Richtlinie zugewiesen wird, werden mit dem Cmdlet Get-CsUser alle Konten in dieser OU abgerufen. Nachdem die Benutzerkonten abgerufen wurden, werden diese Informationen an das Cmdlet Grant-CsConferencingPolicy umgereiht, das jedem Benutzer in der Auflistung die Richtlinie "FinanceConferencingPolicy" zu weist:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Weitere Informationen, einschließlich vollständiger Syntax und einer Liste von Parametern, finden Sie unter [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

