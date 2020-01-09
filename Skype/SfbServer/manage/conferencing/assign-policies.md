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
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="6691e-103">Zuweisen von Konferenzrichtlinien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6691e-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="6691e-104">**Zusammenfassung:** Erfahren Sie, wie Sie in Skype for Business Server Konferenzrichtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6691e-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="6691e-105">Sie können Benutzern Konferenzrichtlinien zuweisen, indem Sie die Skype for Business Server-Verwaltungsshell und das Cmdlet **Grant-CsConferencingPolicy** verwenden.</span><span class="sxs-lookup"><span data-stu-id="6691e-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6691e-106">Zuweisen von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="6691e-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6691e-107">In dem folgenden Beispiel wird die Richtlinie „SalesConferencingPolicy“ dem Benutzer mit der Identität „Jonas Baar“ zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="6691e-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="6691e-p101">Im nächsten Beispiel wird die Konferenzrichtlinie „FinanceConferencingPolicy“ allen Benutzern zugewiesen, die über Konten in der Organisationseinheit „Finance“ verfügen. Damit allen Benutzern einer Organisationseinheit (OU) die gleiche Richtlinie zugewiesen wird, werden mit dem Cmdlet „Get-CsUser“ alle Konten in dieser OU abgerufen. Nachdem alle Benutzerkonten abgerufen wurden, werden diese Informationen an das Cmdlet „Grant-CsConferencingPolicy“ weitergeleitet, das allen Benutzern in der Auflistung die Richtlinie „FinanceConferencingPolicy“ zuweist.</span><span class="sxs-lookup"><span data-stu-id="6691e-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="6691e-111">Weitere Informationen, einschließlich der vollständigen Syntax und einer Liste von Parametern, finden Sie unter [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6691e-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

