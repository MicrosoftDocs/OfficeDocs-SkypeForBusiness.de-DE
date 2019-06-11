---
title: 'Lync Server 2013: Bereitstellungscheckliste für E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9a48ba3d999e55106298d7419e4590147e1e9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="3a427-102">Bereitstellungscheckliste für E9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a427-102">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a427-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3a427-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3a427-104">Um effektiv für Enhanced 9-1-1 (E9-1-1) zu planen, müssen Sie unbedingt die folgenden Bereitstellungsanforderungen berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="3a427-104">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="3a427-105">Voraussetzungen für die Bereitstellung von E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="3a427-105">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="3a427-106">Schritte, die für die Bereitstellung von E9-1-1 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3a427-106">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="3a427-107">Voraussetzungen für die Bereitstellung von E9-1-1</span><span class="sxs-lookup"><span data-stu-id="3a427-107">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="3a427-108">Bevor Sie E9-1-1 bereitstellen, müssen Sie bereits die internen lync Server-Server bereitgestellt haben, einschließlich eines zentralen Verwaltungsspeichers, eines Front-End-Pools oder eines Standard Edition-Servers, eines oder mehrerer Vermittlungsserver oder Mediation Server-Pools und lync Server-Clients.</span><span class="sxs-lookup"><span data-stu-id="3a427-108">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="3a427-109">Darüber hinaus benötigen Sie für eine E9-1-1-Bereitstellung einen SIP-Trunk zu einem qualifizierten E9-1-1-Dienstanbieter oder ein ELIN-Gateway (Emergency Location Identification Number) zu Ihrem Telefonfestnetz (Public Switched Telephone Network, PSTN).</span><span class="sxs-lookup"><span data-stu-id="3a427-109">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="3a427-110">Lync Server unterstützt die Verwendung von E9-1-1-Dienstanbietern nur innerhalb der Vereinigten Staaten.</span><span class="sxs-lookup"><span data-stu-id="3a427-110">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="3a427-111">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="3a427-111">Deployment Process</span></span>

<span data-ttu-id="3a427-112">Die folgende Tabelle zeigt eine Übersicht über den E9-1-1-Bereitstellungsprozess.</span><span class="sxs-lookup"><span data-stu-id="3a427-112">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="3a427-113">Ausführliche Informationen zu Bereitstellungsschritten finden Sie unter [Konfigurieren von erweitertem 9-1-1 in lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3a427-113">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a427-114">Phase</span><span class="sxs-lookup"><span data-stu-id="3a427-114">Phase</span></span></th>
<th><span data-ttu-id="3a427-115">Schritte</span><span class="sxs-lookup"><span data-stu-id="3a427-115">Steps</span></span></th>
<th><span data-ttu-id="3a427-116">Rollen</span><span class="sxs-lookup"><span data-stu-id="3a427-116">Roles</span></span></th>
<th><span data-ttu-id="3a427-117">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="3a427-117">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a427-118">Konfigurieren von VoIP-Nutzungen, Routen und Trunks</span><span class="sxs-lookup"><span data-stu-id="3a427-118">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="3a427-p103">Erstellen Sie einen neuen PSTN-Verwendungseintrag. Hierbei handelt es sich um den gleichen Namen, der in der Standortrichtlinie für die Einstellung <strong>PSTN-Verwendung</strong> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a427-p103">Create a new PSTN usage record. This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="3a427-121">Erstellen Sie eine VoIP-Route oder weisen Sie dem im vorherigen Schritt erstellten PSTN-Verwendungseintrag eine solche zu und lassen Sie das Gatewayattribut auf den E9-1-1-SIP-Trunk oder das ELIN-Gateway verweisen. </span><span class="sxs-lookup"><span data-stu-id="3a427-121">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="3a427-122">Stellen Sie für SIP-Trunk-E9-1-1-Dienstanbieter den Trunk, der E9-1-1-Anrufe über SIP verarbeiten soll, so ein, dass PIDF-LO-Daten weitergegeben werden. Verwenden Sie dazu das Cmdlet <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</span><span class="sxs-lookup"><span data-stu-id="3a427-122">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="3a427-p104">Optional können Sie für SIP-Trunk-E9-1-1-Dienstanbieter eine lokale PSTN-Route für Anrufe erstellen oder zuweisen, die nicht vom SIP-Trunk des E9-1-1-Dienstanbieters verwaltet werden. Diese Route wird verwendet, wenn keine Verbindung zum E9-1-1-Dienstanbieter besteht. Wenn dies von Ihrem E9-1-1-Dienstanbieter unterstützt wird, weisen Sie dem Gateway eine Trunkkonfigurationsregel zu, die die Notrufzeichenfolge in die DID (Direct Inward Dialing)-Nummer des nationalen/regionalen Telefoncenters für Notrufe (Emergency Call Response Center, ECRC) übersetzt.</span><span class="sxs-lookup"><span data-stu-id="3a427-p104">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available. If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="3a427-126">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="3a427-126">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="3a427-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Konfigurieren einer E9-1-1-VoIP-Route in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3a427-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a427-128">Erstellen von Standortrichtlinien und Zuweisen dieser Standortrichtlinien zu Benutzern und Subnetzen</span><span class="sxs-lookup"><span data-stu-id="3a427-128">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="3a427-129">Überprüfen Sie die globale Standortrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="3a427-129">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="3a427-130">Erstellen Sie eine Standortrichtlinie auf Benutzerebene oder erstellen Sie, wenn die Organisation über mehr als einen Standort mit verschiedenen Notfallverwendungen verfügt, eine Standortrichtlinie auf Netzwerkebene.</span><span class="sxs-lookup"><span data-stu-id="3a427-130">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="3a427-131">Weisen Sie die Standortrichtlinie Netzwerkstandorten zu.</span><span class="sxs-lookup"><span data-stu-id="3a427-131">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="3a427-132">Fügen Sie dem Netzwerkstandort geeignete Subnetze hinzu.</span><span class="sxs-lookup"><span data-stu-id="3a427-132">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="3a427-133">(Optional) Weisen Sie die Standortrichtlinie Benutzerrichtlinien zu.</span><span class="sxs-lookup"><span data-stu-id="3a427-133">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="3a427-134">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="3a427-134">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="3a427-135">CSLocationAdmin (außer bei Erstellung von Standortrichtlinien)</span><span class="sxs-lookup"><span data-stu-id="3a427-135">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="3a427-136"><a href="lync-server-2013-create-location-policies.md">Erstellen von Standortrichtlinien in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3a427-136"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3a427-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3a427-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3a427-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Zuordnen von Subnetzen zu Netzwerkstandorten für E9-1-1 in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3a427-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a427-139">Konfigurieren der Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="3a427-139">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="3a427-140">Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf.</span><span class="sxs-lookup"><span data-stu-id="3a427-140">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="3a427-141">Für Elin-Gateways fügen Sie die Elins zur Spalte &lt;CompanyName&gt; hinzu.</span><span class="sxs-lookup"><span data-stu-id="3a427-141">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="3a427-142">Konfigurieren Sie für die Verbindung zum E9-1-1-Dienstanbieter die Überprüfung der Adressen.</span><span class="sxs-lookup"><span data-stu-id="3a427-142">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="3a427-143">Gleichen Sie die Adressen mit dem E9-1-1-Dienstanbieter ab.</span><span class="sxs-lookup"><span data-stu-id="3a427-143">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="3a427-144">Veröffentlichen Sie die aktualisierte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3a427-144">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="3a427-145">Laden Sie für ELIN-Gateways die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hoch.</span><span class="sxs-lookup"><span data-stu-id="3a427-145">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="3a427-146">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="3a427-146">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="3a427-147">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="3a427-147">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="3a427-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3a427-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a427-149">Konfigurieren von erweiterten Funktionen (optional)</span><span class="sxs-lookup"><span data-stu-id="3a427-149">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="3a427-150">Konfigurieren Sie die URL für die SNMP-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3a427-150">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="3a427-151">Konfigurieren Sie die URL für den Speicherort des Informationsdiensts für sekundären Standort.</span><span class="sxs-lookup"><span data-stu-id="3a427-151">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="3a427-152">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="3a427-152">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="3a427-153"><a href="lync-server-2013-configure-an-snmp-application.md">Konfigurieren einer SNMP-Anwendung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3a427-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3a427-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Konfigurieren eines sekundären Standort Informationsdiensts in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3a427-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

