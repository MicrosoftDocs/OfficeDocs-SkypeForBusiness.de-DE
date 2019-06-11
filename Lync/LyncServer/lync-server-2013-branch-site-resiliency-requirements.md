---
title: 'Lync Server 2013: Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff969638f8c46abdd0ebcc8d11821a6a31b3c76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="1d7d6-102">Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d7d6-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d7d6-103">_**Letztes Änderungsdatum des Themas:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="1d7d6-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="1d7d6-104">In diesem Thema finden Sie Informationen dazu, wie Sie Benutzer auf die Ausfallsicherheit von Zweigstellen und Voicemail vorbereiten sowie die entsprechenden Hardware-und Softwareanforderungen angeben.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="1d7d6-105">Vorbereiten von Verzweigungs Benutzern für die Stabilität des Zweig Standorts</span><span class="sxs-lookup"><span data-stu-id="1d7d6-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="1d7d6-106">Bereiten Sie die Benutzer auf die Ausfallsicherheit von Zweigstellen vor, indem Sie deren Registrierungspool als Survivable Branch Appliance (SBA) oder Survivable Branch Server festlegen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="1d7d6-107">Registrierungsstellen Zuweisungen für Verzweigungs Benutzer</span><span class="sxs-lookup"><span data-stu-id="1d7d6-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="1d7d6-108">Unabhängig davon, welche Lösung für eine Zweigstellen-Ausfallsicherheit Sie wählen, müssen Sie jedem Benutzer eine primäre Registrierungsstelle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="1d7d6-109">Benutzer von Verzweigungs Websites sollten sich immer bei der Registrierungsstelle an der Zweigstelle anmelden, und zwar unabhängig davon, ob sich die Registrierungsstelle in der Survivable Branch-Appliance, dem Überlebenden Branch-Server oder einem eigenständigen lync Server 2013 Standard-oder Enterprise Edition-Server befindet.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="1d7d6-110">Ein DNS-Service-Ressourceneintrag (Domain Name System) ist erforderlich, damit ein Client seinen Registrierungspool ermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="1d7d6-111">Wenn die Survivable Branch-Appliance nicht mehr zur Verfügung steht, finden die Zweigstellenclients automatisch die Sicherungs Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="1d7d6-112">Wenn eine Verzweigungs Website nicht über einen DNS-Server verfügt, gibt es zwei alternative Methoden zum Konfigurieren der Ermittlung der Survivable Branch-Appliance oder des Survivable Branch-Servers:</span><span class="sxs-lookup"><span data-stu-id="1d7d6-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="1d7d6-113">Konfigurieren Sie die DHCP-Option 120 auf dem DHCP-Server (Dynamic Host Configuration Protocol) der Zweigstelle so, dass Sie auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder des Survivable Branch-Servers verweist.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="1d7d6-114">Konfigurieren Sie die Survivable Branch-Appliance oder den Survivable Branch-Server, um auf DHCP 120-Abfragen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="1d7d6-115">VoIP-Routing für Branch-Benutzer</span><span class="sxs-lookup"><span data-stu-id="1d7d6-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="1d7d6-116">Wir empfehlen, dass Sie eine separate VoIP-Richtlinie auf Benutzerebene für Benutzer in einer Zweigstelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="1d7d6-117">Diese Richtlinie sollte eine primäre Route umfassen, die die Survivable Branch Appliance oder das Branch Server-Gateway verwendet, und mindestens eine Sicherungs Route, die einen trunk mit einem PSTN-Gateway (Public Switched Telephone Network) am zentralen Standort verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="1d7d6-118">Wenn die primäre Route nicht verfügbar ist, wird stattdessen die Sicherungs Route verwendet, die mindestens ein zentrales Standort Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="1d7d6-119">Auf diese Weise ist die VoIP-Richtlinie des Benutzers unabhängig davon, wo ein Benutzer registriert ist, auf der Zweigstellen-Registrierungsstelle oder dem sicherungsregistrierungspool am zentralen Standort immer gültig.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="1d7d6-120">Dies ist eine wichtige Überlegung für Failover-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="1d7d6-121">Wenn Sie beispielsweise die Survivable Branch-Appliance umbenennen oder die Survivable Branch-Appliance neu konfigurieren müssen, um eine Verbindung mit einem sicherungsregistrierungspool am zentralen Standort herzustellen, müssen Sie die Zweigstellenbenutzer für die Dauer an den zentralen Standort verschieben.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="1d7d6-122">(Einzelheiten zum Umbenennen oder Neukonfigurieren einer Survivable Branch-Appliance finden Sie in [Anhang B: Verwalten einer Survivable Branch-Appliance in lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in der Bereitstellungsdokumentation.) Wenn diese Benutzer keine VoIP-Richtlinien auf Benutzerebene oder Wählpläne auf Benutzerebene haben und die Benutzer auf eine andere Website umgestellt werden, gelten die VoIP-Richtlinien auf Websiteebene und die Wählpläne auf Websiteebene des zentralen Standorts standardmäßig für die Benutzer und nicht für die Websiteebene des Zweigstellen-VoIP Richtlinien und Wählpläne,.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="1d7d6-123">Wenn die VoIP-Richtlinien auf Websiteebene und die vom sicherungsregistrierungspool verwendeten Wählpläne auf Websiteebene auch für die Benutzer der Verzweigungs Website gelten können, treten in diesem Szenario keine Anrufe auf.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="1d7d6-124">Wenn beispielsweise Benutzer von einer Zweigstelle, die sich in Japan befindet, in einen zentralen Standort in Redmond verschoben werden, wird ein Wählplan mit Normalisierungsregeln, der + 1425 allen siebenstelligen anrufen vorangestellt wird, wahrscheinlich nicht geeignet sein, Anrufe für diese Benutzer angemessen zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1d7d6-125">Wenn Sie eine Zweigstellen-Backup-Route erstellen, empfehlen wir, dass Sie der Benutzerrichtlinie für Zweigniederlassungen zwei PSTN-Telefonnutzungsdatensätze hinzufügen und jedem eine separate Route zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="1d7d6-126">Die erste oder primäre Route würde Anrufe an das Gateway weiterleiten, das dem SBA (Survivor Branch Appliance) oder Branch Server zugeordnet ist. die zweite oder Sicherungs-Route würde Anrufe an das Gateway an der zentralen Website weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="1d7d6-127">Bei der Weiterleitung von Anrufen versucht der SBA-oder Branch-Server alle Routen, die dem ersten PSTN-Verwendungsdaten Satz zugeordnet sind, bevor Sie den zweiten Verwendungsdaten Satz versuchen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="1d7d6-128">So stellen Sie sicher, dass eingehende Anrufe an Zweigstellenbenutzer diese Benutzer erreichen, wenn das Branch-Gateway oder die Windows-Komponente der Survivable Branch Appliance-Website nicht verfügbar ist (Dies würde beispielsweise passieren, wenn die Survivable Branch Appliance oder Branch Gateway für die Wartung nicht zur Verfügung standen), erstellen Sie eine Failover-Route auf dem Gateway (oder arbeiten Sie mit Ihrem direkten nach innen Wähl-(DID-) Anbieter), um eingehende Anrufe an den sicherungsregistrierungspool am zentralen Standort umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="1d7d6-129">Von dort aus werden die Anrufe über die WAN-Verbindung an Zweigstellenbenutzer weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="1d7d6-130">Stellen Sie sicher, dass die Route Zahlen übersetzt, um Sie dem PSTN-Gateway oder den akzeptierten Telefonnummernformaten anderer trunk-Peers zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="1d7d6-131">Details zum Erstellen einer Failover-Route finden Sie unter [Konfigurieren einer Failover-Route in lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="1d7d6-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="1d7d6-132">Sie können auch Wählpläne auf Dienstebene für den trunk erstellen, der dem Gateway auf der Zweigstelle zugeordnet ist, um eingehende Anrufe zu normalisieren.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="1d7d6-133">Wenn Sie über zwei überlebensfähige Branch-Appliances an einer Zweigstelle verfügen, können Sie einen Wählplan auf Websiteebene für beide erstellen, es sei denn, es ist ein separater Service-Level-Plan erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d7d6-134">Zum berücksichtigen des Verbrauchs von Ressourcen für die zentrale Website durch alle Zweigstellenbenutzer, die auf die zentrale Website für Anwesenheit, Konferenz oder Failover angewiesen sind, empfehlen wir, dass Sie den jeweiligen Benutzer der Zweigstelle in Betracht ziehen, als ob der Benutzer bei der zentralen Website registriert wäre.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="1d7d6-135">Derzeit gibt es keine Beschränkungen für die Anzahl der Benutzer von Zweigstellen, einschließlich der Benutzer, die bei einer Survivable Branch-Appliance registriert sind.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="1d7d6-136">Wir empfehlen außerdem, einen Wählplan und eine VoIP-Richtlinie auf Benutzerebene zu erstellen und diese dann den Benutzern der Verzweigungs Website zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="1d7d6-137">Ausführliche Informationen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) und [Erstellen der VoIP-Routing Richtlinie für Verzweigungs Benutzer in lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="1d7d6-138">Durchwahlnummern für die Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="1d7d6-138">Routing Extension Numbers</span></span>

<span data-ttu-id="1d7d6-139">Stellen Sie beim Vorbereiten von Wählplänen und VoIP-Richtlinien für Benutzer von Zweigstellen sicher, dass Sie Normalisierungsregeln und Übersetzungsregeln einbeziehen, die mit den Zeichenfolgen und dem Zahlenformat übereinstimmen, die im Attribut msRTCSIP (oder Linien-URI)-Attribut verwendet werden, damit lync 2013-Anrufe zwischen Zweigstellen aktiviert sind. Websitebenutzer und zentrale Websitebenutzer werden ordnungsgemäß weitergeleitet, insbesondere dann, wenn Anrufe über das PSTN umgeleitet werden müssen, weil die WAN-Verbindung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="1d7d6-140">Darüber hinaus gibt es besondere Überlegungen für gewählte Nummern, die Durchwahlnummern enthalten, und nicht nur Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="1d7d6-141">Normalisierungsregeln und Übersetzungen, die mit Linien-URIs übereinstimmen, die eine Durchwahlnummer enthalten, ob ausschließlich oder zusätzlich zu einer vollständigen E. 164-Telefonnummer, haben zusätzliche Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-141">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements.</span></span> <span data-ttu-id="1d7d6-142">In diesem Abschnitt werden verschiedene Beispielszenarien zum Weiterleiten von Anrufen für Linien-URIs mit einer Durchwahlnummer beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-142">This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="1d7d6-143">Wenn Ihre Organisation nicht über direkte Durchwahlnummern (DID) für einzelne Benutzer verfügt und der Leitungs-URI jedes Benutzers *nur* mit einer Durchwahlnummer konfiguriert ist, können interne Benutzer eine andere Rufnummer anrufen, indem Sie nur eine Durchwahlnummer wählen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-143">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number.</span></span> <span data-ttu-id="1d7d6-144">Sie müssen jedoch Normalisierungsregeln konfigurieren, die für Anrufe von einem Zweigstellenbenutzer an einen zentralen Websitebenutzer gelten können, die den Durchwahlnummern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-144">However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="1d7d6-145">In einem Szenario, in dem die WAN-Verbindung zwischen einer Verzweigungs Website und einem zentralen Standort verfügbar ist, ist es für Anrufe von Zweigstellenbenutzern an zentrale Websitebenutzer nicht erforderlich, dass die übereinstimmende Normalisierungsregel die Nummer übersetzt, da der Anruf nicht über das PSTN weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-145">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN.</span></span> <span data-ttu-id="1d7d6-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1d7d6-146">For example:</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d7d6-147">Regelname</span><span class="sxs-lookup"><span data-stu-id="1d7d6-147">Rule name</span></span></th>
<th><span data-ttu-id="1d7d6-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d7d6-148">Description</span></span></th>
<th><span data-ttu-id="1d7d6-149">Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="1d7d6-149">Number pattern</span></span></th>
<th><span data-ttu-id="1d7d6-150">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="1d7d6-150">Translation</span></span></th>
<th><span data-ttu-id="1d7d6-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d7d6-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d7d6-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="1d7d6-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-153">Fünfstellige Zahlen werden nicht übersetzt</span><span class="sxs-lookup"><span data-stu-id="1d7d6-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-154">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="1d7d6-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-155">$1</span><span class="sxs-lookup"><span data-stu-id="1d7d6-155">$1</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-156">10001 wird nicht übersetzt</span><span class="sxs-lookup"><span data-stu-id="1d7d6-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1d7d6-157">Sie müssen auch Durchwahlnummern für bestimmte Szenarien berücksichtigen, beispielsweise, wenn die WAN-Verbindung zwischen einer Verzweigungs Website und einem zentralen Standort nicht verfügbar ist und ein Anruf von einer Zweigstelle über das PSTN weitergeleitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-157">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN.</span></span> <span data-ttu-id="1d7d6-158">Wenn ein Zweigstellenbenutzer bei einem WAN-Ausfall nur einen zentralen Websitebenutzer anruft, indem er die Durchwahl des zentralen Websitebenutzers anwählt, muss eine ausgehende Übersetzungsregel vorhanden sein, mit der die vollständige Telefonnummer des zentralen Websitebenutzers hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-158">During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number.</span></span> <span data-ttu-id="1d7d6-159">Wenn der Linien-URI des Benutzers die vollständige Telefonnummer Ihres Unternehmens und die eindeutige Durchwahlnummer des Benutzers anstelle einer vollständigen Telefonnummer enthält, die für den Benutzer eindeutig ist, müssen Sie über eine Regel für ausgehende Übersetzungen verfügen, die stattdessen die vollständige Telefonnummer Ihrer Organisation hinzufügt. .</span><span class="sxs-lookup"><span data-stu-id="1d7d6-159">If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead.</span></span> <span data-ttu-id="1d7d6-160">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1d7d6-160">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d7d6-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d7d6-161">Description</span></span></th>
<th><span data-ttu-id="1d7d6-162">Übereinstimmungsmuster</span><span class="sxs-lookup"><span data-stu-id="1d7d6-162">Matching pattern</span></span></th>
<th><span data-ttu-id="1d7d6-163">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="1d7d6-163">Translation</span></span></th>
<th><span data-ttu-id="1d7d6-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d7d6-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d7d6-165">Übersetzt fünfstellige Zahlen in die Telefonnummer und Durchwahl eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="1d7d6-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-166">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="1d7d6-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-167">+ 14255550123; EXT = $1</span><span class="sxs-lookup"><span data-stu-id="1d7d6-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-168">10001 wird in + 14255550123; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="1d7d6-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7d6-169">Übersetzt fünfstellige Zahlen in die Telefonnummer Ihrer Organisation und die Durchwahl des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-170">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="1d7d6-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-171">+ 14255550100 übersetzt.; ext = $1</span><span class="sxs-lookup"><span data-stu-id="1d7d6-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-172">10001 wird in + 14255550100 übersetzt.; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="1d7d6-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1d7d6-173">Wenn der trunk-Peer, der das Umleiten an das PSTN übernimmt, keine Durchwahlnummern unterstützt, muss in diesem Szenario auch die ausgehende Übersetzungsregel die Durchwahlnummer entfernen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-173">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number.</span></span> <span data-ttu-id="1d7d6-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1d7d6-174">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d7d6-175">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d7d6-175">Description</span></span></th>
<th><span data-ttu-id="1d7d6-176">Übereinstimmungsmuster</span><span class="sxs-lookup"><span data-stu-id="1d7d6-176">Matching pattern</span></span></th>
<th><span data-ttu-id="1d7d6-177">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="1d7d6-177">Translation</span></span></th>
<th><span data-ttu-id="1d7d6-178">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d7d6-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d7d6-179">Entfernt die Durchwahl von Telefonnummern mit Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="1d7d6-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-180">^\+(\d *); ext = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="1d7d6-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-181">+$1</span><span class="sxs-lookup"><span data-stu-id="1d7d6-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="1d7d6-182">+ 14255550123; ext = 10001 wird in + 14255550123 übersetzt</span><span class="sxs-lookup"><span data-stu-id="1d7d6-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1d7d6-183">Unabhängig davon, ob eine WAN-Verbindung verfügbar ist, wenn Ihre Organisation keine DID-Nummern für einzelne Benutzer konfiguriert hat und der Leitungs-URI für einen Benutzer die Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des Benutzers enthält, müssen Sie Ihre der Telefonnummern-URI der Organisation mit einer Nummer, die über das trunk-Peer-oder PSTN-Gateway auf der Zweigstelle erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-183">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site.</span></span> <span data-ttu-id="1d7d6-184">Darüber hinaus müssen Sie den Telefonnummern-URI Ihrer Organisation so konfigurieren, dass seine eigene eindeutige Durchwahl für die Weiterleitung von Anrufen an diese Nummer hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-184">You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="1d7d6-185">Informationen zu Anrufen von einem zentralen Websitebenutzer zu einem Zweigstellenbenutzer, wenn die WAN-Verbindung zwischen den Websites nicht verfügbar ist, finden Sie weiter unten in diesem Thema unter "Vorbereiten der Überlebensfähigkeit von Voicemail".</span><span class="sxs-lookup"><span data-stu-id="1d7d6-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="1d7d6-186">Details zu Wählplänen und Normalisierungsregeln, einschließlich anderer Beispielregeln, finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation und [Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md) in der Bereitstellung. Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="1d7d6-187">Details zu den Regeln für ausgehende Übersetzungen finden Sie unter [Übersetzungsregeln in lync Server 2013](lync-server-2013-translation-rules.md) in der Planning-Dokumentation und [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="1d7d6-188">Vorbereiten der Überlebensfähigkeit von Voicemail</span><span class="sxs-lookup"><span data-stu-id="1d7d6-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="1d7d6-189">Exchange Unified Messaging (um) wird normalerweise nur an einem zentralen Standort und nicht an Zweigstellen installiert.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="1d7d6-190">Ein Anrufer sollte in der Lage sein, eine Voicemail-Nachricht zu hinterlassen, auch wenn die WAN-Verbindung zwischen der Zweigstelle und dem zentralen Standort nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="1d7d6-191">Daher erfordert die Konfiguration des Linien-URIs für die Telefonnummer der automatischen Exchange UM-Telefonzentrale, die Voicemail für Zweigstellenbenutzer bereitstellt, besondere Überlegungen, zusätzlich zu den VoIP-Richtlinien, dem Wählplan und den Normalisierungsregeln, die für diese Voicemail gelten. Anzahl.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="1d7d6-192">Überlebensfähige Branch Appliances (SBAS) und überlebensfähige Verzweigungs Server sorgen für die Überlebensfähigkeit von Voicemail für Branch-Benutzer bei einem WAN-Ausfall.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="1d7d6-193">Wenn Sie eine Survivable Branch-Appliance oder einen Survivable Branch-Server verwenden und das WAN nicht mehr zur Verfügung steht, leitet der SBA-oder Survivable Branch-Server unbeantwortete Anrufe über das PSTN an Exchange um am zentralen Standort weiter.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="1d7d6-194">Mit einem SBA-oder Survivable-Branch-Server können Benutzer während eines WAN-Ausfalls auch Voicemail-Nachrichten über das PSTN abrufen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="1d7d6-195">Schließlich werden bei einem WAN-Ausfall die überlebensfähige Branch-Appliance oder der Survivable Branch-Server in Warteschlangen verpasste Benachrichtigungen gesetzt und dann auf den Exchange um-Server hochgeladen, wenn das WAN wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="1d7d6-196">Stellen Sie sicher, dass Sie einen Eintrag für den FQDN des zentralen Website Pools und einen Eintrag für den FQDN des Edge-Servers in der Hosts-Datei auf dem Überlebenden Verzweigungs Server hinzufügen, um sicherzustellen, dass das neurouting von Voicemail widerstandsfähig ist.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="1d7d6-197">Andernfalls kann die DNS-Auflösung ein Timeout aufweisen, wenn Sie nicht über einen DNS-Server auf der Zweigstelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="1d7d6-198">Wir empfehlen die folgenden Konfigurationen für die Überlebensfähigkeit von Voicemail für Branch Site-Benutzer:</span><span class="sxs-lookup"><span data-stu-id="1d7d6-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="1d7d6-199">Ein Microsoft Exchange-Administrator sollte die Exchange um-automatische Telefonzentrale (AA) so konfigurieren, dass nur Nachrichten akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="1d7d6-200">Mit dieser Konfiguration werden alle anderen generischen Funktionen, wie etwa die Übertragung an einen Benutzer oder die Übertragung an einen Operator, deaktiviert und die AA auf die Annahme von Nachrichten beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="1d7d6-201">Alternativ kann der Exchange-Administrator einen generischen AA oder AA-Benutzerdefiniert verwenden, um den Anruf an einen Operator weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="1d7d6-202">Der lync Server-Administrator sollte die AA-Telefonnummer übernehmen und diese Telefonnummer in den Einstellungen für die Voicemail-Umleitungseinstellungen für die überlebensfähige Branch-Appliance oder den Branch-Server als die Nummer der **automatischen Exchange UM-Telefonzentrale** verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="1d7d6-203">Der lync Server-Administrator sollte die Telefonnummer für den Exchange um-Teilnehmerzugriff erhalten und diese Nummer als **Teilnehmerzugriffs** Nummer in den Einstellungen für die Voicemail-Umleitung für die Survivable Branch Appliance oder den Survivable Branch-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="1d7d6-204">Der lync Server-Administrator sollte Exchange um so konfigurieren, dass allen Verzweigungs Benutzern, die während eines WAN-Ausfalls Zugriff auf Voicemail benötigen, nur ein Wählplan zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="1d7d6-205">Wenn die WAN-Verbindung nicht verfügbar ist, können Anrufe an Zweigstellenbenutzer an das Exchange Unified Messaging (um)-Voicemail-Postfach des Benutzers weitergeleitet werden, jedoch nur, wenn die auf den Anruf angewendete VoIP-Richtlinie eine eindeutige Voicemail-Telefonnummer angibt und keine Durchwahl enthält. Anzahl.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="1d7d6-206">Hardware-und Software Anforderungen für die Stabilität des Zweigstellen Standorts</span><span class="sxs-lookup"><span data-stu-id="1d7d6-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="1d7d6-207">Die Hardware-und Softwareanforderungen variieren je nach ihrer Resilienz-Lösung.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="1d7d6-208">Voraussetzungen für Survivable Branch Appliances</span><span class="sxs-lookup"><span data-stu-id="1d7d6-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="1d7d6-209">Die erforderliche Hardware und Software ist in der Survivable Branch-Appliance integriert.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="1d7d6-210">Wir empfehlen jedoch auch, dass jede Zweigstelle einen DHCP-Server bereitstellt, um Client-IP-Adressen abzurufen. Wenn die DHCP-Lease abläuft, gibt es andernfalls keine IP-Konnektivität für Clients.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="1d7d6-211">Wenn sich die Enterprise-DNS-Server nur an zentralen Standorten befinden, können Zweigstellenbenutzer während eines WAN-Ausfalls keine Verbindung mit Ihnen herstellen, und daher schlägt die lync Server-Ermittlung, die DNS-SRV (Service (SRV)-Ressourceneintrag verwendet, fehl.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="1d7d6-212">Damit Sie bei einem WAN-Ausfall ein schnelles erneutes Routing sicherstellen können, müssen DNS-Einträge auf der Zweigstelle zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="1d7d6-213">Aktivieren Sie die DNS-Zwischenspeicherung, wenn der Verzweigungs Router dies unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="1d7d6-214">Oder Sie können einen DNS-Server in der Verzweigung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="1d7d6-215">Hierbei kann es sich um einen eigenständigen Server oder eine Version der Survivable Branch-Appliance handeln, die DNS-Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="1d7d6-216">Weitere Informationen erhalten Sie von Ihrem Überlebenden Branch Appliance-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d7d6-217">Es ist nicht erforderlich, einen Domänencontroller an einer Zweigstelle zu haben.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="1d7d6-218">Die Survivable Branch-Appliance authentifiziert Clients mithilfe eines speziellen Zertifikats, das der Client als Antwort auf die Zertifikatanforderung des Clients sendet, wenn er sich anmeldet.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="1d7d6-219">Lync-Clients können den lync-Server mithilfe der DHCP-Option 120 (Option SIP-Registrierungsstelle) ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="1d7d6-220">Dies kann auf eine von zwei Arten konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="1d7d6-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="1d7d6-221">Konfigurieren Sie den DHCP-Server auf der Verzweigungs Website, um auf DHCP 120-Abfragen zu antworten, die den FQDN der Registrierungsstelle auf der Survivable Branch-Appliance oder dem Überlebenden Branch-Server zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="1d7d6-222">Aktivieren Sie lync Server DHCP.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="1d7d6-223">Wenn diese Option aktiviert ist, reagiert die lync Server-Registrierungsstelle auf DHCP-Option 120-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="1d7d6-224">Beachten Sie, dass die Registrierungsstelle nicht auf DHCP-Abfragen anders als DHCP-Optionen 120 reagiert.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="1d7d6-225">Darüber hinaus sollten für größere Zweigstellen, die über mehrere Subnetze verfügen, DHCP-Relay-Agents aktiviert werden, um DHCP-Option 120-Abfragen an den DHCP-Server (Konfiguration 1) oder an die Registrierungsstelle weiterzuleiten (Konfiguration 2).</span><span class="sxs-lookup"><span data-stu-id="1d7d6-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="1d7d6-226">Schließlich müssen die Benutzer der Zweigstelle für Enterprise-VoIP konfiguriert und mit einem geeigneten Unified Communications-Endpunkt bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="1d7d6-227">Voraussetzungen für Überlebende Zweigstellenserver</span><span class="sxs-lookup"><span data-stu-id="1d7d6-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="1d7d6-228">Die Anforderungen für überlebensfähige Zweigstellenserver sind identisch mit den Anforderungen für einen Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="1d7d6-229">Ausführliche Informationen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="1d7d6-230">Voraussetzungen für die vollständige Bereitstellung von lync Server Branch-Websites</span><span class="sxs-lookup"><span data-stu-id="1d7d6-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="1d7d6-231">Ausführliche Informationen finden Sie unter [Ermitteln der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1d7d6-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

