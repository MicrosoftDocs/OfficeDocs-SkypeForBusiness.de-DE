---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5433304af6d88ab6eb8a043bbff69b3718faee5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="88c64-102">Migrieren von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="88c64-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88c64-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="88c64-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="88c64-104">Nachdem die Benutzer in lync Server 2013 Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="88c64-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="88c64-105">Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows und Audiodateien sowie das Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="88c64-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="88c64-106">Nachdem Sie Ihre Legacy-Reaktionsgruppen migriert haben, werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im lync Server 2013-Pool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="88c64-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="88c64-107">Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="88c64-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88c64-108">Obwohl Sie Reaktionsgruppen migrieren können, bevor Sie alle Benutzer in den lync Server 2013 Pool verschieben, wird empfohlen, dass Sie zuerst alle Benutzer verschieben.</span><span class="sxs-lookup"><span data-stu-id="88c64-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="88c64-109">Insbesondere Benutzer, die Reaktionsgruppen-Agents sind, verfügen erst dann über die vollständige Funktionalität der neuen Features, wenn Sie in den lync Server 2013 Pool verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="88c64-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="88c64-110">Bevor Sie Reaktionsgruppen migrieren, müssen Sie einen lync Server 2013-Pool bereitgestellt haben, der das Reaktionsgruppenanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="88c64-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="88c64-111">Das Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="88c64-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="88c64-112">Sie können sicherstellen, dass der Reaktionsgruppenanwendung durch Ausführen des Cmdlets **Get-CsService – ApplicationServer** installiert wird.</span><span class="sxs-lookup"><span data-stu-id="88c64-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88c64-113">Sie können neue lync Server 2013 Reaktionsgruppen im lync Server 2013-Pool erstellen, bevor Sie Ihre Vorgänger Reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="88c64-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="88c64-114">Um Reaktionsgruppen aus einem Legacy Pool in die lync Server 2013 zu migrieren, führen Sie das Cmdlet " **verschieben-CsRgsConfiguration** " aus.</span><span class="sxs-lookup"><span data-stu-id="88c64-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="88c64-115">Bevor Sie **Move-CsRgsConfiguration** ausführen können, müssen Sie zunächst noch das Schnittstellenpaket für die Abwärtskompatibilität mit Windows Management Instrumentation (WMI) installieren.</span><span class="sxs-lookup"><span data-stu-id="88c64-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="88c64-116">Führen Sie dazu die Datei "OCSWMIBC.msi" aus.</span><span class="sxs-lookup"><span data-stu-id="88c64-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="88c64-117">Sie finden diese Datei auf dem Installationsdatenträger im Ordner "Setup".</span><span class="sxs-lookup"><span data-stu-id="88c64-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="88c64-118">Das Cmdlet für die Reaktionsgruppen Migration verschiebt die Reaktionsgruppen Konfiguration für den gesamten Pool.</span><span class="sxs-lookup"><span data-stu-id="88c64-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="88c64-119">Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="88c64-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="88c64-120">Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie die URL aktualisieren, mit der formelle Agents sich bei ihren Reaktionsgruppen an-und abmelden, und lync Server-Systemsteuerung-oder lync Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentgruppen, Warteschlangen und Workflows verschoben wurden. erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="88c64-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="88c64-121">Wenn Sie Reaktionsgruppen migrieren, werden die Office Communications Server 2007 R2 Reaktionsgruppen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="88c64-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="88c64-122">Entfernen Sie Office Communications Server 2007 R2 Reaktionsgruppen nicht.</span><span class="sxs-lookup"><span data-stu-id="88c64-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="88c64-123">Wenn Sie eine Office Communications Server 2007 R2 Reaktionsgruppe entfernen, werden die Reaktionsgruppen in lync Server 2013 nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="88c64-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="88c64-124">Warten Sie mit dem Entfernen von Daten aus früheren Bereitstellungen, bis Sie den Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="88c64-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="88c64-125">Darüber hinaus wird dringend empfohlen, die Reaktionsgruppen unmittelbar nach der Migration zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="88c64-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="88c64-126">Wenn eine Office Communications Server 2007 R2 Reaktionsgruppe entfernt wird, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, um wieder lync Server 2013 Reaktionsgruppen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="88c64-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="88c64-127">Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, verbleiben die Agentgruppen, Warteschlangen, Workflows und Audiodateien für mögliche Rollbacks im Vorversionspool.</span><span class="sxs-lookup"><span data-stu-id="88c64-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="88c64-128">Wenn Sie jedoch keinen Rollback zum Vorversionspool durchführen müssen, müssen Sie das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte wieder in den Vorversionspool zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="88c64-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="88c64-129">Warten Sie mit dem Löschen von Reaktionsgruppen aus dem Vorversionspool, bis Sie den Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="88c64-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="88c64-130">Bei dem Verfahren, das für die Migration von Reaktionsgruppen Konfigurationen befolgt wird, wird davon ausgegangen, dass Sie eine 1:1-Beziehung zwischen Ihren Legacy Pools und den lync Server 2013 Pools haben.</span><span class="sxs-lookup"><span data-stu-id="88c64-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="88c64-131">Wenn Sie während der Migration und Bereitstellung Pools konsolidieren oder aufteilen möchten, müssen Sie planen, welche Legacy-Pool-Karten lync Server 2013 Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="88c64-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="88c64-132">So migrieren Sie Reaktionsgruppen Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="88c64-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="88c64-133">Suchen Sie auf dem Installationsdatenträger die Datei "OCSWMIBC.msi" im Ordner "SetupW", und führen Sie den Installationsvorgang mit der Datei durch.</span><span class="sxs-lookup"><span data-stu-id="88c64-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="88c64-134">Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="88c64-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="88c64-135">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="88c64-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="88c64-136">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="88c64-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="88c64-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88c64-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="88c64-138">Wenn Sie die Registerkarte Reaktionsgruppe für Microsoft Office Communicator 2007 R2 in Ihrer Office Communications Server 2007 R2 Umgebung bereitgestellt haben, entfernen Sie die Registerkarte aus der Datei Office Communicator 2007 R2 Tabs. Xml.</span><span class="sxs-lookup"><span data-stu-id="88c64-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88c64-139">Formelle Agents verwendeten die Reaktionsgruppen-Registerkarte zur Anmeldung an die entsprechenden Reaktionsgruppen, bevor sie Anrufe empfangen konnten.</span><span class="sxs-lookup"><span data-stu-id="88c64-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="88c64-140">Wenn Sie die Registerkarte Reaktionsgruppe bereitgestellt haben, haben Sie den Speicherort für die Datei Office Communicator 2007 R2 Tabs. XML ausgewählt, als Sie sie bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="88c64-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="88c64-141">Informieren Sie Benutzer über die aktualisierte URL, die Agents zur An- und Abmeldung bei ihren Reaktionsgruppen benötigen.</span><span class="sxs-lookup"><span data-stu-id="88c64-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88c64-142">Die URL ist in https://webpoolFQDN/RgsClients/Tab.aspxder Regel, wobei webpoolFQDN der vollqualifizierte Domänenname (FQDN) des webpools ist, der dem Pool zugeordnet ist, den Sie soeben zu lync Server 2013 migriert haben.</span><span class="sxs-lookup"><span data-stu-id="88c64-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88c64-143">Dieser Schritt ist nicht erforderlich, nachdem Benutzer auf lync 2013 aktualisiert haben, da die URL im Menü <STRONG>Extras</STRONG> in lync zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="88c64-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="88c64-144">So überprüfen Sie die Migration von Reaktionsgruppen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="88c64-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="88c64-145">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="88c64-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="88c64-146">Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.</span><span class="sxs-lookup"><span data-stu-id="88c64-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="88c64-147">Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88c64-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="88c64-148">Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88c64-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="88c64-149">Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentgruppen in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88c64-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="88c64-150">So überprüfen Sie die Migration von Reaktionsgruppen mit Cmdlets</span><span class="sxs-lookup"><span data-stu-id="88c64-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="88c64-151">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="88c64-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="88c64-152">Führen Sie Folgendes aus, um nähere Informationen zu den folgenden Cmdlets zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="88c64-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="88c64-153">Geben Sie den folgenden Befehl in der Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="88c64-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="88c64-154">Stellen Sie sicher, dass alle Agentengruppen in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88c64-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="88c64-155">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="88c64-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="88c64-156">Stellen Sie sicher, dass alle Warteschlangen in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88c64-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="88c64-157">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="88c64-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="88c64-158">Stellen Sie sicher, dass alle Workflows in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="88c64-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

