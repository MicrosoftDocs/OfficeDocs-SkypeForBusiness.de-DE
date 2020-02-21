---
title: 'Lync Server 2013: Definieren der Anforderungen für Notrufe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3404a2c9ada6bf73a4fd99dfaa5f386b32b60b03
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="43bcf-102">Definieren der Anforderungen für Notrufe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43bcf-103">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="43bcf-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="43bcf-104">Bevor Sie mit einer Microsoft lync Server 2013 E9-1-1-Bereitstellung beginnen, sollten Sie zunächst in der Lage sein, die in den folgenden Abschnitten erläuterten Fragen zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="43bcf-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="43bcf-105">Welche Planungsmaßnahmen erforderlich sind, ist abhängig von der E9-1-1-Lösung, die Sie bereitstellen möchten: einen SIP-Trunk-E9-1-1-Dienstanbieter oder ein ELIN-Gateway (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="43bcf-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="43bcf-106">In der folgenden Tabelle sind die Abschnitte in dieser Planungsmappe aufgeführt, die Sie für die jeweilige Lösung berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="43bcf-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="43bcf-107">Planungsschritte nach Art der E9-1-1-Lösung</span><span class="sxs-lookup"><span data-stu-id="43bcf-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43bcf-108">SIP-Trunk-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="43bcf-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="43bcf-109">ELIN-Gateway</span><span class="sxs-lookup"><span data-stu-id="43bcf-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43bcf-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definieren des Bereichs der E9-1-1-Bereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43bcf-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definieren des Bereichs der E9-1-1-Bereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43bcf-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definieren der Netzwerkelemente, die zum Bestimmen des Standorts in lync Server 2013 verwendet werden</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43bcf-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definieren der Netzwerkelemente, die zum Bestimmen des Standorts in lync Server 2013 verwendet werden</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43bcf-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Aktivieren von Benutzern für E9-1-1 in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43bcf-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Aktivieren von Benutzern für E9-1-1 in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43bcf-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Verwalten von Speicherorten für SIP-Trunk Dienstanbieter in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43bcf-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Verwalten von Speicherorten für Elin-Gateways in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43bcf-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43bcf-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43bcf-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Entwerfen des SIP-Trunks für E9-1-1 in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43bcf-121"><a href="lync-server-2013-including-the-security-desk.md">Einschließen des Sicherheits Desks in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43bcf-122"><a href="lync-server-2013-including-the-security-desk.md">Einschließen des Sicherheits Desks in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43bcf-123"><a href="lync-server-2013-defining-the-location-policy.md">Definieren der ortungsrichtlinie für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43bcf-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Auswählen eines E9-1-1-Dienstanbieters für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43bcf-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Zuweisen eines Standortrichtlinien Bereichs in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43bcf-126"><a href="lync-server-2013-defining-the-location-policy.md">Definieren der ortungsrichtlinie für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43bcf-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Zuweisen eines Standortrichtlinien Bereichs in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="43bcf-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="43bcf-128">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="43bcf-128">In This Section</span></span>

  - [<span data-ttu-id="43bcf-129">Definieren des Bereichs der E9-1-1-Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="43bcf-130">Definieren der Netzwerkelemente, die zum Bestimmen des Standorts in lync Server 2013 verwendet werden</span><span class="sxs-lookup"><span data-stu-id="43bcf-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="43bcf-131">Aktivieren von Benutzern für E9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="43bcf-132">Verwalten von Speicherorten für SIP-Trunk Dienstanbieter in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="43bcf-133">Verwalten von Speicherorten für Elin-Gateways in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="43bcf-134">Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="43bcf-135">Entwerfen des SIP-Trunks für E9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="43bcf-136">Einschließen des Sicherheits Desks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="43bcf-137">Auswählen eines E9-1-1-Dienstanbieters für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="43bcf-138">Definieren der ortungsrichtlinie für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="43bcf-139">Zuweisen eines Standortrichtlinien Bereichs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bcf-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

