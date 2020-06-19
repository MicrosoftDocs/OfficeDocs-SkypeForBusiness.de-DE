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
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786028"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="289bd-103">Contoso-Fallstudie: Notrufe</span><span class="sxs-lookup"><span data-stu-id="289bd-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="289bd-104">Um die Verfügbarkeit von Notrufen und Terminologie für Notrufe in Notfällen, &mdash; Ort, Notfall Standort und registrierte Adresse zu verstehen, hat &mdash; contoso die Verwaltung von [Notrufen](what-are-emergency-locations-addresses-and-call-routing.md) und die [Planung und Konfiguration dynamischer Notrufe](configure-dynamic-emergency-calling.md)überprüft.</span><span class="sxs-lookup"><span data-stu-id="289bd-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="289bd-105">In Office 365 wird ein Nutzer des Anruf Plans automatisch für Notrufe aktiviert.</span><span class="sxs-lookup"><span data-stu-id="289bd-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="289bd-106">Aber nur Anruf Plan Benutzer in den Vereinigten Staaten können dynamische Speicherorte für die Weiterleitung von Notrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="289bd-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="289bd-107">Für das direkte Routing hat Contoso erfahren, dass für das Routing von Notrufen und möglicherweise für die Partner Konnektivität eine zusätzliche Konfiguration erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="289bd-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="289bd-108">Der Administrator muss die Verbindung mit einem Notverwaltungsdienste (Emergency Routing Service Provider, ERSP) (USA) konfigurieren oder den Session Border Controller (SBC) für eine Emergency Location Identification Number (Elin)-Anwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="289bd-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="289bd-109">Contoso hat Niederlassungen in den USA und außerhalb der Vereinigten Staaten:</span><span class="sxs-lookup"><span data-stu-id="289bd-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="289bd-110">In den Vereinigten Staaten können die Benutzer des Contoso-Anruf Plans dynamische Speicherorte für die Weiterleitung von Notrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="289bd-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="289bd-111">Außerhalb der USA verfügt Contoso über einige Websites, die Anrufpläne und einige Websites verwenden, die über direktes Routing mit dem Telefon System verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="289bd-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="289bd-112">Notfall Anruf-Anwendungsfälle</span><span class="sxs-lookup"><span data-stu-id="289bd-112">Emergency calling use cases</span></span>

<span data-ttu-id="289bd-113">Nach der Entscheidung, wie Contoso eine Verbindung mit dem Telefonsystem herstellen wird, erkannte Contoso die folgenden Anwendungsfälle für Notfälle:</span><span class="sxs-lookup"><span data-stu-id="289bd-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="289bd-114">Benutzer des Anruf Plans in den Vereinigten Staaten</span><span class="sxs-lookup"><span data-stu-id="289bd-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="289bd-115">Anruf Plan Benutzer außerhalb der Vereinigten Staaten</span><span class="sxs-lookup"><span data-stu-id="289bd-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="289bd-116">Benutzer, der über direktes Routing eine Verbindung mit dem Telefon System herstellt</span><span class="sxs-lookup"><span data-stu-id="289bd-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="289bd-117">Benutzer des Anruf Plans in den Vereinigten Staaten</span><span class="sxs-lookup"><span data-stu-id="289bd-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="289bd-118">Es gibt Anforderungen, wenn die Telefonnummer einem Notfall Standort zugeordnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="289bd-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="289bd-119">Um diese Anforderungen zu verstehen, hat Contoso [Überlegungen für Anrufpläne](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)überprüft.</span><span class="sxs-lookup"><span data-stu-id="289bd-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="289bd-120">Basierend auf diesen Anforderungen beschloss contoso, den Standort mit der Telefonnummer zu verknüpfen, wenn eine Nummer einem Benutzer in den USA zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="289bd-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="289bd-121">Anruf Plan Benutzer außerhalb der Vereinigten Staaten</span><span class="sxs-lookup"><span data-stu-id="289bd-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="289bd-122">Um zu verstehen, wann eine Telefonnummer einem Notfall Standort zugeordnet werden muss, hat Contoso [Überlegungen für Anrufpläne](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)überprüft.</span><span class="sxs-lookup"><span data-stu-id="289bd-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="289bd-123">Basierend auf den Anforderungen beschloss Contoso Folgendes:</span><span class="sxs-lookup"><span data-stu-id="289bd-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="289bd-124">Contoso ordnet den Standort mit der Telefonnummer zu, wenn einem Benutzer in Kanada eine Nummer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="289bd-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="289bd-125">Contoso weist einen Notfall Standort zu, wenn die Telefonnummer von Office 365 abgerufen wird oder wenn eine Nummer von einem anderen Dienstanbieter oder Netzbetreiber übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="289bd-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="289bd-126">Benutzer, der über direktes Routing eine Verbindung mit dem Telefon System herstellt</span><span class="sxs-lookup"><span data-stu-id="289bd-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="289bd-127">Zum Planen des Notfall Routings für diesen Anwendungsfall hat Contoso [Überlegungen zur direkten Weiterleitung](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)überprüft.</span><span class="sxs-lookup"><span data-stu-id="289bd-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="289bd-128">Da die Benutzer des direkten Routings keine Notrufe auf die gleiche Weise wie Anruf Plan Benutzer erhalten, musste Contoso entscheiden, wie Notrufe bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="289bd-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="289bd-129">Direktes Routing kann mit einem Notfall-Routingdienst Anbieter (ERSP) verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="289bd-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="289bd-130">Das direkte Routing kann auch einen SBC aufweisen, der eine Notfall Standort-Identifikationsnummer (Elin) enthält.</span><span class="sxs-lookup"><span data-stu-id="289bd-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="289bd-131">Überlegungen zu ERSP (Emergency Routing Service Provider)</span><span class="sxs-lookup"><span data-stu-id="289bd-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="289bd-132">Die Notverwaltungsdienste (Emergency Routing Service Providers, ERSPs) können Notrufe automatisch basierend auf dem Standort des Anrufers weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="289bd-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="289bd-133">Wenn ein Notfall-Routing-Service-Anbieter in eine direkte Routing-Bereitstellung integriert ist, werden Notrufe mit einem dynamisch erworbenen Standort automatisch an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weitergeleitet, der diesem Standort dient.</span><span class="sxs-lookup"><span data-stu-id="289bd-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="289bd-134">Notrufe ohne dynamisch erworbenen Standort werden zuerst angezeigt, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf mit dem entsprechenden Dispatch Center basierend auf dem aktualisierten Standort verbunden wird.</span><span class="sxs-lookup"><span data-stu-id="289bd-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="289bd-135">Elin-Überlegungen</span><span class="sxs-lookup"><span data-stu-id="289bd-135">ELIN considerations</span></span>

<span data-ttu-id="289bd-136">Wenn eine SBC Elin-Anwendung in eine Direct Routing-Bereitstellung integriert ist, müssen zusätzliche Konfigurationsschritte ausgeführt werden, um die Notfalladressen mit Telefonnummern zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="289bd-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="289bd-137">Contoso hat entschieden, Sitzungs Grenz Controller zu verwenden, die Elin-Anwendungen (Emergency Location Identification Number) enthalten.</span><span class="sxs-lookup"><span data-stu-id="289bd-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="289bd-138">Benachrichtigung über Sicherheits Desk</span><span class="sxs-lookup"><span data-stu-id="289bd-138">Security desk notification</span></span>

<span data-ttu-id="289bd-139">Die Möglichkeit, den Security Desk zu benachrichtigen, wenn ein Notruf getätigt wird, steht sowohl für Microsoft-Anrufpläne als auch für das direkte Routing des Telefonsystems zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="289bd-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="289bd-140">Contoso hat die Details in der Security Desk-Benachrichtigung überprüft, um festzustellen, ob dies in ihren Büros konfiguriert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="289bd-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="289bd-141">Contoso hat entschieden, die Benachrichtigung über das Sicherheits Desk zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="289bd-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="289bd-142">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="289bd-142">Configuration</span></span> 

<span data-ttu-id="289bd-143">Contoso befolgte die Schritte unter [Konfigurieren von dynamischen Notrufen](configure-dynamic-emergency-calling.md) an:</span><span class="sxs-lookup"><span data-stu-id="289bd-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="289bd-144">Notfalladressen zuweisen</span><span class="sxs-lookup"><span data-stu-id="289bd-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="289bd-145">Konfigurieren von Netzwerkeinstellungen</span><span class="sxs-lookup"><span data-stu-id="289bd-145">Configure network settings</span></span> 

- <span data-ttu-id="289bd-146">Konfigurieren des Standort Informationsdiensts</span><span class="sxs-lookup"><span data-stu-id="289bd-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="289bd-147">Konfigurieren von Notfall Richtlinien</span><span class="sxs-lookup"><span data-stu-id="289bd-147">Configure emergency policies</span></span> 

- <span data-ttu-id="289bd-148">Aktivieren von Benutzern und Websites</span><span class="sxs-lookup"><span data-stu-id="289bd-148">Enable users and sites</span></span> 

- <span data-ttu-id="289bd-149">Testen von Notrufen</span><span class="sxs-lookup"><span data-stu-id="289bd-149">Test emergency calling</span></span> 

<span data-ttu-id="289bd-150">Nach der Konfiguration des dynamischen Notrufs musste Contoso den Standort dem entsprechenden Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="289bd-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="289bd-151">Zum Hinzufügen, ändern oder Entfernen eines Notfall Standorts für Ihre Organisation folgte Contoso den Schritten unter [hinzufügen, ändern oder Entfernen eines Notfall Standorts für Ihre Organisation](add-change-remove-emergency-location-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="289bd-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="289bd-152">Zum Erstellen von Orten für Gebäude, Etagen und Büros folgte Contoso den Schritten unter [hinzufügen, ändern oder Entfernen eines Orts für einen Notfall Standort](add-change-remove-emergency-place-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="289bd-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="289bd-153">Um einen Notfall Standort zuzuweisen, befolgte Contoso die Schritte unter [zuweisen oder Ändern eines Notfall Standorts für einen Benutzer](assign-change-emergency-location-user.md).</span><span class="sxs-lookup"><span data-stu-id="289bd-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 