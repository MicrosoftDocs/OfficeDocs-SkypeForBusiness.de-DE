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
ms.openlocfilehash: 7cf195e53ec159a8999561c0ddb8461ee1bf0ba6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991870"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="f3660-103">Löschen von Konferenzrichtlinien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f3660-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="f3660-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server löschen.</span><span class="sxs-lookup"><span data-stu-id="f3660-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="f3660-105">Sie können Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell löschen.</span><span class="sxs-lookup"><span data-stu-id="f3660-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f3660-106">Löschen von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f3660-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f3660-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f3660-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f3660-108">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="f3660-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f3660-109">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="f3660-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="f3660-110">Klicken Sie in der Liste der Konferenzrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f3660-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f3660-111">Löschen von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="f3660-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f3660-112">Verwenden Sie das Cmdlet **Remove-CsConferencingPolicy**, um Konferenzrichtlinien zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f3660-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="f3660-113">Mit dem folgenden Befehl wird die Konferenzrichtlinie mit dem Identitätswert "RedmondConferencingPolicy" entfernt:</span><span class="sxs-lookup"><span data-stu-id="f3660-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="f3660-114">Mit dem nächsten Befehl werden alle Konferenzrichtlinien gelöscht, die externen Benutzern das Aufzeichnen der Konferenz erlauben:</span><span class="sxs-lookup"><span data-stu-id="f3660-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="f3660-115">Weitere Informationen, einschließlich der vollständigen Syntax und einer Liste von Parametern, finden Sie unter [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f3660-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

