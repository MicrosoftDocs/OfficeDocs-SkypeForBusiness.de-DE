---
title: Konfigurieren eines Session Border Controller für mehrere Mandanten
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Informationen Sie zum Konfigurieren einer Session Border Controller (SBC), um mehrere Mandanten zu verarbeiten.
ms.openlocfilehash: 537058eef62197a9df8659ed4c3f50802f2f19a1
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "23845517"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="4ea0a-103">Konfigurieren eines Session Border Controller für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="4ea0a-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="4ea0a-104">Direktes Routing unterstützt Konfigurieren einer Session Border Controller (SBC), um mehrere Mandanten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="4ea0a-105">In diesem Szenario dient zur Microsoft-Partnern und/oder PSTN Netzbetreibern, die als Netzbetreiber weiter unten in diesem Dokument bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="4ea0a-106">Ein Netzbetreiber verkauft Telefoniediensten an Microsoft-Teams, ihren Kunden übermittelt.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="4ea0a-107">Ein Netzbetreiber:</span><span class="sxs-lookup"><span data-stu-id="4ea0a-107">A carrier:</span></span>
- <span data-ttu-id="4ea0a-108">Wird bereitgestellt und verwaltet einen SBC im Rechenzentrum (Benutzer müssen sich nicht um einen SBC zu implementieren und sie erhalten Telefoniediensten aus der Netzbetreiber im Teams-Client).</span><span class="sxs-lookup"><span data-stu-id="4ea0a-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="4ea0a-109">Sind den SBC für mehrere Mandanten.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="4ea0a-110">Bietet Services PSTN Kunden.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="4ea0a-111">Verwaltet die Anrufqualität Ende zu Ende.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="4ea0a-112">Gebühren separat für PSTN-Dienste.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="4ea0a-113">Netzbetreiber wird nicht von Microsoft verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="4ea0a-114">Microsoft bietet eine Nebenstellenanlage (Microsoft Telefonsystem) und einem Client Teams, Telefone zertifiziert und zertifiziert SBCs, die in der Microsoft-Telefonsystem verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="4ea0a-115">Bevor Sie einen Netzbetreiber auswählen, stellen Sie sicher, dass Ihrer Wahl über eine zertifizierten SBC und Sprachqualität Ende zum Verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="4ea0a-116">Es folgen die technischen Implementierungsschritte zum Konfigurieren der Szenarios.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="4ea0a-117">**Netzbetreiber:**</span><span class="sxs-lookup"><span data-stu-id="4ea0a-117">**Carrier only:**</span></span>
1. <span data-ttu-id="4ea0a-118">Bereitstellen Sie den SBC, und konfigurieren sie für das hosting Szenario gemäß den [Anweisungen der zertifizierten SBC-Anbieter](#deploy-and-configure-the-sbc).</span><span class="sxs-lookup"><span data-stu-id="4ea0a-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="4ea0a-119">Registrieren Sie einer Benutzerbasis-Domänenname in den Mandanten Netzbetreiber und fordern Sie ein Platzhalterzertifikat an.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="4ea0a-120">Registrieren Sie eine Unterdomäne für jeden Kunden, die Teil der Basis Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="4ea0a-121">**Netzbetreiber mit Kunden globaler Administrator:**</span><span class="sxs-lookup"><span data-stu-id="4ea0a-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="4ea0a-122">Hinzufügen der Unterdomäne Name, die dem Kunden-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="4ea0a-123">Der Name der Unterdomäne zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="4ea0a-124">Konfigurieren Sie den Trunk aus der Netzbetreiber Benutzern Kunden Mandanten und bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="4ea0a-125">*Stellen Sie sicher, dass Sie die Grundlagen von DNS und Verwaltung von der Domänennamen in Office 365 kennen. Überprüfen Sie vor dem Fortsetzen des Vorgangs [Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="4ea0a-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="4ea0a-126">Bereitstellen Sie und konfigurieren Sie den SBC</span><span class="sxs-lookup"><span data-stu-id="4ea0a-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="4ea0a-127">Die detaillierte Schritte zum Bereitstellen und SBCs für einen SBC-hosting-Szenario konfigurieren finden Sie in den SBC Herstellers.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="4ea0a-128">**AudioCodes:** [Direkte Routingkonfiguration Notizen](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), die Konfiguration von den SBC Hosten in "Connecting AudioCodes SBC zu Microsoft-Teams, direkte Routing Hosting-Modell Konfiguration Notiz" beschriebenen Szenario</span><span class="sxs-lookup"><span data-stu-id="4ea0a-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="4ea0a-129">**Des Menübands Communications:** Für SBC Hostingszenarios wird nur die Serie Core unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-129">**Ribbon Communications:** For SBC hosting scenarios, only the core series is supported.</span></span> <span data-ttu-id="4ea0a-130">Bitte finden Sie im [Menüband Communications SBC Core Microsoft Teams Konfigurationshandbuch](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe).</span><span class="sxs-lookup"><span data-stu-id="4ea0a-130">Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe).</span></span>

> [!NOTE]
> <span data-ttu-id="4ea0a-131">Bitte achten Sie auf die Kopfzeile "Kontakt" zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-131">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="4ea0a-132">Die Kontakt Kopfzeile wird verwendet, um den Mandanten Kunden auf eingehende Invite-Nachricht zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-132">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="4ea0a-133">Registrieren einer Basis Domäne und Unterdomänen</span><span class="sxs-lookup"><span data-stu-id="4ea0a-133">Register a base domain and subdomains</span></span>

<span data-ttu-id="4ea0a-134">Sie müssen für das hosting-Szenario erstellen:</span><span class="sxs-lookup"><span data-stu-id="4ea0a-134">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="4ea0a-135">Eine Benutzerbasis-Domänenname Besitz der Netzbetreiber.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-135">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="4ea0a-136">Eine untergeordnete Domäne, die Bestandteil der Benutzerbasis-Domänenname in jeder Mandant des Kunden ist.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-136">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="4ea0a-137">Im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4ea0a-137">In the following example:</span></span>
- <span data-ttu-id="4ea0a-138">Adatum ist einem Netzbetreiber abgeschlossen, die mehrere Privatkunden durch Bereitstellen von Diensten für Internet- und Telefonie.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-138">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="4ea0a-139">Woodgrove Bank, Contoso und Adventure Works sind drei Kunden, die Office 365-Domänen, aber die Telefondienste von Adatum empfangen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-139">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="4ea0a-140">Unterdomänen **müssen** entsprechen den Vollqualifizierten Domänennamen des Trunks, die beim Senden der Einladung zu Office 365 für den Kunden und den FQDN in der Kopfzeile Kontakt konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-140">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="4ea0a-141">Wenn ein Anruf an den Office 365 direkten Routing-Schnittstelle ankommt, verwendet die Schnittstelle die Kopfzeile des Kontakts, um den Mandanten zu erhalten, in dem der Benutzer gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-141">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="4ea0a-142">Direktes Routing wird nicht verwendet, Nachschlagen Telefon auf einladen, wie einige Kunden möglicherweise nicht-DID-Nummern, die in mehreren Mandanten überlappen können.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-142">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="4ea0a-143">Aus diesem Grund ist der FQDN in der Kopfzeile des Kontakts erforderlich identifiziert den genauen Mandanten zum Nachschlagen von der Benutzer von der Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-143">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="4ea0a-144">*Weitere Informationen zum Erstellen von Domänennamen in Office 365-Mandanten [Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) überprüfen.*</span><span class="sxs-lookup"><span data-stu-id="4ea0a-144">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="4ea0a-145">Im folgende Diagramm sind die Anforderungen zur Basis Domäne, untergeordnete Domänen und Kontakt Kopfzeile zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-145">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![Anforderungen zu grundlegenden Unterdomänen und Contact-header](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="4ea0a-147">Der SBC erfordert ein Zertifikat aus, um die Verbindungen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-147">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="4ea0a-148">Für das hosting SBC-Szenario muss der Netzbetreiber zum Anfordern eines Zertifikats mit SAN \* \*.base_domain (beispielsweise \*customers.adatum.biz)\*.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-148">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="4ea0a-149">Dieses Zertifikat kann verwendet werden, um Verbindungen für mehrere Mandanten aus einer einzelnen SBC bedient zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-149">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="4ea0a-150">In der folgenden Tabelle ist ein Beispiel für eine Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-150">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="4ea0a-151">Name der neuen Domäne</span><span class="sxs-lookup"><span data-stu-id="4ea0a-151">New domain name</span></span> |<span data-ttu-id="4ea0a-152">Typ</span><span class="sxs-lookup"><span data-stu-id="4ea0a-152">Type</span></span>|<span data-ttu-id="4ea0a-153">Registriert</span><span class="sxs-lookup"><span data-stu-id="4ea0a-153">Registered</span></span>  |<span data-ttu-id="4ea0a-154">Zertifikat für SBC SAN</span><span class="sxs-lookup"><span data-stu-id="4ea0a-154">Certificate SAN for SBC</span></span>  |<span data-ttu-id="4ea0a-155">Mandanten Standarddomäne im Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ea0a-155">Tenant default domain in the example</span></span>  |<span data-ttu-id="4ea0a-156">FQDN ein, der in der Kopfzeile des Kontakts SBC präsentieren muss, wenn Anrufe an Benutzer senden</span><span class="sxs-lookup"><span data-stu-id="4ea0a-156">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="4ea0a-157">Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-157">customers.adatum.biz</span></span>|    <span data-ttu-id="4ea0a-158">Base</span><span class="sxs-lookup"><span data-stu-id="4ea0a-158">Base</span></span>     |     <span data-ttu-id="4ea0a-159">In Netzbetreiber Mandanten</span><span class="sxs-lookup"><span data-stu-id="4ea0a-159">In carrier tenant</span></span>  |    <span data-ttu-id="4ea0a-160">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-160">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="4ea0a-161">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-161">adatum.biz</span></span>      |<span data-ttu-id="4ea0a-162">NA, handelt es sich um einen Dienst Mandanten, keine Benutzer</span><span class="sxs-lookup"><span data-stu-id="4ea0a-162">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="4ea0a-163">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-163">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="4ea0a-164">Unterdomäne</span><span class="sxs-lookup"><span data-stu-id="4ea0a-164">Subdomain</span></span>  |    <span data-ttu-id="4ea0a-165">In einem Mandanten Kunden</span><span class="sxs-lookup"><span data-stu-id="4ea0a-165">In a customer tenant</span></span>  |    <span data-ttu-id="4ea0a-166">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-166">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="4ea0a-167">woodgrovebank.US</span><span class="sxs-lookup"><span data-stu-id="4ea0a-167">woodgrovebank.us</span></span>  |  <span data-ttu-id="4ea0a-168">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-168">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="4ea0a-169">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-169">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="4ea0a-170">Unterdomäne</span><span class="sxs-lookup"><span data-stu-id="4ea0a-170">Subdomain</span></span> | <span data-ttu-id="4ea0a-171">In einem Mandanten Kunden</span><span class="sxs-lookup"><span data-stu-id="4ea0a-171">In a customer tenant</span></span>   |   <span data-ttu-id="4ea0a-172">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-172">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="4ea0a-173">"contoso.com"</span><span class="sxs-lookup"><span data-stu-id="4ea0a-173">contoso.com</span></span>   |<span data-ttu-id="4ea0a-174">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-174">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="4ea0a-175">SBC3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-175">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="4ea0a-176">Unterdomäne</span><span class="sxs-lookup"><span data-stu-id="4ea0a-176">Subdomain</span></span> | <span data-ttu-id="4ea0a-177">In einem Mandanten Kunden</span><span class="sxs-lookup"><span data-stu-id="4ea0a-177">In a customer tenant</span></span> |   <span data-ttu-id="4ea0a-178">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-178">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="4ea0a-179">AdventureWorks.com</span><span class="sxs-lookup"><span data-stu-id="4ea0a-179">adventureworks.com</span></span> | <span data-ttu-id="4ea0a-180">SBC3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-180">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="4ea0a-181">Um die Base und Unterdomänen zu konfigurieren, führen Sie die unten beschriebenen Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-181">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="4ea0a-182">Im Beispiel wird eine Benutzerbasis-Domänenname (customers.adatum.biz) und eine Unterdomäne für einen bestimmten Kunden (sbc1.customers.adatum.biz in Woodgrove Bank-Mandanten) konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-182">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="4ea0a-183">Registrieren Sie eine Benutzerbasis-Domänenname in den Mandanten Netzbetreiber</span><span class="sxs-lookup"><span data-stu-id="4ea0a-183">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="4ea0a-184">**Diese Aktionen werden in den Mandanten Netzbetreiber ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="4ea0a-184">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="4ea0a-185">Stellen Sie sicher, dass Sie den Mandanten Netzbetreiber erforderlichen Berechtigungen verfügen</span><span class="sxs-lookup"><span data-stu-id="4ea0a-185">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="4ea0a-186">Sie können nur neue Domänen hinzufügen, wenn Sie Office 365 Admin Center als ein globaler Administrator angemeldet.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-186">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="4ea0a-187">Um Ihnen die Rolle zu überprüfen, melden Sie sich der Microsoft-365-Verwaltungskonsole (https://portal.office.com), fahren Sie mit der **Benutzer** > **Aktive Benutzer**, und stellen Sie sicher, dass Sie eine globalen Administratorrolle verfügen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-187">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="4ea0a-188">Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter [Informationen zu Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="4ea0a-188">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="4ea0a-189">Hinzufügen einer Basis Domäne, die dem Mandanten, und bestätigen Sie es</span><span class="sxs-lookup"><span data-stu-id="4ea0a-189">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="4ea0a-190">Wechseln Sie in das Microsoft 365 Administrationscenter zu **Setup** > **Domänen** > **Domäne hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-190">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="4ea0a-191">Geben Sie den FQDN der Basis-Domäne, in das Feld **Geben Sie eine Domäne, die Sie besitzen** .</span><span class="sxs-lookup"><span data-stu-id="4ea0a-191">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="4ea0a-192">Im folgenden Beispiel wird die Basiskalender Domäne *customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-192">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![Hinzufügen einer Basis Domäne](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="4ea0a-194">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-194">Click **Next**.</span></span>
4. <span data-ttu-id="4ea0a-195">Im Beispiel hat der Mandanten adatum.biz bereits als Namen einer überprüften Domäne.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-195">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="4ea0a-196">Der Assistent fordert nicht für eine zusätzliche Überprüfung, da customers.adatum.biz eine Unterdomäne für den Namen bereits registriert ist.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-196">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="4ea0a-197">Wenn Sie einen vollqualifizierten Domänennamen, der nicht hinzufügen vor überprüft wurde, müssen Sie über den Prozess der Überprüfung geleitet.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-197">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="4ea0a-198">Die Überprüfung wird [unten beschriebenen](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span><span class="sxs-lookup"><span data-stu-id="4ea0a-198">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![Bestätigung eines Domänennamens verfied](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="4ea0a-200">Klicken Sie auf **Weiter**, und wählen Sie auf der Seite **Einstellungen für DNS-Updates** **ich fügen die DNS-Datensätze selbst** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-200">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="4ea0a-201">Deaktivieren Sie auf der nächsten Seite alle Werte (es sei denn, Sie den Domänennamen für Exchange, SharePoint oder Teams/Skype für Unternehmen verwenden möchten), klicken Sie auf **Weiter**, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-201">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="4ea0a-202">Stellen Sie sicher, dass die neue Domäne im Status Setup abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-202">Make sure your new domain is in the Setup complete status.</span></span>

    ![Domänen mit dem Status der Installation abgeschlossen](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="4ea0a-204">Aktivieren Sie den Domänennamen</span><span class="sxs-lookup"><span data-stu-id="4ea0a-204">Activate the domain name</span></span>

<span data-ttu-id="4ea0a-205">Nachdem Sie einen Domänennamen registriert haben, müssen Sie mindestens einen Benutzer hinzufügen zu aktivieren, und weisen Sie eine SIP-Adresse mit dem FQDN-Abschnitt, der die SIP-Adresse die erstellte Basiskalender Domäne entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-205">After you have registered a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span>

<span data-ttu-id="4ea0a-206">*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Mandanten [Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) überprüfen.*</span><span class="sxs-lookup"><span data-stu-id="4ea0a-206">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="4ea0a-207">Beispiel: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-207">For example: test@customers.adatum.biz</span></span>

![Die Aktivierungsseite Basis Domäne](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="4ea0a-209">Registrieren Sie einen Unterdomänennamen in einem Mandanten Kunden</span><span class="sxs-lookup"><span data-stu-id="4ea0a-209">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="4ea0a-210">Sie müssen eine eindeutige Unterdomänennamen für jeden Kunden zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-210">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="4ea0a-211">In diesem Beispiel erstellen wir eine Unterdomäne sbc1.customers.adatum.biz in einem Mandanten mit der standardmäßigen Domain Name woodgrovebank.us.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-211">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="4ea0a-212">**Alle nachfolgenden Aktionen sind in den Kunden-Mandanten.**</span><span class="sxs-lookup"><span data-stu-id="4ea0a-212">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="4ea0a-213">Stellen Sie sicher, dass Sie den Mandanten Kunden erforderlichen Berechtigungen verfügen</span><span class="sxs-lookup"><span data-stu-id="4ea0a-213">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="4ea0a-214">Sie können nur neue Domänen hinzufügen, wenn Sie Office 365 Admin Center als ein globaler Administrator angemeldet.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-214">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="4ea0a-215">Um Ihnen die Rolle zu überprüfen, melden Sie sich der Microsoft-365-Verwaltungskonsole (https://portal.office.com), fahren Sie mit der **Benutzer** > **Aktive Benutzer**, und stellen Sie sicher, dass Sie eine globalen Administratorrolle verfügen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-215">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="4ea0a-216">Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter [Informationen zu Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="4ea0a-216">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="4ea0a-217">Den Mandanten Kunden eine Unterdomäne hinzu, und bestätigen Sie es</span><span class="sxs-lookup"><span data-stu-id="4ea0a-217">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="4ea0a-218">Wechseln Sie in das Microsoft 365 Administrationscenter zu **Setup** > **Domänen** > **Domäne hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-218">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="4ea0a-219">Geben Sie den FQDN des die Unterdomäne für diesen Mandanten, in das Feld **Geben Sie eine Domäne, die Sie besitzen** .</span><span class="sxs-lookup"><span data-stu-id="4ea0a-219">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="4ea0a-220">Im folgenden Beispiel wird die Unterdomäne sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-220">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![Hinzufügen einer Unterdomäne Kunden](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="4ea0a-222">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-222">Click **Next**.</span></span>
4. <span data-ttu-id="4ea0a-223">Der FQDN wurde im Mandanten noch nie registriert.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-223">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="4ea0a-224">Im nächsten Schritt müssen Sie die Domäne überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-224">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="4ea0a-225">Wählen Sie aus, **Fügen Sie stattdessen eine TXT-Eintrag hinzu**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-225">Select **Add a TXT record instead**.</span></span> 

    ![Optionen auf der Seite Domäne überprüfen](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="4ea0a-227">Klicken Sie auf **Weiter**, und notieren Sie den TXT-Wert generiert, um den Domänennamen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-227">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![Textdatensätze auf der Seite Domäne überprüfen](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="4ea0a-229">Erstellen der TXT-Eintrag mit dem Wert aus dem vorherigen Schritt im DNS-Hostinganbieter des Mobilfunkbetreibers.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-229">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![Erstellen der TXT-Eintrag in der Netzbetreiber DNS-Hostinganbieter](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="4ea0a-231">Weitere Informationen finden Sie in [Erstellen von DNS-Datensätze an alle DNS-Hostinganbieter für Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span><span class="sxs-lookup"><span data-stu-id="4ea0a-231">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="4ea0a-232">Gehen Sie zurück zu der Kunde Microsoft 365 Administrationscenter, und klicken Sie auf **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-232">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="4ea0a-233">Klicken Sie auf der nächsten Seite Wählen Sie **ich werde die DNS-Datensätze selbst hinzufügen** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-233">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![Optionen auf der Seite Update DNS-Einstellungen](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="4ea0a-235">Klicken Sie auf der Seite **Wählen Sie Ihre online-Dienste** deaktivieren Sie alle Optionen, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-235">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![Wählen Sie die online-Dienste-Seite](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="4ea0a-237">Klicken Sie auf der Seite **Update DNS-Einstellungen** auf **Fertig stellen** .</span><span class="sxs-lookup"><span data-stu-id="4ea0a-237">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![Seite Update DNS-Einstellungen](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="4ea0a-239">Stellen Sie sicher, dass der Status **Setup abgeschlossen**ist.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-239">Ensure that the status is **Setup complete**.</span></span> 
    
    ![Seite Status von Setup vollständig anzeigen](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="4ea0a-241">Aktivieren Sie den Unterdomänennamen</span><span class="sxs-lookup"><span data-stu-id="4ea0a-241">Activate the subdomain name</span></span>

<span data-ttu-id="4ea0a-242">Nachdem Sie einen Domänennamen registrieren, müssen Sie mindestens einen Benutzer hinzufügen zu aktivieren, und weisen Sie eine SIP-Adresse mit dem FQDN-Abschnitt, der die SIP-Adresse die erstellte Unterdomäne im Customer Mandanten übereinstimmenden.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-242">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="4ea0a-243">*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Mandanten [Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) überprüfen.*</span><span class="sxs-lookup"><span data-stu-id="4ea0a-243">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="4ea0a-244">Beispiel: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4ea0a-244">For example: test@sbc1.customers.adatum.biz</span></span>

![Aktivierung von der Seite Unterdomäne](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="4ea0a-246">Erstellen Sie einen Benutzer Trunk und bereitgestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="4ea0a-246">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="4ea0a-247">Basierend auf Feedback, die wir in der technischen Akzeptanzprogramm erhalten haben, kann den Vorgang des Erstellens Trunks in der Customer-Mandanten vereinfacht das Microsoft ändern.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-247">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="4ea0a-248">Sehen Sie sich den Dokumentationsupdates auf dieser Seite, und führen Sie die Microsoft technischen Communityblogs für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-248">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="4ea0a-249">Erstellen Sie einen Trunk in der Customer-Domäne mit dem Befehl New-CSonlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-249">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="4ea0a-250">Der Trunk FQDN **muss** übereinstimmen, die Unterdomäne für den Kunden erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-250">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="4ea0a-251">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4ea0a-251">For example:</span></span>

<span data-ttu-id="4ea0a-252">*Neue-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz - SipSignallingPort 5068*</span><span class="sxs-lookup"><span data-stu-id="4ea0a-252">*New-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068*</span></span>

<span data-ttu-id="4ea0a-253">Bereitstellung von Benutzern mit den Telefonnummern, und konfigurieren Sie VoIP-routing.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="4ea0a-254">Weitere Informationen zu den New-CSOnlinePSTNGateway finden Sie Einrichten von Benutzern und Konfigurieren von VoIP-routing, zum [Direkten Routing konfigurieren](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="4ea0a-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="4ea0a-255">Finden Sie in den [SBC Hersteller Anweisungen](#deploy-and-configure-the-sbc) zum Konfigurieren von den Vollqualifizierten Domänennamen Unterdomänen in der Kopfzeile Kontakt gesendet.</span><span class="sxs-lookup"><span data-stu-id="4ea0a-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

