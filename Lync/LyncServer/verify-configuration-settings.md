---
title: Überprüfen der Konfigurationseinstellungen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 931ec2c67c8cdf0d1856cce7264ee968e3ea96f0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508422"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="8f1ab-102">Überprüfen der Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="8f1ab-102">Verify configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f1ab-103">_**Letztes Änderungsstand des Themas:** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="8f1ab-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="8f1ab-104">Sie können die Replikation von Konfigurationsinformationen auf den Edgeserver überprüfen, indem Sie das Cmdlet "lync Server 2013 **Get-CsManagementStoreReplicationStatus** " auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer in der Domäne, auf dem lync Server 2013 Core Components (OcsCore.msi) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="8f1ab-105">Anfängliche Ergebnisse geben möglicherweise den Status "false" anstelle von "true" für die Replikation an.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="8f1ab-106">Wenn dies der Fall ist, führen Sie das **Invoke-CsManagementStoreReplication-** Cmdlet aus, und lassen Sie die Replikation vor dem erneuten Ausführen des **Get-CsManagementStoreReplicationStatus** Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

