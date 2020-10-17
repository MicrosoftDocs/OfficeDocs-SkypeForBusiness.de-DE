---
title: 'Lync Server 2013: Planen der Notfallwiederherstellung für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f221947975c00eccefe50cb5ca72b264c9596014
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497752"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="4b503-102">Planen der Notfallwiederherstellung für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b503-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b503-103">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="4b503-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="4b503-104">In diesem Abschnitt werden einige Möglichkeiten beschrieben, wie Sie die Anwendung zum Parken von Anrufen für die Notfallwiederherstellung und einige Überlegungen für den Notfall Wiederherstellungsprozess vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="4b503-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="4b503-105">Vorbereiten der Notfallwiederherstellung für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="4b503-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="4b503-106">Beachten Sie bei der Vorbereitung und Durchführung von Notfallwiederherstellungsverfahren Folgendes.</span><span class="sxs-lookup"><span data-stu-id="4b503-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="4b503-107">Planen Sie die Notfallwiederherstellung gleichzeitig mit der Kapazitätsplanung.</span><span class="sxs-lookup"><span data-stu-id="4b503-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="4b503-108">Für die Notfall Wiederherstellungs Kapazität sollte jeder Pool in einem gekoppelten Pool in der Lage sein, die Arbeitslasten der Dienste zum Parken von Anrufen in beiden Pools zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4b503-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="4b503-109">Ausführliche Informationen zur Kapazitätsplanung für das Parken von Anrufen finden Sie unter [Kapazitätsplanung für das Parken von Anrufen in lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span><span class="sxs-lookup"><span data-stu-id="4b503-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="4b503-110">Während der Notfallwiederherstellung verwenden Benutzer, die im Rahmen des Failovers an den Sicherungspool umgeleitet wurden, den Dienst zum Parken von anrufen, der im Sicherungspool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4b503-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="4b503-111">Unterstützung für das Parken von Anrufen während der Notfallwiederherstellung erfordert daher, dass die Anwendung zum Parken von Anrufen sowohl im primären Pool als auch im Sicherungspool bereitgestellt und aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="4b503-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="4b503-112">Jeder Pool muss über einen gültigen Bereich von Orbit-Nummern für Benutzer verfügen, die in diesem Pool verwaltet werden und für das Parken von Anrufen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b503-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="4b503-113">Halten Sie immer eine separate Sicherungskopie aller benutzerdefinierten Wartemusik, die für das Parken von Anrufen hochgeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4b503-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="4b503-114">Diese Dateien werden nicht als Teil des lync Server 2013 Notfall Wiederherstellungsprozesses gesichert und gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4b503-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="4b503-115">Überlegungen zur Notfallwiederherstellung beim Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="4b503-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="4b503-116">Sie können nur eine Gruppe von Anwendung zum Parken von Anrufen Konfigurationseinstellungen und eine benutzerdefinierte Audiodatei pro Pool definieren.</span><span class="sxs-lookup"><span data-stu-id="4b503-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="4b503-117">Zu diesen Einstellungen gehören der Schwellenwert für Timeout, Wartemusik, maximale Anzahl von Anruf Angriffen und Timeout-URI.</span><span class="sxs-lookup"><span data-stu-id="4b503-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="4b503-118">Führen Sie das Cmdlet **Get-CsCpsConfiguration** aus, um diese Konfigurationseinstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4b503-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="4b503-119">Ausführliche Informationen zum Cmdlet **Get-CsCpsConfiguration** finden Sie unter [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="4b503-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="4b503-120">Während der Notfallwiederherstellung verwendet das Parken von Anrufen die Anwendung zum Parken von Anrufen im Sicherungspool, daher werden Einstellungen im primären Pool nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="4b503-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="4b503-121">Wenn der primäre Pool nicht wiederhergestellt werden kann und Sie einen neuen Pool zum Ersetzen des primären Pools bereitstellen, gehen die Einstellungen aus dem primären Pool verloren, und Sie müssen die Einstellungen für das Parken von Anrufen und alle angepassten Musikdateien im neuen Pool neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4b503-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="4b503-122">Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, um den primären Pool zu ersetzen, müssen Sie alle Bereiche des Orbits für das Parken von anrufen, die dem primären Pool zugeordnet sind, dem FQDN des neuen Pools zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4b503-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="4b503-123">Um orbitbereiche erneut dem neuen Pool zuzuweisen, können Sie entweder lync Server-Systemsteuerung oder das Cmdlet " **Sets-CsCallParkOrbit** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b503-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="4b503-124">Ausführliche Informationen zum Cmdlet " **CsCallParkOrbit** " finden Sie unter [festlegen-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="4b503-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

