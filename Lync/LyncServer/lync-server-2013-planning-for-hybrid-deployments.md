---
title: 'Lync Server 2013: Planen von hybridbereitstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b528e22e24635d47755096cd4bf81d4066feb3c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="2f9c3-102">Planen der Bereitstellung von lync Server 2013-hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f9c3-103">_**Letztes Änderungsdatum des Themas:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="2f9c3-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="2f9c3-104">Berücksichtigen Sie beim Planen einer hybridbereitstellung die folgenden Anforderungen für Benutzer und Ihre Netzwerkinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="2f9c3-105">Infrastrukturanforderungen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-105">Infrastructure Requirements</span></span>

<span data-ttu-id="2f9c3-106">Sie müssen die folgenden in Ihrer Umgebung konfiguriert haben, um eine hybridbereitstellung implementieren und bereitstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="2f9c3-107">Ein Microsoft Office 365-Mandant mit aktiviertem Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="2f9c3-108">Beachten Sie, dass Sie nur einen einzelnen Mandanten für eine Hybrid Konfiguration mit Ihrer lokalen Bereitstellung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="2f9c3-109">Eine einzelne lokale Bereitstellung (Infrastruktur) von Skype for Business Server oder lync Server, die in einer unterstützten Topologie bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="2f9c3-110">Siehe Topologie-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="2f9c3-111">Informationen zum Konfigurieren ihrer lync Server 2013-oder lync Server 2010-Bereitstellung für hybride finden Sie unter [Konfigurieren von lync Server 2013-hybridbereitstellungen](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="2f9c3-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="2f9c3-112">Skype for Business Server 2015-Verwaltungstools.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="2f9c3-113">Wenn Sie lync Server 2013 oder lync Server 2010 verwenden, können Sie die Verwaltungstools von lync Server 2013 verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="2f9c3-114">Um die einmalige Anmeldung bei Office 365 zu unterstützen, damit Benutzer dieselben Anmeldeinformationen für die Anmeldung bei Office verwenden können, während Sie lokal tätig sind, können Sie die Kenn Wort Synchronisierungsfeatures von Azure Active Directory (AAD) Connect verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="2f9c3-115">Sie können auch die Active Directory Federation Services (AD FS) für das einmalige Anmelden mit Office 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="2f9c3-116">Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Identitäten in Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="2f9c3-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="2f9c3-117">Eine einzige Lösung für die Verzeichnissynchronisierung, damit Ihre lokalen und Online aktiven Active Directory-Objekte synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="2f9c3-118">Details zur Verzeichnissynchronisierung finden Sie unter [Tools für die Verzeichnis Integration](http://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="2f9c3-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="2f9c3-119">Lync-Client Unterstützung</span><span class="sxs-lookup"><span data-stu-id="2f9c3-119">Lync Client Support</span></span>

<span data-ttu-id="2f9c3-120">Es gibt einige Unterschiede bei den Features, die in lync-Clients unterstützt werden, sowie die Features, die in lokalen und Online Umgebungen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="2f9c3-121">Bevor Sie sich entscheiden, wo Sie die Benutzer in Ihrer Organisation privatisieren möchten, können Sie die Clientunterstützung für die verschiedenen Konfigurationen von lync Server anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="2f9c3-122">Die folgenden Clients werden von Skype for Business Online in einer lync-hybridbereitstellung unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2f9c3-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="2f9c3-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2f9c3-123">Lync 2010</span></span>

  - <span data-ttu-id="2f9c3-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2f9c3-124">Lync 2013</span></span>

  - <span data-ttu-id="2f9c3-125">Windows Store-App für Lync</span><span class="sxs-lookup"><span data-stu-id="2f9c3-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="2f9c3-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="2f9c3-126">Lync Web App</span></span>

  - <span data-ttu-id="2f9c3-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="2f9c3-127">Lync Mobile</span></span>

  - <span data-ttu-id="2f9c3-128">Lync für Mac 2011</span><span class="sxs-lookup"><span data-stu-id="2f9c3-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="2f9c3-129">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="2f9c3-129">Lync Room System</span></span>

  - <span data-ttu-id="2f9c3-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="2f9c3-130">Lync Basic 2013</span></span>

<span data-ttu-id="2f9c3-131">Details zum Client Support finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="2f9c3-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="2f9c3-132">Clients für lync Online</span><span class="sxs-lookup"><span data-stu-id="2f9c3-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="2f9c3-133">Clientvergleichstabellen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9c3-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="2f9c3-134">Vergleichstabellen für mobile Clients für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9c3-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="2f9c3-135">Anforderungen im Hinblick auf die Topologie</span><span class="sxs-lookup"><span data-stu-id="2f9c3-135">Topology Requirements</span></span>

<span data-ttu-id="2f9c3-136">Wenn Sie Ihre Bereitstellung für Hybrid mit Skype for Business Online konfigurieren möchten, müssen Sie über eine der folgenden unterstützten Topologien verfügen:</span><span class="sxs-lookup"><span data-stu-id="2f9c3-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="2f9c3-137">Eine Skype for Business Server 2015-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2015 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="2f9c3-138">Eine lync Server 2013-Bereitstellung mit allen Servern, auf denen lync Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="2f9c3-139">Eine lync Server 2010-Bereitstellung mit allen Servern, auf denen lync Server 2010 mit den neuesten kumulativen Updates ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="2f9c3-140">Auf dem Verbund-Edgeserver und dem Server für den nächsten Hop vom Verbund-Edgeserver muss lync Server 2010 mit den neuesten kumulativen Updates ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="2f9c3-141">Die Verwaltungs Tools für Skype for Business Server 2015 oder lync Server 2013 müssen auf mindestens einem Server oder einer Verwaltungsarbeitsstation installiert sein.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="2f9c3-142">Eine gemischte lync Server 2013-und Skype for Business Server 2015-Bereitstellung mit den folgenden Server Rollen in mindestens einer Website mit Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="2f9c3-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="2f9c3-143">Mindestens ein Enterprise-Pool- oder Standard Edition-Server </span><span class="sxs-lookup"><span data-stu-id="2f9c3-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="2f9c3-144">Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="2f9c3-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="2f9c3-145">Der dem SIP-Partnerverbund zugeordnete Edgepool</span><span class="sxs-lookup"><span data-stu-id="2f9c3-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="2f9c3-146">Eine gemischte lync Server 2010-und Skype for Business Server 2015-Bereitstellung mit den folgenden Serverrollen in mindestens einer Website mit Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="2f9c3-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="2f9c3-147">Mindestens ein Enterprise-Pool- oder Standard Edition-Server </span><span class="sxs-lookup"><span data-stu-id="2f9c3-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="2f9c3-148">Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="2f9c3-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="2f9c3-149">Der dem SIP-Partnerverbund zugeordnete Edgepool für den Standort</span><span class="sxs-lookup"><span data-stu-id="2f9c3-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="2f9c3-150">Eine gemischte lync Server 2010-und lync Server 2013-Bereitstellung mit den folgenden Server Rollen in mindestens einer Website mit lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="2f9c3-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="2f9c3-151">Mindestens ein Enterprise-Pool- oder Standard Edition-Server am Standort</span><span class="sxs-lookup"><span data-stu-id="2f9c3-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="2f9c3-152">Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls am Standort vorhanden</span><span class="sxs-lookup"><span data-stu-id="2f9c3-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="2f9c3-153">Der dem SIP-Partnerverbund zugeordnete Edgepool für den Standort</span><span class="sxs-lookup"><span data-stu-id="2f9c3-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f9c3-154">Die gesamte Benutzerverwaltung, einschließlich des Benutzers, der zwischen lokalen und UNRESOLVED_TOKEN_VAL (skypeforbusiness) Online wechselt, muss mithilfe der neuesten installierten Version der Verwaltungstools ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="2f9c3-155">Die Verwaltungstools müssen auf einem separaten Server installiert sein, auf dem der Zugriff auf die vorhandene lokale Bereitstellung und das Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="2f9c3-156">Das Cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> zum Verschieben von Benutzern aus Ihrer lokalen Bereitstellung in UNRESOLVED_TOKEN_VAL (skype16_online) muss über die Verwaltungstools ausgeführt werden, die mit Ihrer lokalen Bereitstellung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="2f9c3-157">Weitere Informationen zu unterstützten Topologien finden Sie unter [Unterstützte Topologien in lync Server 2013](lync-server-2013-supported-topologies.md)und [lync Server 2013-Referenz Topologien für Enterprise-Hybrid Bereitstellungen](http://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="2f9c3-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="2f9c3-158">Informationen zur Problembehandlung von hybridbereitstellungen und zum Verbinden von PowerShell mit lync Online finden Sie unter [lync online: Problembehandlung bei lync PowerShell und Hybrid](http://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="2f9c3-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="2f9c3-159">Voraussetzungen für zugelassene/blockierte Listen für Föderationen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="2f9c3-p108">Die Liste der zugelassenen Domänen enthält Domänen, für die ein Partner-Edge-FQDN (vollqualifizierter Domänenname) konfiguriert ist. Diese werden mitunter als *zulässige Partnerserver* oder *direkte Verbundpartner* bezeichnet. Sie sollten mit dem Unterschied zwischen einem öffentlichen Partnerverbund und einem geschlossenen Partnerverbund vertraut sein, der in lokalen Bereitstellungen als *Partnerermittlung* bzw. *Liste der zulässigen Partnerdomänen* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-p108">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured. These are sometimes referred to as *allowed partner servers* or *direct federation partners*. You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="2f9c3-163">Die folgenden Anforderungen müssen erfüllt sein, um eine Hybridbereitstellung erfolgreich zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2f9c3-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="2f9c3-p109">Der Domänenabgleich muss für die lokale Bereitstellung und den Office 365-Mandanten identisch konfiguriert sein. Wenn die Partnerermittlung für die lokale Bereitstellung aktiviert ist, muss der öffentliche Partnerverbund für den Onlinemandaten konfiguriert sein. Wenn die Partnerermittlung nicht aktiviert ist, muss für den Onlinemandanten der geschlossene Partnerverbund konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-p109">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="2f9c3-167">Die Liste der blockierten Domänen in der lokalen Bereitstellung muss genau mit der Liste der blockierten Domänen für den Onlinemandanten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="2f9c3-168">Die Liste der zugelassenen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zugelassenen Domänen für den Onlinemandanten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="2f9c3-169">Der Verbund muss für die externe Kommunikation für den Online Mandanten aktiviert sein, der über die lync Online-Systemsteuerung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="2f9c3-170">DNS-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-170">DNS Settings</span></span>

<span data-ttu-id="2f9c3-171">Beim Erstellen von DNS-Einträgen für hybridbereitstellungen sollten alle externen lync-DNS-Einträge auf die lokale Infrastruktur verweisen.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="2f9c3-172">Details zu den erforderlichen DNS-Einträgen finden Sie unter [Domain Name System (DNS) Requirements for lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f9c3-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="2f9c3-173">Darüber hinaus müssen Sie sicherstellen, dass die in der folgenden Tabelle erläuterte DNS-Auflösung in Ihrer lokalen Bereitstellung funktioniert:</span><span class="sxs-lookup"><span data-stu-id="2f9c3-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f9c3-174">DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="2f9c3-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-175">Aufzulösen durch</span><span class="sxs-lookup"><span data-stu-id="2f9c3-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-176">DNS-Anforderung</span><span class="sxs-lookup"><span data-stu-id="2f9c3-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9c3-177">DNS-SRV-Eintrag für _sipfederationtls. _tcp. &lt;sipdomain.com&gt; für alle unterstützten SIP-Domänen, die in Access Edge external IP (s) aufgelöst werden</span><span class="sxs-lookup"><span data-stu-id="2f9c3-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-178">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="2f9c3-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-p111">Aktivieren Sie Partnerverbundkommunikation in einer Hybridkonfiguration. Der Edgeserver muss wissen, wohin der Datenverkehr im Partnerverbund für die zwischen lokal und online aufgeteilte SIP-Domäne geleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-p111">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9c3-181">DNS-A-Eintrag/Einträge für den Edge-Webkonferenzdienst-FQDN, zum Beispiel „webcon.contoso.com“, aufgelöst zu der externen IP/den IPs des Webkonferenzdienst-Edgeservers</span><span class="sxs-lookup"><span data-stu-id="2f9c3-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-182">Über internes Unternehmensnetzwerk verbundene Benutzercomputer</span><span class="sxs-lookup"><span data-stu-id="2f9c3-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-p112">Versetzen Sie Onlinebenutzer in die Lage, in lokal gehosteten Besprechungen Inhalte zu präsentieren oder zu betrachten. Entsprechende Inhalte sind unter anderem PowerPoint-Dateien, Whiteboards, Umfragen und freigegebene Notizen. </span><span class="sxs-lookup"><span data-stu-id="2f9c3-p112">Enable online users to present or view content in on-premises hosted meetings. Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2f9c3-185">Je nachdem, wie DNS in Ihrer Organisation konfiguriert ist, müssen Sie möglicherweise der intern gehosteten DNS-Zone für die entsprechenden SIP-Domäne(n) diese Einträge hinzufügen, um die interne DNS-Auflösung dieser Datensätze zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="2f9c3-186">Firewall-Überlegungen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-186">Firewall Considerations</span></span>

<span data-ttu-id="2f9c3-p113">Die Computer in Ihrem Netzwerk müssen Standard-Internet-DNS-Lookups ausführen können. Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-p113">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="2f9c3-189">Je nach Standort Ihres Microsoft Online Services-Rechenzentrums müssen Sie auch Ihre Netzwerkfirewall-Geräte so konfigurieren, dass Sie Verbindungen basierend auf Platzhalter-Domänennamen (beispielsweise alle Daten \*Verkehr von Outlook.com) akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="2f9c3-190">Wenn die Firewalls Ihrer Organisation Konfigurationen mit Platzhalternamen nicht unterstützen, müssen Sie die IP-Adressbereiche, die Sie zulassen möchten, und die angegebenen Ports manuell festlegen.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="2f9c3-191">Weitere Informationen finden Sie im Hilfethema [Office 365-URLs und IP-Adressbereiche](http://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="2f9c3-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="2f9c3-192">Port-und Protokollanforderungen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="2f9c3-193">Zusätzlich zu den Portanforderungen für die interne lync Server 2013-Kommunikation müssen Sie auch die folgenden Ports konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f9c3-194">Protokoll/Port</span><span class="sxs-lookup"><span data-stu-id="2f9c3-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="2f9c3-195">Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f9c3-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="2f9c3-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-197">Eingehend öffnen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="2f9c3-198">Active Directory-Verbunddienste (Verbundserver Rolle)</span><span class="sxs-lookup"><span data-stu-id="2f9c3-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="2f9c3-199">Weitere Informationen finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Grundlegendes zu AD FS-Rollendiensten</a>.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="2f9c3-200">Active Directory-Verbunddienste (Proxy Serverrolle)</span><span class="sxs-lookup"><span data-stu-id="2f9c3-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="2f9c3-201">Microsoft Online Services-Portal</span><span class="sxs-lookup"><span data-stu-id="2f9c3-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="2f9c3-202">Mein Unternehmens Portal</span><span class="sxs-lookup"><span data-stu-id="2f9c3-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="2f9c3-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="2f9c3-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="2f9c3-204">Lync-Client (Kommunikation mit lync Online von einem lokalen lync-Server)</span><span class="sxs-lookup"><span data-stu-id="2f9c3-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9c3-205">TCP 80 und 443</span><span class="sxs-lookup"><span data-stu-id="2f9c3-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-206">Eingehend öffnen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="2f9c3-207">Microsoft Online Services-Verzeichnis Synchronisierungs Tool</span><span class="sxs-lookup"><span data-stu-id="2f9c3-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9c3-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="2f9c3-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-209">Inbound/Outbound auf dem Edgeserver öffnen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9c3-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="2f9c3-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-211">Eingehende/ausgehende Datenfreigabesitzungen öffnen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9c3-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="2f9c3-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-213">Eingehend/ausgehend für Audio-, Video-und Anwendungsfreigabesitzungen öffnen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9c3-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="2f9c3-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-215">Eingehende/ausgehende für Audio-und Videositzungen öffnen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9c3-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="2f9c3-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="2f9c3-217">Open Outbound für Audio-und Videositzungen</span><span class="sxs-lookup"><span data-stu-id="2f9c3-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="2f9c3-218">Benutzerkonten und-Daten</span><span class="sxs-lookup"><span data-stu-id="2f9c3-218">User Accounts and Data</span></span>

<span data-ttu-id="2f9c3-219">In einer lync Server 2013-hybridbereitstellung müssen alle Benutzer, die Sie in lync Online verwenden möchten, zunächst in der lokalen Bereitstellung erstellt werden, damit das Benutzerkonto in den Active Directory-Domänendiensten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="2f9c3-220">Sie können den Benutzer dann in Skype for Business Online verschieben, wodurch die Kontaktliste des Benutzers verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="2f9c3-221">Wenn Sie Benutzerkonten zwischen Ihren lokalen lync-und lync Online-Bereitstellungen mit AD FS und Dirsync synchronisieren, müssen Sie die Ad-Konten für alle lync-Benutzer in Ihrer Organisation zwischen Ihren lokalen und Online lync-Bereitstellungen synchronisieren, auch wenn Benutzer werden nicht in lync Online verschoben.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="2f9c3-222">Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f9c3-223">Wenn der Benutzer mithilfe des Online Portals für Office 365 erstellt wird, wird das Benutzerkonto nicht mit lokalem Active Directory synchronisiert, und der Benutzer ist nicht im lokalen Active Directory vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="2f9c3-224">Wenn Sie bereits Benutzer in lync online erstellt haben und Hybrid mit einem lokalen lync-Server konfigurieren möchten, lesen Sie <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Verschieben von Benutzern aus lync Online in lync lokal in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2f9c3-225">Sie sollten bei der Planung einer Hybridbereitstellung auch die folgenden benutzerbezogenen Aspekte berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="2f9c3-226">**Benutzer Kontakte**   die Höchstgrenze für Kontakte für lync Online-Benutzer lautet 250.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="2f9c3-227">Alle darüber hinausgehenden Kontakte werden aus der Kontaktliste des Benutzers entfernt, wenn das Konto nach Lync Online verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="2f9c3-228">**Sofortnachrichten und Anwesenheits**   Benutzer-Kontaktlisten, Gruppen und Zugriffssteuerungslisten (ACLs) werden mit dem Benutzerkonto migriert.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="2f9c3-229">**Konferenzdaten, Besprechungsinhalte und geplante Besprechungen**   dieser Inhalt wird nicht mit dem Benutzerkonto migriert.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="2f9c3-230">Benutzer müssen Besprechungen neu planen, nachdem ihre Konten zu Lync Online migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="2f9c3-231">Benutzerrichtlinien und-Features</span><span class="sxs-lookup"><span data-stu-id="2f9c3-231">User Policies and Features</span></span>

  - <span data-ttu-id="2f9c3-232">In einer lync Server 2013-Hybridumgebung können Benutzer für Sofortnachrichten, Sprachanrufe und Besprechungen entweder lokal oder Online aktiviert sein, jedoch nicht beides gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="2f9c3-233">**Lync-Client**     einige Benutzer benötigen möglicherweise eine neue Client Version, wenn Sie nach lync Online verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="2f9c3-234">Für Office Communications Server 2007 R2 müssen Benutzer vor der Migration zu lync Online in einen lync Server 2013-Pool verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="2f9c3-235">Weitere Informationen zum Client Support finden Sie unter [Clients für lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) und [unterstützte lync-Clients und Netzwerk-Portkonfigurationen](http://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="2f9c3-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="2f9c3-236">**Lokale Richtlinien und Konfiguration (nicht-Benutzer)**   Online-und lokale Richtlinien erfordern eine separate Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="2f9c3-237">Sie können keine globalen Richtlinien festlegen, die für beide Umgebungen gelten.</span><span class="sxs-lookup"><span data-stu-id="2f9c3-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

