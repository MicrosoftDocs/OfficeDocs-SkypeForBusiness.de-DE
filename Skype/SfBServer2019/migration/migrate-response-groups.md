---
title: Migrieren von reaktionsgruppen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Ihre Benutzer in Skype für Business Server 2019 Pools verschoben werden, können Sie Ihre reaktionsgruppen migrieren. Migrieren von Antwort Gruppen enthält, agentgruppen, Warteschlangen, Workflows, Audiodateien kopieren und Verschieben von Kontaktobjekten Response Group aus der Bereitstellung der Vorversion in der Skype für Business Server 2019 Pool. Nach dem Migrieren von reaktionsgruppen von Vorversionen werden Anrufe an die reaktionsgruppen von der Anwendung "Reaktionsgruppe" in der Skype für Business Server 2019 Pool behandelt. Aufrufe von reaktionsgruppen werden nicht mehr vom vorversionspool behandelt.
ms.openlocfilehash: 89149210e8041fbc84834cec83e1c1fe13d0765c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372937"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="badaa-106">Migrieren von reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="badaa-106">Migrate response groups</span></span>

<span data-ttu-id="badaa-107">Nachdem Ihre Benutzer in Skype für Business Server 2019 Pools verschoben werden, können Sie Ihre reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="badaa-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="badaa-108">Migrieren von Antwort Gruppen enthält, agentgruppen, Warteschlangen, Workflows, Audiodateien kopieren und Verschieben von Kontaktobjekten Response Group aus der Bereitstellung der Vorversion in der Skype für Business Server 2019 Pool.</span><span class="sxs-lookup"><span data-stu-id="badaa-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="badaa-109">Nach dem Migrieren von reaktionsgruppen von Vorversionen werden Anrufe an die reaktionsgruppen von der Anwendung "Reaktionsgruppe" in der Skype für Business Server 2019 Pool behandelt.</span><span class="sxs-lookup"><span data-stu-id="badaa-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="badaa-110">Aufrufe von reaktionsgruppen werden nicht mehr vom vorversionspool behandelt.</span><span class="sxs-lookup"><span data-stu-id="badaa-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="badaa-111">Obwohl Sie reaktionsgruppen migrieren können, bevor Sie alle Benutzer in der Skype für Business Server 2019 Pool verschieben, wird empfohlen, zunächst alle Benutzer zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="badaa-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="badaa-112">Insbesondere haben Benutzer, die reaktionsgruppen-Agenten sind keinen vollen Funktionsumfang von neuen Features, bis sie an der Skype für Business Server 2019 Pool verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="badaa-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="badaa-113">Bevor Sie reaktionsgruppen migrieren, Sie müssen einen Skype für Business Server 2019 Pool bereitgestellt worden sein, die die Anwendung "Reaktionsgruppe" enthält.</span><span class="sxs-lookup"><span data-stu-id="badaa-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="badaa-114">Die Anwendung "Reaktionsgruppe" wird installiert, und bei der Bereitstellung von Enterprise-VoIP standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="badaa-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="badaa-115">Sie können sicherstellen, dass die Anwendung "Reaktionsgruppe" durch Ausführen des Cmdlets **Get-CsService-ApplicationServer** installiert ist.</span><span class="sxs-lookup"><span data-stu-id="badaa-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="badaa-116">Sie können neue Skype für reaktionsgruppen Business Server 2019 vor der Migration von reaktionsgruppen von Vorversionen in der Skype für Business Server 2019 Pool erstellen.</span><span class="sxs-lookup"><span data-stu-id="badaa-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="badaa-117">Um reaktionsgruppen aus einem vorversionspool zum der Skype für Business Server 2019 zu migrieren, führen Sie das Cmdlet **Move-CsRgsConfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="badaa-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="badaa-118">Das Cmdlet "Migration" Reaktionsgruppe "" wird die reaktionsgruppenkonfiguration für den gesamten Pool verschoben.</span><span class="sxs-lookup"><span data-stu-id="badaa-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="badaa-119">Sie können keine bestimmte Gruppen, Warteschlangen oder Workflows zum Migrieren auswählen.</span><span class="sxs-lookup"><span data-stu-id="badaa-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="badaa-120">Nach der Migration der reaktionsgruppen müssen Sie Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell-Cmdlets verwenden, um sicherzustellen, dass alle agentgruppen, Warteschlangen und Workflows erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="badaa-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="badaa-121">Beim Migrieren von reaktionsgruppen werden die Vorversion reaktionsgruppen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="badaa-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="badaa-122">Wenn Sie reaktionsgruppen nach der Migration mit entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell verwalten, können Sie die Vorversion reaktionsgruppen und die Skype für reaktionsgruppen Business Server 2019 sehen.</span><span class="sxs-lookup"><span data-stu-id="badaa-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="badaa-123">Sie sollten nur für die Skype für reaktionsgruppen Business Server 2019 Updates anwenden.</span><span class="sxs-lookup"><span data-stu-id="badaa-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="badaa-124">Die Vorversion reaktionsgruppen werden nur für Wiederherstellungszwecke beibehalten.</span><span class="sxs-lookup"><span data-stu-id="badaa-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="badaa-125">Nach die Migration abgeschlossen wurde und die neue reaktionsgruppen erstellt wurden, der Skype Business Server-Systemsteuerung und die Skype für Business Server-Verwaltungsshell zeigt der Vorgängerversion und Skype für Business Server 2019 Versionen von Antwort Mitglied der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="badaa-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="badaa-126">Verwenden Sie die Skype nicht für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell, um die Vorversion reaktionsgruppen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="badaa-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="badaa-127">Wenn Sie eine entfernen, wird die entsprechende Antwort-Gruppe, die während der Migration erstellt wurde arbeiten beendet.</span><span class="sxs-lookup"><span data-stu-id="badaa-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="badaa-128">Legacy reaktionsgruppen werden entfernt, wenn Sie Pool den Vorgängerversion außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="badaa-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="badaa-129">Es wird empfohlen, dass Sie keine Daten aus der ursprünglichen Bereitstellung entfernen, bis Sie den Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="badaa-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="badaa-130">Darüber hinaus wird dringend empfohlen, unmittelbar nach dem Migrieren von reaktionsgruppen zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="badaa-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="badaa-131">Wenn eine ältere reaktionsgruppe entfernt erhalten möchten sollte, können Sie aus der Sicherung zum Abrufen von Skype für Business Server 2019 reaktionsgruppen erneut ausführen Ihrer reaktionsgruppen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="badaa-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="badaa-132">Skype für Business Server 2019 führt eine neue Reaktionsgruppe-Funktion, die **Für den Workflow**aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="badaa-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="badaa-133">**Workflowtyp** können **verwaltete** oder **nicht verwaltet**werden.</span><span class="sxs-lookup"><span data-stu-id="badaa-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="badaa-134">Alle reaktionsgruppen werden mit **Workflowtyp** **nicht verwaltet** festgelegt und eine leere managerliste migriert.</span><span class="sxs-lookup"><span data-stu-id="badaa-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="badaa-135">Wenn Sie das **Move-CsRgsConfiguration** -Cmdlet ausführen, bleiben die agentgruppen, Warteschlangen, Workflows und Audiodateien in den Pool der Vorgängerversion für Wiederherstellungszwecke.</span><span class="sxs-lookup"><span data-stu-id="badaa-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="badaa-136">Wenn Sie einen Rollback zu Pool der Vorgängerversion benötigen, müssen Sie jedoch mit dem Cmdlet **Move-CsApplicationEndpoint** zum Verschieben von Kontaktobjekten wieder in Pool der Vorgängerversion ausführen.</span><span class="sxs-lookup"><span data-stu-id="badaa-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="badaa-137">Migrieren von Reaktionsgruppen Konfigurationen im folgende Verfahren wird davon ausgegangen, dass Sie eine 1: 1-Beziehung zwischen Pools der Vorversion und die Skype für Business Server 2019 Pools verfügen.</span><span class="sxs-lookup"><span data-stu-id="badaa-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="badaa-138">Wenn Sie beabsichtigen, konsolidieren oder Pools während der Migration und Bereitstellung aufgeteilt, müssen Sie planen, welche Skype für Business Server 2019 Pool welchen legacy-Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="badaa-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="badaa-139">So migrieren Sie Reaktionsgruppen-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="badaa-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="badaa-140">Melden Sie sich an dem Computer mit einem Konto an, das Mitglied der Gruppe RTCUniversalServerAdmins oder über entsprechende Administratorrechte und-Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="badaa-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="badaa-141">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="badaa-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="badaa-142">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="badaa-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="badaa-143">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="badaa-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="badaa-144">Nach dem Migrieren der reaktionsgruppen und Agents zu den Skype für Business Server 2019 Pool, die URL, die Agents an-und Abmelden verwenden einen Skype für Business Server 2019 URL und steht im Menü **Extras** .</span><span class="sxs-lookup"><span data-stu-id="badaa-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="badaa-145">Erinnern Sie Agents alle Verweise, wie Lesezeichen, in die neue URL zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="badaa-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="badaa-146">So überprüfen Sie die reaktionsgruppenmigration mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="badaa-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="badaa-147">Melden Sie sich an dem Computer mit einem Konto an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.</span><span class="sxs-lookup"><span data-stu-id="badaa-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="badaa-148">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="badaa-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="badaa-149">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von Skype Business Server-Systemsteuerung verwenden können, finden Sie unter [Open Skype für Business Server 2019 Verwaltungstools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="badaa-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="badaa-150">Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.</span><span class="sxs-lookup"><span data-stu-id="badaa-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="badaa-151">Stellen Sie sicher, dass alle Workflows in der vorgängerumgebung in der Liste enthalten sind, klicken Sie auf der Registerkarte **Workflow** .</span><span class="sxs-lookup"><span data-stu-id="badaa-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="badaa-152">Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in der vorgängerumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="badaa-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="badaa-153">Klicken Sie auf der Registerkarte **Gruppe** , und stellen Sie sicher, dass alle agentgruppen in Ihrer legacy-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="badaa-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="badaa-154">So überprüfen Sie die reaktionsgruppenmigration mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="badaa-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="badaa-155">Melden Sie sich an dem Computer mit einem Konto an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.</span><span class="sxs-lookup"><span data-stu-id="badaa-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="badaa-156">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="badaa-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="badaa-157">Ausführliche Informationen zu den folgenden Cmdlets führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="badaa-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="badaa-158">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="badaa-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="badaa-159">Stellen Sie sicher, dass alle agentgruppen in Ihrer legacy-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="badaa-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="badaa-160">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="badaa-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="badaa-161">Stellen Sie sicher, dass alle Warteschlangen in der vorgängerumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="badaa-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="badaa-162">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="badaa-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="badaa-163">Stellen Sie sicher, dass alle Workflows in der vorgängerumgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="badaa-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

