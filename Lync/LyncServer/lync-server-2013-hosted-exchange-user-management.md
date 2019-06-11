---
title: 'Lync Server 2013: Benutzerverwaltung für gehostete Exchange-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead9762c67f3239f84cc1290b4ff2e9acc976318
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="080c0-102">Benutzerverwaltung für gehostete Exchange-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="080c0-102">Hosted Exchange user management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="080c0-103">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="080c0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="080c0-104">Wenn Sie Voicemail-Dienste für lync Server 2013-Benutzer bereitstellen möchten, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, müssen Sie deren Benutzerkonten für gehostete Voicemail aktivieren.</span><span class="sxs-lookup"><span data-stu-id="080c0-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="080c0-105">Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine gehostete Voicemail-Richtlinie bereitgestellt werden, die für das entsprechende Benutzerkonto gilt.</span><span class="sxs-lookup"><span data-stu-id="080c0-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="080c0-106">Die Richtlinie kann global, Site oder pro Benutzer im Umfang sein, sofern Sie für den Benutzer gilt, den Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="080c0-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="080c0-107">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="080c0-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="080c0-108">Das msExchUCVoiceMailSettings-Attribut</span><span class="sxs-lookup"><span data-stu-id="080c0-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="080c0-109">Lync Server 2013 führt ein neues Benutzerattribut mit dem Namen **msExchUCVoiceMailSettings**ein, das im Rahmen der Active Directory-Schemavorbereitung von lync Server 2013 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="080c0-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="080c0-110">Dieses mehrwertige Attribut enthält Einstellungen für Voicemail, die von lync Server 2013 und dem gehosteten Exchange-Dienst freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="080c0-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="080c0-111">Der gehostete Exchange-Dienst kann in einigen Fällen den Wert des Attributs msExchUCVoiceMailSettings beim Aktivieren von Exchange um oder während des Prozesses der Übertragung von Postfächern auf einen gehosteten Exchange-Server einstellen.</span><span class="sxs-lookup"><span data-stu-id="080c0-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="080c0-112">Wenn dieses Attribut nicht von Exchange gesetzt wird, muss der lync Server 2013-Administrator es durch Ausführen des Cmdlets "CsUser", wie weiter oben in diesem Thema beschrieben, einrichten.</span><span class="sxs-lookup"><span data-stu-id="080c0-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="080c0-113">Die Schlüssel-Wert-Paare des Attributs und deren Autoren sind in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="080c0-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="080c0-114">Schlüssel-Wert-Paare des msExchUCVoiceMailSettings-Attributs</span><span class="sxs-lookup"><span data-stu-id="080c0-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="080c0-115">Wert</span><span class="sxs-lookup"><span data-stu-id="080c0-115">Value</span></span></th>
<th><span data-ttu-id="080c0-116">Autor</span><span class="sxs-lookup"><span data-stu-id="080c0-116">Author</span></span></th>
<th><span data-ttu-id="080c0-117">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="080c0-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="080c0-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="080c0-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="080c0-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="080c0-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="080c0-120">Der Benutzer wurde für den gehosteten um-Zugriff durch Exchange Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="080c0-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="080c0-121">Die Exchange um-Routing Anwendung überprüft die Richtlinie des Benutzers für gehostete Voicemail auf Routing Details.</span><span class="sxs-lookup"><span data-stu-id="080c0-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="080c0-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="080c0-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="080c0-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="080c0-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="080c0-124">Der Benutzer wurde für den gehosteten um-Zugriff durch Exchange Server deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="080c0-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="080c0-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="080c0-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="080c0-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="080c0-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="080c0-127">Der Benutzer wurde für den gehosteten um-Zugriff von lync Server 2013 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="080c0-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="080c0-128">Die lync Server 2013 ExUM-Routing Anwendung überprüft die Richtlinie des Benutzers für gehostete Voicemail auf Routing Details.</span><span class="sxs-lookup"><span data-stu-id="080c0-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="080c0-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="080c0-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="080c0-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="080c0-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="080c0-131">Der Benutzer wurde für den gehosteten um-Zugriff von lync Server 2013 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="080c0-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="080c0-132">Wenn das Attribut bereits Werte enthält, die nicht zu den Schlüssel-Wert-Paaren von lync Server 2013 (CSHostedVoiceMail = 0 oder CSHostedVoiceMail = 1) führen, wird eine Warnung angezeigt, die besagt, dass das Attribut von einer anderen Anwendung verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="080c0-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="080c0-133">Beispielsweise wird eine Warnung angezeigt, wenn das Schlüssel-Wert-Paar ExchangeHostedVoiceMail = 0 oder ExchangeHostedVoiceMail = 1 bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="080c0-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="080c0-134">In diesem Fall können Sie den Wert ändern, indem Sie ihn in Active Directory bearbeiten, oder führen Sie das folgende Cmdlet aus, um den Wert auf NULL festzulegen:</span><span class="sxs-lookup"><span data-stu-id="080c0-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="080c0-135">Satz-CsUser – Identity User – HostedVoicemail $NULL</span><span class="sxs-lookup"><span data-stu-id="080c0-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="080c0-136">Aktivieren von Benutzern für gehostete Voicemails</span><span class="sxs-lookup"><span data-stu-id="080c0-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="080c0-137">Damit die Voicemail-Anrufe eines Benutzers an den Hosted Exchange um weitergeleitet werden können, müssen Sie das Cmdlet "setCsUser" ausführen, um den Wert des *HostedVoiceMail* -Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="080c0-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="080c0-138">Dieser Parameter signalisiert auch, dass lync Server 2013 den Indikator "Voicemail anrufen" aufleuchtet.</span><span class="sxs-lookup"><span data-stu-id="080c0-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="080c0-139">Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail aktiviert:</span><span class="sxs-lookup"><span data-stu-id="080c0-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="080c0-140">Das Cmdlet überprüft, ob eine gehostete Voicemail-Richtlinie (Global, Websiteebene oder pro Benutzer) für diesen Benutzer gilt.</span><span class="sxs-lookup"><span data-stu-id="080c0-140">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="080c0-141">Wenn keine Richtlinie zutrifft, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="080c0-141">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="080c0-142">Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="080c0-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="080c0-143">Das Cmdlet überprüft, ob für diesen Benutzer keine gehostete Voicemail-Richtlinie (Global, Website-Ebene oder pro Benutzer) gilt.</span><span class="sxs-lookup"><span data-stu-id="080c0-143">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="080c0-144">Wenn eine Richtlinie angewendet wird, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="080c0-144">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="080c0-145">Ausführliche Informationen zur Verwendung des Cmdlets "CsUser" finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="080c0-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

