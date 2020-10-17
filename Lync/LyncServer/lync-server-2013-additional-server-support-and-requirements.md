---
title: 'Lync Server 2013: zusätzliche Server Unterstützung und-Anforderungen'
description: 'Lync Server 2013: zusätzliche Server Unterstützung und-Anforderungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3af9b3489ba62b3b2dc7cf4fa16cabfe80003e1e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542331"
---
# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="a9bff-103">Zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9bff-103">Additional server support and requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9bff-104">_**Letztes Änderungsstand des Themas:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="a9bff-104">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="a9bff-105">Zusätzlich zu der in den anderen Abschnitten dieser Unterstützungsdokumentation beschriebenen Softwareunterstützung verfügt lync Server 2013 über die folgenden Supporteinschränkungen:</span><span class="sxs-lookup"><span data-stu-id="a9bff-105">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="a9bff-106">Lync Server 2013 unterstützt Domain Name System (DNS)-und Hardwarelastenausgleich für bestimmte Server Rollen.</span><span class="sxs-lookup"><span data-stu-id="a9bff-106">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="a9bff-107">Außerdem wird der Anwendungslastenausgleich für Vermittlungsserver nach Bedarf unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9bff-107">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="a9bff-108">Ausführliche Informationen dazu, in welchen Fällen welcher Lastenausgleich eingesetzt wird, finden Sie in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a9bff-108">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="a9bff-109">Lync Server 2013 verwendet das dlx (Distribution List Expansion Protocol), um Verteilerlisten zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a9bff-109">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="a9bff-110">Dieses Protokoll legt außerdem die Webdienstmethode fest, die zum Erhalten der Mitgliedschaft in einer Verteilerliste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9bff-110">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="a9bff-111">Exchange Server unterstützt dynamische Gruppen, denen keine Mitglieder statisch zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="a9bff-111">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="a9bff-112">Stattdessen werden darin Abfragen gespeichert, die beim Erweitern der Gruppe ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="a9bff-112">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="a9bff-113">DLX unterstützt keine dynamischen Verteilerlisten.</span><span class="sxs-lookup"><span data-stu-id="a9bff-113">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="a9bff-114">Diese dlx-Einschränkung gilt für alle Versionen von lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9bff-114">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="a9bff-115">Der Assistent zum Aktivieren von Benutzern unterstützt nicht die automatische Konvertierung nicht-englischer Zeichen in einen SIP-kompatiblen URI, daher müssen Sie die SIP-Adresse manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="a9bff-115">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="a9bff-116">Für Server, auf denen Antivirensoftware installiert ist, finden Sie unter [Antivirus Scanning Ausschlüsse für lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) für vorgeschlagene Viren Ausschlüsse und andere sicherheitsrelevante Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="a9bff-116">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="a9bff-117">Wenn Sie IPsec verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von Audio- und Videodaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9bff-117">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="a9bff-118">Ausführliche Informationen finden Sie unter [IPSec Exceptions in lync Server 2013](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a9bff-118">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="a9bff-119">Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="a9bff-119">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="a9bff-120">Ausführliche Informationen zum Implementieren von QoS finden Sie unter [Managing Quality of Service (QoS) in lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a9bff-120">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="a9bff-121">Die Verwendung der Betriebssystemfirewall wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9bff-121">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="a9bff-122">Lync Server 2013 verwaltet die Firewall-Ausnahmen für die Betriebssystem Firewall, mit Ausnahme von Microsoft SQL Server-Datenbanksoftware.</span><span class="sxs-lookup"><span data-stu-id="a9bff-122">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="a9bff-123">Ausführliche Informationen zu den Anforderungen hinsichtlich der Firewall für SQL Server finden Sie in der SQL Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a9bff-123">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="a9bff-124">Die zum Implementieren der Unterstützung für den externen Benutzerzugriff verwendeten externen Schnittstellen müssen sich in einem separaten Subnetz befinden, *nicht* in demselben Netzwerk wie die internen Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="a9bff-124">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="a9bff-125">Die XMPP-Funktion von lync Server 2013 wird von Microsoft für den Partnerverbund mit Google Talk getestet und unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9bff-125">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="a9bff-126">Wenden Sie sich für alle anderen XMPP-Systeme an den Drittanbieter, um zu überprüfen, ob der Partnerverbund mit lync Server 2013 und für alle Bereitstellungs-oder Problem Behandlungsempfehlungen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a9bff-126">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="a9bff-127">Mit der Veröffentlichung lync Server 2013 kumulativen Updates: Juli 2013 unterstützt lync Server 2013 jetzt die zweistufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a9bff-127">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="a9bff-128">Weitere Informationen finden Sie unter [zweistufige Authentifizierung in lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a9bff-128">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="a9bff-129">Für die meisten internen Server ist ein Zertifikattyp erforderlich, der als **Open Authentication** (OAuth) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a9bff-129">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="a9bff-130">Sie müssen während der **Anforderungs-, install-und Assign** -Phase des lync Server-Bereitstellungs-Assistenten ein OAuth-Zertifikat anfordern und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a9bff-130">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="a9bff-131">Die Mindestgröße für einen OAuth-Zertifikatschlüssel beträgt 1024 Bit.</span><span class="sxs-lookup"><span data-stu-id="a9bff-131">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="a9bff-132">Eine Warnung wird möglicherweise angezeigt, wenn Sie ein Zertifikat mit einer Schlüssellänge von weniger als 2048 Bits anfordern.</span><span class="sxs-lookup"><span data-stu-id="a9bff-132">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="a9bff-133">Um potenzielle Probleme zu vermeiden, falls eine Schlüssellänge von 2048 anstelle von Warnungen erzwungen wird, wird dringend empfohlen, immer eine Schlüssellänge von 2048 für OAuth-Zertifikate zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9bff-133">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="a9bff-134">Lync Server 2013 und Microsoft Exchange Server 2010 Service Pack 1 (SP1) arbeiten mit Unterstützung für FIPS (Federal Information Processing Standard) 140-2-Algorithmen, wenn die Windows Server 2008 R2-Betriebssysteme für die Verwendung der FIPS 140-2-Algorithmen für die Systemkryptografie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="a9bff-134">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="a9bff-135">Um die FIPS-Unterstützung zu implementieren, müssen Sie jeden Server konfigurieren, der lync Server 2013 ausführt, um ihn zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a9bff-135">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="a9bff-136">Ausführliche Informationen zu FIPS-kompatiblen Algorithmen und zur Implementierung der FIPS-Unterstützung finden Sie im Microsoft Knowledge Base-Artikel 811833, "System Cryptography: Verwenden von FIPS-kompatiblen Algorithmen für Verschlüsselung, Hashing und Signieren von Sicherheitseinstellungen in Windows XP und höheren Windows-Versionen unter [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) .</span><span class="sxs-lookup"><span data-stu-id="a9bff-136">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="a9bff-137">Ausführliche Informationen zur Unterstützung von FIPS 140-2 und zu Einschränkungen in Exchange 2010 finden Sie unter "Exchange 2010 SP1 und Unterstützung für FIPS-konforme Algorithmen" unter [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) .</span><span class="sxs-lookup"><span data-stu-id="a9bff-137">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="a9bff-138">Lync Server 2013 erfordert die Installation anderer Software auf bestimmten Komponenten vor oder während der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a9bff-138">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="a9bff-139">Dies umfasst Software, die mit dem Betriebssystem, herunterladbare Software und Software zur Verfügung steht, die bei der Installation von lync Server 2013 automatisch installiert wird.</span><span class="sxs-lookup"><span data-stu-id="a9bff-139">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="a9bff-140">In der folgenden Liste wird zusätzliche Software aufgeführt, die möglicherweise erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="a9bff-140">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="a9bff-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="a9bff-141">Windows Update</span></span>

  - <span data-ttu-id="a9bff-142">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="a9bff-142">Windows Identity Foundation</span></span>

  - <span data-ttu-id="a9bff-143">Microsoft .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="a9bff-143">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="a9bff-144">Microsoft Visual C++ 2012 Redistributable</span><span class="sxs-lookup"><span data-stu-id="a9bff-144">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a9bff-145">Microsoft Visual C++ 2012 Redistributable wird bei der Installation von lync Server 2013 automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="a9bff-145">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="a9bff-146">Sie sollten keine andere Version installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9bff-146">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="a9bff-147">URL Rewrite Module Version 2.0 Redistributable</span><span class="sxs-lookup"><span data-stu-id="a9bff-147">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="a9bff-148">Windows Media Format-Laufzeitkomponente</span><span class="sxs-lookup"><span data-stu-id="a9bff-148">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="a9bff-149">Windows PowerShell Version 3,0</span><span class="sxs-lookup"><span data-stu-id="a9bff-149">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="a9bff-150">Microsoft Silverlight 4-Browser-Plug-In (Silverlight 4.0.50524.0 oder neueste Version für die Lync Server-Systemsteuerung)</span><span class="sxs-lookup"><span data-stu-id="a9bff-150">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="a9bff-151">Active Directory-Domänendienste Tools</span><span class="sxs-lookup"><span data-stu-id="a9bff-151">Active Directory Domain Services tools</span></span>

<span data-ttu-id="a9bff-152">Einige dieser Softwareanforderungen gelten nur für bestimmte Serverrollen oder Komponenten.</span><span class="sxs-lookup"><span data-stu-id="a9bff-152">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="a9bff-153">Ausführliche Informationen zu diesen Softwareanforderungen finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a9bff-153">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

