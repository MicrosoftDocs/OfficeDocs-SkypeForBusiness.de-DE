---
title: Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Zusammenfassung: Informationen Sie zur Verwendung der Systemsteuerung oder -Verwaltungsshell zum Aktivieren oder Deaktivieren von einwahlkonferenzen in Skype für Business Server 2015.'
ms.openlocfilehash: 6441e548ce944cdd8786178ed7b80b0af7d625f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server-2015"></a><span data-ttu-id="830b9-103">Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="830b9-103">Enable or disable dial-in conferencing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="830b9-104">**Zusammenfassung:** Informationen Sie zur Verwendung der Systemsteuerung oder -Verwaltungsshell zum Aktivieren oder Deaktivieren von einwahlkonferenzen in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="830b9-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="830b9-105">Sie können einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="830b9-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="830b9-106">Aktivieren oder Deaktivieren von einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="830b9-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="830b9-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="830b9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="830b9-108">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="830b9-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="830b9-109">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="830b9-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="830b9-110">Wählen Sie in der Liste der Konferenzrichtlinien die Richtlinie aus, für die Sie Einwahlkonferenzen zulassen möchten, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="830b9-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="830b9-p101">Wenn Sie Benutzern erlauben möchten, per Einwahl an einer Besprechung teilzunehmen, aktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.</span><span class="sxs-lookup"><span data-stu-id="830b9-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="830b9-113">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="830b9-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="830b9-114">Aktivieren oder Deaktivieren von einwahlkonferenzen mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="830b9-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="830b9-115">Verwenden Sie zur Aktivierung oder Deaktivierung von Einwahlkonferenzen das Cmdlet **Set-CsConferencingPolicy** mit den EnableDialInConferencing-Parametern wie folgt:</span><span class="sxs-lookup"><span data-stu-id="830b9-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="830b9-116">Weitere Informationen finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="830b9-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

