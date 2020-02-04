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
ms.openlocfilehash: 55d59a6978b90db82ccf899df90b05c739e71a57
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="41166-102">Wichtige Sicherheitsfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41166-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41166-103">_**Letztes Änderungsdatum des Themas:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="41166-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="41166-104">Lync Server 2013 umfasst verschiedene Sicherheitsfeatures, einschließlich Server-zu-Server-Authentifizierung, rollenbasierte Zugriffssteuerung und zentralisierte Speicherung von Konfigurationsdaten.</span><span class="sxs-lookup"><span data-stu-id="41166-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="41166-105">Dieser Artikel bietet eine allgemeine Übersicht über die lync Server 2013-Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="41166-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="41166-106">Wichtige Sicherheits Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41166-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="41166-107">Sicherheit ist ein äußerst umfangreiches Thema.</span><span class="sxs-lookup"><span data-stu-id="41166-107">Security is a very broad topic.</span></span> <span data-ttu-id="41166-108">Die Sicherheit erreicht alle Funktionen von lync Server 2013 sowie Datenbanken, Dienste und Hardware, die ein lync-Ökosystem ausmachen.</span><span class="sxs-lookup"><span data-stu-id="41166-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="41166-109">In diesem Artikel werden einige der Features in lync Server 2013 erläutert, die speziell für die Sicherheit konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="41166-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="41166-110">Planungs- und Entwurfstools</span><span class="sxs-lookup"><span data-stu-id="41166-110">Planning and Design Tools</span></span>

<span data-ttu-id="41166-111">Lync Server 2013 bietet zwei Tools zur Vereinfachung von Planung und Entwurf sowie zum Verkleinern der Möglichkeit, lync Server-Komponenten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="41166-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="41166-112">Das **Topologie-Planungs Tool** automatisiert einen Großteil des Topologie-Entwurfsprozesses.</span><span class="sxs-lookup"><span data-stu-id="41166-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="41166-113">Sie können die Ergebnisse aus dem Planungstool in den Topologie-Generator exportieren, der das Tool ist, das zum Installieren der einzelnen Server mit lync Server 2013 erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="41166-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="41166-114">Der **Topologie-Generator** speichert alle Konfigurationsinformationen im zentralen Verwaltungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="41166-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="41166-115">Details zu diesen Tools finden Sie unter [Planen von lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="41166-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="41166-116">Zentraler Verwaltungsspeicher (Central Management Store, CMS)</span><span class="sxs-lookup"><span data-stu-id="41166-116">Central Management Store</span></span>

<span data-ttu-id="41166-117">In lync Server 2013 sind Konfigurationsdaten zu Servern und Diensten Teil des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="41166-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="41166-118">Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierten Speicherung der Daten, die zum definieren, einrichten, verwalten, verwalten, beschreiben und betreiben einer lync Server-Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="41166-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="41166-119">Darüber hinaus überprüft er die Daten, um eine konsistente Konfiguration zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="41166-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="41166-120">Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch Synchronisierungsprobleme beseitigt werden.</span><span class="sxs-lookup"><span data-stu-id="41166-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="41166-p104">Schreibgeschützte Kopien der Daten werden an alle Server in der Topologie repliziert, Edgeserver und Survivable Branch Appliances eingeschlossen. Die Replikation wird von einem Dienst verwaltet, der standardmäßig unter dem Kontext des Netzwerkdiensts ausgeführt wird, wodurch die Rechte und Berechtigungen auf die eines einfachen Benutzers auf dem Computer reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="41166-p104">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances. Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="41166-123">Server-zu-Server-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="41166-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="41166-124">In lync Server 2013 kann die Authentifizierung zwischen Servern mithilfe des Open Authorization (OAuth)-Protokolls konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="41166-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="41166-125">So können Sie beispielsweise lync Server 2013 für die Authentifizierung bei einem Server konfigurieren, auf dem Exchange Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="41166-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="41166-126">Mit dem OAuth-Protokoll können sich der lync-Server und der Exchange-Server gegenseitig vertrauen.</span><span class="sxs-lookup"><span data-stu-id="41166-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="41166-127">Auf diese Weise können die Produkte nahtlos integriert werden.</span><span class="sxs-lookup"><span data-stu-id="41166-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="41166-128">Ausführliche Informationen finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="41166-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="41166-129">Windows PowerShell-basierte und webbasierte Verwaltungsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="41166-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="41166-130">Lync Server 2013 bietet eine leistungsfähige Verwaltungsschnittstelle, die auf der Windows PowerShell-Befehlszeilenschnittstelle basiert.</span><span class="sxs-lookup"><span data-stu-id="41166-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="41166-131">Sie enthält Cmdlets für die Verwaltung der Sicherheit und Windows PowerShell-Sicherheitsfeatures sind standardmäßig aktiviert, sodass Skripts von Nutzern nicht versehentlich oder unwissentlich ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="41166-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="41166-132">Dies bedeutet, dass die Softwarestandardeinstellungen so konfiguriert sind, dass die Sicherheit automatisch optimiert wird und Angriffsmöglichkeiten reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="41166-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="41166-133">Details zur Unterstützung der Windows PowerShell-Verwaltung in lync Server 2013 finden Sie unter [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="41166-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="41166-134">Rollenbasierte Zugriffssteuerung (RBAC)</span><span class="sxs-lookup"><span data-stu-id="41166-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="41166-135">Microsoft lync Server 2013 bietet rollenbasierte Zugriffssteuerung, mit der Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards gewährleisten können.</span><span class="sxs-lookup"><span data-stu-id="41166-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="41166-136">Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Nutzer nur die administrativen Rechte erhalten, die sie für ihre Arbeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="41166-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="41166-137">Lync Server 2013 bietet eine Einführung in die Möglichkeit, eine neue Rolle zu erstellen und auch die Möglichkeit, eine vorhandene Rolle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="41166-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="41166-138">Ausführliche Informationen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="41166-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="41166-139">Netzwerkadressenübersetzung (Network Address Translation, NAT)</span><span class="sxs-lookup"><span data-stu-id="41166-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="41166-140">Lync Server 2013 unterstützt nicht die Verwendung der Netzwerkadressübersetzung (Network Address Translation, NAT) auf der internen Schnittstelle des Edge-Servers, aber es unterstützt das Platzieren der externen Schnittstelle des Zugriffs-Edgedienst, des Webkonferenz-Edgedienst und des a/V-Edgedienst hinter einem Router oder einer Firewall, die Netzwerkadressübersetzung (Network Address Translation, NAT) für einzelne und</span><span class="sxs-lookup"><span data-stu-id="41166-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="41166-141">Mehrere Edgeserver hinter einem Hardware-Lastenausgleichsmodul können NAT nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="41166-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="41166-142">Wenn mehrere Edgeserver für Ihre externen Schnittstellen NAT verwenden, ist ein DNS-Lastenausgleich (Domain Name System) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="41166-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="41166-143">Mithilfe des DNS-Lastenausgleichs können Sie wiederum die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edgeserver-Pool reduzieren.</span><span class="sxs-lookup"><span data-stu-id="41166-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="41166-144">Ausführliche Informationen finden Sie unter[Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="41166-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41166-145">Wenn Sie mit einem Verbundunternehmen zusammenarbeiten, das über eine Bereitstellung von Microsoft Office Communications Server 2007 verfügt, und wenn Audio-/Videofunktionen zwischen Ihrem Unternehmen und dem Verbundunternehmen unterstützt werden sollen, entsprechen die Portanforderungen denen für die bereitgestellten älteren Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="41166-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="41166-146">Beispielsweise müssen die für diese älteren Versionen erforderlichen Portbereiche für beide Unternehmen geöffnet werden, bis der Verbundpartner seine Edgeserver auf lync Server 2013 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="41166-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="41166-147">Dann können die Portanforderungen erneut überprüft und gemäß der neuen Konfiguration vermindert werden.</span><span class="sxs-lookup"><span data-stu-id="41166-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="41166-148">Vereinfachte Zertifikate für Edgeserver</span><span class="sxs-lookup"><span data-stu-id="41166-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="41166-149">Der Bereitstellungs-Assistent kann Antragstellernamen (SNs) und alternative Antragstellernamen (SANs) automatisch ausfüllen. Dadurch reduziert sich das Risiko von unnötigen und potenziell unsicheren Einträgen.</span><span class="sxs-lookup"><span data-stu-id="41166-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="41166-150">Trustworthy Computing Security Development Lifecycle (SDL)</span><span class="sxs-lookup"><span data-stu-id="41166-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="41166-151">Lync Server 2013 wurde in Übereinstimmung mit dem Microsoft Trustworthy Computing Security Development Lifecycle (SDL) entwickelt und entwickelt, das unter <http://go.microsoft.com/fwlink/?linkid=68761>beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="41166-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <http://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="41166-152">**Vertrauenswürdig durch Design**   der erste Schritt beim Erstellen eines sichereren Unified Communications-Systems war das Entwerfen von Bedrohungsmodellen und das Testen der einzelnen Features, wie Sie entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="41166-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="41166-153">Außerdem führt Microsoft Tests außerhalb des konzipierten Verhaltens durch, um Sicherheitsrisiken zu finden, die sich aus einem nicht erwarteten Produktverhalten ergeben.</span><span class="sxs-lookup"><span data-stu-id="41166-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="41166-154">Viele sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert.</span><span class="sxs-lookup"><span data-stu-id="41166-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="41166-155">Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="41166-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="41166-156">Natürlich ist es nicht möglich, so zu entwerfen, dass alle unbekannten Sicherheitsbedrohungen beseitigt werden.</span><span class="sxs-lookup"><span data-stu-id="41166-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="41166-157">Es gibt kein System, für das vollständige Sicherheit garantiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="41166-157">No system can guarantee complete security.</span></span> <span data-ttu-id="41166-158">Da die Produktentwicklung jedoch von Anfang an sichere Entwurfsprinzipien umfasste, umfasst lync Server 2013 branchenübliche Sicherheitstechnologien als grundlegende Komponente ihrer Architektur.</span><span class="sxs-lookup"><span data-stu-id="41166-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="41166-159">**Vertrauenswürdig**standardmäßig werden Netzwerkkommunikationen in lync Server 2013 standardmäßig verschlüsselt.   </span><span class="sxs-lookup"><span data-stu-id="41166-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="41166-160">Da alle Serverzertifikate und Kerberos-Authentifizierung, TLS, SRTP (Secure Real-Time Transport Protocol) und andere Industriestandard-Verschlüsselungstechniken verwenden, einschließlich AES-Verschlüsselung (128-Bit Advanced Encryption Standard), praktisch alle lync Server Daten sind im Netzwerk geschützt.</span><span class="sxs-lookup"><span data-stu-id="41166-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="41166-161">Darüber hinaus ermöglicht die rollenbasierte Zugriffssteuerung die Bereitstellung von Servern mit lync Server 2013, damit jede Serverrolle nur die Dienste ausführt und nur die Berechtigungen enthält, die sich auf diese Dienste beziehen, die für die Serverrolle geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="41166-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="41166-162">**Vertrauenswürdig durch Bereitstellung**   alle lync Server 2013-Dokumentation umfasst bewährte Methoden und Empfehlungen, die Ihnen dabei helfen, die optimalen Sicherheitsstufen für Ihre Bereitstellung zu ermitteln und zu konfigurieren und die Sicherheitsrisiken bei der Aktivierung nicht standardmäßiger Optionen zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="41166-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

