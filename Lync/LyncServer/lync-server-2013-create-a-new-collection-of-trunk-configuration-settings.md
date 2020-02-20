---
title: 'Lync Server 2013: Erstellen einer neuen Auflistung von trunkkonfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07e5dc814887a7304a48602e04f48a00137bf8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="9f441-102">Erstellen Sie in lync Server 2013 eine neue Auflistung von trunkkonfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9f441-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f441-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9f441-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9f441-p101">Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="9f441-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="9f441-106">Ob die Medienumgebung für Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f441-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="9f441-107">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f441-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="9f441-108">Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9f441-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="9f441-109">Wenn Sie Microsoft lync Server 2013 installieren, wird eine globale Sammlung von SIP-trunkkonfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="9f441-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="9f441-110">Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).</span><span class="sxs-lookup"><span data-stu-id="9f441-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="9f441-111">Wenn Sie SIP-Trunk-Konfigurationseinstellungen mit lync Server-Systemsteuerung erstellen, stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="9f441-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f441-112">UI-Einstellung</span><span class="sxs-lookup"><span data-stu-id="9f441-112">UI Setting</span></span></th>
<th><span data-ttu-id="9f441-113">PowerShell-Parameter</span><span class="sxs-lookup"><span data-stu-id="9f441-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="9f441-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f441-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f441-115">Name</span><span class="sxs-lookup"><span data-stu-id="9f441-115">Name</span></span></p></td>
<td><p><span data-ttu-id="9f441-116">Identität</span><span class="sxs-lookup"><span data-stu-id="9f441-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="9f441-p103">Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung an Trunkkonfigurationseinstellungen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="9f441-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f441-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f441-119">Description</span></span></p></td>
<td><p><span data-ttu-id="9f441-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f441-120">Description</span></span></p></td>
<td><p><span data-ttu-id="9f441-121">Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).</span><span class="sxs-lookup"><span data-stu-id="9f441-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f441-122">Maximal unterstützte frühe Dialoge</span><span class="sxs-lookup"><span data-stu-id="9f441-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="9f441-123">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="9f441-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="9f441-124">Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="9f441-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f441-125">Unterstützte Verschlüsselungsstufe</span><span class="sxs-lookup"><span data-stu-id="9f441-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="9f441-126">"Srtpmode"</span><span class="sxs-lookup"><span data-stu-id="9f441-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="9f441-127">Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest.</span><span class="sxs-lookup"><span data-stu-id="9f441-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="9f441-128">Bei der Medienumgehung muss dieser Wert mit der Einstellung "EncryptionLevel" in der Medienkonfiguration kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="9f441-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="9f441-129">Die Medienkonfiguration wird mithilfe der Cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> und <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">setCsMediaConfiguration</a> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9f441-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="9f441-130">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9f441-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f441-131">Required: Die SRTP-Verschlüsselung muss verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f441-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="9f441-132">Optional: SRTP wird verwendet, wenn es vom Gateway unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9f441-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="9f441-133">Not Supported: Die SRTP-Verschlüsselung wird nicht unterstützt und daher auch nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f441-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="9f441-p105">"SRTPMode" wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird "SRTPMode" intern auf "Not Supported" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9f441-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f441-136">Support melden</span><span class="sxs-lookup"><span data-stu-id="9f441-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="9f441-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="9f441-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="9f441-138">"Enablerefersupport"</span><span class="sxs-lookup"><span data-stu-id="9f441-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="9f441-139">Mit der Einstellung <strong>Refer-Anforderungen an das Gateway senden</strong> unterstützt der Trunk den Empfang von Refer-Anforderungen vom Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="9f441-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="9f441-140">Mit der Einstellung <strong>Refer-Anforderungen mit 3pcc senden</strong> kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können.</span><span class="sxs-lookup"><span data-stu-id="9f441-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="9f441-141">3PCC wird auch als &quot;Drittanbieter-Steuerelement&quot; bezeichnet und tritt auf, wenn ein Drittanbieter verwendet wird, um ein paar von Anrufern zu verbinden (beispielsweise ein Operator, der einen Anruf von Person a an Person B abruft).</span><span class="sxs-lookup"><span data-stu-id="9f441-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f441-142">Medienumgehung aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f441-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="9f441-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="9f441-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="9f441-p107">Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch <strong>Zentrale Medienverarbeitung</strong> aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9f441-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f441-146">Zentrale Medienverarbeitung</span><span class="sxs-lookup"><span data-stu-id="9f441-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="9f441-147">"Concentratedtopology"</span><span class="sxs-lookup"><span data-stu-id="9f441-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="9f441-p108">Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt die gleiche IP-Adresse hat wie der Signaldatenverkehr-Endpunkt.)</span><span class="sxs-lookup"><span data-stu-id="9f441-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f441-150">RTP-Latching aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f441-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="9f441-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="9f441-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="9f441-p109">Gibt an, ob SIP-Trunks RTP-Latching unterstützen oder nicht. RTP-Latching ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9f441-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f441-154">Weiterleiten der Anrufliste aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f441-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="9f441-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="9f441-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="9f441-156">Gibt an, ob Informationen zum Anruferverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9f441-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f441-157">Weiterleiten von P-Asserted-Identity-Daten aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f441-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="9f441-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="9f441-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="9f441-p110">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9f441-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f441-161">Timer für Ausgangsroutingfailover aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f441-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="9f441-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="9f441-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="9f441-p111">Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gateway-Reaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f441-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f441-165">Zugeordnete PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="9f441-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="9f441-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="9f441-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="9f441-167">Eine Sammlung von dem Trunk zugewiesenen PSTN-Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="9f441-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f441-168">Übersetzte Nummer zum Testen</span><span class="sxs-lookup"><span data-stu-id="9f441-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="9f441-169">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9f441-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="9f441-170">Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f441-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f441-171">Zugehörige Übersetzungsregeln</span><span class="sxs-lookup"><span data-stu-id="9f441-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="9f441-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="9f441-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="9f441-173">Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).</span><span class="sxs-lookup"><span data-stu-id="9f441-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f441-174">Übersetzungsregeln für angerufene Nummern</span><span class="sxs-lookup"><span data-stu-id="9f441-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="9f441-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="9f441-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="9f441-176">Sammlung an Regeln für die Nummernübersetzung für ausgehende Anrufe, die dem Trunk zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="9f441-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f441-177">Testtelefonnummer</span><span class="sxs-lookup"><span data-stu-id="9f441-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="9f441-178">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9f441-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="9f441-179">Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f441-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f441-180">Anrufende Nummer</span><span class="sxs-lookup"><span data-stu-id="9f441-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="9f441-181">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9f441-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="9f441-182">Gibt an, dass die zu testende Telefonnummer die Telefonnummer des Anrufers ist.</span><span class="sxs-lookup"><span data-stu-id="9f441-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f441-183">Angerufene Nummer</span><span class="sxs-lookup"><span data-stu-id="9f441-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="9f441-184">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9f441-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="9f441-185">Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9f441-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="9f441-186">Die lync Server CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die nicht in lync Server-Systemsteuerung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9f441-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="9f441-187">Weitere Informationen finden Sie im Hilfethema zum <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration-</A> Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9f441-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="9f441-188">So erstellen Sie neue trunkkonfigurationseinstellungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="9f441-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9f441-189">Klicken Sie in lync Server-Systemsteuerung auf **VoIP-Routing**, und klicken Sie dann auf **trunk Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9f441-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="9f441-190">Klicken Sie auf der Registerkarte **Trunkkonfiguration** auf **Neu** und dann auf **Standorttrunk**, um die neuen Einstellungen auf Standortebene zu erstellen, oder klicken Sie auf **Pooltrunk**, um die neuen Einstellungen auf Dienstebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f441-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="9f441-p113">Wählen Sie im Dialogfeld **Standort auswählen** oder im Dialogfeld **Dienst auswählen** (das angezeigte Dialogfeld ist abhängig davon, ob Sie Einstellungen auf Standort- oder auf Dienstebene vornehmen) den Standort für die neuen Konfigurationseinstellungen aus, und klicken Sie auf **OK**. Wenn das Dialogfeld leer ist, können Sie keine neuen Einstellungen erstellen. Wenn beispielsweise das Dialogfeld **Standort auswählen** leer ist, bedeutet dies, dass allen Standorten bereits eine Sammlung von Trunkkonfigurationsstandorten zugewiesen wurde. An jedem Standort (und in jedem Dienst) kann jedoch nur eine solche Sammlung gehostet werden. In diesem Fall können Sie die bestehende Sammlung löschen und eine neue erstellen, oder Sie können die bestehende Sammlung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9f441-p113">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**. If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection. In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="9f441-194">Nehmen Sie im Dialogfeld **Neue Trunkkonfiguration** die gewünschten Einstellungen vor, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f441-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="9f441-p114">Die Eigenschaft **Zustand** für die Sammlung wird aktualisiert und lautet jetzt **Ohne Commit**. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit** und dann auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="9f441-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="9f441-197">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f441-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="9f441-198">Klicken Sie im Dialogfeld **Microsoft Lync Server 2013-Systemsteuerung** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f441-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

