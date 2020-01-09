---
title: Löschen einer vorhandenen Archivierungsrichtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Archivierungsrichtlinie für Skype for Business Server löschen.'
ms.openlocfilehash: c08b76996b3d54e8be07e731faae87dce0470cc1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992362"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="a2ceb-103">Löschen einer vorhandenen Archivierungsrichtlinie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a2ceb-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="a2ceb-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Archivierungsrichtlinie für Skype for Business Server löschen.</span><span class="sxs-lookup"><span data-stu-id="a2ceb-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="a2ceb-105">Benutzer- und Standortrichtlinien können gelöscht werden, die globale Richtlinie jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="a2ceb-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="a2ceb-106">Wenn Sie die globale Richtlinie löschen, setzt Skype for Business Server die Richtlinie automatisch auf die Standardwerte zurück.</span><span class="sxs-lookup"><span data-stu-id="a2ceb-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="a2ceb-107">Löschen einer Richtlinie über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="a2ceb-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="a2ceb-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a2ceb-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="a2ceb-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a2ceb-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a2ceb-110">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="a2ceb-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="a2ceb-111">Klicken Sie in der Liste der Archivierungsrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="a2ceb-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="a2ceb-112">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a2ceb-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="a2ceb-113">Verwalten von Archivierungsrichtlinien über Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2ceb-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="a2ceb-114">Archivierungsrichtlinien können auch mit dem Cmdlet **Remove-CsArchivingPolicy** gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a2ceb-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="a2ceb-p102">Beispielsweise dient der folgende Befehl zum Löschen der Richtlinie mit der Identität „site:Redmond“. Für Benutzer, für die zuvor die Standortrichtlinie galt, wird nach dem Löschen einer auf Standortebene konfigurierten Richtlinie stattdessen automatisch die globale Archivierungsrichtlinie angewendet:</span><span class="sxs-lookup"><span data-stu-id="a2ceb-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="a2ceb-117">Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, die auf der Benutzerebene festgelegt wurden:</span><span class="sxs-lookup"><span data-stu-id="a2ceb-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="a2ceb-118">Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, bei denen die interne Archivierung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="a2ceb-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="a2ceb-119">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="a2ceb-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
