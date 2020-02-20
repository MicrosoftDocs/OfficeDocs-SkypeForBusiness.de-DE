---
title: 'Lync Server 2013: Planen der Sicherheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd4fb61648e5d2adb8b49ceb56cc550fd0d2960e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="68269-102">Planen der Sicherheit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68269-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68269-103">_**Letztes Änderungsstand des Themas:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="68269-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="68269-104">Verwenden Sie diesen Abschnitt Sicherheit, um Sicherheitsrisiken für Ihre Bereitstellung von lync Server 2013 zu bewerten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="68269-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="68269-105">Selbst wenn Ihre lync Server 2013 Bereitstellung bescheiden ist, verfügen Sie wahrscheinlich über Komponenten in Ihrem Netzwerk, die über eine eigene Sicherheitsdokumentation verfügen.</span><span class="sxs-lookup"><span data-stu-id="68269-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="68269-106">Daher ist es unwahrscheinlich, dass in diesem Abschnitt alle Aspekte der Sicherheit für alle Komponenten und Bereiche behandelt werden, die für Ihre Bereitstellung relevant sind.</span><span class="sxs-lookup"><span data-stu-id="68269-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="68269-107">Verwenden Sie diesen Abschnitt als Ausgangspunkt, um die Sicherheit Ihrer lync Server 2013-Bereitstellung zu beheben.</span><span class="sxs-lookup"><span data-stu-id="68269-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="68269-108">Es enthält allgemeine Richtlinien und bewährte Methoden für die Bewertung und Verwaltung der häufigsten Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="68269-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="68269-109">Am Ende jedes Themas werden zusätzliche Produkt-und Sicherheitsressourcen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="68269-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68269-110">Sicherheit ist ein ständig weiterentwickeltes Thema.</span><span class="sxs-lookup"><span data-stu-id="68269-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="68269-111">Wenn neue Bedrohungen und Lösungen auftreten, sollten veraltete Dokumente, Lösungen, Methoden und Verfahren durch Aktuelles Material ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="68269-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="68269-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68269-112">In This Section</span></span>

  - [<span data-ttu-id="68269-113">Wichtige Sicherheitsfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68269-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="68269-114">Häufige Sicherheitsbedrohungen in der modernen Datenverarbeitung</span><span class="sxs-lookup"><span data-stu-id="68269-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="68269-115">Antivirus-Scan Ausschlüsse für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68269-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="68269-116">Sicherheitsframework für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68269-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="68269-117">Adressieren von Bedrohungen ihrer Kerninfrastruktur für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68269-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="68269-118">Bereitstellen eines SQL Server nicht standardmäßigen Ports und Alias in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68269-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

