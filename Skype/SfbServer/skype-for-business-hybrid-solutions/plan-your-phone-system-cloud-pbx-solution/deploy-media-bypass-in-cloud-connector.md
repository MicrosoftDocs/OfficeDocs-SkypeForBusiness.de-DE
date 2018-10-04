---
title: Die medienumgehung in der Cloud Connector Edition bereitstellen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lesen Sie dieses Thema Weitere Informationen zu den Schritten zum Bereitstellen von, dass die medienumgehung mit Cloud Connector Edition, Version 2.0 und höher.
ms.openlocfilehash: 841a243b236219fc70c99264249567f2eee63081
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375499"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="05795-103">Die medienumgehung in der Cloud Connector Edition bereitstellen</span><span class="sxs-lookup"><span data-stu-id="05795-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="05795-104">Lesen Sie dieses Thema Weitere Informationen zu den Schritten zum Bereitstellen von, dass die medienumgehung mit Cloud Connector Edition, Version 2.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="05795-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="05795-105">Die medienumgehung kann ein Client zum Senden von Medien direkt an den nächsten Hop (Public Switched Telephone Network, PSTN) – Session Border Controller (SBC) oder ein Gateway – und die Cloud Connector Edition-Komponente aus dem Medienpfad auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="05795-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="05795-106">Siehe auch [Planen Medien in der Cloud Connector Edition umgehen](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="05795-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="05795-107">Medienumgehung aktivieren</span><span class="sxs-lookup"><span data-stu-id="05795-107">Enable media bypass</span></span>

<span data-ttu-id="05795-108">Um die medienumgehung aktivieren, müssen Sie konfigurieren den DNS-Namen des Media Bypass-Webdiensts und schalten Sie die medienumgehung in der Mandantenkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="05795-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="05795-109">Der Media Bypass-Webdienst wird automatisch auf jedem Vermittlungsserver bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="05795-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="05795-110">Mandantenadministrator muss wählen Sie einen Namen für einen Hybrid-VoIP-Dienst (Website), und dieser Name aus einer SIP-Domäne für Hybrid-VoIP registriert sein.</span><span class="sxs-lookup"><span data-stu-id="05795-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="05795-111">Der Dienstname sollten über alle Cloud Connector Einheiten und alle PSTN-Websites, unabhängig von der Standort des Clients übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="05795-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="05795-112">Der Webdienst sollte nur intern im Netzwerk verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="05795-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="05795-113">Mandantenadministrator muss einen DNS-A-Eintrag in der internen Active Directory-Produktion konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="05795-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="05795-114">Wenn Sie eine komplexe Umgebung mit mehreren Standorte haben, finden Sie im Beispiel in [Beispiel: medienumgehung Website DNS-Einträgen in komplexen mit mehreren Umgebungen](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="05795-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="05795-115">Der DNS-Eintrag sollte nur für interne Netzwerkclients auflösen; Es sollte nicht für externe Netzwerkclients aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="05795-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="05795-116">Verbinden Sie nach der Konfiguration des DNS mit Skype für Business Online mithilfe von remote-PowerShell mit Skype Business Administratoranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="05795-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="05795-117">Weitere Informationen finden Sie unter [Connecting to Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="05795-117">For more information, see [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="05795-118">Geben Sie in der PowerShell-Sitzung die folgenden Befehle ein, um die Medienumgehung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="05795-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="05795-119">Aktivieren der medienumgehung umfasst zwei Schritte.</span><span class="sxs-lookup"><span data-stu-id="05795-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="05795-120">Das Cmdlet New-CsNetworkMedia speichern nicht sofort die neue Konfiguration. Es werden nur die Einstellungen im Arbeitsspeicher erstellt.</span><span class="sxs-lookup"><span data-stu-id="05795-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="05795-121">Das Objekt, das mit diesem Cmdlet erstellten muss in einer Variablen gespeichert, und klicken Sie dann an die MediaBypassSettings-Eigenschaft die Netzwerkkonfiguration zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="05795-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="05795-122">Weitere Informationen finden Sie unter [Beispiel: medienumgehung Website DNS-Einträgen in komplexen mit mehreren Umgebungen](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="05795-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="05795-123">Die Replikation zwischen den lokalen Komponenten und den Onlinekomponenten kann bis zu 24 Stunden dauern. Daher empfiehlt Microsoft, die notwendigen Befehle auszuführen, bevor Sie Benutzer aktivieren. 
</span><span class="sxs-lookup"><span data-stu-id="05795-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="05795-124">Überprüfen der Medienumgehungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="05795-124">Confirm media bypass settings</span></span>

<span data-ttu-id="05795-125">Sie können die Medienumgehungseinstellungen wie folgt überprüfen. </span><span class="sxs-lookup"><span data-stu-id="05795-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="05795-126">Führen Sie den folgenden Befehl zum Überprüfen des Mandanten Pools online-Replikation in remote-PowerShell:</span><span class="sxs-lookup"><span data-stu-id="05795-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="05795-127">Überprüfen Sie die lokale Replikation, eine Verbindung mit der Cloud Connector Vermittlungsserver, führen Sie den folgenden Befehl in PowerShell und vergewissern Sie sich, Enabled = True und AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="05795-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="05795-128">Zum Überprüfen der Clienteinstellungen Abmelden bei der Skype für Business-Client, erneut anmelden, und bestätigen Sie, dass der Client die Dienst-URL wie folgt erhalten hat:</span><span class="sxs-lookup"><span data-stu-id="05795-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="05795-129">Öffnen Sie „%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog“. </span><span class="sxs-lookup"><span data-stu-id="05795-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="05795-130">Suchen Sie nach „hybridconfigserviceinternalurl“, und vergewissern Sie sich, dass die URL mit der übereinstimmt, die Sie definiert haben. 
</span><span class="sxs-lookup"><span data-stu-id="05795-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="05795-131">Ändern von Medienumgehungsparametern</span><span class="sxs-lookup"><span data-stu-id="05795-131">Change media bypass parameters</span></span>

<span data-ttu-id="05795-132">Mandantenadministratoren können den DNS-Namen des Webdiensts ändern, indem sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="05795-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="05795-133">Clients müssen sich abmelden und dann wieder anmelden, um den neuen Dienstnahmen zu erhalten und die Änderung zu erkennen. </span><span class="sxs-lookup"><span data-stu-id="05795-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="05795-134">Vorübergehendes Deaktivieren der Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="05795-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="05795-p106">Dieses Szenario kann bei der Problembehandlung oder Wartung hilfreich sein. Um den Dienst zu deaktivieren, führen Sie die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="05795-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="05795-137">Nach der Änderung kann es einige Zeit Änderungen für die Replikation auf alle Cloud Connectors dauern.</span><span class="sxs-lookup"><span data-stu-id="05795-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="05795-138">Um den Status der Replikation zu überprüfen, führen Sie das folgende Cmdlet auf Cloud Connector Vermittlungsservern in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="05795-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="05795-139">Nach der Replikation der Änderungen lehnt der Webdienst auf dem Vermittlungsserver Clientanforderungen für den Medienumgehungsdienst ab.</span><span class="sxs-lookup"><span data-stu-id="05795-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="05795-140">Dauerhaftes Deaktivieren der Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="05795-140">Disable media bypass permanently</span></span>

<span data-ttu-id="05795-141">Um die Medienumgehung dauerhaft zu deaktivieren, muss ein Mandantenadministrator die folgenden Befehle ausführen: </span><span class="sxs-lookup"><span data-stu-id="05795-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="05795-142">Ein Administrator müssen auch die Webadressen für die medienumgehung von internen DNS-Servern zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="05795-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="05795-143">Nach der Änderung kann es Änderungen auf alle Cloud Connector Einheiten repliziert werden einige Zeit dauern.</span><span class="sxs-lookup"><span data-stu-id="05795-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="05795-144">Beispiel: DNS-Einträge für Medienumgehungs-Website in komplexen Umgebungen mit mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="05795-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="05795-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="05795-145"></span></span>

<span data-ttu-id="05795-146">Clients erhalten die Webadresse des Media Bypass-Webdiensts vom einen internen DNS-Server.</span><span class="sxs-lookup"><span data-stu-id="05795-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="05795-147">Der Name des Webdiensts wird in allen Cloud Connector Appliances und Cloud Connector PSTN Websites übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="05795-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="05795-148">In einer Umgebung mit komplexen mit mehreren Standorten wird empfohlen, die Windows 2016 DNS-Richtlinie für Geo-Location-basiertes Datenverkehr Management verwenden, damit Clients an den Webdienst umgeleitet werden können, die lokal für ihr Netzwerk ist.</span><span class="sxs-lookup"><span data-stu-id="05795-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="05795-149">Weitere Informationen zu Windows 2016 DNS-Richtlinien finden Sie unter [Verwendung DNS-Richtlinie für Geo-Location basierte Datenverkehr Management mit primären Servern](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="05795-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="05795-150">Das folgende Beispiel zeigt eine Konfiguration für eine Firma mit mehreren Standorten, in der eine Windows 2016-DNS-Richtlinie für geolocationbasierte Verwaltung des Datenverkehrs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05795-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="05795-151">"Hybridvoice.adatum.biz" ist der Name für den Dienst umgehen.</span><span class="sxs-lookup"><span data-stu-id="05795-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="05795-152">Die Website in Amsterdam besteht aus vier Cloud Connector Appliances mit den folgenden Mediation Server-IP-Adressen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="05795-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="05795-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="05795-153">192.168.1.45</span></span>
    
- <span data-ttu-id="05795-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="05795-154">192.168.1.46</span></span>
    
- <span data-ttu-id="05795-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="05795-155">192.168.1.47</span></span>
    
- <span data-ttu-id="05795-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="05795-156">192.168.1.48</span></span>
    
<span data-ttu-id="05795-157">Die Website in Seattle verfügt über drei Cloud Connector Appliances mit den folgenden Mediation Server-IP-Adressen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="05795-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="05795-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="05795-158">10.10.1.8</span></span>
    
- <span data-ttu-id="05795-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="05795-159">10.10.1.9</span></span>
    
- <span data-ttu-id="05795-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="05795-160">10.10.1.10</span></span>
    
<span data-ttu-id="05795-161">Mithilfe von geolocationbasierter Verwaltung des Datenverkehrs würden Sie die DNS-Server so konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="05795-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="05795-162">Erstellen Sie DNS-Clientsubnetze für die Subnetze von Amsterdam und Seattle.</span><span class="sxs-lookup"><span data-stu-id="05795-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="05795-163">Erstellen Sie für Amsterdam und Seattle DNS-Zonenbereiche für „adatum.biz“.</span><span class="sxs-lookup"><span data-stu-id="05795-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="05795-164">Erstellen Sie in jedem DNS-Zonenbereich DNS-Einträge.</span><span class="sxs-lookup"><span data-stu-id="05795-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="05795-165">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="05795-165">Amsterdam</span></span>
    
   - <span data-ttu-id="05795-166">Typ A</span><span class="sxs-lookup"><span data-stu-id="05795-166">Type A;</span></span>
    
   - <span data-ttu-id="05795-167">Name: „hybridvoice“ in der DNS-Zone für „adatum.biz“</span><span class="sxs-lookup"><span data-stu-id="05795-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="05795-168">Ziel: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="05795-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="05795-169">Erstellen Sie zusätzliche Einträge für weitere Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="05795-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="05795-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="05795-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="05795-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="05795-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="05795-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="05795-172">192.168.1.48</span></span>
    
     <span data-ttu-id="05795-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="05795-173">Seattle</span></span>
    
   - <span data-ttu-id="05795-174">Typ A</span><span class="sxs-lookup"><span data-stu-id="05795-174">Type A</span></span>
    
   - <span data-ttu-id="05795-175">Name: „hybridvoice“ in der DNS-Zone für „adatum.biz“</span><span class="sxs-lookup"><span data-stu-id="05795-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="05795-176">Ziel: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="05795-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="05795-177">Erstellen Sie zusätzliche Einträge für weitere Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="05795-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="05795-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="05795-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="05795-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="05795-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="05795-180">Erstellen Sie die DNS-Richtlinie, die die Clientsubnetze mit den entsprechenden Zonenbereichen verbindet, um die gewünschte DNS-Auflösung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="05795-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="05795-181">An dieser Stelle geben Clients aus dem Amsterdam-Subnetz die DNS-Abfragen für „hybridvoice.adatum.biz“ ausführen, die Adressen 192.168.1.45, 192.168.1.46, 192.168.1.47 und 192.168.1.48 zurück. Clients, die die gleiche Abfrage aus Seattle ausführen, geben dagegen 10.10.1.8, 10.10.1.9 und 10.10.1.10 zurück.</span><span class="sxs-lookup"><span data-stu-id="05795-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="05795-182">Wenn die Appliance CCE scheinbar nicht, die aktualisierten Einstellungen zu erhalten, überprüfen Sie, um festzustellen, ob das Gerät mit den Mandanten über remote-PowerShell eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="05795-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="05795-183">Remote-PowerShell können Sie überprüfen des Appliance Status mit Get-CsHybridPSTNAppliance oder mithilfe von PowerShell auf dem Host CCE um Status mit Get-CcApplianceStatus zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="05795-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="05795-184">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="05795-184">See also</span></span>
<span data-ttu-id="05795-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="05795-185"></span></span>

[<span data-ttu-id="05795-186">Planen der Medienumgehung in Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="05795-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
