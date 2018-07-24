---
title: Erstellen einer neuen Archivierungsrichtlinie in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Zusammenfassung: Informationen Sie zum Erstellen einer neuen Archivierungsrichtlinie für Skype für Business Server.'
ms.openlocfilehash: e900bd9ac73a6e192eba7a506d713a56a69e794d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970358"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="77b5e-103">Erstellen einer neuen Archivierungsrichtlinie in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="77b5e-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="77b5e-104">**Zusammenfassung:** Informationen Sie zum Erstellen einer neuen Archivierungsrichtlinie für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="77b5e-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="77b5e-105">Sie können neue Archivierungsrichtlinien über die Systemsteuerung oder mit Windows PowerShell-Cmdlets erstellen.</span><span class="sxs-lookup"><span data-stu-id="77b5e-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="77b5e-106">Erstellen einer neuen Archivierungsrichtlinie über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="77b5e-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="77b5e-107">So erstellen Sie eine neue Archivierungsrichtlinie über die Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="77b5e-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="77b5e-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="77b5e-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="77b5e-109">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="77b5e-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="77b5e-110">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="77b5e-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="77b5e-111">Klicken Sie auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="77b5e-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="77b5e-112">Um eine Archivierungsrichtlinie auf Standortebene zu erstellen, klicken Sie auf **Standortrichtlinie** und anschließend unter **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="77b5e-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="77b5e-113">Um eine Archivierungsrichtlinie auf Benutzerebene zu erstellen, klicken Sie auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="77b5e-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="77b5e-114">Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="77b5e-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="77b5e-115">Geben Sie unter **Name** einen Namen für die neue Richtlinie an (z. B. „externalContoso“).</span><span class="sxs-lookup"><span data-stu-id="77b5e-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="77b5e-116">Geben Sie unter **Beschreibung** Einzelheiten über den Zweck der Richtlinie an (z. B. Archivierungsrichtlinie für externe Benutzer von Contoso).</span><span class="sxs-lookup"><span data-stu-id="77b5e-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="77b5e-117">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der Kommunikation mit internen Benutzern zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="77b5e-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
  - <span data-ttu-id="77b5e-118">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="77b5e-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="77b5e-119">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="77b5e-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="77b5e-120">Die Einstellungen einer Benutzerrichtlinie gelten nur für bestimmte Benutzer und Benutzergruppen, auf die Sie die Richtlinie anwenden.</span><span class="sxs-lookup"><span data-stu-id="77b5e-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="77b5e-121">Weitere Informationen hierzu finden Sie unter [Anwenden einer Archivierungsrichtlinie für Benutzer in Skype für Business Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="77b5e-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="77b5e-122">Erstellen einer neuen Archivierungsrichtlinie mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77b5e-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="77b5e-123">Sie können neue Archivierungsrichtlinien auch mit dem Windows PowerShell-Cmdlet **New-CsArchivingPolicy** erstellen.</span><span class="sxs-lookup"><span data-stu-id="77b5e-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="77b5e-124">Weitere Informationen finden Sie im Hilfethema für das [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="77b5e-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="77b5e-125">So erstellen Sie eine neue Archivierungsrichtlinie auf Standortebene</span><span class="sxs-lookup"><span data-stu-id="77b5e-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="77b5e-126">Mit diesem Befehl wird eine neue Archivierungsrichtlinie für den Standort „Redmond“ erstellt:</span><span class="sxs-lookup"><span data-stu-id="77b5e-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="77b5e-127">So erstellen Sie eine neue Archivierungsrichtlinie auf Benutzerebene</span><span class="sxs-lookup"><span data-stu-id="77b5e-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="77b5e-128">Um eine neue Archivierungsrichtlinie auf Benutzerebene zu erstellen, geben Sie beim Erstellen der Richtlinie einfach eine eindeutige ID an:</span><span class="sxs-lookup"><span data-stu-id="77b5e-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="77b5e-129">So erstellen Sie eine neue Archivierungsrichtlinie zum Aktivieren der Archivierung interner Kommunikationssitzungen</span><span class="sxs-lookup"><span data-stu-id="77b5e-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="77b5e-130">Da in den vorstehenden Befehlen (außer dem obligatorischen Identity-Parameter) keine Parameter angegeben wurden, werden die neuen Richtlinien die Standardwerte für alle ihre Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="77b5e-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="77b5e-131">Zur Erstellung von Richtlinien, die andere Werte verwenden, müssen Sie einfach enthalten Sie die entsprechenden Parameter und der Wert des Parameters.</span><span class="sxs-lookup"><span data-stu-id="77b5e-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="77b5e-132">Der folgende Befehl wird beispielsweise eine Archivierungsrichtlinie, die es ermöglicht die Archivierung der internen Sofortnachrichtensitzungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="77b5e-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="77b5e-133">So erstellen Sie eine neue Archivierungsrichtlinie zur Archivierung interner und externer Kommunikationssitzungen</span><span class="sxs-lookup"><span data-stu-id="77b5e-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="77b5e-p104">Mehrere Eigenschaftenwerte können durch Einschließen mehrerer Parameter geändert werden. Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie zum Archivieren interner und externer Chatsitzungen konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="77b5e-p104">Multiple property values can be modified by including multiple parameters. For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```