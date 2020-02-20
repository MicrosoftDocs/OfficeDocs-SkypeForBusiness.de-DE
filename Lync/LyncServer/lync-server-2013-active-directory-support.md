---
title: Unterstützung von lync Server 2013 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 193ebaedd11c239ba380937da3051ec8336578a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="90a48-102">Active Directory-Unterstützung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90a48-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90a48-103">_**Letztes Änderungsstand des Themas:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="90a48-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="90a48-104">Die Active Directory-Domänendienste lokalen Topologien, die von lync Server 2013 unterstützt werden, lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="90a48-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="90a48-105">Einzelne Gesamtstruktur mit einzelner Domäne</span><span class="sxs-lookup"><span data-stu-id="90a48-105">Single forest with single domain</span></span>

  - <span data-ttu-id="90a48-106">Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen</span><span class="sxs-lookup"><span data-stu-id="90a48-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="90a48-107">Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces</span><span class="sxs-lookup"><span data-stu-id="90a48-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="90a48-108">Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="90a48-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="90a48-109">Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="90a48-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90a48-110">Lync Server 2013 bietet keine Unterstützung für Domänen mit einfacher Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="90a48-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="90a48-111">Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne namens " <STRONG>contoso. local</STRONG> " unterstützt, aber eine Stammdomäne mit einer einzelnen Bezeichnung namens " <STRONG>local</STRONG> " wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="90a48-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="90a48-112">Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einfacher <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>Bezeichnung" unter.</span><span class="sxs-lookup"><span data-stu-id="90a48-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="90a48-113">Das Umbenennen von Domänen wird von lync Server 2013 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="90a48-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="90a48-114">Wenn Sie eine Domäne umbenennen müssen, in der lync Server bereitgestellt wird, müssen Sie zunächst lync Server deinstallieren und dann die Domäne umbenennen und dann lync Server erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="90a48-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="90a48-115">Ausführliche Informationen zu unterstützten Topologien und Anforderungen für lokale Bereitstellungen finden Sie unter [Active Directory-Domänendienste Anforderungen, Unterstützung und Topologien in lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="90a48-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

