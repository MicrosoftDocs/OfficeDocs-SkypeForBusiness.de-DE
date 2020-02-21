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

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a>Get-CsService für die Adressbuchverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Get-CsService" lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

Get-CsService ist wertvoll, um die aktuelle Konfiguration der definierten Webdienste der Infrastruktur abzurufen und anzuzeigen. Bei Definition des vollqualifizierten Domänennamens des Pools (Fully Qualified Domain Name, FQDN) und des Parameters "WebServer" gibt das Cmdlet die von Ihrem Server angebotenen webbasierten Dienste zurück, einschließlich des Adressbuchhandlers und der URIs für die Verteilerlistenerweiterung.

Beispiel:

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

Dieses Cmdlet gibt Folgendes zurück:

Identität: Webserver:pool01. contoso. net

Filestore: Filestore:DC01. contoso. net

"User Server:" User Server:pool01. contoso. net

PrimaryHttpPort: 80

PrimaryHttpsPort: 443

ExternalHttpPort: 8080

ExternalHttpsPort: 4443

PublishedPrimaryHttpPort: 80

PublishedPrimaryHttpsPort: 443

PublishedExternalHttpPort: 80

PublishedExternalHttpsPort: 443

ReachPrimaryPsomServerPort: 8060

ReachExternalPsomServerPort: 8061

AppSharingPortStart: 49152

AppSharingPortCount: 16383

LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc

ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler

ABHandlerExternalUri :https://csweb.contoso.com/abs/handler

DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc

DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc

CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CollabContentInternalUri :https://internalweb.contoso.net/CollabContent

CollabContentExternalUri :https://csweb.contoso.com/CollabContent

CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri :https://csweb.contoso.com/Meet

DialinExternalUri :https://csweb.contoso.com/Dialin

CscpInternalUri :https://internalweb.contoso.net/Cscp

ReachExternalUri :https://csweb.contoso.com/Reach

ReachInternalUri :https://internalweb.contoso.net/Reach

WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn: csweb.contoso.com

InternalFqdn: internalweb.contoso.net

DependentServiceList: {Registrar:pool01. contoso. net, ConferencingServer:pool01. contoso. net}

Dienst-Nr: 1-Webservices-1

Website-Nr: Standort: Redmond

Poolfqdn ": pool01.contoso.net

Version: 5

Rolle: Webserver

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

