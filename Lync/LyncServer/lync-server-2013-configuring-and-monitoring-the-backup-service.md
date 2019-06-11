---
title: 'Lync Server 2013: Konfigurieren und Überwachen des Sicherungsdiensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a800014b3327e83426c9f758b7d5359c1ce6c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="56d02-102">Konfigurieren und Überwachen des Sicherungsdiensts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56d02-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56d02-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="56d02-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="56d02-104">Sie können die folgenden Befehle der lync Server-Verwaltungsshell verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="56d02-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56d02-105">Die Gruppe RTCUniversalServerAdmins ist die einzige Gruppe, die über die standardmäßige Berechtigung zum Ausführen von <STRONG>Get-CsBackupServiceStatus</STRONG> verfügt.</span><span class="sxs-lookup"><span data-stu-id="56d02-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="56d02-106">Wenn Sie dieses Cmdlet verwenden möchten, melden Sie sich als Mitglied dieser Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="56d02-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="56d02-107">Oder Sie können anderen Gruppen (beispielsweise CSAdministrator) mithilfe des Cmdlets " <STRONG>Satz-CsBackupServiceConfiguration</STRONG> " Zugriff auf diesen Befehl gewähren.</span><span class="sxs-lookup"><span data-stu-id="56d02-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="56d02-108">So zeigen Sie die Konfiguration des Sicherungsdiensts an</span><span class="sxs-lookup"><span data-stu-id="56d02-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="56d02-109">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="56d02-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="56d02-110">Der Standardwert für SyncInterval beträgt zwei Minuten.</span><span class="sxs-lookup"><span data-stu-id="56d02-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="56d02-111">So stellen Sie das Synchronisierungsintervall für den Sicherungsdienst ein</span><span class="sxs-lookup"><span data-stu-id="56d02-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="56d02-112">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="56d02-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="56d02-113">Im folgenden Beispiel wird das Intervall auf drei Minuten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="56d02-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="56d02-114">Obwohl Sie mit diesem Cmdlet das Standard Synchronisierungsintervall für den Sicherungsdienst ändern können, sollten Sie dies nicht tun, es sei denn, dies ist unbedingt erforderlich, da das Synchronisierungsintervall große Auswirkungen auf die Leistung des Sicherungsdiensts und auf das Recovery Point-Ziel (RPO) hat.</span><span class="sxs-lookup"><span data-stu-id="56d02-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="56d02-115">So rufen Sie den Sicherungsdienst Status für einen bestimmten Pool ab</span><span class="sxs-lookup"><span data-stu-id="56d02-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="56d02-116">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="56d02-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="56d02-117">Der Synchronisierungsstatus des Sicherungsdiensts wird unidirektional von einem Pool (P1) zu seinem Sicherungspool (P2) definiert.</span><span class="sxs-lookup"><span data-stu-id="56d02-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="56d02-118">Der Synchronisierungsstatus von P1 zu P2 kann von P2 zu P1 unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="56d02-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="56d02-119">Bei P1 bis P2 befindet sich der Sicherungsdienst in einem "stabilen" Zustand, wenn alle Änderungen, die in P1 vorgenommen wurden, innerhalb des Synchronisierungsintervalls vollständig auf P2 repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="56d02-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="56d02-120">Es befindet sich im "endgültigen" Zustand, wenn keine weiteren Änderungen von P1 zu P2 synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="56d02-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="56d02-121">Beide Zustände deuten auf eine Momentaufnahme des Sicherungsdiensts zu dem Zeitpunkt hin, zu dem das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="56d02-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="56d02-122">Das bedeutet nicht, dass der zurückgegebene Zustand unverändert bleibt.</span><span class="sxs-lookup"><span data-stu-id="56d02-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="56d02-123">Insbesondere bleibt der Zustand "Final" weiterhin nur dann bestehen, wenn P1 nach der Ausführung des Cmdlets keine Änderungen generiert.</span><span class="sxs-lookup"><span data-stu-id="56d02-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="56d02-124">Dies gilt im Fall eines Failovers von P1 auf P2, nachdem P1 als Teil der Ausführungslogik <STRONG>Invoke-CsPoolfailover</STRONG> in den schreibgeschützten Modus versetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="56d02-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="56d02-125">So erhalten Sie Informationen zur Sicherungsbeziehung für einen bestimmten Pool</span><span class="sxs-lookup"><span data-stu-id="56d02-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="56d02-126">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="56d02-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="56d02-127">So erzwingen Sie eine Synchronisierung des Sicherungsdiensts</span><span class="sxs-lookup"><span data-stu-id="56d02-127">To force a Backup Service sync</span></span>

<span data-ttu-id="56d02-128">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="56d02-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

