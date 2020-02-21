---
title: Überprüfen der Konnektivität zwischen internen Servern und Edge-Servern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd749aea86f610cee2671648e4e2ce1486cfba5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="1ee0a-102">Überprüfen der Konnektivität zwischen internen Servern und Edge-Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee0a-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ee0a-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1ee0a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1ee0a-104">In lync Server 2013 war ein separater Validierungs Assistent verfügbar, der die Überprüfung der Konnektivität zwischen Edge-Servern und internen Servern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ee0a-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="1ee0a-105">In lync Server 2013 wird die Überprüfung der Konnektivität bei der Installation Ihrer Edgeserver automatisch durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1ee0a-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="1ee0a-106">Sie können die Replikation von Konfigurationsinformationen auf den Edge überprüfen, indem Sie das Cmdlet Windows PowerShell **Get-CsManagementStoreReplicationStatus** auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet (oder auf einem beliebigen Computer in der Domäne, auf dem lync Server 2013 Core Components (OcsCore. msi) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="1ee0a-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="1ee0a-107">Anfängliche Ergebnisse geben möglicherweise den Status "false" anstelle von "true" für die Replikation an.</span><span class="sxs-lookup"><span data-stu-id="1ee0a-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="1ee0a-108">Wenn dies der Fall ist, führen Sie das **Invoke-CsManagementStoreReplication-** Cmdlet aus, und lassen Sie die Replikation vor dem erneuten Ausführen des **Get-CsManagementStoreReplicationStatus** Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="1ee0a-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="1ee0a-109">Sie können die Konnektivität für externe Benutzer separat überprüfen, einschließlich Verwendung der Remoteverbindungsanalyse von Office Communications Server zum Überprüfen der Remotebenutzerkonnektivität.</span><span class="sxs-lookup"><span data-stu-id="1ee0a-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="1ee0a-110">Ausführliche Informationen finden Sie unter [Überprüfen der Konnektivität für externe Benutzer in lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span><span class="sxs-lookup"><span data-stu-id="1ee0a-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

