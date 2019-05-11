---
title: Ändern von konferenzrichtlinien in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Zusammenfassung: Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server ändern.'
ms.openlocfilehash: 0ca232398c9133c3340cbae909ac43d44ba641dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911987"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="2a4b6-103">Ändern von konferenzrichtlinien in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="2a4b6-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="2a4b6-104">**Zusammenfassung:** Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server ändern.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="2a4b6-105">Sie können konferenzrichtlinien mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell ändern.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2a4b6-106">Ändern von konferenzrichtlinien mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="2a4b6-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2a4b6-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="2a4b6-108">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2a4b6-109">Klicken Sie auf der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="2a4b6-110">Klicken Sie in der Liste mit den Konferenzrichtlinien auf die Richtlinie, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2a4b6-111">Ändern Sie im Abschnitt **Konferenzrichtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="2a4b6-112">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2a4b6-113">Ändern von konferenzrichtlinien mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="2a4b6-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="2a4b6-114">Verwenden Sie das **Set-CsConferencingPolicy** -Cmdlet, um konferenzrichtlinien zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="2a4b6-115">Das folgende Beispiel ändert den Wert einer Eigenschaft der konferenzrichtlinie "salesconferencingpolicy" zu.</span><span class="sxs-lookup"><span data-stu-id="2a4b6-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="2a4b6-116">Der Befehl wird den Wert der AllowConferenceRecording-Eigenschaft auf false festgelegt:</span><span class="sxs-lookup"><span data-stu-id="2a4b6-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="2a4b6-117">Weitere Informationen sowie die vollständige Syntax und eine Liste der Parameter finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2a4b6-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

