---
title: 'Lync Server 2013: Active Directory-Domänendienste-Unterstützung'
description: 'Lync Server 2013: Active Directory-Domänendienste Support.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2a85bab90557c28c4802721d4202f6188cb3f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558681"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="63453-103">Active Directory-Domänendienste-Unterstützung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63453-103">Active Directory Domain Services support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63453-104">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="63453-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="63453-105">Lync Server 2013 verwendet den zentralen Verwaltungsspeicher zum Speichern von Konfigurationsdaten für Server und Dienste, anstatt sich auf Active Directory-Domänendienste für diese Informationen zu verlassen, wie in der Vergangenheit.</span><span class="sxs-lookup"><span data-stu-id="63453-105">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="63453-106">In lync Server 2013 wird weiterhin Folgendes in AD DS gespeichert:</span><span class="sxs-lookup"><span data-stu-id="63453-106">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="63453-107">**Schemaerweiterungen**</span><span class="sxs-lookup"><span data-stu-id="63453-107">**Schema extensions**</span></span>
    
      - <span data-ttu-id="63453-108">Benutzerobjekterweiterungen</span><span class="sxs-lookup"><span data-stu-id="63453-108">User object extensions</span></span>
    
      - <span data-ttu-id="63453-109">Erweiterungen für lync Server 2010-und Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität mit früheren unterstützten Versionen</span><span class="sxs-lookup"><span data-stu-id="63453-109">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="63453-110">**Daten** (in lync Server 2013 Extended Schema und in vorhandenen Klassen gespeichert)</span><span class="sxs-lookup"><span data-stu-id="63453-110">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="63453-111">SIP-URI des Benutzers und andere Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="63453-111">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="63453-112">Kontaktobjekte für Anwendungen (beispielsweise die Reaktionsgruppenanwendung und die Konferenzzentrale)</span><span class="sxs-lookup"><span data-stu-id="63453-112">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="63453-113">Aus Gründen der Abwärtskompatibilität veröffentlichte Daten</span><span class="sxs-lookup"><span data-stu-id="63453-113">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="63453-114">Einen Dienststeuerungspunkt (Service Control Points, SCP) für den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="63453-114">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="63453-115">Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)</span><span class="sxs-lookup"><span data-stu-id="63453-115">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="63453-116">In diesem Abschnitt werden die AD DS Supportanforderungen für lync Server 2013 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="63453-116">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="63453-117">Ausführliche Informationen zur Topologie-Unterstützung finden Sie unter [Supported Active Directory Topologies in lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="63453-117">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="63453-118">Unterstützte Domänen Controller-Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="63453-118">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="63453-119">Lync Server 2013 unterstützt Domänencontroller, die die folgenden Betriebssysteme ausführen:</span><span class="sxs-lookup"><span data-stu-id="63453-119">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="63453-120">Windows Server 2012 R2-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="63453-120">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="63453-121">Windows Server 2012 Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="63453-121">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="63453-122">Windows Server 2008 R2-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="63453-122">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="63453-123">Windows Server 2008-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="63453-123">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="63453-124">Windows Server 2008 Enterprise 32-Bit</span><span class="sxs-lookup"><span data-stu-id="63453-124">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="63453-125">Die 32-Bit-oder 64-Bit-Versionen des Windows Server 2003 R2-Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="63453-125">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="63453-126">Die 32-Bit-oder 64-Bit-Versionen des Windows Server 2003 Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="63453-126">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="63453-127">Gesamtstruktur-und Domänenfunktionsebene</span><span class="sxs-lookup"><span data-stu-id="63453-127">Forest and Domain Functional Level</span></span>

<span data-ttu-id="63453-128">Sie müssen alle Domänen, in denen Sie lync Server 2013 bereitstellen, auf einer Domänenfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 auslösen.</span><span class="sxs-lookup"><span data-stu-id="63453-128">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="63453-129">Alle Gesamtstrukturen, in denen Sie lync Server 2013 bereitstellen, müssen auf eine Gesamtstrukturfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgestuft werden.</span><span class="sxs-lookup"><span data-stu-id="63453-129">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="63453-130">Unterstützung für Read-Only Domänencontroller</span><span class="sxs-lookup"><span data-stu-id="63453-130">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="63453-131">Lync Server 2013 unterstützt Active Directory-Domänendienste-Bereitstellungen, die schreibgeschützte Domänencontroller oder schreibgeschützte globale Katalogserver enthalten, sofern schreibbare Domänencontroller verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="63453-131">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="63453-132">Domänennamen</span><span class="sxs-lookup"><span data-stu-id="63453-132">Domain Names</span></span>

<span data-ttu-id="63453-133">Lync Server bietet keine Unterstützung für Domänen mit einfacher Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="63453-133">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="63453-134">Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne namens **contoso.local** unterstützt, eine Stammdomäne namens **local** hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="63453-134">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="63453-135">Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einfacher Bezeichnung" unter [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) .</span><span class="sxs-lookup"><span data-stu-id="63453-135">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63453-136">Das Umbenennen von Domänen wird von lync Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63453-136">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="63453-137">Wenn Sie eine Domäne umbenennen müssen, in der lync Server bereitgestellt wird, müssen Sie zunächst lync Server deinstallieren und dann die Domäne umbenennen und dann lync Server erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="63453-137">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="63453-138">AD DS Umgebungen gesperrt</span><span class="sxs-lookup"><span data-stu-id="63453-138">Locked Down AD DS Environments</span></span>

<span data-ttu-id="63453-139">In einer gesperrten AD DS Umgebung werden Benutzer und Computer Objekte häufig in bestimmten Organisationseinheiten (Organizational Units, OUs) mit deaktivierten Berechtigungen vererbt, um eine sichere administrative Delegierung zu gewährleisten und die Verwendung von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) zum Erzwingen von Sicherheitsrichtlinien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="63453-139">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="63453-140">Lync Server 2013 können in einer gesperrten Active Directory Umgebung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="63453-140">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="63453-141">Ausführliche Informationen dazu, was für die Bereitstellung von lync Server in einer gesperrten Umgebung erforderlich ist, finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="63453-141">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

