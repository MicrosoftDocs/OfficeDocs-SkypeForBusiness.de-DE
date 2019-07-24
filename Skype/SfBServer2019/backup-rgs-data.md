---
title: Sichern von Daten des Reaktionsgruppendiensts (RGS) in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: Hier erfahren Sie, wie Sie in Skype for Business Server 2019 Daten zum Response Group Service (RGS) sichern.
ms.openlocfilehash: 0a37b4d4771a75513666597de5eb87dedcbcd0c7
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821325"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="6e4eb-103">Sichern von Daten des Reaktionsgruppendiensts (RGS)</span><span class="sxs-lookup"><span data-stu-id="6e4eb-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="6e4eb-104">Mit dem kumulativen Update für Skype for Business Server 2019 Juli haben wir die Möglichkeit aufgenommen, RGS-Daten als Teil der Standardsicherung einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="6e4eb-105">RGS-Datenreplikation</span><span class="sxs-lookup"><span data-stu-id="6e4eb-105">RGS data replication</span></span>

<span data-ttu-id="6e4eb-106">Führen Sie die folgenden Schritte aus, um die Funktionalität der RGS-Datenreplikation zu testen:</span><span class="sxs-lookup"><span data-stu-id="6e4eb-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="6e4eb-107">Installieren Sie das kumulative Update vom Juli auf allen Front-Ends (FES) Ihres gekoppelten Pools.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="6e4eb-108">Installieren Sie die RGS-Datenbank auf beiden Mitgliedern des gekoppelten Pools:</span><span class="sxs-lookup"><span data-stu-id="6e4eb-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="6e4eb-109">Führen Sie das folgende Cmdlet in beiden Pools aus, um vorhandene RGS-Daten in die Sicherungstabellen zu replizieren, damit die Daten von RGSBackupService abgerufen werden können:</span><span class="sxs-lookup"><span data-stu-id="6e4eb-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="6e4eb-110">Aktivieren Sie RGSBackupService (Dadurch wird RGSBackupService global aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="6e4eb-111">Wenn dieser Parameter auf "true" festgelegt ist, startet RGSBackupService die Synchronisierung von RGS-Daten in gekoppelten Pools (beide Pools müssen CU1 sein).</span><span class="sxs-lookup"><span data-stu-id="6e4eb-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="6e4eb-112">Warten Sie ein paar Minuten, um den Vorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="6e4eb-113">Zunächst wird der RGS-Backupservice-Status NotInitialized.):</span><span class="sxs-lookup"><span data-stu-id="6e4eb-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="6e4eb-114">So überprüfen Sie BackupServiceStatus:</span><span class="sxs-lookup"><span data-stu-id="6e4eb-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="6e4eb-115">Verwenden Sie diese Cmdlets, um die Datenreplikation über Pools hinweg zu überprüfen (diese Cmdlets zeigen nur Besitzer Pool Daten an):</span><span class="sxs-lookup"><span data-stu-id="6e4eb-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="6e4eb-116">So überprüfen Sie die RGS-Daten des Besitzer Pools und dessen Sicherungsdaten:</span><span class="sxs-lookup"><span data-stu-id="6e4eb-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="6e4eb-117">Überprüfen Sie die Workflow Funktionalität, indem Sie einen Audioanruf an den Workflow durchführen.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="6e4eb-118">Failover Ihres RGS-Besitzer Pools.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="6e4eb-119">Überprüfen Sie die Workflow Funktionalität, indem Sie einen Audioanruf an den Workflow durchführen.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="6e4eb-120">Failback des Pools.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-120">Failback the pool.</span></span>
1. <span data-ttu-id="6e4eb-121">Aktualisieren Sie RGS-Daten im Quell Pool, und führen Sie ein weiteres Failover durch, um zu überprüfen, ob Änderungen im Sicherungspool wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="6e4eb-122">RGS sollte sich auf die gleiche Weise Verhalten, wie es sich vor dem Failover befand.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="6e4eb-123">Es wird empfohlen, dass Sie diese Schritte für einen Großteil der Daten ausführen und häufige Failover-und Failback-Vorgänge durchführen.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="6e4eb-124">Alle neuen RGS, die nach diesem Cu-Update erstellt wurden, sollten ebenfalls repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="6e4eb-125">RGS-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="6e4eb-125">RGS cmdlets</span></span>

- <span data-ttu-id="6e4eb-126">Zum Überprüfen von BackupServiceStatus (der Exportstatus sollte im endgültigen oder stationären Zustand sein.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="6e4eb-127">Der Importstatus sollte im normalen Zustand sein.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="6e4eb-128">RGSBackupservice sollte aktiviert sein.):</span><span class="sxs-lookup"><span data-stu-id="6e4eb-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="6e4eb-129">Zum vollständigen Synchronisieren von RGS-Daten im Sicherungspool (Hiermit werden die vollständigen RGS-Daten im Sicherungspool synchronisiert.):</span><span class="sxs-lookup"><span data-stu-id="6e4eb-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="6e4eb-130">Zum vollständigen Synchronisieren des RGS-Dateispeichers im Sicherungspool (Hiermit werden die vollständigen RGS-Daten im Sicherungspool synchronisiert.):</span><span class="sxs-lookup"><span data-stu-id="6e4eb-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="6e4eb-131">So synchronisieren Sie RGS-Deltadaten im Sicherungspool (Hiermit werden Delta-Daten nur für RGS in einem Sicherungspool synchronisiert.):</span><span class="sxs-lookup"><span data-stu-id="6e4eb-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="6e4eb-132">So synchronisieren Sie alle Modul Daten einschließlich RGS:</span><span class="sxs-lookup"><span data-stu-id="6e4eb-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="6e4eb-133">So deaktivieren Sie RGSBackupService (Dadurch wird RGSBackupService global deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="6e4eb-134">Wenn dieser Parameter auf "true" festgelegt ist, wird RGSBackupService für alle gekoppelten Pools deaktiviert.):</span><span class="sxs-lookup"><span data-stu-id="6e4eb-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
