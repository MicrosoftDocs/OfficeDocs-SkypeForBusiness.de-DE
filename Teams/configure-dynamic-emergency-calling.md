---
title: Konfigurieren von dynamischen Notrufen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Konfigurieren von dynamischen Notrufen
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516932"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="8a6f4-103">Planen und Konfigurieren von dynamischen Notrufen für Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="8a6f4-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="8a6f4-104">Dynamische Notrufe für Microsoft-Anrufpläne bieten die Möglichkeit, Notrufe auf der Grundlage des aktuellen Standorts des Teams-Clients zu konfigurieren und zu leiten.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="8a6f4-105">Die Möglichkeit zur automatischen Weiterleitung an den entsprechenden öffentlichen Sicherheits-Anrufbeantworter (PSAP) oder zur Benachrichtigung über das Personal von Sicherheitsmitarbeitern variiert je nach dem Land, in dem der Benutzer des Teams verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="8a6f4-106">Dynamische Notrufe stehen derzeit nur in den Vereinigten Staaten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="8a6f4-107">Security Desk-Benachrichtigungen werden jedoch über Ländergrenzen hinweg unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="8a6f4-108">**In den Vereinigten Staaten**können Sie das dynamische Notfall Anrufrouting wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8a6f4-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="8a6f4-109">Wenn sich ein Team-Client an einem vom Mandanten definierten dynamischen Notfall Standort befindet, werden Notrufe von diesem Client automatisch an die PSAP weitergeleitet, die diesem geografischen Standort dienen.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="8a6f4-110">Wenn sich ein Teams-Client nicht an einem vom Mandanten definierten dynamischen Notfall Standort befindet, werden Notrufe von diesem Client von einem nationalen Callcenter durchlaufen, um den Standort des Anrufers zu ermitteln, bevor der Anruf an die PSAP, die diesen geografischen Standort bedient, übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="8a6f4-111">Sie können die Benachrichtigung über das Sicherheits Desk wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8a6f4-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="8a6f4-112">Wenn sich ein Team-Client auf einer vom Mandanten definierten Netzwerk Website befindet, werden die für diese Website konfigurierten Mitglieder der Sicherheitsgruppe benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="8a6f4-113">Wenn sich ein Team-Client nicht auf einer vom Mandanten definierten Netzwerk Website befindet, werden die für den Benutzer konfigurierten Sicherheitsgruppen Mitglieder benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="8a6f4-114">**Außerhalb der Vereinigten Staaten**werden Notrufe an die PSAP weitergeleitet, die der dem Benutzer zugewiesenen Telefonnummer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="8a6f4-115">Einige Länder, wie Großbritannien und Kanada, übertragen die Anrufe auf nationaler Ebene, bevor Sie den Anrufer an die entsprechende PSAP, während andere Personen direkt an das PSAP weiterleiten, unabhängig davon, wo sich der Benutzer gerade befindet.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="8a6f4-116">Beachten Sie, dass Sie die Dynamic Security Desk-Benachrichtigung für alle Benutzer des Anruf Plans konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="8a6f4-117">Unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="8a6f4-117">Supported clients</span></span>

<span data-ttu-id="8a6f4-118">Die folgenden Clients werden zurzeit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-118">The following clients are currently supported.</span></span>  <span data-ttu-id="8a6f4-119">Schauen Sie sich häufig an, um Updates für diese Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="8a6f4-120">Teams-Desktop Client für Windows</span><span class="sxs-lookup"><span data-stu-id="8a6f4-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="8a6f4-121">Teams-Desktop Client für Mac</span><span class="sxs-lookup"><span data-stu-id="8a6f4-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="8a6f4-122">Konfigurieren von dynamischen Notrufen</span><span class="sxs-lookup"><span data-stu-id="8a6f4-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="8a6f4-123">Um dynamische Notrufe konfigurieren zu können, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="8a6f4-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="8a6f4-124">Konfigurieren von Notfalladressen</span><span class="sxs-lookup"><span data-stu-id="8a6f4-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="8a6f4-125">Konfigurieren von Netzwerkeinstellungen</span><span class="sxs-lookup"><span data-stu-id="8a6f4-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="8a6f4-126">Konfigurieren des Standort Informationsdiensts</span><span class="sxs-lookup"><span data-stu-id="8a6f4-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="8a6f4-127">Konfigurieren von Notfall Richtlinien</span><span class="sxs-lookup"><span data-stu-id="8a6f4-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="8a6f4-128">Aktivieren von Benutzern und Websites</span><span class="sxs-lookup"><span data-stu-id="8a6f4-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="8a6f4-129">Testen von Notrufen</span><span class="sxs-lookup"><span data-stu-id="8a6f4-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="8a6f4-130">Konfigurieren von Notfalladressen</span><span class="sxs-lookup"><span data-stu-id="8a6f4-130">Configure emergency addresses</span></span>

<span data-ttu-id="8a6f4-131">Zur Unterstützung des automatisierten Routings innerhalb der USA müssen Sie die bürgerliche Adresse, die Teil der Notfall Speicherorte ist, die Netzwerkkennungen zugeordnet sind, vollständig konfigurieren und die zugehörigen Geo-Codes einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="8a6f4-132">(Notfalladressen ohne Geo-Codes können nicht den Netzwerk Bezeichnern zugewiesen werden, die für dynamische Speicherorte erforderlich sind.)</span><span class="sxs-lookup"><span data-stu-id="8a6f4-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="8a6f4-133">Wenn Sie eine Notfalladresse über das Microsoft Teams Admin Center eingeben, werden die Geo-Codes automatisch einbezogen, wenn eine Übereinstimmung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="8a6f4-134">Wenn eine Übereinstimmung nicht automatisch gefunden wird, haben Sie die Möglichkeit, eine Notfalladresse manuell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="8a6f4-135">Das bedeutet: Wenn eine vorhandene Notfalladresse für Notrufe konfiguriert ist, muss dieselbe Adresse neu erstellt werden, um die Geo-Codes einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="8a6f4-136">Wenn Sie zwischen den beiden Adressen unterscheiden möchten, sollten Sie eine andere Beschreibung angeben.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="8a6f4-137">Die neue Notfalladresse kann den Benutzern zugewiesen werden, die die alte Adresse besitzen.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="8a6f4-138">Nach der vollständigen Migration kann die alte Adresse gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="8a6f4-139">Weitere Informationen zum Konfigurieren von Notfalladressen finden Sie unter [Was sind Notfall Standorte, Orte und Anrufweiterleitung?](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="8a6f4-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="8a6f4-140">Konfigurieren von Netzwerkeinstellungen</span><span class="sxs-lookup"><span data-stu-id="8a6f4-140">Configure network settings</span></span>

<span data-ttu-id="8a6f4-141">Sie müssen die Netzwerkeinstellungen so konfigurieren, dass dynamisch ein Notfall Standort für das Routing von Notrufen abgerufen und optional eine dynamische Konfiguration von Benachrichtigungen über Sicherheits Desk bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="8a6f4-142">Die gewünschte Notruffunktion bestimmt, welche Netzwerkeinstellungen konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="8a6f4-143">Beachten Sie die folgenden Definitionen:</span><span class="sxs-lookup"><span data-stu-id="8a6f4-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="8a6f4-144">Vertrauenswürdige IP-Adressen enthalten eine Sammlung der externen Internet-IPS des Unternehmensnetzwerks und werden verwendet, um festzustellen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="8a6f4-145">Dynamische Speicherorte werden nur aktiviert, wenn die externe IP-Adresse des Benutzers einer IP-Adresse in der vertrauenswürdigen IP-Sammlung entspricht.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="8a6f4-146">Eine Übereinstimmung kann entweder für IPv4-oder IPv6-IP-Adressen erfolgen und hängt vom Format des IP-Pakets ab, das an die Netzwerkeinstellungen gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="8a6f4-147">Eine Netzwerkregion enthält verschiedene Netzwerkstandorte.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="8a6f4-148">Eine Netzwerk Website steht für einen Standort, an dem Ihre Organisation über einen physikalischen Wert verfügt, beispielsweise ein Büro, einen Satz von Gebäuden oder einen Campus.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="8a6f4-149">Diese Websites sind als eine Sammlung von IP-Subnetzen definiert.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="8a6f4-150">Ein Netzwerk-Subnetz muss einer bestimmten Netzwerk Website zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="8a6f4-151">Der Standort eines Clients wird basierend auf dem Netzwerk-Subnetz und der zugehörigen Netzwerk Website bestimmt.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="8a6f4-152">Für Benutzer von Plan anrufen:</span><span class="sxs-lookup"><span data-stu-id="8a6f4-152">For Calling Plan users:</span></span>

- <span data-ttu-id="8a6f4-153">Wenn die dynamische Konfiguration von Security Desk-Benachrichtigungen erforderlich ist, müssen Sie sowohl vertrauenswürdige IP-Adressen als auch Netzwerk Websites konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="8a6f4-154">Wenn nur dynamische Speicherorte erforderlich sind, müssen Sie nur vertrauenswürdige IP-Adressen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="8a6f4-155">Wenn keines von beiden erforderlich ist, ist die Konfiguration von Netzwerkeinstellungen nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="8a6f4-156">Weitere Informationen finden Sie unter [Konfigurieren von Netzwerkeinstellungen für standortbasiertes Routing](location-based-routing-configure-network-settings.md), das beschreibt, wie Netzwerkeinstellungen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="8a6f4-157">(Die Informationen in diesem Artikel beziehen sich auf Anrufpläne und direktes Routing.)</span><span class="sxs-lookup"><span data-stu-id="8a6f4-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="8a6f4-158">Konfigurieren des Standort Informationsdiensts</span><span class="sxs-lookup"><span data-stu-id="8a6f4-158">Configure Location Information Service</span></span>

<span data-ttu-id="8a6f4-159">Ein Team-Client ruft Notfalladressen von den Notfall Standorten ab, die mit verschiedenen Netzwerkkennungen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="8a6f4-160">Subnetze und drahtlose Zugriffspunkte werden beide unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="8a6f4-161">(Unterstützung für Ethernet-Switch/-Port ist ausstehend.)</span><span class="sxs-lookup"><span data-stu-id="8a6f4-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="8a6f4-162">Verwenden Sie die folgenden Cmdlets, um den standortinformationsdienst (LIS) mit Netzwerkkennungen und Notfall Speicherorten zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8a6f4-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="8a6f4-163">Abrufen, einrichten, entfernen-CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="8a6f4-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="8a6f4-164">Abrufen, einrichten, entfernen-CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="8a6f4-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="8a6f4-165">Abrufen, einrichten, entfernen-CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="8a6f4-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="8a6f4-166">Abrufen, einrichten, entfernen-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="8a6f4-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="8a6f4-167">Wenn Subnetze als Teil von Netzwerk Websites verwendet werden, müssen Sie im standortinformationsdienst neu definiert werden, um dynamische Speicherorte zu rendern.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="8a6f4-168">Konfigurieren von Notfall Richtlinien</span><span class="sxs-lookup"><span data-stu-id="8a6f4-168">Configure emergency policies</span></span>

<span data-ttu-id="8a6f4-169">Notfall Richtlinien legen fest, was geschieht, wenn ein Benutzer in Ihrer Organisation einen Notfall Anruf tätigt.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="8a6f4-170">Sie können feststellen, wer benachrichtigt werden soll und wie Sie benachrichtigt werden, wenn ein Benutzer Notrufdienste anruft.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="8a6f4-171">So können Sie beispielsweise Richtlinieneinstellungen so konfigurieren, dass Sie den Security Desk Ihrer Organisation automatisch benachrichtigen und bei Notrufen anhören.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="8a6f4-172">Sie verwalten Notfall Richtlinien mithilfe der Cmdlets für neu-, Satz-und Grant-CsTeamsEmergencyCalling-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="8a6f4-173">Weitere Informationen finden Sie unter [Verwalten von Notruf Richtlinien in Teams](manage-emergency-calling-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8a6f4-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="8a6f4-174">Aktivieren von Benutzern und Websites</span><span class="sxs-lookup"><span data-stu-id="8a6f4-174">Enable users and sites</span></span>

<span data-ttu-id="8a6f4-175">Während die Benutzer des Anruf Plans automatisch für Notrufe aktiviert sind, müssen Sie die Benutzer für die Benachrichtigung über das Security Desk aktivieren, indem Sie die Notruf Richtlinie konfigurieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8a6f4-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="8a6f4-176">Sie können die Notruf Richtlinie auch einer Netzwerk Website zuweisen, wie im folgenden Beispiel gezeigt, das eine Richtlinie namens "Contoso Emergency Calling Policy 1" zu Site 1 zuweist:</span><span class="sxs-lookup"><span data-stu-id="8a6f4-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="8a6f4-177">Wenn Sie einer Netzwerk Website und einem Benutzer eine Notruf Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="8a6f4-178">Testen von Notrufen</span><span class="sxs-lookup"><span data-stu-id="8a6f4-178">Test emergency calling</span></span>

<span data-ttu-id="8a6f4-179">Um Notrufe in den Vereinigten Staaten zu testen, verwenden Sie die vordefinierte Test Notfallnummer 933.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="8a6f4-180">Diese Nummer wird an einen bot weitergeleitet, der dann wieder die Rufnummer des Anrufers (Rufnummernanzeige), die Notfalladresse oder den Standort zurückgibt und feststellt, ob der Anruf automatisch an die PSAP weitergeleitet oder zuerst übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="8a6f4-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  