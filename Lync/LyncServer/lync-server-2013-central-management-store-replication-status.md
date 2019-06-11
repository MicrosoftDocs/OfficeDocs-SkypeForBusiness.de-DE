---
title: 'Lync Server 2013: Replikationsstatus des zentralen Verwaltungsspeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce46b403e27d0a2b69f705b5bada026882eec7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="3f979-102">Replikationsstatus des zentralen Verwaltungsspeichers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f979-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f979-103">_**Letztes Änderungsdatum des Themas:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="3f979-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="3f979-104">Wenn ein Administrator eine Art Änderung an lync Server vornimmt (Wenn beispielsweise ein Administrator eine neue VoIP-Richtlinie erstellt oder die Konfigurationseinstellungen des Adressbuchservers ändert), wird diese Änderung im zentralen Verwaltungsspeicher aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3f979-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="3f979-105">Die Änderung muss dann wiederum auf alle Computer repliziert werden, auf denen lync Server-Dienste oder Serverrollen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3f979-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="3f979-106">Zum Replizieren der Daten erstellt der Master-Replikationsdienst (der auf dem zentralen Verwaltungsserver ausgeführt wird) eine Momentaufnahme der geänderten Konfigurationsdaten.</span><span class="sxs-lookup"><span data-stu-id="3f979-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="3f979-107">Anschließend wird eine Kopie dieses Snapshots an jeden Computer gesendet, auf dem lync Server-Dienste oder Serverrollen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3f979-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="3f979-108">Auf diesen Computern erhält ein lokaler Replikations-Agent die Momentaufnahme und lädt die geänderten Daten hoch.</span><span class="sxs-lookup"><span data-stu-id="3f979-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="3f979-109">Der Agent sendet dann dem Master-Replikationsdienst eine Nachricht mit dem aktuellen Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="3f979-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="3f979-110">Mit dem Cmdlet Get-CsManagementStoreReplicationStatus können Sie den Replikationsstatus für alle (oder alle) lync Server-Computer in Ihrer Organisation überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3f979-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="3f979-111">Wer kann dieses Cmdlet ausführen?</span><span class="sxs-lookup"><span data-stu-id="3f979-111">Who can run this cmdlet?</span></span> <span data-ttu-id="3f979-112">Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Get-CsManagementStoreReplicationStatus" lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3f979-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="3f979-113">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="3f979-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="3f979-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f979-114">See Also</span></span>


[<span data-ttu-id="3f979-115">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="3f979-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

