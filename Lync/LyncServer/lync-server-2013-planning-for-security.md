---
title: 'Lync Server 2013: Planen für mehr Sicherheit'
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
ms.openlocfilehash: 02028b3ed63fe8f5cd40fd118bd36c73af9d15cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="4598a-102">Planen für mehr Sicherheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4598a-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4598a-103">_**Letztes Änderungsdatum des Themas:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="4598a-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="4598a-104">Verwenden Sie diesen Abschnitt "Sicherheit", um Sicherheitsrisiken für Ihre Bereitstellung von lync Server 2013 zu bewerten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4598a-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="4598a-105">Auch wenn Ihre lync Server 2013-Bereitstellung bescheiden ist, verfügen Sie wahrscheinlich über Komponenten in Ihrem Netzwerk, die über eine eigene Sicherheitsdokumentation verfügen.</span><span class="sxs-lookup"><span data-stu-id="4598a-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="4598a-106">Daher ist es unwahrscheinlich, dass in diesem Abschnitt alle Aspekte der Sicherheit für alle Komponenten und Bereiche behandelt werden, die für Ihre Bereitstellung relevant sind.</span><span class="sxs-lookup"><span data-stu-id="4598a-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="4598a-107">Verwenden Sie diesen Abschnitt als Ausgangspunkt, um die Sicherheit Ihrer lync Server 2013-Bereitstellung zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4598a-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="4598a-108">Sie enthält allgemeine Richtlinien und bewährte Methoden für die Bewertung und Verwaltung der häufigsten Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="4598a-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="4598a-109">Am Ende eines jeden Themas werden weitere Produkt-und Sicherheitsressourcen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4598a-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4598a-110">Sicherheit ist ein sich ständig weiter entwickelndes Thema.</span><span class="sxs-lookup"><span data-stu-id="4598a-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="4598a-111">Wenn neue Bedrohungen und Lösungen entstehen, sollten veraltete Dokumente, Lösungen, Methoden und Verfahren durch aktuelle Materialien ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="4598a-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4598a-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4598a-112">In This Section</span></span>

  - [<span data-ttu-id="4598a-113">Wichtige Sicherheitsfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4598a-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="4598a-114">Häufige Sicherheitsrisiken in der modernen Computernutzung</span><span class="sxs-lookup"><span data-stu-id="4598a-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="4598a-115">Ausnahmen in Virenschutzprogrammen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4598a-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="4598a-116">Sicherheitsframework für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4598a-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="4598a-117">Behandeln von Bedrohungen für Ihre Kerninfrastruktur für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4598a-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="4598a-118">Bereitstellen eines nicht standardmäßigen SQL Server-Ports und -Alias in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4598a-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

