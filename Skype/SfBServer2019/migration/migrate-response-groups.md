---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Zum Migrieren von Reaktionsgruppen gehören das Kopieren von Agentengruppen, Warteschlangen, Workflows, Audiodateien und Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den Skype for Business Server 2019-Pool. Nachdem Sie Ihre Legacy-Antwortgruppen migriert haben, werden die Anrufe an die Reaktionsgruppen von der Antwortgruppen Anwendung im Skype for Business Server 2019-Pool abgewickelt. Anrufe an Reaktionsgruppen werden nicht mehr vom Legacy Pool verarbeitet.
ms.openlocfilehash: b8d49205f4f54ca7c00a9aed0b6ac176c11cd617
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237970"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="88fe5-106">Migrieren von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="88fe5-106">Migrate response groups</span></span>

<span data-ttu-id="88fe5-107">Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="88fe5-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="88fe5-108">Zum Migrieren von Reaktionsgruppen gehören das Kopieren von Agentengruppen, Warteschlangen, Workflows, Audiodateien und Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den Skype for Business Server 2019-Pool.</span><span class="sxs-lookup"><span data-stu-id="88fe5-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="88fe5-109">Nachdem Sie Ihre Legacy-Antwortgruppen migriert haben, werden die Anrufe an die Reaktionsgruppen von der Antwortgruppen Anwendung im Skype for Business Server 2019-Pool abgewickelt.</span><span class="sxs-lookup"><span data-stu-id="88fe5-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="88fe5-110">Anrufe an Reaktionsgruppen werden nicht mehr vom Legacy Pool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="88fe5-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88fe5-111">Obwohl Sie Antwortgruppen migrieren können, bevor Sie alle Benutzer in den Skype for Business Server 2019-Pool verschieben, empfiehlt es sich, alle Benutzer zuerst zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="88fe5-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="88fe5-112">Insbesondere haben Benutzer, die Reaktionsgruppen-Agents sind, nicht die vollständige Funktionalität der neuen Features, bis Sie in den Skype for Business Server 2019-Pool verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="88fe5-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="88fe5-113">Bevor Sie Antwortgruppen migrieren, müssen Sie einen Skype for Business Server 2019-Pool bereitgestellt haben, der die reaktionsgruppenanwendung umfasst.</span><span class="sxs-lookup"><span data-stu-id="88fe5-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="88fe5-114">Die reaktionsgruppenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="88fe5-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="88fe5-115">Mit dem Cmdlet **Get-CsService-ApplicationServer** können Sie sicherstellen, dass die reaktionsgruppenanwendung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="88fe5-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="88fe5-116">Sie können neue Skype for Business Server 2019-Antwortgruppen im Skype for Business Server 2019-Pool erstellen, bevor Sie Ihre Legacy-Antwortgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="88fe5-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="88fe5-117">Führen Sie das Cmdlet **Move-CsRgsConfiguration** aus, um Reaktionsgruppen aus einem Legacy Pool in den Skype for Business Server 2019 zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="88fe5-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="88fe5-118">Mit dem Cmdlet "Migration der Reaktionsgruppe" wird die Reaktionsgruppen Konfiguration für den gesamten Pool verschoben.</span><span class="sxs-lookup"><span data-stu-id="88fe5-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="88fe5-119">Sie können keine bestimmten Gruppen, Warteschlangen oder Workflows auswählen, die migriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="88fe5-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="88fe5-120">Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie die Skype for Business Server Control Panel-oder Skype for Business Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentengruppen,-Warteschlangen und-Workflows erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="88fe5-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="88fe5-121">Wenn Sie Antwortgruppen migrieren, werden die Legacy Antwortgruppen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="88fe5-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="88fe5-122">Wenn Sie Antwortgruppen nach der Migration mithilfe der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell verwalten, können Sie sowohl die Legacy-Antwortgruppen als auch die Skype for Business Server 2019-Reaktionsgruppen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="88fe5-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="88fe5-123">Sie sollten Updates nur für die Skype for Business Server 2019-Reaktionsgruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="88fe5-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="88fe5-124">Die Legacy-Antwortgruppen werden nur für Rollback-Zwecke aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="88fe5-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="88fe5-125">Nachdem die Migration abgeschlossen und die neuen Reaktionsgruppen erstellt wurden, werden in der Skype for Business Server-Systemsteuerung und der Skype for Business Server-Verwaltungsshell die Legacy-und Skype for Business Server 2019-Versionen jeder Antwort angezeigt. Gruppe.</span><span class="sxs-lookup"><span data-stu-id="88fe5-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="88fe5-126">Verwenden Sie die Skype for Business Server Control Panel-oder Skype for Business Server-Verwaltungsshell nicht, um die Legacy-Antwortgruppen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="88fe5-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="88fe5-127">Wenn Sie eine entfernen, wird die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="88fe5-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="88fe5-128">Die Legacy-Antwortgruppen werden entfernt, wenn Sie den Legacy Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="88fe5-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="88fe5-129">Wir empfehlen, dass Sie keine Daten aus Ihrer vorherigen Bereitstellung entfernen, bevor Sie den Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="88fe5-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="88fe5-130">Darüber hinaus wird dringend empfohlen, dass Sie Reaktionsgruppen unmittelbar nach der Migration exportieren.</span><span class="sxs-lookup"><span data-stu-id="88fe5-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="88fe5-131">Wenn eine ältere Antwortgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, damit die Skype for Business Server 2019-Reaktionsgruppen erneut ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="88fe5-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="88fe5-132">Skype for Business Server 2019 führt eine neue Reaktionsgruppen Funktion mit \*\*\*\* dem Namen Workflowtyp ein.</span><span class="sxs-lookup"><span data-stu-id="88fe5-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="88fe5-133">\*\*\*\* Der Workflowtyp kann **verwaltet** oder **nicht verwaltet**werden.</span><span class="sxs-lookup"><span data-stu-id="88fe5-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="88fe5-134">Alle Antwortgruppen werden migriert, \*\*\*\* wobei der Workflowtyp auf **nicht verwaltet** und mit einer leeren Manager Liste gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="88fe5-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="88fe5-135">Wenn Sie das Cmdlet **Move-CsRgsConfiguration** ausführen, verbleiben die Agentengruppen,-Warteschlangen,-Workflows und-Audiodateien im Legacy Pool für Rollback-Zwecke.</span><span class="sxs-lookup"><span data-stu-id="88fe5-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="88fe5-136">Wenn Sie jedoch einen Rollback zum Legacy Pool durchführen müssen, müssen Sie das Cmdlet **Move-CsApplicationEndpoint** ausführen, um die Kontaktobjekte wieder in den Legacy Pool zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="88fe5-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="88fe5-137">Das folgende Verfahren zum Migrieren von Reaktionsgruppen Konfigurationen setzt voraus, dass Sie über eine 1:1-Beziehung zwischen Ihren Legacy Pools und den Skype for Business Server 2019-Pools verfügen.</span><span class="sxs-lookup"><span data-stu-id="88fe5-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="88fe5-138">Wenn Sie während der Migration und Bereitstellung Pools konsolidieren oder aufteilen möchten, müssen Sie die Karten für Legacy Pools planen, die dem Skype for Business Server 2019-Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="88fe5-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="88fe5-139">So migrieren Sie Reaktionsgruppen Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="88fe5-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="88fe5-140">Melden Sie sich bei dem Computer mit einem Konto an, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über entsprechende Administratorrechte und-Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="88fe5-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="88fe5-141">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="88fe5-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="88fe5-142">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="88fe5-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="88fe5-143">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88fe5-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="88fe5-144">Nachdem Sie Antwortgruppen und Agents in den Skype for Business Server 2019-Pool migriert haben, ist die URL, die die Agents zum Anmelden und Abmelden verwenden, eine Skype for Business Server 2019-URL und steht im Menü **Extras** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="88fe5-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="88fe5-145">Erinnern Sie die Agents daran, alle Verweise wie Textmarken auf die neue URL zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="88fe5-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="88fe5-146">So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="88fe5-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="88fe5-147">Melden Sie sich bei dem Computer mit einem Konto an, das Mitglied der RTCUniversalReadOnlyAdmins-Gruppe ist, oder wenn es sich um eine minimale Mitgliedschaft in der CsViewOnlyAdministrator-Rolle handelt.</span><span class="sxs-lookup"><span data-stu-id="88fe5-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="88fe5-148">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="88fe5-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="88fe5-149">Details zu den verschiedenen Methoden, die Sie zum Starten von Skype for Business Server Control Panel verwenden können, finden Sie unter [Öffnen von Skype for Business Server 2019-Verwaltungstools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="88fe5-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="88fe5-150">Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.</span><span class="sxs-lookup"><span data-stu-id="88fe5-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="88fe5-151">Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88fe5-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="88fe5-152">Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88fe5-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="88fe5-153">Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentengruppen in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88fe5-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="88fe5-154">So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="88fe5-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="88fe5-155">Melden Sie sich bei dem Computer mit einem Konto an, das Mitglied der RTCUniversalReadOnlyAdmins-Gruppe ist, oder wenn es sich um eine minimale Mitgliedschaft in der CsViewOnlyAdministrator-Rolle handelt.</span><span class="sxs-lookup"><span data-stu-id="88fe5-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="88fe5-156">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="88fe5-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="88fe5-157">Ausführliche Informationen zu den folgenden Cmdlets finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="88fe5-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="88fe5-158">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="88fe5-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="88fe5-159">Überprüfen Sie, ob alle Agentengruppen in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88fe5-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="88fe5-160">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="88fe5-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="88fe5-161">Überprüfen Sie, ob alle Warteschlangen in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88fe5-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="88fe5-162">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="88fe5-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="88fe5-163">Überprüfen Sie, ob alle Workflows in ihrer Legacyumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88fe5-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

