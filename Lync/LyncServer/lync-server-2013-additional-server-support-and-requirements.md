---
title: 'Lync Server 2013: Zusätzliche Serverunterstützung und Anforderungen'
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
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="95374-102">Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95374-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95374-103">_**Letztes Änderungsdatum des Themas:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="95374-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="95374-104">Zusätzlich zu der Softwareunterstützung, die in den anderen Abschnitten dieser Dokumentation zur unter Stützungs Dokumentation beschrieben wird, weist lync Server 2013 die folgenden Supporteinschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="95374-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="95374-105">Lync Server 2013 unterstützt DNS (Domain Name System) und den Hardwarelastenausgleich für bestimmte Server Rollen.</span><span class="sxs-lookup"><span data-stu-id="95374-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="95374-106">Sie unterstützt auch den Anwendungslastenausgleich für Vermittlungsserver, falls dies angemessen ist.</span><span class="sxs-lookup"><span data-stu-id="95374-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="95374-107">Einzelheiten zur Verwendung der einzelnen Informationen finden Sie in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="95374-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="95374-108">Lync Server 2013 verwendet das dlx (Distribution List Expansion Protocol) zum Erweitern von Verteilerlisten.</span><span class="sxs-lookup"><span data-stu-id="95374-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="95374-109">Dieses Protokoll gibt auch die Webdienstmethode an, die zum Abrufen der Mitgliedschaft einer Verteilerliste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95374-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="95374-110">Microsoft Exchange Server unterstützt dynamische Gruppen, denen keine Mitglieder statisch zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="95374-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="95374-111">Stattdessen werden Abfragen gespeichert, die ausgewertet werden, wenn die Gruppe erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="95374-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="95374-112">DLX unterstützt keine dynamischen Verteilerlisten.</span><span class="sxs-lookup"><span data-stu-id="95374-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="95374-113">Diese dlx-Einschränkung gilt für alle Versionen von lync Server.</span><span class="sxs-lookup"><span data-stu-id="95374-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="95374-114">Der Assistent zum Aktivieren des Benutzers unterstützt keine automatische Konvertierung von nicht englischen Zeichen in einen SIP-kompatiblen URI, daher müssen Sie die SIP-Adresse manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="95374-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="95374-115">Informationen zu Servern, auf denen Antivirus-Software ausgeführt wird, finden Sie unter [Ausschlüsse für Antivirus-Scans für lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) für vorgeschlagene Viren Ausschlüsse und andere sicherheitsrelevante Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="95374-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="95374-116">Wenn Sie IPSec verwenden, empfiehlt es sich, IPSec über die für Audio-und Videodatenverkehr verwendeten Portbereiche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="95374-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="95374-117">Ausführliche Informationen finden Sie unter [IPsec-Ausnahmen in lync Server 2013](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="95374-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="95374-118">Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="95374-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="95374-119">Ausführliche Informationen zum Implementieren von QoS finden Sie unter [Verwalten von Quality of Service (QoS) in lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="95374-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="95374-120">Die Verwendung der Firewall des Betriebssystems wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="95374-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="95374-121">Lync Server 2013 verwaltet die Firewall-Ausnahmen für die Betriebssystem Firewall, mit Ausnahme der Microsoft SQL Server-Datenbanksoftware.</span><span class="sxs-lookup"><span data-stu-id="95374-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="95374-122">Details zu den Anforderungen der SQL Server-Firewall finden Sie in der SQL Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="95374-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="95374-123">Die externen Schnittstellen, die zum Implementieren der Unterstützung für den Zugriff durch externe Benutzer verwendet werden, müssen sich in einem separaten Subnetz befinden, *nicht* im gleichen Netzwerk wie die internen Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="95374-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="95374-p106">Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="95374-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="95374-126">Mit der Veröffentlichung von lync Server 2013 kumulativen Updates: Juli 2013 unterstützt lync Server 2013 jetzt die zweistufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="95374-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="95374-127">Weitere Informationen finden Sie unter [zweistufige Authentifizierung in lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="95374-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="95374-128">Für die meisten internen Server ist ein Zertifikattyp erforderlich, der als **Open Authentication** (OAuth) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="95374-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="95374-129">Sie müssen während der **Anforderungs-, Installations-und** Zertifikat Phase des lync Server-Bereitstellungs-Assistenten ein OAuth-Zertifikat anfordern und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="95374-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="95374-130">Die Mindestgröße für einen OAuth-Zertifikatschlüssel lautet 1024-Bits.</span><span class="sxs-lookup"><span data-stu-id="95374-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="95374-131">Eine Warnung wird möglicherweise angezeigt, wenn Sie ein Zertifikat mit einer Schlüssellänge von weniger als 2048 Bits anfordern.</span><span class="sxs-lookup"><span data-stu-id="95374-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="95374-132">Um potenzielle Probleme zu vermeiden, falls eine Schlüssellänge von 2048 anstelle einer Warnung erzwungen wird, wird dringend empfohlen, immer eine Schlüssellänge von 2048 für OAuth-Zertifikate zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="95374-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="95374-133">Lync Server 2013 und Microsoft Exchange Server 2010 Service Pack 1 (SP1) funktionieren mit Unterstützung für FIPS (Federal Information Processing Standard) 140-2-Algorithmen, wenn die Windows Server 2008 R2-Betriebssysteme so konfiguriert sind, dass Sie die FIPS 140-2-Algorithmen für Systemkryptografie.</span><span class="sxs-lookup"><span data-stu-id="95374-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="95374-134">Zum Implementieren der FIPS-Unterstützung müssen Sie jeden Server mit lync Server 2013 so konfigurieren, dass er unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="95374-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="95374-135">Ausführliche Informationen zu FIPS-kompatiblen Algorithmen und zur Implementierung der FIPS-Unterstützung finden Sie im Microsoft Knowledge Base-Artikel 811833, "System Kryptographie: Verwenden von FIPS-kompatiblen Algorithmen für Verschlüsselung, Hashing und Signatur Sicherheit in Windows XP und späteren Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)-Versionen unter.</span><span class="sxs-lookup"><span data-stu-id="95374-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="95374-136">Details zu FIPS 140-2-Unterstützung und Einschränkungen in Exchange 2010 finden Sie unter "Exchange 2010 SP1 und Unterstützung für FIPS- [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)konforme Algorithmen" unter.</span><span class="sxs-lookup"><span data-stu-id="95374-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="95374-137">Lync Server 2013 erfordert die Installation anderer Software auf bestimmten Komponenten vor oder während der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="95374-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="95374-138">Dazu gehören Software, die mit dem Betriebssystem, herunterladbarer Software und Software zur Verfügung steht, die während der Installation von lync Server 2013 automatisch installiert wird.</span><span class="sxs-lookup"><span data-stu-id="95374-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="95374-139">Im folgenden finden Sie eine Liste zusätzlicher Software, die erforderlich sein kann:</span><span class="sxs-lookup"><span data-stu-id="95374-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="95374-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="95374-140">Windows Update</span></span>

  - <span data-ttu-id="95374-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="95374-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="95374-142">Microsoft .NET 4,5-Framework</span><span class="sxs-lookup"><span data-stu-id="95374-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="95374-143">Microsoft Visual C++ 2012 Redistributable</span><span class="sxs-lookup"><span data-stu-id="95374-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="95374-144">Microsoft Visual C++ 2012 Redistributable wird automatisch installiert, wenn Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="95374-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="95374-145">Sie sollten keine andere Version installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="95374-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="95374-146">URL-umschreibungs Modul, Version 2,0, verteilbare</span><span class="sxs-lookup"><span data-stu-id="95374-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="95374-147">Windows Media Format-Laufzeitkomponente</span><span class="sxs-lookup"><span data-stu-id="95374-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="95374-148">Windows PowerShell, Version 3,0</span><span class="sxs-lookup"><span data-stu-id="95374-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="95374-149">Microsoft Silverlight 4-Browser-Plug-in (Silverlight-4.0.50524.0 oder die neueste Version der lync Server-Systemsteuerung)</span><span class="sxs-lookup"><span data-stu-id="95374-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="95374-150">Tools für Active Directory-Domänendienste</span><span class="sxs-lookup"><span data-stu-id="95374-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="95374-151">Einige dieser Softwareanforderungen gelten nur für bestimmte Serverrollen oder Komponenten.</span><span class="sxs-lookup"><span data-stu-id="95374-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="95374-152">Details zu diesen Softwareanforderungen finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="95374-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

