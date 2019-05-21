---
title: Konfigurieren eines Session Border Controllers für mehrere Mandanten
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Hier erfahren Sie, wie Sie einen SBC (Session Border Controller) für die Bereitstellung mehrerer Mandanten konfigurieren.
ms.openlocfilehash: 5392359307d97e010f86d3bb71f2f7c3f3d1ffb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290469"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="1daad-103">Konfigurieren eines Session Border Controllers für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="1daad-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="1daad-104">Das direkte Routing unterstützt die Konfiguration eines SBC (Session Border Controller) für die Bereitstellung mehrerer Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1daad-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="1daad-105">Dieses Szenario wurde für Microsoft-Partner und/oder PSTN-Netzbetreiber entwickelt, die später in diesem Dokument als Carrier bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="1daad-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="1daad-106">Ein Netzbetreiber verkauft Telefondienste, die an Microsoft Teams an Ihre Kunden ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="1daad-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="1daad-107">Ein Netzbetreiber:</span><span class="sxs-lookup"><span data-stu-id="1daad-107">A carrier:</span></span>
- <span data-ttu-id="1daad-108">Bereitstellung und Verwaltung eines SBC in seinem Rechenzentrum (Kunden müssen keinen SBC implementieren, und Sie erhalten Telefonie-Services vom Netzbetreiber im Teams-Client).</span><span class="sxs-lookup"><span data-stu-id="1daad-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="1daad-109">Verbindet den SBC mit mehreren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1daad-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="1daad-110">Bietet Kunden PSTN-Dienste.</span><span class="sxs-lookup"><span data-stu-id="1daad-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="1daad-111">Verwaltet die Anrufqualität Ende bis Ende.</span><span class="sxs-lookup"><span data-stu-id="1daad-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="1daad-112">Gebühren separat für PSTN-Dienste.</span><span class="sxs-lookup"><span data-stu-id="1daad-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="1daad-113">Microsoft verwaltet keine Netzbetreiber.</span><span class="sxs-lookup"><span data-stu-id="1daad-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="1daad-114">Microsoft bietet eine Telefonanlage (Microsoft Phone System) und einen Teams-Client, bescheinigt Telefone und bescheinigt SBCS, die mit dem Microsoft-Telefonsystem verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1daad-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="1daad-115">Bevor Sie einen Netzbetreiber auswählen, stellen Sie bitte sicher, dass Ihre Wahl über einen zertifizierten SBC verfügt und die Sprachqualität bis zum Ende verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="1daad-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="1daad-116">Im folgenden finden Sie die Schritte zur technischen Implementierung zum Konfigurieren des Szenarios.</span><span class="sxs-lookup"><span data-stu-id="1daad-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="1daad-117">**Nur Netzbetreiber:**</span><span class="sxs-lookup"><span data-stu-id="1daad-117">**Carrier only:**</span></span>
1. <span data-ttu-id="1daad-118">Stellen Sie den SBC bereit, und konfigurieren Sie ihn für das Hosting-Szenario gemäß den [Anweisungen der Certified SBC-Anbieter](#deploy-and-configure-the-sbc).</span><span class="sxs-lookup"><span data-stu-id="1daad-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="1daad-119">Registrieren Sie einen Basisdomänen Namen im Carrier-Mandanten, und fordern Sie ein Platzhalterzertifikat an.</span><span class="sxs-lookup"><span data-stu-id="1daad-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="1daad-120">Registrieren Sie eine Unterdomäne für jeden Kunden, der Teil der Basisdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="1daad-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="1daad-121">**Netzbetreiber mit einem globalen Kunden Administrator:**</span><span class="sxs-lookup"><span data-stu-id="1daad-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="1daad-122">Fügen Sie den Namen der Unterdomäne dem Kundenmandanten hinzu.</span><span class="sxs-lookup"><span data-stu-id="1daad-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="1daad-123">Aktivieren Sie den Namen der Unterdomäne.</span><span class="sxs-lookup"><span data-stu-id="1daad-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="1daad-124">Konfigurieren Sie den trunk vom Netzbetreiber zum Kundenmandanten und Bereitstellen von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="1daad-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="1daad-125">*Stellen Sie bitte sicher, dass Sie die DNS-Grundlagen kennen und wissen, wie der Domänenname in Office 365 verwaltet wird. Überprüfen [Sie, wie Sie Hilfe zu Office 365-Domänen erhalten](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) , bevor Sie fortfahren.*</span><span class="sxs-lookup"><span data-stu-id="1daad-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="1daad-126">Bereitstellen und Konfigurieren des SBC</span><span class="sxs-lookup"><span data-stu-id="1daad-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="1daad-127">Die detaillierten Schritte zum Bereitstellen und Konfigurieren von SBCS für ein SBC-Hosting-Szenario finden Sie in der Dokumentation des SBC-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="1daad-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="1daad-128">**AudioCodes:** [Direct Routing-Konfigurationshinweise](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), die Konfiguration des SBC-Host Szenarios, das unter "Verbinden von AudioCodes SBC mit Microsoft Teams Direct Routing Hosting Model Configuration Note" beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1daad-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="1daad-129">**Band Kommunikation:**  Weitere Informationen finden Sie im [Menüband Communications SBC Core Microsoft Teams-Konfigurationshandbuch](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) für die Dokumentation zur Konfiguration der Menüband-Core-Serie SBCS und zu diesem Seiten [Menüband bewährte Methode – Konfigurieren von Netzbetreibern für Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="1daad-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="1daad-130">Bitte achten Sie darauf, wie Sie die Kopfzeile "Kontakt" konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1daad-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="1daad-131">Der Kontakt Kopf wird verwendet, um den Kundenmandanten in der eingehenden Einladungsnachricht zu finden.</span><span class="sxs-lookup"><span data-stu-id="1daad-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="1daad-132">Registrieren einer Basisdomäne und Unterdomänen</span><span class="sxs-lookup"><span data-stu-id="1daad-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="1daad-133">Für das Hosting-Szenario müssen Sie Folgendes erstellen:</span><span class="sxs-lookup"><span data-stu-id="1daad-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="1daad-134">Ein Basisdomänenname im Besitz des Netzbetreibers.</span><span class="sxs-lookup"><span data-stu-id="1daad-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="1daad-135">Eine Unterdomäne, die Teil des Basisdomänen namens in jedem Kundenmandanten ist.</span><span class="sxs-lookup"><span data-stu-id="1daad-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="1daad-136">Im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1daad-136">In the following example:</span></span>
- <span data-ttu-id="1daad-137">Adatum ist ein Carrier, der mehreren Kunden dient, indem es Internet-und Telefonie-Dienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1daad-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="1daad-138">Woodgrove Bank, Contoso und Adventure Works sind drei Kunden, die über Office 365-Domänen verfügen, aber die Telefonie-Services von Adatum erhalten.</span><span class="sxs-lookup"><span data-stu-id="1daad-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="1daad-139">Unterdomänen **müssen** mit dem FQDN-Namen des Trunks übereinstimmen, der für den Kunden konfiguriert wird, und dem FQDN in der Kontakt Kopfzeile, wenn Sie die Einladung zu Office 365 senden.</span><span class="sxs-lookup"><span data-stu-id="1daad-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="1daad-140">Wenn ein Anruf an der Office 365 Direct-Routing Schnittstelle eingeht, verwendet die Schnittstelle die Kontakt Kopfzeile, um den Mandanten zu finden, in dem der Benutzer nachgeschlagen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1daad-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="1daad-141">Bei der direkten Weiterleitung wird keine telefonnummernsuche auf der Einladung verwendet, da einige Kunden möglicherweise nicht-DID-Nummern haben, die sich in mehreren Mandanten überlappen können.</span><span class="sxs-lookup"><span data-stu-id="1daad-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="1daad-142">Daher ist der FQDN-Name in der Kopfzeile des Kontakts erforderlich, um den genauen Mandanten zu identifizieren, um den Benutzer anhand der Telefonnummer nachschlagen zu können.</span><span class="sxs-lookup"><span data-stu-id="1daad-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="1daad-143">*Weitere Informationen zum Erstellen von Domänennamen in Office 365-Mandanten finden Sie [unter Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="1daad-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="1daad-144">Das folgende Diagramm fasst die Anforderungen für Basisdomänen, Unterdomänen und Kontakt Kopfzeilen zusammen.</span><span class="sxs-lookup"><span data-stu-id="1daad-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![Anforderungen für die Basisdomäne, Unterdomänen und Kontakt Kopfzeile](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="1daad-146">Für den SBC ist ein Zertifikat erforderlich, um die Verbindungen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="1daad-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="1daad-147">Für das SBC-Hosting-Szenario muss der Netzbetreiber ein Zertifikat mit San \* \*. base_domain (beispielsweise \*Customers.adatum.biz)\* anfordern.</span><span class="sxs-lookup"><span data-stu-id="1daad-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="1daad-148">Dieses Zertifikat kann verwendet werden, um Verbindungen mit mehreren Mandanten zu authentifizieren, die über einen einzelnen SBC bedient werden.</span><span class="sxs-lookup"><span data-stu-id="1daad-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="1daad-149">Die folgende Tabelle zeigt ein Beispiel für eine Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="1daad-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="1daad-150">Neuer Domänenname</span><span class="sxs-lookup"><span data-stu-id="1daad-150">New domain name</span></span> |<span data-ttu-id="1daad-151">Typ</span><span class="sxs-lookup"><span data-stu-id="1daad-151">Type</span></span>|<span data-ttu-id="1daad-152">Registriert</span><span class="sxs-lookup"><span data-stu-id="1daad-152">Registered</span></span>  |<span data-ttu-id="1daad-153">Zertifikat-San für SBC</span><span class="sxs-lookup"><span data-stu-id="1daad-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="1daad-154">Standarddomäne des Mandanten im Beispiel</span><span class="sxs-lookup"><span data-stu-id="1daad-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="1daad-155">FQDN-Name, den SBC beim Senden von Anrufen an Benutzer in der Kontakt Kopfzeile vorlegen muss</span><span class="sxs-lookup"><span data-stu-id="1daad-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="1daad-156">Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-156">customers.adatum.biz</span></span>|    <span data-ttu-id="1daad-157">Basis</span><span class="sxs-lookup"><span data-stu-id="1daad-157">Base</span></span>     |     <span data-ttu-id="1daad-158">In Carrier-Mandant</span><span class="sxs-lookup"><span data-stu-id="1daad-158">In carrier tenant</span></span>  |    <span data-ttu-id="1daad-159">\*. Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="1daad-160">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-160">adatum.biz</span></span>      |<span data-ttu-id="1daad-161">Na, dies ist ein Dienst Mandant, keine Benutzer</span><span class="sxs-lookup"><span data-stu-id="1daad-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="1daad-162">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="1daad-163">Subdomain</span><span class="sxs-lookup"><span data-stu-id="1daad-163">Subdomain</span></span>  |    <span data-ttu-id="1daad-164">In einem Kundenmandanten</span><span class="sxs-lookup"><span data-stu-id="1daad-164">In a customer tenant</span></span>  |    <span data-ttu-id="1daad-165">\*. Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="1daad-166">woodgrovebank.US</span><span class="sxs-lookup"><span data-stu-id="1daad-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="1daad-167">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="1daad-168">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="1daad-169">Subdomain</span><span class="sxs-lookup"><span data-stu-id="1daad-169">Subdomain</span></span> | <span data-ttu-id="1daad-170">In einem Kundenmandanten</span><span class="sxs-lookup"><span data-stu-id="1daad-170">In a customer tenant</span></span>   |   <span data-ttu-id="1daad-171">\*. Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="1daad-172">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1daad-172">contoso.com</span></span>   |<span data-ttu-id="1daad-173">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="1daad-174">sbc3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="1daad-175">Subdomain</span><span class="sxs-lookup"><span data-stu-id="1daad-175">Subdomain</span></span> | <span data-ttu-id="1daad-176">In einem Kundenmandanten</span><span class="sxs-lookup"><span data-stu-id="1daad-176">In a customer tenant</span></span> |   <span data-ttu-id="1daad-177">\*. Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="1daad-178">AdventureWorks.com</span><span class="sxs-lookup"><span data-stu-id="1daad-178">adventureworks.com</span></span> | <span data-ttu-id="1daad-179">sbc3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="1daad-180">Führen Sie die nachstehenden Schritte aus, um die Basis-und Subdomänen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1daad-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="1daad-181">Im Beispiel konfigurieren wir einen Basisdomänen Namen (Customers.adatum.biz) und eine Unterdomäne für einen Kunden (sbc1.Customers.adatum.biz in Woodgrove Bank-Mandanten).</span><span class="sxs-lookup"><span data-stu-id="1daad-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="1daad-182">Registrieren eines Basisdomänen namens im Carrier-Mandanten</span><span class="sxs-lookup"><span data-stu-id="1daad-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="1daad-183">**Diese Aktionen werden beim Mandanten des Netzbetreibers ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="1daad-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="1daad-184">Stellen Sie sicher, dass Sie über die erforderlichen Rechte im Anbieter Mandanten verfügen</span><span class="sxs-lookup"><span data-stu-id="1daad-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="1daad-185">Wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben, können Sie nur neue Domänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1daad-185">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="1daad-186">Um die Rolle zu überprüfen, die Sie haben, melden Sie sich bitte beim Microsofthttps://portal.office.com)365 Admin Center \*\*\*\* > an (wechseln Sie zu**aktive**Benutzer von Benutzern, und überprüfen Sie, ob Sie über eine globale Administrator Rolle verfügen.</span><span class="sxs-lookup"><span data-stu-id="1daad-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="1daad-187">Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter Informationen zu [Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="1daad-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="1daad-188">Dem Mandanten eine Basisdomäne hinzufügen und diese überprüfen</span><span class="sxs-lookup"><span data-stu-id="1daad-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="1daad-189">Wechseln Sie im Microsoft 365 Admin Center zu **Setup** > **Domains** > **Domain hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1daad-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="1daad-190">Geben Sie im Feld Ihre **eigene Domäne eingeben** den FQDN der Basisdomäne ein.</span><span class="sxs-lookup"><span data-stu-id="1daad-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="1daad-191">Im folgenden Beispiel ist die Basisdomäne *Customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="1daad-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![Hinzufügen einer Basisdomäne](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="1daad-193">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1daad-193">Click **Next**.</span></span>
4. <span data-ttu-id="1daad-194">Im Beispiel hat der Mandant bereits adatum.biz als bestätigten Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="1daad-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="1daad-195">Der Assistent fragt keine zusätzliche Überprüfung ab, da Customers.adatum.biz eine Unterdomäne für den bereits registrierten Namen ist.</span><span class="sxs-lookup"><span data-stu-id="1daad-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="1daad-196">Wenn Sie jedoch einen FQDN hinzufügen, der noch nicht überprüft wurde, müssen Sie den Verifizierungsprozess durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="1daad-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="1daad-197">Der Verifizierungsprozess wird im [folgenden beschrieben](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span><span class="sxs-lookup"><span data-stu-id="1daad-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![Bestätigung eines bestätigten Domänennamens](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="1daad-199">Klicken Sie auf **weiter**, und wählen Sie auf der Seite **DNS-Einstellungen aktualisieren** die Option **Ich möchte die DNS-Einträge selbst hinzufügen** aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1daad-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="1daad-200">Deaktivieren Sie auf der nächsten Seite alle Werte (es sei denn, Sie möchten den Domänennamen für Exchange, SharePoint oder Teams/Skype for Business verwenden), klicken Sie auf **weiter**, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1daad-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="1daad-201">Stellen Sie sicher, dass sich Ihre neue Domäne im Status "Setup abgeschlossen" befindet.</span><span class="sxs-lookup"><span data-stu-id="1daad-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![Domänen mit dem Status "Setup abgeschlossen"](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="1daad-203">Aktivieren des Domänennamens</span><span class="sxs-lookup"><span data-stu-id="1daad-203">Activate the domain name</span></span>

<span data-ttu-id="1daad-204">Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen von E1, E3 oder E5 lizenzierten Benutzer hinzufügen und dem FQDN-Teil der SIP-Adresse, die der erstellten Basisdomäne entspricht, eine SIP-Adresse zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1daad-204">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="1daad-205">*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Mandanten finden Sie [unter Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="1daad-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="1daad-206">Beispiel: Test@Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-206">For example: test@customers.adatum.biz</span></span>

![Seite "Basisdomänen Aktivierung"](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="1daad-208">Registrieren eines Unterdomänen namens in einem Kundenmandanten</span><span class="sxs-lookup"><span data-stu-id="1daad-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="1daad-209">Sie müssen für jeden Kunden einen eindeutigen Subdomain-Namen erstellen.</span><span class="sxs-lookup"><span data-stu-id="1daad-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="1daad-210">In diesem Beispiel wird eine Subdomain-sbc1.Customers.adatum.biz in einem Mandanten mit dem standardmäßigen Domänennamen woodgrovebank.US erstellt.</span><span class="sxs-lookup"><span data-stu-id="1daad-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="1daad-211">**Alle nachstehenden Aktionen befinden sich im Kundenmandanten.**</span><span class="sxs-lookup"><span data-stu-id="1daad-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="1daad-212">Sicherstellen, dass Sie über die erforderlichen Rechte im Kundenmandanten verfügen</span><span class="sxs-lookup"><span data-stu-id="1daad-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="1daad-213">Wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben, können Sie nur neue Domänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1daad-213">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="1daad-214">Um die Rolle zu überprüfen, die Sie haben, melden Sie sich bitte beim Microsofthttps://portal.office.com)365 Admin Center \*\*\*\* > an (wechseln Sie zu**aktive**Benutzer von Benutzern, und überprüfen Sie, ob Sie über eine globale Administrator Rolle verfügen.</span><span class="sxs-lookup"><span data-stu-id="1daad-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="1daad-215">Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter Informationen zu [Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="1daad-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="1daad-216">Hinzufügen einer Unterdomäne zum Kundenmandanten und zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="1daad-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="1daad-217">Wechseln Sie im Microsoft 365 Admin Center zu **Setup** > **Domains** > **Domain hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1daad-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="1daad-218">Geben Sie im Feld Ihre **eigene Domäne eingeben** den FQDN der Unterdomäne für diesen Mandanten ein.</span><span class="sxs-lookup"><span data-stu-id="1daad-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="1daad-219">Im folgenden Beispiel ist die Unterdomäne sbc1.Customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="1daad-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![Hinzufügen einer Kunden-Unterdomäne](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="1daad-221">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1daad-221">Click **Next**.</span></span>
4. <span data-ttu-id="1daad-222">Der FQDN wurde nie im Mandanten registriert.</span><span class="sxs-lookup"><span data-stu-id="1daad-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="1daad-223">Im nächsten Schritt müssen Sie die Domäne überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1daad-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="1daad-224">Wählen Sie **stattdessen TXT-Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="1daad-224">Select **Add a TXT record instead**.</span></span> 

    ![Optionen auf der Seite "Domäne überprüfen"](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="1daad-226">Klicken Sie auf **weiter**, und notieren Sie sich den generierten txt-Wert, um den Domänennamen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1daad-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![Text Einträge auf der Seite "Domäne überprüfen"](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="1daad-228">Erstellen Sie den TXT-Eintrag mit dem Wert aus dem vorherigen Schritt im DNS-Hostinganbieter des Carriers.</span><span class="sxs-lookup"><span data-stu-id="1daad-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![Erstellen des txt-Eintrags im DNS-Hostinganbieter des Netzbetreibers](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="1daad-230">Weitere Informationen finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span><span class="sxs-lookup"><span data-stu-id="1daad-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="1daad-231">Wechseln Sie zurück zum Microsoft 365 Admin Center des Kunden, und klicken Sie auf **überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="1daad-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="1daad-232">Wählen Sie auf der nächsten Seite **die Option Ich füge die DNS-Einträge selbst hinzu** , und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1daad-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![Optionen auf der Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="1daad-234">Deaktivieren Sie auf der Seite **Onlinedienste auswählen** alle Optionen, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1daad-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![Seite "wählen Sie Ihre Onlinedienste aus"](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="1daad-236">Klicken Sie auf der Seite " **DNS-Einstellungen aktualisieren** " auf **Fertig stellen** .</span><span class="sxs-lookup"><span data-stu-id="1daad-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="1daad-238">Stellen Sie sicher, dass der Status **Setup abgeschlossen**ist.</span><span class="sxs-lookup"><span data-stu-id="1daad-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![Seite mit dem Status "Setup abgeschlossen"](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="1daad-240">Aktivieren des Unterdomänen namens</span><span class="sxs-lookup"><span data-stu-id="1daad-240">Activate the subdomain name</span></span>

<span data-ttu-id="1daad-241">Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, die der erstellten Unterdomäne im Kundenmandanten entspricht.</span><span class="sxs-lookup"><span data-stu-id="1daad-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="1daad-242">*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Mandanten finden Sie [unter Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="1daad-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="1daad-243">Beispiel: Test@sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="1daad-243">For example: test@sbc1.customers.adatum.biz</span></span>

![Aktivierung der Subdomain-Seite](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="1daad-245">Erstellen eines Trunks und Bereitstellen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="1daad-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="1daad-246">Basierend auf dem Feedback, das wir im technischen Adoptionsprogramm erhalten haben, kann Microsoft das Verfahren zum Erstellen von Trunks in den Kundenmandanten ändern, um den Prozess zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="1daad-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="1daad-247">Schauen Sie sich die Dokumentationsupdates auf dieser Seite an, und folgen Sie den Blogs der Microsoft Technical Community, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1daad-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="1daad-248">Erstellen Sie einen trunk in der Kundendomäne mit dem Befehl New-CSonlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="1daad-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="1daad-249">Der trunk-FQDN **muss** der für den Kunden erstellten Unterdomäne entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1daad-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="1daad-250">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1daad-250">For example:</span></span>

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

<span data-ttu-id="1daad-251">Beim Erstellen des Trunks wird möglicherweise die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1daad-251">When creating the trunk, you may receive the following error message:</span></span>

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

<span data-ttu-id="1daad-252">Bitte warten Sie, bis die Domänenregistrierung und-Aktivierung repliziert sind, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="1daad-252">Please allow some time for domain registration and activation to replicate and try again.</span></span>

<span data-ttu-id="1daad-253">Bereitstellen von Benutzern mit den Telefonnummern und Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="1daad-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="1daad-254">Weitere Informationen zu den neuen CSOnlinePSTNGateway und zur Bereitstellung von Benutzern sowie zum Konfigurieren des VoIP-Routings finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="1daad-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="1daad-255">Lesen Sie dazu die [Anweisungen des SBC-Herstellers](#deploy-and-configure-the-sbc) zum Konfigurieren des Sendens des FQDN-namens von Unterdomänen in der Kontakt Kopfzeile.</span><span class="sxs-lookup"><span data-stu-id="1daad-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

