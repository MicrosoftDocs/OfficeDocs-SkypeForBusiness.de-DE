---
title: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Die Migration der Anwendung für den Anruf Park umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit benutzerdefinierten Musikdateien, die in die Legacy Installation hochgeladen wurden, Wiederherstellen der Einstellungen für den Service Level und erneutes anvisieren aller Orbits des Anruf Parks an die Skype for Business Server 2019-Pool. Wenn benutzerdefinierte Musik-in-Warte-Dateien im Pool konfiguriert wurden, müssen diese Dateien in den neuen Skype for Business Server 2019-Pool kopiert werden. Darüber hinaus empfiehlt es sich, dass Sie alle für den Anruf Park angepassten Music-on-halten-Dateien von einem anderen Ziel aus sichern, um eine separate Sicherungskopie aller angepassten Music-on-halten-Dateien zu erhalten, die für den Anruf Park hochgeladen wurden. Die angepassten Music-on-halten-Dateien für die Anwendung "Parken" werden im Dateispeicher des Pools gespeichert. Wenn Sie die Audiodateien aus einem Pool Dateispeicher in einen Skype for Business Server 2019-Dateispeicher kopieren möchten, verwenden Sie den Befehl xcopy mit den folgenden Parametern:'
ms.openlocfilehash: aa4ac3cfbe6802b8853a8ec8886f8fffe1a20a51
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280830"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="da101-107">Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="da101-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="da101-108">Die Migration der Anwendung "Parken des Anrufs" umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit benutzerdefinierten Musik-in-situ-Dateien, die in die Legacy Installation hochgeladen wurden, Wiederherstellen der Einstellungen auf Dienstebene und erneutes Targeting für alle Orbits des Anruf Parks zum Skype for Business Server 2019-Pool.</span><span class="sxs-lookup"><span data-stu-id="da101-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="da101-109">Wenn benutzerdefinierte Musik-in-Warte-Dateien im Pool konfiguriert wurden, müssen diese Dateien in den neuen Skype for Business Server 2019-Pool kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="da101-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="da101-110">Darüber hinaus empfiehlt es sich, dass Sie alle angefügten Music-on-Keep-Dateien auf einem anderen Ziel gesichert haben, um eine separate Sicherungskopie aller angepassten Music-on-halten-Dateien zu erhalten, die für den Anruf Park hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="da101-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="da101-111">Die angepassten Music-on-halten-Dateien für die Anwendung "Parken" werden im Dateispeicher des Pools gespeichert.</span><span class="sxs-lookup"><span data-stu-id="da101-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="da101-112">Wenn Sie die Audiodateien aus einem Pool Dateispeicher in einen Skype for Business Server 2019-Dateispeicher kopieren möchten, verwenden Sie den Befehl **xcopy** mit den folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="da101-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="da101-113">Wenn alle angepassten Audiodateien in den Skype for Business Server 2019-Dateispeicher kopiert wurden, müssen die Einstellungen für den Anruf Park des Skype for Business Server 2019-Pools konfiguriert und die Umlaufbahn Bereiche des Anruf Parks, die dem Legacy Pool zugeordnet sind, angegeben werden. muss dem Skype for Business Server 2019-Pool erneut zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="da101-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="da101-114">Die Anwendungseinstellungen des Anruf Parks beinhalten den Schwellenwert für das Pickup-Zeitlimit, das Aktivieren oder Deaktivieren von Musik in Wartestellung, die maximale Anzahl von Anruf Angriffen und die Timeout Anforderung.</span><span class="sxs-lookup"><span data-stu-id="da101-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="da101-115">Sie müssen die Einstellungen für die Anruf Park Anwendung verwalten, indem Sie die Skype for Business Server-Verwaltungsshell verwenden, um das Cmdlet " **Satz-CsCpsConfiguration** " auszuführen.</span><span class="sxs-lookup"><span data-stu-id="da101-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="da101-116">Sie können die Einstellungen für den Anruf Park nicht über das Control Panel von Skype for Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="da101-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="da101-117">Neukonfigurieren der Einstellungen für den Anruf Park Dienst</span><span class="sxs-lookup"><span data-stu-id="da101-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="da101-118">Öffnen Sie auf dem Front-End-Server von Skype for Business Server 2019 die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="da101-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="da101-119">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="da101-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="da101-120">Wenn die Anwendungseinstellungen Ihres Skype for Business Server 2019-Anrufs mit den Legacy-Einstellungen identisch sind, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="da101-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="da101-121">Wenn sich die Einstellungen für den Anruf Park für die Skype for Business Server 2019-und Legacy-Umgebungen unterscheiden, verwenden Sie das unten aufgeführte Cmdlet als Vorlage, um diese Änderungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="da101-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="da101-122">Wenn Sie alle orbitbereiche des Anruf Parks vom Legacy Pool zum Skype for Business Server 2019-Pool neu zuweisen möchten, können Sie entweder das Skype for Business Server Control Panel oder die Skype for Business Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="da101-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="da101-123">Alle orbitbereiche für den Anruf Bereich über die Skype for Business Server-Systemsteuerung neu zuweisen</span><span class="sxs-lookup"><span data-stu-id="da101-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="da101-124">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="da101-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="da101-125">Wählen Sie im linken Bereich **sprach Features**aus.</span><span class="sxs-lookup"><span data-stu-id="da101-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="da101-126">Wählen Sie die Registerkarte **Anruf parken** aus.</span><span class="sxs-lookup"><span data-stu-id="da101-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="da101-127">Bearbeiten Sie für jeden Orbit-Bereich, der einem Legacy Pool zugewiesen ist, den **FQDN der Zielserver** Einstellung, und wählen Sie den Skype for Business Server 2019-Pool aus, der die Anforderungen des Anruf Parks verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="da101-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="da101-128">Wählen Sie **Commit** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="da101-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="da101-129">Erneutes Zuweisen aller orbitbereiche für den Anruf Bereich mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="da101-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="da101-130">Öffnen Sie die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="da101-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="da101-131">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="da101-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="da101-132">Mit diesem Cmdlet werden alle orbitbereiche des Anruf Parks in der Bereitstellung aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="da101-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="da101-133">Alle Orbits des Anruf Parks, deren **CallParkServiceId** -und **CallParkServerFqdn** -Parameter als Legacy Pool festgelegt sind, müssen neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="da101-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="da101-134">Geben Sie in der Befehlszeile Folgendes ein, um den Legacy-Anruf Park Orbit-Bereich dem Skype for Business Server 2019-Pool erneut zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="da101-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="da101-135">Nach der Neuzuweisung aller orbitbereiche für den Anruf Bereich zum Skype for Business Server 2019-Pool wird der Migrationsprozess für die Anwendung "Parken" abgeschlossen, und der Skype for Business Server 2019-Pool verarbeitet alle zukünftigen Anruf Park Anfragen.</span><span class="sxs-lookup"><span data-stu-id="da101-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


