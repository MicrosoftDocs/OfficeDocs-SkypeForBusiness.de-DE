---
title: 'Lync Server 2013: Planen des ausgehenden VoIP-Routings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 852e11c596a541f04fe1dd5771dee193db48e600
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513432"
---
# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="51aa4-102">Planen der ausgehenden VoIP-Weiterleitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51aa4-102">Planning outbound voice routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51aa4-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="51aa4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="51aa4-p101">Das Routing ausgehender Anrufe wird auf Anrufe angewendet, die an ein PSTN-Gateway (Public Switched Telephone Network) , einen Trunk oder eine Nebenstellenanlage gerichtet sind. Wenn ein Benutzer einen Anruf tätigt, normalisiert der Server die Rufnummer ggf., indem er diese in das E.164-Format übersetzt und versucht, sie einem SIP-URI zuzuordnen. Ermittelt der Server keine Übereinstimmung, wird die Routinglogik für ausgehende Anrufe basierend auf der bereitgestellten Wählzeichenfolge angewendet. Sie können diese Logik durch Konfigurieren der Servereinstellungen definieren, die in der folgenden Tabelle beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="51aa4-p101">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string. You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="51aa4-108">Einstellungen für das Routing ausgehender Anrufe in Lync Server</span><span class="sxs-lookup"><span data-stu-id="51aa4-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51aa4-109">Objekt</span><span class="sxs-lookup"><span data-stu-id="51aa4-109">Object</span></span></th>
<th><span data-ttu-id="51aa4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51aa4-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51aa4-111">Wähleinstellungen</span><span class="sxs-lookup"><span data-stu-id="51aa4-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="51aa4-112">Wähleinstellungen sind benannte Sätze aus Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="51aa4-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51aa4-113">Normalisierungsregel</span><span class="sxs-lookup"><span data-stu-id="51aa4-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="51aa4-p102">Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt. Ein und dieselbe Wählzeichenfolge kann je nach Standort, an dem sie gewählt wurde, und je nach Person oder Kontaktobjekt, die bzw. das den Anruf tätigt, unterschiedlich interpretiert und übersetzt werden. Eine Gruppe von Normalisierungsregeln, die einem bestimmten Standort zugeordnet sind, bildet einen Satz mit Wähleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="51aa4-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51aa4-117">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="51aa4-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="51aa4-p103">Eine VoIP-Richtlinie ordnet einem Benutzer oder einer Benutzergruppe mindestens einen PSTN-Verwendungsdatensatz zu. Eine VoIP-Richtlinie stellt darüber hinaus eine Liste der Anruffunktionen bereit, die Sie aktivieren oder deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="51aa4-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51aa4-120">PSTN-Verwendungsdatensatz</span><span class="sxs-lookup"><span data-stu-id="51aa4-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="51aa4-121">Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von bestimmten Benutzern oder Benutzergruppen in einer Organisation getätigt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="51aa4-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51aa4-122">Anrufroute</span><span class="sxs-lookup"><span data-stu-id="51aa4-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="51aa4-p104">Eine Anrufroute ordnet Zielrufnummern bestimmte Trunks und PSTN-Verwendungseinträge zu. Ein PSTN-Gateway wird als Trunk angesehen.</span><span class="sxs-lookup"><span data-stu-id="51aa4-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="51aa4-125">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="51aa4-125">In This Section</span></span>

<span data-ttu-id="51aa4-126">In diesem Abschnitt werden Richtlinien zum Konfigurieren der folgenden Servereinstellungen für das Ausgangsrouting bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="51aa4-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="51aa4-127">Wählpläne und Normalisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51aa4-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="51aa4-128">VoIP-Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51aa4-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="51aa4-129">PSTN-Verwendungsdaten Sätze in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51aa4-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="51aa4-130">VoIP-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51aa4-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51aa4-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51aa4-131">See Also</span></span>


[<span data-ttu-id="51aa4-132">SIP-Trunking in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51aa4-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="51aa4-133">Direkte SIP-Verbindungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51aa4-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

