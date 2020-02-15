---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows, Audiodateien und Kontaktobjekten der beweglichen Reaktionsgruppe aus der Legacy Bereitstellung in den Skype for Business Server 2019-Pool. Nachdem Sie Ihre Legacy-Reaktionsgruppen migriert haben, werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im Pool Skype for Business Server 2019 verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.
ms.openlocfilehash: 2d439462fa103cc16fd7ae70b79364be7d79803a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016106"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="d50ab-106">Migrieren von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="d50ab-106">Migrate response groups</span></span>

<span data-ttu-id="d50ab-107">Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="d50ab-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="d50ab-108">Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows, Audiodateien und Kontaktobjekten der beweglichen Reaktionsgruppe aus der Legacy Bereitstellung in den Skype for Business Server 2019-Pool.</span><span class="sxs-lookup"><span data-stu-id="d50ab-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d50ab-109">Nachdem Sie Ihre Legacy-Reaktionsgruppen migriert haben, werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im Pool Skype for Business Server 2019 verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d50ab-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d50ab-110">Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d50ab-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d50ab-111">Obwohl Sie Reaktionsgruppen migrieren können, bevor Sie alle Benutzer in den Pool Skype for Business Server 2019 verschieben, wird empfohlen, dass Sie zuerst alle Benutzer verschieben.</span><span class="sxs-lookup"><span data-stu-id="d50ab-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="d50ab-112">Insbesondere Benutzer, die Reaktionsgruppen-Agents sind, verfügen erst dann über die vollständige Funktionalität der neuen Features, wenn Sie in den Pool Skype for Business Server 2019 verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="d50ab-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="d50ab-113">Bevor Sie Reaktionsgruppen migrieren, müssen Sie einen Skype for Business Server 2019-Pool bereitgestellt haben, der das Reaktionsgruppenanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="d50ab-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="d50ab-114">Das Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d50ab-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="d50ab-115">Sie können sicherstellen, dass die Reaktionsgruppenanwendung installiert wird, indem Sie das Cmdlet **Get-CsService-ApplicationServer** ausführen.</span><span class="sxs-lookup"><span data-stu-id="d50ab-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d50ab-116">Sie können neue Skype for Business Server 2019-Reaktionsgruppen im Pool Skype for Business Server 2019 erstellen, bevor Sie Ihre Legacy-Reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="d50ab-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="d50ab-117">Um Reaktionsgruppen von einem Legacy Pool zu Skype for Business Server 2019 zu migrieren, führen Sie das Cmdlet " **verschieben-CsRgsConfiguration** " aus.</span><span class="sxs-lookup"><span data-stu-id="d50ab-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d50ab-118">Das Cmdlet für die Reaktionsgruppen Migration verschiebt die Reaktionsgruppen Konfiguration für den gesamten Pool.</span><span class="sxs-lookup"><span data-stu-id="d50ab-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="d50ab-119">Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="d50ab-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="d50ab-120">Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie Skype for Business Server Systemsteuerung oder Skype for Business Server Cmdlets der Verwaltungsshell verwenden, um zu überprüfen, ob alle Agentgruppen, Warteschlangen und Workflows erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="d50ab-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="d50ab-121">Wenn Sie Reaktionsgruppen migrieren, werden die Legacy-Reaktionsgruppen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="d50ab-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="d50ab-122">Wenn Sie Reaktionsgruppen nach der Migration mithilfe von Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell verwalten, können Sie sowohl die Legacy-Reaktionsgruppen als auch die Skype for Business Server 2019-Reaktionsgruppen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d50ab-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="d50ab-123">Sie sollten Updates nur auf die Skype for Business Server 2019-Reaktionsgruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="d50ab-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="d50ab-124">Die Legacy-Reaktionsgruppen werden nur für Rollback-Zwecke beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d50ab-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="d50ab-125">Nachdem die Migration abgeschlossen ist und die neuen Reaktionsgruppen erstellt wurden, werden in der Skype for Business Server-Systemsteuerung und in der Skype for Business Server-Verwaltungsshell die Versionen Legacy und Skype for Business Server 2019 der einzelnen Antworten angezeigt. Gruppe.</span><span class="sxs-lookup"><span data-stu-id="d50ab-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="d50ab-126">Verwenden Sie nicht Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell, um die Vorgänger Reaktionsgruppen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d50ab-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="d50ab-127">Wenn Sie eine entfernen, wird die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d50ab-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="d50ab-128">Die Legacy-Reaktionsgruppen werden entfernt, wenn Sie den Legacy Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="d50ab-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d50ab-129">Warten Sie mit dem Entfernen von Daten aus früheren Bereitstellungen, bis Sie den Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="d50ab-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="d50ab-130">Darüber hinaus wird dringend empfohlen, die Reaktionsgruppen unmittelbar nach der Migration zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="d50ab-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="d50ab-131">Wenn eine ältere Reaktionsgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, um wieder Skype for Business Server 2019-Reaktionsgruppen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d50ab-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="d50ab-132">In Skype for Business Server 2019 wird ein neues Reaktionsgruppen Feature mit dem Namen **Workflowtyp**eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d50ab-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="d50ab-133">Der **Workflowtyp** kann **Verwaltet** oder **Nicht veraltet** sein.</span><span class="sxs-lookup"><span data-stu-id="d50ab-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="d50ab-134">Alle Reaktionsgruppen werden mit dem **Workflowtyp\*\*\*\*Nicht verwaltet** und mit leerer Manager-Liste migriert.</span><span class="sxs-lookup"><span data-stu-id="d50ab-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="d50ab-135">Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, bleiben die Agent-Gruppen, Warteschlangen, Workflows und Audiodateien zu Wiederherstellungszwecken im Vorversionspool.</span><span class="sxs-lookup"><span data-stu-id="d50ab-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="d50ab-136">Wenn Sie jedoch keinen Rollback zum Vorversionspool durchführen müssen, müssen Sie das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte wieder in den Vorversionspool zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="d50ab-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="d50ab-137">Bei der folgenden Vorgehensweise für die Migration von Reaktionsgruppen Konfigurationen wird vorausgesetzt, dass Sie eine 1:1-Beziehung zwischen Ihren Legacy Pools und den Skype for Business Server 2019-Pools haben.</span><span class="sxs-lookup"><span data-stu-id="d50ab-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="d50ab-138">Wenn Sie während der Migration und Bereitstellung Pools konsolidieren oder aufteilen möchten, müssen Sie planen, welche Legacy-Poolkarten Skype for Business Server Pool 2019.</span><span class="sxs-lookup"><span data-stu-id="d50ab-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="d50ab-139">So migrieren Sie Reaktionsgruppen Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="d50ab-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="d50ab-140">Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe RTCUniversalServerAdmins ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="d50ab-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="d50ab-141">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d50ab-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d50ab-142">Ausführen</span><span class="sxs-lookup"><span data-stu-id="d50ab-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="d50ab-143">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d50ab-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="d50ab-144">Nachdem Sie Reaktionsgruppen und Agents in den Skype for Business Server 2019-Pool migriert haben, ist die URL, die Agents zur Anmeldung und Abmeldung verwenden, eine Skype for Business Server 2019-URL und steht im Menü **Extras** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d50ab-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="d50ab-145">Erinnern Sie Agents daran, sämtliche Referenzen, beispielsweise Lesezeichen, auf die neue URL zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d50ab-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d50ab-146">So überprüfen Sie die Migration von Reaktionsgruppen mithilfe Skype for Business Server Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d50ab-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d50ab-147">Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.</span><span class="sxs-lookup"><span data-stu-id="d50ab-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="d50ab-148">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d50ab-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d50ab-149">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von Skype for Business Server Systemsteuerung verwenden können, finden Sie unter [Open Skype for Business Server 2019 Administrative Tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="d50ab-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="d50ab-150">Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.</span><span class="sxs-lookup"><span data-stu-id="d50ab-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="d50ab-151">Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d50ab-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="d50ab-152">Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d50ab-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="d50ab-153">Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentgruppen in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d50ab-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d50ab-154">So überprüfen Sie die Migration von Reaktionsgruppen mithilfe von Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d50ab-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d50ab-155">Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.</span><span class="sxs-lookup"><span data-stu-id="d50ab-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="d50ab-156">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d50ab-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="d50ab-157">Führen Sie Folgendes aus, um nähere Informationen zu den folgenden Cmdlets zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="d50ab-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="d50ab-158">Ausführen</span><span class="sxs-lookup"><span data-stu-id="d50ab-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="d50ab-159">Stellen Sie sicher, dass alle Agentengruppen in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d50ab-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="d50ab-160">Ausführen</span><span class="sxs-lookup"><span data-stu-id="d50ab-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="d50ab-161">Stellen Sie sicher, dass alle Warteschlangen in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d50ab-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="d50ab-162">Ausführen</span><span class="sxs-lookup"><span data-stu-id="d50ab-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="d50ab-163">Stellen Sie sicher, dass alle Workflows in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d50ab-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

