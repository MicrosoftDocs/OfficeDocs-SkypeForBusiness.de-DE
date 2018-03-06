---
title: Aktivieren von Teams Seite an Seite mit Skype for Business
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Anleitung zur gleichzeitigen Verwendung von Skype for Business und Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3052c406675ac8f8423469783c9831c84b3e0e05
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a><span data-ttu-id="3a72d-103">Aktivieren von Teams Seite an Seite mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3a72d-103">Enable Microsoft Teams side-by-side with Skype for Business</span></span> 
=============================================================

<span data-ttu-id="3a72d-104">Für Organisationen mit vorhandenen Bereitstellungen von Skype for Business Online stellt die kürzliche Einführung von Microsoft Teams eine Möglichkeit dar, das Potenzial von Teams als eigenständige Lösung für Kommunikation und Zusammenarbeit zu bewerten. Des Weiteren stellt sie eine Herausforderung dar, die beiden Lösungen gegenüber zu stellen und zu ermitteln, ob sie in Ihrer Umgebung koexistieren können.</span><span class="sxs-lookup"><span data-stu-id="3a72d-104">For organizations with existing deployments of Skype for Business Online, the recent introduction of Microsoft Teams presents an opportunity to evaluate the potential of Teams as a sole, communications and collaboration solution, and a challenge to tip the scale between the two solutions and how they can coexist in your environment.</span></span>

<span data-ttu-id="3a72d-105">Wenn Teams Ihre heutigen Geschäftsanforderungen erfüllen kann, können Sie mit der Übernahme von Teams als alleinige Lösung für Kommunikation und Zusammenarbeit in Ihrer Organisation beginnen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-105">If Teams can meet your business requirements today, you can start adopting Teams to become your single communications and collaboration solution for your organization.</span></span>

<span data-ttu-id="3a72d-106">Teams ist standardmäßig auf allen berechtigten Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3a72d-106">Teams is enabled by default, on all eligible tenants.</span></span> <span data-ttu-id="3a72d-107">Aus diesem Grund müssen Sie entscheiden, wie Sie Teams bei gleichzeitiger Verwendung von Skype for Business verwalten möchten, und damit fortfahren, die Erwartungen Ihrer Benutzer zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-107">Therefore, you need to decide on how to manage Teams side-by-side with Skype for Business, and continue to meet user expectations.</span></span>

<span data-ttu-id="3a72d-108">Im Allgemeinen gibt es zwei Szenarien für Kunden, beide Lösungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-108">In general, there are two major side-by-side customer journeys.</span></span> <span data-ttu-id="3a72d-109">Bei diesen handelt es sich um:</span><span class="sxs-lookup"><span data-stu-id="3a72d-109">They are:</span></span>

-   <span data-ttu-id="3a72d-110">**Option 1:** Nicht verwaltete Customer Journey beim Einsatz beider Lösungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-110">**Option 1:** Unmanaged side-by-side customer journey.</span></span>

    <span data-ttu-id="3a72d-111">Das IT-Team steuert die Verwendung von beiden Lösungen nicht aktiv, und die Benutzer werden angehalten, ihre bevorzugte App selbst auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-111">IT does not actively control the side-by-side experience, and users are empowered to make the choice of preferred app.</span></span>

-   <span data-ttu-id="3a72d-112">**Option 2:** Verwaltete Customer Journey beim Einsatz beider Lösungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-112">**Option 2:** Managed side-by-side customer journey.</span></span>

    <span data-ttu-id="3a72d-113">Das IT-Team steuert die Verwendung von beiden Lösungen, nimmt die Benutzer mit auf die Reise der schrittweisen Einführung in Teams und führt zuerst einen neuen chatbasierten Arbeitsbereich für Zusammenarbeit mit privatem Chat, dann die Besprechungsfunktionen und schließlich die Anruffunktionen von Teams ein.</span><span class="sxs-lookup"><span data-stu-id="3a72d-113">IT controls the side-by-side experience, taking users through a journey of gradually introducing Teams to first introduce a new chat-based collaboration workspace with private chat, then meeting experiences, and finally the calling experiences in Teams.</span></span>

![Diagramm, von zwei parallelen Customer Journeys: verwaltet und nicht verwaltet.](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a><span data-ttu-id="3a72d-115">Vorteile und Überlegungen zum gleichzeitigen Einsatz beider Lösungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-115">Side-by-side benefits and considerations</span></span>
----------------------------------------

<span data-ttu-id="3a72d-116">Um den richtigen Weg in Abhängigkeit vom Profil Ihrer Organisation zu beschreiten, müssen die Vorteile und Aspekte der jeweiligen Reise unter verschiedenen Gesichtspunkten betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="3a72d-116">Each journey has benefits and considerations to evaluate when determining the right path forward based on your organization's profile.</span></span> <span data-ttu-id="3a72d-117">In der Tabelle unten werden die verwaltete und nicht verwaltete Customer Journey beim Einsatz beider Lösungen gegenübergestellt.</span><span class="sxs-lookup"><span data-stu-id="3a72d-117">The table below provides the comparisons between managed and unmanaged side-by-side customer journeys.</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3a72d-118">Migrationspfade</span><span class="sxs-lookup"><span data-stu-id="3a72d-118">Migration Paths</span></span></th>
<th align="left"><span data-ttu-id="3a72d-119">Nicht verwalteter Einsatz beider Lösungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-119">Unmanaged Side-by-Side</span></span></th>
<th align="left"><span data-ttu-id="3a72d-120">Verwalteter Einsatz beider Lösungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-120">Managed Side-by-Side</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="3a72d-121"><strong>Organisationsprofil</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-121"><strong>Organization profile</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="3a72d-122">Normalerweise für kleinere Organisationen ohne dedizierte IT-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="3a72d-122">Typically, smaller organizations with no dedicated IT resources</span></span></li>
<li><span data-ttu-id="3a72d-123">Das IT-Team stellt es den Benutzern frei, die richtigen Tools für ihre Arbeit auszuwählen</span><span class="sxs-lookup"><span data-stu-id="3a72d-123">IT allows user discretion in selecting right tools for their work</span></span></li>
<li><span data-ttu-id="3a72d-124">Primäre Skype for Business-Nutzung besteht aus Chats, Anrufen und Besprechungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-124">Primary Skype for Business usage is IM/P and meetings</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="3a72d-125">Normalerweise für Organisationen mittlerer Größe</span><span class="sxs-lookup"><span data-stu-id="3a72d-125">Typically, mid-size to larger organizations</span></span></li>
<li><span data-ttu-id="3a72d-126">Die IT-Abteilung möchte das Rollout von neuen Tools rigoroser kontrollieren</span><span class="sxs-lookup"><span data-stu-id="3a72d-126">IT wants to control roll out of new tools more rigorously</span></span></li>
<li><span data-ttu-id="3a72d-127">Derzeit größere Akzeptanz von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3a72d-127">Deeper adoption of Skype for Business today</span></span></li>
<li><span data-ttu-id="3a72d-128">Erhöhte Komplexität für Netzwerk und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="3a72d-128">Increased complexity in network and infrastructure</span></span></li>
<li><span data-ttu-id="3a72d-129">Mehrere Standorte</span><span class="sxs-lookup"><span data-stu-id="3a72d-129">Multiple locations</span></span></p>
<li><span data-ttu-id="3a72d-130">Präferenz für einzelne App mit eindeutigen UC-Funktionen</span><span class="sxs-lookup"><span data-stu-id="3a72d-130">Preference for single app with unique UC capabilities</span></span></li></ul></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3a72d-131"><strong>Vorteile</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-131"><strong>Benefits</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="3a72d-132">Nutzung von Funktionen in Teams, die in Skype for Business nicht verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="3a72d-132">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="3a72d-133">Verbesserter moderner Arbeitsplatz mit Office 365</span><span class="sxs-lookup"><span data-stu-id="3a72d-133">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="3a72d-134">Erhöhte Benutzerflexibilität</span><span class="sxs-lookup"><span data-stu-id="3a72d-134">Increased user flexibility</span></span></li>
<li><span data-ttu-id="3a72d-135">Gleichzeitige Aktivierung aller Funktionen</span><span class="sxs-lookup"><span data-stu-id="3a72d-135">Enable all capabilities at once</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="3a72d-136">Nutzung von Funktionen in Teams, die in Skype for Business nicht verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="3a72d-136">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="3a72d-137">Verbesserter moderner Arbeitsplatz mit Office 365</span><span class="sxs-lookup"><span data-stu-id="3a72d-137">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="3a72d-138">Die Auswirkungen auf die Benutzerproduktivität werden minimiert</span><span class="sxs-lookup"><span data-stu-id="3a72d-138">Minimize user productivity impact</span></span></li>
<li><span data-ttu-id="3a72d-139">Die Funktionsüberlappung wird reduziert</span><span class="sxs-lookup"><span data-stu-id="3a72d-139">Reduce capability overlap</span></span></li>
<li><span data-ttu-id="3a72d-140">Die Tool-Auswahl für UC-Szenarien wird optimiert</span><span class="sxs-lookup"><span data-stu-id="3a72d-140">Streamline tool choice for UC scenarios</span></span></li>
<li><span data-ttu-id="3a72d-141">Die IT-Abteilung und die operative Abteilung werden bestärkt, die Funktionen nach Bedarf in der Organisation einzusetzen</span><span class="sxs-lookup"><span data-stu-id="3a72d-141">Empower IT and business to enable capabilities as appropriate in organization</span></span></li>
<li><span data-ttu-id="3a72d-142">Das Veränderungstempo wird für Benutzer gesteuert</span><span class="sxs-lookup"><span data-stu-id="3a72d-142">Control the pace of change for users</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="3a72d-143"><strong>Überlegungen</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-143"><strong>Considerations</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="3a72d-144">Mehrere Apps mit ähnlichen, sich überschneidenden Funktionen</span><span class="sxs-lookup"><span data-stu-id="3a72d-144">Multiple apps with similar, overlapping capabilities</span></span></li>
<li><span data-ttu-id="3a72d-145">Erhöhte Gefahr von Benutzerkonfusion, die zu vermehrten Supportanrufen, erhöhter Belastung des IT-Teams und Produktivitätseinbußen führt</span><span class="sxs-lookup"><span data-stu-id="3a72d-145">Increased potential for user confusion which can lead to increased support calls, shadow IT, impacted productivity</span></span></li>
<li><span data-ttu-id="3a72d-146">Bei der Netzwerkplanung und -überwachung muss die Verwendung von zwei Diensten in Betracht gezogen werden</span><span class="sxs-lookup"><span data-stu-id="3a72d-146">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="3a72d-147">Ein erhöhter und unmittelbarer Change Management-Aufwand ist erforderlich: Sensibilisierung, Schulung und Support</span><span class="sxs-lookup"><span data-stu-id="3a72d-147">Increased and immediate change management efforts required: awareness, training, and support</span></span></li>
<li><span data-ttu-id="3a72d-148">Die Benutzer können auf Einschränkungen der Interoperabilität zwischen den Apps stoßen</span><span class="sxs-lookup"><span data-stu-id="3a72d-148">Users may experience interoperability limitations between apps</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="3a72d-149">Durch die granulare Kontrolle der IT-Abteilung – von der Lizenzierung bis zu den Funktionen für die Benutzer – sind zusätzliche Zyklen für Planung und Implementierung erforderlich</span><span class="sxs-lookup"><span data-stu-id="3a72d-149">IT has granular control, from licensing to user experiences, requiring additional cycles of planning and implementation</span></span></li>
<li><span data-ttu-id="3a72d-150">Benutzerschulungen und Aktionen sind erforderlich, um ausgewählte Funktionen in Teams zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="3a72d-150">User education and action required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="3a72d-151">Change Management-Maßnahmen sind erforderlich, um ausgewählte Funktionen in Teams zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="3a72d-151">Change management efforts required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="3a72d-152">Bei der Netzwerkplanung und -überwachung muss die Verwendung von zwei Diensten in Betracht gezogen werden</span><span class="sxs-lookup"><span data-stu-id="3a72d-152">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="3a72d-153">Die Benutzer können auf Einschränkungen der Interoperabilität zwischen den Apps stoßen</span><span class="sxs-lookup"><span data-stu-id="3a72d-153">Users may experience interoperability limitations between apps</span></span></li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a><span data-ttu-id="3a72d-154">Nicht verwaltete Customer Journey beim Einsatz beider Lösungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-154">Unmanaged side-by-side customer journey</span></span>
---------------------------------------


![Diagramm der nicht verwalteten Customer Journey beim Einsatz beider Lösungen](media/guidance_SkypeforBusiness_image4.png)

<span data-ttu-id="3a72d-156">Auf einer nicht verwalteten Customer Journey beim Einsatz beider Lösungen wird Teams als Lösung zur Zusammenarbeit eingeführt (chatbasierter Arbeitsbereich, Kanäle, Apps, Integration in andere Office 365-Arbeitsauslastungen usw.), die Clientsoftware und einen Webclient auf Desktopcomputern (PC oder Mac) und Mobilgeräte mit einschließen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-156">In an unmanaged side-by-side customer journey, Teams is introduced as a collaboration solution (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.) that involves client software and web client on desktop computers (PC or Mac) and mobile devices.</span></span>


<span data-ttu-id="3a72d-157">Standardmäßig bietet Teams auch sich mit Skype for Business überlappende Funktionen. Diese beinhalten private Chats und Anrufe sowie geplante Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-157">By default, Teams also presents overlapping capabilities with Skype for Business, these include private chat and calling, and scheduled meetings.</span></span> <span data-ttu-id="3a72d-158">Das heißt, dass Teams als vollständige Lösung für Kommunikation und Zusammenarbeit für die Organisation eingesetzt werden kann, während Skype for Business zur gleichen Zeit ähnliche Funktionen bietet.</span><span class="sxs-lookup"><span data-stu-id="3a72d-158">This means Teams ends up providing complete communications and collaboration for the organization, while at the same time Skype for Business provides similar capabilities.</span></span>

<span data-ttu-id="3a72d-159">Teams unterstützt die Interoperabilität mit Skype for Business Online-Benutzern, und Benutzer erhalten die Möglichkeit, ihre bevorzugte Chat- und Anruf-App auszuwählen, wenn sie Teams starten.</span><span class="sxs-lookup"><span data-stu-id="3a72d-159">Teams supports interoperability with Skype for Business Online users, and users will be given an opportunity to choose their preferred chat and calling app when they launch Teams.</span></span> <span data-ttu-id="3a72d-160">Wenn ein Benutzer Teams als seine bevorzugte App verwendet, und ein anderer Benutzer Teams nicht installiert oder Skype for Business nicht als seine bevorzugte Chat- und Anruf-App nutzt, können die beiden weiterhin über die Interoperablititätsfunktionen, die Teil von Teams sind, miteinander chatten oder sich anrufen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-160">If one user picks Teams as the preferred app, and another user hasn’t installed Teams or picked Skype for Business as the preferred chat and calling app, they can continue to chat and call each other through the interop capabilities that are part of Teams.</span></span>

<span data-ttu-id="3a72d-161">Microsoft verbessert kontinuierlich die Funktionen für Interoperablitität.</span><span class="sxs-lookup"><span data-stu-id="3a72d-161">Microsoft is continuously improving the interop experiences.</span></span> <span data-ttu-id="3a72d-162">Anfänglich können jedoch Situationen auftreten, in denen die Interoperabilität nicht die Erwartungen der Benutzer erfüllt.</span><span class="sxs-lookup"><span data-stu-id="3a72d-162">In the beginning, there may be some cases whereby the interop experiences are not meeting user expectations.</span></span> <span data-ttu-id="3a72d-163">Da Skype for Business den Benutzern aber immer noch zur Verfügung steht, können Sie zu Skype for Business wechseln, um die Funktionen zu verwenden, die von Teams derzeit nicht bedient werden können.</span><span class="sxs-lookup"><span data-stu-id="3a72d-163">Since Skype for Business is still available to users, they can switch to Skype for Business for the capabilities that currently cannot be served by Teams.</span></span>

<span data-ttu-id="3a72d-164">„Geplante Besprechungen“ in Teams ist eine weitere überlappende Funktion, mit denen Benutzer Teams- oder Skype for Business-Besprechungen planen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-164">Scheduled meetings in Teams is another overlapping capability that lets users schedule Teams meetings, or Skype for Business meetings.</span></span> <span data-ttu-id="3a72d-165">Jede Lösung bietet ihre eigenen Vorteile, und mit der Zeit, wenn die Teams-Besprechungsfunktion die Geschäftsanforderungen erfüllt oder die Funktionen von Skype for Business-Besprechungen in puncto Qualität überholt, ist es nur natürlich, wenn die Benutzer zu Teams wechseln.</span><span class="sxs-lookup"><span data-stu-id="3a72d-165">Each has its own advantages, and over time, when Teams meeting experience meets business requirements or surpasses the functionalities of Skype for Business meetings, we expect users to naturally switch to Teams meetings.</span></span>

<span data-ttu-id="3a72d-166">Bereiten Sie Ihr Helpdesk-Team auf diese nicht verwalteten Customer Journey beim Einsatz beider Lösungen vor, die Supportanrufe von Benutzern in Bezug auf Probleme mit der Interoperabilität zu bewältigen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-166">In this unmanaged side-by-side customer journey, prepare your helpdesk team to handle support calls from users when facing issues with interop capabilities.</span></span> <span data-ttu-id="3a72d-167">Sie können die Benutzer auch dahingehend beraten, wann die Verwendung von Teams-Besprechungen sinnvoller als der Einsatz von Skype for Business-Besprechungen ist bzw. umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="3a72d-167">Or advise users when to choose Teams meetings over Skype for Business meetings, and vice versa.</span></span>

<span data-ttu-id="3a72d-168">Diese Customer Journey beim Einsatz beider Lösungen kann für Ihre Organisation passend sein, wobei die Benutzer empfänglicher für die nicht verwaltete Reise sind, bei der die Organisation Ihre Benutzer offen dazu auffordert, die ihren Anforderungen am ehesten entsprechenden Tools zur Kommunikation und Zusammenarbeit auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-168">This side-by-side customer journey may be applicable to your organization, whereby the users are more receptive to the nature of the unmanaged side-by-side experience, and the organization openly allows the users to pick the best communications and collaboration tools that suit their requirements.</span></span>

<a name="managed-side-by-side-customer-journey"></a><span data-ttu-id="3a72d-169">Verwaltete Customer Journey beim Einsatz beider Lösungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-169">Managed side-by-side customer journey</span></span>
-------------------------------------

![Diagramm der verwalteten Customer Journey beim Einsatz beider Lösungen](media/guidance_SkypeforBusiness_image2.png)

<span data-ttu-id="3a72d-171">Eine verwaltete Customer Journey beim Einsatz beider Lösungen beginnt damit, dass die Organisation mehr Kontrolle über die Art und Weise der Einführung von Teams wünscht.</span><span class="sxs-lookup"><span data-stu-id="3a72d-171">A managed side-by-side customer journey starts with organization wanting more control over how Teams is introduced.</span></span>

-   <span data-ttu-id="3a72d-172">Der **erste Schritt** dieser Reise ist ein limitiertes Teams-Pilotprojekt auf Basis von Anforderungen für moderne Zusammenarbeit (chatbasierter Arbeitsbereich, Kanäle, Apps, Integration in andere Office 365-Auslastungen usw.)</span><span class="sxs-lookup"><span data-stu-id="3a72d-172">The **first step** of this journey is a limited pilot of Teams scoped to modern collaboration requirements (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.).</span></span> <span data-ttu-id="3a72d-173">Ad-hoc-Kanalbesprechungen und private Chats in Teams sind ebenfalls aktiviert, um Teilnehmern des Pilotprojekts die Chance zu geben, die Teams-Besprechungsfunktionen und die Funktionen für private Chats zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="3a72d-173">Ad-hoc channel meetings and private chat in Teams is also enabled to provide a chance for pilot users to evaluate the Teams meetings experience and private chat experiences.</span></span> <span data-ttu-id="3a72d-174">In dieser Phase sind geplante Besprechungen und private Anruffunktionen in Teams deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3a72d-174">Scheduled meetings and private calling capabilities in Teams are disabled at this stage.</span></span> <span data-ttu-id="3a72d-175">Um ein Pilotprojekt zu starten, navigieren Sie zu [Teams als Pilotprojekt neben Skype for Business](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="3a72d-175">To get started with a pilot, go to [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>
    
-   <span data-ttu-id="3a72d-176">Der **zweite Schritt** dieser Reise ist die Erweiterung des Rollouts von Teams für moderne Zusammenarbeit mit der Funktion für privaten Chat in der gesamten Organisation.</span><span class="sxs-lookup"><span data-stu-id="3a72d-176">The **second step** of this journey is extending the rollout of Teams for modern collaboration with private chat throughout the organization.</span></span> <span data-ttu-id="3a72d-177">Die Funktionen für geplante Besprechungen und private Anrufe sind in Teams weiterhin deaktiviert, um die Überlappung mit Skype for Business-Funktionen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="3a72d-177">Scheduled meetings, and private calling continue to be disabled in Teams to reduce the overlap  with with Skype for Business capabilities.</span></span>

    <span data-ttu-id="3a72d-178">In dieser Phase müssen Sie darüber nachdenken, ob es sich bei der bevorzugten Chatanwendung für die gesamte Organisation um Teams oder Skype for Business handeln soll.</span><span class="sxs-lookup"><span data-stu-id="3a72d-178">At this stage, you may need to consider whether preferred chat application should be set to Teams or Skype for Business for the entire organization.</span></span>

    - <span data-ttu-id="3a72d-179">Wenn Sie sich für Teams entscheiden, bereiten Sie Ihre Benutzer darauf vor, bei der Kommunikation mit anderen Benutzern in der Organisation möglicherweise auftretende Probleme bei der Interoperabilität frühzeitig zu beheben.</span><span class="sxs-lookup"><span data-stu-id="3a72d-179">If set to Teams, prepare your users to handle early interoperability challenges when communicating with other parties within and across the organization.</span></span>
    
    - <span data-ttu-id="3a72d-180">Wenn Sie sich für Skype for Business entscheiden, werden private Chats innerhalb von Teams in Teams beibehalten. Endbenutzer können sofort die Vorteile der plattformübergreifenden und beständigen Chatfunktionen innerhalb von Teams nutzen und weiterhin Skype for Business für private Chats mit anderen Skype for Business-Benutzern innerhalb und außerhalb der Organisation nutzen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-180">If set to Skype for Business, private chats within Teams will remain in Teams, and end users can immediately take advantage of the cross-platform persistent nature of chat capabilities within Teams, and they will continue to use Skype for Business for private chats among Skype for Business users, within the organization and across the organization.</span></span>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3a72d-181">Hinweis</span><span class="sxs-lookup"><span data-stu-id="3a72d-181">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="3a72d-182">Die Einstellung für die bevorzugte Chatanwendung ist derzeit nur auf der Clientebene verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3a72d-182">Currently the preferred chat application setting is available only at the client level.</span></span> <span data-ttu-id="3a72d-183">Benutzerschulungen und Übernahmekampagnen sind erforderlich, um die beabsichtigte organisationsweite Konfiguration voranzutreiben.</span><span class="sxs-lookup"><span data-stu-id="3a72d-183">User training and adoption campaign will be required to drive the intended organization-wide configuration.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="3a72d-184">Der **dritte Schritt** der verwalteten Customer Journey beim Einsatz beider Lösungen startet, wenn die Organisation entscheidet, dass die Teams-Besprechungsfunktionen ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-184">The **third step** of the managed side-by-side customer journey starts when the organization decides that Teams meeting experience and capabilities meet their business requirements.</span></span> <span data-ttu-id="3a72d-185">Durch die Aktivierung von privaten und Kanalbesprechungen in Teams erhalten Benutzer Optionen zum Planen von Teams-Besprechungen und Skype for Business-Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-185">By enabling private and channel meetings in Teams, users are presented with options to schedule both Teams meetings and Skype for Business meetings.</span></span> <span data-ttu-id="3a72d-186">Es ist daher zu erwarten, dass Benutzer mit der Zeit aufgrund kontinuierlicher Innovationen in Teams zwangsläufig zu Teams-Besprechungen wechseln.</span><span class="sxs-lookup"><span data-stu-id="3a72d-186">Therefore, it is expected that over time users will naturally switch to Teams meetings given the continued innovations in Teams.</span></span> <span data-ttu-id="3a72d-187">Um den Übergang von Skype for Business zu Teams ordnungsgemäß zu lenken, implementieren Sie ein robustes Change Management-Programm, das unter anderem Schulungen, Support und Kommunikationsinitiativen enthält, die den Benutzern den Mehrwert von Teams erklären und ihnen klare Vorgaben für die ersten Schritte mit Teams bieten.</span><span class="sxs-lookup"><span data-stu-id="3a72d-187">To be successful in steering usage from Skype for Business to Teams, implement a robust change management program inclusive of training, support and communications that explains the value-add that Teams offers to the user, with clear guidance on how to get started with Teams.</span></span> <span data-ttu-id="3a72d-188">Nutzen Sie Ihre Ressourcen für [Benutzerakzeptanz](http://aka.ms/UserReadiness) zur Unterstützung für den Entwurf Ihrer Sensibilisierungskampagne.</span><span class="sxs-lookup"><span data-stu-id="3a72d-188">Leverage our [User Readiness](http://aka.ms/UserReadiness) resources to help design your awareness campaign.</span></span>


<span data-ttu-id="3a72d-189">Der **vierte Schritt** der verwalteten Customer Journey beim Einsatz beider Lösungen beginnt mit der Aktivierung der Anruffunktion in Teams.</span><span class="sxs-lookup"><span data-stu-id="3a72d-189">The **fourth step** of the managed side-by-side customer journey begins with enabling calling in Teams.</span></span> <span data-ttu-id="3a72d-190">Die Teams-Interoperabilitätsfunktionen nehmen in diesem Schritt eine zentrale Bedeutung ein, um eine nahtlose Erfahrung beider Lösungen nebeneinander zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-190">Teams interoperability capabilities will feature heavily in this step to ensure a seamless side-by-side experience.</span></span> <span data-ttu-id="3a72d-191">Idealerweise wird Teams als die Standardanruf-App festgelegt, um die Verwendung von Teams für private Anrufe durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-191">Ideally, to enforce the use of Teams for private calling, Teams is set as the default calling app.</span></span> 

<span data-ttu-id="3a72d-192">Mit der Zeit kann sich die gesamte Organisation potenziell nur auf Teams verlassen, um die Anforderungen für Kommunikation und Zusammenarbeit zu erfüllen, und mit dem **fünften Schritt** beginnen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-192">Over time, potentially the whole organization can rely solely on Teams to meet communications and collaboration requirements and take the **fifth step**.</span></span> <span data-ttu-id="3a72d-193">In der [Office 365-Roadmap](http://aka.ms/TeamsRoadmap) erfahren Sie, wann in Teams neue Funktionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3a72d-193">To see when new features are coming in Teams, see the [Office 365 Roadmap](http://aka.ms/TeamsRoadmap).</span></span> 

<a name="managing-side-by-side-experience"></a><span data-ttu-id="3a72d-194">Verwalten der Funktionen beim Einsatz beider Lösungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-194">Managing side-by-side experience</span></span>
--------------------------------

<span data-ttu-id="3a72d-195">Für Organisationen mit den entsprechenden Office 365-Abonnements ist Microsoft Teams standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3a72d-195">By default, for organizations with eligible Office 365 subscriptions, Microsoft Teams is enabled.</span></span> <span data-ttu-id="3a72d-196">Wenn Ihre Organisation dem Profil für die nicht verwaltete Customer Journey beim Einsatz beider Lösungen entspricht, wird dringend empfohlen, dieses Profil beizubehalten, um die organische Übernahme von Microsoft Teams zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-196">If your organization fits the profile for unmanaged side-by-side customer journey, we highly recommend you keep it as-is to foster organic adoption of Microsoft Teams.</span></span>

<span data-ttu-id="3a72d-197">Der Zugriff auf Teams erfolgt über moderne Webbrowser-Desktopclients, für die keine administrativen Rechte (für die Installation, derzeit nur für PCs anwendbar) und keine mobilen Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3a72d-197">Teams is accessible via modern Web browser desktop clients which require no IT administrative privilege (for installation, currently applicable to PC only) and mobile clients.</span></span>

<span data-ttu-id="3a72d-198">Alle Funktionen in Teams – von privaten Chats und Anrufen, Ad-hoc- und geplanten Besprechungen bis zu Apps – werden standardmäßig aktiviert. Dadurch können Benutzer die Funktionen ausprobieren, die ihren Anforderungen am ehesten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-198">All capabilities in Teams, from private chat and calling, ad-hoc and scheduled meetings, and apps are enabled by default, allowing users to experiment and use the capabilities that suit their needs.</span></span> <span data-ttu-id="3a72d-199">Bei der erstmaligen Ausführung von Teams werden Benutzer angeleitet, ihre bevorzugte Chat- und Anrufanwendung (Microsoft Teams oder Skype for Business) auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-199">A first-run experience in Teams guides users to pick their preferred chat and calling application (Microsoft Teams or Skype for Business).</span></span>

<span data-ttu-id="3a72d-200">Wenn Ihre Organisation eine kontrolliertere Version der neuen Tools, wie zum Beispiel Teams, benötigt, können die folgenden Optionen für eine verwaltete Customer Journey beim Einsatz beider Lösungen in Betracht gezogen werden:</span><span class="sxs-lookup"><span data-stu-id="3a72d-200">Should your organization require a more controlled release of new tools such as Teams, the following options can be considered for your managed side-by-side customer journey, they are:</span></span>

-   <span data-ttu-id="3a72d-201">Einsatz und Rollout von Teams als Pilotprojekt für Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="3a72d-201">Pilot and rollout of Teams for collaboration.</span></span> <span data-ttu-id="3a72d-202">Siehe [Teams als Pilotprojekt neben Skype for Business](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="3a72d-202">See [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>

-   <span data-ttu-id="3a72d-203">Rollout von Teams für Besprechungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-203">Rollout of Teams for meetings</span></span>

-   <span data-ttu-id="3a72d-204">Rollout von Teams für Anrufe</span><span class="sxs-lookup"><span data-stu-id="3a72d-204">Rollout of Teams for calling</span></span>

### <a name="teams-pilot-and-rollout-for-collaboration"></a><span data-ttu-id="3a72d-205">Einsatz von Teams als Pilotprojekt und Rollout für Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="3a72d-205">Teams pilot and rollout for collaboration</span></span>

<span data-ttu-id="3a72d-206">Durch die Optimierung von Office 365-Gruppen wurde Microsoft Teams im Kern um beständigen Chat und die Integration in Office 365 herum aufgebaut.</span><span class="sxs-lookup"><span data-stu-id="3a72d-206">At its core, Microsoft Teams was built around persistent chat and integration with Office 365 by enhancing Office 365 Groups.</span></span>

<span data-ttu-id="3a72d-207">Da Benutzer in Ihrer Organisation mit einer Office 365-Abonnementlizenz standardmäßig für Teams aktiviert, wird in einem limitierten Teams-Pilotprojekt unter anderem die Teams-Lizenz für alle Benutzer deaktiviert, die nicht der Pilotprojektgruppe angehören.</span><span class="sxs-lookup"><span data-stu-id="3a72d-207">Since by default users in your organization with an eligible Office 365 subscription license are enabled for Teams, a limited Teams pilot will involve disabling the Teams license for all users who are outside of the pilot group.</span></span>

<span data-ttu-id="3a72d-208">Um den Schwerpunkt der Teams-Version auf Zusammenarbeit und privaten Chat zu legen und die Benutzerkonfusion aufgrund von sich mit Skype for Business-Funktionen überlappenden Funktionen zu verringern, können Sie die folgenden Einstellungen auf der Office 365-Mandantenebene vornehmen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-208">To focus the Teams release as a collaboration and private chat solution, and to reduce user confusion due to overlapping capabilities with Skype for Business, you can change the following settings at the Office 365 tenant level.</span></span> <span data-ttu-id="3a72d-209">Informationen zum Ändern dieser Office 365-Einstellungen finden Sie unter [Einrichten von Microsoft Teams in Ihrer Office 365-Organisation](Office-365-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="3a72d-209">To change these Office 365 settings, see [Set up Microsoft Teams in your Office 365 organization](Office-365-set-up.md).</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3a72d-210">Abschnittsüberschrift</span><span class="sxs-lookup"><span data-stu-id="3a72d-210">Section</span></span></th>
<th align="left"><span data-ttu-id="3a72d-211">Einstellung</span><span class="sxs-lookup"><span data-stu-id="3a72d-211">Setting</span></span></th>
<th align="left"><span data-ttu-id="3a72d-212">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a72d-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="3a72d-213">Anrufe und Besprechungen</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-213">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="3a72d-214">Planen von privaten Besprechungen zulassen: <strong>Aus</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-214">Allow scheduling for private meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="3a72d-215">Planen von Kanalbesprechungen zulassen: <strong>Aus</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-215">Allow scheduling for channel meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="3a72d-216">Private Anrufe zulassen: <strong>Aus</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-216">Allow private calling: <strong>Off</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="3a72d-217">Wenn diese Einstellung deaktiviert ist, können Benutzer keine privaten Besprechungen planen</span><span class="sxs-lookup"><span data-stu-id="3a72d-217">Disabling this setting prevents users from scheduling private meetings</span></span></p><p><span data-ttu-id="3a72d-218">Wenn diese Einstellung deaktiviert ist, können Benutzer keine Kanalbesprechungen planen</span><span class="sxs-lookup"><span data-stu-id="3a72d-218">Disabling this setting prevents users from scheduling channel meetings</span></span></p><p><span data-ttu-id="3a72d-219">Wenn diese Einstellung deaktiviert ist, können Benutzer keine privaten Anrufe (Audio oder Video) tätigen</span><span class="sxs-lookup"><span data-stu-id="3a72d-219">Disabling this setting prevents users from making private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3a72d-220">Hinweis</span><span class="sxs-lookup"><span data-stu-id="3a72d-220">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="3a72d-221">Sie müssen die Option „Private Anrufe“ für Business- und Enterprise-Benutzer sowie für Gastbenutzer (falls Gastzugriff in Ihrer Organisation gewährt wird) deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3a72d-221">You must disable Private Calling to both Business and Enterprise users, and Guest users (if Guest Access is applicable to your organization).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>



<span data-ttu-id="3a72d-222">Mit dieser Konfiguration können Benutzer eine Einführung in die Funktionsweise von Besprechungen in Teams erhalten, indem sie die Verwendung von Ad-hoc-Kanal-MeetUps befürworten und VoIP, Video und Bildschirmfreigabe als Teil der Funktionen für moderne Zusammenarbeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a72d-222">With this configuration, users can be introduced to how meetings work in Teams by advocating the use of ad-hoc channel meetup, enabling the use of voice, video, and screen sharing as part of the modern collaboration experience.</span></span> <span data-ttu-id="3a72d-223">Endbenutzer können auch von den beständigen und plattformübergreifenden Funktionen für privaten Chat profitieren.</span><span class="sxs-lookup"><span data-stu-id="3a72d-223">End users can also benefit from Teams persistent, cross-platform, private chat capabilities.</span></span>

<span data-ttu-id="3a72d-224">Darüber hinaus kann ein erfolgreiches Teams-Pilotprojekt für Zusammenarbeit und privaten Chat mit einem durch die Verteilung von Teams-Lizenzen für alle Benutzer großflächig angelegten Rollout in der Organisation durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3a72d-224">A successful Teams pilot for collaboration and private chat can be followed up with broad rollout throughout the organization by enabling Teams license for all users.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3a72d-225">Hinweis</span><span class="sxs-lookup"><span data-stu-id="3a72d-225">Note</span></span></p></td>
<td align="left"><span data-ttu-id="3a72d-226">Während des Pilotprojekts und in Phase 2, wenn die Funktion für privaten Chat aktiviert ist, kann ein Teams-Benutzer, der mit einem Skype for Business-Benutzer chattet, folgende Aktionen nicht ausführen:</span><span class="sxs-lookup"><span data-stu-id="3a72d-226">During the pilot, and in phase two when private chat is enabled, a Teams user chatting with a Skype for Business user will not be able to do the following:</span></span><br><span data-ttu-id="3a72d-227">
- Starten eines Videoanrufs über eine Chatsitzung</span><span class="sxs-lookup"><span data-stu-id="3a72d-227">
- Start video call from a chat session</span></span><br><span data-ttu-id="3a72d-228">
- Übertragen von Dateien</span><span class="sxs-lookup"><span data-stu-id="3a72d-228">
- Transfers files</span></span> <br><span data-ttu-id="3a72d-229">
- Initiieren eines Anrufs mit mehreren Parteien in der Chatsitzung</span><span class="sxs-lookup"><span data-stu-id="3a72d-229">
- Initiate a multiparty call from the chat session</span></span><br><span data-ttu-id="3a72d-230">
- Benutzer können keine Desktopfreigabesitzung starten</span><span class="sxs-lookup"><span data-stu-id="3a72d-230">
- Users will not be able to start a desktop sharing session</span></span><br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a><span data-ttu-id="3a72d-231">Rollout von Teams für Besprechungen</span><span class="sxs-lookup"><span data-stu-id="3a72d-231">Rollout of Teams for meetings</span></span>

<span data-ttu-id="3a72d-232">Wenn sich Benutzer an die Zusammenarbeit unter Verwendung von Microsoft Teams gewöhnt haben, können geplante Besprechungen als nächste Funktion in der Organisation eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3a72d-232">As users are getting accustomed to collaborating using Microsoft Teams, scheduled meetings can be considered as the next capability to enable in the organization.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3a72d-233">Hinweis</span><span class="sxs-lookup"><span data-stu-id="3a72d-233">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="3a72d-234">Die Organisatoren von geplanten Besprechungen müssen über Postfächer verfügen, die sich in einer mehrinstanzfähigen Exchange Online-Version (oder in einer Exchange Online Dedicated vNext-Version) befinden.</span><span class="sxs-lookup"><span data-stu-id="3a72d-234">The organizers of scheduled meetings must have their mailboxes in Exchange Online multi-tenant (or Exchange Online Dedicated vNext).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="3a72d-235">Die folgenden Einstellungen können auf der Mandantenebene konfiguriert werden, um geplante Besprechungen in Teams durchzuführen. Diese Einstellungen können nur von Business- und Enterprise-Benutzern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a72d-235">The following settings can be configured at the tenant level to enable scheduled meetings in Teams, and the settings are applicable to Business and Enterprise users only.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3a72d-236">Abschnittsüberschrift</span><span class="sxs-lookup"><span data-stu-id="3a72d-236">Section</span></span></th>
<th align="left"><span data-ttu-id="3a72d-237">Einstellung</span><span class="sxs-lookup"><span data-stu-id="3a72d-237">Setting</span></span></th>
<th align="left"><span data-ttu-id="3a72d-238">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a72d-238">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="3a72d-239">Anrufe und Besprechungen</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-239">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="3a72d-240">Planen von privaten Besprechungen zulassen: <strong>Ein</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-240">Allow scheduling for private meetings: <strong>On</strong></span></span></p><p><span data-ttu-id="3a72d-241">Planen von Kanalbesprechungen zulassen: <strong>Ein</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-241">Allow scheduling for channel meetings: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="3a72d-242">Wenn diese Einstellung aktiviert ist, können Benutzer private Besprechungen planen</span><span class="sxs-lookup"><span data-stu-id="3a72d-242">Enabling this setting allows users to schedule private meetings</span></span></p><p><span data-ttu-id="3a72d-243">Wenn diese Einstellung aktiviert ist, können Benutzer Kanalbesprechungen planen</span><span class="sxs-lookup"><span data-stu-id="3a72d-243">Enabling this setting allows users to schedule channel meetings</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3a72d-244">Geplante Besprechungen können über den Teams-Desktopclient, einen Browser oder über Microsoft Outlook mit dem Besprechungs-Add-In für Microsoft Teams organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3a72d-244">Scheduled meetings can be organized via the Teams desktop client, a browser, or via Microsoft Outlook using the meeting add-in for Microsoft Teams.</span></span> <span data-ttu-id="3a72d-245">Sobald geplante Besprechungen in Teams aktiviert sind, wird eine Schulung der Benutzer zum Erstellen neuer Teams-Besprechungen oder zum Aktualisieren von vorhandenen Skype for Business-Besprechungen in Teams-Besprechungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-245">Once scheduled meetings in Teams is enabled, we recommend you start educating users to create new Teams meetings or update existing Skype for Business meetings to Teams meetings.</span></span>

### <a name="rollout-of-teams-for-calling"></a><span data-ttu-id="3a72d-246">Rollout von Teams für Anrufe</span><span class="sxs-lookup"><span data-stu-id="3a72d-246">Rollout of Teams for calling</span></span>

<span data-ttu-id="3a72d-247">„Private Anrufe“ ist die Funktion in Teams, die kontinuierlich entwickelt wird. Es dauert aber nicht mehr lange, bis sie sich gegenüber Skype for Business durchsetzen wird.</span><span class="sxs-lookup"><span data-stu-id="3a72d-247">Private calling is the Teams capability that will be continuously developed, and over time provide a compelling replacement to Skype for Business.</span></span> <span data-ttu-id="3a72d-248">Wenn Ihre Organisation der Ansicht ist, dass die Funktionen für private Anrufe die wichtigsten Geschäftsanforderungen erfüllt, können die folgenden Einstellungen auf der Mandantenebene konfiguriert werden, um die Funktion für private Anrufe in Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3a72d-248">When your organization considers that Teams private calling capabilities meet key business requirements, the following settings can be configured at the tenant level to enable private calling in Teams.</span></span> 

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3a72d-249">Abschnittsüberschrift</span><span class="sxs-lookup"><span data-stu-id="3a72d-249">Section</span></span></th>
<th align="left"><span data-ttu-id="3a72d-250">Einstellung</span><span class="sxs-lookup"><span data-stu-id="3a72d-250">Setting</span></span></th>
<th align="left"><span data-ttu-id="3a72d-251">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a72d-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="3a72d-252">Anrufe und Besprechungen</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-252">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="3a72d-253">Private Anrufe zulassen: <strong>Ein</strong></span><span class="sxs-lookup"><span data-stu-id="3a72d-253">Allow private calling: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="3a72d-254">Wenn diese Einstellung aktiviert ist, können Benutzer private Anrufe (Audio oder Video) tätigen</span><span class="sxs-lookup"><span data-stu-id="3a72d-254">Enabling this setting allows users to place private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="3a72d-255">Hinweis</span><span class="sxs-lookup"><span data-stu-id="3a72d-255">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="3a72d-256">Zulassen, dass Benutzer privat chatten: Wenn diese Einstellung aktiviert ist, können Benutzer mit anderen Benutzern privat chatten.</span><span class="sxs-lookup"><span data-stu-id="3a72d-256">Allow users to chat privately: Enabling this setting allows users to chat with other users privately.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>


<span data-ttu-id="3a72d-257">In dieser Phase müssen alle Benutzer angewiesen werden, Teams als ihre bevorzugte Anruf-App auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-257">At this stage, all users must be instructed to choose Teams as the preferred calling app.</span></span>

<span data-ttu-id="3a72d-258">Mit der Aktivierung der Funktion für private Anrufe stellt Teams alle der derzeit in Skype for Business verfügbaren Funktionen zur Verfügung, und Benutzer können mit dem Einsatz von Teams beginnen, um ihre Anforderungen an Kommunikation und Zusammenarbeit zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-258">With the enablement of private calling, Teams will deliver all capabilities currently provided by Skype for Business, and users can start using Teams to fulfill their communications and collaboration requirements.</span></span>


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><span data-ttu-id="3a72d-259"><strong>Nächste Aktion</strong>: Sobald Teams eingerichtet und neben Skype for Business ausgeführt wird, [erzielen Sie durch die Benutzerakzeptanz von Teams einen Mehrwert](continue-journey.md), indem Sie Ihre Reise von Skype for Business nach Teams fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="3a72d-259"><strong>Next Action:</strong> Once Teams is up and running side-by-side with Skype for Business, [Drive Value through user adoption of Teams](continue-journey.md), while continuing your journey from Skype for Business to Teams.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>