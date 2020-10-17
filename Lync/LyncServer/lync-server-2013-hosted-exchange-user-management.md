---
title: 'Lync Server 2013: Hosted Exchange User Management'
description: 'Lync Server 2013: Hosted Exchange User Management.'
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
ms.openlocfilehash: 9ceda9352fc627fc7b762b5995d788ffafa159ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550111"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="76762-103">Gehostete Exchange-Benutzerverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76762-103">Hosted Exchange user management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76762-104">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="76762-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="76762-105">Um Voicemail-Dienste für lync Server 2013 Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, müssen Sie Ihre Benutzerkonten für gehostete Voicemail aktivieren.</span><span class="sxs-lookup"><span data-stu-id="76762-105">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76762-106">Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine Richtlinie für gehostete Voicemail, die für das entsprechende Benutzerkonto gilt, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="76762-106">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="76762-107">Die Richtlinie kann global, Standort oder benutzerbezogen sein, solange Sie auf den Benutzer angewendet wird, den Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="76762-107">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="76762-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted Voice Mail Policies in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="76762-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="76762-109">Das "msexchucvoicemailsettings"-Attribut</span><span class="sxs-lookup"><span data-stu-id="76762-109">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="76762-110">Lync Server 2013 stellt ein neues Benutzerattribut namens **"msexchucvoicemailsettings"** vor, das im Rahmen der Vorbereitung des lync Server 2013 Active Directory Schemas erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="76762-110">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="76762-111">Dieses mehrwertige Attribut umfasst Voicemaileinstellungen, die von lync Server 2013 und dem gehosteten Exchange-Dienst gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76762-111">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="76762-112">Der gehostete Exchange-Dienst kann in einigen Fällen den Wert des "msexchucvoicemailsettings"-Attributs bei der Aktivierung von Exchange um oder beim Übertragen von Postfächern in einen gehosteten Exchange Server festlegen.</span><span class="sxs-lookup"><span data-stu-id="76762-112">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="76762-113">Wenn dieses Attribut nicht von Exchange festgelegt wird, muss der lync Server 2013 Administrator es durch Ausführen des Set-CsUser-Cmdlets festlegen, wie weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76762-113">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="76762-114">Die Schlüssel-Wert-Paare des Attributs und deren Autoren sind in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="76762-114">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="76762-115">Schlüssel-Wert-Paare des "msexchucvoicemailsettings"-Attributs</span><span class="sxs-lookup"><span data-stu-id="76762-115">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76762-116">Wert</span><span class="sxs-lookup"><span data-stu-id="76762-116">Value</span></span></th>
<th><span data-ttu-id="76762-117">Ursprung</span><span class="sxs-lookup"><span data-stu-id="76762-117">Author</span></span></th>
<th><span data-ttu-id="76762-118">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="76762-118">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76762-119">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="76762-119">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="76762-120">Exchange</span><span class="sxs-lookup"><span data-stu-id="76762-120">Exchange</span></span></p></td>
<td><p><span data-ttu-id="76762-121">Der Benutzer wurde für den gehosteten um-Zugriff über Exchange Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="76762-121">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="76762-122">Die Exchange um Routing Anwendung prüft die Richtlinie für gehostete Voicemail des Benutzers auf Routing Details.</span><span class="sxs-lookup"><span data-stu-id="76762-122">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76762-123">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="76762-123">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="76762-124">Exchange</span><span class="sxs-lookup"><span data-stu-id="76762-124">Exchange</span></span></p></td>
<td><p><span data-ttu-id="76762-125">Der Benutzer wurde für den gehosteten um-Zugriff mit Exchange Server deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="76762-125">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76762-126">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="76762-126">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="76762-127">Lync Server</span><span class="sxs-lookup"><span data-stu-id="76762-127">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="76762-128">Der Benutzer wurde für den gehosteten um-Zugriff über lync Server 2013 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="76762-128">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="76762-129">Die lync Server 2013 ExUM-Routing Anwendung prüft die Richtlinie für gehostete Voicemail des Benutzers auf Routing Details.</span><span class="sxs-lookup"><span data-stu-id="76762-129">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76762-130">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="76762-130">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="76762-131">Lync Server</span><span class="sxs-lookup"><span data-stu-id="76762-131">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="76762-132">Der Benutzer wurde für den gehosteten um-Zugriff mit lync Server 2013 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="76762-132">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="76762-133">Wenn das Attribut bereits Werte enthält, die nicht zu den lync Server 2013 Schlüssel/Wert-Paaren (CSHostedVoiceMail = 0 oder CSHostedVoiceMail = 1), wird eine Warnung angezeigt, dass das Attribut von einer anderen Anwendung verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="76762-133">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="76762-134">Beispielsweise wird eine Warnung angezeigt, wenn das Schlüssel/Wert-Paar ExchangeHostedVoiceMail = 0 oder ExchangeHostedVoiceMail = 1 bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="76762-134">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="76762-135">In diesem Fall können Sie den Wert ändern, indem Sie ihn im Active Directory bearbeiten oder das folgende Cmdlet ausführen, um den Wert auf NULL festzulegen:</span><span class="sxs-lookup"><span data-stu-id="76762-135">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="76762-136">Set-CsUser – Identitäts Benutzer – HostedVoicemail $NULL</span><span class="sxs-lookup"><span data-stu-id="76762-136">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="76762-137">Aktivieren von Benutzern für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="76762-137">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="76762-138">Um zu ermöglichen, dass die Voicemail-Anrufe eines Benutzers an gehostete Exchange um weitergeleitet werden, müssen Sie das Set-CsUser-Cmdlet ausführen, um den Wert des Parameters *HostedVoiceMail* festzulegen.</span><span class="sxs-lookup"><span data-stu-id="76762-138">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="76762-139">Dieser Parameter signalisiert auch lync Server 2013, das Symbol "Voicemail anrufen" aufzuhellen.</span><span class="sxs-lookup"><span data-stu-id="76762-139">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="76762-140">Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail aktiviert:</span><span class="sxs-lookup"><span data-stu-id="76762-140">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="76762-141">Das Cmdlet überprüft, ob eine Richtlinie für gehostete Voicemail (Global, Websiteebene oder pro Benutzer) auf diesen Benutzer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="76762-141">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="76762-142">Wenn keine Richtlinie angewendet wird, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="76762-142">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="76762-143">Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="76762-143">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="76762-144">Das Cmdlet überprüft, ob für diesen Benutzer keine Richtlinie für gehostete Voicemails (Global, Websiteebene oder pro Benutzer) gilt.</span><span class="sxs-lookup"><span data-stu-id="76762-144">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="76762-145">Wenn eine Richtlinie angewendet wird, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="76762-145">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="76762-146">Ausführliche Informationen zur Verwendung des Set-CsUser-Cmdlets finden Sie in der lync Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="76762-146">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

