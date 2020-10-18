---
title: 'Lync Server 2013: Aushandlungs Einstellungen für XMPP-Verbundpartner'
description: 'Lync Server 2013: Aushandlungs Einstellungen für XMPP-Verbundpartner.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578641"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="c7a46-103">Aushandlungs Einstellungen für XMPP-Verbundpartner in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7a46-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7a46-104">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c7a46-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c7a46-105">Die Einstellungen für die Aushandlungstypen in der Konfiguration eines XMPP-Partners können die unterschiedlichsten Kombinationen annehmen.</span><span class="sxs-lookup"><span data-stu-id="c7a46-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="c7a46-106">Doch nicht alle diese Kombinationen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="c7a46-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="c7a46-107">In der Tabelle in diesem Abschnitt werden die gültigen und die ungültigen Einstellungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7a46-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="c7a46-108">Gängige Konfigurationen sind in der ersten Tabelle enthalten, die zweite Tabelle ist eine Auflistung aller möglichen Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="c7a46-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="c7a46-109">Beachten Sie, dass Sie keine *Simple Authentication and Security Layer* (SASL) haben können, **es sei denn** , *Transport Layer Security* (TLS) ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7a46-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="c7a46-110">SASL wird in einem unverschlüsselten (lesbaren) Format gesendet und sollte nie übertragen werden, es sei denn, es besteht Schutz durch einen anderen Mechanismus wie etwa TLS.</span><span class="sxs-lookup"><span data-stu-id="c7a46-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="c7a46-111">Gängige XMPP-Partnerverbund-Aushandlungsmethoden</span><span class="sxs-lookup"><span data-stu-id="c7a46-111">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="c7a46-112">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="c7a46-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="c7a46-113">Simple Authentication and Security Layer (SASL)</span><span class="sxs-lookup"><span data-stu-id="c7a46-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="c7a46-114">Rückrufauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7a46-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="c7a46-115">Erwartete Authentifizierungsmethode(n)</span><span class="sxs-lookup"><span data-stu-id="c7a46-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="c7a46-116">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c7a46-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-117">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-117">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-118">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-118">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-119">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-119">False</span></span></p></td>
<td><p><span data-ttu-id="c7a46-120">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c7a46-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="c7a46-p102">Wenn TLS und SASL auf Erforderlich festgelegt werden, kann damit sichergestellt werden, dass der SASL-Nachrichtenstream sicher ist. Rückruf ist nicht verfügbar und kann nicht für eine Fallbackmethode verwendet werden, wenn für den XMPP-Verbundpartner TLS nicht auf Erforderlich oder Optional festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-123">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-123">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-124">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-125">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-125">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-126">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c7a46-p103">Wenn TLS auf Erforderlich festgelegt wird, wird SASL verwendet, wenn für den XMPP-Verbundpartner SASL auf Optional oder Erforderlich festgelegt ist. Ist SASL nicht verfügbar, wird Rückruf über TLS verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-129">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-130">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-131">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-131">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-132">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c7a46-p104">Diese Einstellungen sind zwar sehr flexibel hinsichtlich der angebotenen Aushandlungsmethoden, erfordern aber die Einstellungen des XMPP-Verbundpartners. Wenn für den Partner TLS auf Optional oder Erforderlich festgelegt ist, SASL aber nicht unterstützt wird, ist TLS-Rückruf verfügbar. Wenn für den Partner TLS und SASL auf Optional oder Erforderlich festgelegt sind, wird die optimale Auswahl von TLS über SASL verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-136">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-137">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-138">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-138">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-139">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c7a46-p105">In vielen Fällen ist TCP-Rückruf die einzig mögliche Lösung. Das ist zwar weniger optimal als andere Optionen, bietet aber ein bestimmtes Maß an Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="c7a46-142">Schema der XMPP-Partnerverbund-Aushandlungsmethoden (vollständig)</span><span class="sxs-lookup"><span data-stu-id="c7a46-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="c7a46-143">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="c7a46-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="c7a46-144">Simple Authentication and Security Layer (SASL)</span><span class="sxs-lookup"><span data-stu-id="c7a46-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="c7a46-145">Rückrufauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7a46-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="c7a46-146">Erwartete Authentifizierungsmethode</span><span class="sxs-lookup"><span data-stu-id="c7a46-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="c7a46-147">Anmerkungen, Warnung oder Fehler wegen ungültiger Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c7a46-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-148">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-148">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-149">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-149">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-150">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-150">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-151">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c7a46-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-152">Rückruf funktioniert nicht, wenn sowohl SASL als auch TLS erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c7a46-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-153">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-153">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-154">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-154">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-155">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-155">False</span></span></p></td>
<td><p><span data-ttu-id="c7a46-156">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c7a46-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-157">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-158">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-158">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-159">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-159">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-160">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-p106">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p106">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-163">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-164">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-164">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-165">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-165">False</span></span></p></td>
<td><p><span data-ttu-id="c7a46-166">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c7a46-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-p107">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p107">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-169">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-170">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-170">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-171">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-171">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-172">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-p108">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p108">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-175">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-176">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-176">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-177">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-178">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c7a46-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-p109">Da SASL TLS erfordert und TLS nicht verfügbar ist, SASL/TLS kann nicht erfolgreich sein. TCP-Rückruf ist auf False festgelegt und kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-181">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-181">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-182">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-183">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-183">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-184">SASL über TLS, TLS-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-185">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-185">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-186">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-187">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-187">False</span></span></p></td>
<td><p><span data-ttu-id="c7a46-188">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c7a46-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-189">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-190">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-191">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-191">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-192">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-p110">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p110">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-195">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-196">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-197">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-197">False</span></span></p></td>
<td><p><span data-ttu-id="c7a46-198">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c7a46-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-p111">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p111">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-201">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-202">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-203">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-203">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-204">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-p112">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p112">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-207">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-208">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-209">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-210">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c7a46-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-p113">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c7a46-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-213">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-213">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-214">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-215">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-215">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-216">TLS-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="c7a46-217">Konfiguration erlaubt TLS-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="c7a46-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-218">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7a46-218">Required</span></span></p></td>
<td><p><span data-ttu-id="c7a46-219">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-220">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-220">False</span></span></p></td>
<td><p><span data-ttu-id="c7a46-221">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c7a46-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-222">SASL oder Rückruf muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c7a46-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-223">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-224">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-225">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-225">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-226">TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c7a46-227">Je nach den Aushandlungsoptionen am anderen Endpunkt wird TCP- oder TLS-Rückruf akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c7a46-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-228">Optional</span><span class="sxs-lookup"><span data-stu-id="c7a46-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="c7a46-229">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-230">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-230">False</span></span></p></td>
<td><p><span data-ttu-id="c7a46-231">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c7a46-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-232">SASL oder Rückruf muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c7a46-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a46-233">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-234">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-235">Richtig</span><span class="sxs-lookup"><span data-stu-id="c7a46-235">True</span></span></p></td>
<td><p><span data-ttu-id="c7a46-236">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c7a46-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c7a46-237">TCP-Rückruf ist die einzige verfügbare Aushandlungsmethode</span><span class="sxs-lookup"><span data-stu-id="c7a46-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a46-238">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-239">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c7a46-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c7a46-240">False</span><span class="sxs-lookup"><span data-stu-id="c7a46-240">False</span></span></p></td>
<td><p><span data-ttu-id="c7a46-241">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c7a46-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c7a46-242">SASL oder Rückruf muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c7a46-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

