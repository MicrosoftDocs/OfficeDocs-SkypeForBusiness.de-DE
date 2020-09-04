---
title: Bereitstellen der medienumgehung in Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: In diesem Thema erfahren Sie mehr über die Schritte zur Bereitstellung der medienumgehung mit Cloud Connector Edition Version 2,0 und höher.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359311"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="76290-103">Bereitstellen der medienumgehung in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="76290-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="76290-104">Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="76290-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="76290-105">Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="76290-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="76290-106">In diesem Thema erfahren Sie mehr über die Schritte zur Bereitstellung der medienumgehung mit Cloud Connector Edition Version 2,0 und höher.</span><span class="sxs-lookup"><span data-stu-id="76290-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="76290-107">Durch die medienumgehung kann ein Client Medien direkt an den nächsten Hop (Public Switched Telephone Network, PSTN) – einen Gateway-oder Session Border Controller (SBC) – senden und die Cloud Connector Edition-Komponente aus dem Medienpfad entfernen.</span><span class="sxs-lookup"><span data-stu-id="76290-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="76290-108">Siehe auch [Plan for Media Bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="76290-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="76290-109">Medienumgehung aktivieren</span><span class="sxs-lookup"><span data-stu-id="76290-109">Enable media bypass</span></span>

<span data-ttu-id="76290-110">Um die medienumgehung zu aktivieren, müssen Sie den DNS-Namen des Medien Umgehungs-Webdiensts konfigurieren und die medienumgehung in der Mandanten Konfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="76290-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="76290-111">Der Medien Umgehungs-Webdienst wird automatisch auf jeder Vermittlungsserver bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="76290-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="76290-112">Ein mandantenadministrator muss einen Namen für einen Hybrid-VoIP-Dienst (Standort) auswählen, und dieser Name sollte aus einer für Hybrid-VoIP registrierten SIP-Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="76290-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="76290-113">Der Dienstname sollte unabhängig vom Clientstandort für alle Cloud Connector-Appliances und alle PSTN-Standorte gleich sein.</span><span class="sxs-lookup"><span data-stu-id="76290-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="76290-114">Der Webdienst sollte nur intern im Netzwerk verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="76290-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="76290-115">Ein mandantenadministrator muss einen DNS-a-Eintrag im internen Produktions Active Directory konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="76290-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="76290-116">Wenn Sie über eine komplexe Umgebung mit mehreren Standorten verfügen, lesen Sie das Beispiel unter [Beispiel: DNS-Einträge für die Medien Umgehungs Website in komplexen Umgebungen mit mehreren](deploy-media-bypass-in-cloud-connector.md#Example)Standorten.</span><span class="sxs-lookup"><span data-stu-id="76290-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="76290-117">Der DNS-Eintrag sollte nur für interne Netzwerkclients aufgelöst werden; Es sollte nicht für externe Netzwerkclients aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="76290-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="76290-118">Stellen Sie nach dem Konfigurieren von DNS eine Verbindung mit Skype for Business Online mithilfe von Remote-PowerShell mit Skype for Business Administrator Anmeldeinformationen her.</span><span class="sxs-lookup"><span data-stu-id="76290-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="76290-119">Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="76290-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="76290-120">Geben Sie in der PowerShell-Sitzung die folgenden Befehle ein, um die medienumgehung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="76290-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="76290-121">Das Aktivieren der medienumgehung ist ein zweistufiger Prozess.</span><span class="sxs-lookup"><span data-stu-id="76290-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="76290-122">Mit dem Cmdlet New-CsNetworkMedia wird die neue Konfiguration nicht sofort gespeichert; Es werden nur die Einstellungen im Arbeitsspeicher erstellt.</span><span class="sxs-lookup"><span data-stu-id="76290-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="76290-123">Das von diesem Cmdlet erstellte Objekt muss in einer Variablen gespeichert und dann der MediaBypassSettings-Eigenschaft der Netzwerkkonfiguration zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="76290-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="76290-124">Weitere Informationen finden Sie unter [Beispiel: DNS-Einträge für die Medien Umgehungs Website in komplexen Umgebungen mit mehreren Standorten](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="76290-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="76290-125">Die Replikation zwischen den lokalen und den Online-Komponenten kann bis zu 24 Stunden dauern, daher empfiehlt Microsoft, die erforderlichen Befehle auszuführen, bevor Sie Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="76290-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="76290-126">Bestätigen der Einstellungen für die medienumgehung</span><span class="sxs-lookup"><span data-stu-id="76290-126">Confirm media bypass settings</span></span>

<span data-ttu-id="76290-127">Sie können die Einstellungen für die medienumgehung wie folgt überprüfen.</span><span class="sxs-lookup"><span data-stu-id="76290-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="76290-128">Führen Sie den folgenden Befehl in Remote PowerShell aus, um die Online Replikation auf ihren Mandanten Pool zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="76290-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="76290-129">Um die lokale Replikation zu überprüfen, stellen Sie eine Verbindung mit den Cloud Connector-Vermittlungsservern her, führen Sie den folgenden Befehl in PowerShell aus, und bestätigen Sie, dass Enabled = true und "alwaysbypass" = true sind.</span><span class="sxs-lookup"><span data-stu-id="76290-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="76290-130">Um die Clienteinstellungen zu überprüfen, melden Sie sich vom Skype for Business-Client ab, melden Sie sich wieder an, und bestätigen Sie, dass der Client die Dienst-URL wie folgt erhalten hat:</span><span class="sxs-lookup"><span data-stu-id="76290-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="76290-131">%Appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. Öffnen</span><span class="sxs-lookup"><span data-stu-id="76290-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="76290-132">Suchen Sie nach "hybridconfigserviceinternalurl", und bestätigen Sie, dass die URL mit der von Ihnen definierten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="76290-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="76290-133">Ändern der Parameter für die medienumgehung</span><span class="sxs-lookup"><span data-stu-id="76290-133">Change media bypass parameters</span></span>

<span data-ttu-id="76290-134">Mandantenadministratoren können den DNS-Namen des Webdiensts ändern, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="76290-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="76290-135">Clients müssen sich abmelden und sich anmelden, um den neuen Dienstnamen zu erhalten und die Änderung zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="76290-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="76290-136">Medienumgehung vorübergehend deaktivieren</span><span class="sxs-lookup"><span data-stu-id="76290-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="76290-137">Dieses Szenario kann bei der Problembehandlung oder Wartung hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="76290-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="76290-138">Führen Sie die folgenden Cmdlets aus, um den Dienst zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="76290-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="76290-139">Nachdem Sie die Änderung vorgenommen haben, kann es einige Zeit dauern, bis Änderungen an alle Cloud-Konnektoren repliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="76290-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="76290-140">Um den Status der Replikation zu überprüfen, führen Sie das folgende Cmdlet in PowerShell auf den Vermittlungsservern von Cloud Connector aus:</span><span class="sxs-lookup"><span data-stu-id="76290-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="76290-141">Nachdem die Änderungen repliziert wurden, startet der Webdienst im Vermittlungsserver die Ablehnung von Clientanforderungen für den Medien Umgehungs Dienst.</span><span class="sxs-lookup"><span data-stu-id="76290-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="76290-142">Medienumgehung dauerhaft deaktivieren</span><span class="sxs-lookup"><span data-stu-id="76290-142">Disable media bypass permanently</span></span>

<span data-ttu-id="76290-143">Um die medienumgehung dauerhaft zu deaktivieren, muss ein mandantenadministrator die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="76290-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="76290-144">Ein Administrator muss außerdem die Webadressen für die medienumgehung von internen DNS-Servern entfernen.</span><span class="sxs-lookup"><span data-stu-id="76290-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="76290-145">Nachdem Sie die Änderung vorgenommen haben, kann es einige Zeit dauern, bis Änderungen an alle Cloud Connector-Appliances repliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="76290-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="76290-146">Beispiel: DNS-Einträge für die Medien Umgehungs Website in komplexen Umgebungen mit mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="76290-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="76290-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="76290-147"><a name="Example"> </a></span></span>

<span data-ttu-id="76290-148">Clients erhalten die Webadresse des Medien Umgehungs-Webdiensts von einem internen DNS-Server.</span><span class="sxs-lookup"><span data-stu-id="76290-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="76290-149">Der Name des Webdiensts ist für alle Cloud Connector-Appliances und Cloud Connector-PSTN-Standorte gleich.</span><span class="sxs-lookup"><span data-stu-id="76290-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="76290-150">In einer komplexen Umgebung mit mehreren Standorten empfiehlt es sich, die Windows 2016-DNS-Richtlinie für die Verwaltung geografischer Standorte zu verwenden, sodass Clients an den Webdienst umgeleitet werden können, der für Ihr Netzwerk lokal ist.</span><span class="sxs-lookup"><span data-stu-id="76290-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="76290-151">Weitere Informationen zu Windows 2016-DNS-Richtlinien finden Sie unter [use DNS Policy for Geo-Location based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="76290-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="76290-152">Im folgenden finden Sie ein Beispiel für die Konfiguration für ein Unternehmen mit mehreren Standorten, die die Windows 2016-DNS-Richtlinie für die Verwaltung von Geo-Standort-Datenverkehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="76290-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="76290-153">Der Name für den Bypass-Dienst lautet "hybridvoice.adatum.biz".</span><span class="sxs-lookup"><span data-stu-id="76290-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="76290-154">Auf der Website in Amsterdam sind vier Cloud Connector-Appliances mit den folgenden Vermittlungsserver-IP-Adressen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="76290-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="76290-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="76290-155">192.168.1.45</span></span>
    
- <span data-ttu-id="76290-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="76290-156">192.168.1.46</span></span>
    
- <span data-ttu-id="76290-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="76290-157">192.168.1.47</span></span>
    
- <span data-ttu-id="76290-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="76290-158">192.168.1.48</span></span>
    
<span data-ttu-id="76290-159">Die Website in Seattle verfügt über drei Cloud Connector-Appliances, die mit den folgenden Vermittlungsserver-IP-Adressen bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="76290-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="76290-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="76290-160">10.10.1.8</span></span>
    
- <span data-ttu-id="76290-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="76290-161">10.10.1.9</span></span>
    
- <span data-ttu-id="76290-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="76290-162">10.10.1.10</span></span>
    
<span data-ttu-id="76290-163">Mithilfe der geografischen standortbasierten Datenverkehrsverwaltung würden die DNS-Server wie folgt konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="76290-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="76290-164">Erstellen Sie DNS-Client-Subnetze für die Subnetze Amsterdam und Seattle.</span><span class="sxs-lookup"><span data-stu-id="76290-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="76290-165">Erstellen von DNS-Zonen Bereichen für adatum.biz für Amsterdam und Seattle.</span><span class="sxs-lookup"><span data-stu-id="76290-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="76290-166">Erstellen von DNS-Einträgen in jedem DNS-zonenbereich.</span><span class="sxs-lookup"><span data-stu-id="76290-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="76290-167">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="76290-167">Amsterdam</span></span>
    
   - <span data-ttu-id="76290-168">Geben Sie A ein;</span><span class="sxs-lookup"><span data-stu-id="76290-168">Type A;</span></span>
    
   - <span data-ttu-id="76290-169">Name: hybridvoice in der Adatum.biz-DNS-Zone</span><span class="sxs-lookup"><span data-stu-id="76290-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="76290-170">Ziel: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="76290-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="76290-171">Erstellen zusätzlicher Datensätze für zusätzliche Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="76290-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="76290-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="76290-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="76290-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="76290-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="76290-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="76290-174">192.168.1.48</span></span>
    
     <span data-ttu-id="76290-175">Seattle</span><span class="sxs-lookup"><span data-stu-id="76290-175">Seattle</span></span>
    
   - <span data-ttu-id="76290-176">Geben Sie A ein.</span><span class="sxs-lookup"><span data-stu-id="76290-176">Type A</span></span>
    
   - <span data-ttu-id="76290-177">Name: hybridvoice in der Adatum.biz-DNS-Zone</span><span class="sxs-lookup"><span data-stu-id="76290-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="76290-178">Ziel: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="76290-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="76290-179">Erstellen zusätzlicher Datensätze für zusätzliche Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="76290-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="76290-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="76290-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="76290-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="76290-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="76290-182">Erstellen Sie die DNS-Richtlinie, mit der die Client Subnetze mit den entsprechenden Zonen Bereichen verbunden werden, um die gewünschte DNS-Auflösung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="76290-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="76290-183">Zu diesem Zeitpunkt werden von Clients, die DNS-Abfragen aus dem Amsterdamer Subnetz für hybridvoice.adatum.biz durchführen, die 192.168.1.45-, 192.168.1.46-, 192.168.1.47-und 192.168.1.48-Adressen zurückgegeben, während Clients, die dasselbe Abfrage Formular in Seattle erstellen, 10.10.1.8, 10.10.1.9 und 10.10.1.10 zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="76290-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="76290-184">Wenn die CCE-Appliance anscheinend nicht die aktualisierten Einstellungen erhält, überprüfen Sie, ob die Appliance über Remote-PowerShell Kontakt mit dem Mandanten aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="76290-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="76290-185">Mithilfe von Remote-PowerShell können Sie den Appliance-Status mit Get-CsHybridPSTNAppliance überprüfen oder mithilfe von PowerShell auf dem CCE-Host den Status mit Get-CcApplianceStatus überprüfen.</span><span class="sxs-lookup"><span data-stu-id="76290-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="76290-186">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="76290-186">See also</span></span>
<span data-ttu-id="76290-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="76290-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="76290-188">Planen der Medienumgehung in der Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="76290-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
