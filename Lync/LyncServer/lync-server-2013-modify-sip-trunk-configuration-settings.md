---
title: 'Lync Server 2013: Ändern von SIP-Trunk-Konfigurationseinstellungen'
description: 'Lync Server 2013: Ändern Sie die SIP-Trunk-Konfigurationseinstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42cb213211a11494a96b5a762734a2b5db49dfbb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562141"
---
# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c3610-103">Ändern von SIP-Trunk-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3610-103">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3610-104">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c3610-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c3610-p101">Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="c3610-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="c3610-107">Ob die Medienumgebung für Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3610-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="c3610-108">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3610-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="c3610-109">Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c3610-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="c3610-110">Wenn Sie Microsoft lync Server 2013 installieren, wird eine globale Sammlung von SIP-trunkkonfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="c3610-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="c3610-111">Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).</span><span class="sxs-lookup"><span data-stu-id="c3610-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="c3610-112">Jede dieser Auflistungen kann später mit lync Server-Systemsteuerung oder Windows PowerShell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c3610-112">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="c3610-113">Wenn Sie SIP-Trunk-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung ändern, stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c3610-113">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3610-114">UI-Einstellung</span><span class="sxs-lookup"><span data-stu-id="c3610-114">UI Setting</span></span></th>
<th><span data-ttu-id="c3610-115">PowerShell-Parameter</span><span class="sxs-lookup"><span data-stu-id="c3610-115">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="c3610-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3610-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3610-117">Name</span><span class="sxs-lookup"><span data-stu-id="c3610-117">Name</span></span></p></td>
<td><p><span data-ttu-id="c3610-118">Identität</span><span class="sxs-lookup"><span data-stu-id="c3610-118">Identity</span></span></p></td>
<td><p><span data-ttu-id="c3610-p103">Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung an Trunkkonfigurationseinstellungen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c3610-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3610-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3610-121">Description</span></span></p></td>
<td><p><span data-ttu-id="c3610-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3610-122">Description</span></span></p></td>
<td><p><span data-ttu-id="c3610-123">Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).</span><span class="sxs-lookup"><span data-stu-id="c3610-123">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3610-124">Maximal unterstützte frühe Dialoge</span><span class="sxs-lookup"><span data-stu-id="c3610-124">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="c3610-125">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="c3610-125">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="c3610-126">Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="c3610-126">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3610-127">Unterstützte Verschlüsselungsstufe</span><span class="sxs-lookup"><span data-stu-id="c3610-127">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="c3610-128">"Srtpmode"</span><span class="sxs-lookup"><span data-stu-id="c3610-128">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="c3610-129">Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest.</span><span class="sxs-lookup"><span data-stu-id="c3610-129">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="c3610-130">Bei der Medienumgehung muss dieser Wert mit der Einstellung "EncryptionLevel" in der Medienkonfiguration kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="c3610-130">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="c3610-131">Die Medienkonfiguration wird mithilfe der Cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> und <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">setCsMediaConfiguration</a> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c3610-131">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="c3610-132">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c3610-132">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c3610-133">Required: Die SRTP-Verschlüsselung muss verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3610-133">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="c3610-134">Optional: SRTP wird verwendet, wenn es vom Gateway unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="c3610-134">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="c3610-135">Not Supported: Die SRTP-Verschlüsselung wird nicht unterstützt und daher auch nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3610-135">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="c3610-p105">"SRTPMode" wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird "SRTPMode" intern auf "Not Supported" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c3610-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3610-138">Support melden</span><span class="sxs-lookup"><span data-stu-id="c3610-138">Refer support</span></span></p></td>
<td><p><span data-ttu-id="c3610-139">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="c3610-139">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="c3610-140">"Enablerefersupport"</span><span class="sxs-lookup"><span data-stu-id="c3610-140">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="c3610-141">Mit der Einstellung <strong>Refer-Anforderungen an das Gateway senden</strong> unterstützt der Trunk den Empfang von Refer-Anforderungen vom Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="c3610-141">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="c3610-142">Mit der Einstellung <strong>Refer-Anforderungen mit 3pcc senden</strong> kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können.</span><span class="sxs-lookup"><span data-stu-id="c3610-142">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="c3610-143">3PCC wird auch als &quot; Drittanbieter-Steuerelement bezeichnet &quot; und tritt auf, wenn ein Drittanbieter verwendet wird, um ein paar von Anrufern zu verbinden (beispielsweise ein Operator, der einen Anruf von Person a an Person B abruft).</span><span class="sxs-lookup"><span data-stu-id="c3610-143">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3610-144">Medienumgehung aktivieren</span><span class="sxs-lookup"><span data-stu-id="c3610-144">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="c3610-145">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="c3610-145">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="c3610-p107">Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch <strong>Zentrale Medienverarbeitung</strong> aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c3610-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3610-148">Zentrale Medienverarbeitung</span><span class="sxs-lookup"><span data-stu-id="c3610-148">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="c3610-149">"Concentratedtopology"</span><span class="sxs-lookup"><span data-stu-id="c3610-149">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="c3610-p108">Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt die gleiche IP-Adresse hat wie der Signaldatenverkehr-Endpunkt.)</span><span class="sxs-lookup"><span data-stu-id="c3610-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3610-152">RTP-Latching aktivieren</span><span class="sxs-lookup"><span data-stu-id="c3610-152">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="c3610-153">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="c3610-153">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="c3610-p109">Gibt an, ob SIP-Trunks RTP-Latching unterstützen oder nicht. RTP-Latching ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c3610-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3610-156">Weiterleiten der Anrufliste aktivieren</span><span class="sxs-lookup"><span data-stu-id="c3610-156">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="c3610-157">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="c3610-157">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="c3610-158">Gibt an, ob Informationen zum Anruferverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c3610-158">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3610-159">Weiterleiten von P-Asserted-Identity-Daten aktivieren</span><span class="sxs-lookup"><span data-stu-id="c3610-159">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="c3610-160">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="c3610-160">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="c3610-p110">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c3610-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3610-163">Timer für Ausgangsroutingfailover aktivieren</span><span class="sxs-lookup"><span data-stu-id="c3610-163">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="c3610-164">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="c3610-164">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="c3610-p111">Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gateway-Reaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3610-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3610-167">Zugeordnete PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="c3610-167">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="c3610-168">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="c3610-168">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="c3610-169">Eine Sammlung von dem Trunk zugewiesenen PSTN-Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="c3610-169">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3610-170">Übersetzte Nummer zum Testen</span><span class="sxs-lookup"><span data-stu-id="c3610-170">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="c3610-171">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c3610-171">N/A</span></span></p></td>
<td><p><span data-ttu-id="c3610-172">Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c3610-172">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3610-173">Zugehörige Übersetzungsregeln</span><span class="sxs-lookup"><span data-stu-id="c3610-173">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="c3610-174">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="c3610-174">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="c3610-175">Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).</span><span class="sxs-lookup"><span data-stu-id="c3610-175">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3610-176">Übersetzungsregeln für angerufene Nummern</span><span class="sxs-lookup"><span data-stu-id="c3610-176">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="c3610-177">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="c3610-177">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="c3610-178">Sammlung an Regeln für die Nummernübersetzung für ausgehende Anrufe, die dem Trunk zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="c3610-178">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3610-179">Testtelefonnummer</span><span class="sxs-lookup"><span data-stu-id="c3610-179">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="c3610-180">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c3610-180">N/A</span></span></p></td>
<td><p><span data-ttu-id="c3610-181">Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c3610-181">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3610-182">Anrufende Nummer</span><span class="sxs-lookup"><span data-stu-id="c3610-182">Calling number</span></span></p></td>
<td><p><span data-ttu-id="c3610-183">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c3610-183">N/A</span></span></p></td>
<td><p><span data-ttu-id="c3610-184">Gibt an, dass die zu testende Telefonnummer die Telefonnummer des Anrufers ist.</span><span class="sxs-lookup"><span data-stu-id="c3610-184">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3610-185">Angerufene Nummer</span><span class="sxs-lookup"><span data-stu-id="c3610-185">Called number</span></span></p></td>
<td><p><span data-ttu-id="c3610-186">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c3610-186">N/A</span></span></p></td>
<td><p><span data-ttu-id="c3610-187">Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c3610-187">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c3610-188">Die lync Server CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die nicht in lync Server-Systemsteuerung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c3610-188">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="c3610-189">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">CsTrunkConfiguration</A> ".</span><span class="sxs-lookup"><span data-stu-id="c3610-189">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="c3610-190">So ändern Sie die SIP-Trunk-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="c3610-190">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c3610-191">Klicken Sie in lync Server-Systemsteuerung auf **VoIP-Routing**, und klicken Sie dann auf **trunk Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c3610-191">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="c3610-p113">Doppelklicken Sie auf der Registerkarte **Trunkkonfiguration** auf die Trunkkonfigurationseinstellungen, die Sie ändern möchten. Beachten Sie, dass Sie immer nur eine Einstellung bearbeiten können. Wenn Sie die gleichen Änderungen an mehreren Sammlungen vornehmen möchten, verwenden Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3610-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="c3610-195">Nehmen Sie im Dialogfeld **trunk Konfiguration bearbeiten** die entsprechenden Optionen vor, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3610-195">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="c3610-p114">Die Eigenschaft **State** für die Auflistung wird in **Commit nicht ausgeführt** aktualisiert. Um für die Änderungen ein Commit auszuführen und die Auflistung zu löschen, klicken Sie auf **Commit ausführen**, und klicken Sie dann auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c3610-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="c3610-198">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3610-198">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="c3610-199">Klicken Sie im Dialogfeld **Microsoft Lync Server 2013-Systemsteuerung** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3610-199">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

