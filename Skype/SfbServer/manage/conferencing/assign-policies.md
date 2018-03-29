---
title: Zuweisen von Konferenzrichtlinien in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Zusammenfassung: Informationen Sie zum Zuweisen von konferenzrichtlinien in Skype für Business Server 2015.'
ms.openlocfilehash: 532065bee6f33b492639f5bcf949e29b082c5e84
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="assign-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="c9d40-103">Zuweisen von Konferenzrichtlinien in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c9d40-103">Assign conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c9d40-104">**Zusammenfassung:** Informationen Sie zum Zuweisen von konferenzrichtlinien in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c9d40-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c9d40-105">Sie können Benutzer mithilfe von Skype für Business Server-Verwaltungsshell und das Cmdlet **Grant-CsConferencingPolicy** konferenzrichtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c9d40-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c9d40-106">Zuweisen von konferenzrichtlinien mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="c9d40-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c9d40-107">In dem folgenden Beispiel wird die Richtlinie „SalesConferencingPolicy“ dem Benutzer mit der Identität „Jonas Baar“ zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="c9d40-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy

```

<span data-ttu-id="c9d40-p101">Im nächsten Beispiel wird die Konferenzrichtlinie „FinanceConferencingPolicy“ allen Benutzern zugewiesen, die über Konten in der Organisationseinheit „Finance“ verfügen. Damit allen Benutzern einer Organisationseinheit (OU) die gleiche Richtlinie zugewiesen wird, werden mit dem Cmdlet „Get-CsUser“ alle Konten in dieser OU abgerufen. Nachdem alle Benutzerkonten abgerufen wurden, werden diese Informationen an das Cmdlet „Grant-CsConferencingPolicy“ weitergeleitet, das allen Benutzern in der Auflistung die Richtlinie „FinanceConferencingPolicy“ zuweist.</span><span class="sxs-lookup"><span data-stu-id="c9d40-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy

```

<span data-ttu-id="c9d40-111">Weitere Informationen sowie die vollständige Syntax und eine Liste der Parameter finden Sie unter [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c9d40-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

