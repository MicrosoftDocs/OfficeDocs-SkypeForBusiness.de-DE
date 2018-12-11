---
title: Konfigurieren und Überwachen des Sicherungsdiensts
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können Skype für Business Server Management Shell-Befehle zum Konfigurieren und Überwachen des Sicherungsdienstes verwenden.
ms.openlocfilehash: f06da0cad4bf6a7deb5ab098530bfea548db21f9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222884"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="a0025-103">Konfigurieren und Überwachen des Sicherungsdienstes in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a0025-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="a0025-104">Sie können die folgenden Skype für Business Server Management Shell-Befehle konfigurieren und Überwachen des Sicherungsdienstes verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0025-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="a0025-105">Um in den Dateispeicher eines Front-End-Pools gespeicherten Konferenzinformationen wiederherzustellen, finden Sie unter [Wiederherstellen von konferenzinhalten mithilfe des Sicherungsdienstes](#restore-conference-contents-using-the-backup-service), unten.</span><span class="sxs-lookup"><span data-stu-id="a0025-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="a0025-106">Die Gruppe "RTCUniversalServerAdmins" ist die einzige Gruppe, die Berechtigungen zum Ausführen von **Get-CsBackupServiceStatus** standardmäßig verfügt.</span><span class="sxs-lookup"><span data-stu-id="a0025-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="a0025-107">Wenn Sie dieses Cmdlet verwenden, melden Sie sich als Mitglied dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="a0025-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="a0025-108">Oder Sie können Zugriff auf mit diesem Befehl zu anderen Gruppen (z. B. "csadministrator") gewähren, mit dem Cmdlet **"Set-csbackupserviceconfiguration"** .</span><span class="sxs-lookup"><span data-stu-id="a0025-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="a0025-109">Um die Konfiguration des Sicherungsdiensts finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="a0025-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="a0025-110">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="a0025-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="a0025-111">Der Standard für SyncInterval sind zwei Minuten.</span><span class="sxs-lookup"><span data-stu-id="a0025-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="a0025-112">So legen Sie das Synchronisierungsintervall Sicherungsdienst fest</span><span class="sxs-lookup"><span data-stu-id="a0025-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="a0025-113">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="a0025-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="a0025-114">Folgendes wird beispielsweise das Intervall von drei Minuten.</span><span class="sxs-lookup"><span data-stu-id="a0025-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="a0025-115">Obwohl Sie dieses Cmdlet zum Ändern des Standard-Synchronisierungsintervall für den Sicherungsdienst verwenden können, sollten Sie nicht, damit es sei denn, dies unbedingt erforderlich ist, als die Synchronisierung Intervall großen Einfluss auf die Leistung Sicherungsdienst und die Recovery Point Objectives (RPO) hat.</span><span class="sxs-lookup"><span data-stu-id="a0025-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="a0025-116">Um den sicherungsdienststatus für einen bestimmten Pool zu erhalten</span><span class="sxs-lookup"><span data-stu-id="a0025-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="a0025-117">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="a0025-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="a0025-118">Der Synchronisierungsstatus des Sicherungsdienstes ist gleich dem Sicherungspool (P2) unidirectionally aus einem Pool (P1) definiert.</span><span class="sxs-lookup"><span data-stu-id="a0025-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="a0025-119">Der Synchronisierungsstatus von P1 zu P2 kann andere als die von P2 zu P1 sein.</span><span class="sxs-lookup"><span data-stu-id="a0025-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="a0025-120">Für P1 zu P2 ist Sicherungsdienst im Zustand "stetig", wenn alle Änderungen in P1 vollständig in das Synchronisierungsintervall über zu P2 repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="a0025-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="a0025-121">Es ist in "Endzustand" liegen keine weitere Änderungen, die von P1 zu P2 synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0025-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="a0025-122">Sowohl Zustand Geben Sie eine Momentaufnahme der des Sicherungsdienstes an, zu dem Zeitpunkt, die das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0025-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="a0025-123">Es impliziert nicht, dass der zurückgegebene Status während bleibt unverändert anschließend.</span><span class="sxs-lookup"><span data-stu-id="a0025-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="a0025-124">Insbesondere wird "Endzustand" weiterhin nur enthalten, wenn P1 keine Änderungen generiert, nachdem Sie das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0025-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="a0025-125">Dies gilt im Fall von Failover P1 zu P2 nach P1 als Teil der Ausführungslogik **Invoke-CsPoolfailover** in den schreibgeschützten Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="a0025-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="a0025-126">Zum Abrufen von Informationen zur sicherungsbeziehung für einen bestimmten pool</span><span class="sxs-lookup"><span data-stu-id="a0025-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="a0025-127">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="a0025-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="a0025-128">So erzwingen Sie eine Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="a0025-128">To force a Backup Service sync</span></span>

<span data-ttu-id="a0025-129">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="a0025-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="a0025-130">Wiederherstellen von konferenzinhalten mithilfe des Sicherungsdienstes</span><span class="sxs-lookup"><span data-stu-id="a0025-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="a0025-131">In gespeicherte Konferenzinformationen in den Dateispeicher eines Front-End-Pools nicht mehr verfügbar ist, können Sie diese Informationen müssen wiederherstellen, sodass Benutzer im Pool verwaltet behalten ihre Konferenzdaten.</span><span class="sxs-lookup"><span data-stu-id="a0025-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="a0025-132">Wenn Sie der Front-End-Pool, der Konferenzdaten verloren wurde mit einer anderen Front-End-Pool verbunden ist, können Sie den Sicherungsdienst zum Wiederherstellen der Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0025-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="a0025-133">Sie müssen auch für diese Aufgabe ausführen, wenn ein gesamtes Pools ausgefallen ist und Sie haben die Benutzer zu einem Sicherungspool Failover.</span><span class="sxs-lookup"><span data-stu-id="a0025-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="a0025-134">Wenn diese Benutzer auf ihre ursprünglichen Pool wieder Failover ausgeführt werden, müssen Sie dieses Verfahren zum Kopieren von ihren konferenzinhalten wieder auf ihre ursprünglichen Pool auch verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0025-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="a0025-135">Wird davon ausgegangen Sie, dass Pool1 Pool2 zugeordnet ist, und die Konferenzdaten in Pool1 verloren geht.</span><span class="sxs-lookup"><span data-stu-id="a0025-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="a0025-136">Das folgende Cmdlet können zum Aufrufen des Sicherungsdienstes, um den Inhalt wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="a0025-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="a0025-137">Wiederherstellen der Konferenz Inhalt kann je nach ihrer Größe einige Zeit dauern.</span><span class="sxs-lookup"><span data-stu-id="a0025-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="a0025-138">Das folgende Cmdlet können Sie um den Prozessstatus zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="a0025-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="a0025-139">Der Vorgang ist abgeschlossen, wenn dieses Cmdlet gibt einen Wert für die Konferenz zu verwendenden Datenmoduls datenkonferenzmodul zurück.</span><span class="sxs-lookup"><span data-stu-id="a0025-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>