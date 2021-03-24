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
description: 'Zusammenfassung: Informationen zum Zuweisen von Konferenzrichtlinien in Skype for Business Server.'
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099161"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Zuweisen von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server zuweisen.
  
Sie können Benutzern Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell und des **Grant-CsConferencingPolicy-Cmdlets** zuweisen.
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Zuweisen von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell

Im folgenden Beispiel wird die Richtlinie "SalesConferencingPolicy" dem Benutzer mit der Identität "Ken Myer" zugewiesen:
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Im nächsten Beispiel wird die Konferenzrichtlinie FinanceConferencingPolicy allen Benutzern zugewiesen, die über Konten in der Organisationseinheit Finance verfügen. Damit allen Benutzern einer Organisationseinheit (OU) die gleiche Richtlinie zugewiesen wird, werden mit dem Cmdlet Get-CsUser alle Konten in dieser OU abgerufen. Nachdem die Benutzerkonten abgerufen wurden, werden diese Informationen an das cmdlet Grant-CsConferencingPolicy weitergepfrät, das jedem Benutzer in der Auflistung die Richtlinie FinanceConferencingPolicy zurät:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Weitere Informationen, einschließlich vollständiger Syntax und einer Liste von Parametern, finden Sie unter [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
