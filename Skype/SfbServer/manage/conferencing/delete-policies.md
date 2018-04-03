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
description: 'Zusammenfassung: Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server 2015 zu löschen.'
ms.openlocfilehash: 783e2ef4c1bc0732fd93949427cea21c5ca165ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="delete-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="3fc67-103">Löschen von Konferenzrichtlinien in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3fc67-103">Delete conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3fc67-104">**Zusammenfassung:** Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server 2015 zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3fc67-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3fc67-105">Sie können konferenzrichtlinien mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell löschen.</span><span class="sxs-lookup"><span data-stu-id="3fc67-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3fc67-106">Löschen von konferenzrichtlinien mithilfe der Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="3fc67-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3fc67-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3fc67-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="3fc67-108">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="3fc67-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3fc67-109">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3fc67-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="3fc67-110">Klicken Sie in der Liste der Konferenzrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3fc67-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3fc67-111">Löschen von konferenzrichtlinien mithilfe der Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="3fc67-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3fc67-112">Verwenden Sie das Cmdlet **Remove-CsConferencingPolicy**, um Konferenzrichtlinien zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3fc67-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3fc67-113">Mit dem folgenden Befehl wird die Konferenzrichtlinie mit dem Identitätswert "RedmondConferencingPolicy" entfernt:</span><span class="sxs-lookup"><span data-stu-id="3fc67-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="3fc67-114">Mit dem nächsten Befehl werden alle Konferenzrichtlinien gelöscht, die externen Benutzern das Aufzeichnen der Konferenz erlauben:</span><span class="sxs-lookup"><span data-stu-id="3fc67-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="3fc67-115">Weitere Informationen sowie die vollständige Syntax und eine Liste der Parameter finden Sie unter [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3fc67-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

