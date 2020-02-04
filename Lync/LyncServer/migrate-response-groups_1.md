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
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="8eeb2-102">Migrieren von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="8eeb2-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8eeb2-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8eeb2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8eeb2-104">Nachdem die Benutzer in die lync Server 2013-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="8eeb2-105">Zum Migrieren von Reaktionsgruppen gehören das Kopieren von Agentengruppen, Warteschlangen, Workflows und Audiodateien sowie das Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="8eeb2-106">Nachdem Sie Ihre Legacy Antwortgruppen migriert haben, werden die Anrufe an die Reaktionsgruppen von der Antwortgruppen Anwendung im lync Server 2013-Pool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="8eeb2-107">Anrufe an Reaktionsgruppen werden nicht mehr vom Legacy Pool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8eeb2-108">Obwohl Sie Antwortgruppen migrieren können, bevor Sie alle Benutzer in den lync Server 2013-Pool verschieben, empfiehlt es sich, zuerst alle Benutzer zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="8eeb2-109">Insbesondere haben Benutzer, die Reaktionsgruppen-Agents sind, nicht die vollständige Funktionalität der neuen Features, bis Sie in den lync Server 2013-Pool verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="8eeb2-110">Bevor Sie Antwortgruppen migrieren, müssen Sie einen lync Server 2013-Pool bereitgestellt haben, der die reaktionsgruppenanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="8eeb2-111">Die reaktionsgruppenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="8eeb2-112">Sie können sicherstellen, dass die reaktionsgruppenanwendung installiert ist, indem Sie das Cmdlet " **Get-CsService – ApplicationServer** " ausführen.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8eeb2-113">Sie können neue lync Server 2013-Antwortgruppen im lync Server 2013-Pool erstellen, bevor Sie Ihre Legacy Antwortgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="8eeb2-114">Führen Sie das Cmdlet **Move-CsRgsConfiguration** aus, um Reaktionsgruppen aus einem Legacy Pool auf den lync Server 2013 zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="8eeb2-115">Bevor Sie **Move-CsRgsConfiguration**ausführen können, müssen Sie zuerst das Windows-Verwaltungs Instrumentations Paket (WMI)-abwärts Kompatibilitäts Schnittstellen installieren.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="8eeb2-116">Installieren Sie diese Anwendung, indem Sie OCSWMIBC. msi ausführen.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="8eeb2-117">Sie können OCSWMIBC. msi auf dem Installationsmedium im Setup-Ordner finden.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8eeb2-118">Mit dem Cmdlet "Migration der Reaktionsgruppe" wird die Reaktionsgruppen Konfiguration für den gesamten Pool verschoben.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="8eeb2-119">Sie können keine bestimmten Gruppen, Warteschlangen oder Workflows auswählen, die migriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="8eeb2-120">Nachdem Sie die Antwortgruppen migriert haben, müssen Sie die URL aktualisieren, mit der sich die formellen Agents bei ihren Antwortgruppen an-und abmelden und die lync Server Control Panel-oder lync Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentengruppen,-Warteschlangen und-Workflows verschoben wurden. erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8eeb2-121">Wenn Sie Antwortgruppen migrieren, werden die Office Communications Server 2007 R2-Antwortgruppen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="8eeb2-122">Entfernen Sie keine Office Communications Server 2007 R2-Antwortgruppen.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="8eeb2-123">Wenn Sie eine Office Communications Server 2007 R2-Reaktionsgruppe entfernen, funktionieren die Antwortgruppen in lync Server 2013 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8eeb2-124">Wir empfehlen, dass Sie keine Daten aus Ihrer vorherigen Bereitstellung entfernen, bevor Sie den Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="8eeb2-125">Darüber hinaus wird dringend empfohlen, dass Sie Reaktionsgruppen unmittelbar nach der Migration exportieren.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="8eeb2-126">Wenn eine Office Communications Server 2007 R2-Reaktionsgruppe entfernt wird, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, damit die lync Server 2013-Reaktionsgruppen erneut ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="8eeb2-127">Wenn Sie das Cmdlet **Move-CsRgsConfiguration** ausführen, verbleiben die Agentengruppen,-Warteschlangen,-Workflows und-Audiodateien im Legacy Pool für Rollback-Zwecke.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="8eeb2-128">Wenn Sie jedoch einen Rollback zum Legacy Pool durchführen müssen, müssen Sie das Cmdlet **Move-CsApplicationEndpoint** ausführen, um die Kontaktobjekte wieder in den Legacy Pool zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8eeb2-129">Wir empfehlen, dass Sie keine Antwortgruppen Daten aus dem Legacy Pool löschen, bis Sie den Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="8eeb2-130">Bei der folgenden Vorgehensweise für die Migration von Reaktionsgruppen Konfigurationen wird davon ausgegangen, dass Sie über eine 1:1-Beziehung zwischen Ihren Legacy Pools und den lync Server 2013-Pools verfügen.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="8eeb2-131">Wenn Sie beabsichtigen, Pools während ihrer Migration und Bereitstellung zu konsolidieren oder aufzuteilen, müssen Sie planen, welche Legacy Pool-Zuordnungen dem lync Server 2013-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="8eeb2-132">So migrieren Sie Reaktionsgruppen Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="8eeb2-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="8eeb2-133">Suchen Sie OCSWMIBC. msi im Setup-Ordner des Installationsmediums, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="8eeb2-134">Melden Sie sich bei dem Computer mit einem Konto an, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über entsprechende Administratorrechte und-Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="8eeb2-135">Öffnen Sie die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="8eeb2-136">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8eeb2-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="8eeb2-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8eeb2-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="8eeb2-138">Wenn Sie die Registerkarte Reaktionsgruppe für Microsoft Office Communicator 2007 R2 in Ihrer Office Communications Server 2007 R2-Umgebung bereitgestellt haben, entfernen Sie die Registerkarte aus der Office Communicator 2007 R2-Datei "Tabs. xml".</span><span class="sxs-lookup"><span data-stu-id="8eeb2-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8eeb2-139">Formale Agents verwendeten die Registerkarte Reaktionsgruppe, um sich bei ihren Reaktionsgruppen anzumeldeten, bevor Sie Anrufe empfangen konnten.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="8eeb2-140">Wenn Sie die Registerkarte Reaktionsgruppe bereitgestellt haben, haben Sie beim Bereitstellen den Speicherort für die Office Communicator 2007 R2-Datei "Tabs. xml" ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="8eeb2-141">Stellen Sie den Benutzern die aktualisierte URL zur Verfügung, die die Agents bei ihren Antwortgruppen anmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8eeb2-142">Die URL ist in https://webpoolFQDN/RgsClients/Tab.aspxder Regel, wobei webpoolFQDN der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des webpools ist, der dem Pool zugeordnet ist, der gerade zu lync Server 2013 migriert wurde.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8eeb2-143">Dieser Schritt ist nicht erforderlich, nachdem Benutzer auf lync 2013 aktualisiert haben, da die URL über das Menü <STRONG>Extras</STRONG> in lync zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="8eeb2-144">So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="8eeb2-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8eeb2-145">Öffnen Sie die lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="8eeb2-146">Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="8eeb2-147">Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="8eeb2-148">Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="8eeb2-149">Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentengruppen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="8eeb2-150">So überprüfen Sie die Migration der Reaktionsgruppe mithilfe von Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8eeb2-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="8eeb2-151">Öffnen Sie die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="8eeb2-152">Ausführliche Informationen zu den folgenden Cmdlets finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="8eeb2-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="8eeb2-153">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8eeb2-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="8eeb2-154">Überprüfen Sie, ob alle Agentengruppen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="8eeb2-155">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8eeb2-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="8eeb2-156">Überprüfen Sie, ob alle Warteschlangen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="8eeb2-157">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8eeb2-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="8eeb2-158">Überprüfen Sie, ob alle Workflows in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8eeb2-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

