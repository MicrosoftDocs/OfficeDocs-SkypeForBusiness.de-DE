---
title: 'Lync Server 2013: VoIP-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a9df9b1caa42d3dc17d2f4f9e0908ed69d5660d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="2b5e7-102">VoIP-Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b5e7-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b5e7-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2b5e7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2b5e7-104">In lync Server *VoIP-Richtlinien* werden für jeden Benutzer, Standort oder jede Organisation, dem die Richtlinie zugewiesen ist, Folgendes definiert:</span><span class="sxs-lookup"><span data-stu-id="2b5e7-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="2b5e7-105">Eine Reihe von Anruffunktionen, die aktiviert oder deaktiviert werden können, um die für Benutzer verfügbare Enterprise-VoIP-Funktionalität zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="2b5e7-106">Einer Gruppe von Telefonfestnetz-Verwendungsdatensätzen, die festlegen, welche Arten von Anrufen erlaubt sind.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="2b5e7-107">Planen der VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="2b5e7-107">Planning for Voice Policies</span></span>

<span data-ttu-id="2b5e7-108">Die folgenden Schritte helfen Ihnen beim Planen der VoIP-Richtlinien, die Sie für Ihre Enterprise-VoIP-Bereitstellung benötigen:</span><span class="sxs-lookup"><span data-stu-id="2b5e7-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="2b5e7-109">Legen Sie fest, wie die globale VoIP-Richtlinie (die Standard-VoIP-Richtlinie, die mit dem Produkt installiert wird), konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="2b5e7-110">Diese Richtlinie gilt für alle Enterprise-VoIP-Benutzer, denen nicht explizit eine Richtlinie auf Standort-oder Benutzerebene zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="2b5e7-111">Bestimmen der ggf. erforderlichen VoIP-Richtlinien auf Standortebene.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="2b5e7-112">Bestimmen der ggf. erforderlichen benutzerbezogenen VoIP-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="2b5e7-113">Entscheiden, welche Anruffunktionen für jede VoIP-Richtlinie aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="2b5e7-114">Bestimmen, welche PSTN-Verwendungsdatensätze für jede VoIP-Richtlinie konfiguriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="2b5e7-115">Gültigkeitsbereich von VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="2b5e7-115">Voice Policy Scope</span></span>

<span data-ttu-id="2b5e7-116">Der *Gültigkeitsbereich von VoIP-Richtlinien* bestimmt die Hierarchieebene, auf der die Richtlinie gelten soll.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="2b5e7-117">In lync Server können Sie VoIP-Richtlinien mit den folgenden Bereichsebenen konfigurieren (aufgeführt aus den am häufigsten verwendeten für die allgemeinsten).</span><span class="sxs-lookup"><span data-stu-id="2b5e7-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="2b5e7-p103">Die **VoIP-Benutzerrichtlinie** kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Dies ist die niedrigste Richtlinienebene. VoIP-Benutzerrichtlinien können bereitgestellt werden, um Funktionen nur für bestimmte Benutzer oder Gruppen an einem Standort zu aktivieren. Sie können damit z. B. bei bestimmten Mitarbeitern Ferngespräche deaktivieren. Damit eine VoIP-Richtlinie zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p103">**User voice policy** can be assigned to individual users, groups, or contact objects. This is the lowest level policy. User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site. For example, you may want to disable long distance dialing for some employees. For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2b5e7-123">Es wird empfohlen, eine Benutzer VoIP-Richtlinie für die Niederlassung von Enterprise-VoIP-Benutzern bereitzustellen, die bei der zentralen Standortbereitstellung registriert sind, oder für Benutzer, die in einem Survivable Branch Appliance registriert sind.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="2b5e7-p104">Eine **VoIP-Standortrichtlinie** gilt für einen gesamten Standort. Ausgenommen sind Benutzer, Gruppen oder Kontaktobjekte, denen eine Benutzerrichtlinie zugeordnet wurde. Zum Definieren einer VoIP-Standortrichtlinie müssen Sie den Standort angeben, für den die Richtlinie gelten soll. Wenn keine VoIP-Benutzerrichtlinie zugewiesen ist, wird die VoIP-Standortrichtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p104">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy. To define a site voice policy, you must specify the site to which the policy applies. If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="2b5e7-127">**Globale VoIP-Richtlinie** ist die standardmäßige VoIP-Richtlinie, die mit dem Produkt installiert wird.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="2b5e7-128">Sie können die globale VoIP-Richtlinie so bearbeiten, dass Sie den spezifischen Anforderungen Ihrer Organisation entspricht, Sie können Sie jedoch nicht umbenennen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="2b5e7-129">Diese VoIP-Richtlinie gilt für alle Enterprise-VoIP-Benutzer,-Gruppen und-Kontaktobjekte in Ihrer Bereitstellung, sofern Sie keine VoIP-Richtlinie mit spezifischeren Bereich konfigurieren und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="2b5e7-130">Wenn Sie diese Richtlinie vollständig deaktivieren möchten, stellen Sie sicher, dass allen Websites und Benutzern benutzerdefinierte Richtlinien zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="2b5e7-131">Anruffunktionen</span><span class="sxs-lookup"><span data-stu-id="2b5e7-131">Call Features</span></span>

<span data-ttu-id="2b5e7-132">Für jede Richtlinie können Sie die folgenden Anruffunktionen aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="2b5e7-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="2b5e7-p106">**Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p106">**Call forwarding** enables users to forward calls to other phones and client devices. Enabled by default.</span></span>

  - <span data-ttu-id="2b5e7-p107">**Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p107">**Delegation** enables users to specify other users to send and receive calls on their behalf. Enabled by default.</span></span>

  - <span data-ttu-id="2b5e7-p108">**Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

  - <span data-ttu-id="2b5e7-p109">**Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p109">**Call park** enables users to park calls and then pick up the call from a different phone or client. Disabled by default.</span></span>

  - <span data-ttu-id="2b5e7-p110">**Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Läuten auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p110">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices. Enabled by default.</span></span>

  - <span data-ttu-id="2b5e7-p111">**Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

  - <span data-ttu-id="2b5e7-p112">**PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p112">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>

  - <span data-ttu-id="2b5e7-p113">**Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht es Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

  - <span data-ttu-id="2b5e7-149">Durch die **Ablaufverfolgung für böswillige** Anrufe können Benutzer böswillige Anrufe über den lync-Client melden und dann solche Anrufe in den Anruf Detaildatensätzen kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="2b5e7-150">Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-150">Disabled by default.</span></span>

  - <span data-ttu-id="2b5e7-151">**Voicemail-Ausweg** verhindert, dass Anrufe sofort an das Voicemail-System des Mobiltelefons des Benutzers weitergeleitet werden, wenn gleichzeitiges Klingeln konfiguriert und das Telefon abgeschaltet, ohne Strom oder außer Reichweite ist und auf einem Timer-Wert basiert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="2b5e7-152">Diese Einstellung aktiviert und deaktiviert den Timer und stellt den Wert des Timers ein.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="2b5e7-153">Sie kann nur mithilfe der lync Server-Verwaltungsshell konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="2b5e7-154">Diese ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-154">Disabled by default.</span></span>

  - <span data-ttu-id="2b5e7-p116">**PSTN-Verwendungen Anrufweiterleitung und Gleichzeitiges Klingeln** ermöglicht Administratoren, bei Anrufweiterleitung und gleichzeitigem Klingeln die gleiche PSTN-Verwendung wie für die VoIP-Richtlinie anzugeben, Anrufweiterleitung und gleichzeitiges Klingeln auf interne Lync-Benutzer zu beschränken oder eine benutzerdefinierte PSTN-Verwendung anzugeben, die sich von der PSTN-Verwendung der VoIP-Richtlinie unterscheidet. Standardmäßig wird für Anrufweiterleitung und gleichzeitiges Klingeln die gleiche PSTN-Verwendung verwendet, wie bei der VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p116">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage. The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="2b5e7-157">PSTN-Verwendungsdatensätze</span><span class="sxs-lookup"><span data-stu-id="2b5e7-157">PSTN Usage Records</span></span>

<span data-ttu-id="2b5e7-158">Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungsdatensatz zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="2b5e7-159">PSTN-Verwendungen können nur zum Zweck von Anrufweiterleitung und gleichzeitigem Klingeln einer VoIP-Richtlinie zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="2b5e7-160">Ausführliche Informationen zum Planen von PSTN-Verwendungsdatensätzen finden Sie unter [PSTN-Verwendungsdaten Sätze in lync Server 2013](lync-server-2013-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="2b5e7-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b5e7-p118">Die Reihenfolge der PSTN-Verwendungsdatensätze ist wichtig, da die Ausgangsroutingfunktion beim Zuordnen von Benutzern zu Routen die PSTN-Verwendungsdatensätze von oben nach unten vergleicht. Wenn der erste Datensatz mit der Anrufroute übereinstimmt, wird diese Route verwendet. Falls nicht, unterstützt die Ausgangsroutingfunktion den nächsten PSTN-Verwendungsdatensatz in der Liste und fährt damit fort, bis eine Übereinstimmung gefunden wird. Die nachfolgenden PSTN-Verwendungsdatensätze dienen der zusätzlichen Absicherung, wenn der erste Datensatz in der Liste nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2b5e7-p118">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom. If the first usage matches the call route, that route is used. If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found. In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

