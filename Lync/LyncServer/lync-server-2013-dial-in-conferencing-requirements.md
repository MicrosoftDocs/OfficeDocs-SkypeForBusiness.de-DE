---
title: Lync Server 2013 Anforderungen für Einwahlkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80ab9db6b565530db211db8aa47e2e00cbd9cf2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="e3b19-102">Anforderungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3b19-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3b19-103">_**Letztes Änderungsstand des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="e3b19-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="e3b19-104">Bevor Sie mit dem lync Server 2013 Bereitstellungsprozess beginnen, müssen Sie Folgendes planen:</span><span class="sxs-lookup"><span data-stu-id="e3b19-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="e3b19-105">Die für die Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) zu verwendende Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e3b19-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="e3b19-106">Ihre Strategie für die Zuweisung von Regionen für Einwahlkonferenzen zu Einwahlnummern</span><span class="sxs-lookup"><span data-stu-id="e3b19-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="e3b19-107">Ihre Strategie für die Erstellung von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="e3b19-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="e3b19-108">Planen der Einwahl-PSTN-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="e3b19-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="e3b19-109">Einwahlkonferenzen erfordern mindestens eine Vermittlungsserver und mindestens ein PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="e3b19-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="e3b19-110">Sie können eine Vermittlungsserver an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="e3b19-111">An einem zentralen Standort können Sie ein Vermittlungsserver auf einem Front-End-Pool oder Standard Edition-Server collocate oder auf einem eigenständigen Server oder Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="e3b19-112">In einem Zweigstellenstandort können Sie eine Vermittlungsserver auf einem eigenständigen Server oder als Komponente des Survivable Branch Appliance bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="e3b19-113">Sie können ein PSTN-Gateway an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="e3b19-114">An einem Zweigstellenstandort kann das PSTN-Gateway eigenständig oder eine Komponente des Survivable Branch Appliance sein.</span><span class="sxs-lookup"><span data-stu-id="e3b19-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3b19-115">Bei Einwahlkonferenzen wird die medienumgehung nicht verwendet, da A/V-Konferenzserver keine medienumgehung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="e3b19-116">Ausführliche Informationen zum Planen der Konfiguration für Vermittlungsserver-und PSTN-Gateways für Einwahlkonferenzen finden Sie unter [Components and Topologies for Vermittlungsserver in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e3b19-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="e3b19-117">Planen von Regionen für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="e3b19-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="e3b19-p103">Während der Einwahlkonfiguration erstellen Sie Wähleinstellungen und Zugriffsnummern für Einwahlkonferenzen. Wähleinstellungen sind Sätze von Normalisierungsregeln, in welchen die Anzahl und das Muster von Ziffern in einer Telefonnummern festgelegt wird und die die Telefonnummer in das Standard-E.164-Format zur Anrufweiterleitung übersetzen. Zugriffsnummern für Einwahlkonferenzen sind die Nummern, die Benutzer zur Teilnahme an Konferenzen wählen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-p103">During dial-in configuration, you create dial plans and dial-in conferencing access numbers. Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing. Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="e3b19-p104">Jede Zugriffsnummer für Einwahlkonferenzen muss mindestens einem Satz mit Wähleinstellungen zugeordnet sein. Regionen für Einwahlkonferenzen ordnen eine Zugriffsnummer für Einwahlkonferenzen den entsprechenden Wähleinstellungen zu. Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-p104">Every dial-in conferencing access number must be associated with at least one dial plan. Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans. When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="e3b19-p105">Beim Erstellen von Wähleinstellungen geben Sie den Gültigkeitsbereich der Wähleinstellungen an: Benutzer, Pool oder Standort. Jedem Benutzer werden die Wähleinstellungen aus dem am engsten gefassten Gültigkeitsbereich zugeordnet, der für den Benutzer gilt. Beispielsweise werden dem Benutzer Wähleinstellungen auf Benutzerebene zugewiesen, falls solche gelten. Gelten keine Wähleinstellungen auf Benutzerebene, werden dem Benutzer Wähleinstellungen auf Poolebene zugewiesen. Gelten keine Wähleinstellungen auf Poolebene, werden dem Benutzer Wähleinstellungen auf Standortebene zugewiesen. Gelten keine Wähleinstellungen auf Standortebene, werden dem Benutzer die globalen Wähleinstellungen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-p105">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope. Every user is assigned the dial plan from the narrowest scope that applies to the user. For example, a user is assigned a user-level dial plan, if one applies. If a user-level dial plan does not apply, the user is assigned a pool-level dial plan. If a pool-level dial plan does not apply, the user is assigned a site-level dial plan. If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="e3b19-p106">Bevor Sie die Wähleinstellungen konfigurieren, ist es wichtig zu planen, wie die Regionen benannt und verwendet werden sollen. Für die Regionen von Einwahlkonferenzen gelten folgende Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="e3b19-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="e3b19-133">Eine Region ist in der Regel ein geografischer Bereich, der einem Büro oder einer Gruppe von Büros zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e3b19-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="e3b19-p107">Den Einwahlnummern werden Sprachen zugeordnet. Wenn Sie geografische Bereiche mit mehreren Sprachen unterstützen, sollten Sie entscheiden, wie die Regionen für die Unterstützung der verschiedenen Sprachen definiert werden sollen. Beispielsweise können Sie mehrere Regionen basierend auf einer Kombination aus Geografie und Sprache definieren, oder Sie können eine einzige Region basierend auf der Geografie definieren und für jede Sprache eine eigene Einwahlnummer verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3b19-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="e3b19-137">Wenn ein Benutzer eine Besprechung plant, wird für die Besprechung standardmäßig die Region verwendet, die durch die Wähleinstellungen des Benutzers festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e3b19-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="e3b19-138">Standardmäßig sind in der Besprechungseinladung alle Einwahlnummern für die Region enthalten.</span><span class="sxs-lookup"><span data-stu-id="e3b19-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="e3b19-139">Regionen müssen unbedingt so benannt werden, dass sie klar erkennbar sind.</span><span class="sxs-lookup"><span data-stu-id="e3b19-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="e3b19-140">Der Benutzer kann anhand der Regionsnamen die Region einer Besprechung ändern, damit in der Einladung andere Zugriffsnummern enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e3b19-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="e3b19-141">(Wenn Benutzer Outlook verwenden, um eine Besprechung zu planen, verwendet der Benutzer das Online-Besprechungs-Add-in für lync 2013, um die Region zu ändern).</span><span class="sxs-lookup"><span data-stu-id="e3b19-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="e3b19-142">Regionen sollten so konzipiert werden, dass jedem eingeladenen Benutzer, der sich in eine Konferenz einwählen möchte, eine lokale Zugriffsnummer in der Konferenzeinladung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e3b19-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="e3b19-143">Sie können die Reihenfolge konfigurieren, in der Zugriffsnummern in einem Bereich in der Seite "Einstellungen für Einwahlkonferenzen" (und daher in der Reihenfolge, in der Sie in der Konferenzeinladung angezeigt werden) mithilfe von lync Server-Verwaltungsshell-Cmdlets angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e3b19-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="e3b19-144">Jeder Benutzer kann an jedem beliebigen Standort eine beliebige Einwahlnummer wählen, um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="e3b19-145">Planen von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="e3b19-145">Planning for Conference Directories</span></span>

<span data-ttu-id="e3b19-146">Konferenzverzeichnisse verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer für die Teilnahme an einer Konferenz bei Verwendung von lync 2013 verwendet, und der numerischen Konferenz-ID, die ein Teilnehmer für Einwahlkonferenzen verwendet, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="e3b19-147">Das Format der Konferenz-ID lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="e3b19-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="e3b19-p110">Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Wenn diese Richtlinie eingehalten wird, bleiben die Konferenz-IDs in der Regel kurz. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) neun übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e3b19-p110">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created. In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3b19-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3b19-152">See Also</span></span>


[<span data-ttu-id="e3b19-153">Vermittlungsserver Komponente in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3b19-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="e3b19-154">Wählpläne und Normalisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3b19-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

