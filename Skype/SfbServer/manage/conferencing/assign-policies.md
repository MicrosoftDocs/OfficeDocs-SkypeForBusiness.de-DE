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
ms.localizationpriority: medium
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server zuweisen.'
ms.openlocfilehash: 3ae21518cf53aad48d4fc9b6963d0e5402007db9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635279"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Zuweisen von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server zuweisen.
  
Sie können Benutzern Konferenzrichtlinien zuweisen, indem Sie Skype for Business Server Verwaltungsshell und das Cmdlet **Grant-CsConferencingPolicy** verwenden.
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Zuweisen von Konferenzrichtlinien mithilfe Skype for Business Server Verwaltungsshell

Im folgenden Beispiel wird die Richtlinie SalesConferencingPolicy dem Benutzer mit der Identität "Ken Myer" zugewiesen:
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Im nächsten Beispiel wird die Konferenzrichtlinie "FinanceConferencingPolicy" allen Benutzern zugewiesen, die über Konten in der Organisationseinheit "Finance" verfügen. Damit allen Benutzern einer Organisationseinheit (OU) die gleiche Richtlinie zugewiesen wird, werden mit dem Cmdlet Get-CsUser alle Konten in dieser OU abgerufen. Nachdem die Benutzerkonten abgerufen wurden, werden diese Informationen an das Cmdlet Grant-CsConferencingPolicy weitergeleitet, das die FinanceConferencingPolicy-Richtlinie jedem Benutzer in der Sammlung zuweist:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Weitere Informationen, einschließlich der vollständigen Syntax und einer Liste von Parametern, finden Sie unter [Grant-CsConferencingPolicy.](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)
