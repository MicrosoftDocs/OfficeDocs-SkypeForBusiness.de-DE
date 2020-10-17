---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b51fd9bd16da2f6cf135332d68c70c4b4714cdd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527502"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="f01fc-102">Migrieren von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="f01fc-102">Migrate response groups</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f01fc-103">_**Letztes Änderungsstand des Themas:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="f01fc-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="f01fc-104">Nachdem die Benutzer in lync Server 2013 Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="f01fc-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="f01fc-105">Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows, Audiodateien und Kontaktobjekten der verschobenen Reaktionsgruppe aus der Legacy Bereitstellung in den lync Server 2013 Pool.</span><span class="sxs-lookup"><span data-stu-id="f01fc-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="f01fc-106">Nachdem Sie Ihre Legacy-Reaktionsgruppen migriert haben, werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im lync Server 2013-Pool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f01fc-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="f01fc-107">Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f01fc-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f01fc-108">Obwohl Sie Reaktionsgruppen migrieren können, bevor Sie alle Benutzer in den lync Server 2013 Pool verschieben, wird empfohlen, dass Sie zuerst alle Benutzer verschieben.</span><span class="sxs-lookup"><span data-stu-id="f01fc-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="f01fc-109">Insbesondere Benutzer, die Reaktionsgruppen-Agents sind, verfügen erst dann über die vollständige Funktionalität der neuen Features, wenn Sie in den lync Server 2013 Pool verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="f01fc-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="f01fc-110">Bevor Sie Reaktionsgruppen migrieren, müssen Sie einen lync Server 2013-Pool bereitgestellt haben, der das Reaktionsgruppenanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="f01fc-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="f01fc-111">Das Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f01fc-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f01fc-112">Sie können sicherstellen, dass der Reaktionsgruppenanwendung durch Ausführen des Cmdlets **Get-CsService – ApplicationServer** installiert wird.</span><span class="sxs-lookup"><span data-stu-id="f01fc-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f01fc-113">Sie können neue lync Server 2013 Reaktionsgruppen im lync Server 2013-Pool erstellen, bevor Sie Ihre Vorgänger Reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="f01fc-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="f01fc-114">Um Reaktionsgruppen aus einem Legacy Pool in die lync Server 2013 zu migrieren, führen Sie das Cmdlet " **verschieben-CsRgsConfiguration** " aus.</span><span class="sxs-lookup"><span data-stu-id="f01fc-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f01fc-115">Das Cmdlet für die Reaktionsgruppen Migration verschiebt die Reaktionsgruppen Konfiguration für den gesamten Pool.</span><span class="sxs-lookup"><span data-stu-id="f01fc-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="f01fc-116">Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="f01fc-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="f01fc-117">Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie lync Server-Systemsteuerung oder lync Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentgruppen, Warteschlangen und Workflows erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="f01fc-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="f01fc-118">Wenn Sie Reaktionsgruppen migrieren, werden die lync Server 2010 Reaktionsgruppen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="f01fc-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="f01fc-119">Wenn Sie Reaktionsgruppen nach der Migration mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell verwalten, können Sie sowohl die lync Server 2010 Reaktionsgruppen als auch die lync Server 2013 Reaktionsgruppen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f01fc-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="f01fc-120">Sie sollten Updates nur auf die lync Server 2013 Reaktionsgruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="f01fc-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="f01fc-121">Die lync Server 2010 Reaktionsgruppen werden nur für Rollback-Zwecke beibehalten.</span><span class="sxs-lookup"><span data-stu-id="f01fc-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f01fc-122">Nachdem die Migration abgeschlossen ist und die neuen Reaktionsgruppen erstellt wurden, werden im lync Server-Systemsteuerung und im lync Server-Verwaltungsshell die lync Server 2010 und lync Server 2013 Versionen der einzelnen Reaktionsgruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f01fc-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="f01fc-123">Verwenden Sie nicht lync Server-Systemsteuerung oder lync Server-Verwaltungsshell, um die lync Server 2010 Reaktionsgruppen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f01fc-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="f01fc-124">Wenn Sie eine entfernen, wird die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f01fc-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="f01fc-125">Die lync Server 2010 Reaktionsgruppen werden entfernt, wenn Sie den lync Server 2010 Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="f01fc-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f01fc-126">Warten Sie mit dem Entfernen von Daten aus früheren Bereitstellungen, bis Sie den Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="f01fc-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="f01fc-127">Darüber hinaus wird dringend empfohlen, die Reaktionsgruppen unmittelbar nach der Migration zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="f01fc-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="f01fc-128">Wenn eine lync Server 2010 Reaktionsgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen dann aus der Sicherung wiederherstellen, damit lync Server 2013 Reaktionsgruppen erneut zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f01fc-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="f01fc-129">In lync Server 2013 wird ein neues Reaktionsgruppen Feature mit dem Namen **Workflowtyp**eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f01fc-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="f01fc-130">Der **Workflowtyp** kann **Verwaltet** oder **Nicht veraltet** sein.</span><span class="sxs-lookup"><span data-stu-id="f01fc-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="f01fc-131">Alle Reaktionsgruppen werden mit dem **Workflowtyp\*\*\*\*Nicht verwaltet** und mit leerer Manager-Liste migriert.</span><span class="sxs-lookup"><span data-stu-id="f01fc-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="f01fc-132">Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, bleiben die Agent-Gruppen, Warteschlangen, Workflows und Audiodateien zu Wiederherstellungszwecken im Vorversionspool.</span><span class="sxs-lookup"><span data-stu-id="f01fc-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="f01fc-133">Wenn Sie jedoch keinen Rollback zum Vorversionspool durchführen müssen, müssen Sie das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte wieder in den Vorversionspool zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="f01fc-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="f01fc-134">Das folgende Verfahren zum Migrieren von Reaktionsgruppen Konfigurationen setzt voraus, dass Sie eine 1:1-Beziehung zwischen Ihren Legacy Pools und den lync Server 2013 Pools haben.</span><span class="sxs-lookup"><span data-stu-id="f01fc-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="f01fc-135">Wenn Sie während der Migration und Bereitstellung Pools konsolidieren oder aufteilen möchten, müssen Sie planen, welche Legacy-Pool-Karten lync Server 2013 Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f01fc-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="f01fc-136">So migrieren Sie Reaktionsgruppen Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="f01fc-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="f01fc-137">Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe RTCUniversalServerAdmins ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="f01fc-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="f01fc-138">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f01fc-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f01fc-139">Ausführen</span><span class="sxs-lookup"><span data-stu-id="f01fc-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="f01fc-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f01fc-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="f01fc-141">Nachdem Sie Reaktionsgruppen und Agents in den lync Server 2013 Pool migriert haben, ist die URL, die Agents zur Anmeldung und Abmeldung verwenden, eine lync Server 2013-URL und steht im Menü **Extras** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f01fc-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="f01fc-142">Erinnern Sie Agents daran, sämtliche Referenzen, beispielsweise Lesezeichen, auf die neue URL zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f01fc-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="f01fc-143">So überprüfen Sie die Reaktionsgruppenmigration mithilfe der Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f01fc-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f01fc-144">Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist, am Computer an.</span><span class="sxs-lookup"><span data-stu-id="f01fc-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="f01fc-145">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f01fc-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f01fc-146">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f01fc-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f01fc-147">Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.</span><span class="sxs-lookup"><span data-stu-id="f01fc-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="f01fc-148">Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f01fc-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="f01fc-149">Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f01fc-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="f01fc-150">Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentgruppen in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f01fc-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="f01fc-151">So überprüfen Sie die Migration von Reaktionsgruppen mithilfe von lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="f01fc-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f01fc-152">Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.</span><span class="sxs-lookup"><span data-stu-id="f01fc-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="f01fc-153">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f01fc-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="f01fc-154">Führen Sie Folgendes aus, um nähere Informationen zu den folgenden Cmdlets zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="f01fc-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="f01fc-155">Ausführen</span><span class="sxs-lookup"><span data-stu-id="f01fc-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="f01fc-156">Stellen Sie sicher, dass alle Agentengruppen in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f01fc-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="f01fc-157">Ausführen</span><span class="sxs-lookup"><span data-stu-id="f01fc-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="f01fc-158">Stellen Sie sicher, dass alle Warteschlangen in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f01fc-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="f01fc-159">Ausführen</span><span class="sxs-lookup"><span data-stu-id="f01fc-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="f01fc-160">Stellen Sie sicher, dass alle Workflows in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f01fc-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

