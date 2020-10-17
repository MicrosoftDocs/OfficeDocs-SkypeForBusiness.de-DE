---
title: Überprüfen der Replikation von Konfigurationseinstellungen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 850ee0365496932fec4476a50607774e6ceb1ee1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508442"
---
# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="c1d4b-102">Überprüfen der Replikation von Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="c1d4b-102">Validate replication of configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1d4b-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c1d4b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c1d4b-104">Sie können die Replikation von Konfigurationsinformationen in der Edgeserver überprüfen, indem Sie lync Server 2013 das Cmdlet **Get-CsManagementStoreReplicationStatus** auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer in der Domäne, auf dem lync Server 2013 Kernkomponenten installiert sind.</span><span class="sxs-lookup"><span data-stu-id="c1d4b-104">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="c1d4b-105">Anfängliche Ergebnisse geben möglicherweise den Status "false" anstelle von "true" für die Replikation an.</span><span class="sxs-lookup"><span data-stu-id="c1d4b-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="c1d4b-106">Wenn dies der Fall ist, führen Sie das Cmdlet **Invoke-CsManagementStoreReplication** aus, und lassen Sie die Replikation Zeit, bevor Sie das Cmdlet **Get-CsManagementStoreReplicationStatus** erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="c1d4b-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

