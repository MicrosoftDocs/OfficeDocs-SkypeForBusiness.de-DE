---
title: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Die Migration der Anwendung zum Parken von Anrufen umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit beliebigen benutzerdefinierten Archivdateien, die in der Legacy Installation hochgeladen wurden, wobei die Einstellungen für den Service Level wiederhergestellt und alle Orbits für das Parken von Anrufen an den Skype for Business Server 2019-Pool neu ausgerichtet wurden. Wenn benutzerdefinierte Musikdateien im Pool konfiguriert wurden, müssen diese Dateien in den neuen Pool Skype for Business Server 2019 kopiert werden. Außerdem wird empfohlen, dass Sie alle benutzerdefinierten Music-on-Hold-Dateien für das Parken von Anrufen von einem anderen Ziel aus sichern, um eine separate Sicherungskopie aller benutzerdefinierten Musikarchiv Dateien aufzubewahren, die für das Parken von Anrufen hochgeladen wurden. Die angepassten Music-on-Hold-Dateien für die Anwendung zum Parken von Anrufen werden im Dateispeicher des Pools gespeichert. Wenn Sie die Audiodateien aus einem Pool Dateispeicher in einen Skype for Business Server 2019-Dateispeicher kopieren möchten, verwenden Sie den Befehl xcopy mit den folgenden Parametern:'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752817"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="10e71-107">Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="10e71-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="10e71-108">Die Migration der Anwendung zum Parken von Anrufen umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit beliebigen benutzerdefinierten Musikarchiv Dateien, die in die Legacy Installation hochgeladen wurden, wobei die Einstellungen auf Serviceebene wiederhergestellt und alle Orbits für das Parken von Anrufen auf den Skype for Business Server 2019-Pool neu ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="10e71-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="10e71-109">Wenn benutzerdefinierte Musikdateien im Pool konfiguriert wurden, müssen diese Dateien in den neuen Pool Skype for Business Server 2019 kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="10e71-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="10e71-110">Darüber hinaus wird empfohlen, dass Sie alle benutzerdefinierten Music-on-Hold-Dateien für das Parken von Anrufen an ein anderes Ziel sichern, um eine separate Sicherungskopie aller benutzerdefinierten Musikarchiv Dateien aufzubewahren, die für das Parken von Anrufen hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="10e71-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="10e71-111">Die angepassten Music-on-Hold-Dateien für die Anwendung zum Parken von Anrufen werden im Dateispeicher des Pools gespeichert.</span><span class="sxs-lookup"><span data-stu-id="10e71-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="10e71-112">Wenn Sie die Audiodateien aus einem Pool Dateispeicher in einen Skype for Business Server 2019-Dateispeicher kopieren möchten, verwenden Sie den Befehl **xcopy** mit den folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="10e71-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="10e71-113">Wenn alle benutzerdefinierten Audiodateien in den Dateispeicher Skype for Business Server 2019 kopiert wurden, müssen die Anwendung zum Parken von Anrufen Einstellungen des Skype for Business Server 2019-Pools konfiguriert werden, und die dem Legacy Pool zugeordneten orbitbereiche für das Parken von anrufen müssen dem Skype for Business Server 2019-Pool neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="10e71-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="10e71-114">Die Anwendung zum Parken von Anrufen Einstellungen umfassen den Schwellenwert für das Pickup-Timeout, das Aktivieren oder Deaktivieren von Wartemusik, die maximale Anzahl von Anruf Angriffen und die Timeout Anforderung.</span><span class="sxs-lookup"><span data-stu-id="10e71-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="10e71-115">Sie müssen Anwendung zum Parken von Anrufen Einstellungen verwalten, indem Sie das Cmdlet "CsCpsConfiguration" mithilfe der Skype for Business Server **-** Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="10e71-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="10e71-116">Die Anwendung zum Parken von Anrufen Einstellungen können nicht mithilfe der Skype for Business Server-Systemsteuerung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="10e71-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="10e71-117">Erneutes Konfigurieren der Einstellungen für den Dienst zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="10e71-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="10e71-118">Öffnen Sie im Skype for Business Server 2019 Front-End-Server die Skype for Business Server Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="10e71-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="10e71-119">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="10e71-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="10e71-120">Wenn Ihre Skype for Business Server 2019-Anwendung zum Parken von Anrufen Einstellungen mit den Legacy Einstellungen identisch sind, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="10e71-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="10e71-121">Wenn Anwendung zum Parken von Anrufen Einstellungen für die Skype for Business Server 2019-und Legacy Umgebungen unterschiedlich sind, verwenden Sie das unten aufgeführte Cmdlet als Vorlage, um diese Änderungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="10e71-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="10e71-122">Zum erneuten Zuweisen aller orbitbereiche zum Parken von Anrufen vom Legacy Pool zum Pool Skype for Business Server 2019 können Sie entweder die Skype for Business Server-Systemsteuerung oder die Skype for Business Server Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="10e71-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="10e71-123">Neuzuweisen aller Umlaufbahn Bereiche für das Parken von Anrufen mithilfe Skype for Business Server Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="10e71-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="10e71-124">Öffnen Sie Skype for Business Server Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="10e71-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="10e71-125">Wählen Sie im linken Bereich **VoIP-Funktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="10e71-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="10e71-126">Wählen Sie die Registerkarte **Parken von Anrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="10e71-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="10e71-127">Bearbeiten Sie für jeden orbitbereich für das Parken von anrufen, der einem Legacy Pool zugewiesen ist, die Einstellung **FQDN of Destination Server** , und wählen Sie den Pool Skype for Business Server 2019 aus, der die Anforderungen für das Parken von Anrufen verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="10e71-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="10e71-128">Klicken Sie auf **Commit ausführen**, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="10e71-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="10e71-129">Alle Bereiche des Orbits für das Parken von Anrufen mit Skype for Business Server Verwaltungsshell neu zuweisen</span><span class="sxs-lookup"><span data-stu-id="10e71-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="10e71-130">Öffnen Sie Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="10e71-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="10e71-131">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="10e71-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="10e71-132">Dieses Cmdlet listet alle Bereiche für den Anrufparkorbit in der Bereitstellung auf.</span><span class="sxs-lookup"><span data-stu-id="10e71-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="10e71-133">Alle Orbits für das Parken von anrufen, bei denen die Parameter **CallParkServiceId** und **CallParkServerFqdn** als Legacy Pool festgelegt sind, müssen neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="10e71-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="10e71-134">Geben Sie an der Befehlszeile Folgendes ein, um den Legacy Orbit für das Parken von Anrufen im Skype for Business Server 2019-Pool neu zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="10e71-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="10e71-135">Nach dem erneuten Zuweisen aller orbitbereiche für das Parken von Anrufen zum Pool Skype for Business Server 2019 wird der Migrationsprozess für die Anwendung zum Parken von Anrufen abgeschlossen, und der Skype for Business Server 2019-Pool verarbeitet alle zukünftigen Anforderungen für das Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="10e71-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


