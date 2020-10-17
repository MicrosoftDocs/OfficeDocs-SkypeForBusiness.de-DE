---
title: 'Lync Server 2013: zurückschlagen eines Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2ad8ee15d0242a5512284e00064dfe9b49c41c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522362"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="932f9-102">Zurückschlagen eines Pools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="932f9-102">Failing back a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="932f9-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="932f9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="932f9-104">Nachdem der ausgefallene Pool (d. h. Pool1 im vorliegenden Beispiel) wieder online ist, müssen Sie die folgenden Schritte ausführen, um Ihre Bereitstellung wieder in den normalen Betriebszustand zurückzuversetzen.</span><span class="sxs-lookup"><span data-stu-id="932f9-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="932f9-p101">Beachten Sie, dass der Failback-Prozess einige Zeit in Anspruch nehmen kann. So würde zum Beispiel ein Pool mit 20.000 Benutzern bis zu 60 Minuten benötigen.</span><span class="sxs-lookup"><span data-stu-id="932f9-p101">Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="932f9-107">Führen Sie für die Benutzer, die ursprünglich in Pool1 untergebracht waren und auf Pool2 verlegt wurden, ein Failback mit dem folgenden Cmdlet durch:</span><span class="sxs-lookup"><span data-stu-id="932f9-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="932f9-108">Weitere Schritte sind nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="932f9-108">No other steps are necessary.</span></span> <span data-ttu-id="932f9-109">Wenn Sie den zentralen Verwaltungs Server nicht erfolgreich ausgeführt haben, können Sie ihn in Pool2 belassen.</span><span class="sxs-lookup"><span data-stu-id="932f9-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

