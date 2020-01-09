---
title: Zuweisen von Konferenzrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server Konferenzrichtlinien zuweisen.'
ms.openlocfilehash: f5e88e14c9516785cb3c45b5682bac13865b20ae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991910"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Zuweisen von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie in Skype for Business Server Konferenzrichtlinien zuweisen.
  
Sie können Benutzern Konferenzrichtlinien zuweisen, indem Sie die Skype for Business Server-Verwaltungsshell und das Cmdlet **Grant-CsConferencingPolicy** verwenden.
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Zuweisen von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell

In dem folgenden Beispiel wird die Richtlinie „SalesConferencingPolicy“ dem Benutzer mit der Identität „Jonas Baar“ zugewiesen:
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Im nächsten Beispiel wird die Konferenzrichtlinie „FinanceConferencingPolicy“ allen Benutzern zugewiesen, die über Konten in der Organisationseinheit „Finance“ verfügen. Damit allen Benutzern einer Organisationseinheit (OU) die gleiche Richtlinie zugewiesen wird, werden mit dem Cmdlet „Get-CsUser“ alle Konten in dieser OU abgerufen. Nachdem alle Benutzerkonten abgerufen wurden, werden diese Informationen an das Cmdlet „Grant-CsConferencingPolicy“ weitergeleitet, das allen Benutzern in der Auflistung die Richtlinie „FinanceConferencingPolicy“ zuweist.
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Weitere Informationen, einschließlich der vollständigen Syntax und einer Liste von Parametern, finden Sie unter [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

