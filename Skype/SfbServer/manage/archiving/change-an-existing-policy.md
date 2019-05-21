---
title: Ändern einer vorhandenen Archivierungsrichtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Richtlinien für die Benutzer Archivierung für Skype for Business Server ändern.'
ms.openlocfilehash: 4a3da0bfe403d1a00807865cd07762111b59b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282021"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="41afb-103">Ändern einer vorhandenen Archivierungsrichtlinie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="41afb-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="41afb-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie die Richtlinien für die Benutzer Archivierung für Skype for Business Server ändern.</span><span class="sxs-lookup"><span data-stu-id="41afb-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="41afb-105">Bei der ersten Bereitstellung von Skype for Business Server richten Sie anfängliche Archivierungsrichtlinien ein, die bestimmen, wie die Archivierung für die Benutzer in Ihrer Bereitstellung implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="41afb-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="41afb-106">In diesem Thema wird beschrieben, wie Richtlinien verwaltet und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="41afb-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="41afb-107">Bearbeiten von Archivierungsrichtlinien über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="41afb-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="41afb-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="41afb-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="41afb-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="41afb-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="41afb-110">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="41afb-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="41afb-111">Führen Sie in der Liste der Richtlinie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="41afb-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="41afb-112">Um die Richtlinie für Ihre gesamte Bereitstellung zu ändern, klicken Sie in der Liste der Richtlinien auf **Global**, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="41afb-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="41afb-113">Um die Richtlinie für einen einzelnen Standort zu ändern, klicken Sie in der Liste der Richtlinien auf den Standortnamen, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="41afb-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="41afb-114">Um die Richtlinie für einen einzelnen Benutzer oder eine Benutzergruppe zu ändern, klicken Sie in der Liste der Richtlinien auf den Benutzer- oder Gruppennamen, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="41afb-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="41afb-115">Führen Sie auf der Seite **Bearbeiten der Archivierungsrichtlinien** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="41afb-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="41afb-116">Markieren Sie das Kontrollkästchen **Interne Kommunikation archivieren** oder entfernen Sie die Markierung, um die interne Archivierung für die Richtlinie zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="41afb-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="41afb-117">Markieren Sie das Kontrollkästchen **Externe Kommunikation archivieren** oder entfernen Sie die Markierung, um die externe Archivierung für die Richtlinie zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="41afb-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="41afb-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="41afb-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="41afb-119">Die Einstellungen einer Benutzerrichtlinie gelten nur für bestimmte Benutzer und Benutzergruppen, auf die Sie die Richtlinie anwenden.</span><span class="sxs-lookup"><span data-stu-id="41afb-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="41afb-120">Ausführliche Informationen finden Sie unter [Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="41afb-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="41afb-121">Bearbeiten von Archivierungsrichtlinien mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41afb-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="41afb-122">Archivierungsrichtlinien können auch mit dem Windows PowerShell-Cmdlet **Set-CsArchivingPolicy** bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="41afb-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="41afb-123">Archivierungsrichtlinien aktivieren</span><span class="sxs-lookup"><span data-stu-id="41afb-123">Enable archiving policies</span></span>

<span data-ttu-id="41afb-124">Setzen Sie den Wert des Parameters „ArchiveInternal“ auf „True ($True)“, um die Archivierung von internen Kommunikationssitzungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="41afb-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="41afb-125">Setzen Sie den Wert des Parameters „ArchiveExternal“ auf „True ($True)“, um die Archivierung von externen Kommunikationssitzungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="41afb-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="41afb-126">Um die Archivierung sowohl interner als auch externer Kommunikationssitzungen zu ermöglichen, setzen Sie den Wert für die ArchiveInternal-und ArchiveExternal-Parameter auf true:</span><span class="sxs-lookup"><span data-stu-id="41afb-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="41afb-127">Archivierungsrichtlinien deaktivieren</span><span class="sxs-lookup"><span data-stu-id="41afb-127">Disable archiving policies</span></span>

<span data-ttu-id="41afb-128">Setzen Sie die Werte der Parameter für „ArchiveInternal“ und „ArchiveExternal“ auf „False ($False)“, um die Archivierung vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="41afb-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
