---
title: 'Lync Server 2013: Unterstützte Active Directory-Topologien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 199191b8e87ba7f46956ff92fcda7239ff27dc5c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="254f8-102">Unterstützte Active Directory Topologien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="254f8-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="254f8-103">_**Letztes Änderungsstand des Themas:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="254f8-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="254f8-104">Lync Server 2013 unterstützt dieselben Active Directory-Domänendienste Topologien wie Microsoft lync Server 2010 und Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="254f8-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="254f8-105">Folgende Topologien werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="254f8-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="254f8-106">Einzelne Gesamtstruktur mit einzelner Domäne</span><span class="sxs-lookup"><span data-stu-id="254f8-106">Single forest with single domain</span></span>

  - <span data-ttu-id="254f8-107">Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen</span><span class="sxs-lookup"><span data-stu-id="254f8-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="254f8-108">Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces</span><span class="sxs-lookup"><span data-stu-id="254f8-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="254f8-109">Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="254f8-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="254f8-110">Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="254f8-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="254f8-111">Mehrere Gesamtstrukturen in einer lync-Ressourcengesamtstruktur-Topologie mit Exchange Online</span><span class="sxs-lookup"><span data-stu-id="254f8-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="254f8-112">Nachfolgend werden die in den Abbildungen in diesem Abschnitt verwendeten Symbole erläutert.</span><span class="sxs-lookup"><span data-stu-id="254f8-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="254f8-113">**Legende zu den Topologieabbildungen**</span><span class="sxs-lookup"><span data-stu-id="254f8-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="254f8-114">![Legende zu den Topologieabbildungen](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Legende zu den Topologieabbildungen")</span><span class="sxs-lookup"><span data-stu-id="254f8-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="254f8-115">Einzelne Gesamtstruktur, einzelne Domäne</span><span class="sxs-lookup"><span data-stu-id="254f8-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="254f8-116">Die einfachste Active Directory Topologie, die von lync Server, einer einzelnen Domänengesamtstruktur, unterstützt wird, ist eine allgemeine Topologie.</span><span class="sxs-lookup"><span data-stu-id="254f8-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="254f8-117">In der folgenden Abbildung wird eine lync Server-Bereitstellung in einer einzelnen Domäne Active Directory Topologie veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="254f8-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="254f8-118">**Topologie mit einer einzelnen Domäne**</span><span class="sxs-lookup"><span data-stu-id="254f8-118">**Single domain topology**</span></span>

<span data-ttu-id="254f8-119">![Topologie mit einer einzelnen Domäne](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologie mit einer einzelnen Domäne")</span><span class="sxs-lookup"><span data-stu-id="254f8-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="254f8-120">Einzelne Gesamtstruktur, mehrere Domänen</span><span class="sxs-lookup"><span data-stu-id="254f8-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="254f8-121">Eine andere Active Directory Topologie, die von lync Server unterstützt wird, ist eine einzelne Gesamtstruktur, die aus einer Stammdomäne und einer oder mehreren untergeordneten Domänen besteht.</span><span class="sxs-lookup"><span data-stu-id="254f8-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="254f8-122">Bei dieser Art von Active Directory Topologie kann die Domäne, in der Sie Benutzer erstellen, sich von der Domäne unterscheiden, in der Sie lync Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="254f8-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="254f8-123">Wenn Sie jedoch einen Front-End-Pool bereitstellen, müssen Sie alle Front-End-Server im Pool innerhalb einer einzelnen Domäne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="254f8-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="254f8-124">Lync Server-Unterstützung für Windows universelle Administratorgruppen ermöglicht die domänenübergreifende Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="254f8-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="254f8-125">Die folgende Abbildung zeigt eine Bereitstellung in einer einzelnen Gesamtstruktur mit mehreren Domänen.</span><span class="sxs-lookup"><span data-stu-id="254f8-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="254f8-126">In dieser Abbildung zeigt ein Benutzersymbol die Domäne an, in der das Benutzerkonto verwaltet wird, und der Pfeil verweist auf die Domäne, in der sich der lync Server Pool befindet.</span><span class="sxs-lookup"><span data-stu-id="254f8-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="254f8-127">Es gibt folgende Benutzerkonten:</span><span class="sxs-lookup"><span data-stu-id="254f8-127">User accounts include the following:</span></span>

  - <span data-ttu-id="254f8-128">Benutzerkonten in derselben Domäne wie der lync Server Pool</span><span class="sxs-lookup"><span data-stu-id="254f8-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="254f8-129">Benutzerkonten in einer anderen Domäne als der lync Server Pool</span><span class="sxs-lookup"><span data-stu-id="254f8-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="254f8-130">Benutzerkonten in einer untergeordneten Domäne der Domäne mit dem lync Server Pool</span><span class="sxs-lookup"><span data-stu-id="254f8-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="254f8-131">**Einzelne Gesamtstruktur mit mehreren Domänen**</span><span class="sxs-lookup"><span data-stu-id="254f8-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="254f8-132">![Einzelne Gesamtstruktur mit mehreren Domänen](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Einzelne Gesamtstruktur mit mehreren Domänen")</span><span class="sxs-lookup"><span data-stu-id="254f8-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="254f8-133">Einzelne Gesamtstruktur, mehrere Strukturen</span><span class="sxs-lookup"><span data-stu-id="254f8-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="254f8-134">Eine Gesamtstruktur mit mehreren Strukturen besteht aus zwei oder mehr Domänen, die unabhängige Strukturen und separate Active Directory-Namespaces definieren.</span><span class="sxs-lookup"><span data-stu-id="254f8-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="254f8-135">In der folgenden Abbildung ist eine einzelne Gesamtstruktur mit mehreren Strukturen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="254f8-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="254f8-136">In dieser Abbildung zeigt ein Benutzersymbol die Domäne, in der das Benutzerkonto verwaltet wird, eine durchgehende Linie verweist auf einen lync Server Pool, der sich in derselben oder einer anderen Domäne befindet, und eine gestrichelte Linie verweist auf lync Server Pool, der sich in einer anderen Struktur befindet.</span><span class="sxs-lookup"><span data-stu-id="254f8-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="254f8-137">Es gibt folgende Benutzerkonten:</span><span class="sxs-lookup"><span data-stu-id="254f8-137">User accounts include the following:</span></span>

  - <span data-ttu-id="254f8-138">Benutzerkonten in derselben Domäne wie der lync Server Pool</span><span class="sxs-lookup"><span data-stu-id="254f8-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="254f8-139">Benutzerkonten in einer anderen Domäne als der lync Server Pool (jedoch dieselbe Struktur wie)</span><span class="sxs-lookup"><span data-stu-id="254f8-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="254f8-140">Benutzerkonten in einer anderen Struktur als der lync Server Pool</span><span class="sxs-lookup"><span data-stu-id="254f8-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="254f8-141">**Einzelne Gesamtstruktur mit mehreren Strukturen**</span><span class="sxs-lookup"><span data-stu-id="254f8-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="254f8-142">![Einzelne Gesamtstruktur mit mehreren Strukturen](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Einzelne Gesamtstruktur mit mehreren Strukturen")</span><span class="sxs-lookup"><span data-stu-id="254f8-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="254f8-143">Mehrere Gesamtstrukturen, zentrale Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="254f8-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="254f8-144">Lync Server unterstützt mehrere Gesamtstrukturen, die in einer Topologie mit zentraler Gesamtstruktur konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="254f8-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="254f8-145">In Topologien mit zentraler Gesamtstruktur werden Kontaktobjekte in der zentralen Gesamtstruktur dazu verwendet, Benutzer in den anderen Gesamtstrukturen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="254f8-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="254f8-146">In der zentralen Gesamtstruktur werden auch die Benutzerkonten von anderen Benutzern in dieser Gesamtstruktur gehostet.</span><span class="sxs-lookup"><span data-stu-id="254f8-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="254f8-147">Ein Produkt zur Verzeichnissynchronisierung, wie z. B. Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), verwaltet den Lebenszyklus von Benutzerkonten innerhalb Ihrer Organisation: Wenn ein neues Benutzerkonto in einer der Gesamtstrukturen erstellt wird oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Programm zur Verzeichnissynchronisierung den entsprechenden Kontakt in der zentralen Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="254f8-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="254f8-148">Eine zentrale Gesamtstruktur bietet die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="254f8-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="254f8-149">Server mit lync Server werden in einer einzelnen Gesamtstruktur zentralisiert.</span><span class="sxs-lookup"><span data-stu-id="254f8-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="254f8-150">Benutzer können nach anderen Benutzern in einer beliebigen Gesamtstruktur suchen oder mit ihnen kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="254f8-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="254f8-151">Benutzer können Anwesenheitsinformationen zu anderen Benutzern in einer beliebigen Gesamtstruktur anzeigen.</span><span class="sxs-lookup"><span data-stu-id="254f8-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="254f8-152">Das Produkt zur Verzeichnissynchronisierung automatisiert das Hinzufügen und Löschen von Kontaktobjekten in der zentralen Gesamtstruktur, wenn Benutzerkonten erstellt oder entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="254f8-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="254f8-153">Die folgende Abbildung zeigt eine Topologie mit zentraler Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="254f8-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="254f8-154">In dieser Abbildung gibt es bidirektionale Vertrauensstellungen zwischen der Domäne, die lync Server hostet, der sich in der zentralen Gesamtstruktur befindet, und jeder Benutzerdomäne, die sich in einer separaten Gesamtstruktur befindet.</span><span class="sxs-lookup"><span data-stu-id="254f8-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="254f8-155">Das Schema in den separaten Benutzergesamtstrukturen muss nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="254f8-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="254f8-156">**Topologie mit einer zentralen Gesamtstruktur**</span><span class="sxs-lookup"><span data-stu-id="254f8-156">**Central forest topology**</span></span>

<span data-ttu-id="254f8-157">![Topologie mit einer zentralen Gesamtstruktur](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologie mit einer zentralen Gesamtstruktur")</span><span class="sxs-lookup"><span data-stu-id="254f8-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="254f8-158">Mehrere Gesamtstrukturen, Ressourcengesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="254f8-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="254f8-159">In einer Topologie mit Ressourcengesamtstruktur ist eine Gesamtstruktur für die Ausführung von Serveranwendungen dediziert, beispielsweise Exchange Server und lync Server.</span><span class="sxs-lookup"><span data-stu-id="254f8-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="254f8-160">Die Ressourcengesamtstruktur hostet die Serveranwendungen sowie eine synchronisierte Darstellung des aktiven Benutzerobjekts, enthält jedoch keine für die Anmeldung aktivierten Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="254f8-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="254f8-161">Die Ressourcengesamtstruktur fungiert als Umgebung für freigegebene Dienste für die weiteren Gesamtstrukturen, in denen sich Benutzerobjekte befinden.</span><span class="sxs-lookup"><span data-stu-id="254f8-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="254f8-162">Zwischen den Benutzergesamtstrukturen und der Ressourcengesamtstruktur besteht eine Vertrauensstellung auf Gesamtstrukturebene.</span><span class="sxs-lookup"><span data-stu-id="254f8-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="254f8-163">Wenn Sie lync Server in dieser Art von Topologie bereitstellen, erstellen Sie ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur für jedes Benutzerkonto in den Benutzergesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="254f8-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="254f8-164">Wenn Microsoft Exchange bereits in der Ressourcengesamtstruktur bereitgestellt wurde, sind die deaktivierten Benutzerkonten möglicherweise bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="254f8-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="254f8-165">Ein Produkt zur Verzeichnissynchronisierung, wie z. B. Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), verwaltet den Lebenszyklus von Benutzerkonten innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="254f8-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="254f8-166">Wenn ein neues Benutzerkonto in einer der Benutzerstrukturen erstellt wird oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Programm zur Verzeichnissynchronisierung das entsprechende Benutzerobjekt in der Ressourcengesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="254f8-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="254f8-p108">Diese Topologie kann verwendet werden, um eine freigegebene Infrastruktur für Dienste in Organisationen bereitzustellen, in denen mehrere Gesamtstrukturen verwaltet werden, oder um die Verwaltung von Active Directory-Objekten von anderen Verwaltungsaufgaben zu trennen. Diese Topologie wird häufig von Unternehmen eingesetzt, die die Active Directory-Verwaltung aus Sicherheitsgründen isolieren müssen.</span><span class="sxs-lookup"><span data-stu-id="254f8-p108">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration. Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="254f8-169">Diese Topologie bietet den Vorteil, dass das Active Directory-Schema lediglich in einer einzelnen Gesamtstruktur (der Ressourcengesamtstruktur) erweitert werden muss.</span><span class="sxs-lookup"><span data-stu-id="254f8-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="254f8-170">Die folgende Abbildung zeigt eine Topologie mit Ressourcengesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="254f8-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="254f8-171">**Ressourcengesamtstruktur-Topologie**</span><span class="sxs-lookup"><span data-stu-id="254f8-171">**Resource forest topology**</span></span>

<span data-ttu-id="254f8-172">![Active Directory Topologie der Ressourcengesamtstruktur](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Topologie der Ressourcengesamtstruktur")</span><span class="sxs-lookup"><span data-stu-id="254f8-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="254f8-173">Mehrere Gesamtstrukturen in einer lync-Ressourcengesamtstruktur-Topologie mit Exchange Online</span><span class="sxs-lookup"><span data-stu-id="254f8-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="254f8-174">In dieser Topologie befinden sich eine oder mehrere Gesamtstrukturen lokal und sind dem Hosten Active Directory Benutzerkonten gewidmet.</span><span class="sxs-lookup"><span data-stu-id="254f8-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="254f8-175">Die Ressourcengesamtstruktur befindet sich außerhalb des Standorts und wird von einem Drittanbieter-Hostinganbieter verwaltet.</span><span class="sxs-lookup"><span data-stu-id="254f8-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="254f8-176">Die Ressourcengesamtstruktur enthält nur die lync Server-Bereitstellung und eine synchronisierte Replikation der Benutzerkonten aus der lokalen Benutzerkonten-Gesamtstruktur (en).</span><span class="sxs-lookup"><span data-stu-id="254f8-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="254f8-177">Sie enthält keine Anmelde aktivierten Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="254f8-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="254f8-178">Exchange wird entweder in den lokalen Benutzerkonten-Gesamtstrukturen bereitgestellt, die zusammen mit Exchange Online (Hybrid) integriert sind, oder e-Mail-Dienste für die lokalen Benutzerkonten werden ausschließlich von Exchange Online bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="254f8-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="254f8-179">Die Ressourcengesamtstruktur fungiert als Umgebung für gemeinsame Dienste für die lokalen Active Directory Gesamtstruktur (en), in der sich Benutzerobjekte befinden.</span><span class="sxs-lookup"><span data-stu-id="254f8-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="254f8-180">Die Benutzerkontengesamtstruktur (en) haben eine unidirektionale Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="254f8-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="254f8-181">Wenn Sie lync Server in dieser Art von Topologie bereitstellen, erstellen Sie ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur für jedes Benutzerkonto in den Benutzergesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="254f8-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="254f8-182">Ein Produkt zur Verzeichnissynchronisierung, wie z. B. Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), verwaltet den Lebenszyklus von Benutzerkonten innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="254f8-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="254f8-183">Wenn ein neues Benutzerkonto in einer der Benutzerstrukturen erstellt wird oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Programm zur Verzeichnissynchronisierung das entsprechende Benutzerobjekt in der Ressourcengesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="254f8-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="254f8-184">Weitere Informationen zum Konfigurieren einer Bereitstellung mit mehreren Gesamtstrukturen finden Sie unter [Deploying lync in a Multi-Forest Architecture (Partner Hosted lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="254f8-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

