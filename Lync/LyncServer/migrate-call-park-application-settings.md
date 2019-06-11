---
title: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f01429a85b679ae5d3710585db84c17e6e64e34b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="c5d48-102">Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="c5d48-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5d48-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c5d48-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c5d48-104">Die Migration der Anruf Park Anwendung von lync Server 2010 zu lync Server 2013 umfasst die Bereitstellung des lync Server 2013-Pools mit beliebigen benutzerdefinierten Musikdateien, die in lync Server 2010 hochgeladen wurden, die Einstellungen für den Service Level wiederherstellen und eine erneute Zielausrichtung durchführen. alle Anruf parken umkreist den lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="c5d48-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c5d48-105">Wenn benutzerdefinierte Music-on-halten-Dateien im lync Server 2010-Pool konfiguriert wurden, müssen diese Dateien in den neuen lync Server 2013-Pool kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="c5d48-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="c5d48-106">Darüber hinaus empfiehlt es sich, dass Sie alle angefügten Music-on-Keep-Dateien von lync Server 2010 zu einem anderen Ziel sichern, um eine separate Sicherungskopie aller angepassten Music-on-halten-Dateien zu erhalten, die für den Anruf Park hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="c5d48-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="c5d48-107">Die angepassten Music-on-halten-Dateien für die Anwendung "Parken" werden im Dateispeicher des Pools gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c5d48-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="c5d48-108">Wenn Sie die Audiodateien aus einem lync Server 2010-Pool Dateispeicher in einen lync Server 2013-Dateispeicher kopieren möchten, verwenden Sie den Befehl **xcopy** mit den folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="c5d48-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="c5d48-109">Wenn alle angepassten Audiodateien in den lync Server 2013-Dateispeicher kopiert wurden, müssen die Einstellungen für den Anruf Park des lync Server 2013-Pools konfiguriert sein, und die orbitbereiche für den Anruf Park, die dem lync Server 2010-Pool zugeordnet sind, müssen erneut zugewiesen werden. der lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="c5d48-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="c5d48-110">Die Anwendungseinstellungen des Anruf Parks beinhalten den Schwellenwert für das Pickup-Zeitlimit, das Aktivieren oder Deaktivieren von Musik in Wartestellung, die maximale Anzahl von Anruf Angriffen und die Timeout-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="c5d48-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="c5d48-111">Sie müssen die Einstellungen für die Anruf Park Anwendung verwalten, indem Sie die lync Server-Verwaltungsshell verwenden, um das Cmdlet " **Satz-CsCpsConfiguration** " auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c5d48-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="c5d48-112">Mit der lync Server-Systemsteuerung können Sie die Anwendungseinstellungen für den Anruf Park nicht verwalten.</span><span class="sxs-lookup"><span data-stu-id="c5d48-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="c5d48-113">**Neukonfigurieren der Einstellungen für den Anruf Park Dienst**</span><span class="sxs-lookup"><span data-stu-id="c5d48-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="c5d48-114">Öffnen Sie auf dem lync Server 2013-Front-End-Server die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c5d48-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="c5d48-115">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c5d48-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5d48-116">Wenn die Anwendungseinstellungen Ihres lync Server 2013-Anrufs mit den Legacy Einstellungen von lync Server 2010 identisch sind, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="c5d48-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="c5d48-117">Wenn sich die Einstellungen für den Anruf Park für die lync Server 2013-und lync Server 2010-Umgebungen unterscheiden, verwenden Sie das unten aufgeführte Cmdlet als Vorlage, um diese Änderungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c5d48-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

<span data-ttu-id="c5d48-118">Wenn Sie alle orbitbereiche des Anruf Parks vom lync Server 2010-Pool zum lync Server 2013-Pool neu zuweisen möchten, können Sie entweder die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5d48-118">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="c5d48-119">**Erneutes Zuweisen aller orbitbereiche für den Anruf Bereich mithilfe der lync Server-Systemsteuerung**</span><span class="sxs-lookup"><span data-stu-id="c5d48-119">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="c5d48-120">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="c5d48-120">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="c5d48-121">Wählen Sie im linken Bereich **sprach Features**aus.</span><span class="sxs-lookup"><span data-stu-id="c5d48-121">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="c5d48-122">Wählen Sie die Registerkarte **Anruf parken** aus.</span><span class="sxs-lookup"><span data-stu-id="c5d48-122">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="c5d48-123">Bearbeiten Sie für jeden Anruf Park-orbitbereich, der einem lync Server 2010-Pool zugewiesen ist, den **FQDN der Ziel Server** Einstellung, und wählen Sie den lync Server 2013-Pool aus, der die Anforderungen des Anruf Parks verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c5d48-123">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="c5d48-124">Wählen Sie **Commit** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c5d48-124">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="c5d48-125">**Erneutes Zuweisen aller orbitbereiche für den Anruf Bereich mithilfe der lync Server-Verwaltungsshell**</span><span class="sxs-lookup"><span data-stu-id="c5d48-125">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="c5d48-126">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c5d48-126">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="c5d48-127">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c5d48-127">At the command line, type the following:</span></span>
    
        Get-CsCallParkOrbit
    
    <span data-ttu-id="c5d48-128">Mit diesem Cmdlet werden alle orbitbereiche des Anruf Parks in der Bereitstellung aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c5d48-128">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="c5d48-129">Alle Orbits des Anruf Parks, deren **CallParkServiceId** -und **CallParkServerFqdn** -Parameter als lync Server 2010-Pool festgelegt sind, müssen neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c5d48-129">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="c5d48-130">Geben Sie in der Befehlszeile Folgendes ein, um den lync Server 2010-Orbit für den Anruf Bereich zum lync Server 2013-Pool erneut zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="c5d48-130">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

<span data-ttu-id="c5d48-131">Nach dem erneuten Zuweisen aller orbitbereiche für den Anruf Bereich zum lync Server 2013-Pool wird der Migrationsprozess für die Anwendung "Parken" abgeschlossen, und der lync Server 2013-Pool verarbeitet alle zukünftigen Anruf Park Anfragen.</span><span class="sxs-lookup"><span data-stu-id="c5d48-131">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

