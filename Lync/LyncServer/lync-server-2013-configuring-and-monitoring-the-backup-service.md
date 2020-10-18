---
title: 'Lync Server 2013: Konfigurieren und Überwachen des Sicherungsdiensts'
description: 'Lync Server 2013: Konfigurieren und Überwachen des Sicherungsdiensts.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35302aeb430e8591babd88969d4c5c158c1ac0bf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574641"
---
# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="ffbbf-103">Konfigurieren und Überwachen des Sicherungsdiensts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbbf-103">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffbbf-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ffbbf-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ffbbf-105">Sie können die folgenden lync Server-Verwaltungsshell Befehle verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-105">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ffbbf-106">Die RTCUniversalServerAdmins-Gruppe ist die einzige Gruppe mit Berechtigungen zum standardmäßigen Ausführen von <STRONG>Get-CsBackupServiceStatus</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ffbbf-106">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="ffbbf-107">Um dieses Cmdlet zu verwenden, melden Sie sich als Mitglied dieser Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="ffbbf-108">Sie können auch anderen Gruppen (beispielsweise CSAdministrator) Zugriff auf diesen Befehl gewähren, indem Sie das Cmdlet " <STRONG>csbackupserviceconfiguration"</STRONG> "verwenden.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="ffbbf-109">So zeigen Sie die Sicherungsdienst Konfiguration an</span><span class="sxs-lookup"><span data-stu-id="ffbbf-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="ffbbf-110">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="ffbbf-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="ffbbf-111">Der Standardwert für SyncInterval ist zwei Minuten.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-111">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="ffbbf-112">So legen Sie das Synchronisierungsintervall für den Sicherungsdienst fest</span><span class="sxs-lookup"><span data-stu-id="ffbbf-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="ffbbf-113">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="ffbbf-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="ffbbf-114">Im folgenden Beispiel wird das Intervall auf drei Minuten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ffbbf-115">Obwohl Sie dieses Cmdlet zum Ändern des standardmäßigen Synchronisierungsintervalls für den Sicherungsdienst verwenden können, sollten Sie dies nur tun, wenn dies unbedingt erforderlich ist, da das Synchronisierungsintervall große Auswirkungen auf die Leistung des Sicherungsdiensts und das Ziel des Wiederherstellungspunkts (RPO) hat.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="ffbbf-116">So rufen Sie den Sicherungsdienst Status für einen bestimmten Pool ab</span><span class="sxs-lookup"><span data-stu-id="ffbbf-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="ffbbf-117">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="ffbbf-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="ffbbf-118">Der Synchronisierungsstatus des Sicherungsdiensts wird von einem Pool (P1) auf den Sicherungspool (P2) unidirektional festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="ffbbf-119">Der Synchronisierungsstatus von P1 bis P2 kann unterschiedlich sein als der von P2 bis P1.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="ffbbf-120">Bei P1 bis P2 befindet sich der Sicherungsdienst in einem "stationären" Zustand, wenn alle in P1 vorgenommenen Änderungen innerhalb des Synchronisierungsintervalls vollständig auf P2 repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="ffbbf-121">Es befindet sich im "endgültigen" Zustand, wenn keine Änderungen mehr von P1 zu P2 synchronisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="ffbbf-122">Beide Zustände deuten auf eine Momentaufnahme des Sicherungsdiensts zu dem Zeitpunkt hin, an dem das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="ffbbf-123">Dies bedeutet nicht, dass der zurückgegebene Status wie im Anschluss bleibt.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="ffbbf-124">Insbesondere wird der Status "endgültig" nur dann beibehalten, wenn P1 nach dem Ausführen des Cmdlets keine Änderungen mehr generiert.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="ffbbf-125">Dies gilt für den Fall, dass P1 über bis P2 verfällt, nachdem P1 als Teil der <STRONG>Invoke-CsPoolfailover-</STRONG> Ausführungslogik in den schreibgeschützten Modus versetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="ffbbf-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="ffbbf-126">So rufen Sie Informationen zur Sicherungsbeziehung für einen bestimmten Pool ab</span><span class="sxs-lookup"><span data-stu-id="ffbbf-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="ffbbf-127">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="ffbbf-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="ffbbf-128">So erzwingen Sie die Synchronisierung eines Sicherungsdiensts</span><span class="sxs-lookup"><span data-stu-id="ffbbf-128">To force a Backup Service sync</span></span>

<span data-ttu-id="ffbbf-129">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="ffbbf-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

