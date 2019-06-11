---
title: Überprüfen der Konnektivität zwischen internen Servern und Edgeservern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3868462036312be97484e41c69b51ae022b57c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="d6aea-102">Überprüfen der Konnektivität zwischen internen Servern und Edgeservern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6aea-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6aea-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d6aea-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d6aea-104">In lync Server 2013 war ein separater Überprüfungs-Assistent verfügbar, der die Überprüfung der Konnektivität zwischen Edge-Servern und internen Servern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d6aea-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="d6aea-105">In lync Server 2013 erfolgt die Überprüfung der Konnektivität automatisch, wenn Sie Ihre Edgeserver installieren.</span><span class="sxs-lookup"><span data-stu-id="d6aea-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="d6aea-106">Sie können die Replikation von Konfigurationsinformationen an den Edge überprüfen, indem Sie das Windows PowerShell-Cmdlet " **Get-CsManagementStoreReplicationStatus** " auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet (oder eine beliebige Domäne, der beigetreten ist. Computer, auf dem lync Server 2013-Core-Komponenten (OcsCore. msi) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d6aea-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="d6aea-107">Anfängliche Ergebnisse können den Status "falsch" anstelle von "true" für die Replikation angeben.</span><span class="sxs-lookup"><span data-stu-id="d6aea-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="d6aea-108">Wenn dies der Fall ist, führen Sie das Cmdlet **Invoke-CsManagementStoreReplication** aus, und lassen Sie die Replikation Zeit, bevor **Sie die Get-CsManagementStoreReplicationStatus** erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="d6aea-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="d6aea-109">Sie können die Konnektivität externer Benutzer separat überprüfen, einschließlich der Verwendung von Office Communications Server-Remote Verbindungsanalyse, um die Remotebenutzerkonnektivität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d6aea-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="d6aea-110">Ausführliche Informationen finden Sie unter [Überprüfen der Konnektivität für externe Benutzer in lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span><span class="sxs-lookup"><span data-stu-id="d6aea-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

