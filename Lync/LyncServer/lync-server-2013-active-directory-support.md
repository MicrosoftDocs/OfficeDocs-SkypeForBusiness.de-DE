---
title: 'Lync Server 2013: Active Directory-Unterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9be3bda71e44d0e739fce3a8d01db9cb84e2b9e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="51323-102">Active Directory-Unterstützung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51323-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51323-103">_**Letztes Änderungsdatum des Themas:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="51323-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="51323-104">Die lokalen Topologien für Active Directory-Domänendienste, die von lync Server 2013 unterstützt werden, sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="51323-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="51323-105">Einzelne Gesamtstruktur mit einzelner Domäne</span><span class="sxs-lookup"><span data-stu-id="51323-105">Single forest with single domain</span></span>

  - <span data-ttu-id="51323-106">Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen</span><span class="sxs-lookup"><span data-stu-id="51323-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="51323-107">Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces</span><span class="sxs-lookup"><span data-stu-id="51323-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="51323-108">Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="51323-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="51323-109">Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="51323-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51323-110">Lync Server 2013 unterstützt keine Single-Label-Domänen.</span><span class="sxs-lookup"><span data-stu-id="51323-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="51323-111">Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne mit dem Namen " <STRONG>contoso. local</STRONG> " unterstützt, aber eine Stammdomäne mit einer einzelnen Bezeichnung, die " <STRONG>local</STRONG> " heißt, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51323-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="51323-112">Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einer <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>Bezeichnung" unter.</span><span class="sxs-lookup"><span data-stu-id="51323-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="51323-113">Lync Server 2013 unterstützt keine Umbenennung von Domänen.</span><span class="sxs-lookup"><span data-stu-id="51323-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="51323-114">Wenn Sie eine Domäne umbenennen müssen, in der lync Server bereitgestellt wird, müssen Sie zunächst lync Server deinstallieren, dann die Domäne umbenennen und dann lync Server erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="51323-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="51323-115">Ausführliche Informationen zu unterstützten Topologien und Anforderungen für lokale Bereitstellungen finden Sie unter [Anforderungen für Active Directory-Domänendienste, Unterstützung und Topologien in lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="51323-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

