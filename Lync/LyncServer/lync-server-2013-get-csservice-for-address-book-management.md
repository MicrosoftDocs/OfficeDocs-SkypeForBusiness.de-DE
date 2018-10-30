---
title: "\"Get-CsService\" für die Adressbuchverwaltung"
TOCTitle: "\"Get-CsService\" für die Adressbuchverwaltung"
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429698(v=OCS.15)
ms:contentKeyID: 49293669
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"Get-CsService\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Get-CsService" lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

"Get-CsService" eignet sich zum Abrufen und Anzeigen der aktuellen Konfiguration der in Ihrer Infrastruktur definierten Webdienste. Bei Definition des vollqualifizierten Domänennamens des Pools (Fully Qualified Domain Name, FQDN) und des Parameters "WebServer" gibt das Cmdlet die von Ihrem Server angebotenen webbasierten Dienste zurück, einschließlich des Adressbuchhandlers und der URIs für die Verteilerlistenerweiterung.

Beispiel:

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

Dieses Cmdlet gibt Folgendes zurück:

Identity : WebServer:pool01.contoso.net

FileStore : FileStore:dc01.contoso.net

UserServer : UserServer:pool01.contoso.net

PrimaryHttpPort : 80

PrimaryHttpsPort : 443

ExternalHttpPort : 8080

ExternalHttpsPort : 4443

PublishedPrimaryHttpPort : 80

PublishedPrimaryHttpsPort : 443

PublishedExternalHttpPort : 80

PublishedExternalHttpsPort : 443

ReachPrimaryPsomServerPort : 8060

ReachExternalPsomServerPort : 8061

AppSharingPortStart : 49152

AppSharingPortCount : 16383

LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc

ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler

ABHandlerExternalUri : https://csweb.contoso.com/abs/handler

DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc

DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc

CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CollabContentInternalUri : https://internalweb.contoso.net/CollabContent

CollabContentExternalUri : https://csweb.contoso.com/CollabContent

CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri : https://csweb.contoso.com/Meet

DialinExternalUri : https://csweb.contoso.com/Dialin

CscpInternalUri : https://internalweb.contoso.net/Cscp

ReachExternalUri : https://csweb.contoso.com/Reach

ReachInternalUri : https://internalweb.contoso.net/Reach

WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn : csweb.contoso.com

InternalFqdn : internalweb.contoso.net

DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}

ServiceId : 1-WebServices-1

SiteId : Site:Redmond

PoolFqdn : pool01.contoso.net

Version : 5

Role : WebServer

Eine detaillierte Beschreibung des vollständigen Befehls finden Sie im folgenden Abschnitt der Referenz zu den Windows PowerShell-RTCCmdlets von Lync Server.

## Siehe auch

#### Weitere Ressourcen

[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)

