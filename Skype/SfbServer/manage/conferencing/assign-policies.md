---
title: Zuweisen von konferenzrichtlinien in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Zusammenfassung: Informationen Sie zum Zuweisen von konferenzrichtlinien in Skype für Business Server.'
ms.openlocfilehash: 90a291c707be70d3d30d868013ec38b33f684050
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969711"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Zuweisen von konferenzrichtlinien in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zum Zuweisen von konferenzrichtlinien in Skype für Business Server.
  
Sie können Benutzer mithilfe von Skype für Business Server-Verwaltungsshell und das Cmdlet **Grant-CsConferencingPolicy** konferenzrichtlinien zuweisen.
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Zuweisen von konferenzrichtlinien mithilfe von Skype für Business Server-Verwaltungsshell

In dem folgenden Beispiel wird die Richtlinie „SalesConferencingPolicy“ dem Benutzer mit der Identität „Jonas Baar“ zugewiesen:
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Im nächsten Beispiel wird die Konferenzrichtlinie „FinanceConferencingPolicy“ allen Benutzern zugewiesen, die über Konten in der Organisationseinheit „Finance“ verfügen. Damit allen Benutzern einer Organisationseinheit (OU) die gleiche Richtlinie zugewiesen wird, werden mit dem Cmdlet „Get-CsUser“ alle Konten in dieser OU abgerufen. Nachdem alle Benutzerkonten abgerufen wurden, werden diese Informationen an das Cmdlet „Grant-CsConferencingPolicy“ weitergeleitet, das allen Benutzern in der Auflistung die Richtlinie „FinanceConferencingPolicy“ zuweist.
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Weitere Informationen sowie die vollständige Syntax und eine Liste der Parameter finden Sie unter [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

