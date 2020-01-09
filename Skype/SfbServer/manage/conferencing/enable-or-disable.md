---
title: Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Systemsteuerung oder die Verwaltungsshell verwenden, um Einwahlkonferenzen in Skype for Business Server zu aktivieren oder zu deaktivieren.'
ms.openlocfilehash: aed5f82678dce89190ba5449ada8eb988e1a1864
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991840"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="5ff6c-103">Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5ff6c-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="5ff6c-104">**Zusammenfassung:** Erfahren Sie, wie Sie die Systemsteuerung oder die Verwaltungsshell verwenden können, um Einwahlkonferenzen in Skype for Business Server zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="5ff6c-105">Sie können Einwahlkonferenzen über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5ff6c-106">Aktivieren oder Deaktivieren von Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="5ff6c-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5ff6c-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="5ff6c-108">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5ff6c-109">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="5ff6c-110">Wählen Sie in der Liste der Konferenzrichtlinien die Richtlinie aus, für die Sie Einwahlkonferenzen zulassen möchten, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="5ff6c-p101">Wenn Sie Benutzern erlauben möchten, per Einwahl an einer Besprechung teilzunehmen, aktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="5ff6c-113">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5ff6c-114">Aktivieren oder Deaktivieren von Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="5ff6c-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5ff6c-115">Verwenden Sie zur Aktivierung oder Deaktivierung von Einwahlkonferenzen das Cmdlet **Set-CsConferencingPolicy** mit den EnableDialInConferencing-Parametern wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5ff6c-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="5ff6c-116">Weitere Informationen finden Sie unter [Satz-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5ff6c-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

