---
title: Teams Voice Contoso-Fallstudie
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786025"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="00bd7-103">Contoso-Fallstudie: Telefon System</span><span class="sxs-lookup"><span data-stu-id="00bd7-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="00bd7-104">Je nach geographischem Standort und anderen Faktoren hatte Contoso Offices mit den folgenden Telefonie-Lösungen:</span><span class="sxs-lookup"><span data-stu-id="00bd7-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="00bd7-105">Websitetyp A: Skype for Business Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="00bd7-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="00bd7-106">Website Typ B: herkömmliche Legacy-Telefoniesysteme</span><span class="sxs-lookup"><span data-stu-id="00bd7-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="00bd7-107">Websitetyp C: eine Kombination aus Skype for Business Enterprise-VoIP und herkömmlichem Legacy-Telefoniesystem</span><span class="sxs-lookup"><span data-stu-id="00bd7-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="00bd7-108">Um eine Microsoft Phone-Systemlösung für Ihre gesamte Organisation zu implementieren, musste Contoso &mdash; für jeden Websitetyp ermitteln, &mdash; welche der folgenden Optionen für das Telefonsystem verwendet werden soll, um eine Verbindung mit dem öffentlichen Telefonnetz (PSTN) herzustellen:</span><span class="sxs-lookup"><span data-stu-id="00bd7-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="00bd7-109">Telefon System mit Anrufplan</span><span class="sxs-lookup"><span data-stu-id="00bd7-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="00bd7-110">Telefon System mit eigenem PSTN-Netzbetreiber über direktes Routing</span><span class="sxs-lookup"><span data-stu-id="00bd7-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="00bd7-111">Kombination aus Telefonsystem mit Anrufplan und Telefonsystem mit eigenem PSTN-Netzbetreiber über direktes Routing</span><span class="sxs-lookup"><span data-stu-id="00bd7-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="00bd7-112">Um die richtige Lösung für Ihre Organisation zu ermitteln, verwendete Contoso [Microsoft-Telefonie-Lösungen](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) und die Ignite-2019-Session- [Anrufe in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="00bd7-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="00bd7-113">Websitetyp A: Skype for Business Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="00bd7-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="00bd7-114">Contoso Skype for Business Enterprise-VoIP wurde als Hub eingerichtet und sprach.</span><span class="sxs-lookup"><span data-stu-id="00bd7-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="00bd7-115">Es gab einen zentralen Standort, an dem das PSTN-Gateway in der Region verwaltet wurde, die die Verbindung mit dem PSTN für die Skype for Business Enterprise-VoIP-Benutzer in Land bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="00bd7-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="00bd7-116">Oft hatten diese Satellitenbüros keinen eigenen Internet-Ausstieg.</span><span class="sxs-lookup"><span data-stu-id="00bd7-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="00bd7-117">Die Nummern für diese Benutzer befanden sich im SIP-Stamm, der eine Verbindung mit einem vorhandenen SBC herstellt.</span><span class="sxs-lookup"><span data-stu-id="00bd7-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="00bd7-118">Um festzustellen, ob der bereits bereitgestellte SBC für Direct Routing und medienumgehung zertifiziert ist, hat Contoso die [Liste der für die direkte Weiterleitung zertifizierten Session Border Controller](direct-routing-border-controllers.md)überprüft.</span><span class="sxs-lookup"><span data-stu-id="00bd7-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="00bd7-119">Die Wählgewohnheiten des Benutzers waren die Wahl eines Benutzers im Legacy-Telefoniesystem mithilfe einer Durchwahl, auch wenn der Benutzer einen Skype for Business-Client für Peer-to-Peer-Audio zur Verfügung hat.</span><span class="sxs-lookup"><span data-stu-id="00bd7-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="00bd7-120">Contoso hat ihre Entscheidung auf die folgenden Fragen gestützt:</span><span class="sxs-lookup"><span data-stu-id="00bd7-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="00bd7-121">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-121">Q.</span></span> <span data-ttu-id="00bd7-122">Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen beibehalten werden?</span><span class="sxs-lookup"><span data-stu-id="00bd7-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="00bd7-123">Eine.</span><span class="sxs-lookup"><span data-stu-id="00bd7-123">A.</span></span> <span data-ttu-id="00bd7-124">Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-124">No</span></span> 

- <span data-ttu-id="00bd7-125">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-125">Q.</span></span> <span data-ttu-id="00bd7-126">Müssen wir mit PBX-Anlagen und anderen Telefonanlagen von Drittanbietern kooperieren?</span><span class="sxs-lookup"><span data-stu-id="00bd7-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="00bd7-127">Eine.</span><span class="sxs-lookup"><span data-stu-id="00bd7-127">A.</span></span> <span data-ttu-id="00bd7-128">Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-128">No</span></span> 

- <span data-ttu-id="00bd7-129">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-129">Q.</span></span> <span data-ttu-id="00bd7-130">Müssen wir unseren derzeitigen Drittanbieter behalten?</span><span class="sxs-lookup"><span data-stu-id="00bd7-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="00bd7-131">A. ja (regulierte Länder) und Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="00bd7-132">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-132">Q.</span></span> <span data-ttu-id="00bd7-133">Muss der ROI für SBCS bereitgestellt werden?</span><span class="sxs-lookup"><span data-stu-id="00bd7-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="00bd7-134">A. ja und Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-134">A. Yes and No</span></span>  

- <span data-ttu-id="00bd7-135">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-135">Q.</span></span> <span data-ttu-id="00bd7-136">Steht Microsoft PSTN-Anrufpläne in dieser Region zur Verfügung?</span><span class="sxs-lookup"><span data-stu-id="00bd7-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="00bd7-137">A. ja und Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-137">A. Yes and No</span></span> 

<span data-ttu-id="00bd7-138">Basierend auf den Antworten auf Ihre Fragen beschloss contoso, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="00bd7-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="00bd7-139">Verschieben Sie die Benutzer, die sich in einem Bereich befinden, in dem PSTN-Anrufpläne für das Telefon System mit Anrufplänen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="00bd7-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="00bd7-140">Verschieben Sie die Benutzer, die sich nicht in einem Bereich befinden, in dem PSTN-Anrufpläne verfügbar sind, Benutzer, die sich auf einer Website befinden, auf der der ROI auf dem SBCS noch nicht erfüllt ist, und Benutzer, die in einem Land gewohnt sind, das Telefonanlagen mit direktem Routing für Telefonsysteme besitzt.</span><span class="sxs-lookup"><span data-stu-id="00bd7-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="00bd7-141">Das folgende Diagramm zeigt die anfängliche Bereitstellung von Skype for Business Enterprise-VoIP und wie diese Bereitstellung sowohl in Microsoft-Anrufpläne als auch direktes Routing migriert wurde:</span><span class="sxs-lookup"><span data-stu-id="00bd7-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagramm, das vor und nach Zuständen angezeigt wird](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="00bd7-143">Website Typ B: herkömmliche Legacy-Telefoniesysteme</span><span class="sxs-lookup"><span data-stu-id="00bd7-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="00bd7-144">Contoso hatte viele Offices, in denen Legacy-Telefoniesysteme genutzt wurden.</span><span class="sxs-lookup"><span data-stu-id="00bd7-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="00bd7-145">Es gab eine Teilmenge der Benutzer, die eine e-1.64-Telefonnummer hatten, während andere nur eine Durchwahl hatten.</span><span class="sxs-lookup"><span data-stu-id="00bd7-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="00bd7-146">Diese Nummern befanden sich auf dem TDM-Stamm des PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="00bd7-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="00bd7-147">Die Intra-Site-Wählfunktion wurde durch Nutzung eines Website Codes vor der Erweiterung konfiguriert, um zu bestimmen, wohin der Anruf weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="00bd7-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="00bd7-148">Die Wählgewohnheiten der Benutzer waren die Durchwahl.</span><span class="sxs-lookup"><span data-stu-id="00bd7-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="00bd7-149">Contoso hat ihre Entscheidung auf die folgenden Fragen gestützt:</span><span class="sxs-lookup"><span data-stu-id="00bd7-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="00bd7-150">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-150">Q.</span></span> <span data-ttu-id="00bd7-151">Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen beibehalten werden?</span><span class="sxs-lookup"><span data-stu-id="00bd7-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="00bd7-152">Eine.</span><span class="sxs-lookup"><span data-stu-id="00bd7-152">A.</span></span> <span data-ttu-id="00bd7-153">Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-153">No</span></span> 

- <span data-ttu-id="00bd7-154">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-154">Q.</span></span> <span data-ttu-id="00bd7-155">Müssen wir mit PBX-Anlagen und anderen Telefonanlagen von Drittanbietern kooperieren?</span><span class="sxs-lookup"><span data-stu-id="00bd7-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="00bd7-156">A. ja</span><span class="sxs-lookup"><span data-stu-id="00bd7-156">A. Yes</span></span>

- <span data-ttu-id="00bd7-157">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-157">Q.</span></span> <span data-ttu-id="00bd7-158">Müssen wir unseren derzeitigen Drittanbieter behalten?</span><span class="sxs-lookup"><span data-stu-id="00bd7-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="00bd7-159">A. Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-159">A. No</span></span> 

- <span data-ttu-id="00bd7-160">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-160">Q.</span></span> <span data-ttu-id="00bd7-161">Steht der Anrufplan von Microsoft PSTN in unserer Region zur Verfügung?</span><span class="sxs-lookup"><span data-stu-id="00bd7-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="00bd7-162">A. ja und Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-162">A. Yes and No</span></span> 

<span data-ttu-id="00bd7-163">Basierend auf den Antworten auf Ihre Fragen beschloss contoso, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="00bd7-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="00bd7-164">Verschieben Sie die Benutzer, die sich in einem Bereich befinden, in dem PSTN-Anrufpläne für das Telefon System mit Anrufplänen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="00bd7-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="00bd7-165">Verschieben Sie die Benutzer, die sich nicht in einem Bereich befinden, in dem PSTN-Anrufpläne für das Telefon System mit direktem Routing verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="00bd7-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="00bd7-166">Verwalten Sie eine PSTN-Verbindung mit geschäftlichen kritischen analogen Geräten.</span><span class="sxs-lookup"><span data-stu-id="00bd7-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="00bd7-167">Die folgenden Diagramme zeigen die ursprüngliche Bereitstellung von Legacysystemen mit Remotestandorten und die Migration zu einer direkten Routing Bereitstellung mit lokaler Medienoptimierung:</span><span class="sxs-lookup"><span data-stu-id="00bd7-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="00bd7-168">**Ursprüngliche Legacy Bereitstellung**  
 ![ Diagramm, das vor und nach Zuständen angezeigt wird](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="00bd7-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="00bd7-169">**Bereitstellung mit direktem Routing**</span><span class="sxs-lookup"><span data-stu-id="00bd7-169">**Deployment with Direct Routing**</span></span>

![Diagramm, das vor und nach Zuständen angezeigt wird](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="00bd7-171">Website Typ C: Kombination von Skype for Business Enterprise-VoIP und herkömmlichem Legacy-Telefoniesystem</span><span class="sxs-lookup"><span data-stu-id="00bd7-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="00bd7-172">Die Nummern der Contoso-Skype for Business Enterprise-VoIP-Nutzer befinden sich auf dem SIP-Stamm im SBC vom Netzbetreiber.</span><span class="sxs-lookup"><span data-stu-id="00bd7-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="00bd7-173">Die Nummern für die herkömmlichen Telefoniesysteme befanden sich auf dem TDM-Stamm für das PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="00bd7-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="00bd7-174">Contoso hat ihre Entscheidung auf die folgenden Fragen gestützt:</span><span class="sxs-lookup"><span data-stu-id="00bd7-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="00bd7-175">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-175">Q.</span></span> <span data-ttu-id="00bd7-176">Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen beibehalten werden?</span><span class="sxs-lookup"><span data-stu-id="00bd7-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="00bd7-177">Eine.</span><span class="sxs-lookup"><span data-stu-id="00bd7-177">A.</span></span> <span data-ttu-id="00bd7-178">Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-178">No</span></span> 

- <span data-ttu-id="00bd7-179">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-179">Q.</span></span> <span data-ttu-id="00bd7-180">Müssen wir mit PBX-Anlagen und anderen Telefonanlagen von Drittanbietern kooperieren?</span><span class="sxs-lookup"><span data-stu-id="00bd7-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="00bd7-181">A. Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-181">A. No</span></span> 

- <span data-ttu-id="00bd7-182">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-182">Q.</span></span> <span data-ttu-id="00bd7-183">Müssen wir unseren derzeitigen Drittanbieter behalten?</span><span class="sxs-lookup"><span data-stu-id="00bd7-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="00bd7-184">A. Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-184">A. No</span></span> 

- <span data-ttu-id="00bd7-185">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-185">Q.</span></span> <span data-ttu-id="00bd7-186">Muss der ROI für SBCS bereitgestellt werden?</span><span class="sxs-lookup"><span data-stu-id="00bd7-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="00bd7-187">A. ja und Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-187">A. Yes and No</span></span>  

- <span data-ttu-id="00bd7-188">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-188">Q.</span></span> <span data-ttu-id="00bd7-189">Steht der PSTN-Anrufplan von Microsoft in dieser Region zur Verfügung?</span><span class="sxs-lookup"><span data-stu-id="00bd7-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="00bd7-190">A. Nein</span><span class="sxs-lookup"><span data-stu-id="00bd7-190">A. No</span></span> 

<span data-ttu-id="00bd7-191">Basierend auf den Antworten auf Ihre Fragen beschloss Contoso Folgendes:</span><span class="sxs-lookup"><span data-stu-id="00bd7-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="00bd7-192">Für die Legacy-Telefonie-Benutzer, die für die direkte Weiterleitung aktiviert werden, hat Contoso die Nummern aus dem TDM-Stamm an den SIP-Stamm für den SBC portiert, da der SBC für das direkte Routing zertifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="00bd7-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="00bd7-193">Um eine Teilmenge der Benutzer zu unterstützen, die in das Telefonsystem wechseln, und um die fortgesetzte Weiterleitung über das Legacy System zu ermöglichen, wurde das Legacy-Telefoniesystem als nächster Hop zum SBC eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="00bd7-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="00bd7-194">Darüber hinaus hat Contoso für die Verwendung von Teams für alle internen Anrufe Anleitungen bereitgestellt, um das Benutzerverhalten zu unterstützen und die Abhängigkeit von Wähleinstellungen für Inter-und Intra-Site-Erweiterungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="00bd7-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="00bd7-195">Die folgenden Diagramme zeigen die ursprüngliche Bereitstellung von Skype for Business Enterprise-VoIP und des Legacy-Telefonie-Systems sowie die Migration zu einer gemischten Bereitstellung mithilfe des direkten Routings:</span><span class="sxs-lookup"><span data-stu-id="00bd7-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="00bd7-196">**Ursprüngliche gemischte Bereitstellung** 
 ![ Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="00bd7-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="00bd7-197">**Gemischte Bereitstellung mit direktem Routing** 
 ![ Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="00bd7-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="00bd7-198">Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="00bd7-198">Calling Plans</span></span>

<span data-ttu-id="00bd7-199">Um die Konfigurationsanforderungen für Anrufpläne zu ermitteln, hat Contoso die [grundlegenden Bereitstellungsentscheidungen des Anruf Plans](calling-plan-landing-page.md#core-deployment-decisions)überprüft.</span><span class="sxs-lookup"><span data-stu-id="00bd7-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="00bd7-200">Es wurden die folgenden Entscheidungen getroffen:</span><span class="sxs-lookup"><span data-stu-id="00bd7-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="00bd7-201">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-201">Q.</span></span> <span data-ttu-id="00bd7-202">Benötigen meine Nutzer Auslandsanrufe?</span><span class="sxs-lookup"><span data-stu-id="00bd7-202">Do my users need international calling?</span></span><br> <span data-ttu-id="00bd7-203">A. ja</span><span class="sxs-lookup"><span data-stu-id="00bd7-203">A. Yes</span></span> 

- <span data-ttu-id="00bd7-204">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-204">Q.</span></span> <span data-ttu-id="00bd7-205">Haben meine Benutzer jeweils eine direkte nach innen Telefonnummer?</span><span class="sxs-lookup"><span data-stu-id="00bd7-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="00bd7-206">A. nicht heute.</span><span class="sxs-lookup"><span data-stu-id="00bd7-206">A. Not today.</span></span> <span data-ttu-id="00bd7-207">Alle aktivierten Benutzer erhalten eine did-Funktion.</span><span class="sxs-lookup"><span data-stu-id="00bd7-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="00bd7-208">F.</span><span class="sxs-lookup"><span data-stu-id="00bd7-208">Q.</span></span> <span data-ttu-id="00bd7-209">Soll die Rufnummernanzeige maskiert oder deaktiviert werden?</span><span class="sxs-lookup"><span data-stu-id="00bd7-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="00bd7-210">A. die Rufnummernanzeige für einen Benutzer wird mit der lokalen Nummer für Contoso maskiert.</span><span class="sxs-lookup"><span data-stu-id="00bd7-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="00bd7-211">Direktes Routing</span><span class="sxs-lookup"><span data-stu-id="00bd7-211">Direct Routing</span></span>

<span data-ttu-id="00bd7-212">Contoso hat Ignite besucht, um auf Office 365-Features, einschließlich verfügbarer Telefone und direktes Routing, auf dem Laufenden zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="00bd7-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="00bd7-213">Technische Leitung und Architekten verwendeten die Anleitungen, die während des Ignite 2019 zur Verfügung gestellt wurden, um deren Richtung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="00bd7-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="00bd7-214">Wichtige Sitzungen, die verwendet wurden:</span><span class="sxs-lookup"><span data-stu-id="00bd7-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="00bd7-215">Planen des Erfolgs mit Microsoft Teams Direct Routing</span><span class="sxs-lookup"><span data-stu-id="00bd7-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="00bd7-216">Updates für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="00bd7-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="00bd7-217">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="00bd7-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="00bd7-218">Websites für Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="00bd7-218">Calling Plans sites</span></span>

<span data-ttu-id="00bd7-219">Um Lizenzen zu erhalten und Benutzern Telefonnummern zuzuweisen, befolgte Contoso die Schritte unter [Einrichten von Anrufplänen](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="00bd7-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="00bd7-220">Aufgrund der Anzahl der Benutzer, denen Telefonnummern zugewiesen werden mussten, beschloss contoso, die Telefonnummern mithilfe von PowerShell zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="00bd7-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="00bd7-221">Informationen zum Zuweisen von Zahlen mithilfe von PowerShell &mdash; sowie zu anderen Einstellungen, die von Contoso verwendet werden, finden Sie in &mdash; der [Übersicht über Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="00bd7-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="00bd7-222">Direktes Routing von Websites</span><span class="sxs-lookup"><span data-stu-id="00bd7-222">Direct Routing sites</span></span>

<span data-ttu-id="00bd7-223">Um die lokale Telefonie-Infrastruktur von Contoso mit Microsoft Teams zu verbinden, befolgte der Contoso-Administrator die Schritte unter [Konfigurieren des direkten Routings](direct-routing-configure.md) und überprüfte das Video- [Direct-Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) , um Anleitungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="00bd7-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="00bd7-224">Contoso bezog sich auch auf die Dokumentation zur direkten Routing Bereitstellung durch den Certified SBC-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="00bd7-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="00bd7-225">Nachdem das direkte Routing zwischen dem SBC-und dem Microsoft Phone-System konfiguriert wurde, musste Contoso die Konfiguration testen.</span><span class="sxs-lookup"><span data-stu-id="00bd7-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="00bd7-226">Zu diesem Zweck haben Contoso-Administratoren den SIP-Tester-Client verwendet, der in der [Sitzung Updates für Direct Routing bei Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)besprochen wurde.</span><span class="sxs-lookup"><span data-stu-id="00bd7-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="00bd7-227">Das SIP-Tester-Clientskript und die Dokumentation wurden aus dem PowerShell-Skript heruntergeladen, um die Verbindungen des direkten Routing Sitzung-Grenz Controllers zu testen.</span><span class="sxs-lookup"><span data-stu-id="00bd7-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="00bd7-228">Lokale Medienoptimierung</span><span class="sxs-lookup"><span data-stu-id="00bd7-228">Local Media Optimization</span></span>

<span data-ttu-id="00bd7-229">Contoso erkannte die Möglichkeit, die lokale Medienoptimierung in den verschiedenen Regionen weltweit zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="00bd7-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="00bd7-230">Die unterstützten Szenarien für Contoso werden in der [lokalen Medienoptimierung für das direkte Routing](direct-routing-media-optimization.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00bd7-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="00bd7-231">Die Konfiguration der lokalen Medienoptimierung erfolgte durch die folgenden Anleitungen sowohl des SBC-Anbieters als auch von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="00bd7-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="00bd7-232">Zu den Konfigurationsschritten für die lokale Medienoptimierung gehören:</span><span class="sxs-lookup"><span data-stu-id="00bd7-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="00bd7-233">Konfigurieren der Benutzer-und SBC-Websites</span><span class="sxs-lookup"><span data-stu-id="00bd7-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="00bd7-234">Konfigurieren Sie den SBC gemäß der SBC-Lieferanten Spezifikation,</span><span class="sxs-lookup"><span data-stu-id="00bd7-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="00bd7-235">Hinzufügen externer vertrauenswürdiger IP-Adressen zu jeder Website, die für die lokale Medienoptimierung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="00bd7-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="00bd7-236">Definieren der Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="00bd7-236">Define the network topology</span></span> 

- <span data-ttu-id="00bd7-237">Definieren der virtuellen Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="00bd7-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="00bd7-238">Ermitteln des Modus: immer umgehen oder nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="00bd7-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="00bd7-239">Netzwerküberlegungen</span><span class="sxs-lookup"><span data-stu-id="00bd7-239">Networking considerations</span></span>

<span data-ttu-id="00bd7-240">Contoso hatte eine Reihe von Benutzern, die über einen längeren Zeitraum Remote arbeiten mussten, nachdem Sie für das Telefon System aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="00bd7-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="00bd7-241">Die Benutzer haben VPN für den Zugriff auf bestimmte Branchenanwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="00bd7-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="00bd7-242">Während Sie sich im VPN befanden, erfuhren die Benutzer des Telefonsystems eine Verschlechterung der Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="00bd7-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="00bd7-243">Um das Qualitätsproblem zu beheben, hat Contoso VPN-Split-Tunneling implementiert, wodurch der Office 365-Datenverkehr das Internet durchlaufen konnte, während die Verbindung zu den internen apps auf dem VPN verblieb.</span><span class="sxs-lookup"><span data-stu-id="00bd7-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="00bd7-244">Um VPN-Split-Tunneling zu implementieren, folgte Contoso den Anleitungen [für die Implementierung von VPN-Split-Tunneling für Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="00bd7-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





