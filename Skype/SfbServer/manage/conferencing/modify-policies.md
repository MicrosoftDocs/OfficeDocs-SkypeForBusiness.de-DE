---
title: Ändern von Konferenzrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server ändern.'
ms.openlocfilehash: 9cfb13436a01439a8d5ea152ca1d8ac543bc0e88
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991810"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="6c1d8-103">Ändern von Konferenzrichtlinien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6c1d8-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="6c1d8-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server ändern.</span><span class="sxs-lookup"><span data-stu-id="6c1d8-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="6c1d8-105">Sie können Konferenzrichtlinien über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell ändern.</span><span class="sxs-lookup"><span data-stu-id="6c1d8-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6c1d8-106">Ändern von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6c1d8-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6c1d8-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="6c1d8-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6c1d8-108">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6c1d8-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6c1d8-109">Klicken Sie auf der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="6c1d8-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="6c1d8-110">Klicken Sie in der Liste mit den Konferenzrichtlinien auf die Richtlinie, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="6c1d8-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6c1d8-111">Ändern Sie im Abschnitt **Konferenzrichtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6c1d8-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="6c1d8-112">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6c1d8-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6c1d8-113">Ändern von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="6c1d8-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6c1d8-114">Wenn Sie Konferenzrichtlinien ändern möchten, verwenden Sie das Cmdlet " **Satz-CsConferencingPolicy** ".</span><span class="sxs-lookup"><span data-stu-id="6c1d8-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="6c1d8-115">Im folgenden Beispiel wird ein Eigenschaftswert der Konferenzrichtlinien-SalesConferencingPolicy geändert.</span><span class="sxs-lookup"><span data-stu-id="6c1d8-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="6c1d8-116">Mit dem Befehl wird der Wert der AllowConferenceRecording-Eigenschaft auf false festgelegt:</span><span class="sxs-lookup"><span data-stu-id="6c1d8-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="6c1d8-117">Weitere Informationen, einschließlich der vollständigen Syntax und einer Liste von Parametern, finden Sie unter [CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6c1d8-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

