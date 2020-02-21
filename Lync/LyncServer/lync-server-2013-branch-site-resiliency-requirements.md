---
title: 'Lync Server 2013: Anforderungen an die Ausfallsicherheit für Zweigstellenstandorte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1e8fb2cdbf2b9192411f74c5099930d8bd7d7a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="710b6-102">Anforderungen für Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="710b6-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="710b6-103">_**Letztes Änderungsstand des Themas:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="710b6-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="710b6-104">Dieses Thema unterstützt Sie bei der Vorbereitung von Benutzern im Hinblick auf die Ausfallsicherheit für Zweigstellenstandorte und für VoIP-Funktionen, und es werden die relevanten Hardware- und Softwareanforderungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="710b6-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="710b6-105">Vorbereiten von Zweigstellenbenutzern für die Ausfallsicherheit für Zweigstellenstandorte</span><span class="sxs-lookup"><span data-stu-id="710b6-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="710b6-106">Bereiten Sie Benutzer für die Ausfallsicherheit von Zweigstellenstandorten vor, indem Sie Ihren registrierungsstellenpool als Survivable Branch Appliance (SBA) oder Survivable Branch Server festlegen.</span><span class="sxs-lookup"><span data-stu-id="710b6-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="710b6-107">Registrierungszuweisungen für Zweigstellenbenutzer</span><span class="sxs-lookup"><span data-stu-id="710b6-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="710b6-108">Unabhängig davon, welche ausfallsicherheitslösung für Zweigstellenstandorte Sie auswählen, müssen Sie jedem Benutzer eine primäre Registrierungsstelle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="710b6-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="710b6-109">Zweigstellenbenutzer sollten sich immer am Zweigstellenstandort bei der Registrierungsstelle registrieren, unabhängig davon, ob sich diese Registrierungsstelle im Survivable Branch Appliance, Survivable Branch Server oder eigenständigen lync Server 2013 Standard oder Enterprise Edition-Server befindet.</span><span class="sxs-lookup"><span data-stu-id="710b6-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="710b6-110">Ein DNS-Dienst (Domain Name System)-Ressourceneintrag (SRV) ist erforderlich, damit ein Client seinen registrierungsstellenpool ermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="710b6-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="710b6-111">Wenn die Survivable Branch Appliance nicht mehr verfügbar ist, ermitteln Zweigstellenclients automatisch die Sicherungs Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="710b6-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="710b6-112">Wenn für einen Zweigstellenstandort kein DNS-Server vorhanden ist, gibt es zwei alternative Methoden zum Konfigurieren der Ermittlung der Survivable Branch Appliance oder Survivable Branch Server:</span><span class="sxs-lookup"><span data-stu-id="710b6-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="710b6-113">Konfigurieren Sie die DHCP-Option 120 auf dem DHCP-Server (Dynamic Host Configuration Protocol) der Zweigstelle so, dass Sie auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Survivable Branch Appliance oder Survivable Branch Server verweist.</span><span class="sxs-lookup"><span data-stu-id="710b6-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="710b6-114">Konfigurieren Sie die Survivable Branch Appliance oder Survivable Branch Server, um auf DHCP 120-Abfragen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="710b6-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="710b6-115">VoIP-Routing für Zweigstellenbenutzer</span><span class="sxs-lookup"><span data-stu-id="710b6-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="710b6-116">Es wird empfohlen, eine separate VoIP-Richtlinie auf Benutzerebene für Benutzer an einem Zweigstellenstandort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="710b6-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="710b6-117">Diese Richtlinie sollte eine primäre Route umfassen, die das Survivable Branch Appliance-oder Zweigstellenserver Gateway verwendet, sowie eine oder mehrere Sicherungs Routen, die einen trunk mit einem PSTN-Gateway (Public Switched Telephone Network) am zentralen Standort verwenden.</span><span class="sxs-lookup"><span data-stu-id="710b6-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="710b6-118">Wenn die primäre Route nicht verfügbar ist, wird stattdessen die Sicherungs Route verwendet, die ein oder mehrere zentrale Standort Gateways verwendet.</span><span class="sxs-lookup"><span data-stu-id="710b6-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="710b6-119">Auf diese Weise ist die VoIP-Richtlinie des Benutzers unabhängig davon, wo ein Benutzer registriert ist, auf der Zweigstellen Registrierungsstelle oder dem sicherungsregistrierungspool am zentralen Standort immer gültig.</span><span class="sxs-lookup"><span data-stu-id="710b6-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="710b6-120">Dies ist eine wichtige Überlegung bei Failover-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="710b6-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="710b6-121">Wenn Sie beispielsweise die Survivable Branch Appliance umbenennen oder die Survivable Branch Appliance neu konfigurieren müssen, um eine Verbindung mit einem sicherungsregistrierungspool am zentralen Standort herzustellen, müssen Sie die Zweigstellenbenutzer für die Dauer an den zentralen Standort verlagern.</span><span class="sxs-lookup"><span data-stu-id="710b6-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="710b6-122">(Ausführliche Informationen zum Umbenennen oder Neukonfigurieren eines Survivable Branch Appliance finden Sie in [Anhang B: Verwalten eines Survivable Branch Appliance in lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in der Bereitstellungsdokumentation.) Wenn diese Benutzer keine VoIP-Richtlinien auf Benutzerebene oder Wählpläne auf Benutzerebene haben und die Benutzer an einen anderen Standort verschoben werden, gelten die VoIP-Richtlinien auf Standortebene und die Wähleinstellungen auf Standortebene des zentralen Standorts standardmäßig für die Benutzer, statt auf Standortebene-VoIP-Richtlinien und Wähleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="710b6-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="710b6-123">Wenn die VoIP-Richtlinien auf Standortebene und die Wählpläne auf Standortebene, die vom sicherungsregistrierungspool verwendet werden, auch auf die Benutzer der Zweigstellenstandorte angewendet werden können, tritt in diesem Szenario ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="710b6-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="710b6-124">Wenn beispielsweise Benutzer von einem Zweigstellenstandort in Japan an einen zentralen Standort in Redmond verschoben werden, ist es unwahrscheinlich, dass ein Wählplan mit Normalisierungsregeln, der + 1425 allen 7-stelligen anrufen anbietet, Anrufe für diese Benutzer nicht ordnungsgemäß übersetzt.</span><span class="sxs-lookup"><span data-stu-id="710b6-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="710b6-125">Beim Erstellen einer Alternativroute für eine Zweigstelle empfiehlt es sich, der Zweigstellenbenutzerrichtlinie zwei PSTN-Verwendungsdatensätze hinzuzufügen und ihnen jeweils separate Routen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="710b6-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="710b6-126">Die erste oder primäre Route würde Anrufe an das Gateway weiterleiten, das dem Survivable Branch Appliance (SBA) oder dem Zweigstellenserver zugeordnet ist; die zweite oder gesicherte Route würde Anrufe an das Gateway am zentralen Standort weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="710b6-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="710b6-127">Beim Leiten von Anrufen probiert die SBA oder der Zweigstellenserver alle dem ersten PSTN-Verwendungsdatensatz zugewiesenen Routen aus, bevor der zweite Verwendungsdatensatz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="710b6-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="710b6-128">Um sicherzustellen, dass eingehende Anrufe an Zweigstellenbenutzer diese Benutzer erreichen, wenn das Zweigstellen Gateway oder die Windows-Komponente des Survivable Branch Appliance-Standorts nicht verfügbar ist (beispielsweise wenn der Survivable Branch Appliance oder die Verzweigung Gateway für die Wartung nicht zur Verfügung stand), erstellen Sie eine Failover-Route auf dem Gateway (oder arbeiten Sie mit Ihrem Direct Inward Dialing (DID)-Anbieter), um eingehende Anrufe an den sicherungsregistrierungspool am zentralen Standort umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="710b6-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="710b6-129">Von dort aus werden die Anrufe über die WAN-Verbindung an Zweigstellenbenutzer weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="710b6-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="710b6-130">Stellen Sie sicher, dass die Route Nummern so übersetzt, dass sie den zulässigen Telefonnummernformaten des PSTN-Gateways oder eines anderen Trunkpeers entspricht.</span><span class="sxs-lookup"><span data-stu-id="710b6-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="710b6-131">Ausführliche Informationen zum Erstellen einer Failover-Route finden Sie unter [Configuring a Failover Route in lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="710b6-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="710b6-132">Erstellen Sie außerdem Wählpläne auf Dienstebene für den Trunkt, der dem Gateway an der Zweigstelle zugeordnet ist, damit eingehende Anrufe normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="710b6-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="710b6-133">Wenn Sie zwei Survivable Branch Appliances an einem Zweigstellenstandort haben, können Sie einen Wählplan auf Standortebene für beide erstellen, es sei denn, es ist ein separater Service Level-Plan für jeden erforderlich.</span><span class="sxs-lookup"><span data-stu-id="710b6-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="710b6-134">Um den Verbrauch der Ressourcen eines zentralen Standorts durch Zweigstellenbenutzer zu ermitteln, die für Anwesenheits-, Konferenz- oder Failoverfunktionen vom zentralen Standort abhängen, sollten Sie jeden Zweigstellenbenutzer so betrachten, als wäre er für den zentralen Standort registriert.</span><span class="sxs-lookup"><span data-stu-id="710b6-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="710b6-135">Derzeit gibt es keine Beschränkungen für die Anzahl der Zweigstellenbenutzer, einschließlich der Benutzer, die mit einem Survivable Branch Appliance registriert sind.</span><span class="sxs-lookup"><span data-stu-id="710b6-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="710b6-136">Es empfiehlt sich außerdem, einen Wählplan und eine VoIP-Richtlinie auf Benutzerebene zu erstellen und diese dann den Zweigstellenbenutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="710b6-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="710b6-137">Ausführliche Informationen finden Sie unter [Erstellen von Wähleinstellungen in lync Server 2013](lync-server-2013-create-a-dial-plan.md) und [Erstellen der VoIP-Routing Richtlinie für Zweigstellenbenutzer in lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="710b6-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="710b6-138">Weiterleiten von Durchwahlnummern</span><span class="sxs-lookup"><span data-stu-id="710b6-138">Routing Extension Numbers</span></span>

<span data-ttu-id="710b6-139">Bei der Vorbereitung von Wähleinstellungen und VoIP-Richtlinien für Zweigstellenbenutzer müssen Sie die Normalisierungsregeln und Übersetzungsregeln einbeziehen, die mit den Zeichenfolgen und dem Zahlenformat übereinstimmen, die im msRTCSIP-Linien Attribut (oder dem Linien-URI) verwendet werden, sodass lync 2013 Anrufe zwischen Verzweigung aktiviert sind. Websitebenutzer und Benutzer des zentralen Standorts werden ordnungsgemäß weitergeleitet, insbesondere dann, wenn Anrufe über das PSTN umgeleitet werden müssen, da die WAN-Verbindung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="710b6-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="710b6-140">Weitere besondere Überlegungen betreffen gewählte Nummern, die nur Durchwahlnummern und keine Telefonnummern enthalten.</span><span class="sxs-lookup"><span data-stu-id="710b6-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="710b6-p108">Besondere Voraussetzungen gelten für Normalisierungs- und Übersetzungsregeln, die Anschluss-URIs entsprechen, die eine Durchwahlnummer enthalten – sei es ausschließlich oder zusätzlich zu einer vollständigen E.164-Telefonnummer. In diesem Abschnitt werden einige Beispielszenarien zur Weiterleitung von Anrufen für Anschluss-URIs mit einer Durchwahlnummer beschrieben.</span><span class="sxs-lookup"><span data-stu-id="710b6-p108">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements. This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="710b6-p109">Wenn in Ihrer Organisation keine DID-Telefonnummern (Direct Inward Dial) für die einzelnen Benutzer konfiguriert sind und der Anschluss-URI für jeden Benutzer *nur* mit einer Durchwahlnummer konfiguriert ist, können interne Benutzer sich gegenseitig anrufen, indem Sie einfach nur eine Durchwahlnummer wählen. Allerdings müssen Sie Normalisierungsregeln konfigurieren, die für Anrufe eines Zweigstellenbenutzers an einen Benutzer am zentralen Standort gelten können, die mit den Durchwahlnummern übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="710b6-p109">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number. However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="710b6-p110">In einem Szenario, in dem die WAN-Verbindung zwischen einer Zweigstelle und einem zentralen Standort verfügbar ist, muss für Anrufe von Zweigstellenbenutzern an Benutzer am zentralen Standort nicht die Nummer durch eine entsprechende Normalisierungsregel übersetzt werden, da der Anruf nicht über das PSTN weitergeleitet wird. Ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="710b6-p110">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN. For example:</span></span>


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
<th><span data-ttu-id="710b6-147">Regelname</span><span class="sxs-lookup"><span data-stu-id="710b6-147">Rule name</span></span></th>
<th><span data-ttu-id="710b6-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="710b6-148">Description</span></span></th>
<th><span data-ttu-id="710b6-149">Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="710b6-149">Number pattern</span></span></th>
<th><span data-ttu-id="710b6-150">Translation</span><span class="sxs-lookup"><span data-stu-id="710b6-150">Translation</span></span></th>
<th><span data-ttu-id="710b6-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="710b6-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="710b6-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="710b6-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="710b6-153">Fünfstellige Nummern werden nicht übersetzt</span><span class="sxs-lookup"><span data-stu-id="710b6-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="710b6-154">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="710b6-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="710b6-155">$1</span><span class="sxs-lookup"><span data-stu-id="710b6-155">$1</span></span></p></td>
<td><p><span data-ttu-id="710b6-156">10001 wird nicht übersetzt</span><span class="sxs-lookup"><span data-stu-id="710b6-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="710b6-p111">Sie müssen auch Durchwahlnummern für besondere Szenarien mit einbeziehen, bei denen z. B. die WAN-Verbindung zwischen einer Zweigstelle und dem zentralen Standort nicht verfügbar ist und ein Anruf von einer Zweigstelle über das Festnetz weitergeleitet werden muss. Während eines WAN-Ausfalls wird, wenn ein Zweigstellenbenutzer einen Benutzer am zentralen Standort anruft, indem er nur dessen Durchwahlnummer wählt, eine ausgehende Übersetzungsregel benötigt, die die vollständige Telefonnummer des Benutzers am zentralen Standort hinzufügt. Wenn der Anschluss-URI die vollständige Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des Benutzers anstelle einer vollständigen eindeutigen Telefonnummer für den Benutzer enthält, benötigen Sie eine ausgehende Übersetzungsregel, die stattdessen die vollständige Telefonnummer Ihrer Organisation hinzufügt. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="710b6-p111">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN. During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number. If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="710b6-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="710b6-161">Description</span></span></th>
<th><span data-ttu-id="710b6-162">Vergleichsmuster</span><span class="sxs-lookup"><span data-stu-id="710b6-162">Matching pattern</span></span></th>
<th><span data-ttu-id="710b6-163">Translation</span><span class="sxs-lookup"><span data-stu-id="710b6-163">Translation</span></span></th>
<th><span data-ttu-id="710b6-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="710b6-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="710b6-165">Übersetzt fünfstellige Nummern in die Telefon- und Durchwahlnummer eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="710b6-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="710b6-166">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="710b6-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="710b6-167">+ 14255550123; EXT = $1</span><span class="sxs-lookup"><span data-stu-id="710b6-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="710b6-168">10001 wird in +14255550123;ext=10001 übersetzt</span><span class="sxs-lookup"><span data-stu-id="710b6-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="710b6-169">Übersetzt fünfstellige Nummern in die Telefonnummer Ihrer Organisation und die Durchwahlnummer eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="710b6-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="710b6-170">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="710b6-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="710b6-171">+ 14255550100 übersetzt; EXT = $1</span><span class="sxs-lookup"><span data-stu-id="710b6-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="710b6-172">10001 wird in +14255550100;ext=10001 übersetzt</span><span class="sxs-lookup"><span data-stu-id="710b6-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="710b6-p112">In diesem Szenario muss die ausgehende Übersetzungsregel, wenn der Trunkpeer, der die Rückumleitung an das Festnetz abwickelt, keine Durchwahlnummern unterstützt, auch die Durchwahlnummer entfernen. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="710b6-p112">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="710b6-175">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="710b6-175">Description</span></span></th>
<th><span data-ttu-id="710b6-176">Vergleichsmuster</span><span class="sxs-lookup"><span data-stu-id="710b6-176">Matching pattern</span></span></th>
<th><span data-ttu-id="710b6-177">Translation</span><span class="sxs-lookup"><span data-stu-id="710b6-177">Translation</span></span></th>
<th><span data-ttu-id="710b6-178">Beispiel</span><span class="sxs-lookup"><span data-stu-id="710b6-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="710b6-179">Entfernt die Durchwahl von Telefonnummern mit Durchwahlnummern</span><span class="sxs-lookup"><span data-stu-id="710b6-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="710b6-180">^\+(\d *); ext = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="710b6-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="710b6-181">+ $1</span><span class="sxs-lookup"><span data-stu-id="710b6-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="710b6-182">+14255550123;ext=10001 wird in +14255550123 übersetzt</span><span class="sxs-lookup"><span data-stu-id="710b6-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="710b6-p113">Unabhängig davon, ob eine WAN-Verbindung verfügbar ist, gilt Folgendes: Wenn in Ihrer Organisation keine DID-Nummern für einzelne Benutzer konfiguriert sind und der Anschluss-URI für einen Benutzer die Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des jeweiligen Benutzers enthält, müssen Sie den Anschluss-URI der Telefonnummer Ihrer Organisation mit einer Nummer konfigurieren, die vom Trunkpeer oder vom PSTN-Gateway am Zweigstellenstandort erreicht werden kann. Außerdem müssen Sie den Anschluss-URI der Telefonnummer Ihrer Organisation so konfigurieren, dass er eine eigene, eindeutige Durchwahlnummer für die Weiterleitung von Anrufen zu dieser Nummer enthält.</span><span class="sxs-lookup"><span data-stu-id="710b6-p113">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site. You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="710b6-185">Einzelheiten zu Anrufen von einem Benutzer am zentralen Standort zu einem Zweigstellenbenutzer bei nicht verfügbarer WAN-Verbindung zwischen den Standorten finden Sie im Abschnitt "Vorbereiten der Ausfallsicherheit für VoIP-Funktionen" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="710b6-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="710b6-186">Ausführliche Informationen zu Wählplänen und Normalisierungsregeln, einschließlich anderer Beispielregeln, finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation und [Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="710b6-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="710b6-187">Ausführliche Informationen zu Regeln für ausgehende Übersetzungen finden Sie unter [Übersetzungsregeln in lync Server 2013](lync-server-2013-translation-rules.md) in der Planungsdokumentation und [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="710b6-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="710b6-188">Vorbereiten der Ausfallsicherheit für VoIP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="710b6-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="710b6-189">Exchange Unified Messaging (um) wird normalerweise nur an einem zentralen Standort und nicht an Zweigstellenstandorten installiert.</span><span class="sxs-lookup"><span data-stu-id="710b6-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="710b6-190">Ein Anrufer sollte auch dann eine Voicemailnachricht hinterlassen können, wenn die WAN-Verbindung zwischen Zweigstelle und zentralem Standort nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="710b6-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="710b6-191">Daher erfordert das Konfigurieren des Leitungs-URI für die Exchange um Telefonnummer für die automatische Telefonzentrale, die Voicemail für Zweigstellenbenutzer bereitstellt, zusätzlich zu den für diese Voicemail geltenden VoIP-Richtlinien, Wähleinstellungen und Normalisierungsregeln besondere Überlegungen. Anzahl.</span><span class="sxs-lookup"><span data-stu-id="710b6-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="710b6-192">Survivable Branch Appliances (SBAS) und Survivable Branch Server bieten Filial Benutzern während eines WAN-Ausfalls eine Überlebensfähigkeit von Voicemail.</span><span class="sxs-lookup"><span data-stu-id="710b6-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="710b6-193">Wenn Sie beispielsweise eine Survivable Branch Appliance oder Survivable Branch Server verwenden und das WAN nicht mehr verfügbar ist, leitet das SBA oder Survivable Branch Server unbeantwortete Anrufe über das PSTN an Exchange um am zentralen Standort weiter.</span><span class="sxs-lookup"><span data-stu-id="710b6-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="710b6-194">Mit einem SBA oder Survivable Branch Server können Benutzer während eines WAN-Ausfalls auch Voicemail-Nachrichten über das PSTN abrufen.</span><span class="sxs-lookup"><span data-stu-id="710b6-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="710b6-195">Schließlich werden bei einem WAN-Ausfall die Survivable Branch Appliance oder Survivable Branch Server in Warteschlangen verpasste Benachrichtigungen gesendet und dann auf den Exchange um Server hochzuladen, wenn das WAN wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="710b6-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="710b6-196">Um sicherzustellen, dass das Voicemail-neurouting widerstandsfähig ist, müssen Sie einen Eintrag für den FQDN des zentralen Website Pools und einen Eintrag für den Edgeserver FQDN der Hosts-Datei auf dem Survivable Branch Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="710b6-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="710b6-197">Andernfalls kann es bei der DNS-Auflösung zu einem Timeout kommen, wenn an der Zweigstelle kein DNS-Server vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="710b6-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="710b6-198">Für die Bereitstellung ausfallsicherer VoIP-Funktionen für Zweigstellenbenutzer werden die folgenden Konfigurationen empfohlen:</span><span class="sxs-lookup"><span data-stu-id="710b6-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="710b6-199">Ein Microsoft Exchange Administrator sollte Exchange um automatische Telefonzentrale (AA) so konfigurieren, dass nur Nachrichten akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="710b6-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="710b6-200">Durch diese Konfiguration wird jede andere allgemeine Funktionalität deaktiviert, beispielsweise das Durchstellen an einen Benutzer oder an einen Agent, und beschränkt die automatische Telefonzentrale auf die Annahme von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="710b6-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="710b6-201">Alternativ dazu kann der Exchange-Administrator auch eine allgemeine automatische Telefonzentrale oder eine benutzerdefinierte automatische Telefonzentrale zum Routen des Anrufs an einen Agent verwenden.</span><span class="sxs-lookup"><span data-stu-id="710b6-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="710b6-202">Der lync Server Administrator sollte die AA-Telefonnummer übernehmen und diese Telefonnummer als **automatische Telefonzentrale für die Exchange um** -Telefonzentrale in den Einstellungen für die Voicemail-Umleitung für den Survivable Branch Appliance-oder Zweigstellen Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="710b6-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="710b6-203">Der lync Server Administrator sollte die Telefonnummer des Exchange um Teilnehmerzugriffs erhalten und diese Nummer als **Teilnehmerzugriffs** Nummer in den Einstellungen für die Voicemail-Umleitung für die Survivable Branch Appliance oder Survivable Branch Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="710b6-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="710b6-204">Der lync Server Administrator sollte Exchange um so konfigurieren, dass nur ein Wählplan allen Zweigstellenbenutzern zugeordnet ist, die während eines WAN-Ausfalls auf Voicemail zugreifen müssen.</span><span class="sxs-lookup"><span data-stu-id="710b6-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="710b6-205">Wenn die WAN-Verbindung nicht verfügbar ist, können Anrufe an Zweigstellenbenutzer an den Exchange Unified Messaging (UM)-Sprachposteingang des Benutzers umgeleitet werden, jedoch nur, wenn die auf den Anruf angewendete VoIP-Richtlinie eine Voicemailtelefonnummer angibt, die eindeutig ist und keine Durchwahlnummer enthält.</span><span class="sxs-lookup"><span data-stu-id="710b6-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="710b6-206">Hardware- und Softwareanforderungen für die Ausfallsicherheit am Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="710b6-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="710b6-207">Die Hardware- und Softwareanforderungen variieren je nach Ausfallsicherheitslösung.</span><span class="sxs-lookup"><span data-stu-id="710b6-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="710b6-208">Anforderungen für Survivable Branch Appliances</span><span class="sxs-lookup"><span data-stu-id="710b6-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="710b6-209">Die erforderliche Hardware und Software ist in den Survivable Branch Appliance integriert.</span><span class="sxs-lookup"><span data-stu-id="710b6-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="710b6-210">Es wird jedoch auch empfohlen, dass jeder Zweigstellenstandort einen DHCP-Server bereitstellt, um Client-IP-Adressen zu erhalten. Andernfalls kann es sein, dass Clients keine IP-Konnektivität haben, wenn die DHCP-Lease abläuft.</span><span class="sxs-lookup"><span data-stu-id="710b6-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="710b6-211">Wenn sich die Enterprise-DNS-Server nur an zentralen Standorten befinden, können Zweigstellenbenutzer während eines WAN-Ausfalls keine Verbindung mit diesen herstellen, und daher schlägt lync Server Erkennung, die DNS-SRV (Service (SRV)-Ressourceneintrag verwendet) fehl.</span><span class="sxs-lookup"><span data-stu-id="710b6-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="710b6-212">Damit eine sofortige Umleitung während eines WAN-Ausfalls gewährleistet ist, müssen DNS-Einträge am Zweigstellenstandort zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="710b6-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="710b6-213">Wenn der Zweigstellenrouter die DNS-Zwischenspeicherung unterstützt, aktivieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="710b6-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="710b6-214">Sie können auch einen DNS-Server in der Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="710b6-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="710b6-215">Hierbei kann es sich um einen eigenständigen Server oder eine Version der Survivable Branch Appliance handeln, die DNS-Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="710b6-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="710b6-216">Weitere Informationen erhalten Sie von Ihrem Survivable Branch Appliance Anbieter.</span><span class="sxs-lookup"><span data-stu-id="710b6-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="710b6-217">Es ist nicht erforderlich, an jedem Zweigstellenstandort einen Domänencontroller zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="710b6-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="710b6-218">Das Survivable Branch Appliance authentifiziert Clients mithilfe eines speziellen Zertifikats, das den Client als Antwort auf die Zertifikatanforderung des Clients sendet, wenn er sich anmeldet.</span><span class="sxs-lookup"><span data-stu-id="710b6-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="710b6-219">Lync-Clients können die lync Server mithilfe der DHCP-Option 120 (SIP-Registrierungsoption) ermitteln.</span><span class="sxs-lookup"><span data-stu-id="710b6-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="710b6-220">Dies ist mit einer von zwei Konfigurationen möglich:</span><span class="sxs-lookup"><span data-stu-id="710b6-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="710b6-221">Konfigurieren Sie den DHCP-Server am Zweigstellenstandort so, dass er auf DHCP 120-Abfragen antwortet, die den FQDN der Registrierungsstelle auf dem Survivable Branch Appliance oder Survivable Branch Server zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="710b6-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="710b6-222">Aktivieren Sie lync Server DHCP.</span><span class="sxs-lookup"><span data-stu-id="710b6-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="710b6-223">Wenn dieser aktiviert ist, antwortet die lync Server Registrierungsstelle auf DHCP-Option 120-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="710b6-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="710b6-224">Beachten Sie, dass die Registrierung nicht auf andere DHCP-Abfragen als DHCP-Option 120 reagiert.</span><span class="sxs-lookup"><span data-stu-id="710b6-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="710b6-225">Zusätzlich sollten für größere Zweigstellenstandorte mit mehreren Subnetzen DHCP-Relay-Agents aktiviert werden, um Abfragen der DHCP-Option 120 an den DHCP Server (Konfiguration 1) oder die Registrierung (Konfiguration 2) weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="710b6-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="710b6-226">Schließlich müssen Zweigstellenbenutzer für Enterprise-VoIP konfiguriert und mit einem entsprechenden Unified Communications-Endpunkt eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="710b6-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="710b6-227">Anforderungen für Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="710b6-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="710b6-228">Die Anforderungen für Survivable Branch Server entsprechen den Anforderungen für ein Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="710b6-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="710b6-229">Ausführliche Informationen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="710b6-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="710b6-230">Anforderungen für vollständige Lync Server-Bereitstellungen am Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="710b6-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="710b6-231">Ausführliche Informationen finden Sie unter [bestimmen der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="710b6-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

