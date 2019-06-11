---
title: Voraussetzungen für Einwahlkonferenzen in lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="b0162-102">Anforderungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0162-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0162-103">_**Letztes Änderungsdatum des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="b0162-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="b0162-104">Bevor Sie den lync Server 2013-Bereitstellungsprozess starten, müssen Sie Folgendes planen:</span><span class="sxs-lookup"><span data-stu-id="b0162-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="b0162-105">Die Konfiguration, die zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="b0162-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="b0162-106">Ihre Strategie für das Zuweisen von Einwahlkonferenz Regionen zu Einwahl Zugriffsnummern</span><span class="sxs-lookup"><span data-stu-id="b0162-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="b0162-107">Ihre Strategie zum Erstellen von Konferenz Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="b0162-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="b0162-108">Planen der Einwahl PSTN-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="b0162-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="b0162-109">Für Einwahlkonferenzen ist mindestens ein Vermittlungs Server und mindestens ein PSTN-Gateway erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b0162-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="b0162-110">Sie können einen Vermittlungsserver an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b0162-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="b0162-111">An einem zentralen Standort kann ein Vermittlungsserver in einem Front-End-Pool oder auf einem Standard Edition-Server ausgeführt oder auf einem eigenständigen Server oder in einem eigenständigen Pool bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b0162-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="b0162-112">An einem Zweigstellenstandort können Sie einen Vermittlungsserver auf einem eigenständigen Server oder als Komponente der Survivable Branch Appliance bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b0162-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="b0162-p102">Sie können ein PSTN-Gateway an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem Zweigstellenstandort kann das PSTN-Gateway eigenständig oder als Komponente der Survivable Branch Appliance eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b0162-p102">You can deploy a PSTN gateway in a central site or in a branch site. In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0162-115">Einwahlkonferenzen verwenden keine medienumgehung, da ein/V-Konferenz Server keine medienumgehung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b0162-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="b0162-116">Ausführliche Informationen zum Planen Ihrer Konfiguration für den Vermittlungsserver und für PSTN-Gateways für Einwahlkonferenzen finden Sie unter [Komponenten und Topologien für den Vermittlungsserver in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b0162-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="b0162-117">Planen von Einwahlkonferenz Regionen</span><span class="sxs-lookup"><span data-stu-id="b0162-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="b0162-118">Während der Einwahl Konfiguration erstellen Sie Wählpläne und Zugriffsnummern für Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="b0162-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="b0162-119">Wählpläne sind Sätze von Normalisierungsregeln, die die Anzahl und das Muster von Ziffern in einer Telefonnummer angeben und die Telefonnummer in das standardmäßige E. 164-Format für das Anrufrouting übersetzen.</span><span class="sxs-lookup"><span data-stu-id="b0162-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="b0162-120">Zugriffsnummern für Einwahlkonferenzen sind die Nummern, die Benutzer zur Teilnahme an Konferenzen wählen.</span><span class="sxs-lookup"><span data-stu-id="b0162-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="b0162-121">Jede Zugriffsnummer für Einwahlkonferenzen muss mindestens einem Satz mit Wähleinstellungen zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="b0162-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="b0162-122">In den Regionen für Einwahlkonferenzen wird eine Zugriffsnummer für Einwahlkonferenzen mit ihren Wählplänen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="b0162-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="b0162-123">Wenn Sie einen Wählplan einrichten, geben Sie den Bereich für Einwahlkonferenzen an, der für die Wähleinstellungen gilt.</span><span class="sxs-lookup"><span data-stu-id="b0162-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="b0162-124">Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b0162-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="b0162-125">Wenn Sie einen Wählplan erstellen, geben Sie den Bereich des Wählplans an: Benutzerbereich, Poolbereich oder Website Bereich.</span><span class="sxs-lookup"><span data-stu-id="b0162-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="b0162-126">Jedem Benutzer werden die Wähleinstellungen aus dem am engsten gefassten Gültigkeitsbereich zugeordnet, der für den Benutzer gilt.</span><span class="sxs-lookup"><span data-stu-id="b0162-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="b0162-127">Beispielsweise werden dem Benutzer Wähleinstellungen auf Benutzerebene zugewiesen, falls solche gelten.</span><span class="sxs-lookup"><span data-stu-id="b0162-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="b0162-128">Gelten keine Wähleinstellungen auf Benutzerebene, werden dem Benutzer Wähleinstellungen auf Poolebene zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b0162-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="b0162-129">Gelten keine Wähleinstellungen auf Poolebene, werden dem Benutzer Wähleinstellungen auf Standortebene zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b0162-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="b0162-130">Gelten keine Wähleinstellungen auf Standortebene, werden dem Benutzer die globalen Wähleinstellungen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b0162-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="b0162-p106">Bevor Sie die Wähleinstellungen konfigurieren, ist es wichtig zu planen, wie die Regionen benannt und verwendet werden sollen. Für die Regionen von Einwahlkonferenzen gelten folgende Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="b0162-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="b0162-133">Eine Region ist in der Regel ein geografischer Bereich, der einem Büro oder einer Gruppe von Büros zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="b0162-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="b0162-p107">Den Einwahlnummern werden Sprachen zugeordnet. Wenn Sie geografische Bereiche mit mehreren Sprachen unterstützen, sollten Sie entscheiden, wie die Regionen für die Unterstützung der verschiedenen Sprachen definiert werden sollen. Beispielsweise können Sie mehrere Regionen basierend auf einer Kombination aus Geografie und Sprache definieren, oder Sie können eine einzige Region basierend auf der Geografie definieren und für jede Sprache eine eigene Einwahlnummer verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0162-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="b0162-137">Wenn ein Benutzer eine Besprechung plant, wird für die Besprechung standardmäßig die Region verwendet, die durch die Wähleinstellungen des Benutzers festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b0162-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="b0162-138">Standardmäßig sind alle Einwahl Zugriffsnummern für den Bereich in der Besprechungseinladung enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0162-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="b0162-139">Regionen müssen unbedingt so benannt werden, dass sie klar erkennbar sind.</span><span class="sxs-lookup"><span data-stu-id="b0162-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="b0162-140">Der Benutzer kann anhand der Regionsnamen die Region einer Besprechung ändern, damit in der Einladung andere Zugriffsnummern enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b0162-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="b0162-141">(Wenn Benutzer Outlook zum Planen einer Besprechung verwenden, verwendet der Benutzer das Online Besprechungs-Add-in für lync 2013, um den Bereich zu ändern).</span><span class="sxs-lookup"><span data-stu-id="b0162-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="b0162-142">Regionen sollten so konzipiert werden, dass jedem eingeladenen Benutzer, der sich in eine Konferenz einwählen möchte, eine lokale Zugriffsnummer in der Konferenzeinladung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b0162-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="b0162-143">Sie können die Reihenfolge konfigurieren, in der Zugriffsnummern in einem Bereich auf der Seite Einstellungen für Einwahlkonferenzen angezeigt werden (und daher die Reihenfolge, in der Sie in der Konferenzeinladung angezeigt werden), mithilfe der lync Server-Verwaltungsshell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b0162-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="b0162-144">Jeder Benutzer kann an jedem beliebigen Standort eine beliebige Einwahlnummer wählen, um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b0162-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="b0162-145">Planen von Konferenz Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="b0162-145">Planning for Conference Directories</span></span>

<span data-ttu-id="b0162-146">Konferenzverzeichnisse verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer für die Teilnahme an einer Konferenz bei Verwendung von lync 2013 verwendet, und der numerischen Konferenz-ID, die ein Teilnehmer für Einwahlkonferenzen verwendet, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b0162-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="b0162-147">Das Format der Konferenz-ID lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="b0162-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="b0162-148">Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b0162-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="b0162-149">Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0162-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="b0162-150">Mit dieser Richtlinie können die Konferenz-IDs in der Regel klein gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="b0162-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="b0162-151">Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) 9 übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b0162-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0162-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0162-152">See Also</span></span>


[<span data-ttu-id="b0162-153">Vermittlungsserver Komponente in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0162-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="b0162-154">Wählpläne und Normalisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0162-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

