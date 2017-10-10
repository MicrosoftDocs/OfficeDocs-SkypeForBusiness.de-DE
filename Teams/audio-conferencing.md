---
title: Audiokonferenzen in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Praktische Anleitungen zur Bereitstellung von Cloud Voice in Microsoft Teams.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: cf50e6468bdf4fc96419d39fbc889c5b5a220a8d
ms.sourcegitcommit: e0efee5350da54a1f1ae1c317f8613652c820bc6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="52105-103">Audiokonferenzen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52105-103">Audio Conferencing in Microsoft Teams</span></span>
=====================================

> [!IMPORTANT]
> <span data-ttu-id="52105-104">Die Funktion „Audiokonferenzen“ ist als Public Preview-Funktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52105-104">Audio conferencing is in Public Preview.</span></span> <span data-ttu-id="52105-105">Early Adopters (EA) und Preview-Kunden können auf diese Funktion zugreifen und sie nach der Veröffentlichung oder Aktualisierung ändern.</span><span class="sxs-lookup"><span data-stu-id="52105-105">It's available to Early Adopters (EA) and preview customers and could change as it is released or updated.</span></span>

<span data-ttu-id="52105-106">Mit der Funktion „Audiokonferenzen“ in Office 365 (ehemals als PSTN-Konferenzen bezeichnet) können Teilnehmer mit einem beliebigen Telefon an Ihren Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="52105-106">Audio Conferencing in Office 365 (formerly known as PSTN Conferencing) allows participants to join your meetings from any telephone.</span></span> <span data-ttu-id="52105-107">Diese Funktion ist jetzt auch in Microsoft Teams verfügbar – Benutzer können sich mit ihren Telefonen in Teams-Besprechungen einwählen.</span><span class="sxs-lookup"><span data-stu-id="52105-107">This feature is now available in Microsoft Teams, allowing users to join Teams meetings using their phones.</span></span> <span data-ttu-id="52105-108">Die praktischen Anleitungen in diesem Artikel begleiten Sie schrittweise auf Ihrer Office 365 FastTrack-Customer Journey für Audiokonferenzen. Die Themen lauten: Ausblick, Onboarding und Wertschöpfung.</span><span class="sxs-lookup"><span data-stu-id="52105-108">The practical guidance in this article steps you through the Office 365 FastTrack customer journey framework for Audio Conferencing - Envision, Onboard, and Drive value.</span></span>

<span data-ttu-id="52105-109">Das bekommen Sie mit [Audiokonferenzen](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="52105-109">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="52105-110">Audiokonferenzen werden sowohl in Teams als auch in Skype for Business Online unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52105-110">Audio Conferencing supports both Teams and Skype for Business Online.</span></span> <span data-ttu-id="52105-111">Das Skype for Business Admin Center und die PowerShell bieten Verwaltungsschnittstellen zur Verwaltung von Audiokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="52105-111">Currently, the existing Skype for Business Admin center and remote PowerShell provide the administrative interfaces to manage Audio Conferencing.</span></span>


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

<span data-ttu-id="52105-112">Ausblick <a name="Envision_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="52105-112">Envision <a name="Envision_AudioConferencing"> </a></span></span>
=========

<span data-ttu-id="52105-113">Die Ausblick-Phase bietet die Grundlage für die Office 365 Customer Journey und kann auf alle Arbeitsauslastungen wie zum Beispiel Audiokonferenzen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="52105-113">The Envision phase provides the foundation for the Office 365 customer journey and is applicable to all workloads such as Audio Conferencing.</span></span>

<span data-ttu-id="52105-114">In dieser Phase formulieren die jeweiligen Projektbeteiligten die Geschäftsziele und stellen Folgendes bereit: </span><span class="sxs-lookup"><span data-stu-id="52105-114">In this phase, business goals are captured, with relevant project stakeholders assembled, to ultimately deliver:</span></span>

-   <span data-ttu-id="52105-115">Ein umfassendes Erfolgskonzept mit Geschäftsanwendungsfällen, wichtigen Projektbeteiligen, Zielen und wesentlichen Ergebnissen, wichtigen Erfolgsindikatoren, Risiken, einer Einschätzung der Umgebung, Übernahmebereitschaft und Einsatzplanung.</span><span class="sxs-lookup"><span data-stu-id="52105-115">a high-level success plan that contains business use cases, key stakeholders, objectives and key results (OKRs), key success indicators (KSIs), risks, environmental assessment, adoption readiness, and operational plan.</span></span>

-   <span data-ttu-id="52105-116">Ein detaillierter Plan für die technische Implementierung der Audiokonferenzfunktion, um den gewünschten Endzustand zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="52105-116">and subsequently, a detailed Audio Conferencing technical implementation plan to achieve the desired end state.</span></span>

<a name="define-business-use-cases-for-audio-conferencing"></a><span data-ttu-id="52105-117">Definieren von Geschäftsanwendungsfällen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-117">Define business use cases for Audio Conferencing</span></span>
------------------------------------------------

<span data-ttu-id="52105-118">Mit Audiokonferenzen erhalten Organisationen weitere Einstiegspunkte zu geplanten Besprechungen, indem Teilnehmer über PSTN an Besprechungen teilnehmen können, wenn sie sich mit einem herkömmlichen Festnetz, PBX oder Mobiltelefonen einwählen.</span><span class="sxs-lookup"><span data-stu-id="52105-118">Audio Conferencing provides organizations with additional entry points to any scheduled meetings by allowing meeting participants to join via PSTN by dialing in using traditional landline, PBX, or mobile phones.</span></span>

<span data-ttu-id="52105-119">Dies ist hilfreich, wenn der Organisator oder die Teilnehmer nicht vor ihren Computern sitzen oder wenn die Datenverbindungen für VoIP-Kommunikation nicht verfügbar oder nicht zuverlässig sind – zum Beispiel an einem Remotestandort mit schlechter Netzabdeckung, bei Verbindungen über einen gebührenfreien, öffentlichen WLAN-Dienst mit eingeschränkter Bandbreite oder, wenn es Besprechungsteilnehmer bevorzugen, sich über einen ihnen zur Verfügung stehenden Telefonie-Endgeräten einwählen.</span><span class="sxs-lookup"><span data-stu-id="52105-119">This is useful when the organizer or participants are not in front of a computer, or when data connections are unavailable or unreliable to support voice communications—such as when in a remote area with spotty mobile data coverage, or if connected to a free, public Wi-Fi service with limited bandwidth, or when meeting participants prefer to dial in to the meeting using telephony endpoint readily accessible to them.</span></span>

<span data-ttu-id="52105-120">In diesem Schritt definieren die wichtigsten Projektbeteiligten Geschäftsanwendungsfälle, die die Implementierung von Audiokonferenzen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="52105-120">In this step, core project stakeholders will define business use cases that support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="52105-121">Mit Geschäftsanwendungsfällen werden die erwarteten und messbaren Geschäftsergebnisse definiert und dokumentiert. Dazu zählen:</span><span class="sxs-lookup"><span data-stu-id="52105-121">Business use cases are meant to define and document the expected and measurable business outcomes, and include the following:</span></span>

-   <span data-ttu-id="52105-122">Beschreibung des aktuellen Geschäftsprozesses</span><span class="sxs-lookup"><span data-stu-id="52105-122">Description of current business process.</span></span>

-   <span data-ttu-id="52105-123">Herausforderungen mit vorhandenen bereits definierten Geschäftsprozessen</span><span class="sxs-lookup"><span data-stu-id="52105-123">Challenges with existing business process defined.</span></span>

-   <span data-ttu-id="52105-124">Wie diesen Herausforderungen am besten begegnet werden kann</span><span class="sxs-lookup"><span data-stu-id="52105-124">How technology can help overcome these challenges.</span></span>

-   <span data-ttu-id="52105-125">Die erwarteten und messbaren Geschäftsergebnisse, wenn diese Herausforderungen gemeistert wurden</span><span class="sxs-lookup"><span data-stu-id="52105-125">The expected and measurable business outcome if these challenges are overcome.</span></span>

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><span data-ttu-id="52105-126"><strong>Beschreibung des aktuellen Geschäftsprozesses</strong></span><span class="sxs-lookup"><span data-stu-id="52105-126"><strong>Description of current business process</strong></span></span></p>
<p><span data-ttu-id="52105-127">Für interne Besprechungen und Besprechungen mit Dritten nutzt Contoso derzeit die von etablierten lokalen Telefonanbietern bereitgestellten PSTN-Konferenzdienste, die im Minutentakt abgerechnet werden.</span><span class="sxs-lookup"><span data-stu-id="52105-127">Contoso currently relies on PSTN conferencing services provided by the incumbent local telephony provider chargeable by meeting minutes for internal meetings and meetings involving external parties.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><span data-ttu-id="52105-128"><strong>Herausforderungen mit vorhandenen Geschäftsprozessen</strong></span><span class="sxs-lookup"><span data-stu-id="52105-128"><strong>Challenges with existing business process</strong></span></span></p>
<p><span data-ttu-id="52105-129">Contoso investiert jährlich rund 1 Million US-Dollar für den aktuellen PSTN-Konferenzdienst, wobei 75 % der Kosten auf interne Besprechungen zurückzuführen sind.</span><span class="sxs-lookup"><span data-stu-id="52105-129">Contoso spends roughly USD 1 million per year for the current PSTN conferencing service, with 75% of the cost incurred for internal meetings.</span></span></p>
<p><span data-ttu-id="52105-130">Die Verwendung von herkömmlichen Telefonie-Endpunkten für die Teilnahme an durch den PSTN-Konferenzdienst gehosteten Besprechungen ist nicht an das Konzept für die Organisation zur Übernahme von Teams als moderne Plattform für Kommunikation und Zusammenarbeit angepasst.</span><span class="sxs-lookup"><span data-stu-id="52105-130">The use of traditional telephony endpoints to join the meetings hosted by the PSTN conferencing service is not aligned with the plan for the organization to adopt Teams as modern communications and collaboration platform.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><span data-ttu-id="52105-131"><strong>Wie diesen Herausforderungen am besten begegnet werden kann</strong></span><span class="sxs-lookup"><span data-stu-id="52105-131"><strong>How technology can overcome these challenges</strong></span></span></p>
<p><span data-ttu-id="52105-132">Mit der Übernahme von Microsoft Teams als Plattform für Kommunikation und Zusammenarbeit wird von internen Benutzern erwartet, dass sie primär mit ihren PCs (mit optimierten Headsets und Geräten für Besprechungsräume) an Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="52105-132">With the adoption of Microsoft Teams as modern communications and collaboration platform, internal users are expected to primarily join meetings using their PCs equipped with optimized headsets and meeting room devices.</span></span> <span data-ttu-id="52105-133">Der Audiokonferenzdienst dient der Unterstützung von externen Teilnehmern oder der Unterstützung von Situationen, in denen die Verwendung der PC-Audiofunktionen für die internen Teilnehmer nicht vorteilhaft ist.</span><span class="sxs-lookup"><span data-stu-id="52105-133">Audio Conferencing service will be available to support external participants or to support situations where the use of PC audio is not favorable for the internal participants.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><span data-ttu-id="52105-134"><strong>Erwartete, messbare Geschäftsergebnisse</strong></span><span class="sxs-lookup"><span data-stu-id="52105-134"><strong>Expected, measurable, business outcomes</strong></span></span></p>
<p><span data-ttu-id="52105-135">Mit dem Wechsel zu Teams als moderne Plattform für Kommunikation und Zusammenarbeit in Kombination mit dem Audiokonferenzdienst werden die Kosten der Bereitstellung des PSTN-Konferenzdiensts erheblich reduziert. Die Einsparungen gehen sogar so weit, dass Contoso lediglich 20 % der jährlichen Kosten im Vergleich zum herkömmlichen PSTN-Konferenzdienst aufwenden muss.</span><span class="sxs-lookup"><span data-stu-id="52105-135">The move to Teams as modern communications and collaboration platform, combined with Audio Conferencing service, will greatly reduce the cost to deliver the PSTN conferencing service to the point that Contoso is expected to only spend approximately 20% of the annual cost of the existing PSTN conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-136">_Tabelle 1: Geschäftsanwendungsfall – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-136">_Table 1 Business use case example_</span></span>


<span data-ttu-id="52105-137">Zusätzlich zum Definieren von Geschäftsanwendungsfällen hilft eine Klarheit in Bezug auf den organisatorischen Geltungsbereich und die Projektzeitschiene in diesem Schritt, zum nächsten Schritt der Ausblick-Phase zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="52105-137">In addition to defining the business use cases, having a clarity around the organizational scope and project timelines at this step helps move onto the next step of the Envision phase.</span></span>

<a name="identify-key-stakeholders"></a><span data-ttu-id="52105-138">Identifizieren der wichtigsten Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="52105-138">Identify key stakeholders</span></span>
-------------------------

<span data-ttu-id="52105-139">Die im vorherigen Schritte definierten Geschäftsanwendungsfälle enthalten die Implementierung von Audiokonferenzen als organisatorischen Geltungsbereich, und basierend darauf kann eine umfassende Liste mit Projektbeteiligten erstellt werden, um die richtigen Personen in das Projekt einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="52105-139">The business use cases defined in the previous step will include organizational scope of Audio Conferencing implementation, and based on that, the comprehensive stakeholder matrix can be completed to include the right people to be involved in the project.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-140">Rolle</span><span class="sxs-lookup"><span data-stu-id="52105-140">Role</span></span></th>
<th align="left"><span data-ttu-id="52105-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52105-141">Description</span></span></th>
<th align="left"><span data-ttu-id="52105-142">Name, Kontaktinformationen, Standort</span><span class="sxs-lookup"><span data-stu-id="52105-142">Name, contact information, location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-143"><strong>Leitender Projektsponsor</strong></span><span class="sxs-lookup"><span data-stu-id="52105-143"><strong>Project Executive Sponsor</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-144">Hat höchste Entscheidungsbefugnis und Rechenschaftspflicht für das Projekt und die Bereitstellung von Projektzielen</span><span class="sxs-lookup"><span data-stu-id="52105-144">Ultimate authority and accountability for the project and delivery on project objectives</span></span></li>
<li><span data-ttu-id="52105-145">Bietet Unterstützung bei der Lösung der vom Projektleiter eskalierten Probleme</span><span class="sxs-lookup"><span data-stu-id="52105-145">Help resolve issues escalated by Project Lead</span></span></li>
<li><span data-ttu-id="52105-146">Bietet Unterstützung bei die Kommunikation innerhalb des Unternehmens </span><span class="sxs-lookup"><span data-stu-id="52105-146">Sponsors communication within the company about project goals</span></span></li>
<li><span data-ttu-id="52105-147">Ist für wichtige strategische Entscheidungen verantwortlich</span><span class="sxs-lookup"><span data-stu-id="52105-147">Responsible for making key strategic decisions</span></span></li>
<li><span data-ttu-id="52105-148">Trägt Verantwortung für die Verfügbarkeit der erforderlichen Ressourcen und das benötigte Budget</span><span class="sxs-lookup"><span data-stu-id="52105-148">Responsible for availability of required resources and budget</span></span></p>
<li><span data-ttu-id="52105-149">Verfasst vierteljährliche Geschäftsberichte</span><span class="sxs-lookup"><span data-stu-id="52105-149">Leading Quarterly Business Reviews (QBR)</span></span></li>
<li><span data-ttu-id="52105-150">Organisiert und unterstützt Sensibilisierungskampagnen</span><span class="sxs-lookup"><span data-stu-id="52105-150">Buy-In and support of awareness campaign effort</span></span></li>
<li><span data-ttu-id="52105-151">Ist Projektsponsor für das Programm-Rollout</span><span class="sxs-lookup"><span data-stu-id="52105-151">Serving as the Project Sponsor to the program rollout</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-152">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-152">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-153"><strong>Projektleiter</strong></span><span class="sxs-lookup"><span data-stu-id="52105-153"><strong>Project Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-154">Führt und leitet das Projektteam</span><span class="sxs-lookup"><span data-stu-id="52105-154">Managing and leading project team</span></span></li>
<li><span data-ttu-id="52105-155">Koordiniert die am Projekt beteiligten Partner und Arbeitsteams</span><span class="sxs-lookup"><span data-stu-id="52105-155">Coordinates partners and working teams engaged in the project</span></span></li>
<li><span data-ttu-id="52105-156">Ist für das Erstellen und Verwalten von Projektplänen verantwortlich, um die wesentlichen Quartalsergebnisse zu erzielen</span><span class="sxs-lookup"><span data-stu-id="52105-156">Accountable for creating and managing project plans to meet quarterly key results</span></span></li>
<li><span data-ttu-id="52105-157">Behebt funktionsübergreifende Probleme</span><span class="sxs-lookup"><span data-stu-id="52105-157">Resolving cross-functional issues</span></span></li>
<li><span data-ttu-id="52105-158">Erstellt einen regelmäßigen Rechenschaftsbericht für die Projektsponsoren</span><span class="sxs-lookup"><span data-stu-id="52105-158">Providing regular updates to the project sponsors</span></span></li>
<li><span data-ttu-id="52105-159">Bezieht Übernahmeaspekte in den fertigen Projektplan ein</span><span class="sxs-lookup"><span data-stu-id="52105-159">Incorporating Adoption aspects into the all-up project plan</span></span></li>
<li><span data-ttu-id="52105-160">Verfasst monatliche Geschäftsberichte als Grundlage für vierteljährliche Geschäftsberichte</span><span class="sxs-lookup"><span data-stu-id="52105-160">Leading Monthly Business and Operational Reviews (MBR), contributing to Quarterly Business Reviews</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-161">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-161">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-162"><strong>Leiter/Architekt für Zusammenarbeit</strong></span><span class="sxs-lookup"><span data-stu-id="52105-162"><strong>Collaboration Lead/Architect</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-163">Ist für die Ausführung der Zusammenarbeitsstrategie verantwortlich, die von den Führungskräften des Unternehmens definiert wird</span><span class="sxs-lookup"><span data-stu-id="52105-163">Responsible for execution on collaboration strategy defined by company executives</span></span></li>
<li><span data-ttu-id="52105-164">Analysiert und wählt Produkte für die Zusammenarbeit für das Unternehmen aus, das die Geschäftsziele erreicht</span><span class="sxs-lookup"><span data-stu-id="52105-164">Analyzing and choosing collaboration products for the company that meets business goals</span></span></li>
<li><span data-ttu-id="52105-165">Ist für die operationale Architektur von Produkten für die Zusammenarbeit verantwortlich</span><span class="sxs-lookup"><span data-stu-id="52105-165">Responsible for the design of the operations for collaboration products</span></span></li>
<li><span data-ttu-id="52105-166">Definiert operative und Support-Modelle</span><span class="sxs-lookup"><span data-stu-id="52105-166">Defines operation and support model</span></span></li>
<li><span data-ttu-id="52105-167">Liefert Beiträge für die monatlichen und vierteljährlichen Geschäftsberichte</span><span class="sxs-lookup"><span data-stu-id="52105-167">Contributing to Monthly and Quarterly Business Reviews</span></span></li><ul></td>
<td align="left"><span data-ttu-id="52105-168">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-168">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-169"><strong>Berater</strong></span><span class="sxs-lookup"><span data-stu-id="52105-169"><strong>Consultant</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-170">Ist für Konfigurationsdienste verantwortlich</span><span class="sxs-lookup"><span data-stu-id="52105-170">Responsible for configuration services</span></span></li>
<li><span data-ttu-id="52105-171">Liefert Beiträge zur Architektur der Gesamtlösung</span><span class="sxs-lookup"><span data-stu-id="52105-171">Contributes in overall solution architecture</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-172">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-172">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-173"><strong>Projektmanager</strong></span><span class="sxs-lookup"><span data-stu-id="52105-173"><strong>Project Manager</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-174">Entwickelt und verwaltet den Projektplan</span><span class="sxs-lookup"><span data-stu-id="52105-174">Developing and maintaining project plan</span></span></li>
<li><span data-ttu-id="52105-175">Verwaltet die Projektergebnisse in Bezug auf die Einhaltung des Projektplans und des Budgets</span><span class="sxs-lookup"><span data-stu-id="52105-175">Managing project deliverables in line with project plan and budget</span></span></li>
<li><span data-ttu-id="52105-176">Zeichnet Projektprobleme (zum Beispiel Eskalationen) auf und verwaltet diese</span><span class="sxs-lookup"><span data-stu-id="52105-176">Recording and managing project issues, including escalations</span></span></li>
<li><span data-ttu-id="52105-177">Tätigt wöchentliche Teamanrufe</span><span class="sxs-lookup"><span data-stu-id="52105-177">Conducting weekly stand up calls</span></span></li>
<li><span data-ttu-id="52105-178">Kontaktiert die leitenden Projektsponsoren und stellt aktuelle Informationen bereit</span><span class="sxs-lookup"><span data-stu-id="52105-178">Liaises with, and provides updates to project executive sponsors</span></span></li>
<li><span data-ttu-id="52105-179">Arbeitet mit dem Architekten zusammen, um den Change Management-Ansatz und die Kommunikationspläne zu definieren</span><span class="sxs-lookup"><span data-stu-id="52105-179">Working with the Architect to define the Change Management approach and Communication Plans</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-180">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-180">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-181"><strong>Experte für Change Management/Übernahme</strong></span><span class="sxs-lookup"><span data-stu-id="52105-181"><strong>Change Management/Adoption Specialist</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-182">Liefert Beiträge zu Übernahme- und Schulungsprozessen in der Entdeckungsphase</span><span class="sxs-lookup"><span data-stu-id="52105-182">Provide input on Discovery phase into adoption and training processes</span></span></li>
<li><span data-ttu-id="52105-183">Nimmt am Workshop für Übernahmestrategie teil</span><span class="sxs-lookup"><span data-stu-id="52105-183">Participate in adoption strategy workshop</span></span></li>
<li><span data-ttu-id="52105-184">Entwickelt die Übernahmestrategie und ist für diese verantwortlich</span><span class="sxs-lookup"><span data-stu-id="52105-184">Developing and responsible for adoption strategy</span></span></li>
<li><span data-ttu-id="52105-185">Entwickelt Kommunikationspläne und führt diese aus</span><span class="sxs-lookup"><span data-stu-id="52105-185">Developing and executing communication plan</span></span></li>
<li><span data-ttu-id="52105-186">Ist verantwortlich für die Bereitstellung von Schulungen für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="52105-186">Responsible for delivering trainings to end users</span></span></li>
<li><span data-ttu-id="52105-187">Sammelt Feedback und führt Umfragen durch</span><span class="sxs-lookup"><span data-stu-id="52105-187">Collect feedback and conduct surveys</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-188">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-188">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-189"><strong>Netzwerkleiter</strong></span><span class="sxs-lookup"><span data-stu-id="52105-189"><strong>Network Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-190">Liefert Beiträge zum Netzwerkdesign in der Entdeckungsphase </span><span class="sxs-lookup"><span data-stu-id="52105-190">Providing input on Discovery phase into network design</span></span></li>
<li><span data-ttu-id="52105-191">Nimmt an der Planung während des Ausblick-Workshops teil</span><span class="sxs-lookup"><span data-stu-id="52105-191">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="52105-192">Koordiniert die Arbeit des Netzwerkteams während der Projektausführung</span><span class="sxs-lookup"><span data-stu-id="52105-192">Coordinates work of networking team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-193">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-193">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-194"><strong>Leiter der Sicherheit</strong></span><span class="sxs-lookup"><span data-stu-id="52105-194"><strong>Security Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-195">Liefert Beiträge zu Übernahme- und Schulungsprozessen in der Entdeckungsphase</span><span class="sxs-lookup"><span data-stu-id="52105-195">Providing input on Discovery phase into security design and processes</span></span></li>
<li><span data-ttu-id="52105-196">Nimmt an der Planung während des Ausblick-Workshops teil</span><span class="sxs-lookup"><span data-stu-id="52105-196">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="52105-197">Koordiniert die Arbeit des Sicherheitsteams während der Projektausführung</span><span class="sxs-lookup"><span data-stu-id="52105-197">Coordinates work of security team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-198">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-198">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-199"><strong>Telefonie-Leiter</strong></span><span class="sxs-lookup"><span data-stu-id="52105-199"><strong>Telephony Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-200">Liefert Beiträge zum Telefonie-Design in der Entdeckungsphase</span><span class="sxs-lookup"><span data-stu-id="52105-200">Providing input on Discovery phase into telephony design</span></span></li>
<li><span data-ttu-id="52105-201">Nimmt an der Planung während des Ausblick-Workshops teil</span><span class="sxs-lookup"><span data-stu-id="52105-201">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="52105-202">Koordiniert die Arbeit des Telefonie-Teams während der Projektausführung</span><span class="sxs-lookup"><span data-stu-id="52105-202">Coordinates work of telephony team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-203">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-203">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-204"><strong>Desktop-Leiter</strong></span><span class="sxs-lookup"><span data-stu-id="52105-204"><strong>Desktop Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-205">Liefert Beiträge zu Client- und Updateprozessen in der Entdeckungsphase</span><span class="sxs-lookup"><span data-stu-id="52105-205">Providing input on Discovery phase into clients and update process</span></span></li>
<li><span data-ttu-id="52105-206">Nimmt an der Planung während des Ausblick-Workshops teil</span><span class="sxs-lookup"><span data-stu-id="52105-206">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="52105-207">Koordiniert die Arbeit des Desktop-Teams während der Projektausführung</span><span class="sxs-lookup"><span data-stu-id="52105-207">Coordinates work of desktop team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-208">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-208">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-209"><strong>Support-/Helpdesk-Leiter</strong></span><span class="sxs-lookup"><span data-stu-id="52105-209"><strong>Support/Help Desk Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-210">Liefert Beiträge zum operativen Modell und zum Support-Modell in der Entdeckungsphase</span><span class="sxs-lookup"><span data-stu-id="52105-210">Providing input on Discovery phase into operational and support model</span></span></li>
<li><span data-ttu-id="52105-211">Nimmt an der Planung während des Ausblick-Workshops teil</span><span class="sxs-lookup"><span data-stu-id="52105-211">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="52105-212">Nimmt an der Planung des Support-Modells teil</span><span class="sxs-lookup"><span data-stu-id="52105-212">Participating into support model planning</span></span></li>
<li><span data-ttu-id="52105-213">Koordiniert die Arbeit des Support-Teams/der Ressourcen während der Projektausführung</span><span class="sxs-lookup"><span data-stu-id="52105-213">Coordinates work of support teams/resources during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-214">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-214">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-215"><strong>Repräsentanten der Geschäftseinheiten</strong></span><span class="sxs-lookup"><span data-stu-id="52105-215"><strong>Business Unit Representatives</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-216">Liefern Beiträge zur Endbenutzer-basierten Übernahme von Anleitungen und Begleitmaterialien</span><span class="sxs-lookup"><span data-stu-id="52105-216">Contribute in End User based adoption guides and materials</span></span></li>
<li><span data-ttu-id="52105-217">Tragen zu Geschäftsanwendungsfällen bei und überprüfen diese</span><span class="sxs-lookup"><span data-stu-id="52105-217">Contribute to and review Business Use Cases</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-218">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-218">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-219"><strong>Bereitstellungsleiter</strong></span><span class="sxs-lookup"><span data-stu-id="52105-219"><strong>Deployment Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-220">Stellt sicher, dass die Systemvoraussetzungen erfüllt sind</span><span class="sxs-lookup"><span data-stu-id="52105-220">Ensure that deployment prerequisites are met</span></span></li>
<li><span data-ttu-id="52105-221">Leitet Kundenressourcen an, sich an der Vorbereitung und Bereitstellung von Aktivitäten in den einzelnen Phasen zu beteiligen</span><span class="sxs-lookup"><span data-stu-id="52105-221">Engage customer resources to engage on prepare and deploy stage activities</span></span></li>
<li><span data-ttu-id="52105-222">Nimmt an Besprechungen zur Überprüfung des Vorbereitungs- und Bereitstellungsstatus teil</span><span class="sxs-lookup"><span data-stu-id="52105-222">Participate in meetings to review prepare and deploy status</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-223">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-223">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-224"><strong>IT-Administratoren</strong></span><span class="sxs-lookup"><span data-stu-id="52105-224"><strong>IT Admins</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-225">IT-Experten, die für die Unterstützung in der Testplanung und -ausführung verantwortlich sind</span><span class="sxs-lookup"><span data-stu-id="52105-225">IT Pros responsible for assistance with test planning and execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-226">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-226">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-227"><strong>Leiter des Kundendiensts</strong></span><span class="sxs-lookup"><span data-stu-id="52105-227"><strong>Service Owner</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-228">Ist für den reibungslosen Ablauf des Audiokonferenzdiensts verantwortlich</span><span class="sxs-lookup"><span data-stu-id="52105-228">Is responsible for the operation of the Audio Conferencing service all up</span></span></li>
<li><span data-ttu-id="52105-229">Leiter des Audiokonferenzdiensts</span><span class="sxs-lookup"><span data-stu-id="52105-229">Owner of Audio Conferencing service</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-230">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-230">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-231"><strong>Qualitätspionier</strong></span><span class="sxs-lookup"><span data-stu-id="52105-231"><strong>Quality Champion</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-232">Trägt zur Verbesserung der Qualität, Verlässlichkeit und des Benutzerfeedbacks bei</span><span class="sxs-lookup"><span data-stu-id="52105-232">Drives quality, reliability and user feedback</span></span></li>
<li><span data-ttu-id="52105-233">Ermittelt Qualitätstrends und schafft Abhilfe bei Problemen mit den jeweiligen Teams</span><span class="sxs-lookup"><span data-stu-id="52105-233">Identifies the quality trends and drive remediation with the respective teams</span></span></li>
<li><span data-ttu-id="52105-234">Ist verantwortlich für die Berichterstattung zwischen dem Lenkungsteam und dem Führungsstab</span><span class="sxs-lookup"><span data-stu-id="52105-234">Reports through the steering committee back to leadership</span></span></li>
<li><span data-ttu-id="52105-235">Erstellt Berichte über Qualität, Verlässlichkeit und Verbraucherstimmung über „Meinen Anruf bewerten“ und „Net Promoter Score“</span><span class="sxs-lookup"><span data-stu-id="52105-235">Reports on quality, reliability, and user sentiment through Rate My Call and Net Promoter Score</span></span></li></ul></td>
<td align="left"><span data-ttu-id="52105-236">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-236">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-237">_Tabelle 2: Matrixvorlage für Projektbeteiligte – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-237">_Table 2 Stakeholder matrix template example_</span></span>


> [!NOTE]
> <span data-ttu-id="52105-238">Die Beispieltabelle oben und nachfolgende Tabellen in diesem Dokument dienen als Vorlage.</span><span class="sxs-lookup"><span data-stu-id="52105-238">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="52105-239">Der Hinweis „TBA“ (To Be Added, wird ergänzt) zeigt an, dass Sie hier Informationen als Teil Ihres Planungsprozesses eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="52105-239">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a><span data-ttu-id="52105-240">Definieren von Zielen und wesentlichen Ergebnissen, wichtigen Erfolgsindikatoren und Risiken</span><span class="sxs-lookup"><span data-stu-id="52105-240">Define objectives and key results, key success indicators, and risks</span></span>
--------------------------------------------------------------------

<span data-ttu-id="52105-241">Bei der Zusammenkunft der Projektbeteiligten können Geschäftsanwendungsfälle, organisatorische Geltungsbereiche und Projektzeitschienen in Ziele und wesentliche Ergebnisse übersetzt werden, und die Kennzahlen des Projekterfolgs können in einer Liste mit den wichtigen Erfolgsindikatoren festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="52105-241">With the project stakeholders assembled, business use cases, organizational scope and project timelines can be translated into objectives and key results (OKRs) and the measures of project success can be defined into a list of key success indicators (KSIs).</span></span>

<span data-ttu-id="52105-242">Durch die Teilnahme aller Projektbeteiligten bei der Festlegung der Ziele und wesentlichen Ergebnissen sowie der wichtigen Erfolgsindikatoren wird das Verantwortungsbewusstsein geschärft, und eine Anpassung an die organisatorischen Geschäftsanforderungen wird sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="52105-242">Full participation from project stakeholders when defining the OKRs and KSIs will ensure sense of ownership and they are aligned to organizational business requirements.</span></span>

<span data-ttu-id="52105-243">Ziele und wesentliche Ergebnisse enthalten die Liste der Ziele, die zu Projektbeginn festgelegt wurden. Sie enthalten unter anderem messbare Ergebnisse auf Quartalsbasis.</span><span class="sxs-lookup"><span data-stu-id="52105-243">OKRs will contain the list of objectives set in the beginning of the project, with measurable key results defined in a quarterly basis.</span></span> <span data-ttu-id="52105-244">Diese Kernergebnisse werden monatlich ausgewertet, um den Status des gesamten Projekts zu verfolgen. Des Weiteren kann basierend auf dem Fortschritt eine Anpassung der Quartalspläne nach Bedarf vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="52105-244">The key results are reviewed monthly to track status of the overall project, and based on progress, adjustment to the quarterly plans can be made as needed.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><p><span data-ttu-id="52105-245"><strong>Vision</strong>: Steigern der Produktivität durch Erhöhung der Office 365-Ausgaben</span><span class="sxs-lookup"><span data-stu-id="52105-245"><strong>Vision</strong>: Increase productivity by maximizing Office 365 investments</span></span></p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-246"><strong>Ziele</strong></span><span class="sxs-lookup"><span data-stu-id="52105-246"><strong>Objectives</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-247"><strong>Wesentliche Resultate</strong></span><span class="sxs-lookup"><span data-stu-id="52105-247"><strong>Key Results</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-248"><strong>Aufgabe</strong></span><span class="sxs-lookup"><span data-stu-id="52105-248"><strong>To Do</strong></span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-249">Bereitstellen von Audiokonferenzen in Teams gegen Ende des Geschäftsjahres 2018</span><span class="sxs-lookup"><span data-stu-id="52105-249">Deploy Audio Conferencing in Teams by end of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="52105-250">1. Quartal des Geschäftsjahres 2018: Globale Bereitstellung von Audiokonferenzen in Teams</span><span class="sxs-lookup"><span data-stu-id="52105-250">FY18Q1: Deploy Audio Conferencing in Teams globally</span></span></td>
<td align="left"><p><span data-ttu-id="52105-251">Ausblick</span><span class="sxs-lookup"><span data-stu-id="52105-251">Envision</span></span></p>
<ul><li><span data-ttu-id="52105-252">Erfolgsplan erstellen</span><span class="sxs-lookup"><span data-stu-id="52105-252">Create success plan</span></span></li>
<li><span data-ttu-id="52105-253">Detaillierten Plan für die technische Implementierung erstellen</span><span class="sxs-lookup"><span data-stu-id="52105-253">Create detailed technical implementation plan</span></span></li></ul>
<p><span data-ttu-id="52105-254">Onboarding</span><span class="sxs-lookup"><span data-stu-id="52105-254">Onboard</span></span></p>
<ul><li><span data-ttu-id="52105-255">Erfolgsplan ausführen</span><span class="sxs-lookup"><span data-stu-id="52105-255">Execute success plan</span></span></li>
<li><span data-ttu-id="52105-256">Plan für die technische Implementierung ausführen</span><span class="sxs-lookup"><span data-stu-id="52105-256">Execute technical implementation plan</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-257">Den Legacy-PSTN-Konferenzdienst zur Mitte des Finanzjahres 2018 deaktivieren</span><span class="sxs-lookup"><span data-stu-id="52105-257">Decommission legacy PSTN Conferencing service globally by mid of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="52105-258">2. Quartal des Finanzjahres 2018: Den Legacy-PSTN-Konferenzdienst deaktivieren</span><span class="sxs-lookup"><span data-stu-id="52105-258">FY18Q2: Decommission legacy PSTN Conferencing service globally</span></span></td>
<td align="left"><p><span data-ttu-id="52105-259">Höhere Wertschöpfung erzielen</span><span class="sxs-lookup"><span data-stu-id="52105-259">Drive Value</span></span></p>
<ul><li><span data-ttu-id="52105-260">Benutzerengagement verstärken und Übernahme vorantreiben</span><span class="sxs-lookup"><span data-stu-id="52105-260">Boost user engagement and drive adoption</span></span></li>
<li><span data-ttu-id="52105-261">Veränderungen vorbereiten und verwalten</span><span class="sxs-lookup"><span data-stu-id="52105-261">Manage and prepare for change</span></span></li>
<li><span data-ttu-id="52105-262">Erfolg messen und teilen und Durchlauf beschleunigen</span><span class="sxs-lookup"><span data-stu-id="52105-262">Measure, share success, and iterate</span></span></li></ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-263">_Tabelle 3: Ziele und wesentliche Ergebnisse – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-263">_Table 3 Example of OKRs_</span></span>


<span data-ttu-id="52105-264">Mit den wichtigen Erfolgsindikatoren werden die Qualität und der Erfolg der Kernergebnisse gemessen, und sie vervollständigen den binären Charakter von Zielen und wesentlichen Ergebnissen (erreicht oder nicht erreicht) durch detaillierte Aufschlüsselung von guten bzw. schlechten Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="52105-264">KSIs measure quality and success of the key results and complement the binary nature of OKRs (achieved or not achieved), by detailing the good and/or bad results.</span></span> <span data-ttu-id="52105-265">Bei der Definition der wichtigen Erfolgsindikatoren empfehlen wir, „spezifische, messbare, zuweisbare, realistische, zeitbezogene“ und INTELLIGENTE Kriterien zugrunde zu legen.</span><span class="sxs-lookup"><span data-stu-id="52105-265">When defining KSIs, we recommend leveraging the “specific, measurable, assignable, realistic, time-related” or SMART criteria.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-266">Typ</span><span class="sxs-lookup"><span data-stu-id="52105-266">Type</span></span></th>
<th align="left"><p><span data-ttu-id="52105-267">Fragen zu den wichtigen Erfolgsindikatoren &amp;</span><span class="sxs-lookup"><span data-stu-id="52105-267">KSI questions &amp;</span></span></p>
<p><span data-ttu-id="52105-268">Kriterien</span><span class="sxs-lookup"><span data-stu-id="52105-268">criteria</span></span></p></th>
<th align="left"><span data-ttu-id="52105-269">Messmethode</span><span class="sxs-lookup"><span data-stu-id="52105-269">How measured</span></span></th>
<th align="left"><span data-ttu-id="52105-270">Erfolgskriterien</span><span class="sxs-lookup"><span data-stu-id="52105-270">Success criteria</span></span></th>
<th align="left"><span data-ttu-id="52105-271">Bemessungszeitpunkt</span><span class="sxs-lookup"><span data-stu-id="52105-271">Measured</span></span></th>
<th align="left"><span data-ttu-id="52105-272">Verantwortlich</span><span class="sxs-lookup"><span data-stu-id="52105-272">Responsible</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-273"><strong>Verwendung/Übernahme</strong></span><span class="sxs-lookup"><span data-stu-id="52105-273"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-274">Anrufqualität entspricht der vorherigen Lösung oder übertrifft diese</span><span class="sxs-lookup"><span data-stu-id="52105-274">Call quality is equal to or better than the previous solution</span></span></td>
<td align="left"><span data-ttu-id="52105-275">Umfrage</span><span class="sxs-lookup"><span data-stu-id="52105-275">Survey page</span></span></td>
<td align="left"><span data-ttu-id="52105-276">Zustimmung oder starke Zustimmung bei 80 % der Benutzer </span><span class="sxs-lookup"><span data-stu-id="52105-276">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="52105-277">Nach der Aktivierung und vierteljährlich</span><span class="sxs-lookup"><span data-stu-id="52105-277">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="52105-278">IT-Team</span><span class="sxs-lookup"><span data-stu-id="52105-278">Information Technology team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-279"><strong>Verwendung/Übernahme</strong></span><span class="sxs-lookup"><span data-stu-id="52105-279"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-280">Teams hat den Kommunikationsprozess vereinfacht</span><span class="sxs-lookup"><span data-stu-id="52105-280">Teams made the communication process easier</span></span></td>
<td align="left"><span data-ttu-id="52105-281">Umfrage</span><span class="sxs-lookup"><span data-stu-id="52105-281">Survey page</span></span></td>
<td align="left"><span data-ttu-id="52105-282">Zustimmung oder starke Zustimmung bei 80 % der Benutzer </span><span class="sxs-lookup"><span data-stu-id="52105-282">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="52105-283">Nach der Aktivierung und vierteljährlich</span><span class="sxs-lookup"><span data-stu-id="52105-283">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="52105-284">Change Management-Team</span><span class="sxs-lookup"><span data-stu-id="52105-284">Change Management team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-285"><strong>Verwendung/Übernahme</strong></span><span class="sxs-lookup"><span data-stu-id="52105-285"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-286">Aktive Verwendung der Lösung durch die Benutzer</span><span class="sxs-lookup"><span data-stu-id="52105-286">Users actively use the solution</span></span></td>
<td align="left"><span data-ttu-id="52105-287">Office 365-Berichte, Anrufqualitäts-Dashboard</span><span class="sxs-lookup"><span data-stu-id="52105-287">Office 365 reports, Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="52105-288">80 % der Benutzer sind täglich aktiv</span><span class="sxs-lookup"><span data-stu-id="52105-288">80% of users are active daily users</span></span></td>
<td align="left"><span data-ttu-id="52105-289">Täglich</span><span class="sxs-lookup"><span data-stu-id="52105-289">Daily</span></span></td>
<td align="left"><span data-ttu-id="52105-290">Change Management-Team</span><span class="sxs-lookup"><span data-stu-id="52105-290">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-291"><strong>Nutzung/Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="52105-291"><strong>Usage/quality</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-292">Prozentsatz der Anrufe/Konferenzen mit schlechter Qualität sollte verringert werden</span><span class="sxs-lookup"><span data-stu-id="52105-292">Percentage of poor calls/conferences should be minimal</span></span></td>
<td align="left"><span data-ttu-id="52105-293">Anrufqualitäts-Dashboard</span><span class="sxs-lookup"><span data-stu-id="52105-293">Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="52105-294">&lt; 5 % Anrufe mit schlechter Qualität pro Monat</span><span class="sxs-lookup"><span data-stu-id="52105-294">&lt; 5% of poor calls per month</span></span></td>
<td align="left"><span data-ttu-id="52105-295">Täglich</span><span class="sxs-lookup"><span data-stu-id="52105-295">Daily</span></span></td>
<td align="left"><span data-ttu-id="52105-296">IT-Team</span><span class="sxs-lookup"><span data-stu-id="52105-296">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-297"><strong>Nutzung/Support</strong></span><span class="sxs-lookup"><span data-stu-id="52105-297"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-298">Ich weiß, wo ich technischen Support erhalte</span><span class="sxs-lookup"><span data-stu-id="52105-298">I know how to get technical support</span></span></td>
<td align="left"><span data-ttu-id="52105-299">Umfrage</span><span class="sxs-lookup"><span data-stu-id="52105-299">Survey page</span></span></td>
<td align="left"><span data-ttu-id="52105-300">Zustimmung oder starke Zustimmung bei 90% der Benutzer</span><span class="sxs-lookup"><span data-stu-id="52105-300">90% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="52105-301">Nach der Aktivierung und vierteljährlich</span><span class="sxs-lookup"><span data-stu-id="52105-301">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="52105-302">Change Management-Team</span><span class="sxs-lookup"><span data-stu-id="52105-302">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-303"><strong>Nutzung/Support</strong></span><span class="sxs-lookup"><span data-stu-id="52105-303"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-304">Ich bin zufrieden mit der Qualität des technischen Supports</span><span class="sxs-lookup"><span data-stu-id="52105-304">I am satisfied with the quality of technical support</span></span></td>
<td align="left"><span data-ttu-id="52105-305">Umfrage</span><span class="sxs-lookup"><span data-stu-id="52105-305">Survey page</span></span></td>
<td align="left"><span data-ttu-id="52105-306">Zustimmung oder starke Zustimmung bei 80 % der Benutzer </span><span class="sxs-lookup"><span data-stu-id="52105-306">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="52105-307">Nach jedem Vorfall</span><span class="sxs-lookup"><span data-stu-id="52105-307">After each incident</span></span></td>
<td align="left"><span data-ttu-id="52105-308">IT-Team</span><span class="sxs-lookup"><span data-stu-id="52105-308">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-309"><strong>Finanzen</strong></span><span class="sxs-lookup"><span data-stu-id="52105-309"><strong>Financial</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-310">Weniger Minuten mit Legacy-Konferenzlösung</span><span class="sxs-lookup"><span data-stu-id="52105-310">Reduction of legacy conferencing minutes</span></span></td>
<td align="left"><span data-ttu-id="52105-311">Finanzsystem</span><span class="sxs-lookup"><span data-stu-id="52105-311">Financial system</span></span></td>
<td align="left"><span data-ttu-id="52105-312">Definierte Rendite erzielen</span><span class="sxs-lookup"><span data-stu-id="52105-312">Meet defined ROI</span></span></td>
<td align="left"><span data-ttu-id="52105-313">Basierend auf Rendite</span><span class="sxs-lookup"><span data-stu-id="52105-313">Based on ROI</span></span></td>
<td align="left"><span data-ttu-id="52105-314">Change Management-Team</span><span class="sxs-lookup"><span data-stu-id="52105-314">Change Management team</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-315">_Tabelle 4: Wichtige Erfolgsindikatoren – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-315">_Table 4 Example of KSIs_</span></span>


<span data-ttu-id="52105-316">Als Teil dieser Übung müssen Sie Geschäftsrisiken sowie einen Risikominderungsplan für jedes erkannte Risiko definieren.</span><span class="sxs-lookup"><span data-stu-id="52105-316">You need to identify business risks as part of this exercise and define a mitigation plan for each identified risk.</span></span> <span data-ttu-id="52105-317">Diese Informationen können in einem Risikoplan erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="52105-317">This information can be captured into a risk plan.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-318">Risiko</span><span class="sxs-lookup"><span data-stu-id="52105-318">Risk</span></span></th>
<th align="left"><span data-ttu-id="52105-319">Wahrscheinlichkeit</span><span class="sxs-lookup"><span data-stu-id="52105-319">Likelihood</span></span></th>
<th align="left"><span data-ttu-id="52105-320">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="52105-320">Impact</span></span></th>
<th align="left"><span data-ttu-id="52105-321">Gesamt</span><span class="sxs-lookup"><span data-stu-id="52105-321">Overall</span></span></th>
<th align="left"><span data-ttu-id="52105-322">Risikominderungsplan</span><span class="sxs-lookup"><span data-stu-id="52105-322">Mitigation plan</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-323">Bei der bevorstehenden Fusion werden bis zu 1.000 Personen dazukommen</span><span class="sxs-lookup"><span data-stu-id="52105-323">Upcoming merger will add up to 1,000 people</span></span></td>
<td align="left"><span data-ttu-id="52105-324">Hoch</span><span class="sxs-lookup"><span data-stu-id="52105-324">High</span></span></td>
<td align="left"><span data-ttu-id="52105-325">Hoch</span><span class="sxs-lookup"><span data-stu-id="52105-325">High</span></span></td>
<td align="left"><span data-ttu-id="52105-326">Hoch</span><span class="sxs-lookup"><span data-stu-id="52105-326">High</span></span></td>
<td align="left"><p><span data-ttu-id="52105-327">Separate Ziele und wesentliche Ergebnisse mit eigenem Prozess (Ausblick, Onboarding und Wertschöpfung) für fusioniertes Unternehmen </span><span class="sxs-lookup"><span data-stu-id="52105-327">For merged companies, separate OKR with own process (Envision, Onboard, Drive Value)</span></span></p>
<p><span data-ttu-id="52105-328">Beziehen Sie diesen Prozess nicht in vorhandene Ziele und wesentliche Ergebnisse ein.</span><span class="sxs-lookup"><span data-stu-id="52105-328">Do not include them in existing OKRs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-329">Die Portierung von Telefonnummern verzögert den Projektabschluss.</span><span class="sxs-lookup"><span data-stu-id="52105-329">Telephone number porting will delay project completion</span></span></td>
<td align="left"><span data-ttu-id="52105-330">Hoch</span><span class="sxs-lookup"><span data-stu-id="52105-330">High</span></span></td>
<td align="left"><span data-ttu-id="52105-331">Hoch</span><span class="sxs-lookup"><span data-stu-id="52105-331">High</span></span></td>
<td align="left"><span data-ttu-id="52105-332">Hoch</span><span class="sxs-lookup"><span data-stu-id="52105-332">High</span></span></td>
<td align="left"><p><span data-ttu-id="52105-333">Bereiten Sie frühzeitig alle erforderlichen Informationen zur Unterstützung der Portierung von Telefonnummern vor (z. B. Kundendiensteintrag, Rechnungsdetails, schriftliche Vollmacht).</span><span class="sxs-lookup"><span data-stu-id="52105-333">Prepare all the required information to support telephone number porting ahead of time (i.e.: customer service record, billing details, Letter of Authorization)</span></span></p>
<p><span data-ttu-id="52105-334">Passen Sie die Zeitschiene für das Projekt an, um die Dauer für die Portierung der Telefonnummern zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="52105-334">Adjust project timeline to accommodate turnaround time of telephone number porting execution</span></span></p>
<p><span data-ttu-id="52105-335">Teilen Sie den externen Teilnehmern die neuen Einwahlkonferenznummern mit.</span><span class="sxs-lookup"><span data-stu-id="52105-335">Communicate the use of new dial-in conferencing numbers to external participants</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-336">Geplante Umgestaltung des Netzwerks</span><span class="sxs-lookup"><span data-stu-id="52105-336">Planned network redesign</span></span></td>
<td align="left"><span data-ttu-id="52105-337">Hoch</span><span class="sxs-lookup"><span data-stu-id="52105-337">High</span></span></td>
<td align="left"><span data-ttu-id="52105-338">Mittel</span><span class="sxs-lookup"><span data-stu-id="52105-338">Medium</span></span></td>
<td align="left"><span data-ttu-id="52105-339">Mittel</span><span class="sxs-lookup"><span data-stu-id="52105-339">Medium</span></span></td>
<td align="left"><span data-ttu-id="52105-340">Führen Sie vor der Implementierung von Teams als moderne Plattform für Kommunikation und Zusammenarbeit eine Auswertung der Netzwerkbereitschaft für Websites durch, die im Geltungsbereich des Projekts liegen.</span><span class="sxs-lookup"><span data-stu-id="52105-340">Before implementing Teams as modern communications and collaboration platform, run network readiness assessment for sites in scope of the project</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-341">_Tabelle 5: Risikoplan – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-341">_Table 5 Risk plan example_</span></span>


<a name="assess-environment-and-evaluate-adoption-readiness"></a><span data-ttu-id="52105-342">Bewerten der Umgebung und Überprüfen der Übernahmebereitschaft</span><span class="sxs-lookup"><span data-stu-id="52105-342">Assess environment and evaluate adoption readiness</span></span>
--------------------------------------------------

<span data-ttu-id="52105-343">Um die gewünschten Ziele und wesentlichen Ergebnisse zu erreichen, müssen Sie möglicherweise die allgemeine Architektur der Lösung definieren.</span><span class="sxs-lookup"><span data-stu-id="52105-343">To achieve the intended OKRs, you may have to define the high-level architecture of the solution.</span></span> <span data-ttu-id="52105-344">Sie müssen Ihre Umgebung sehr gründlich erkunden, um alle Aspekte der IT- und Telefonie-Infrastruktur, des Netzwerks und des Betriebs auswerten zu können.</span><span class="sxs-lookup"><span data-stu-id="52105-344">It takes environmental discovery to evaluate all aspects relating to IT and telephony infrastructure, networking, and operations.</span></span>

<span data-ttu-id="52105-345">Alle Angelegenheiten bezüglich Endbenutzer-Computing wie die Auswertung der einsatzfähigen PCs und Mobilgeräten zwecks Unterstützung von Audiokonferenz-Geschäftsanwendungsfällen – von Hardwareanforderungen bis Softwareanforderungen – sind Teil der Erkundung der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="52105-345">All matters related to end-user computing, such as readiness assessment of the personal computers and mobile devices to support Audio Conferencing business use cases, from hardware requirements to software requirements, will be included as part of the environmental discovery.</span></span>

<span data-ttu-id="52105-346">Bei der Erkundung der Umgebung kann auch festgestellt werden, ob es Anforderungen für die [Portierung von Telefonnummern nach Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e) gibt.</span><span class="sxs-lookup"><span data-stu-id="52105-346">Environmental discovery can also uncover if there are requirements to [transfer phone numbers to Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span> <span data-ttu-id="52105-347">Dies hilft Ihrer Organisation, den Projektplan entsprechend anzupassen und die für die Nummernportierung notwendigen Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="52105-347">This will help your organization to adjust the project plan accordingly and prepare the necessary information required for number porting.</span></span> <span data-ttu-id="52105-348">Sie können die Umgebung erkunden, indem Sie den folgenden [Fragebogen](https://go.microsoft.com/fwlink/?linkid=858995) ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="52105-348">You can perform environmental discovery by leveraging the following [questionnaire](https://go.microsoft.com/fwlink/?linkid=858995).</span></span>

<span data-ttu-id="52105-349">Bei der Erkundung der Umgebung muss die Bereitschaft des Netzwerks bewertet werden, um sicherzustellen, dass das Netzwerk in der Lage ist, die Implementierung des Audiokonferenzdiensts zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="52105-349">Environmental discovery must include network readiness assessment to ensure the network is ready to support the implementation of the Audio Conferencing service.</span></span>

<span data-ttu-id="52105-350">Die Netzwerkbereitschaft zur Unterstützung des Audiokonferenzdiensts kann durch die durch die Erkundung des Netzwerks gesammelten Informationen ermittelt werden. Diese Informationen umfassen Details zur Internetkonnektivität und WAN-Topologie, Websitelinks, verfügbare Bandbreite und Personenanalysedaten, die mit dem [My Advisor Network Planner-Tool](https://go.microsoft.com/fwlink/?linkid=858999) in eine erwartete Nutzung der einzelnen Arbeitsauslastungen übersetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="52105-350">Network readiness to support the Audio Conferencing service can be determined by leveraging the information captured through the environmental discovery (such as details of internet connectivity and WAN topology, site links, available bandwidth, and persona analysis data (that can be translated into an expected usage of each workload) into the [My Advisor Network Planner tool](https://go.microsoft.com/fwlink/?linkid=858999).</span></span> <span data-ttu-id="52105-351">Um die Netzwerkbereitschaft noch genauer zu ermitteln, kann eine Simulation von Mediendatenverkehr in Echtzeit mit den von [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) oder [Partnern von Network Readiness Assessment-Tools](https://go.microsoft.com/fwlink/?linkid=859003) bereitgestellten Lösungen durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52105-351">To further confirm network readiness, real-time media traffic simulation can be performed using the solutions provided by [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) or by [Network Readiness Assessment tools partners](https://go.microsoft.com/fwlink/?linkid=859003).</span></span>

<span data-ttu-id="52105-352">Die Ergebnisse der Auswertung der Netzwerkbereitschaft zeichnen ein klares Bild der für eine erfolgreiche Implementierung der Audiokonferenzlösung erforderlichen Netzwerkoptimierung sowie Verbesserungsmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="52105-352">The results of the Network Readiness Assessment will paint a clearer picture of the required network optimization or remediation required for the success of Audio Conferencing implementation.</span></span>

<span data-ttu-id="52105-353">Die Übernahmebereitschaft kann anhand der Ausführung einer Personenanalyse durchgeführt werden, um eine Liste der Personen in Ihrer Organisation zu erstellen, die für die Implementierung des Audiokonferenzdiensts in Frage kommen.</span><span class="sxs-lookup"><span data-stu-id="52105-353">Adoption readiness can be evaluated by executing persona analysis to come up with a list of personas in the organization who can be targeted for the implementation of Audio Conferencing service.</span></span> <span data-ttu-id="52105-354">Die Personenanalyse umfasst die Ermittlung weiterer Peripheriegeräte und sonstigen Geräten, die für die Erzielung der gewünschten Geschäftsergebnisse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="52105-354">The persona analysis includes the identification of additional peripherals or devices required to realize the intended business outcomes.</span></span>

<span data-ttu-id="52105-355">Zur Ausführung einer Personenanalyse können Sie einen Workshop durchführen, indem Sie die jeweiligen Projektbeteiligten einbeziehen und die Workshop-Folie [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) und die [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006) verwenden.</span><span class="sxs-lookup"><span data-stu-id="52105-355">To perform persona analysis, you can conduct a workshop by involving relevant project stakeholders, leveraging the [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) workshop deck and [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006).</span></span> <span data-ttu-id="52105-356">Das Ergebnis des Personenanalyse-Workshops kann mit der Vorlage [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007) in einem Bericht zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="52105-356">The result of persona analysis workshop can be summarized into a report using the [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007) template.</span></span>


> [!NOTE]
> <span data-ttu-id="52105-357">Obwohl die Discovery Questionnaire- und die Persona Analysis-Beispiele zunächst für Skype for Business Online geschrieben wurden, sind die meisten Inhalte auch auf Teams übertragbar.</span><span class="sxs-lookup"><span data-stu-id="52105-357">While the Discovery Questionnaire and Persona Analysis examples were initially written for Skype for Business Online, a majority of the content is relevant to Teams.</span></span> <span data-ttu-id="52105-358">Sie können Punkte, die für Ihre Projektziele nicht relevant sind, gerne ändern oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="52105-358">Feel free to modify and remove items that are not relevant to the project goals.</span></span>


<span data-ttu-id="52105-359">Sie können die technischen Risiken als Teil einer Auswertung der Umgebung und Bewertung der Übernahmebereitschaft ermitteln und einen Plan zur Abhilfe für jedes erkannte Risiko entwickeln.</span><span class="sxs-lookup"><span data-stu-id="52105-359">You can identify technical risks as part of an environmental assessment and adoption readiness evaluation and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="52105-360">Diese Informationen sollten als Teil des Risikoplans berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="52105-360">This information should be incorporated as part of the risk plan.</span></span>

<a name="map-operational-roles"></a><span data-ttu-id="52105-361">Zuordnen von operativen Rollen</span><span class="sxs-lookup"><span data-stu-id="52105-361">Map operational roles</span></span>
---------------------

<span data-ttu-id="52105-362">Die Planung der Ausführung und die Zusammenstellung des Teams, das den Audiokonferenzdienst ausführt, ist ein wichtiger Schritt, da die Ausführung beginnen muss, wenn die ersten Teilnehmer des Pilotprojekts aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="52105-362">Planning for operations and identifying the teams that will operate the Audio Conferencing service is an important step, as operations must start when the first pilot users are enabled.</span></span> <span data-ttu-id="52105-363">Jedes zusammengestellte Team muss die angegebenen Aufgaben und Verantwortlichkeiten prüfen und diesen zustimmen und mit der Vorbereitung der Ausführung des Audiokonferenzdiensts beginnen.</span><span class="sxs-lookup"><span data-stu-id="52105-363">Each identified team must review and agree on the tasks and responsibilities identified and start the preparation to operate the Audio Conferencing service.</span></span> <span data-ttu-id="52105-364">Die Vorbereitung kann Schulungen, die Bewertung der Bereitschaft, die Einbeziehung zusätzlicher Mitarbeiter oder die Verpflichtung von externen Anbietern zur Bereitstellung des Diensts umfassen.</span><span class="sxs-lookup"><span data-stu-id="52105-364">The preparation might include training and readiness, additional staffing, or ensuring external providers are set up to deliver the service.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-365">Operative Rolle</span><span class="sxs-lookup"><span data-stu-id="52105-365">Operational Role</span></span></th>
<th align="left"><span data-ttu-id="52105-366">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52105-366">Description</span></span></th>
<th align="left"><span data-ttu-id="52105-367">Team</span><span class="sxs-lookup"><span data-stu-id="52105-367">Team Member</span></span></th>
<th align="left"><span data-ttu-id="52105-368">Kontaktdetails</span><span class="sxs-lookup"><span data-stu-id="52105-368">Contact Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-369">Leiter des Kundendiensts</span><span class="sxs-lookup"><span data-stu-id="52105-369">Service Owner</span></span></td>
<td align="left"><span data-ttu-id="52105-370">Diensteigentümer, Schnittstelle zu Geschäftsabteilungen, Strategie</span><span class="sxs-lookup"><span data-stu-id="52105-370">Service owner, interface to business divisions, strategy</span></span></td>
<td align="left"><span data-ttu-id="52105-371">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-371">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-372">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-372">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-373">Aufgaben für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-373">Audio Conferencing Operations</span></span></td>
<td align="left"><span data-ttu-id="52105-374">Tägliche Aufgaben, Verschieben/Hinzufügen/Ändern von Benutzer- und Gerätekonten, Überwachung</span><span class="sxs-lookup"><span data-stu-id="52105-374">Daily operations, user and device account move/add/change, monitoring</span></span></td>
<td align="left"><span data-ttu-id="52105-375">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-375">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-376">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-376">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-377">Mandantenadministrator</span><span class="sxs-lookup"><span data-stu-id="52105-377">Office 365 Tenant Admin</span></span></td>
<td align="left"><span data-ttu-id="52105-378">Ändern von mandantenweiten Einstellungen, Aktivieren von neuen Funktionen</span><span class="sxs-lookup"><span data-stu-id="52105-378">Change tenant-wide settings, enable new features</span></span></td>
<td align="left"><span data-ttu-id="52105-379">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-379">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-380">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-380">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-381">Helpdesk</span><span class="sxs-lookup"><span data-stu-id="52105-381">Help Desk.</span></span></td>
<td align="left"><span data-ttu-id="52105-382">Support-Schnittstelle für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="52105-382">Interface for end-users to get support</span></span></td>
<td align="left"><span data-ttu-id="52105-383">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-383">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-384">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-384">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-385">Netzwerkaufgaben</span><span class="sxs-lookup"><span data-stu-id="52105-385">Network Operations</span></span></td>
<td align="left"><span data-ttu-id="52105-386">Ausführung von LAN, WAN, WLAN und Internetzugriff</span><span class="sxs-lookup"><span data-stu-id="52105-386">Runs LAN, WAN, Wi-Fi, and Internet Access</span></span></td>
<td align="left"><span data-ttu-id="52105-387">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-387">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-388">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-388">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-389">Client- &amp; Endgeräte-Team</span><span class="sxs-lookup"><span data-stu-id="52105-389">Client &amp; Endpoints Team</span></span></td>
<td align="left"><span data-ttu-id="52105-390">Verwalten von Desktopbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="52105-390">Manage desktop deployments</span></span></td>
<td align="left"><span data-ttu-id="52105-391">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-391">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-392">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-392">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-393">Ermitteln von Aufgaben</span><span class="sxs-lookup"><span data-stu-id="52105-393">Identity Operations</span></span></td>
<td align="left"><span data-ttu-id="52105-394">Verwalten der Identitätsinfrastruktur (AD, ADFS, Azure AD)</span><span class="sxs-lookup"><span data-stu-id="52105-394">Manage identity infrastructure (AD, ADFS, Azure AD)</span></span></td>
<td align="left"><span data-ttu-id="52105-395">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-395">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-396">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-396">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-397">Übernahme/Change Management</span><span class="sxs-lookup"><span data-stu-id="52105-397">Adoption/change management</span></span></td>
<td align="left"><span data-ttu-id="52105-398">Sensibilisierung, Schulung und Übernahme für die Lösung</span><span class="sxs-lookup"><span data-stu-id="52105-398">Manage awareness, training and adoption for the solution</span></span></td>
<td align="left"><span data-ttu-id="52105-399">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-399">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-400">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-400">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-401">Exchange-Aufgaben</span><span class="sxs-lookup"><span data-stu-id="52105-401">Exchange Operations</span></span></td>
<td align="left"><span data-ttu-id="52105-402">Verwalten der Exchange-Umgebung</span><span class="sxs-lookup"><span data-stu-id="52105-402">Manages the Exchange environment</span></span></td>
<td align="left"><span data-ttu-id="52105-403">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-403">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-404">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-404">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-405">_Tabelle 6: Zuordnung der operativen Rolle – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-405">_Table 6 Example of operational roles mapping_</span></span>


<span data-ttu-id="52105-406">Um die detailliertere Zuordnung der operativen Rollen zu vereinfachen (einschließlich der mit jeder operativen Rolle verbundenen Aufgaben), können Sie das [Operational Role Mapping Workbook](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) verwenden, um die Details zu erfassen, die Ihnen einen Überblick über die Rollen und Verantwortlichkeiten für die Unterstützung des Audiokonferenzdiensts bieten.</span><span class="sxs-lookup"><span data-stu-id="52105-406">To facilitate a more detailed operational roles mapping, including the tasks associated with each operational role, you can use the [Operational Role Mapping Workbook](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) to capture the details that will provide the clarity around roles and responsibilities to support Audio Conferencing service.</span></span>

<a name="document-success-plan"></a><span data-ttu-id="52105-407">Dokumentieren des Erfolgsplans</span><span class="sxs-lookup"><span data-stu-id="52105-407">Document success plan</span></span>
---------------------

<span data-ttu-id="52105-408">Ein Erfolgsplan ist die in der Phase Ausblick erstellte Dokumentation, die aus dem Geschäftsszenario, der Bereitschaft für den Dienst, dem Übernahme- und Aufgabenplan besteht.</span><span class="sxs-lookup"><span data-stu-id="52105-408">A success plan is the documentation created in the Envision phase that consists of business case, service readiness, adoption plan, and operational plan.</span></span>

<span data-ttu-id="52105-409">Der Erfolgsplan stattet das Projektteam – das FastTrack oder einen Bereitstellungspartner enthalten kann – mit ausreichend Informationen aus, um die Ziele der Organisation mit dem Audiokonferenzdienst zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="52105-409">The success plan will provide the project team, which can include FastTrack or deployment partner, with sufficient information to realize the organization’s goals with Audio Conferencing service.</span></span>

<span data-ttu-id="52105-410">In der Regel enthält ein Erfolgsplan die folgenden Hauptabschnitte:</span><span class="sxs-lookup"><span data-stu-id="52105-410">In general, a success plan will contain the following main sections:</span></span>

-   <span data-ttu-id="52105-411">Geschäftsszenario</span><span class="sxs-lookup"><span data-stu-id="52105-411">Business case</span></span>

-   <span data-ttu-id="52105-412">Bereitschaft für den Dienst</span><span class="sxs-lookup"><span data-stu-id="52105-412">Service readiness</span></span>

-   <span data-ttu-id="52105-413">Übernahmeplan</span><span class="sxs-lookup"><span data-stu-id="52105-413">Adoption plan</span></span>

-   <span data-ttu-id="52105-414">Aufgabenplan</span><span class="sxs-lookup"><span data-stu-id="52105-414">Operational plan</span></span>

### <a name="business-case"></a><span data-ttu-id="52105-415">Geschäftsszenario</span><span class="sxs-lookup"><span data-stu-id="52105-415">Business case</span></span>

<span data-ttu-id="52105-416">Geschäftsanwendungsfälle, Projektbeteiligte, wesentliche Ergebnisse und wichtige Erfolgsindikatoren, Risiken und Projektzeitschienen bilden normalerweise die für ein Geschäftsszenario erforderlichen Informationen.</span><span class="sxs-lookup"><span data-stu-id="52105-416">Business use cases, stakeholders, OKRs and KSIs, risks, and project timelines typically make up the bulk of information required for a business case.</span></span> <span data-ttu-id="52105-417">Sie müssen sie als Teil des Erfolgsplans dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="52105-417">You need to document them as part of the success plan.</span></span>

### <a name="service-readiness"></a><span data-ttu-id="52105-418">Bereitschaft für den Dienst</span><span class="sxs-lookup"><span data-stu-id="52105-418">Service readiness</span></span>

<span data-ttu-id="52105-419">Die Auswertung der Umgebung bietet erste Informationen, die zur Einschätzung der technischen Bereitschaft für die Implementierung des Audiokonferenzdiensts erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="52105-419">Environmental assessment provides the initial information required to determine technical readiness for the organization to implement Audio Conferencing.</span></span>

<span data-ttu-id="52105-420">Enthalten hier ist der Plan zur Adressierung der Bereiche, für die aufgrund der Auswertung der Umgebung Verbesserungsmaßnahmen durchgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="52105-420">Included here is the plan to address areas needing remediation discovered through environmental assessment.</span></span> <span data-ttu-id="52105-421">Sie müssen die Auswertung der Dienstbereitschaft und den Wartungsplan als Teil des Erfolgsplans einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="52105-421">You need to include the service readiness assessment and remediation plan as part of the success plan.</span></span>

### <a name="adoption-plan"></a><span data-ttu-id="52105-422">Übernahmeplan</span><span class="sxs-lookup"><span data-stu-id="52105-422">Adoption plan</span></span>

<span data-ttu-id="52105-423">Nach der Auswertung der Übernahmebereitschaft muss das Projektteam eine weitere detaillierte Planung vornehmen. Hierzu zählen umfassende Kommunikationspläne, ein Schulungsplan sowie Übernahmeaktivitäten vor, während und nach der Einführung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="52105-423">Following an adoption readiness assessment, further detailed planning must be completed for the project team to come up with a comprehensive set of communication plans, training plan, and pre-launch, at-launch, and post-launch adoption activities.</span></span>

<span data-ttu-id="52105-424">Ressourcen zur Unterstützung der Übernahmeaktivitäten wie Flyer, Willkommmens-E-Mails und Schulungsmaterialien sowie alle für die Anforderungen der Organisation notwendigen Anpassungen zählen zu diesem Schritt.</span><span class="sxs-lookup"><span data-stu-id="52105-424">Resources to support adoption activities such as flyers, welcome emails, and training materials are identified at this step, along with any customizations needed to meet organizational requirements.</span></span>

<span data-ttu-id="52105-425">Die Vorlagen für Übernahmeaktivitäten sind [hier](https://www.microsoft.com/download/details.aspx?id=54244) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52105-425">The templates for adoption activities are available [here](https://www.microsoft.com/download/details.aspx?id=54244).</span></span>

### <a name="operational-plan"></a><span data-ttu-id="52105-426">Aufgabenplan</span><span class="sxs-lookup"><span data-stu-id="52105-426">Operational plan</span></span>

<span data-ttu-id="52105-427">Bei der Zuordnung von operativen Rollen werden Rollen und Verantwortlichkeiten sowie die jeder operativen Rolle zugewiesenen Teams definiert, um die Implementierung des Audiokonferenzdiensts zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="52105-427">Operational roles mapping exercise will establish the roles and responsibilities, and the teams assigned to each operational role to support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="52105-428">Sie müssen diesen Schritt abschließen und den operativen Plan als Teil des Erfolgsplans berücksichtigen, um die operative Bereitschaft der Lösung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="52105-428">You need to complete this and include the operational plan as part of the success plan to ensure operational readiness of the solution.</span></span>

<span data-ttu-id="52105-429">Planen von Audiokonferenzen in Teams  <a name="Planning_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="52105-429">Planning for Audio Conferencing in Teams  <a name="Planning_AudioConferencing"> </a></span></span>
========================================

<span data-ttu-id="52105-430">Um die Implementierung von Audiokonferenzen in Teams zu planen, müssen Sie frühzeitig eine Reihe von Entscheidungen treffen, um Ihre Organisation auf die Implementierung einer Lösung besser vorzubereiten, die die Geschäfsanforderungen erfüllen muss.</span><span class="sxs-lookup"><span data-stu-id="52105-430">To plan for the implementation of Audio Conferencing in Teams, a series of decisions must be made ahead of time to better prepare your organization to implement a solution that meets business requirements.</span></span> <span data-ttu-id="52105-431">Diese Entscheidungen werden in einem Plan zur technischen Implementierung dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="52105-431">These decisions will be documented into a technical implementation plan.</span></span>

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a><span data-ttu-id="52105-432">Verfügbarkeit von Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-432">Availability of Audio Conferencing</span></span>

<span data-ttu-id="52105-433">Audiokonferenzen sind in diesen [Ländern und Regionen](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52105-433">Audio Conferencing is available in these [countries and regions](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="52105-434">Aufgrund von rechtlichen Beschränkungen muss der Vertrag für Office 365-Abonnements aus den Ländern und Regionen stammen, die vom Audiokonferenzdienst abgedeckt werden, damit Audiokonferenzen in multinationalen Organisationen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="52105-434">Due to legal constraints, for Audio Conferencing to be available to multinational organizations, the contract for Office 365 subscriptions must be sourced from countries and regions covered by Audio Conferencing service.</span></span>

<span data-ttu-id="52105-435">Wenn die Nutzung des Audiokonferenzdiensts durch Ihre Organisation bestätigt ist, erstellen Sie eine Liste der Benutzerstandorte oder Niederlassungen, in denen der Audiokonferenzdienst basierend auf der in der Liste verfügbaren Ländern und Regionen implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="52105-435">After confirming your organization’s eligibility for obtaining the Audio Conferencing service, compile the list of user locations or offices where Audio Conferencing service will be implemented based on the list of available countries and regions.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="52105-436">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="52105-436">Decision Points</span></span></td>
<td align="left"><p><span data-ttu-id="52105-437">Entscheiden Sie, an welchen Benutzerstandorten oder in welchen Niederlassungen der Audiokonferenzdienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="52105-437">Decide which user locations or offices will implement the Audio Conferencing service.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="52105-438">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="52105-438">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="52105-439">Dokumentieren Sie die Benutzerstandorte oder Niederlassungen, die für den Audiokonferenzdienst aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="52105-439">Document the user locations or offices to be enabled for the Audio Conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-440">Niederlassung</span><span class="sxs-lookup"><span data-stu-id="52105-440">Office</span></span></th>
<th align="left"><span data-ttu-id="52105-441">Standort</span><span class="sxs-lookup"><span data-stu-id="52105-441">Location</span></span></th>
<th align="left"><span data-ttu-id="52105-442">PSTN-Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="52105-442">PSTN Conference Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-443">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-443">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-444">Australien</span><span class="sxs-lookup"><span data-stu-id="52105-444">Australia</span></span></td>
<td align="left"><span data-ttu-id="52105-445">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-445">Audio conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-446">100 Cyberport Road</span><span class="sxs-lookup"><span data-stu-id="52105-446">100 Cyberport Road</span></span></td>
<td align="left"><span data-ttu-id="52105-447">Hong Kong SAR (香港特別行政區)</span><span class="sxs-lookup"><span data-stu-id="52105-447">Hong Kong SAR</span></span></td>
<td align="left"><span data-ttu-id="52105-448">Legacy-PSTN-Konferenz</span><span class="sxs-lookup"><span data-stu-id="52105-448">Legacy PSTN Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-449">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-449">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-450">Singapur</span><span class="sxs-lookup"><span data-stu-id="52105-450">Singapore</span></span></td>
<td align="left"><span data-ttu-id="52105-451">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-451">Audio conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-452">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-452">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-453">Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="52105-453">United Kingdom</span></span></td>
<td align="left"><span data-ttu-id="52105-454">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-454">Audio conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-455">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-455">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-456">Frankreich</span><span class="sxs-lookup"><span data-stu-id="52105-456">France</span></span></td>
<td align="left"><span data-ttu-id="52105-457">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-457">Audio conferencing</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-458">_Tabelle 7: Aktivierungsliste für Audiokonferenzdienst-Standorte – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-458">_Table 7 Example of Audio Conferencing service site enablement list_</span></span>


## <a name="licensing-for-audio-conferencing"></a><span data-ttu-id="52105-459">Lizenzierung für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-459">Licensing for Audio Conferencing</span></span>

<span data-ttu-id="52105-460">[Audiokonferenzlizenz](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US) (vormals Skype for Business PSTN-Konferenzlizenz) ist als Teil der Office 365 E5-Abonnementpläne oder als Add-On für 365 E1- oder Office 365 E3-Abonnementpläne verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52105-460">[Audio Conferencing license](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), formerly known as Skype for Business PSTN Conferencing license, is available as part of Office 365 E5 subscription plans, or as an add-on to Office 365 E1 or Office 365 E3 subscription plans.</span></span>

> [!NOTE]
> <span data-ttu-id="52105-461">PSTN- oder Einwahlkonferenzen in Teams bieten keine Unterstützung für <sup>Drittanbieter</sup> von Audiokonferenzanbieter-Partnern (Audio Conferencing Provider, ACP).</span><span class="sxs-lookup"><span data-stu-id="52105-461">PSTN or dial-in conferencing in Teams does not support 3<sup>rd</sup>-party Audio Conferencing Providers (ACPs).</span></span>
> <br><span data-ttu-id="52105-462">Wenn Sie den PSTN-Konferenzdienst für Skype for Business bereits verwenden, können Sie unmittelbar die Vorteile des Audiokonferenzdiensts in Teams nutzen.</span><span class="sxs-lookup"><span data-stu-id="52105-462">If you already use Skype for Business Online PSTN Conferencing today, you can immediately take advantage of Audio Conferencing in Teams.</span></span>

<span data-ttu-id="52105-463">Um gebührenfreie Telefonnummern für Konferenzbrücken zur Verfügung zu stellen und ausgehende Konferenzanrufe für internationale Telefonnummern zu unterstützen, müssen Sie [Kommunikationsguthaben](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) für Ihre Organisation einrichten.</span><span class="sxs-lookup"><span data-stu-id="52105-463">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to International phone numbers, you need to setup [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) for your organization.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="52105-464">Für einige Länder/Regionen gibt es nur gebührenfreie Telefonnummern für Konferenzbrücken. In diesem Fall ist die Verwendung von Kommunikationsguthaben verpflichtend, um die Einwahl für diese Länder/Regionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="52105-464">Some countries are serviced by toll-free conference bridge phone numbers only, and in this case the use of Communications Credits is a mandatory requirement to support dial in for such countries.</span></span>

<span data-ttu-id="52105-465">Bei der Implementierung von Kommunikationsguthaben müssen Sie zunächst überlegen, wie hoch der anfängliche Betrag für das Guthaben sein soll.</span><span class="sxs-lookup"><span data-stu-id="52105-465">The first consideration to make when implementing Communications Credits is to decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="52105-466">In der Dokumentation [Communications Credits](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) finden Sie eine Auflistung der empfohlenen Beträge.</span><span class="sxs-lookup"><span data-stu-id="52105-466">Recommended funding amounts can be referenced from the [Communications Credits](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span>

<span data-ttu-id="52105-467">Wenn sich Ihre Organisation für das automatische Auffüllen des Betrags entscheidet, finden Sie in der Dokumentation [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) ebenfalls eine Empfehlung dafür, wie hoch der niedrigste Betrag sein sollte, ab dem die automatische Auffüllung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="52105-467">If your organization chooses to use auto-recharge, a recommendation on the trigger (lowest amount of funds) is also included in the [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span> <span data-ttu-id="52105-468">Der Betrag für die automatische Auffüllung richtet sich nach der tatsächlichen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="52105-468">Auto-recharge amount needs to be determined by the actual usage.</span></span> <span data-ttu-id="52105-469">Die Verwendung von Kommunikationsguthaben sollte immer überwacht werden, und der Auffüllungsbetrag muss dynamisch angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="52105-469">Communications Credits usage should be monitored over time and the recharge amount needs to be adjusted as required.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="52105-470">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="52105-470">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-471">Wenn Ihre Organisation die erforderliche Lizenzen für Audiokonferenzen noch nicht erworben hat, können Sie überlegen, ob Sie vorhandene Office 365-Abonnements erweitern oder Add-Ons für Audiokonferenzen anschaffen möchten.</span><span class="sxs-lookup"><span data-stu-id="52105-471">If your organization has not already purchased the required Audio Conferencing licensing, decide whether Audio Conferencing licenses will be acquired by stepping up existing Office 365 subscriptions or by acquiring Audio Conferencing add-ons.</span></span></li>
<li><span data-ttu-id="52105-472">Entscheiden Sie, ob Kommunikationsguthaben für die Implementierung von Audiokonferenzen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="52105-472">Decide if Communications Credits is required for Audio Conferencing implementation.</span></span> <span data-ttu-id="52105-473">Wenn ja, legen Sie den anfänglichen Auffüllungsbetrag fest.</span><span class="sxs-lookup"><span data-stu-id="52105-473">If so, decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="52105-474">Legen Sie zudem fest, wie hoch der niedrigste Betrag sein sollte, bei dem die automatische Auffüllung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="52105-474">Where applicable, decide the trigger amount and auto-recharge amount.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="52105-475">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="52105-475">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-476">Listen Sie die Benutzer auf, denen eine Lizenz für Audiokonferenzen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="52105-476">Document the users that will be assigned Audio Conferencing license.</span></span></li>
<li><span data-ttu-id="52105-477">Dokumentieren Sie den Plan für Kommunikationsguthaben (anfänglicher Betrag und Betrag für die Auslösung der Auffüllung, Höhe des Betrags für die automatische Auffüllung).</span><span class="sxs-lookup"><span data-stu-id="52105-477">Document the Communications Credits plan (initial amount, trigger amount, auto-recharge amount).</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-478">Benutzer</span><span class="sxs-lookup"><span data-stu-id="52105-478">User</span></span></th>
<th align="left"><span data-ttu-id="52105-479">Niederlassung</span><span class="sxs-lookup"><span data-stu-id="52105-479">Office</span></span></th>
<th align="left"><span data-ttu-id="52105-480">Office 365-Lizenz</span><span class="sxs-lookup"><span data-stu-id="52105-480">Office 365 License</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-481">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="52105-481">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="52105-482">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-482">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-483">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="52105-483">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-484">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="52105-484">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="52105-485">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-485">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-486">Office 365 E3, Add-On für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-486">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-487">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="52105-487">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="52105-488">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-488">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-489">Office 365 E3, Add-On für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-489">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-490">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="52105-490">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="52105-491">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-491">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-492">Office 365 E3, Add-On für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-492">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-493">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="52105-493">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="52105-494">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-494">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-495">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="52105-495">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-496">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="52105-496">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="52105-497">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-497">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-498">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="52105-498">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-499">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="52105-499">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="52105-500">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-500">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-501">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="52105-501">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-502">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="52105-502">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="52105-503">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-503">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-504">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="52105-504">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-505">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="52105-505">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="52105-506">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-506">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-507">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="52105-507">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-508">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="52105-508">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="52105-509">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-509">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-510">Office 365 E3, Add-On für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-510">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-511">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="52105-511">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="52105-512">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-512">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-513">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="52105-513">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-514">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="52105-514">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="52105-515">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-515">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-516">Office 365 E3, Add-On für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-516">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-517">_Tabelle 8: Lizenzzuweisungsliste für Besprechungsorganisatoren von Audiokonferenzen – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-517">_Table 8 Example of license assignment list for Audio Conferencing meeting organizers_</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-518">Anfangsbetrag</span><span class="sxs-lookup"><span data-stu-id="52105-518">Initial amount</span></span></th>
<td align="left"><span data-ttu-id="52105-519">1.000 US-Dollar</span><span class="sxs-lookup"><span data-stu-id="52105-519">$ 1,000</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-520">Betrag für die Auslösung der Auffüllung</span><span class="sxs-lookup"><span data-stu-id="52105-520">Trigger amount</span></span></th>
<td align="left"><span data-ttu-id="52105-521">400 US-Dollar</span><span class="sxs-lookup"><span data-stu-id="52105-521">$ 400</span></span></td>
</tr>
<tr class="header">
<th align="left"><span data-ttu-id="52105-522">Höhe des Betrags für die automatische Auffüllung</span><span class="sxs-lookup"><span data-stu-id="52105-522">Auto-recharge amount</span></span></th>
<td align="left"><span data-ttu-id="52105-523">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-523">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-524">_Tabelle 9: Zahlen für die Planung von Kommunikationsguthaben – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-524">_Table 9 Example of Communications Credits planning numbers_</span></span>


## <a name="conference-bridge-phone-numbers"></a><span data-ttu-id="52105-525">Telefonnummern für Konferenzbrücken</span><span class="sxs-lookup"><span data-stu-id="52105-525">Conference bridge phone numbers</span></span>

<span data-ttu-id="52105-526">Der Audiokonferenzdienst in Office 365 umfasst:</span><span class="sxs-lookup"><span data-stu-id="52105-526">The Audio Conferencing service in Office 365 includes:</span></span>

-   <span data-ttu-id="52105-527">Mehrere Typen von Telefonnummern für Konferenzbrücken (gebührenpflichtig und gebührenfrei)</span><span class="sxs-lookup"><span data-stu-id="52105-527">Multiple types of conference bridge phone numbers (Toll and Toll-Free)</span></span>

-   <span data-ttu-id="52105-528">Mehrere Kategorien der Telefonnummer (dediziert oder freigegeben)</span><span class="sxs-lookup"><span data-stu-id="52105-528">Multiple categories of the phone number (dedicated and shared)</span></span>

-   <span data-ttu-id="52105-529">Unterstützung für mehrere Sprachen für die Konferenzbrücke (primär oder sekundär)</span><span class="sxs-lookup"><span data-stu-id="52105-529">Support for multiple languages for the conference bridge (primary and secondary)</span></span>

-   <span data-ttu-id="52105-530">Eine Standardtelefonnummer für den Mandanten.</span><span class="sxs-lookup"><span data-stu-id="52105-530">A default phone number for the tenant.</span></span>

<span data-ttu-id="52105-531">Eine vollständige Beschreibung der enthaltenen Funktionen finden Sie unter [Einrichten von Einwahl- oder PSTN-Konferenzen für Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) und [Telefonnummern für Einwahlkonferenzen](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span><span class="sxs-lookup"><span data-stu-id="52105-531">Full description of the included capabilities can be referenced from [Set up dial-in or PSTN conferencing for Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) and [Phone numbers for dial-in conferencing](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span></span>

> [!NOTE]
> <span data-ttu-id="52105-532">Dedizierte Telefonnummern für Konferenzbrücken werden basierend auf der Anzahl der anwendbaren Lizenzen auf die Telefonnummern angerechnet, die pro Mandant angefordert werden können. Erläuterungen hierzu erhalten Sie unter [Erste Schritte mit Skype for Business-Servicenummern](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span><span class="sxs-lookup"><span data-stu-id="52105-532">Dedicated conference bridge phone numbers are counted towards the limit of phone numbers that can be acquired per tenant, based on the number of applicable licenses as described in [Getting Skype for Business service phone numbers](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span></span> <span data-ttu-id="52105-533">Für gebührenfreie Telefonnummern für Konferenzbrücken ist Kommunikationsguthaben erforderlich.</span><span class="sxs-lookup"><span data-stu-id="52105-533">Toll-free conference bridge phone numbers require Communications Credits.</span></span>

<span data-ttu-id="52105-534">Vorhandene Telefonnummern für Konferenzbrücken, die in den Audiokonferenzdienst übertragen werden müssen, und unter der Voraussetzung, dass diese die landespezifischen Anforderungen erfüllen, können nach Microsoft portiert werden.</span><span class="sxs-lookup"><span data-stu-id="52105-534">If there are existing conference bridge phone numbers that must be transferred to the Audio Conferencing service, assuming they are meeting the country-specific requirements, then the existing conference bridge phone numbers can be transferred to Microsoft.</span></span>


> [!NOTE]
> <span data-ttu-id="52105-535">Die Komplexität der Portierung von Telefonnummern nach Microsoft richtet sich sehr stark nach den jeweiligen Ländern oder Regionen, Netzbetreibern, der Anzahl der beteiligten Verbindungen und vielen anderen Faktoren.</span><span class="sxs-lookup"><span data-stu-id="52105-535">Complexity of transferring phone numbers to Microsoft varies greatly based on the countries or regions, carriers, the number of circuits involved, and many other contributing factors.</span></span> <span data-ttu-id="52105-536">Informationen zur Portierung von Telefonnummern finden Sie im [Handbuch zur Portierung von Telefonnummern](https://go.microsoft.com/fwlink/?linkid=859011).</span><span class="sxs-lookup"><span data-stu-id="52105-536">To plan for phone number porting, check out the [Number Porting Guide](https://go.microsoft.com/fwlink/?linkid=859011).</span></span>

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

<span data-ttu-id="52105-537">Weitere Details zur Portierung von Telefonnummern zum Audiokonferenzdienst finden Sie unter [Portierung von Telefonnummern nach Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span><span class="sxs-lookup"><span data-stu-id="52105-537">Additional details on transferring phone numbers to Audio Conferencing service can be found in [Transfer phone numbers to Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="52105-538">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="52105-538">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-539">Wählen Sie aus, ob Ihre Organisation dedizierte Telefonnummern für Konferenzbrücken benötigt.</span><span class="sxs-lookup"><span data-stu-id="52105-539">Decide whether the organization requires dedicated conference bridge phone numbers</span></span></li>
<li><span data-ttu-id="52105-540">Entscheiden Sie, wie die dedizierten Telefonnummern für Konferenzbrücken für die jeweiligen Benutzerstandorte oder Niederlassungen für die Implementierung von Audiokonferenzen abgerufen werden sollen (über Microsoft oder anhand der Portierung von vorhandenen Telefonnummern).</span><span class="sxs-lookup"><span data-stu-id="52105-540">Decide how the dedicated conference bridge phone numbers will be obtained for user locations or offices in-scope for the Audio Conferencing implementation (obtain from Microsoft or transfer existing phone numbers)</span></span></li>
<li><span data-ttu-id="52105-541">Wenn Sie sich für Microsoft entscheiden, wählen Sie die Methode zum Abrufen von Telefonnummern (Formulareingabe oder automatisch) für die jeweiligen Benutzerstandorte oder Niederlassungen für die Implementierung von Audiokonferenzen aus.</span><span class="sxs-lookup"><span data-stu-id="52105-541">If you choose to obtain from Microsoft, decide the method to obtain phone numbers (form submission or automated) for user locations or offices in-scope for the Audio Conferencing implementation</span></span></li>
<li><span data-ttu-id="52105-542">Wählen Sie die Spracheinstellungen für alle dedizierten Telefonnummern für Konferenzbrücken aus.</span><span class="sxs-lookup"><span data-stu-id="52105-542">Decide the language preferences to be set up for each dedicated conference bridge phone number</span></span></li>
<li><span data-ttu-id="52105-543">Wählen Sie die Standardtelefonnummer für Konferenzbrücken für den Mandanten aus.</span><span class="sxs-lookup"><span data-stu-id="52105-543">Decide the tenant default conference bridge phone number</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="52105-544">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="52105-544">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-545">Dokumentieren Sie den Masterplan für den Erwerb von Telefonnummern mit Details darüber, wie die Telefonnummern an jedem einzelnen Benutzerstandort oder jeder einzelnen Niederlassung für die Implementierung von Audiokonferenzen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="52105-545">Document the master plan for phone numbers acquisition, detailing how phone numbers will be obtained for each user location or office in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="52105-546">Falls anwendbar, füllen Sie für jeden Standort oder jede Niederlassung das Formular <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">für die Anforderung neuer Telefonnummern</a> aus.</span><span class="sxs-lookup"><span data-stu-id="52105-546">If applicable, complete <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">the New Telephone Number Request form</a>, one form for each location or office</span></span></li>
<li><span data-ttu-id="52105-547">Wenn Sie vorhandene Telefonnummern portieren möchten, können Sie diesen Vorgang mit Unterstützung des <a href="https://go.microsoft.com/fwlink/?linkid=859011">Handbuchs zur Portierung von Telefonnummern</a> planen und die zeitgerechte Implementierung des Audiokonferenzdiensts entsprechend anpassen.</span><span class="sxs-lookup"><span data-stu-id="52105-547">If you choose to transfer existing phone numbers, check out the <a href="https://go.microsoft.com/fwlink/?linkid=859011">Number Porting Guide</a> to plan it and adjust Audio Conferencing implementation timeline accordingly.</span></span></li>
<li><span data-ttu-id="52105-548">Dokumentieren Sie die detaillierten Konfigurationen der Telefonnummern für Konferenzbrücken (freigegebene und dedizierte Telefonnummern für Konferenzbrücken, Spracheinstellungen für jede dedizierte Telefonnummer für Konferenzbrücken, standardmäßige Telefonnummer für Konferenzbrücken für den Mandanten).</span><span class="sxs-lookup"><span data-stu-id="52105-548">Document the detailed conference bridge phone number configurations (shared and dedicated conference bridge phone numbers, language preferences for each dedicated conference bridge phone number, tenant default conference bridge phone number)</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-549">Niederlassung</span><span class="sxs-lookup"><span data-stu-id="52105-549">Office</span></span></th>
<th align="left"><span data-ttu-id="52105-550">Anschaffung der Brückennummer und Brückentyp</span><span class="sxs-lookup"><span data-stu-id="52105-550">Bridge Number Acquisition and Bridge Type</span></span></th>
<th align="left"><span data-ttu-id="52105-551">Brückennummer</span><span class="sxs-lookup"><span data-stu-id="52105-551">Bridge Number</span></span></th>
<th align="left"><span data-ttu-id="52105-552">Brückensprache</span><span class="sxs-lookup"><span data-stu-id="52105-552">Bridge Language</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-553">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-553">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-554">Neu anschaffen, dediziert</span><span class="sxs-lookup"><span data-stu-id="52105-554">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="52105-555">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-555">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-556">Englisch (Australien)</span><span class="sxs-lookup"><span data-stu-id="52105-556">en-AU – English (Australia)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-557">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-557">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-558">Neu anschaffen, freigegeben</span><span class="sxs-lookup"><span data-stu-id="52105-558">Acquire new, shared</span></span></td>
<td align="left"><span data-ttu-id="52105-559">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-559">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-560">Englisch (Vereinigte Staaten), Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="52105-560">English (United States), Chinese (Simplified, PRC)</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-561">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-561">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-562">Port vorhanden, dediziert</span><span class="sxs-lookup"><span data-stu-id="52105-562">Port existing, dedicated</span></span></td>
<td align="left"><span data-ttu-id="52105-563">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="52105-563">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="52105-564">Englisch (Vereinigtes Königreich)</span><span class="sxs-lookup"><span data-stu-id="52105-564">en-GB – English (United Kingdom)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-565">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-565">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-566">Neu anschaffen, dediziert</span><span class="sxs-lookup"><span data-stu-id="52105-566">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="52105-567">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-567">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-568">Französisch (Frankreich), Englisch (Vereinigtes Königreich)</span><span class="sxs-lookup"><span data-stu-id="52105-568">French (France), English (United Kingdom)</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-569">_Tabelle 10: Beispiel der Details einer Konferenzbrücke_</span><span class="sxs-lookup"><span data-stu-id="52105-569">_Table 10 Example of conference bridge details_</span></span>


> [!NOTE]
> <span data-ttu-id="52105-570">Die Beispieltabelle oben und nachfolgende Tabellen in diesem Dokument dienen als Vorlage.</span><span class="sxs-lookup"><span data-stu-id="52105-570">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="52105-571">Der Hinweis „TBA“ (To Be Added, wird ergänzt) zeigt an, dass Sie hier Informationen als Teil Ihres Planungsprozesses eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="52105-571">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

## <a name="conference-bridge-settings"></a><span data-ttu-id="52105-572">Einstellungen der Konferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="52105-572">Conference bridge settings</span></span>

<span data-ttu-id="52105-573">Organisationsweite Konfigurationsoptionen für die Teilnahme an Audiokonferenzbesprechungen (Benachrichtigung über Zu- und Abgänge der Besprechung sowie die Aufzeichnung des Anrufernamens), PIN-Länge des Besprechungsorganisators und E-Mail-Benachrichtigung sind zur weiteren Anpassung der Endbenutzerfunktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52105-573">Organization-wide configuration options around Audio Conferencing meeting join experience (meeting entry and exit notification and caller name recording), meeting organizer’s PIN length, and email notification are available to further tailor the end-user experience.</span></span>

-   <span data-ttu-id="52105-574">Benachrichtigungen über Zu- und Abgänge in Besprechungen sind in Form eines aufgezeichneten Namens, einer Telefonnummer und Signaltönen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52105-574">Meeting entry and exit notifications are available in the form of recorded name, phone number, and tones.</span></span>

-   <span data-ttu-id="52105-575">Die PIN-Länge ist mit 4 bis zwölf Ziffern konfigurierbar, wobei eine PIN standardmäßig aus 5 Ziffern besteht.</span><span class="sxs-lookup"><span data-stu-id="52105-575">PIN length is configurable from 4 to 12 digits, with a 5-digit PIN as the default.</span></span>

-   <span data-ttu-id="52105-576">Benachrichtigungs-E-Mails werden bei der Aktivierung der Lizenz für Audiokonferenzen oder durch andere vom Administrator vorgenommenen Änderungen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="52105-576">Notification emails upon enablement of Audio Conferencing license or any other admin-driven changes are enabled by default.</span></span> <span data-ttu-id="52105-577">Sie können diese Funktion deaktivieren und die Kontrolle über die Kommunikation Ihrer Endbenutzer übernehmen.</span><span class="sxs-lookup"><span data-stu-id="52105-577">You can disable this feature and take control of your organization’s end-user communications.</span></span>

<span data-ttu-id="52105-578">Für Benutzer, denen eine Lizenz für Audiokonferenzen zugewiesen ist, können die gebührenpflichtigen bzw. gebührenfreien Nummern (wie in den Koordinaten für Audiokonferenzen gezeigt) so konfiguriert werden, dass sie Folgendes verwenden können:</span><span class="sxs-lookup"><span data-stu-id="52105-578">For users who are assigned an Audio Conferencing license, the default toll/toll-free numbers, shown in the Audio Conferencing coordinates, are configurable to use:</span></span>

-   <span data-ttu-id="52105-579">die standardmäßigen Telefonnummern für Konferenzbrücken auf der Ebene des Mandanten</span><span class="sxs-lookup"><span data-stu-id="52105-579">the tenant-level default, or</span></span>

-   <span data-ttu-id="52105-580">die automatisch zugewiesenen Telefonnummern für Konferenzbrücken</span><span class="sxs-lookup"><span data-stu-id="52105-580">the automatically-assigned conference bridge phone numbers, or</span></span>

-   <span data-ttu-id="52105-581">die für jeden Benutzer manuell definierten Telefonnummern für Konferenzbrücken</span><span class="sxs-lookup"><span data-stu-id="52105-581">manually defined conference bridge phone numbers for each user.</span></span>

<span data-ttu-id="52105-582">Benutzerspezifische Telefonnummern für Konferenzbrücken sind in der Regel in globalen oder überregionalen Organisationen sinnvoll, in denen Benutzer verteilt sind und lokale Nummern als Standardtelefonnummern für Konferenzbrücken in den Besprechungseinladungen angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="52105-582">User-specific conference bridge phone numbers are typically useful in global or nationwide organizations where users are distributed and must provide local numbers as the default conference bridge phone numbers in the meeting invites.</span></span>

<span data-ttu-id="52105-583">Teilnehmer aus anderen Städten oder aus dem Ausland können weitere auf der Mandantenebene konfigurierte Nummern nachschlagen, diese Nummern werden jedoch nicht direkt in den Besprechungseinladungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52105-583">Participants joining from different cities or overseas can look up additional numbers configured at the tenant-level, but these numbers do not appear directly in the meeting invites.</span></span> <span data-ttu-id="52105-584">Die Besprechungseinladungen enthalten einen Link, über den die Teilnehmer zu der Seite mit den Einwahlnummern für Teams-Konferenzen gelangen. Dort können die Teilnehmer die für Ihren Standort geltenden Telefonnummern für Konferenzbrücken in Erfahrung bringen.</span><span class="sxs-lookup"><span data-stu-id="52105-584">The meeting invites provide a link that will take participants to the Teams Conference Dial-in Numbers page for them to lookup the closest conference bridge phone numbers available from their location.</span></span>

<span data-ttu-id="52105-585">Sie können auch konfigurieren, wie nicht authentifizierte Anrufer von jedem einzelnen Besprechungsorganisator gehandhabt werden. Dabei können Sie festlegen, ob der Besprechungsorganisator die Besprechung starten muss, bevor nicht authentifizierte Benutzer zugelassen werden, oder ob nicht authentifizierte Anrufer eine Besprechung starten können.</span><span class="sxs-lookup"><span data-stu-id="52105-585">You can also configure how unauthenticated callers are handled by each individual meeting organizer, whether to require meeting organizer to start the meeting before unauthenticated callers are admitted, or to allow unauthenticated callers to start a meeting.</span></span>

<span data-ttu-id="52105-586">Zusätzliche für jeden Benutzer anwendbare Konfigurationen sind verfügbar, um die Verwendung von gebührenfreien Telefonnummern für Konferenzbrücken sowie das Anrufen aus einer Konferenz heraus zu steuern.</span><span class="sxs-lookup"><span data-stu-id="52105-586">Additional configurations that can be applied for each user are available to control the use of toll-free conference bridge phone numbers and dial-out from a conference.</span></span>

> [!NOTE]
> <span data-ttu-id="52105-587">Diese mit Kosten verbundenen Steuerelemente sind derzeit nur für Preview-Kunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52105-587">These cost-related controls are currently available for preview customers only.</span></span> <span data-ttu-id="52105-588">Über die Seite [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013) können Sie Ihre Organisation für das Preview-Programm registrieren.</span><span class="sxs-lookup"><span data-stu-id="52105-588">You can enroll your organization in the preview program from [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span></span>

<span data-ttu-id="52105-589">Mit diesen Steuerelementen können Sie entscheiden, ob Besprechungsorganisatoren gebührenfreie Telefonnummern für Konferenzbrücken für die von ihnen organisierten Besprechungen zur Verfügung stellen können, und ob sie steuern können, ob Teilnehmer Anrufe aus den von ihnen organisierten Besprechungen heraus tätigen können.</span><span class="sxs-lookup"><span data-stu-id="52105-589">With these controls, you can decide whether meeting organizers can provide toll-free conference bridge phone numbers for meetings organized by them, and to control whether participants can dial out from the meetings organized by them.</span></span> <span data-ttu-id="52105-590">Die Steuerungsebene rangiert hierbei vom Nichtzulassen von ausgehenden Anrufen, Zulassen von ausgehenden Anrufen an Inlandsnummern bis zum Zulassen von ausgehenden Anrufen an Inlands- und Auslandsnummern.</span><span class="sxs-lookup"><span data-stu-id="52105-590">The level of dial-out control spans from disallowing dial out, only allowing dial out to domestic numbers, to allowing dial out to both domestic and international numbers.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="52105-591">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="52105-591">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-592">Entscheiden Sie, ob die Organisation Benachrichtigungen über Zu- und Abgänge benötigt. Wenn ja, wählen Sie den zu implementierenden Benachrichtigungstyp (Signaltöne, Telefonnummer, aufgezeichneter Name) aus.</span><span class="sxs-lookup"><span data-stu-id="52105-592">Decide whether the organization requires entry and exit notifications, and if yes, the type of notification to be implemented (tones, phone number, or recorded name).</span></span></li>
<li><span data-ttu-id="52105-593">Legen Sie die PIN-Länge für Audiokonferenzen in Übereinstimmung mit den Sicherheitsanforderungen Ihrer Organisation fest.</span><span class="sxs-lookup"><span data-stu-id="52105-593">Decide the Audio Conferencing PIN length that meets the organizational security requirements.</span></span></li>
<li><span data-ttu-id="52105-594">Legen Sie fest, ob die Organisation die mit dem Audiokonferenzdienst verbundene Kommunikation der Endbenutzer steuern möchte.</span><span class="sxs-lookup"><span data-stu-id="52105-594">Decide if the organization wants to take control of end-user communications related to Audio Conferencing service.</span></span></li>
<li><span data-ttu-id="52105-595">Wählen Sie die Telefonnummern für Konferenzbrücken aus, die jedem Besprechungsorganisator zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="52105-595">Decide the conference bridge phone numbers to be assigned to each meeting organizer.</span></span></li>
<li><span data-ttu-id="52105-596">Legen Sie fest, ob einige Besprechungsorganisatoren in die Lage versetzt werden sollen, gebührenfreie Telefonnummern für Konferenzbrücken in Ihren Besprechungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="52105-596">Decide whether some meeting organizers require the ability to use toll-free conference bridge phone numbers for their meeings</span></span></li>
<li><span data-ttu-id="52105-597">Legen Sie fest, ob einige Besprechungsorganisatoren in die Lage versetzt werden sollen, nicht authentifizierten Anrufern zu erlauben, eine Besprechung zu starten.</span><span class="sxs-lookup"><span data-stu-id="52105-597">Decide whether some meeting organizers require the ability to allow unauthenticated callers to start a meeting.</span></span></li>
<li><span data-ttu-id="52105-598">Legen Sie fest, ob für einige Besprechungsorganisatoren die ausgehenden Anrufe gesteuert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="52105-598">Decide whether some meeting organizers require conference dial out to be controlled.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="52105-599">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="52105-599">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-600">Dokumentieren Sie die detaillierten Konferenzbrückeneinstellungen (Benachrichtigungen über Zu- und Abgänge, PIN-Länge, E-Mail-Benachrichtigung über Konfigurationsänderungen).</span><span class="sxs-lookup"><span data-stu-id="52105-600">Document the detailed conference bridge settings (entry and exit notifications, PIN length, configuration change email notification).</span></span></li>
<li><span data-ttu-id="52105-601">Dokumentieren Sie die Telefonnummern für Konferenzbrücken, die jedem Besprechungsorganisator zugewiesen werden, und die entsprechende Einstellung, um die Richtlinie für nicht authentifizierte Anrufer zu steuern, sowie Steuerelemente für gebührenfreie und ausgehende Anrufe.</span><span class="sxs-lookup"><span data-stu-id="52105-601">Document the conference bridge phone numbers to be assinged to each meeting organizer and the corresponding setting to control unauthenticated caller’s policy, and toll-free and dial out controls.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="52105-602"><strong>Benachrichtigungen über Zu- und Abgänge in Besprechungen aktivieren</strong></span><span class="sxs-lookup"><span data-stu-id="52105-602"><strong>Enable meeting entry and exit notifications</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-603">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-603">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="52105-604"><strong>Ankündigungstyp für Zu- und Abgänge</strong></span><span class="sxs-lookup"><span data-stu-id="52105-604"><strong>Entry/exit announcement type</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-605">Signaltöne</span><span class="sxs-lookup"><span data-stu-id="52105-605">Tones</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="52105-606"><strong>Anrufer fragen, ob ihr Name vor der Teilnahme an der Besprechung aufgezeichnet werden kann</strong></span><span class="sxs-lookup"><span data-stu-id="52105-606"><strong>Ask callers to record their name before joining the meeting</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-607">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-607">Disabled.</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="52105-608"><strong>PIN-Länge</strong></span><span class="sxs-lookup"><span data-stu-id="52105-608"><strong>Minimum PIN length</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-609">5</span><span class="sxs-lookup"><span data-stu-id="52105-609">Example 5</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="52105-610"><strong>Es werden automatisch E-Mails an den Benutzer gesendet, wenn sich die Einwahleinstellungen ändern</strong></span><span class="sxs-lookup"><span data-stu-id="52105-610"><strong>Automatically send emails to users if their dial-in settings change</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-611">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-611">Disabled.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-612">_Tabelle 11: Einstellungen einer Konferenzbrücke – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-612">_Table 11 Example of conference bridge settings_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-613">Benutzer</span><span class="sxs-lookup"><span data-stu-id="52105-613">User</span></span></th>
<th align="left"><span data-ttu-id="52105-614">Niederlassung</span><span class="sxs-lookup"><span data-stu-id="52105-614">Office</span></span></th>
<th align="left"><span data-ttu-id="52105-615">Gebührenpflichtige Standardnummer</span><span class="sxs-lookup"><span data-stu-id="52105-615">Default toll number</span></span></th>
<th align="left"><span data-ttu-id="52105-616">Gebührenfreie Standardnummer</span><span class="sxs-lookup"><span data-stu-id="52105-616">Default toll-free number</span></span></th>
<th align="left"><span data-ttu-id="52105-617">Gebührenfreie Nummer zulassen</span><span class="sxs-lookup"><span data-stu-id="52105-617">Allow toll-free</span></span></th>
<th align="left"><span data-ttu-id="52105-618">Nicht authentifizierte Anrufer umgehen Wartebereich</span><span class="sxs-lookup"><span data-stu-id="52105-618">PSTN callers bypass lobby</span></span></th>
<th align="left"><span data-ttu-id="52105-619">Konferenzauswahl</span><span class="sxs-lookup"><span data-stu-id="52105-619">Conference dial out</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-620">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="52105-620">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="52105-621">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-621">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-622">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-622">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-623">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-623">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-624">Ja</span><span class="sxs-lookup"><span data-stu-id="52105-624">Yes</span></span></td>
<td align="left"><span data-ttu-id="52105-625">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-625">Enabled</span></span></td>
<td align="left"><span data-ttu-id="52105-626">In- und Auslandsanrufe</span><span class="sxs-lookup"><span data-stu-id="52105-626">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-627">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="52105-627">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="52105-628">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-628">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-629">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-629">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-630">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-630">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-631">Nein</span><span class="sxs-lookup"><span data-stu-id="52105-631">No</span></span></td>
<td align="left"><span data-ttu-id="52105-632">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-632">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="52105-633">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="52105-633">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-634">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="52105-634">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="52105-635">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-635">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-636">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-636">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-637">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-637">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-638">Nein</span><span class="sxs-lookup"><span data-stu-id="52105-638">No</span></span></td>
<td align="left"><span data-ttu-id="52105-639">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-639">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="52105-640">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="52105-640">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-641">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="52105-641">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="52105-642">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-642">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-643">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-643">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-644">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-644">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-645">Ja</span><span class="sxs-lookup"><span data-stu-id="52105-645">Yes</span></span></td>
<td align="left"><span data-ttu-id="52105-646">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-646">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="52105-647">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="52105-647">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-648">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="52105-648">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="52105-649">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-649">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-650">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-650">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-651">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-651">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-652">Ja</span><span class="sxs-lookup"><span data-stu-id="52105-652">Yes</span></span></td>
<td align="left"><span data-ttu-id="52105-653">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-653">Enabled</span></span></td>
<td align="left"><span data-ttu-id="52105-654">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="52105-654">Domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-655">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="52105-655">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="52105-656">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-656">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-657">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-657">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-658">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-658">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-659">Ja</span><span class="sxs-lookup"><span data-stu-id="52105-659">Yes</span></span></td>
<td align="left"><span data-ttu-id="52105-660">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-660">Enabled</span></span></td>
<td align="left"><span data-ttu-id="52105-661">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="52105-661">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-662">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="52105-662">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="52105-663">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-663">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-664">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="52105-664">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="52105-665">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-665">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-666">Ja</span><span class="sxs-lookup"><span data-stu-id="52105-666">Yes</span></span></td>
<td align="left"><span data-ttu-id="52105-667">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-667">Enabled</span></span></td>
<td align="left"><span data-ttu-id="52105-668">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="52105-668">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-669">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="52105-669">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="52105-670">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-670">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-671">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="52105-671">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="52105-672">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-672">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-673">Ja</span><span class="sxs-lookup"><span data-stu-id="52105-673">Yes</span></span></td>
<td align="left"><span data-ttu-id="52105-674">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-674">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="52105-675">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="52105-675">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-676">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="52105-676">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="52105-677">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-677">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-678">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="52105-678">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="52105-679">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-679">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-680">Ja</span><span class="sxs-lookup"><span data-stu-id="52105-680">Yes</span></span></td>
<td align="left"><span data-ttu-id="52105-681">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-681">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="52105-682">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="52105-682">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-683">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="52105-683">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="52105-684">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-684">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-685">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-685">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-686">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-686">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-687">Nein</span><span class="sxs-lookup"><span data-stu-id="52105-687">No</span></span></td>
<td align="left"><span data-ttu-id="52105-688">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-688">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="52105-689">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="52105-689">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-690">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="52105-690">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="52105-691">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-691">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-692">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-692">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-693">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-693">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-694">Ja</span><span class="sxs-lookup"><span data-stu-id="52105-694">Yes</span></span></td>
<td align="left"><span data-ttu-id="52105-695">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-695">Enabled</span></span></td>
<td align="left"><span data-ttu-id="52105-696">In- und Auslandsanrufe</span><span class="sxs-lookup"><span data-stu-id="52105-696">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-697">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="52105-697">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="52105-698">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-698">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-699">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-699">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-700">TBA</span><span class="sxs-lookup"><span data-stu-id="52105-700">TBA</span></span></td>
<td align="left"><span data-ttu-id="52105-701">Nein</span><span class="sxs-lookup"><span data-stu-id="52105-701">No</span></span></td>
<td align="left"><span data-ttu-id="52105-702">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-702">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="52105-703">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="52105-703">Domestic</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-704">_Tabelle 12: Zuweisungen der Einstellungen für Konferenzbrücke – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-704">_Table 12 Example of conference bridge settings assignments_</span></span>


## <a name="dial-plans"></a><span data-ttu-id="52105-705">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="52105-705">Dial plans</span></span>

<span data-ttu-id="52105-706">Ein [Wählplan](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) (eine Telefonsystemfunktion von Office 365) ist eine Gruppe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise das Format [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) übersetzt, um Anrufe zu autorisieren und weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="52105-706">A [Dial Plan](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), a Phone System feature of Office 365, is a set of normalization rules that translates dialed phone numbers into an alternate format (typically [E.164](https://go.microsoft.com/fwlink/?linkid=859014) format) for call authorization and call routing.</span></span> <span data-ttu-id="52105-707">Der Audiokonferenzdienst nutzt dieselben Funktionen wie das Telefonsystem, um gewählte Telefonnummern in Szenarien für die Konferenzauswahl zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="52105-707">Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial out scenarios.</span></span>

<span data-ttu-id="52105-708">Mit einem Wählplan können Benutzer Telefonnummern so wählen, wie sie es gewöhnt sind. Zum Beispiel müssen sie bei Ortsgesprächen keine Vorwahl wählen, bei Inlandsanrufen keine Landeskennzahl wählen, und sie können sogar Kurzwahlnummern für ausgehende Anrufe in Konferenzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="52105-708">A dial plan allows users to dial phone numbers the way they are accustomed to, such as omitting area code for local calls, omitting country code for domestic calls, or even using short digit dialing when performing conference dial out.</span></span>

<span data-ttu-id="52105-709">Innerhalb der Telefonsystemfunktion in Office 36 gibt es zwei Arten von Wählplänen:</span><span class="sxs-lookup"><span data-stu-id="52105-709">Within the Phone System feature of Office 365, there are two types of dial plans:</span></span>

-   <span data-ttu-id="52105-710">**Dienstwählplan**.</span><span class="sxs-lookup"><span data-stu-id="52105-710">**Service dial plan**.</span></span> <span data-ttu-id="52105-711">Dies ist der Standardwählplan, der auf einem Office 365-Verwendungsstandort basiert und nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="52105-711">This is the default dial plan and applied to users based on Office 365 usage location, and it cannot be modified.</span></span>

<!-- -->

-   <span data-ttu-id="52105-712">**Mandantenwählplan**.</span><span class="sxs-lookup"><span data-stu-id="52105-712">**Tenant dial plan**.</span></span> <span data-ttu-id="52105-713">Dies ist ein anpassbarer Wählplan innerhalb eines Mandanten, der wiederum zwei Typen umfasst:</span><span class="sxs-lookup"><span data-stu-id="52105-713">This is a customizable dial plan within a tenant, and further divided into two types:</span></span>

    -   <span data-ttu-id="52105-714">**Globaler Wählplan für Mandanten**: Der Wählplan gilt für alle Benutzer innerhalb des Mandanten.</span><span class="sxs-lookup"><span data-stu-id="52105-714">**Tenant-global dial plan**—the dial plan applies to all users within the tenant.</span></span>

    -   <span data-ttu-id="52105-715">**Wählplan für Mandantenbenutzer**: Der Wählplan gilt nur für bestimmte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="52105-715">**Tenant-user dial plan**—the dial plan applies only to specific users.</span></span>


> [!NOTE]
> <span data-ttu-id="52105-716">Weitere Details und Beispiele finden Sie in der Dokumentation [Office 365 Calling Plan dial plans](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) (Office 365-Wählpläne).</span><span class="sxs-lookup"><span data-stu-id="52105-716">Check out the [Office 365 Calling Plan dial plans](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) documentation for further details and examples.</span></span>

<span data-ttu-id="52105-717">Der den Benutzern zugewiesene wirksame Wählplan stellt eine Kombination aus dem Dienstwählplan (basierend auf dem Office 365-Verwendungsstandort des Benutzers) und dem Mandantenwählplan (entweder globaler Wählplan für Mandanten oder Wählplan für Mandantenbenutzer) dar.</span><span class="sxs-lookup"><span data-stu-id="52105-717">The effective dial plan assigned to users is the combination of service dial plan (based on user’s Office 365 usage location) and tenant dial plan (can be either tenant-global dial plan or tenant-user dial plan).</span></span>

![](media/audio_conferencing_image8.png)

<span data-ttu-id="52105-718">Normalisierungsregeln können maximal 25 Regeln in jedem Mandantenwählplan enthalten. Eine Duplizierung von bereits als Teil des Dienstwählplans vorhandenen Normalisierungsregeln sollte daher vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="52105-718">There is a maximum of 25 normalization rules in each tenant dial plan, and thus duplication with normalization rules already available as part of service dial plan needs to be avoided.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="52105-719">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="52105-719">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-720">Legen Sie fest, ob Ihre Organisation angepasste Wählpläne (Geschäftsanforderungen, Übernahmeanforderungen usw.) benötigt.</span><span class="sxs-lookup"><span data-stu-id="52105-720">Decide if your organization requires customized dial plans (business requirements, adoption requirements, etc.).</span></span></li>
<li><span data-ttu-id="52105-721">Legen Sie (falls anwendbar) den Gültigkeitsbereich für den Mandantenwählplan (globaler Wählplan für Mandanten oder Wählplan für Mandantenbenutzer) fest, um die Anforderungen für angepasste Wählpläne zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="52105-721">If applicable, decide the scope of tenant dial plan (tenant-global or tenant-user) to support the requirements for customized dial plans.</span></span></li>
<li><span data-ttu-id="52105-722">Legen Sie (falls anwendbar) die Mandantenwählpläne fest, die zur Unterstützung von Benutzerstandorten oder Niederlassungen für die Implementierung von Audiokonferenzen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="52105-722">If applicable, decide the tenant dial plans that will be created to support user locations or offices in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="52105-723">Legen Sie (falls anwendbar) fest, welche Benutzer einen angepassten Wählplan erfordern, und wählen Sie den jedem Benutzer zuzuweisenden Mandantenwählplan aus.</span><span class="sxs-lookup"><span data-stu-id="52105-723">If applicable, decide which user require customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="52105-724">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="52105-724">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="52105-725">Dokumentieren Sie die angepassten Wählpläne und die zugehörigen Normalisierungsregeln, die als Teil der Implementierung von Audiokonferenzen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="52105-725">Document the customized dial plans and the associated normalization rules to be configured as part of Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="52105-726">Dokumentieren Sie die Benutzer, denen ein angepasster Wählplan zugewiesen wird, und die den Mandantenwählplan für jeden einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="52105-726">Document the users to be assigned with customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-727">Name/Beschreibung des Mandantenwählplans</span><span class="sxs-lookup"><span data-stu-id="52105-727">Tenant Dial Plan Name/Description</span></span></th>
<th align="left"><span data-ttu-id="52105-728">Name/Beschreibung der Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="52105-728">Normalization Rules Name/Description</span></span></th>
<th align="left"><span data-ttu-id="52105-729">Muster</span><span class="sxs-lookup"><span data-stu-id="52105-729">IPv6 Pattern</span></span></th>
<th align="left"><span data-ttu-id="52105-730">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="52105-730">Translation</span></span></th>
<th align="left"><span data-ttu-id="52105-731">IsInternalExtension</span><span class="sxs-lookup"><span data-stu-id="52105-731">IsInternalExtension</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="52105-732"><strong>AU-NSW-NorthRyde-OER</strong></span><span class="sxs-lookup"><span data-stu-id="52105-732"><strong>AU-NSW-NorthRyde-OER</strong></span></span></p>
<p><span data-ttu-id="52105-733"><em>One Epping Road North Ryde, NSW, Wählplan für Australien</em></span><span class="sxs-lookup"><span data-stu-id="52105-733"><em>One Epping Road North Ryde, NSW, AU Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="52105-734"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="52105-734"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span></span></p>
<p><span data-ttu-id="52105-735"><em>Interne Nummer (x7000 - x7999) für One Epping Road-Niederlassung, North Ryde, NSW, Australien</em></span><span class="sxs-lookup"><span data-stu-id="52105-735"><em>Internal number (x7000 - x7999) for One Epping Road office, North Ryde, NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="52105-736">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="52105-736">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="52105-737">+6125550$1</span><span class="sxs-lookup"><span data-stu-id="52105-737">+6125550$1</span></span></td>
<td align="left"><span data-ttu-id="52105-738">Wahr</span><span class="sxs-lookup"><span data-stu-id="52105-738">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="52105-739"><strong>AU-NSW-Local</strong></span><span class="sxs-lookup"><span data-stu-id="52105-739"><strong>AU-NSW-Local</strong></span></span></p>
<p><span data-ttu-id="52105-740"><em>Normalisierung für lokale Nummern für NSW, Australien</em></span><span class="sxs-lookup"><span data-stu-id="52105-740"><em>Local number normalization for NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="52105-741">^([2-9]\d{7})$</span><span class="sxs-lookup"><span data-stu-id="52105-741">^([2-9]\d{7})$</span></span></td>
<td align="left"><span data-ttu-id="52105-742">+612$1</span><span class="sxs-lookup"><span data-stu-id="52105-742">+612$1</span></span></td>
<td align="left"><span data-ttu-id="52105-743">Falsch</span><span class="sxs-lookup"><span data-stu-id="52105-743">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="52105-744"><strong>AU-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="52105-744"><strong>AU-TollFree</strong></span></span></p>
<p><span data-ttu-id="52105-745"><em>Normalisierung für gebührenfreie Nummern für Australien</em></span><span class="sxs-lookup"><span data-stu-id="52105-745"><em>Toll Free number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="52105-746">^(1[38]\d{4,8})\d*$</span><span class="sxs-lookup"><span data-stu-id="52105-746">^(1[38]\d{4,8})\d*$</span></span></td>
<td align="left"><span data-ttu-id="52105-747">+61$1</span><span class="sxs-lookup"><span data-stu-id="52105-747">+61$1</span></span></td>
<td align="left"><span data-ttu-id="52105-748">Falsch</span><span class="sxs-lookup"><span data-stu-id="52105-748">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="52105-749"><strong>AU-Service</strong></span><span class="sxs-lookup"><span data-stu-id="52105-749"><strong>AU-Service</strong></span></span></p>
<p><span data-ttu-id="52105-750"><em>Normalisierung für Servicenummern für Australien</em></span><span class="sxs-lookup"><span data-stu-id="52105-750"><em>Service number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="52105-751">^(000|1[0125]\d{1,8})$</span><span class="sxs-lookup"><span data-stu-id="52105-751">^(000|1[0125]\d{1,8})$</span></span></td>
<td align="left"><span data-ttu-id="52105-752">$1</span><span class="sxs-lookup"><span data-stu-id="52105-752">$1</span></span></td>
<td align="left"><span data-ttu-id="52105-753">Falsch</span><span class="sxs-lookup"><span data-stu-id="52105-753">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="52105-754"><strong>SG-Singapore-OMB</strong></span><span class="sxs-lookup"><span data-stu-id="52105-754"><strong>SG-Singapore-OMB</strong></span></span></p>
<p><span data-ttu-id="52105-755"><em>OMB Singapore, Wählplan für Singapur</em></span><span class="sxs-lookup"><span data-stu-id="52105-755"><em>OMB Singapore, SG Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="52105-756"><strong>SG-OMB-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="52105-756"><strong>SG-OMB-Internal</strong></span></span></p>
<p><span data-ttu-id="52105-757"><em>Interne Nummer (x8000 – x8999) für OMB-Niederlassung, Singapur</em></span><span class="sxs-lookup"><span data-stu-id="52105-757"><em>Internal number (x8000 – x8999) for OMB office, Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="52105-758">^(8\d{3})$</span><span class="sxs-lookup"><span data-stu-id="52105-758">^(8\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="52105-759">+656888$1</span><span class="sxs-lookup"><span data-stu-id="52105-759">+656888$1</span></span></td>
<td align="left"><span data-ttu-id="52105-760">Wahr</span><span class="sxs-lookup"><span data-stu-id="52105-760">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="52105-761"><strong>SG-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="52105-761"><strong>SG-TollFree</strong></span></span></p>
<p><span data-ttu-id="52105-762"><em>Normalisierung für gebührenfreie Nummern für Singapur</em></span><span class="sxs-lookup"><span data-stu-id="52105-762"><em>Toll Free number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="52105-763">^(1?800\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="52105-763">^(1?800\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="52105-764">+65$1</span><span class="sxs-lookup"><span data-stu-id="52105-764">+65$1</span></span></td>
<td align="left"><span data-ttu-id="52105-765">Falsch</span><span class="sxs-lookup"><span data-stu-id="52105-765">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="52105-766"><strong>SG-Service</strong></span><span class="sxs-lookup"><span data-stu-id="52105-766"><strong>SG-Service</strong></span></span></p>
<p><span data-ttu-id="52105-767"><em>Normalisierung für Servicenummern für Singapur</em></span><span class="sxs-lookup"><span data-stu-id="52105-767"><em>Service number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="52105-768">^(1\d{3,4}|9\d{2})$</span><span class="sxs-lookup"><span data-stu-id="52105-768">^(1\d{3,4}|9\d{2})$</span></span></td>
<td align="left"><span data-ttu-id="52105-769">$1</span><span class="sxs-lookup"><span data-stu-id="52105-769">$1</span></span></td>
<td align="left"><span data-ttu-id="52105-770">Falsch</span><span class="sxs-lookup"><span data-stu-id="52105-770">False</span></span></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="52105-771"><strong>FR-Paris-Issy-39qdPR</strong></span><span class="sxs-lookup"><span data-stu-id="52105-771"><strong>FR-Paris-Issy-39qdPR</strong></span></span></p>
<p><span data-ttu-id="52105-772"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, Wählplan für Frankreich</em></span><span class="sxs-lookup"><span data-stu-id="52105-772"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="52105-773"><strong>FR-39qdPR-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="52105-773"><strong>FR-39qdPR-Internal</strong></span></span></p>
<p><span data-ttu-id="52105-774"><em>Interne Nummer (x7000 – x7999) für 39 quai du Président Roosevelt-Niederlassung, Issy-les-Moulineaux, Frankreich</em></span><span class="sxs-lookup"><span data-stu-id="52105-774"><em>Internal number (x7000 – x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France</em></span></span></p></td>
<td align="left"><span data-ttu-id="52105-775">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="52105-775">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="52105-776">+3319999$1</span><span class="sxs-lookup"><span data-stu-id="52105-776">+3319999$1</span></span></td>
<td align="left"><span data-ttu-id="52105-777">Wahr</span><span class="sxs-lookup"><span data-stu-id="52105-777">True</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="52105-778"><strong>FR-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="52105-778"><strong>FR-TollFree</strong></span></span></p>
<p><span data-ttu-id="52105-779"><em>Normalisierung für gebührenfreie Nummern für Frankreich</em></span><span class="sxs-lookup"><span data-stu-id="52105-779"><em>Toll Free number normalization for France</em></span></span></p></td>
<td align="left"><span data-ttu-id="52105-780">^0?(80\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="52105-780">^0?(80\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="52105-781">+33$1</span><span class="sxs-lookup"><span data-stu-id="52105-781">+33$1</span></span></td>
<td align="left"><span data-ttu-id="52105-782">Falsch</span><span class="sxs-lookup"><span data-stu-id="52105-782">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="52105-783"><strong>FR-Service</strong></span><span class="sxs-lookup"><span data-stu-id="52105-783"><strong>FR-Service</strong></span></span></p>
<p><span data-ttu-id="52105-784"><em>Normalisierung für Servicenummern für Frankreich</em></span><span class="sxs-lookup"><span data-stu-id="52105-784"><em>Service number normalization for France</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="52105-785">^(1\d{1,2}|11[68]\d{3}|</span><span class="sxs-lookup"><span data-stu-id="52105-785">^(1\d{1,2}|11[68]\d{3}|</span></span></p>
<p><span data-ttu-id="52105-786">10\d{2}|3\d{3})$</span><span class="sxs-lookup"><span data-stu-id="52105-786">10\d{2}|3\d{3})$</span></span></p></td>
<td align="left"><span data-ttu-id="52105-787">$1</span><span class="sxs-lookup"><span data-stu-id="52105-787">$1</span></span></td>
<td align="left"><span data-ttu-id="52105-788">Falsch</span><span class="sxs-lookup"><span data-stu-id="52105-788">False</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-789">_Tabelle 13: Mandantenwählpläne – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-789">_Table 13 Example of tenant dial plans_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52105-790">Benutzer</span><span class="sxs-lookup"><span data-stu-id="52105-790">User</span></span></th>
<th align="left"><span data-ttu-id="52105-791">Niederlassung</span><span class="sxs-lookup"><span data-stu-id="52105-791">Office</span></span></th>
<th align="left"><span data-ttu-id="52105-792">Typ des Wählplans</span><span class="sxs-lookup"><span data-stu-id="52105-792">Dial Plan Type</span></span></th>
<th align="left"><span data-ttu-id="52105-793">Name des Wählplans</span><span class="sxs-lookup"><span data-stu-id="52105-793">Dial Plan Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-794">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="52105-794">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="52105-795">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-795">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-796">Mandantenwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-796">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-797">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="52105-797">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-798">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="52105-798">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="52105-799">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-799">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-800">Mandantenwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-800">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-801">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="52105-801">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-802">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="52105-802">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="52105-803">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="52105-803">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="52105-804">Mandantenwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-804">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-805">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="52105-805">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-806">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="52105-806">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="52105-807">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-807">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-808">Mandantenwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-808">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-809">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="52105-809">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-810">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="52105-810">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="52105-811">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-811">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-812">Mandantenwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-812">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-813">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="52105-813">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-814">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="52105-814">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="52105-815">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="52105-815">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="52105-816">Mandantenwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-816">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-817">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="52105-817">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-818">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="52105-818">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="52105-819">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-819">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-820">Dienstwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-820">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-821">n/v</span><span class="sxs-lookup"><span data-stu-id="52105-821">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-822">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="52105-822">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="52105-823">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-823">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-824">Dienstwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-824">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-825">n/v</span><span class="sxs-lookup"><span data-stu-id="52105-825">N/A</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-826">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="52105-826">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="52105-827">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="52105-827">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="52105-828">Dienstwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-828">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-829">n/v</span><span class="sxs-lookup"><span data-stu-id="52105-829">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-830">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="52105-830">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="52105-831">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-831">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-832">Mandantenwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-832">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-833">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="52105-833">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-834">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="52105-834">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="52105-835">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-835">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-836">Mandantenwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-836">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-837">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="52105-837">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="52105-838">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="52105-838">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="52105-839">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="52105-839">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="52105-840">Mandantenwählplan</span><span class="sxs-lookup"><span data-stu-id="52105-840">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="52105-841">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="52105-841">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-842">_Tabelle 14: Wählplanzuweisungen – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-842">_Table 14 Example of dial plan assignments_</span></span>


## <a name="microsoft-teams-configurations"></a><span data-ttu-id="52105-843">Microsoft Teams-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="52105-843">Microsoft Teams configurations</span></span>

<span data-ttu-id="52105-844">Da der Audiokonferenzdienst nur für geplante Besprechungen verfügbar ist, müssen Konfigurationen auf Mandantenebene aktiviert werden, die die Planung von Besprechungen (private und Kanalbesprechungen) steuern.</span><span class="sxs-lookup"><span data-stu-id="52105-844">Since Audio Conferencing is only available for scheduled meetings, tenant-level configurations that govern meeting scheduling (private and channel meetings) must be enabled.</span></span>


> [!NOTE]
> <span data-ttu-id="52105-845">Wenn Ihre Organisation Compliance-Anforderungen erfüllen muss, um sicherzustellen, dass alle Besprechungsdiskussionen gefunden werden können, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.</span><span class="sxs-lookup"><span data-stu-id="52105-845">Currently, if your organization has compliance requirements to ensure all meeting discussions are discoverable, you should disable private meetings if the organizer has an Exchange on-premises mailbox.</span></span><br><br>
> <span data-ttu-id="52105-846">Wenn in einem anderen Anwendungsfall alle Besprechungen in der Organisation nur für <strong>eingeladene Benutzer</strong> sichtbar sein müssen, empfehlen wir Ihnen, die Funktion zum Planen von Besprechungen in <strong>Kanälen</strong> zu deaktivieren, um die Offenlegung von Informationen für nicht eingeladene Benutzer zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="52105-846">In another use case, if all meetings in the organization must be visible <strong>to invited parties</strong> only, to avoid disclosing meeting information to uninvited parties, we recommend that you disable the ability to schedule meetings in <strong>channels</strong>.</span></span>

<span data-ttu-id="52105-847">Die als Konfigurationen auf Mandantenebene verfügbaren Einstellungen sind auf alle Benutzer in der Organisation anwendbar und wirken sich auf die gesamte Besprechungsplanung in Teams und nicht nur auf Teams-Besprechungen **mit** Audiokonferenzen aus.</span><span class="sxs-lookup"><span data-stu-id="52105-847">The settings, available as tenant-level configurations, are applicable to all users in the organization, and will impact all meeting scheduling in Teams, not specific to Teams meetings **with** Audio Conferencing.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="52105-848">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="52105-848">Decision Point</span></span></td>
<td align="left"><p><span data-ttu-id="52105-849">Legen Sie fest, ob es für die Organisation erforderlich ist, das Planen von privaten Besprechungen zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="52105-849">Decide if the organization requires to enable or disable scheduling of private meetings.</span></span></p>
<p><span data-ttu-id="52105-850">Legen Sie fest, ob es für die Organisation erforderlich ist, das Planen von Kanalbesprechungen zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="52105-850">Decide if the organization requires to enable or disable scheduling of channel meetings.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="52105-851">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="52105-851">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="52105-852">Dokumentieren Sie die Konfigurationen für die Besprechungsplanung für Teams.</span><span class="sxs-lookup"><span data-stu-id="52105-852">Document the meeting scheduling configurations for Teams.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="52105-853"><strong>Lassen Sie das Planen von privaten Besprechungen zu</strong></span><span class="sxs-lookup"><span data-stu-id="52105-853"><strong>Allow scheduling for private meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-854">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-854">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><span data-ttu-id="52105-855"><strong>Lassen Sie das Planen von Kanalbesprechungen zu</strong></span><span class="sxs-lookup"><span data-stu-id="52105-855"><strong>Allow scheduling for channel meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="52105-856">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52105-856">Disabled.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="52105-857">_Tabelle 15: Microsoft Teams-Besprechungskonfigurationen – Beispiel_</span><span class="sxs-lookup"><span data-stu-id="52105-857">_Table 15 Example of Microsoft Teams meetings configurations_</span></span>


## <a name="document-technical-implementation-plan"></a><span data-ttu-id="52105-858">Dokumentieren des Plans für die technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="52105-858">Document technical implementation plan</span></span>

<span data-ttu-id="52105-859">Verwenden Sie die Entscheidungspunkte oben, um Ihren Plan zur technischen Implementierung zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="52105-859">Use the decision points above to document your technical implementation plan.</span></span>

<span data-ttu-id="52105-860">Mit diesem Plan wird das Projektteam (mit FastTrack oder einem Bereitstellungspartner) mit Informationen zur Ausführung des technischen Onboardings für die Implementierung von Audiokonferenzen versorgt.</span><span class="sxs-lookup"><span data-stu-id="52105-860">This technical implementation plan will provide the project team, which can include FastTrack or a deployment partner, with the information required to execute the technical onboarding for the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="52105-861">In der Regel enthält ein Plan zur technischen Implementierung die folgenden Hauptabschnitte:</span><span class="sxs-lookup"><span data-stu-id="52105-861">In general, a technical implementation plan will contain the following main sections:</span></span>

-   <span data-ttu-id="52105-862">Aktivierungsliste für Audiokonferenzdienst-Standorte</span><span class="sxs-lookup"><span data-stu-id="52105-862">Audio Conferencing service site enablement list</span></span>

-   <span data-ttu-id="52105-863">Lizenzzuweisungsliste für Besprechungsorganisatoren von Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="52105-863">License assignment list for Audio Conferencing meeting organizers</span></span>

-   <span data-ttu-id="52105-864">Zahlen für die Planung des Kommunikationsguthabens</span><span class="sxs-lookup"><span data-stu-id="52105-864">Communications Credits planning numbers</span></span>

-   <span data-ttu-id="52105-865">Details zur Konferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="52105-865">Conference bridge details</span></span>

-   <span data-ttu-id="52105-866">Einstellungen der Konferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="52105-866">Conference bridge settings</span></span>

-   <span data-ttu-id="52105-867">Zuweisungen der Einstellungen für die Konferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="52105-867">Conference bridge settings assignments</span></span>

-   <span data-ttu-id="52105-868">Mandantenwählpläne</span><span class="sxs-lookup"><span data-stu-id="52105-868">Tenant dial plans</span></span>

-   <span data-ttu-id="52105-869">Wählplanzuweisungen</span><span class="sxs-lookup"><span data-stu-id="52105-869">Dial plan assignments</span></span>

-   <span data-ttu-id="52105-870">Microsoft Teams-Besprechungskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="52105-870">Microsoft Teams meetings configurations</span></span>

<span data-ttu-id="52105-871">Nach Abschluss des Erfolgsplans und des Plans zur technischen Implementierung können Sie Ihrer Organisation jetzt die nächsten Schritte entlang des Office 365 Customer Journey unterbreiten.</span><span class="sxs-lookup"><span data-stu-id="52105-871">With the completion of success plan and technical implementation plan, you are now ready to take your organization to the next steps along the Office 365 customer journey.</span></span>

<a name="onboard"></a><span data-ttu-id="52105-872">Onboarding</span><span class="sxs-lookup"><span data-stu-id="52105-872">Onboard</span></span>
=======

<span data-ttu-id="52105-873">*In Kürze verfügbar.*</span><span class="sxs-lookup"><span data-stu-id="52105-873">*Coming Soon*</span></span>

<a name="drive-value"></a><span data-ttu-id="52105-874">Höhere Wertschöpfung erzielen</span><span class="sxs-lookup"><span data-stu-id="52105-874">Drive Value</span></span>
===========

<span data-ttu-id="52105-875">*In Kürze verfügbar.*</span><span class="sxs-lookup"><span data-stu-id="52105-875">*Coming Soon*</span></span>



### <a name="see-also"></a><span data-ttu-id="52105-876">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52105-876">See also</span></span>
[<span data-ttu-id="52105-877">Konfigurieren von Einwahl- oder PSTN-Konferenzen für Skype for Business</span><span class="sxs-lookup"><span data-stu-id="52105-877">Set up dial-in or PSTN conferencing for Skype for Business</span></span>](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
