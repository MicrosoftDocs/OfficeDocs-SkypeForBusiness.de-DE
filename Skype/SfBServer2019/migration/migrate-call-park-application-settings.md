---
title: Migrieren von Einstellungen für das Parken von Anrufen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Die Migration von der Anwendung einschließlich der Bereitstellung der Skype für Business Server 2019 Pool mit eine beliebige benutzerdefinierte Musik in der Warteschleife-Dateien, die in der Vorversion Installation hochgeladen wurden parken, zum Wiederherstellen der Einstellungen auf Poolebene Service und alle Parken Neuzuweisen umkreist die Skype für Business Server 2019 Pool. Wenn benutzerdefinierte Musik halten Dateien im Pool konfiguriert wurden, müssen diese Dateien in die neue Skype für Business Server 2019 Pool kopiert werden. Darüber hinaus wird empfohlen, dass Sie alle Parken sichern Musik halten-Dateien an ein anderes Ziel angepasst beibehalten eine separate Sicherungskopie der angepassten Musik halten Dateien, die hochgeladen wurden für das Parken. Die angepassten Musik halten-Dateien für die Anwendung zum Parken von Anrufen werden in den Dateispeicher des Pools gespeichert. Um die Audiodateien aus einem Pool-Dateispeicher in einen Skype für Business Server 2019 Dateispeicher kopieren möchten, verwenden Sie den Befehl Xcopy mit den folgenden Parametern:'
ms.openlocfilehash: bcc2da8192f0c94f20d11073b1b18439ccc9df61
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370994"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="b8c73-107">Migrieren von Einstellungen für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="b8c73-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="b8c73-108">Die Migration von der Anwendung zum Parken einschließlich der Bereitstellung der Skype für Business Server 2019 Pool mit den benutzerdefinierten Musik halten-Dateien, die in der Vorversion installieren, die Einstellungen Servicelevel wiederherstellen und Zielversion alle Orbits für das Parken von Anrufen hochgeladen wurden um die Skype für Business Server 2019 Pool.</span><span class="sxs-lookup"><span data-stu-id="b8c73-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b8c73-109">Wenn benutzerdefinierte Musik halten Dateien im Pool konfiguriert wurden, müssen diese Dateien in die neue Skype für Business Server 2019 Pool kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8c73-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b8c73-110">Darüber hinaus wird empfohlen, dass alle zum Parken von Anrufen zu sichern Musik halten Dateien an ein anderes Ziel angepasst beibehalten eine separate Sicherungskopie der angepassten Musik halten Dateien, die hochgeladen wurden für das Parken.</span><span class="sxs-lookup"><span data-stu-id="b8c73-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="b8c73-111">Die angepassten Musik halten-Dateien für die Anwendung zum Parken von Anrufen werden in den Dateispeicher des Pools gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b8c73-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="b8c73-112">Um die Audiodateien aus einem Pool-Dateispeicher in einen Skype für Business Server 2019 Dateispeicher kopieren möchten, verwenden Sie den Befehl **Xcopy** mit den folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="b8c73-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="b8c73-113">Wenn alle benutzerdefinierte Audiodateien in der Skype für Business Server 2019 Dateispeicher kopiert wurden, orbit die Einstellungen für den Anwendung zum Parken von Anrufen über die Skype für Business Server 2019 Pool konfiguriert werden muss, und die Parken Bereiche, die dem vorversionspool zugeordnet sind die Skype für Business Server 2019 Pool zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="b8c73-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="b8c73-114">Einstellungen für die Parken enthalten den Timeoutschwellenwert pickup aktivieren oder Deaktivieren von wartemusik, die maximale pickup Anrufversuche, und die Timeout-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b8c73-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="b8c73-115">Verwalten des Parkens von Anrufen Einstellungen müssen Sie mithilfe der Skype für Business Server-Verwaltungsshell das Cmdlet **Set-CsCpsConfiguration** ausführen.</span><span class="sxs-lookup"><span data-stu-id="b8c73-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="b8c73-116">Sie können nicht zum Parken von Anrufen der Einstellungen für die Verwendung der Skype für Business Server-Systemsteuerung verwalten.</span><span class="sxs-lookup"><span data-stu-id="b8c73-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="b8c73-117">Konfigurieren von Einstellungen für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="b8c73-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="b8c73-118">Öffnen Sie in der Skype für Business Server 2019 Front-End-Server der Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="b8c73-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="b8c73-119">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b8c73-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8c73-120">Wenn Ihre Skype für Business Server 2019 Call Park-Anwendungseinstellungen an den Einstellungen der Vorversionen identisch sind, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="b8c73-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="b8c73-121">Wenn Parken-Anwendungseinstellungen für die Skype für Business Server 2019 und legacy-Umgebungen unterschiedlich sind, verwenden Sie das Cmdlet unterhalb als Vorlage, um die Änderungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b8c73-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="b8c73-122">Um alle Anruf Bereiche für den anrufparkorbit aus dem vorversionspool, der Skype für Business Server 2019 Pool neu zuzuweisen, können Sie die Skype Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8c73-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b8c73-123">Neuzuordnen Sie aller Anruf Parken Orbit Bereiche mit Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="b8c73-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b8c73-124">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="b8c73-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="b8c73-125">Wählen Sie im linken Bereich **VoIP-Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="b8c73-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="b8c73-126">Wählen Sie die Registerkarte **Parken** .</span><span class="sxs-lookup"><span data-stu-id="b8c73-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="b8c73-127">Bearbeiten Sie für jede Parken orbitbereichs ein, die einem legacypool zugewiesen sind die Einstellung **FQDN des Zielservers** , und wählen Sie die Skype für Business Server 2019-Pool, die die Anforderungen zum Parken von Anrufen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b8c73-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="b8c73-128">Wählen Sie auf **Commit** , um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b8c73-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b8c73-129">Neuzuordnen Sie aller Anruf Parken Orbit Bereiche mit Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="b8c73-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b8c73-130">Öffnen Sie Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="b8c73-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="b8c73-131">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b8c73-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="b8c73-132">Mit diesem Cmdlet werden alle orbitbereiche zum Parken von Anrufen in der Bereitstellung aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b8c73-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="b8c73-133">Alle Orbits für das Parken von Anrufen, die die Parameter **CallParkServiceId** und **CallParkServerFqdn** als Pool der Vorgängerversion festgelegt haben, müssen neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b8c73-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="b8c73-134">Um die Vorversion anrufparkorbits geben Bereiche an der Skype für Business Server 2019 Pool, an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b8c73-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="b8c73-135">Nach Neuzuweisen alle Anruf Bereiche für den anrufparkorbit, der Skype für Business Server 2019 Pool, der Migrationsprozess für die Anwendung zum Parken wird abgeschlossen, und die Skype für Business Server 2019 Pool alle zukünftige Parken-Anforderungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="b8c73-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


