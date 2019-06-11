---
title: 'Lync Server 2013: Aushandlungseinstellungen für XMPP-Verbundpartner'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="76005-102">Aushandlungseinstellungen für XMPP-Verbundpartner in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76005-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76005-103">_**Letztes Änderungsdatum des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="76005-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="76005-104">Die Einstellungen für die Aushandlungs Typen in der Konfiguration eines XMPP-Partners haben eine Vielzahl möglicher Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="76005-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="76005-105">Nicht alle diese Kombinationen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="76005-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="76005-106">In der in diesem Thema beschriebenen Tabelle werden die gültigen und ungültigen Einstellungen definiert.</span><span class="sxs-lookup"><span data-stu-id="76005-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="76005-107">Allgemeine Konfigurationen werden in der ersten Tabelle dargestellt, der zweiten Tabelle, in der alle möglichen Kombinationen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="76005-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="76005-108">Beachten Sie, dass Sie keine *einfache Authentifizierungs-und Sicherheitsschicht* (SASL) haben können, **es sei denn** , *Transport Layer Security* (TLS) steht ebenfalls zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="76005-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="76005-109">SASL wird in einem unverschlüsselten (lesbaren) Format gesendet und sollte niemals übertragen werden, es sei denn, es wird durch ein anderes Mittel wie TLS geschützt.</span><span class="sxs-lookup"><span data-stu-id="76005-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="76005-110">Allgemeine Methoden zur XMPP-Föderations Verhandlung</span><span class="sxs-lookup"><span data-stu-id="76005-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="76005-111">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="76005-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="76005-112">Einfache Authentifizierungs-und Sicherheitsschicht (SASL)</span><span class="sxs-lookup"><span data-stu-id="76005-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="76005-113">Dialback-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="76005-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="76005-114">Erwartete Authentifizierungsmethode (n)</span><span class="sxs-lookup"><span data-stu-id="76005-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="76005-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76005-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76005-116"> Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-116">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-117">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-117">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-118">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-118">False</span></span></p></td>
<td><p><span data-ttu-id="76005-119">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="76005-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="76005-120">TLS und SASL sind hilfreich, um sicherzustellen, dass der SASL-Nachrichtendatenstrom sicher ist.</span><span class="sxs-lookup"><span data-stu-id="76005-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="76005-121">Dialback ist nicht verfügbar und kann nicht für eine Fallback-Methode verwendet werden, wenn der XMPP-Verbundpartner TLS nicht auf Required oder optional gesetzt hat.</span><span class="sxs-lookup"><span data-stu-id="76005-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-122">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-122">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-123">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-124">True</span><span class="sxs-lookup"><span data-stu-id="76005-124">True</span></span></p></td>
<td><p><span data-ttu-id="76005-125">SASL über TLS, TLS-Dialback, TCP-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="76005-126">Wenn der XMPP-Föderationspartner SASL auf optional oder erforderlich SASL gesetzt hat, wird eine TLS-Anforderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="76005-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="76005-127">Wenn SASL nicht zur Verfügung steht, wird Dialback über TLS verwendet.</span><span class="sxs-lookup"><span data-stu-id="76005-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76005-128">Optional </span><span class="sxs-lookup"><span data-stu-id="76005-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-129">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-130">True</span><span class="sxs-lookup"><span data-stu-id="76005-130">True</span></span></p></td>
<td><p><span data-ttu-id="76005-131">SASL über TLS, TLS-Dialback, TCP-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="76005-132">Obwohl die angebotenen Verhandlungsmethoden sehr flexibel sind, basieren diese Einstellungen auf den Einstellungen des XMPP-Verbundpartners.</span><span class="sxs-lookup"><span data-stu-id="76005-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="76005-133">Wenn der Partner TLS optional oder erforderlich hat, aber SASL nicht unterstützt wird, steht TLS-Dialback zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="76005-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="76005-134">Wenn der Partner TLS und SASL auf optional oder required eingestellt hat, wird die optimale Auswahl von TLS über SASL verwendet.</span><span class="sxs-lookup"><span data-stu-id="76005-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-135">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-136">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-137">True</span><span class="sxs-lookup"><span data-stu-id="76005-137">True</span></span></p></td>
<td><p><span data-ttu-id="76005-138">TCP-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="76005-139">In vielen Fällen ist TCP-Dialback die einzige mögliche Lösung.</span><span class="sxs-lookup"><span data-stu-id="76005-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="76005-140">Weniger wünschenswert als andere Optionen, bietet dies ein gewisses Maß an Vertrauen.</span><span class="sxs-lookup"><span data-stu-id="76005-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="76005-141">XMPP-Verbund-Aushandlungs Methoden-Matrix – abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="76005-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="76005-142">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="76005-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="76005-143">Einfache Authentifizierungs-und Sicherheitsschicht (SASL)</span><span class="sxs-lookup"><span data-stu-id="76005-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="76005-144">Dialback-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="76005-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="76005-145">Erwartete Authentifizierungsmethode</span><span class="sxs-lookup"><span data-stu-id="76005-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="76005-146">Hinweise, Warnung oder Fehler für ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="76005-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76005-147"> Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-147">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-148">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-148">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-149">True</span><span class="sxs-lookup"><span data-stu-id="76005-149">True</span></span></p></td>
<td><p><span data-ttu-id="76005-150">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="76005-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-151">Dialback wird nicht ausgeführt, wenn sowohl SASL als auch TLS erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="76005-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-152"> Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-152">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-153">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-153">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-154">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-154">False</span></span></p></td>
<td><p><span data-ttu-id="76005-155">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="76005-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76005-156">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-157">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-157">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-158">True</span><span class="sxs-lookup"><span data-stu-id="76005-158">True</span></span></p></td>
<td><p><span data-ttu-id="76005-159">SASL über TLS, TLS-Dialback, TCP-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-160">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="76005-160">SASL requires TLS.</span></span> <span data-ttu-id="76005-161">Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="76005-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-162">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-163">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-163">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-164">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-164">False</span></span></p></td>
<td><p><span data-ttu-id="76005-165">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="76005-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-166">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="76005-166">SASL requires TLS.</span></span> <span data-ttu-id="76005-167">Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="76005-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76005-168">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-169">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-169">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-170">True</span><span class="sxs-lookup"><span data-stu-id="76005-170">True</span></span></p></td>
<td><p><span data-ttu-id="76005-171">TCP-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-172">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="76005-172">SASL requires TLS.</span></span> <span data-ttu-id="76005-173">Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="76005-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-174">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-175">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-175">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-176">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-177">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="76005-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-178">Da SASL TLS erfordert und TLS nicht zur Verfügung steht, kann SASL/TLS nicht erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="76005-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="76005-179">TCP Dialback ist auf "false" festgelegt und kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76005-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76005-180">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-180">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-181">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-182">True</span><span class="sxs-lookup"><span data-stu-id="76005-182">True</span></span></p></td>
<td><p><span data-ttu-id="76005-183">SASL über TLS, TLS-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-184">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-184">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-185">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-186">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-186">False</span></span></p></td>
<td><p><span data-ttu-id="76005-187">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="76005-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76005-188">Optional </span><span class="sxs-lookup"><span data-stu-id="76005-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-189">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-190">True</span><span class="sxs-lookup"><span data-stu-id="76005-190">True</span></span></p></td>
<td><p><span data-ttu-id="76005-191">SASL über TLS, TLS-Dialback, TCP-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-192">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="76005-192">SASL requires TLS.</span></span> <span data-ttu-id="76005-193">Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="76005-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-194">Optional </span><span class="sxs-lookup"><span data-stu-id="76005-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-195">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-196">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-196">False</span></span></p></td>
<td><p><span data-ttu-id="76005-197">SASL über TLS</span><span class="sxs-lookup"><span data-stu-id="76005-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-198">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="76005-198">SASL requires TLS.</span></span> <span data-ttu-id="76005-199">Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="76005-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76005-200">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-201">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-202">True</span><span class="sxs-lookup"><span data-stu-id="76005-202">True</span></span></p></td>
<td><p><span data-ttu-id="76005-203">TCP-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-204">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="76005-204">SASL requires TLS.</span></span> <span data-ttu-id="76005-205">Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="76005-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-206">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-207">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-208">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-209">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="76005-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-210">SASL erfordert TLS.</span><span class="sxs-lookup"><span data-stu-id="76005-210">SASL requires TLS.</span></span> <span data-ttu-id="76005-211">Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.</span><span class="sxs-lookup"><span data-stu-id="76005-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76005-212">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-212">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-213">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-214">True</span><span class="sxs-lookup"><span data-stu-id="76005-214">True</span></span></p></td>
<td><p><span data-ttu-id="76005-215">TLS-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="76005-216">Die Konfiguration ermöglicht TLS-Dialback.</span><span class="sxs-lookup"><span data-stu-id="76005-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-217">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="76005-217">Required</span></span></p></td>
<td><p><span data-ttu-id="76005-218">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-219">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-219">False</span></span></p></td>
<td><p><span data-ttu-id="76005-220">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="76005-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-221">SASL oder Dialback muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="76005-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76005-222">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-223">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-224">True</span><span class="sxs-lookup"><span data-stu-id="76005-224">True</span></span></p></td>
<td><p><span data-ttu-id="76005-225">TLS-Dialback, TCP-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="76005-226">Basierend auf den Aushandlungs Optionen des anderen Endpunkts werden TCP-oder TLS-Dialback akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="76005-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-227">Optional</span><span class="sxs-lookup"><span data-stu-id="76005-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="76005-228">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-229">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-229">False</span></span></p></td>
<td><p><span data-ttu-id="76005-230">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="76005-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-231">SASL oder Dialback muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="76005-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76005-232">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-233">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-234">True</span><span class="sxs-lookup"><span data-stu-id="76005-234">True</span></span></p></td>
<td><p><span data-ttu-id="76005-235">TCP-Dialback</span><span class="sxs-lookup"><span data-stu-id="76005-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="76005-236">TCP-Dialback ist die einzige verfügbare Aushandlungsmethode.</span><span class="sxs-lookup"><span data-stu-id="76005-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76005-237">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-238">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="76005-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="76005-239">Falsch</span><span class="sxs-lookup"><span data-stu-id="76005-239">False</span></span></p></td>
<td><p><span data-ttu-id="76005-240">Ungültige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="76005-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="76005-241">SASL oder Dialback muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="76005-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

