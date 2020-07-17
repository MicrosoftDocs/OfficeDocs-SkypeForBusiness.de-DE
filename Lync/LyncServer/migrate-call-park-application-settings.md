---
title: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2789a8a83c8f3ee831fb91c85999d936ea54dd8b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="84c2b-102">Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="84c2b-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84c2b-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="84c2b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="84c2b-104">Die Migration der Anwendung zum Parken von Anrufen von lync Server 2010 zu lync Server 2013 umfasst die Bereitstellung des lync Server 2013 Pools mit beliebigen benutzerdefinierten Musikdateien, die in lync Server 2010 hochgeladen wurden, wobei die Einstellungen für den Service Level wiederhergestellt und alle Orbits für das Parken von Anrufen an den lync Server 2013 Pool umgeplant werden.</span><span class="sxs-lookup"><span data-stu-id="84c2b-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="84c2b-105">Wenn benutzerdefinierte Musikdateien im lync Server 2010 Pool konfiguriert wurden, müssen diese Dateien in den neuen lync Server 2013-Pool kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="84c2b-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="84c2b-106">Darüber hinaus wird empfohlen, dass Sie alle benutzerdefinierten Music-on-Hold-Dateien vom lync Server 2010 auf ein anderes Ziel sichern, um eine separate Sicherungskopie aller benutzerdefinierten Musikarchiv Dateien zu behalten, die für das Parken von Anrufen hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="84c2b-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="84c2b-107">Die angepassten Music-on-Hold-Dateien für die Anwendung zum Parken von Anrufen werden im Dateispeicher des Pools gespeichert.</span><span class="sxs-lookup"><span data-stu-id="84c2b-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="84c2b-108">Wenn Sie die Audiodateien aus einem lync Server 2010 Pool-Dateispeicher in einen lync Server 2013 Dateispeicher kopieren möchten, verwenden Sie den Befehl **xcopy** mit den folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="84c2b-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="84c2b-109">Wenn alle angepassten Audiodateien in den lync Server 2013 Dateispeicher kopiert wurden, müssen die Anwendung zum Parken von Anrufen Einstellungen des lync Server 2013 Pools konfiguriert werden, und die dem lync Server 2010 Pool zugeordneten orbitbereiche zum Parken von anrufen müssen dem lync Server 2013 Pool neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="84c2b-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="84c2b-110">Zu den Einstellungen der Anwendung zum Parken von Anrufen gehören die Auswahl des Timeoutschwellenwerts für die Anrufannahme, das Aktivieren oder Deaktivieren der Wartemusik, die maximale Anzahl von Versuchen der Anrufannahme und die Timeoutanforderung.</span><span class="sxs-lookup"><span data-stu-id="84c2b-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="84c2b-111">Sie müssen Anwendung zum Parken von Anrufen Einstellungen verwalten, indem Sie das Cmdlet " **CsCpsConfiguration** " mithilfe der lync Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="84c2b-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="84c2b-112">Die Anwendung zum Parken von Anrufen Einstellungen können nicht mithilfe der lync Server-Systemsteuerung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="84c2b-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="84c2b-113">**Erneutes Konfigurieren der Einstellungen für den Dienst zum Parken von Anrufen**</span><span class="sxs-lookup"><span data-stu-id="84c2b-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="84c2b-114">Öffnen Sie im lync Server 2013 Front-End-Server die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="84c2b-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="84c2b-115">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="84c2b-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84c2b-116">Wenn Ihre lync Server 2013 Anwendung zum Parken von Anrufen Einstellungen mit den lync Server 2010 Einstellungen für Legacy identisch sind, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="84c2b-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="84c2b-117">Wenn Anwendung zum Parken von Anrufen Einstellungen für die lync Server 2013-und lync Server 2010-Umgebungen unterschiedlich sind, verwenden Sie das unten aufgeführte Cmdlet als Vorlage, um diese Änderungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84c2b-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="84c2b-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-" enablemusiconhold "" <LS2010 CPS value> "-" maxcallpickupattempts "" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> "```</span><span class="sxs-lookup"><span data-stu-id="84c2b-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="84c2b-119">Um alle orbitbereiche für das Parken von Anrufen von lync Server 2010 Pool zum lync Server 2013-Pool neu zuzuweisen, können Sie entweder den lync Server-Systemsteuerung oder den lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="84c2b-119">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="84c2b-120">**Neuzuordnen aller Bereiche für den Anrufparkorbit mit der Lync Server-Systemsteuerung**</span><span class="sxs-lookup"><span data-stu-id="84c2b-120">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="84c2b-121">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="84c2b-121">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="84c2b-122">Wählen Sie im linken Bereich **VoIP-Funktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="84c2b-122">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="84c2b-123">Wählen Sie die Registerkarte **Parken von Anrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="84c2b-123">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="84c2b-124">Bearbeiten Sie für jeden orbitbereich für das Parken von anrufen, der einem lync Server 2010 Pool zugewiesen ist, die Einstellung **FQDN des Zielservers** , und wählen Sie den lync Server 2013 Pool aus, in dem die Anforderungen für das Parken von Anrufen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="84c2b-124">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="84c2b-125">Klicken Sie auf **Commit ausführen**, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="84c2b-125">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="84c2b-126">**Neuzuordnen aller Bereiche für den Anrufparkorbit mit der Lync Server-Verwaltungsshell**</span><span class="sxs-lookup"><span data-stu-id="84c2b-126">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="84c2b-127">Öffnen Sie lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="84c2b-127">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="84c2b-128">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="84c2b-128">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="84c2b-129">Dieses Cmdlet listet alle Bereiche für den Anrufparkorbit in der Bereitstellung auf.</span><span class="sxs-lookup"><span data-stu-id="84c2b-129">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="84c2b-130">Alle Orbits für das Parken von anrufen, bei denen die Parameter **CallParkServiceId** und **CallParkServerFqdn** als lync Server 2010 Pool festgelegt sind, müssen neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="84c2b-130">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="84c2b-131">Geben Sie an der Befehlszeile Folgendes ein, um die lync Server 2010 orbitbereiche für das Parken von Anrufen dem lync Server 2013-Pool zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="84c2b-131">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="84c2b-132">Nachdem Sie alle orbitbereiche für das Parken von Anrufen an den lync Server 2013 Pool neu zugewiesen haben, wird der Migrationsprozess für die Anwendung zum Parken von Anrufen abgeschlossen, und der lync Server 2013 Pool verarbeitet alle zukünftigen Anforderungen für das Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="84c2b-132">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

