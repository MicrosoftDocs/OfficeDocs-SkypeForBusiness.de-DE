---
title: Konfigurieren und Überwachen des Sicherungsdiensts
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie können die Befehle für die Skype for Business Server-Verwaltungsshell verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen.
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818216"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="9874a-103">Konfigurieren und Überwachen des Sicherungsdiensts in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9874a-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="9874a-104">Sie können die folgenden Befehle der Skype for Business Server-Verwaltungsshell verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="9874a-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="9874a-105">Informationen zum Wiederherstellen von Konferenz Informationen, die im Dateispeicher eines Front-End-Pools gespeichert sind, finden Sie weiter unten unter [Wiederherstellen von Konferenz Inhalten mithilfe des Sicherungsdiensts](#restore-conference-contents-using-the-backup-service).</span><span class="sxs-lookup"><span data-stu-id="9874a-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="9874a-106">Die Gruppe RTCUniversalServerAdmins ist die einzige Gruppe, die über die standardmäßige Berechtigung zum Ausführen von **Get-CsBackupServiceStatus** verfügt.</span><span class="sxs-lookup"><span data-stu-id="9874a-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="9874a-107">Wenn Sie dieses Cmdlet verwenden möchten, melden Sie sich als Mitglied dieser Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="9874a-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="9874a-108">Oder Sie können anderen Gruppen (beispielsweise CSAdministrator) mithilfe des Cmdlets " **Satz-CsBackupServiceConfiguration** " Zugriff auf diesen Befehl gewähren.</span><span class="sxs-lookup"><span data-stu-id="9874a-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="9874a-109">So zeigen Sie die Konfiguration des Sicherungsdiensts an</span><span class="sxs-lookup"><span data-stu-id="9874a-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="9874a-110">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="9874a-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="9874a-111">Der Standardwert für SyncInterval beträgt zwei Minuten.</span><span class="sxs-lookup"><span data-stu-id="9874a-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="9874a-112">So stellen Sie das Synchronisierungsintervall für den Sicherungsdienst ein</span><span class="sxs-lookup"><span data-stu-id="9874a-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="9874a-113">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="9874a-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="9874a-114">Im folgenden Beispiel wird das Intervall auf drei Minuten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9874a-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="9874a-115">Obwohl Sie mit diesem Cmdlet das Standard Synchronisierungsintervall für den Sicherungsdienst ändern können, sollten Sie dies nicht tun, es sei denn, dies ist unbedingt erforderlich, da das Synchronisierungsintervall große Auswirkungen auf die Leistung des Sicherungsdiensts und auf das Recovery Point-Ziel (RPO) hat.</span><span class="sxs-lookup"><span data-stu-id="9874a-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="9874a-116">So rufen Sie den Sicherungsdienst Status für einen bestimmten Pool ab</span><span class="sxs-lookup"><span data-stu-id="9874a-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="9874a-117">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="9874a-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="9874a-118">Der Synchronisierungsstatus des Sicherungsdiensts wird unidirektional von einem Pool (P1) zu seinem Sicherungspool (P2) definiert.</span><span class="sxs-lookup"><span data-stu-id="9874a-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="9874a-119">Der Synchronisierungsstatus von P1 zu P2 kann von P2 zu P1 unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="9874a-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="9874a-120">Bei P1 bis P2 befindet sich der Sicherungsdienst in einem "stabilen" Zustand, wenn alle Änderungen, die in P1 vorgenommen wurden, innerhalb des Synchronisierungsintervalls vollständig auf P2 repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="9874a-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="9874a-121">Es befindet sich im "endgültigen" Zustand, wenn keine weiteren Änderungen von P1 zu P2 synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9874a-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="9874a-122">Beide Zustände deuten auf eine Momentaufnahme des Sicherungsdiensts zu dem Zeitpunkt hin, zu dem das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9874a-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="9874a-123">Das bedeutet nicht, dass der zurückgegebene Zustand unverändert bleibt.</span><span class="sxs-lookup"><span data-stu-id="9874a-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="9874a-124">Insbesondere bleibt der Zustand "Final" weiterhin nur dann bestehen, wenn P1 nach der Ausführung des Cmdlets keine Änderungen generiert.</span><span class="sxs-lookup"><span data-stu-id="9874a-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="9874a-125">Dies gilt im Fall eines Failovers von P1 auf P2, nachdem P1 als Teil der Ausführungslogik **Invoke-CsPoolfailover** in den schreibgeschützten Modus versetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="9874a-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="9874a-126">So erhalten Sie Informationen zur Sicherungsbeziehung für einen bestimmten Pool</span><span class="sxs-lookup"><span data-stu-id="9874a-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="9874a-127">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="9874a-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="9874a-128">So erzwingen Sie eine Synchronisierung des Sicherungsdiensts</span><span class="sxs-lookup"><span data-stu-id="9874a-128">To force a Backup Service sync</span></span>

<span data-ttu-id="9874a-129">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="9874a-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="9874a-130">Wiederherstellen von Konferenz Inhalten mithilfe des Sicherungsdiensts</span><span class="sxs-lookup"><span data-stu-id="9874a-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="9874a-131">Wenn die Konferenz Informationen, die im Dateispeicher eines Front-End-Pools gespeichert sind, nicht mehr zur Verfügung stehen, müssen Sie diese Informationen so wiederherstellen, dass Benutzer, die im Pool verwaltet werden, ihre Konferenzdaten beibehalten.</span><span class="sxs-lookup"><span data-stu-id="9874a-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="9874a-132">Wenn der Front-End-Pool, in dem Konferenzdaten verloren gegangen sind, mit einem anderen Front-End-Pool gekoppelt ist, können Sie die Daten mithilfe des Sicherungsdiensts wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="9874a-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="9874a-133">Sie müssen diese Aufgabe auch ausführen, wenn ein gesamter Pool fehlgeschlagen ist und Sie die Benutzer nicht mit einem Sicherungspool durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="9874a-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="9874a-134">Wenn diese Benutzer wieder in ihren ursprünglichen Pool zurückgekehrt sind, müssen Sie diese Vorgehensweise verwenden, um Ihre Konferenzinhalte wieder in ihren ursprünglichen Pool zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="9874a-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="9874a-135">Gehen Sie davon aus, dass pool1 mit Pool2 gekoppelt ist und die Konferenzdaten in pool1 verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="9874a-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="9874a-136">Sie können das folgende Cmdlet verwenden, um den Sicherungsdienst aufzurufen, um den Inhalt wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="9874a-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="9874a-137">Das Wiederherstellen der Konferenzinhalte kann je nach Größe einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="9874a-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="9874a-138">Sie können das folgende Cmdlet verwenden, um den Prozessstatus zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="9874a-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="9874a-139">Der Vorgang erfolgt, wenn dieses Cmdlet den Wert des Steady-State-Werts für das Datenkonferenz Modul zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9874a-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
