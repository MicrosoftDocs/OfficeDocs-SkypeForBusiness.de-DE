---
title: 'Lync Server 2013: Active Directory Infrastrukturanforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14980b886ac9a00b9ea23a0d915bc34ac3956c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="e81fa-102">Active Directory Infrastrukturanforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e81fa-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e81fa-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e81fa-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e81fa-104">Bevor Sie mit dem vorbereiten Active Directory-Domänendienste für lync Server 2013 beginnen, müssen Sie sicherstellen, dass Ihre Active Directory Infrastruktur die folgenden Voraussetzungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="e81fa-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="e81fa-105">Alle Domänencontroller (einschließlich aller globalen Katalogserver) in der Gesamtstruktur, in der Sie lync Server bereitstellen, führen eines der folgenden Betriebssysteme aus:</span><span class="sxs-lookup"><span data-stu-id="e81fa-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="e81fa-106">Windows Server 2012 R2-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="e81fa-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="e81fa-107">Windows Server 2012 Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="e81fa-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="e81fa-108">Windows Server 2008 R2-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="e81fa-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="e81fa-109">Windows Server 2008-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="e81fa-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="e81fa-110">Windows Server 2008 Enterprise 32-Bit</span><span class="sxs-lookup"><span data-stu-id="e81fa-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="e81fa-111">32-Bit- oder 64-Bit-Version von Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="e81fa-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="e81fa-112">32-Bit-oder 64-Bit-Versionen des Windows Server 2003-Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="e81fa-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="e81fa-113">Alle Domänen, in denen Sie lync Server bereitstellen, werden auf eine Domänenfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e81fa-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="e81fa-114">Die Gesamtstruktur, in der Sie lync Server bereitstellen, wird auf eine Gesamtstrukturfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e81fa-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e81fa-115">Informationen zum Ändern der Domänen-oder Gesamtstrukturfunktionsebene finden Sie unter "Heraufstufen von Domänen-und Gesamtstruktur <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>Funktionsebenen" in der TechNet-Bibliothek unter.</span><span class="sxs-lookup"><span data-stu-id="e81fa-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="e81fa-116">Ein globaler Katalog wird in jeder Domäne bereitgestellt, in der Sie lync Server Computer oder Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e81fa-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="e81fa-117">Lync Server 2013 unterstützt die universellen Gruppen in den Betriebssystemen Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 und Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e81fa-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="e81fa-118">Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen.</span><span class="sxs-lookup"><span data-stu-id="e81fa-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="e81fa-119">Die universelle Gruppenunterstützung in Kombination mit der Administrator Delegierung vereinfacht die Verwaltung einer lync Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e81fa-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="e81fa-120">Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e81fa-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

