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
ms.openlocfilehash: bdb09d52970b5fd97395acda6a2e4fbc824a378d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505592"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="0a2f2-102">Aushandlungs Einstellungen für XMPP-Verbundpartner in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a2f2-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a2f2-103">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="0a2f2-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="0a2f2-104">Die Einstellungen für die Aushandlungstypen in der Konfiguration eines XMPP-Partners können die unterschiedlichsten Kombinationen annehmen.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="0a2f2-105">Doch nicht alle diese Kombinationen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="0a2f2-106">In der Tabelle in diesem Abschnitt werden die gültigen und die ungültigen Einstellungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="0a2f2-107">Gängige Konfigurationen sind in der ersten Tabelle enthalten, die zweite Tabelle ist eine Auflistung aller möglichen Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="0a2f2-108">Beachten Sie, dass Sie keine *Simple Authentication and Security Layer* (SASL) haben können, **es sei denn** , *Transport Layer Security* (TLS) ist ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="0a2f2-109">SASL wird in einem unverschlüsselten (lesbaren) Format gesendet und sollte nie übertragen werden, es sei denn, es besteht Schutz durch einen anderen Mechanismus wie etwa TLS.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="0a2f2-110">Gängige XMPP-Partnerverbund-Aushandlungsmethoden</span><span class="sxs-lookup"><span data-stu-id="0a2f2-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="0a2f2-111">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="0a2f2-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="0a2f2-112">Simple Authentication and Security Layer (SASL)</span><span class="sxs-lookup"><span data-stu-id="0a2f2-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="0a2f2-113">Rückrufauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="0a2f2-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="0a2f2-114">Erwartete Authentifizierungsmethode(n)</span><span class="sxs-lookup"><span data-stu-id="0a2f2-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="0a2f2-115">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="0a2f2-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-116">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-116">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-117">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-117">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-118">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-118">False</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-119">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="0a2f2-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-p102">Wenn TLS und SASL auf Erforderlich festgelegt werden, kann damit sichergestellt werden, dass der SASL-Nachrichtenstream sicher ist. Rückruf ist nicht verfügbar und kann nicht für eine Fallbackmethode verwendet werden, wenn für den XMPP-Verbundpartner TLS nicht auf Erforderlich oder Optional festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-122">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-122">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-123">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-124">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-124">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-125">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-p103">Wenn TLS auf Erforderlich festgelegt wird, wird SASL verwendet, wenn für den XMPP-Verbundpartner SASL auf Optional oder Erforderlich festgelegt ist. Ist SASL nicht verfügbar, wird Rückruf über TLS verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-128">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-129">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-130">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-130">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-131">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-p104">Diese Einstellungen sind zwar sehr flexibel hinsichtlich der angebotenen Aushandlungsmethoden, erfordern aber die Einstellungen des XMPP-Verbundpartners. Wenn für den Partner TLS auf Optional oder Erforderlich festgelegt ist, SASL aber nicht unterstützt wird, ist TLS-Rückruf verfügbar. Wenn für den Partner TLS und SASL auf Optional oder Erforderlich festgelegt sind, wird die optimale Auswahl von TLS über SASL verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-135">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-136">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-137">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-137">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-138">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-p105">In vielen Fällen ist TCP-Rückruf die einzig mögliche Lösung. Das ist zwar weniger optimal als andere Optionen, bietet aber ein bestimmtes Maß an Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="0a2f2-141">Schema der XMPP-Partnerverbund-Aushandlungsmethoden (vollständig)</span><span class="sxs-lookup"><span data-stu-id="0a2f2-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="0a2f2-142">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="0a2f2-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="0a2f2-143">Simple Authentication and Security Layer (SASL)</span><span class="sxs-lookup"><span data-stu-id="0a2f2-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="0a2f2-144">Rückrufauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="0a2f2-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="0a2f2-145">Erwartete Authentifizierungsmethode</span><span class="sxs-lookup"><span data-stu-id="0a2f2-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="0a2f2-146">Anmerkungen, Warnung oder Fehler wegen ungültiger Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0a2f2-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-147">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-147">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-148">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-148">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-149">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-149">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-150">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="0a2f2-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-151">Rückruf funktioniert nicht, wenn sowohl SASL als auch TLS erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-152">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-152">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-153">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-153">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-154">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-154">False</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-155">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="0a2f2-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-156">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-157">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-157">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-158">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-158">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-159">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-p106">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p106">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-162">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-163">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-163">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-164">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-164">False</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-165">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="0a2f2-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-p107">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p107">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-168">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-169">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-169">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-170">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-170">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-171">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-p108">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p108">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-174">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-175">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-175">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-176">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-177">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0a2f2-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-p109">Da SASL TLS erfordert und TLS nicht verfügbar ist, SASL/TLS kann nicht erfolgreich sein. TCP-Rückruf ist auf False festgelegt und kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-180">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-180">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-181">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-182">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-182">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-183">SASL über TLS, TLS-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-184">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-184">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-185">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-186">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-186">False</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-187">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="0a2f2-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-188">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-189">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-190">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-190">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-191">SASL über TLS, TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-p110">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p110">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-194">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-195">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-196">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-196">False</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-197">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="0a2f2-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-p111">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p111">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-200">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-201">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-202">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-202">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-203">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-p112">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p112">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-206">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-207">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-208">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-209">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0a2f2-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-p113">SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-212">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-212">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-213">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-214">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-214">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-215">TLS-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-216">Konfiguration erlaubt TLS-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-217">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0a2f2-217">Required</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-218">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-219">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-219">False</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-220">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0a2f2-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-221">SASL oder Rückruf muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-222">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-223">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-224">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-224">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-225">TLS-Rückruf, TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-226">Je nach den Aushandlungsoptionen am anderen Endpunkt wird TCP- oder TLS-Rückruf akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-227">Optional</span><span class="sxs-lookup"><span data-stu-id="0a2f2-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-228">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-229">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-229">False</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-230">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0a2f2-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-231">SASL oder Rückruf muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a2f2-232">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-233">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-234">Richtig</span><span class="sxs-lookup"><span data-stu-id="0a2f2-234">True</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-235">TCP-Rückruf</span><span class="sxs-lookup"><span data-stu-id="0a2f2-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-236">TCP-Rückruf ist die einzige verfügbare Aushandlungsmethode</span><span class="sxs-lookup"><span data-stu-id="0a2f2-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a2f2-237">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-238">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="0a2f2-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-239">False</span><span class="sxs-lookup"><span data-stu-id="0a2f2-239">False</span></span></p></td>
<td><p><span data-ttu-id="0a2f2-240">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0a2f2-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="0a2f2-241">SASL oder Rückruf muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="0a2f2-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

