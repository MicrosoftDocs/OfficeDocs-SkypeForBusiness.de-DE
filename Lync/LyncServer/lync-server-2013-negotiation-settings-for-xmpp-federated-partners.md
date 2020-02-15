---
title: 'Lync Server 2013: Aushandlungs Einstellungen für XMPP-Verbundpartner'
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
ms.openlocfilehash: c190e4a45a70bd527aa8fc6323a671d481f04872
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="c6a20-102">Aushandlungs Einstellungen für XMPP-Verbundpartner in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6a20-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6a20-103">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c6a20-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c6a20-104">Die Einstellungen für die Aushandlungstypen in der Konfiguration eines XMPP-Partners können die unterschiedlichsten Kombinationen annehmen.</span><span class="sxs-lookup"><span data-stu-id="c6a20-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="c6a20-105">Doch nicht alle diese Kombinationen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="c6a20-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="c6a20-106">In der Tabelle in diesem Abschnitt werden die gültigen und die ungültigen Einstellungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c6a20-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="c6a20-107">Gängige Konfigurationen sind in der ersten Tabelle enthalten, die zweite Tabelle ist eine Auflistung aller möglichen Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="c6a20-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="c6a20-108">Beachten Sie, dass Sie keine *Simple Authentication and Security Layer* (SASL) haben können, **es sei denn** , *Transport Layer Security* (TLS) ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c6a20-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="c6a20-109">SASL wird in einem unverschlüsselten (lesbaren) Format gesendet und sollte nie übertragen werden, es sei denn, es besteht Schutz durch einen anderen Mechanismus wie etwa TLS.</span><span class="sxs-lookup"><span data-stu-id="c6a20-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="c6a20-110">Gängige XMPP-Partnerverbund-Aushandlungsmethoden</span><span class="sxs-lookup"><span data-stu-id="c6a20-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="c6a20-111">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="c6a20-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="c6a20-112">Simple Authentication and Security Layer (SASL)</span><span class="sxs-lookup"><span data-stu-id="c6a20-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="c6a20-113">Rückrufauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="c6a20-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="c6a20-114">Erwartete Authentifizierungsmethode(n)</span><span class="sxs-lookup"><span data-stu-id="c6a20-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="c6a20-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6a20-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-116">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-116">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-117">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-117">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-118">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-118">False</span></span></p></td>
<td><p><span data-ttu-id="c6a20-119">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c6a20-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="c6a20-p102">Wenn TLS und SASL auf Erforderlich festgelegt werden, kann damit sichergestellt werden, dass der SASL-Nachrichtenstream sicher ist. Rückruf ist nicht verfügbar und kann nicht für eine Fallbackmethode verwendet werden, wenn für den XMPP-Verbundpartner TLS nicht auf Erforderlich oder Optional festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c6a20-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-122">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-122">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-123">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-124">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-124">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-125">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c6a20-p103">Wenn TLS auf Erforderlich festgelegt wird, wird SASL verwendet, wenn für den XMPP-Verbundpartner SASL auf Optional oder Erforderlich festgelegt ist. Ist SASL nicht verfügbar, wird Rückruf über TLS verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6a20-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-128">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-129">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-130">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-130">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-131">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c6a20-p104">Diese Einstellungen sind zwar sehr flexibel hinsichtlich der angebotenen Aushandlungsmethoden, erfordern aber die Einstellungen des XMPP-Verbundpartners. Wenn für den Partner TLS auf Optional oder Erforderlich festgelegt ist, SASL aber nicht unterstützt wird, ist TLS-Rückruf verfügbar. Wenn für den Partner TLS und SASL auf Optional oder Erforderlich festgelegt sind, wird die optimale Auswahl von TLS über SASL verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6a20-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-135">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-136">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-137">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-137">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-138">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c6a20-p105">In vielen Fällen ist TCP-Rückruf die einzig mögliche Lösung. Das ist zwar weniger optimal als andere Optionen, bietet aber ein bestimmtes Maß an Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="c6a20-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="c6a20-141">Schema der XMPP-Partnerverbund-Aushandlungsmethoden (vollständig)</span><span class="sxs-lookup"><span data-stu-id="c6a20-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="c6a20-142">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="c6a20-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="c6a20-143">Simple Authentication and Security Layer (SASL)</span><span class="sxs-lookup"><span data-stu-id="c6a20-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="c6a20-144">Rückrufauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="c6a20-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="c6a20-145">Erwartete Authentifizierungsmethode</span><span class="sxs-lookup"><span data-stu-id="c6a20-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="c6a20-146">Anmerkungen, Warnung oder Fehler wegen ungültiger Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6a20-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-147">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-147">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-148">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-148">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-149">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-149">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-150">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c6a20-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-151">Rückruf funktioniert nicht, wenn sowohl SASL als auch TLS erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c6a20-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-152">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-152">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-153">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-153">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-154">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-154">False</span></span></p></td>
<td><p><span data-ttu-id="c6a20-155">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c6a20-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-156">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-157">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-157">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-158">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-158">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-159">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-160">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="c6a20-160">SASL requires TLS.</span></span> <span data-ttu-id="c6a20-161">Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c6a20-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-162">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-163">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-163">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-164">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-164">False</span></span></p></td>
<td><p><span data-ttu-id="c6a20-165">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c6a20-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-166">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="c6a20-166">SASL requires TLS.</span></span> <span data-ttu-id="c6a20-167">Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c6a20-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-168">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-169">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-169">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-170">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-170">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-171">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-172">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="c6a20-172">SASL requires TLS.</span></span> <span data-ttu-id="c6a20-173">Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c6a20-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-174">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-175">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-175">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-176">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-177">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6a20-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-p109">Da SASL TLS erfordert und TLS nicht verfügbar ist, SASL/TLS kann nicht erfolgreich sein. TCP-Rückruf ist auf False festgelegt und kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6a20-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-180">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-180">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-181">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-182">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-182">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-183">SASL über TLS, TLS-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-184">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-184">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-185">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-186">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-186">False</span></span></p></td>
<td><p><span data-ttu-id="c6a20-187">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c6a20-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-188">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-189">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-190">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-190">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-191">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-192">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="c6a20-192">SASL requires TLS.</span></span> <span data-ttu-id="c6a20-193">Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c6a20-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-194">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-195">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-196">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-196">False</span></span></p></td>
<td><p><span data-ttu-id="c6a20-197">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="c6a20-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-198">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="c6a20-198">SASL requires TLS.</span></span> <span data-ttu-id="c6a20-199">Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c6a20-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-200">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-201">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-202">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-202">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-203">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-204">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="c6a20-204">SASL requires TLS.</span></span> <span data-ttu-id="c6a20-205">Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c6a20-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-206">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-207">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-208">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-209">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6a20-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-p113">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="c6a20-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-212">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-212">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-213">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-214">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-214">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-215">TLS-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="c6a20-216">Konfiguration erlaubt TLS-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="c6a20-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-217">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c6a20-217">Required</span></span></p></td>
<td><p><span data-ttu-id="c6a20-218">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-219">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-219">False</span></span></p></td>
<td><p><span data-ttu-id="c6a20-220">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6a20-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-221">SASL oder Rückruf muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c6a20-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-222">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-223">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-224">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-224">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-225">TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c6a20-226">Je nach den Aushandlungsoptionen am anderen Endpunkt wird TCP- oder TLS-Rückruf akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c6a20-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-227">Optional</span><span class="sxs-lookup"><span data-stu-id="c6a20-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="c6a20-228">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-229">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-229">False</span></span></p></td>
<td><p><span data-ttu-id="c6a20-230">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6a20-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-231">SASL oder Rückruf muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c6a20-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6a20-232">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-233">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-234">Wahr</span><span class="sxs-lookup"><span data-stu-id="c6a20-234">True</span></span></p></td>
<td><p><span data-ttu-id="c6a20-235">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="c6a20-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="c6a20-236">TCP-Rückruf ist die einzige verfügbare Aushandlungsmethode</span><span class="sxs-lookup"><span data-stu-id="c6a20-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6a20-237">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-238">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c6a20-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c6a20-239">False</span><span class="sxs-lookup"><span data-stu-id="c6a20-239">False</span></span></p></td>
<td><p><span data-ttu-id="c6a20-240">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6a20-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="c6a20-241">SASL oder Rückruf muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c6a20-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

