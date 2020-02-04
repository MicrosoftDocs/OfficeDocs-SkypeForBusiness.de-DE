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
ms.openlocfilehash: a76052297e527e24fd3daf0c03d02661c7ddc255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="3a529-102">Planen der Notfallwiederherstellung für das Parken von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a529-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a529-103">_**Letztes Änderungsdatum des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3a529-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3a529-104">In diesem Abschnitt werden einige Möglichkeiten beschrieben, wie Sie die Anwendung für den Parken von Anrufen für die Disaster Recovery und einige Überlegungen für den Disaster Recovery-Prozess vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="3a529-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="3a529-105">Vorbereiten der Disaster Recovery für den Anruf Park</span><span class="sxs-lookup"><span data-stu-id="3a529-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="3a529-106">Beachten Sie bei der Vorbereitung und Durchführung von Disaster Recovery-Verfahren Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3a529-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="3a529-107">Planen Sie die Disaster Recovery, wenn Sie Ihre Kapazitätsplanung durchführen.</span><span class="sxs-lookup"><span data-stu-id="3a529-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="3a529-108">Für die Disaster Recovery-Kapazität sollte jeder Pool in einem gekoppelten Pool in der Lage sein, die Arbeitslasten der Anruf Park Dienste in beiden Pools zu bewältigen.</span><span class="sxs-lookup"><span data-stu-id="3a529-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="3a529-109">Details zur Kapazitätsplanung des Anruf Parks finden Sie unter [Kapazitätsplanung für den Parken von Anrufen in lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span><span class="sxs-lookup"><span data-stu-id="3a529-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="3a529-110">Während der Disaster Recovery verwenden Benutzer, die im Rahmen des Failovers an den Sicherungspool umgeleitet wurden, den Anruf Park Dienst, der im Sicherungspool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3a529-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="3a529-111">Daher erfordert die Unterstützung für den Parken von Anrufen während der Disaster Recovery, dass die Anwendung für den Parken von Anrufen sowohl im primären Pool als auch im Sicherungspool bereitgestellt und aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="3a529-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="3a529-112">Jeder Pool muss über einen gültigen Bereich von Orbit-Nummern für Benutzer verfügen, die in diesem Pool verwaltet werden, um Sie für Park Anrufe zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a529-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="3a529-113">Bewahren Sie immer eine separate Sicherungskopie jeder angepassten Musik auf, die für den Anruf Park hochgeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="3a529-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="3a529-114">Diese Dateien werden im Rahmen des lync Server 2013-Wiederherstellungsprozesses nicht gesichert und gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="3a529-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="3a529-115">Überlegungen zur Disaster Recovery in Park anrufen</span><span class="sxs-lookup"><span data-stu-id="3a529-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="3a529-116">Pro Pool können Sie nur einen Satz von Einstellungen für die Anwendungskonfiguration des Anruf Parks und eine angepasste Musik-zu-halten-Audiodatei definieren.</span><span class="sxs-lookup"><span data-stu-id="3a529-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="3a529-117">Zu diesen Einstellungen gehören der Schwellenwert für Timeout, Musik in Wartestellung, maximale Anruf Abzugs Versuche und Timeout-URI.</span><span class="sxs-lookup"><span data-stu-id="3a529-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="3a529-118">Führen Sie das Cmdlet " **Get-CsCpsConfiguration** " aus, um diese Konfigurationseinstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3a529-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="3a529-119">Details zum Cmdlet **Get-CsCpsConfiguration** finden Sie unter [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3a529-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="3a529-120">Bei der Wiederherstellung des Notfalls verwendet Call Park die Anwendung "Parken" im Backup-Pool, sodass die Einstellungen im primären Pool nicht gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="3a529-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="3a529-121">Wenn der primäre Pool nicht wiederhergestellt werden kann und Sie einen neuen Pool zum Ersetzen des primären Pools bereitstellen, gehen die Einstellungen des primären Pools verloren, und Sie müssen die Einstellungen für den Anruf Park und alle angepassten Music-on-halten-Audiodateien im neuen Pool neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3a529-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="3a529-122">Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, um den primären Pool zu ersetzen, müssen Sie dem FQDN des neuen Pools alle orbitbereiche für den Anruf Bereich zuweisen, die dem primären Pool zugeordnet waren.</span><span class="sxs-lookup"><span data-stu-id="3a529-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="3a529-123">Wenn Sie dem neuen Pool Umlaufbahn Bereiche erneut zuweisen möchten, können Sie entweder die lync Server-Systemsteuerung oder das Cmdlet " **Satz-CsCallParkOrbit** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a529-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="3a529-124">Details zum Cmdlet " **setCsCallParkOrbit** " finden Sie unter [Satz-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="3a529-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

