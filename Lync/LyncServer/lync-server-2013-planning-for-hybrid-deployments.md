---
title: 'Lync Server 2013: Planen von hybridbereitstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47e8bc57edbf3b6414820aba1613be8b44fc670e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="49407-102">Planen von lync Server 2013 hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="49407-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49407-103">_**Letztes Änderungsstand des Themas:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="49407-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="49407-104">Bei der Planung einer hybridbereitstellung sollten Sie die folgenden Anforderungen für Benutzer und Ihre Netzwerkinfrastruktur berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="49407-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="49407-105">Infrastrukturanforderungen</span><span class="sxs-lookup"><span data-stu-id="49407-105">Infrastructure Requirements</span></span>

<span data-ttu-id="49407-106">In Ihrer Umgebung muss Folgendes konfiguriert sein, damit Sie eine hybridbereitstellung implementieren und bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="49407-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="49407-107">Eine Microsoft 365-oder Office 365-Organisation mit aktivierter Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="49407-107">A Microsoft 365 or Office 365 organization with Skype for Business Online enabled.</span></span> <span data-ttu-id="49407-108">Beachten Sie, dass Sie für eine Hybrid Konfiguration mit Ihrer lokalen Bereitstellung nur einen einzelnen Mandanten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="49407-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="49407-109">Eine einzelne lokale Bereitstellung (Infrastruktur) von Skype for Business Server oder lync Server, die in einer unterstützten Topologie bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="49407-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="49407-110">Siehe Topologie-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="49407-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="49407-111">Informationen zum Konfigurieren der lync Server 2013 oder lync Server 2010-Bereitstellung für hybridbereitstellungen finden Sie unter [Configuring lync Server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="49407-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="49407-112">Skype for Business Server 2015 Verwaltungstools.</span><span class="sxs-lookup"><span data-stu-id="49407-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="49407-113">Wenn Sie lync Server 2013 oder lync Server 2010 verwenden, können Sie die lync Server 2013 Verwaltungstools verwenden.</span><span class="sxs-lookup"><span data-stu-id="49407-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="49407-114">Zur Unterstützung des einmaligen Anmeldens mit Microsoft 365 oder Office 365, damit Benutzer dieselben Anmeldeinformationen für die Anmeldung bei Office verwenden können, wenn diese lokal Vorgehen, können Sie die Kenn Wort Synchronisierungsfeatures von Azure Active Directory (AAD) Connect verwenden.</span><span class="sxs-lookup"><span data-stu-id="49407-114">To support Single Sign-on with Microsoft 365 or Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="49407-115">Sie können auch Active Directory Verbunddienste (AD FS) für einmaliges Anmelden mit Microsoft 365 oder Office 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="49407-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Microsoft 365 or Office 365.</span></span>
    
    <span data-ttu-id="49407-116">Weitere Informationen finden Sie unter [Integrieren Ihrer lokalen Identitäten in Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="49407-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="49407-117">Eine einzelne Verzeichnis Synchronisierungslösung, mit der Sie Ihre lokalen und Online Active Directory-Objekte synchron halten.</span><span class="sxs-lookup"><span data-stu-id="49407-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="49407-118">Ausführliche Informationen zur Verzeichnissynchronisierung finden Sie unter [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="49407-118">For details about Directory Synchronization, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="49407-119">Lync-Client Unterstützung</span><span class="sxs-lookup"><span data-stu-id="49407-119">Lync Client Support</span></span>

<span data-ttu-id="49407-120">Es gibt einige Unterschiede in den Features, die in lync-Clients unterstützt werden, sowie die Features, die in lokalen und Online-Umgebungen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="49407-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="49407-121">Bevor Sie entscheiden, wo Benutzer in Ihrer Organisation zu Hause sein sollen, können Sie die Clientunterstützung für die verschiedenen Konfigurationen von lync Server anzeigen.</span><span class="sxs-lookup"><span data-stu-id="49407-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="49407-122">Die folgenden Clients werden mit Skype for Business Online in einer lync-hybridbereitstellung unterstützt:</span><span class="sxs-lookup"><span data-stu-id="49407-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="49407-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="49407-123">Lync 2010</span></span>

  - <span data-ttu-id="49407-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="49407-124">Lync 2013</span></span>

  - <span data-ttu-id="49407-125">Lync Windows Store-App</span><span class="sxs-lookup"><span data-stu-id="49407-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="49407-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="49407-126">Lync Web App</span></span>

  - <span data-ttu-id="49407-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="49407-127">Lync Mobile</span></span>

  - <span data-ttu-id="49407-128">Lync für Mac 2011</span><span class="sxs-lookup"><span data-stu-id="49407-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="49407-129">Lync-Raumsystem</span><span class="sxs-lookup"><span data-stu-id="49407-129">Lync Room System</span></span>

  - <span data-ttu-id="49407-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="49407-130">Lync Basic 2013</span></span>

<span data-ttu-id="49407-131">Ausführliche Informationen zur Clientunterstützung finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="49407-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="49407-132">Clients für lync Online</span><span class="sxs-lookup"><span data-stu-id="49407-132">Clients for Lync Online</span></span>](https://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="49407-133">Client Vergleichstabellen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49407-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="49407-134">Vergleichstabellen für mobile Clients für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49407-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="49407-135">Anforderungen im Hinblick auf die Topologie</span><span class="sxs-lookup"><span data-stu-id="49407-135">Topology Requirements</span></span>

<span data-ttu-id="49407-136">Um Ihre Bereitstellung für Hybrid mit Skype for Business Online zu konfigurieren, müssen Sie über eine der folgenden unterstützten Topologien verfügen:</span><span class="sxs-lookup"><span data-stu-id="49407-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="49407-137">Eine Skype for Business Server 2015 Bereitstellung mit allen Servern, auf denen Skype for Business Server 2015 läuft.</span><span class="sxs-lookup"><span data-stu-id="49407-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="49407-138">Eine lync Server 2013 Bereitstellung mit allen Servern, auf denen lync Server 2013 läuft.</span><span class="sxs-lookup"><span data-stu-id="49407-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="49407-139">Eine lync Server 2010 Bereitstellung mit allen Servern, auf denen lync Server 2010 mit den neuesten kumulativen Updates läuft.</span><span class="sxs-lookup"><span data-stu-id="49407-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="49407-140">Der Verbund Edgeserver und der Server für den nächsten Hop aus dem Verbund Edgeserver müssen lync Server 2010 mit den neuesten kumulativen Updates laufen.</span><span class="sxs-lookup"><span data-stu-id="49407-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="49407-141">Die Skype for Business Server 2015-oder lync Server 2013-Verwaltungs Tools müssen auf mindestens einem Server oder einer Verwaltungsarbeitsstation installiert sein.</span><span class="sxs-lookup"><span data-stu-id="49407-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="49407-142">Eine gemischte lync Server 2013-und Skype for Business Server 2015-Bereitstellung mit den folgenden Server Rollen an mindestens einer Website mit Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="49407-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="49407-143">Mindestens ein Enterprise-Pool oder Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="49407-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="49407-144">Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="49407-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="49407-145">Dem SIP-Partnerverbund zugeordneter Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="49407-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="49407-146">Eine gemischte lync Server 2010-und Skype for Business Server 2015-Bereitstellung mit den folgenden Serverrollen an mindestens einem Standort, auf dem Skype for Business Server 2015 läuft:</span><span class="sxs-lookup"><span data-stu-id="49407-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="49407-147">Mindestens ein Enterprise-Pool oder Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="49407-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="49407-148">Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="49407-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="49407-149">Der dem SIP-Partnerverbund für den Standort zugeordnete Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="49407-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="49407-150">Eine gemischte lync Server 2010-und lync Server 2013-Bereitstellung mit den folgenden Server Rollen an mindestens einer Website mit lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="49407-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="49407-151">Mindestens ein Enterprise-Pool oder Standard Edition-Server am Standort</span><span class="sxs-lookup"><span data-stu-id="49407-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="49407-152">Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls dieser in der Website vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="49407-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="49407-153">Der dem SIP-Partnerverbund für den Standort zugeordnete Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="49407-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="49407-154">Die gesamte Benutzerverwaltung, einschließlich der Benutzer Verschiebungen zwischen lokalen und UNRESOLVED_TOKEN_VAL Online (skypeforbusiness), muss mithilfe der neuesten installierten Version der Verwaltungstools ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="49407-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="49407-155">Die Verwaltungstools müssen auf einem separaten Server installiert sein, der über einen Connect-Zugriff auf die vorhandene lokale Bereitstellung und das Internet verfügt.</span><span class="sxs-lookup"><span data-stu-id="49407-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="49407-156">Das Cmdlet " <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">CsUser</A> ", um Benutzer von Ihrer lokalen Bereitstellung in UNRESOLVED_TOKEN_VAL (skype16_online) zu verlagern, muss über die Verwaltungstools ausgeführt werden, die mit Ihrer lokalen Bereitstellung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="49407-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="49407-157">Weitere Informationen zu unterstützten Topologien finden Sie unter [Unterstützte Topologien in lync Server 2013](lync-server-2013-supported-topologies.md)und [lync Server 2013 Referenz Topologien für Enterprise-Hybrid Bereitstellungen](https://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="49407-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](https://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="49407-158">Informationen zur Problembehandlung bei hybridbereitstellungen und zum Verbinden von PowerShell mit lync Online finden Sie unter [lync online: lync PowerShell and Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="49407-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="49407-159">Anforderungen für zugelassene/blockierte Verbund Listen</span><span class="sxs-lookup"><span data-stu-id="49407-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="49407-160">Die Liste der zugelassenen Domänen enthält Domänen, für die der vollqualifizierte Domänenname (FQDN) des Partner Edges konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="49407-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="49407-161">Diese werden manchmal als *zugelassene Partnerserver* oder *direkte Verbundpartner*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="49407-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="49407-162">Sie sollten mit dem Unterschied zwischen Open Federation und Closed Federation vertraut sein, der in lokalen Bereitstellungen als *Partner Discovery* und *zugelassene Partnerdomänen Liste*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="49407-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="49407-163">Die folgenden Anforderungen müssen erfüllt sein, um eine hybridbereitstellung erfolgreich zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="49407-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="49407-164">Domänen Abgleich muss für Ihre lokale Bereitstellung und Ihre Microsoft 365-oder Office 365-Organisation identisch konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="49407-164">Domain matching must be configured the same for your on-premises deployment and your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="49407-165">Wenn die Partner Ermittlung für die lokale Bereitstellung aktiviert ist, muss Open Federation für Ihren Online-Mandanten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="49407-165">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="49407-166">Wenn die Partner Ermittlung nicht aktiviert ist, muss Closed Federation für Ihren Online-Mandanten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="49407-166">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="49407-167">Die Liste blockierter Domänen in der lokalen Bereitstellung muss genau mit der Liste der blockierten Domänen für den Online Mandanten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="49407-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="49407-168">Die Liste der zugelassenen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zugelassenen Domänen für den Online Mandanten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="49407-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="49407-169">Der Partnerverbund muss für die externe Kommunikation für den Online Mandanten aktiviert sein, der über die lync Online-Systemsteuerung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="49407-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="49407-170">DNS-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="49407-170">DNS Settings</span></span>

<span data-ttu-id="49407-171">Beim Erstellen von DNS-Einträgen für hybridbereitstellungen sollten alle externen lync-DNS-Einträge auf die lokale Infrastruktur hinweisen.</span><span class="sxs-lookup"><span data-stu-id="49407-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="49407-172">Ausführliche Informationen zu den erforderlichen DNS-Einträgen finden Sie unter [Domain Name System (DNS) Anforderungen für lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49407-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="49407-173">Außerdem müssen Sie sicherstellen, dass die in der folgenden Tabelle beschriebene DNS-Auflösung in Ihrer lokalen Bereitstellung funktioniert:</span><span class="sxs-lookup"><span data-stu-id="49407-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49407-174">DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="49407-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="49407-175">Auflösbar durch</span><span class="sxs-lookup"><span data-stu-id="49407-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="49407-176">DNS-Anforderung</span><span class="sxs-lookup"><span data-stu-id="49407-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49407-177">DNS-SRV-Eintrag für _sipfederationtls. _tcp. &lt; sipdomain.com &gt; für alle unterstützten SIP-Domänen, die auf Edge-externe IP (s) zugreifen</span><span class="sxs-lookup"><span data-stu-id="49407-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="49407-178">Edgeserver (s)</span><span class="sxs-lookup"><span data-stu-id="49407-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="49407-179">Aktivieren Sie die Verbundkommunikation in einer Hybrid Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="49407-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="49407-180">Die Edgeserver müssen wissen, wo der Verbunddatenverkehr für die SIP-Domäne, die zwischen lokal und Online aufgeteilt ist, weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="49407-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49407-181">DNS-A-Einträge für den FQDN des Edge-Webkonferenz Diensts, beispielsweise webcon.contoso.com auflösen in Webkonferenz-Edge-externe IP (s)</span><span class="sxs-lookup"><span data-stu-id="49407-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="49407-182">Interne Unternehmensnetzwerk verbundene Benutzer Computer</span><span class="sxs-lookup"><span data-stu-id="49407-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="49407-183">Ermöglichen Sie Online-Benutzern das präsentieren oder Anzeigen von Inhalten in lokalen gehosteten Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="49407-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="49407-184">Der Inhalt enthält PowerPoint-Dateien, Whiteboards, Umfragen und freigegebene Notizen.</span><span class="sxs-lookup"><span data-stu-id="49407-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="49407-185">Je nachdem, wie DNS in Ihrer Organisation konfiguriert ist, müssen Sie diese Einträge möglicherweise der internen gehosteten DNS-Zone für die entsprechenden SIP-Domänen hinzufügen, um die interne DNS-Auflösung für diese Einträge bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="49407-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="49407-186">Überlegungen zu Firewalls</span><span class="sxs-lookup"><span data-stu-id="49407-186">Firewall Considerations</span></span>

<span data-ttu-id="49407-187">Computer in Ihrem Netzwerk müssen in der Lage sein, standardmäßige Internet-DNS-Lookups durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="49407-187">Computers on your network must be able to perform standard Internet DNS lookups.</span></span> <span data-ttu-id="49407-188">Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.</span><span class="sxs-lookup"><span data-stu-id="49407-188">If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="49407-189">Je nach Speicherort Ihres Microsoft Online Services-Rechenzentrums müssen Sie auch die Netzwerkfirewall-Geräte so konfigurieren, dass Verbindungen basierend auf Platzhalterdomänen Namen akzeptiert werden (beispielsweise der gesamte Datenverkehr von \* . Outlook.com).</span><span class="sxs-lookup"><span data-stu-id="49407-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="49407-190">Wenn die Firewalls Ihrer Organisation keine Platzhalternamen Konfigurationen unterstützen, müssen Sie die IP-Adressbereiche, die Sie zulassen möchten, und die angegebenen Ports manuell bestimmen.</span><span class="sxs-lookup"><span data-stu-id="49407-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="49407-191">Weitere Informationen finden Sie im Hilfethema [Office 365 URLs und IP-Adressbereiche](https://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="49407-191">Refer to the Help topic [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="49407-192">Port-und Protokollanforderungen</span><span class="sxs-lookup"><span data-stu-id="49407-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="49407-193">Zusätzlich zu den Portanforderungen für die interne lync Server 2013 Kommunikation müssen Sie auch die folgenden Ports konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49407-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49407-194">Protokoll/Port</span><span class="sxs-lookup"><span data-stu-id="49407-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="49407-195">Anwendungen</span><span class="sxs-lookup"><span data-stu-id="49407-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49407-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="49407-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="49407-197">Geöffnet, eingehend</span><span class="sxs-lookup"><span data-stu-id="49407-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="49407-198">Active Directory-Verbunddienste (Active Directory Federation Services, AD FS) (Verbundserverrolle)</span><span class="sxs-lookup"><span data-stu-id="49407-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="49407-199">Weitere Informationen finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span><span class="sxs-lookup"><span data-stu-id="49407-199">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="49407-200">Active Directory-Verbunddienste (Proxyserverrolle)</span><span class="sxs-lookup"><span data-stu-id="49407-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="49407-201">Microsoft Online Services-Portal</span><span class="sxs-lookup"><span data-stu-id="49407-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="49407-202">Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="49407-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="49407-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="49407-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="49407-204">Lync-Client (Kommunikation mit lync Online von lokalen lync Server)</span><span class="sxs-lookup"><span data-stu-id="49407-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49407-205">TCP 80 und 443</span><span class="sxs-lookup"><span data-stu-id="49407-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="49407-206">Geöffnet, eingehend</span><span class="sxs-lookup"><span data-stu-id="49407-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="49407-207">Microsoft Online Services-Verzeichnissynchronisierungstool</span><span class="sxs-lookup"><span data-stu-id="49407-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49407-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="49407-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="49407-209">Eingehend/ausgehend im Edgeserver öffnen</span><span class="sxs-lookup"><span data-stu-id="49407-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49407-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="49407-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="49407-211">Öffnen von eingehenden/ausgehenden Datenfreigabesitzungen</span><span class="sxs-lookup"><span data-stu-id="49407-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49407-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="49407-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="49407-213">Öffnen eines eingehenden/ausgehenden für Audio-, Video-, Anwendungsfreigabesitzungen</span><span class="sxs-lookup"><span data-stu-id="49407-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49407-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="49407-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="49407-215">Öffnen von eingehenden/ausgehenden Daten für Audio-und Videositzungen</span><span class="sxs-lookup"><span data-stu-id="49407-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49407-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="49407-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="49407-217">Offener Ausgang für Audio-und Videositzungen</span><span class="sxs-lookup"><span data-stu-id="49407-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="49407-218">Benutzerkonten und-Daten</span><span class="sxs-lookup"><span data-stu-id="49407-218">User Accounts and Data</span></span>

<span data-ttu-id="49407-219">In einer lync Server 2013 hybridbereitstellung müssen alle Benutzer, die in lync online zu Hause sein sollen, zuerst in der lokalen Bereitstellung erstellt werden, damit das Benutzerkonto in Active Directory-Domänendienste erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="49407-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="49407-220">Anschließend können Sie den Benutzer zu Skype for Business Online, der die Kontaktliste des Benutzers verschiebt, weitergeben.</span><span class="sxs-lookup"><span data-stu-id="49407-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="49407-221">Wenn Sie Benutzerkonten zwischen Ihren lokalen lync-und lync Online-Bereitstellungen mit AD FS und Dirsync synchronisieren, müssen Sie die Ad-Konten für alle lync-Benutzer in Ihrer Organisation zwischen Ihren lokalen und Online lync-Bereitstellungen synchronisieren, auch wenn Benutzer nicht in lync Online verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="49407-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="49407-222">Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Online Benutzern in Ihrer Organisation möglicherweise nicht wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="49407-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="49407-223">Wenn der Benutzer mithilfe des Online Portals für Microsoft 365 Admin Center erstellt wird, wird das Benutzerkonto nicht mit lokalen Active Directory synchronisiert, und der Benutzer ist in der lokalen Active Directory nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="49407-223">If the user is created by using the online portal for Microsoft 365 admin center, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="49407-224">Wenn Sie bereits Benutzer in lync online erstellt haben und Hybrid mit einer lokalen lync Server konfigurieren möchten, finden Sie weitere Informationen unter <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Verschieben von Benutzern von lync Online in lync lokal in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="49407-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="49407-225">Bei der Planung einer hybridbereitstellung sollten Sie auch die folgenden benutzerbezogenen Probleme berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="49407-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="49407-226">**Benutzer Kontakte**     Der Grenzwert für Kontakte für lync Online Benutzer lautet 250.</span><span class="sxs-lookup"><span data-stu-id="49407-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="49407-227">Alle Kontakte außerhalb dieser Nummer werden aus der Kontaktliste des Benutzers entfernt, wenn das Konto in lync Online verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="49407-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="49407-228">**Instant Messaging und Anwesenheit**     Benutzer Kontaktlisten, Gruppen und Zugriffssteuerungslisten (Access Control Lists, ACLs) werden mit dem Benutzerkonto migriert.</span><span class="sxs-lookup"><span data-stu-id="49407-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="49407-229">**Konferenzdaten, Besprechungsinhalte und geplante Besprechungen**     Dieser Inhalt wird nicht mit dem Benutzerkonto migriert.</span><span class="sxs-lookup"><span data-stu-id="49407-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="49407-230">Benutzer müssen Besprechungen neu planen, nachdem Ihre Konten zu lync Online migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="49407-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="49407-231">Benutzerrichtlinien und-Features</span><span class="sxs-lookup"><span data-stu-id="49407-231">User Policies and Features</span></span>

  - <span data-ttu-id="49407-232">In einer lync Server 2013-Hybridumgebung können Benutzer sowohl lokal als auch online, aber nicht beides gleichzeitig für Chatnachrichten, VoIP und Besprechungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="49407-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="49407-233">**Lync-Client**     Einige Benutzer benötigen möglicherweise eine neue Client Version, wenn Sie in lync Online verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="49407-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="49407-234">Für Office Communications Server 2007 R2 müssen Benutzer vor der Migration zu lync Online in einen lync Server 2013 Pool verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="49407-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="49407-235">Weitere Informationen zur Clientunterstützung finden Sie unter [Clients for lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) und [Supported lync Clients and Network Port Configurations](https://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="49407-235">For more information about client support, see [Clients for Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](https://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="49407-236">**Lokale Richtlinien und Konfiguration (nicht Benutzer)**     Online-und lokale Richtlinien erfordern eine separate Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="49407-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="49407-237">Sie können keine globalen Richtlinien festlegen, die für beides gelten.</span><span class="sxs-lookup"><span data-stu-id="49407-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
