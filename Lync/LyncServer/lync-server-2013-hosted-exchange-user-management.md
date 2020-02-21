---
title: 'Lync Server 2013: Hosted Exchange User Management'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cceaeaa869d1e058251a62d237c563143a4ae4c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="2635e-102">Gehostete Exchange-Benutzerverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2635e-102">Hosted Exchange user management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2635e-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2635e-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2635e-104">Um Voicemail-Dienste für lync Server 2013 Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, müssen Sie Ihre Benutzerkonten für gehostete Voicemail aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2635e-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2635e-105">Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine Richtlinie für gehostete Voicemail, die für das entsprechende Benutzerkonto gilt, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2635e-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="2635e-106">Die Richtlinie kann global, Standort oder benutzerbezogen sein, solange Sie auf den Benutzer angewendet wird, den Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2635e-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="2635e-107">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted Voice Mail Policies in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2635e-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="2635e-108">Das "msexchucvoicemailsettings"-Attribut</span><span class="sxs-lookup"><span data-stu-id="2635e-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="2635e-109">Lync Server 2013 stellt ein neues Benutzerattribut namens **"msexchucvoicemailsettings"** vor, das im Rahmen der Vorbereitung des lync Server 2013 Active Directory Schemas erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2635e-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="2635e-110">Dieses mehrwertige Attribut umfasst Voicemaileinstellungen, die von lync Server 2013 und dem gehosteten Exchange-Dienst gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2635e-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="2635e-111">Der gehostete Exchange-Dienst kann in einigen Fällen den Wert des "msexchucvoicemailsettings"-Attributs bei der Aktivierung von Exchange um oder beim Übertragen von Postfächern in einen gehosteten Exchange Server festlegen.</span><span class="sxs-lookup"><span data-stu-id="2635e-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="2635e-112">Wenn dieses Attribut nicht von Exchange festgelegt wird, muss der lync Server 2013 Administrator es durch Ausführen des Cmdlets "CsUser" festlegen, wie weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2635e-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="2635e-113">Die Schlüssel-Wert-Paare des Attributs und deren Autoren sind in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2635e-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="2635e-114">Schlüssel-Wert-Paare des "msexchucvoicemailsettings"-Attributs</span><span class="sxs-lookup"><span data-stu-id="2635e-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2635e-115">Wert</span><span class="sxs-lookup"><span data-stu-id="2635e-115">Value</span></span></th>
<th><span data-ttu-id="2635e-116">Ursprung</span><span class="sxs-lookup"><span data-stu-id="2635e-116">Author</span></span></th>
<th><span data-ttu-id="2635e-117">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="2635e-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2635e-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="2635e-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="2635e-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="2635e-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="2635e-120">Der Benutzer wurde für den gehosteten um-Zugriff über Exchange Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2635e-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="2635e-121">Die Exchange um Routing Anwendung prüft die Richtlinie für gehostete Voicemail des Benutzers auf Routing Details.</span><span class="sxs-lookup"><span data-stu-id="2635e-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2635e-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="2635e-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="2635e-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="2635e-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="2635e-124">Der Benutzer wurde für den gehosteten um-Zugriff mit Exchange Server deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2635e-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2635e-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="2635e-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="2635e-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="2635e-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="2635e-127">Der Benutzer wurde für den gehosteten um-Zugriff über lync Server 2013 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2635e-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="2635e-128">Die lync Server 2013 ExUM-Routing Anwendung prüft die Richtlinie für gehostete Voicemail des Benutzers auf Routing Details.</span><span class="sxs-lookup"><span data-stu-id="2635e-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2635e-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="2635e-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="2635e-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="2635e-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="2635e-131">Der Benutzer wurde für den gehosteten um-Zugriff mit lync Server 2013 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2635e-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2635e-132">Wenn das Attribut bereits Werte enthält, die nicht zu den lync Server 2013 Schlüssel/Wert-Paaren (CSHostedVoiceMail = 0 oder CSHostedVoiceMail = 1), wird eine Warnung angezeigt, dass das Attribut von einer anderen Anwendung verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2635e-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="2635e-133">Beispielsweise wird eine Warnung angezeigt, wenn das Schlüssel/Wert-Paar ExchangeHostedVoiceMail = 0 oder ExchangeHostedVoiceMail = 1 bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2635e-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="2635e-134">In diesem Fall können Sie den Wert ändern, indem Sie ihn im Active Directory bearbeiten oder das folgende Cmdlet ausführen, um den Wert auf NULL festzulegen:</span><span class="sxs-lookup"><span data-stu-id="2635e-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="2635e-135">Gruppe-CsUser – Identity User – HostedVoicemail $NULL</span><span class="sxs-lookup"><span data-stu-id="2635e-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="2635e-136">Aktivieren von Benutzern für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="2635e-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="2635e-137">Um zu ermöglichen, dass die Voicemail-Anrufe eines Benutzers an gehostete Exchange um weitergeleitet werden, müssen Sie das Cmdlet "Cmdlet festlegen" ausführen, um den Wert des *HostedVoiceMail* -Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2635e-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="2635e-138">Dieser Parameter signalisiert auch lync Server 2013, das Symbol "Voicemail anrufen" aufzuhellen.</span><span class="sxs-lookup"><span data-stu-id="2635e-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="2635e-139">Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail aktiviert:</span><span class="sxs-lookup"><span data-stu-id="2635e-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="2635e-140">Das Cmdlet überprüft, ob eine Richtlinie für gehostete Voicemail (Global, Websiteebene oder pro Benutzer) auf diesen Benutzer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2635e-140">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="2635e-141">Wenn keine Richtlinie angewendet wird, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="2635e-141">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="2635e-142">Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="2635e-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="2635e-143">Das Cmdlet überprüft, ob für diesen Benutzer keine Richtlinie für gehostete Voicemails (Global, Websiteebene oder pro Benutzer) gilt.</span><span class="sxs-lookup"><span data-stu-id="2635e-143">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="2635e-144">Wenn eine Richtlinie angewendet wird, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="2635e-144">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="2635e-145">Ausführliche Informationen zur Verwendung des Cmdlets "CsUser" finden Sie in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="2635e-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

