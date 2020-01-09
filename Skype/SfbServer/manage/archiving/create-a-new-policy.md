---
title: Erstellen einer neuen Archivierungsrichtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine neue Archivierungsrichtlinie für Skype for Business Server erstellen.'
ms.openlocfilehash: 8542c31050cf4ca9383c22b39c83b28309d3ea32
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992732"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="5989b-103">Erstellen einer neuen Archivierungsrichtlinie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5989b-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="5989b-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine neue Archivierungsrichtlinie für Skype for Business Server erstellen.</span><span class="sxs-lookup"><span data-stu-id="5989b-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="5989b-105">Sie können neue Archivierungsrichtlinien über die Systemsteuerung oder mit Windows PowerShell-Cmdlets erstellen.</span><span class="sxs-lookup"><span data-stu-id="5989b-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="5989b-106">Erstellen einer neuen Archivierungsrichtlinie über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="5989b-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="5989b-107">So erstellen Sie eine neue Archivierungsrichtlinie über die Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="5989b-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="5989b-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="5989b-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="5989b-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5989b-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5989b-110">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="5989b-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="5989b-111">Klicken Sie auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5989b-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="5989b-112">Um eine Archivierungsrichtlinie auf Standortebene zu erstellen, klicken Sie auf **Standortrichtlinie** und anschließend unter **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5989b-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="5989b-113">Um eine Archivierungsrichtlinie auf Benutzerebene zu erstellen, klicken Sie auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="5989b-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="5989b-114">Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5989b-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="5989b-115">Geben Sie unter **Name** einen Namen für die neue Richtlinie an (z. B. „externalContoso“).</span><span class="sxs-lookup"><span data-stu-id="5989b-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="5989b-116">Geben Sie unter **Beschreibung** Einzelheiten über den Zweck der Richtlinie an (z. B. Archivierungsrichtlinie für externe Benutzer von Contoso).</span><span class="sxs-lookup"><span data-stu-id="5989b-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="5989b-117">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der Kommunikation mit internen Benutzern zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5989b-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="5989b-118">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5989b-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="5989b-119">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5989b-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5989b-120">Die Einstellungen einer Benutzerrichtlinie gelten nur für bestimmte Benutzer und Benutzergruppen, auf die Sie die Richtlinie anwenden.</span><span class="sxs-lookup"><span data-stu-id="5989b-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="5989b-121">Ausführliche Informationen finden Sie unter [Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="5989b-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="5989b-122">Erstellen einer neuen Archivierungsrichtlinie mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5989b-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="5989b-123">Sie können neue Archivierungsrichtlinien auch mit dem Windows PowerShell-Cmdlet **New-CsArchivingPolicy** erstellen.</span><span class="sxs-lookup"><span data-stu-id="5989b-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="5989b-124">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="5989b-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="5989b-125">So erstellen Sie eine neue Archivierungsrichtlinie auf Standortebene</span><span class="sxs-lookup"><span data-stu-id="5989b-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="5989b-126">Mit diesem Befehl wird eine neue Archivierungsrichtlinie für den Standort „Redmond“ erstellt:</span><span class="sxs-lookup"><span data-stu-id="5989b-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="5989b-127">So erstellen Sie eine neue Archivierungsrichtlinie auf Benutzerebene</span><span class="sxs-lookup"><span data-stu-id="5989b-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="5989b-128">Um eine neue Archivierungsrichtlinie auf Benutzerebene zu erstellen, geben Sie beim Erstellen der Richtlinie einfach eine eindeutige ID an:</span><span class="sxs-lookup"><span data-stu-id="5989b-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="5989b-129">So erstellen Sie eine neue Archivierungsrichtlinie zum Aktivieren der Archivierung interner Kommunikationssitzungen</span><span class="sxs-lookup"><span data-stu-id="5989b-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="5989b-130">Da in den vorhergehenden Befehlen keine Parameter (mit Ausnahme des Parameters zur obligatorischen Identität) angegeben wurden, verwenden die neuen Richtlinien die Standardwerte für alle ihre Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5989b-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="5989b-131">Zum Erstellen von Richtlinien, die unterschiedliche Eigenschaftswerte verwenden, fügen Sie einfach den entsprechenden Parameter-und Parameterwert hinzu.</span><span class="sxs-lookup"><span data-stu-id="5989b-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="5989b-132">Mit dem folgenden Befehl wird beispielsweise eine Archivierungsrichtlinie erstellt, die die Archivierung interner Instant Messaging-Sitzungen ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="5989b-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="5989b-133">So erstellen Sie eine neue Archivierungsrichtlinie zur Archivierung interner und externer Kommunikationssitzungen</span><span class="sxs-lookup"><span data-stu-id="5989b-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="5989b-p104">Mehrere Eigenschaftenwerte können durch Einschließen mehrerer Parameter geändert werden. Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie zum Archivieren interner und externer Chatsitzungen konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="5989b-p104">Multiple property values can be modified by including multiple parameters. For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
