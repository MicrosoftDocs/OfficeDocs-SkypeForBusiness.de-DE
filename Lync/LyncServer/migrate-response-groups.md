---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="dba04-102">Migrieren von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="dba04-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dba04-103">_**Letztes Änderungsdatum des Themas:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="dba04-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="dba04-104">Nachdem die Benutzer in die lync Server 2013-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="dba04-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="dba04-105">Zum Migrieren von Reaktionsgruppen gehören das Kopieren von Agentengruppen, Warteschlangen, Workflows, Audiodateien und Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="dba04-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="dba04-106">Nachdem Sie Ihre Legacy Antwortgruppen migriert haben, werden die Anrufe an die Reaktionsgruppen von der Antwortgruppen Anwendung im lync Server 2013-Pool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="dba04-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="dba04-107">Anrufe an Reaktionsgruppen werden nicht mehr vom Legacy Pool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="dba04-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dba04-108">Obwohl Sie Antwortgruppen migrieren können, bevor Sie alle Benutzer in den lync Server 2013-Pool verschieben, empfiehlt es sich, zuerst alle Benutzer zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="dba04-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="dba04-109">Insbesondere haben Benutzer, die Reaktionsgruppen-Agents sind, nicht die vollständige Funktionalität der neuen Features, bis Sie in den lync Server 2013-Pool verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="dba04-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="dba04-110">Bevor Sie Antwortgruppen migrieren, müssen Sie einen lync Server 2013-Pool bereitgestellt haben, der die reaktionsgruppenanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="dba04-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="dba04-111">Die reaktionsgruppenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dba04-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="dba04-112">Sie können sicherstellen, dass die reaktionsgruppenanwendung installiert ist, indem Sie das Cmdlet " **Get-CsService – ApplicationServer** " ausführen.</span><span class="sxs-lookup"><span data-stu-id="dba04-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dba04-113">Sie können neue lync Server 2013-Antwortgruppen im lync Server 2013-Pool erstellen, bevor Sie Ihre Legacy Antwortgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="dba04-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="dba04-114">Führen Sie das Cmdlet **Move-CsRgsConfiguration** aus, um Reaktionsgruppen aus einem Legacy Pool auf den lync Server 2013 zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="dba04-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dba04-115">Mit dem Cmdlet "Migration der Reaktionsgruppe" wird die Reaktionsgruppen Konfiguration für den gesamten Pool verschoben.</span><span class="sxs-lookup"><span data-stu-id="dba04-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="dba04-116">Sie können keine bestimmten Gruppen, Warteschlangen oder Workflows auswählen, die migriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dba04-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="dba04-117">Nachdem Sie die Antwortgruppen migriert haben, müssen Sie die lync Server Control Panel-oder lync Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentengruppen,-Warteschlangen und-Workflows erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="dba04-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="dba04-118">Wenn Sie Antwortgruppen migrieren, werden die lync Server 2010-Antwortgruppen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="dba04-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="dba04-119">Wenn Sie Antwortgruppen nach der Migration mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell verwalten, werden sowohl die lync Server 2010-Antwortgruppen als auch die lync Server 2013-Reaktionsgruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dba04-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="dba04-120">Sie sollten Updates nur auf die lync Server 2013-Reaktionsgruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="dba04-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="dba04-121">Die lync Server 2010-Reaktionsgruppen werden nur für Rollback-Zwecke aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="dba04-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="dba04-122">Nachdem die Migration abgeschlossen und die neuen Reaktionsgruppen erstellt wurden, werden in der lync Server-Systemsteuerung und der lync Server-Verwaltungsshell die Versionen lync Server 2010 und lync Server 2013 jeder Reaktionsgruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dba04-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="dba04-123">Verwenden Sie die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell nicht, um die lync Server 2010-Reaktionsgruppen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="dba04-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="dba04-124">Wenn Sie eine entfernen, wird die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="dba04-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="dba04-125">Die lync Server 2010-Reaktionsgruppen werden entfernt, wenn Sie den lync Server 2010-Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="dba04-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dba04-126">Wir empfehlen, dass Sie keine Daten aus Ihrer vorherigen Bereitstellung entfernen, bevor Sie den Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="dba04-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="dba04-127">Darüber hinaus wird dringend empfohlen, dass Sie Reaktionsgruppen unmittelbar nach der Migration exportieren.</span><span class="sxs-lookup"><span data-stu-id="dba04-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="dba04-128">Wenn eine lync Server 2010-Reaktionsgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, damit die lync Server 2013-Reaktionsgruppen erneut ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="dba04-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="dba04-129">Lync Server 2013 führt ein neues Reaktionsgruppen Feature namens **Workflowtyp**ein.</span><span class="sxs-lookup"><span data-stu-id="dba04-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="dba04-130">Der **Workflowtyp** kann **verwaltet** oder **nicht verwaltet**werden.</span><span class="sxs-lookup"><span data-stu-id="dba04-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="dba04-131">Alle Antwortgruppen werden migriert, wobei der **Workflowtyp** auf **nicht verwaltet** und mit einer leeren Manager Liste gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="dba04-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="dba04-132">Wenn Sie das Cmdlet **Move-CsRgsConfiguration** ausführen, verbleiben die Agentengruppen,-Warteschlangen,-Workflows und-Audiodateien im Legacy Pool für Rollback-Zwecke.</span><span class="sxs-lookup"><span data-stu-id="dba04-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="dba04-133">Wenn Sie jedoch einen Rollback zum Legacy Pool durchführen müssen, müssen Sie das Cmdlet **Move-CsApplicationEndpoint** ausführen, um die Kontaktobjekte wieder in den Legacy Pool zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="dba04-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="dba04-134">Das folgende Verfahren zum Migrieren von Reaktionsgruppen Konfigurationen setzt voraus, dass Sie über eine 1:1-Beziehung zwischen Ihren Legacy Pools und den lync Server 2013-Pools verfügen.</span><span class="sxs-lookup"><span data-stu-id="dba04-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="dba04-135">Wenn Sie beabsichtigen, Pools während ihrer Migration und Bereitstellung zu konsolidieren oder aufzuteilen, müssen Sie planen, welche Legacy Pool-Zuordnungen dem lync Server 2013-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="dba04-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="dba04-136">So migrieren Sie Reaktionsgruppen Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="dba04-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="dba04-137">Melden Sie sich bei dem Computer mit einem Konto an, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über entsprechende Administratorrechte und-Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="dba04-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="dba04-138">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="dba04-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dba04-139">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dba04-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="dba04-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dba04-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="dba04-141">Nachdem Sie Antwortgruppen und Agents in den lync Server 2013-Pool migriert haben, ist die URL, die Agents zum Anmelden und Abmelden verwenden, eine lync Server 2013-URL und steht im Menü **Extras** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="dba04-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="dba04-142">Erinnern Sie die Agents daran, alle Verweise wie Textmarken auf die neue URL zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="dba04-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="dba04-143">So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="dba04-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dba04-144">Melden Sie sich bei dem Computer mit einem Konto an, das Mitglied der RTCUniversalReadOnlyAdmins-Gruppe ist, oder wenn es sich um eine minimale Mitgliedschaft in der CsViewOnlyAdministrator-Rolle handelt.</span><span class="sxs-lookup"><span data-stu-id="dba04-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="dba04-145">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dba04-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dba04-146">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dba04-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dba04-147">Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.</span><span class="sxs-lookup"><span data-stu-id="dba04-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="dba04-148">Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dba04-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="dba04-149">Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dba04-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="dba04-150">Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentengruppen in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dba04-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="dba04-151">So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="dba04-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="dba04-152">Melden Sie sich bei dem Computer mit einem Konto an, das Mitglied der RTCUniversalReadOnlyAdmins-Gruppe ist, oder wenn es sich um eine minimale Mitgliedschaft in der CsViewOnlyAdministrator-Rolle handelt.</span><span class="sxs-lookup"><span data-stu-id="dba04-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="dba04-153">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="dba04-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="dba04-154">Ausführliche Informationen zu den folgenden Cmdlets finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="dba04-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="dba04-155">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dba04-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="dba04-156">Überprüfen Sie, ob alle Agentengruppen in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dba04-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="dba04-157">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dba04-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="dba04-158">Überprüfen Sie, ob alle Warteschlangen in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dba04-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="dba04-159">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dba04-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="dba04-160">Überprüfen Sie, ob alle Workflows in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dba04-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

