---
title: Überprüfen der Konfigurationseinstellungen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd35ed2d153bb33f93f6533e9eacb0ffab7788f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="460c2-102">Überprüfen der Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="460c2-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="460c2-103">_**Letztes Änderungsdatum des Themas:** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="460c2-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="460c2-104">Sie können die Replikation von Konfigurationsinformationen auf dem Edgeserver überprüfen, indem Sie das lync Server 2013-Cmdlet " **Get-CsManagementStoreReplicationStatus** " auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einer beliebigen Domäne verbundener Computer, auf dem die lync Server 2013-Core-Komponenten (OcsCore. msi) installiert sind.</span><span class="sxs-lookup"><span data-stu-id="460c2-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="460c2-105">Anfängliche Ergebnisse können den Status "falsch" anstelle von "true" für die Replikation angeben.</span><span class="sxs-lookup"><span data-stu-id="460c2-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="460c2-106">Wenn dies der Fall ist, führen Sie das Cmdlet **Invoke-CsManagementStoreReplication** aus, und lassen Sie die Replikation Zeit, bevor **Sie die Get-CsManagementStoreReplicationStatus** erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="460c2-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

