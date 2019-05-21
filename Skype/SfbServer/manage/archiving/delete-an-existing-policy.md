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
ms.openlocfilehash: 04ea9db10a2f95ba5010471f262d58c269c173d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278412"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="9c866-103">Löschen einer vorhandenen Archivierungsrichtlinie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9c866-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="9c866-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Archivierungsrichtlinie für Skype for Business Server löschen.</span><span class="sxs-lookup"><span data-stu-id="9c866-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="9c866-105">Benutzer- und Standortrichtlinien können gelöscht werden, die globale Richtlinie jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="9c866-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="9c866-106">Wenn Sie die globale Richtlinie löschen, setzt Skype for Business Server die Richtlinie automatisch auf die Standardwerte zurück.</span><span class="sxs-lookup"><span data-stu-id="9c866-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="9c866-107">Löschen einer Richtlinie über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="9c866-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="9c866-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9c866-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9c866-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c866-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9c866-110">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="9c866-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="9c866-111">Klicken Sie in der Liste der Archivierungsrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="9c866-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="9c866-112">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9c866-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="9c866-113">Verwalten von Archivierungsrichtlinien über Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c866-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="9c866-114">Archivierungsrichtlinien können auch mit dem Cmdlet **Remove-CsArchivingPolicy** gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="9c866-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="9c866-p102">Beispielsweise dient der folgende Befehl zum Löschen der Richtlinie mit der Identität „site:Redmond“. Für Benutzer, für die zuvor die Standortrichtlinie galt, wird nach dem Löschen einer auf Standortebene konfigurierten Richtlinie stattdessen automatisch die globale Archivierungsrichtlinie angewendet:</span><span class="sxs-lookup"><span data-stu-id="9c866-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="9c866-117">Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, die auf der Benutzerebene festgelegt wurden:</span><span class="sxs-lookup"><span data-stu-id="9c866-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="9c866-118">Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, bei denen die interne Archivierung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="9c866-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="9c866-119">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9c866-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
