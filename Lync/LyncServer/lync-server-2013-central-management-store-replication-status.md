---
title: 'Lync Server 2013: Replikationsstatus des zentralen Verwaltungsspeichers'
description: 'Lync Server 2013: Replikationsstatus des zentralen Verwaltungsspeichers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f1f9008a966040cf34ac0499c023f9dbe53a541
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544361"
---
# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="279cf-103">Replikationsstatus des zentralen Verwaltungsspeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="279cf-103">Central management store replication status in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="279cf-104">_**Letztes Änderungsstand des Themas:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="279cf-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="279cf-105">Wenn ein Administrator eine Art Änderung an lync Server vornimmt (beispielsweise wenn ein Administrator eine neue VoIP-Richtlinie erstellt oder die Konfigurationseinstellungen für den Adressbuch Server ändert), wird diese Änderung im zentralen Verwaltungsspeicher aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="279cf-105">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="279cf-106">Die Änderung muss wiederum auf alle Computer repliziert werden, auf denen lync Server Dienste oder Server Rollen ausführt.</span><span class="sxs-lookup"><span data-stu-id="279cf-106">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="279cf-107">Zum Replizieren von Daten erstellt der Haupt Replikationsdienst (auf dem zentralen Verwaltungs Server ausgeführt) eine Momentaufnahme der geänderten Konfigurationsdaten.</span><span class="sxs-lookup"><span data-stu-id="279cf-107">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="279cf-108">Eine Kopie dieses Snapshots wird dann an jeden Computer gesendet, auf dem lync Server Dienste oder Server Rollen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="279cf-108">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="279cf-109">Auf diesen Computern empfängt ein Replikations-Agent den Snapshot und lädt die geänderten Daten hoch.</span><span class="sxs-lookup"><span data-stu-id="279cf-109">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="279cf-110">Der Agent sendet dann dem Haupt Replikationsdienst eine Nachricht, die den neuesten Replikationsstatus meldet.</span><span class="sxs-lookup"><span data-stu-id="279cf-110">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="279cf-111">Mit dem Get-CsManagementStoreReplicationStatus-Cmdlet können Sie den Replikationsstatus für alle (oder alle) der lync Server Computer in Ihrer Organisation überprüfen.</span><span class="sxs-lookup"><span data-stu-id="279cf-111">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="279cf-112">Wer kann dieses Cmdlet ausführen?</span><span class="sxs-lookup"><span data-stu-id="279cf-112">Who can run this cmdlet?</span></span> <span data-ttu-id="279cf-113">Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Get-CsManagementStoreReplicationStatus-Cmdlet lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="279cf-113">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="279cf-114">Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="279cf-114">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="279cf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="279cf-115">See Also</span></span>


[<span data-ttu-id="279cf-116">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="279cf-116">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

