---
title: 'Lync Server 2013: Get-CsService für die Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a9e8be425a86eef0d548493e1466888d3d8728c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="621c4-102">Get-CsService für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="621c4-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="621c4-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="621c4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="621c4-p101">Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Get-CsService" lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="621c4-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="621c4-106">Get-CsService ist wertvoll, um die aktuelle Konfiguration der definierten Webdienste der Infrastruktur abzurufen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="621c4-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="621c4-107">Bei Definition des vollqualifizierten Domänennamens des Pools (Fully Qualified Domain Name, FQDN) und des Parameters "WebServer" gibt das Cmdlet die von Ihrem Server angebotenen webbasierten Dienste zurück, einschließlich des Adressbuchhandlers und der URIs für die Verteilerlistenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="621c4-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="621c4-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="621c4-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="621c4-109">Dieses Cmdlet gibt Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="621c4-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="621c4-110">Identität: Webserver:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="621c4-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="621c4-111">Filestore: Filestore:DC01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="621c4-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="621c4-112">"User Server:" User Server:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="621c4-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="621c4-113">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="621c4-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="621c4-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="621c4-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="621c4-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="621c4-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="621c4-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="621c4-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="621c4-117">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="621c4-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="621c4-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="621c4-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="621c4-119">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="621c4-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="621c4-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="621c4-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="621c4-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="621c4-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="621c4-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="621c4-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="621c4-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="621c4-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="621c4-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="621c4-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="621c4-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="621c4-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="621c4-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="621c4-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="621c4-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="621c4-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="621c4-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="621c4-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="621c4-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="621c4-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="621c4-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="621c4-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="621c4-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="621c4-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="621c4-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="621c4-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="621c4-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="621c4-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="621c4-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="621c4-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="621c4-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="621c4-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="621c4-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="621c4-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="621c4-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="621c4-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="621c4-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="621c4-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="621c4-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="621c4-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="621c4-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="621c4-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="621c4-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="621c4-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="621c4-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="621c4-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="621c4-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="621c4-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="621c4-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="621c4-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="621c4-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="621c4-150">DependentServiceList: {Registrar:pool01. contoso. net, ConferencingServer:pool01. contoso. net}</span><span class="sxs-lookup"><span data-stu-id="621c4-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="621c4-151">Dienst-Nr: 1-Webservices-1</span><span class="sxs-lookup"><span data-stu-id="621c4-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="621c4-152">Website-Nr: Standort: Redmond</span><span class="sxs-lookup"><span data-stu-id="621c4-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="621c4-153">Poolfqdn ": pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="621c4-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="621c4-154">Version: 5</span><span class="sxs-lookup"><span data-stu-id="621c4-154">Version : 5</span></span>

<span data-ttu-id="621c4-155">Rolle: Webserver</span><span class="sxs-lookup"><span data-stu-id="621c4-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="621c4-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="621c4-156">See Also</span></span>


[<span data-ttu-id="621c4-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="621c4-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

