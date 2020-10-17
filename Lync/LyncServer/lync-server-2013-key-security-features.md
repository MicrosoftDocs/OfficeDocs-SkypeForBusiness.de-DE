---
title: 'Lync Server 2013: wichtige Sicherheitsfeatures'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a1ff88b11c7d0ce007fc3bac38e7e3618771fb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514022"
---
# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="1d135-102">Wichtige Sicherheitsfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d135-102">Key security features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d135-103">_**Letztes Änderungsstand des Themas:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="1d135-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="1d135-104">Lync Server 2013 umfasst verschiedene Sicherheitsfeatures, einschließlich Server-zu-Server-Authentifizierung, rollenbasierte Zugriffssteuerung und zentralisierte Speicherung von Konfigurationsdaten.</span><span class="sxs-lookup"><span data-stu-id="1d135-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="1d135-105">Dieser Artikel bietet eine allgemeine Übersicht über lync Server 2013 Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="1d135-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="1d135-106">Wichtige Sicherheits Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d135-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="1d135-107">Sicherheit ist ein sehr breites Thema.</span><span class="sxs-lookup"><span data-stu-id="1d135-107">Security is a very broad topic.</span></span> <span data-ttu-id="1d135-108">Die Sicherheit erreicht alle Funktionen von lync Server 2013 sowie Datenbanken, Dienste und Hardware, aus denen ein lync-Ökosystem besteht.</span><span class="sxs-lookup"><span data-stu-id="1d135-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="1d135-109">In diesem Artikel werden einige der Features in lync Server 2013 beschrieben, die speziell auf die Sicherheit ausgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="1d135-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="1d135-110">Planungs-und Entwurfs Tools</span><span class="sxs-lookup"><span data-stu-id="1d135-110">Planning and Design Tools</span></span>

<span data-ttu-id="1d135-111">Lync Server 2013 bietet zwei Tools zur Vereinfachung der Planung und des Designs sowie zur Verringerung der Wahrscheinlichkeit, dass lync Server-Komponenten nicht mehr konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="1d135-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="1d135-112">Das **Topologie-Planungs Tool** automatisiert einen Großteil des Topologie-Entwurfsprozesses.</span><span class="sxs-lookup"><span data-stu-id="1d135-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="1d135-113">Sie können die Ergebnisse aus dem Planungstool in den Topologie-Generator exportieren, bei dem es sich um das Tool handelt, das zum Installieren der einzelnen Server mit lync Server 2013 erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1d135-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="1d135-114">Im **Topologie-Generator** werden alle Konfigurationsinformationen im zentralen Verwaltungsspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1d135-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="1d135-115">Ausführliche Informationen zu diesen Tools finden Sie unter [Planning for lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="1d135-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="1d135-116">Zentraler Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="1d135-116">Central Management Store</span></span>

<span data-ttu-id="1d135-117">In lync Server 2013 sind Konfigurationsdaten zu Servern und Diensten Teil des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="1d135-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="1d135-118">Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierten Speicherung der Daten, die für die Definition, Einrichtung, Verwaltung, Verwaltung, Beschreibung und den Betrieb einer lync Server-Bereitstellung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="1d135-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="1d135-119">Darüber hinaus werden die Daten überprüft, um eine konsistente Konfiguration zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="1d135-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="1d135-120">Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch nicht mehr synchrone Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="1d135-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="1d135-121">Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, Edgeserver eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1d135-121">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances.</span></span> <span data-ttu-id="1d135-122">Die Replikation wird von einem Dienst verwaltet, der standardmäßig unter dem Kontext des Netzwerkdiensts ausgeführt wird, wodurch die Rechte und Berechtigungen auf die eines einfachen Benutzers auf dem Computer reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="1d135-122">Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="1d135-123">Server-zu-Server-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="1d135-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="1d135-124">In lync Server 2013 kann die Authentifizierung zwischen Servern mithilfe des Open Authorization (OAuth)-Protokolls konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1d135-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="1d135-125">Beispielsweise können Sie lync Server 2013 für die Authentifizierung bei einem Server konfigurieren, auf dem Exchange Server 2013 läuft.</span><span class="sxs-lookup"><span data-stu-id="1d135-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="1d135-126">Mithilfe des OAuth-Protokolls können der lync-Server und der Exchange-Server einander vertrauen.</span><span class="sxs-lookup"><span data-stu-id="1d135-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="1d135-127">Auf diese Weise können Sie die Produkte nahtlos integrieren.</span><span class="sxs-lookup"><span data-stu-id="1d135-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="1d135-128">Ausführliche Informationen finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="1d135-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="1d135-129">Windows PowerShell basierte Verwaltung und webbasierte Verwaltungsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d135-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="1d135-130">Lync Server 2013 bietet eine leistungsstarke Verwaltungsschnittstelle, die auf der Windows PowerShell-Befehlszeilenschnittstelle basiert.</span><span class="sxs-lookup"><span data-stu-id="1d135-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="1d135-131">Sie enthält Cmdlets für die Verwaltung der Sicherheit, und Windows PowerShell-Sicherheitsfeatures sind standardmäßig aktiviert, sodass Skripts von Benutzern nicht versehentlich oder unwissentlich ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="1d135-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="1d135-132">Dies bedeutet, dass die Softwarestandardeinstellungen so konfiguriert sind, dass die Sicherheit automatisch optimiert wird und Angriffsmöglichkeiten reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="1d135-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="1d135-133">Ausführliche Informationen zur Windows PowerShell-Verwaltungsunterstützung in lync Server 2013 finden Sie unter [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="1d135-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="1d135-134">Role-Based Zugriffssteuerung (RBAC)</span><span class="sxs-lookup"><span data-stu-id="1d135-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="1d135-135">Microsoft lync Server 2013 bietet rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC), mit der Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards aufrecht erhalten können.</span><span class="sxs-lookup"><span data-stu-id="1d135-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="1d135-136">Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Benutzer nur die administrativen Rechte erhalten, die sie für ihre Arbeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="1d135-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="1d135-137">Lync Server 2013 bietet die Möglichkeit, eine neue Rolle zu erstellen und außerdem die Möglichkeit, eine vorhandene Rolle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1d135-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="1d135-138">Ausführliche Informationen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="1d135-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="1d135-139">Netzwerkadressübersetzung (Network Address Translation, NAT)</span><span class="sxs-lookup"><span data-stu-id="1d135-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="1d135-140">Lync Server 2013 unterstützt nicht die Verwendung der Netzwerkadressübersetzung (Network Address Translation, NAT) auf der internen Schnittstelle des Edgeserver, aber es unterstützt das Platzieren der externen Schnittstelle der Zugriffs-Edgedienst, Webkonferenz-Edgedienst und A/V-Edgedienst hinter einem Router oder einer Firewall, die Netzwerkadressübersetzung (Network Address Translation, NAT) für einzelne und skalierte konsolidierte Edgeserver Topologien ausführt.</span><span class="sxs-lookup"><span data-stu-id="1d135-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="1d135-141">Mehrere Edgeserver hinter einem Hardwaregerät zum Lastenausgleich können keine NAT verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d135-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="1d135-142">Wenn mehrere Edgeserver NAT auf Ihren externen Schnittstellen verwenden, ist Domain Name System (DNS) Lastenausgleich erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1d135-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="1d135-143">Mithilfe des DNS-Lastenausgleichs können Sie wiederum die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edgeserver-Pool reduzieren.</span><span class="sxs-lookup"><span data-stu-id="1d135-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="1d135-144">Ausführliche Informationen finden Sie unter[Planning for external User Access in lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1d135-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d135-145">Wenn Sie einen Verbund mit Unternehmen mit einer Microsoft Office Communications Server 2007-Bereitstellung haben und Sie Audio/Video zwischen Ihrem Unternehmen und dem Verbundunternehmen verwenden müssen, werden die Portanforderungen für die ältere Version der bereitgestellten Edgeserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d135-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="1d135-146">Beispielsweise müssen die für diese älteren Versionen erforderlichen Portbereiche für beide Unternehmen geöffnet werden, bis der Partnerverbund seine Edgeserver auf lync Server 2013 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1d135-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="1d135-147">Dann können die Portanforderungen erneut überprüft und gemäß der neuen Konfiguration vermindert werden.</span><span class="sxs-lookup"><span data-stu-id="1d135-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="1d135-148">Vereinfachte Zertifikate für Edgeserver</span><span class="sxs-lookup"><span data-stu-id="1d135-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="1d135-149">Der Bereitstellungs-Assistent kann automatisch die Antragstellernamen (SNS) und die alternativen Antragstellernamen (Subject Alternative Names, Sans) auffüllen, wodurch die Möglichkeit zur Einbeziehung unnötiger und potenziell unsich</span><span class="sxs-lookup"><span data-stu-id="1d135-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="1d135-150">Trustworthy Computing Security Development Lifecycle (SDL)</span><span class="sxs-lookup"><span data-stu-id="1d135-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="1d135-151">Lync Server 2013 wurde in Übereinstimmung mit dem Microsoft Trustworthy Computing Security Development Lifecycle (SDL) entworfen und entwickelt, der unter beschrieben wird <https://go.microsoft.com/fwlink/?linkid=68761> .</span><span class="sxs-lookup"><span data-stu-id="1d135-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <https://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="1d135-152">**Vertrauenswürdig nach Design**     Der erste Schritt bei der Erstellung eines sicheren Unified Communications-Systems war das Entwerfen von Bedrohungsmodellen und das Testen der einzelnen Features, die so entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="1d135-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="1d135-153">Darüber hinaus führt Microsoft Tests außerhalb des entworfenen Verhaltens durch, um Sicherheitsrisiken zu finden, die aus einem unerwarteten Produktverhalten resultieren.</span><span class="sxs-lookup"><span data-stu-id="1d135-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="1d135-154">Mehrere sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert.</span><span class="sxs-lookup"><span data-stu-id="1d135-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="1d135-155">Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="1d135-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="1d135-156">Natürlich ist es nicht möglich, alle unbekannten Sicherheitsbedrohungen vorherzusehen.</span><span class="sxs-lookup"><span data-stu-id="1d135-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="1d135-157">Es gibt kein System ohne Sicherheitslücken.</span><span class="sxs-lookup"><span data-stu-id="1d135-157">No system can guarantee complete security.</span></span> <span data-ttu-id="1d135-158">Da die Produktentwicklung jedoch von Anfang an sichere Entwurfsprinzipien umfasste, umfasst lync Server 2013 Branchenstandard-Sicherheitstechnologien als grundlegender Bestandteil ihrer Architektur.</span><span class="sxs-lookup"><span data-stu-id="1d135-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="1d135-159">**Standardmäßig**     vertrauenswürdig Die Netzwerkkommunikation in lync Server 2013 wird standardmäßig verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="1d135-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="1d135-160">Da alle Serverzertifikate und Kerberos-Authentifizierung, TLS, Secure Real-Time Transport Protocol (SRTP) und andere Standard Verschlüsselungstechniken (einschließlich 128-Bit Advanced Encryption Standard) (AES)-Verschlüsselung verwenden, sind praktisch alle lync Server Daten im Netzwerk geschützt.</span><span class="sxs-lookup"><span data-stu-id="1d135-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="1d135-161">Darüber hinaus ermöglicht die rollenbasierte Zugriffssteuerung die Bereitstellung von Servern, auf denen lync Server 2013 ausgeführt wird, sodass jede Serverrolle nur die Dienste ausführt und nur über die Berechtigungen für diese Dienste verfügt, die für die Serverrolle geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="1d135-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="1d135-162">**Vertrauenswürdig durch Bereitstellung**     In der lync Server 2013 Dokumentation finden Sie bewährte Methoden und Empfehlungen, mit denen Sie die optimalen Sicherheitsstufen für Ihre Bereitstellung ermitteln und konfigurieren und die Sicherheitsrisiken der Aktivierung nicht standardmäßiger Optionen bewerten können.</span><span class="sxs-lookup"><span data-stu-id="1d135-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

