---
title: Einführung in die richtlinienbasierte Aufzeichnung von Teams für den Anruf & Besprechungen
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Informationen zu Teamrichtlinien basierter Aufzeichnung für den Anruf & Besprechungen
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a7a40a4f7e99f79f67c0aaea0e5259652b5a8d8
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908574"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="e3300-103">Einführung in die richtlinienbasierte Aufzeichnung von Teams für Anrufe & Besprechungen</span><span class="sxs-lookup"><span data-stu-id="e3300-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="e3300-104">Mithilfe einer richtlinienbasierten Aufzeichnung können Organisationen, die Microsoft Teams für Anrufe und Besprechungen übernehmen, unter Verwendung einer Verwaltungsrichtlinie festlegen, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die spätere Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies in den entsprechenden Unternehmens-oder Aufsichtsrichtlinien erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e3300-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="e3300-105">Teams wurden verbessert, um die Integration von Drittanbieter-Aufzeichnungslösungen zu unterstützen, einschließlich der Plattformfunktionen, Benutzer Erfahrungen und administrativen Schnittstellen, die für die Bereitstellung einer End-to-End-Lösung für die Konfiguration, Verwaltung, Aufzeichnung, Speicherung und Analyse von Teams-Kommunikationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e3300-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="e3300-106">Dazu gehören Kommunikationsplattform-APIs und Ereignisse für die Aufzeichnung, die Folgendes bietet:</span><span class="sxs-lookup"><span data-stu-id="e3300-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="e3300-107">Nahtlose, qualitativ hochwertige Medien Erfassung auf allen Geräten und alle unterstützten Endpunkte für Audio, Video, Bildschirmfreigabe und Chat.</span><span class="sxs-lookup"><span data-stu-id="e3300-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="e3300-108">Unterstützung für die Interaktions Erfassung zwischen Teams-Benutzern und unterstützten Anruf Endpunkten (Teams, Mobile Teams, Skype for Business, PSTN)</span><span class="sxs-lookup"><span data-stu-id="e3300-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="e3300-109">Neue administrative Richtlinien für die Konformitäts Aufzeichnung, einschließlich der Integration in vorhandene Teams administrative Anruf-und Besprechungstools und-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e3300-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="e3300-110">Die Konformitäts Aufzeichnung kann für Benutzer von Microsoft 365 a3/A5/E3/E5 und Office 365 a3/A5/E3/E5 aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e3300-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5 and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="e3300-111">Die Integrationsfunktionen der Kompatibilitäts Aufzeichnung wurden auch bei Ignite 2019 in der [<span class="underline">Sitzung Compliance Recording und Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)überprüft.</span><span class="sxs-lookup"><span data-stu-id="e3300-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="e3300-112">Übersicht über die Interaktions Aufzeichnung für Teams</span><span class="sxs-lookup"><span data-stu-id="e3300-112">Teams interaction recording overview</span></span>

<span data-ttu-id="e3300-113">Anwendungsfälle für die Interaktions Aufzeichnung können effektiv in vier primäre Kategorien von Aufzeichnungsfunktionen aufgeteilt werden – Bequemlichkeit, funktionelle, organisatorische und rechtmäßige abfangfunktion, wie in der Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e3300-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="e3300-114">![Screenshot der Interaktions Aufzeichnung was und warum.](media/recording-taxonomy.png "Das Bild zeigt die Aufzeichnungs Kategorien.")</span><span class="sxs-lookup"><span data-stu-id="e3300-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="e3300-115">Jede der Kategorien umfasst unterschiedliche Anforderungen für die Art und Weise, wie Aufzeichnungen initiiert werden, was aufgezeichnet wird, wo Aufzeichnungen gespeichert werden, wer benachrichtigt wird, wer den Zugriff steuert und wie die Aufbewahrung gehandhabt wird.</span><span class="sxs-lookup"><span data-stu-id="e3300-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="e3300-116">Typ</span><span class="sxs-lookup"><span data-stu-id="e3300-116">Type</span></span>                   | <span data-ttu-id="e3300-117">Komfort</span><span class="sxs-lookup"><span data-stu-id="e3300-117">Convenience</span></span>        | <span data-ttu-id="e3300-118">Funktions</span><span class="sxs-lookup"><span data-stu-id="e3300-118">Functional</span></span>         | <span data-ttu-id="e3300-119">Org-allgemein</span><span class="sxs-lookup"><span data-stu-id="e3300-119">Org - General</span></span>      | <span data-ttu-id="e3300-120">Org-reguliert</span><span class="sxs-lookup"><span data-stu-id="e3300-120">Org - Regulated</span></span> | <span data-ttu-id="e3300-121">Rechtmäßiger Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e3300-121">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="e3300-122">Initiator</span><span class="sxs-lookup"><span data-stu-id="e3300-122">Initiator</span></span>              | <span data-ttu-id="e3300-123">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e3300-123">User</span></span>               | <span data-ttu-id="e3300-124">App/Lösung</span><span class="sxs-lookup"><span data-stu-id="e3300-124">App/Solution</span></span>       | <span data-ttu-id="e3300-125">Administrator (System)</span><span class="sxs-lookup"><span data-stu-id="e3300-125">Admin (system)</span></span>     | <span data-ttu-id="e3300-126">Administrator (System)</span><span class="sxs-lookup"><span data-stu-id="e3300-126">Admin (system)</span></span>  | <span data-ttu-id="e3300-127">Lea</span><span class="sxs-lookup"><span data-stu-id="e3300-127">LEA</span></span>                |
| <span data-ttu-id="e3300-128"> Target</span><span class="sxs-lookup"><span data-stu-id="e3300-128">Target</span></span>                 | <span data-ttu-id="e3300-129">Pro Anruf/Besprechung</span><span class="sxs-lookup"><span data-stu-id="e3300-129">Per-call / meeting</span></span> | <span data-ttu-id="e3300-130">Pro Anruf/Besprechung</span><span class="sxs-lookup"><span data-stu-id="e3300-130">Per-call / meeting</span></span> | <span data-ttu-id="e3300-131">Pro Anruf/Besprechung</span><span class="sxs-lookup"><span data-stu-id="e3300-131">Per-call / meeting</span></span> | <span data-ttu-id="e3300-132">Pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="e3300-132">Per-user</span></span>        | <span data-ttu-id="e3300-133">Pro Endpunkt/did</span><span class="sxs-lookup"><span data-stu-id="e3300-133">Per-endpoint / DID</span></span> |
| <span data-ttu-id="e3300-134">Speicher Besitzer</span><span class="sxs-lookup"><span data-stu-id="e3300-134">Storage owner</span></span>          | <span data-ttu-id="e3300-135">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e3300-135">User</span></span>               | <span data-ttu-id="e3300-136">App</span><span class="sxs-lookup"><span data-stu-id="e3300-136">App</span></span>                | <span data-ttu-id="e3300-137">Admin</span><span class="sxs-lookup"><span data-stu-id="e3300-137">Admin</span></span>              | <span data-ttu-id="e3300-138">Compliance</span><span class="sxs-lookup"><span data-stu-id="e3300-138">Compliance</span></span>      | <span data-ttu-id="e3300-139">Lea</span><span class="sxs-lookup"><span data-stu-id="e3300-139">LEA</span></span>                |
| <span data-ttu-id="e3300-140">Benachrichtigung erforderlich?</span><span class="sxs-lookup"><span data-stu-id="e3300-140">Notification required?</span></span> | <span data-ttu-id="e3300-141">Ja</span><span class="sxs-lookup"><span data-stu-id="e3300-141">Yes</span></span>                | <span data-ttu-id="e3300-142">Ja</span><span class="sxs-lookup"><span data-stu-id="e3300-142">Yes</span></span>                | <span data-ttu-id="e3300-143">Ja</span><span class="sxs-lookup"><span data-stu-id="e3300-143">Yes</span></span>                | <span data-ttu-id="e3300-144">Ja</span><span class="sxs-lookup"><span data-stu-id="e3300-144">Yes</span></span>             | <span data-ttu-id="e3300-145">Nein</span><span class="sxs-lookup"><span data-stu-id="e3300-145">No</span></span>                 |
| <span data-ttu-id="e3300-146">Zugriffs Besitzer</span><span class="sxs-lookup"><span data-stu-id="e3300-146">Access Owner</span></span>           | <span data-ttu-id="e3300-147">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e3300-147">User</span></span>               | <span data-ttu-id="e3300-148">App</span><span class="sxs-lookup"><span data-stu-id="e3300-148">App</span></span>                | <span data-ttu-id="e3300-149">Admin</span><span class="sxs-lookup"><span data-stu-id="e3300-149">Admin</span></span>              | <span data-ttu-id="e3300-150">Compliance</span><span class="sxs-lookup"><span data-stu-id="e3300-150">Compliance</span></span>      | <span data-ttu-id="e3300-151">Lea</span><span class="sxs-lookup"><span data-stu-id="e3300-151">LEA</span></span>                |
| <span data-ttu-id="e3300-152">Aufbewahrungsrichtlinie?</span><span class="sxs-lookup"><span data-stu-id="e3300-152">Retention Policy?</span></span>      | <span data-ttu-id="e3300-153">Optional</span><span class="sxs-lookup"><span data-stu-id="e3300-153">Optional</span></span>           | <span data-ttu-id="e3300-154">Ja</span><span class="sxs-lookup"><span data-stu-id="e3300-154">Yes</span></span>                | <span data-ttu-id="e3300-155">Ja</span><span class="sxs-lookup"><span data-stu-id="e3300-155">Yes</span></span>                | <span data-ttu-id="e3300-156">Ja</span><span class="sxs-lookup"><span data-stu-id="e3300-156">Yes</span></span>             | <span data-ttu-id="e3300-157">Ja</span><span class="sxs-lookup"><span data-stu-id="e3300-157">Yes</span></span>                |

<span data-ttu-id="e3300-158">Teams bietet verschiedene Funktionen für die [<span class="underline">bequeme</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) und funktionelle Aufzeichnung für Besprechungen und Live-Events.</span><span class="sxs-lookup"><span data-stu-id="e3300-158">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="e3300-159">Die organisatorische Aufzeichnung bedeutet, dass Organisationen, die Teams für Anrufe und Besprechungen einführen, in einer administrativen Richtlinie festlegen können, ob Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die spätere Verarbeitung und Aufbewahrung nach Maßgabe der einschlägigen Unternehmens-oder Aufsichtsrichtlinien festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e3300-159">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="e3300-160">Benutzern, die dieser Richtlinie unterliegen, ist bewusst, dass Ihre digitalen Interaktionen mit Teams aufgezeichnet werden, Sie aber nicht in der Lage sind, die Aufzeichnung zu deaktivieren, und nach Abschluss der Interaktion keinen Zugriff auf die Aufzeichnung hat.</span><span class="sxs-lookup"><span data-stu-id="e3300-160">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="e3300-161">Die Aufzeichnung wird Teil des Organisations Archivs, das Compliance-und juristischen Personen für eDiscovery, rechtliche Aufbewahrung und andere Unternehmens Aufbewahrungszwecke zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="e3300-161">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="e3300-162">Beispiel für Benutzeranforderungen</span><span class="sxs-lookup"><span data-stu-id="e3300-162">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e3300-163"><strong>Persona</strong></span><span class="sxs-lookup"><span data-stu-id="e3300-163"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="e3300-164"><strong>Muss</strong></span><span class="sxs-lookup"><span data-stu-id="e3300-164"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e3300-165">Aufgezeichnete Benutzer</span><span class="sxs-lookup"><span data-stu-id="e3300-165">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="e3300-166">Benachrichtigt werden, wenn die Aufzeichnung gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e3300-166">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="e3300-167">Informieren Sie sich, wenn der Richtlinien-und/oder Rekorder-Fehler Änderungen beim Anrufverhalten verursacht.</span><span class="sxs-lookup"><span data-stu-id="e3300-167">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e3300-168">Kommunikations Administrator</span><span class="sxs-lookup"><span data-stu-id="e3300-168">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="e3300-169">Erläutern Sie, warum und wie Sie Aufzeichnungs Richtlinien für Benutzer/Endpunkte von Teams anwenden/erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e3300-169">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="e3300-170">Konfigurieren und Verwalten von Teams zum Aufzeichnen von Richtlinien für die Organisation</span><span class="sxs-lookup"><span data-stu-id="e3300-170">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="e3300-171">Überwachen und behandeln von Problemen mit der Aufzeichnung bei Anrufen und Besprechungen in Teams.</span><span class="sxs-lookup"><span data-stu-id="e3300-171">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="e3300-172">Unterstützen Sie den internen Compliance Officer mit betrieblichen Analysen zu Nutzung, Qualität und Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="e3300-172">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e3300-173">Compliance Officer</span><span class="sxs-lookup"><span data-stu-id="e3300-173">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="e3300-174">Sammeln Sie alle Teams-Kommunikationen in der Weise, die erforderlich ist, um Compliance-Verpflichtungen in angemessenen regionalen Grenzen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e3300-174">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="e3300-175">Suchen Sie nach Interaktionen basierend auf kommunikationsbezogenen Metadaten oder Interaktions Inhalten.</span><span class="sxs-lookup"><span data-stu-id="e3300-175">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="e3300-176">Gängige Beispiele sind:</span><span class="sxs-lookup"><span data-stu-id="e3300-176">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="e3300-177"><strong>Metadaten</strong> - Teilnehmer, Zeit, Richtung, gewählte Nummer, Herkunftsnummer, benutzerdefinierte Geschäftsdaten</span><span class="sxs-lookup"><span data-stu-id="e3300-177"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="e3300-178"><strong>Inhalt</strong> – Transkription, Sentiment, Phonetik, Verwandte Interaktionen</span><span class="sxs-lookup"><span data-stu-id="e3300-178"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="e3300-179">Analysieren und interagieren Sie mit gesammelten Kommunikationen, einschließlich der Möglichkeit, Interaktionen während der Erfassung zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="e3300-179">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="e3300-180">Sicherstellen der Sicherheit der gesammelten Kommunikation und verhindern von Manipulationen in allen Phasen.</span><span class="sxs-lookup"><span data-stu-id="e3300-180">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="e3300-181">Übersicht über die Lösungsarchitektur</span><span class="sxs-lookup"><span data-stu-id="e3300-181">Solution architecture overview</span></span>

<span data-ttu-id="e3300-182">Lösungen für die Compliance-Aufzeichnung sind in Teams integriert, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e3300-182">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="e3300-183">![Screenshot mit der Einstellung "benutzerdefinierte App für Team"](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Die Bilder zeigen den Fluss an, wenn eine Teams-Besprechung oder ein Anruf gesendet und empfangen wird.")</span><span class="sxs-lookup"><span data-stu-id="e3300-183">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="e3300-184">Recorder</span><span class="sxs-lookup"><span data-stu-id="e3300-184">Recorder</span></span>

<span data-ttu-id="e3300-185">Die wichtigste Komponente der Compliance-Aufzeichnungslösung ist die Aufzeichnung.</span><span class="sxs-lookup"><span data-stu-id="e3300-185">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="e3300-186">Datenschreiber sind als skalierbare Azure-based Services (Bots) konzipiert, die die [<span class="underline">Kommunikationsplattform von Microsoft nutzen</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) und sich als Anwendungen mit Microsoft Graph registrieren.</span><span class="sxs-lookup"><span data-stu-id="e3300-186">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="e3300-187">Der Recorder bietet die direkte Interaktion mit den Teams für Anrufe und Besprechungen der [<span class="underline">Kommunikationsplattform-APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) und stellt den Endpunkt für die Medien aufnahmebereit.</span><span class="sxs-lookup"><span data-stu-id="e3300-187">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="e3300-188">Eine [<span class="underline">Beispielanwendung für Compliance-Recorder steht zur Verfügung</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , die zeigt, wie der bot konfiguriert, die app-Instanz erstellt und die Konformitätsrichtlinien zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e3300-188">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="e3300-189">Das Beispiel enthält auch Beispiele für die API-Verwendung für die Aufzeichnung bestimmter Interaktionen, beispielsweise die Behandlung des [<span class="underline">eingehenden Anruf</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) Routings, [<span class="underline">Ändern der Aufnahme Zustände</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)und [<span class="underline">Entfernen des Benutzers, der aufgezeichnet wird</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="e3300-189">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="e3300-190">Graph-Dokumentation zu den spezifischen APIs finden Sie hier für [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) und [<span class="underline">incomingcontext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="e3300-190">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="e3300-191">Die genaue Implementierung des Recorder-Diensts variiert je nach Partner, muss aber so konzipiert sein, dass mehrere Datenschreiber unterstützt werden, um eine hohe Verfügbarkeit und geografische Verteilung der Bereitstellung zu erreichen, um die Latenz von Teams auf die Aufzeichnung zu verringern.</span><span class="sxs-lookup"><span data-stu-id="e3300-191">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="e3300-192">Außerdem wird davon ausgegangen, dass die Datenschreiber selbst mit Flexibilität und Redundanz konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="e3300-192">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="e3300-193">Partner müssen die mindestens erforderliche Veröffentlichungsversion der Microsoft Graph Communications-APIs und-SDKs mit Microsoft bestätigen, bevor Sie Ihre Lösung für die Zertifizierung übermitteln, um sicherzustellen, dass alle Anforderungen der Integration der Konformitäts Aufzeichnung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e3300-193">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="e3300-194">Zwei spezifische Anforderungen, die für das Szenario der Konformitäts Aufzeichnung grundlegend sind, sind:</span><span class="sxs-lookup"><span data-stu-id="e3300-194">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="e3300-195">Recorder-bot muss in Azure bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="e3300-195">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="e3300-196">Der Recorder-bot muss auf einer Windows-VM in Azure ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="e3300-196">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="e3300-197">Die Azure-und Windows-VM-Anforderungen gelten nur für die Teams-bot-Komponente, was bedeutet, dass ein Partner die restliche Plattform Ihrer Wahl implementieren kann, vorausgesetzt, Sie kann die relevanten Leistungs-und Funktionsanforderungen für die Compliance-Aufzeichnung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e3300-197">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="e3300-198">Richtlinienzuweisung und Bereitstellung von Compliance-Aufzeichnungen</span><span class="sxs-lookup"><span data-stu-id="e3300-198">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="e3300-199">IT-Administratoren können ermitteln, welche Benutzer aufgezeichnet werden und welche Aufzeichnung für jeden Benutzer verwendet werden soll, indem Sie Richtlinien für die Konformitäts Aufzeichnung erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e3300-199">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="e3300-200">Datenschreiber werden automatisch zur Teilnahme an Unterhaltungen eingeladen, die auf der Konfiguration dieser Richtlinien basieren, wenn eine Kommunikations Interaktion stattfindet.</span><span class="sxs-lookup"><span data-stu-id="e3300-200">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="e3300-201">Richtlinien für die Richtlinien Konformitäts Aufzeichnung werden mithilfe von [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) verwaltet und können für jede Organisation auf Mandanten-, pro-Benutzer-und Sicherheitsgruppen Ebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3300-201">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="e3300-202">Weitere Informationen zu Microsoft docs für [<span class="underline">Besprechungsrichtlinien</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">Anruf Richtlinien</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) und  [<span class="underline">Gruppenrichtlinien</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="e3300-202">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="e3300-203">Erstellen Sie eine Anwendungsinstanz in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="e3300-203">Create an application instance in your tenant.</span></span>

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. <span data-ttu-id="e3300-204">Erstellen einer Richtlinie für die Konformitäts Aufzeichnung</span><span class="sxs-lookup"><span data-stu-id="e3300-204">Create a Compliance Recording policy.</span></span>

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span data-ttu-id="e3300-205"><span class="underline">Satz-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="e3300-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="e3300-206">Weisen Sie die Richtlinien für die Konformitäts Aufzeichnung einem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="e3300-206">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="e3300-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="e3300-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="e3300-208">Benutzererlebnisse</span><span class="sxs-lookup"><span data-stu-id="e3300-208">User experiences</span></span>

<span data-ttu-id="e3300-209">Die Unterstützung für Benachrichtigungen wird mithilfe der Erfahrungen des Teams-Clients aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e3300-209">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="e3300-210">Die Erfahrungen können entweder visuell oder Audio sein.</span><span class="sxs-lookup"><span data-stu-id="e3300-210">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="e3300-211">**Teams-Clients – visuelle Benachrichtigung**</span><span class="sxs-lookup"><span data-stu-id="e3300-211">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="e3300-212">Desktop/Web</span><span class="sxs-lookup"><span data-stu-id="e3300-212">Desktop/web</span></span>
- <span data-ttu-id="e3300-213">Mobil (IOS/Android)</span><span class="sxs-lookup"><span data-stu-id="e3300-213">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="e3300-214">Teams-Telefone</span><span class="sxs-lookup"><span data-stu-id="e3300-214">Teams phones</span></span>
- <span data-ttu-id="e3300-215">Teams-Räume</span><span class="sxs-lookup"><span data-stu-id="e3300-215">Teams rooms</span></span>

<span data-ttu-id="e3300-216">**Andere Endpunkte-Audio-Hinweis**</span><span class="sxs-lookup"><span data-stu-id="e3300-216">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="e3300-217">SIP-Telefone</span><span class="sxs-lookup"><span data-stu-id="e3300-217">SIP phones</span></span>
- <span data-ttu-id="e3300-218">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e3300-218">Skype for Business</span></span>
- <span data-ttu-id="e3300-219">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="e3300-219">Audio conferencing</span></span>
- <span data-ttu-id="e3300-220">PSTN-Anrufer</span><span class="sxs-lookup"><span data-stu-id="e3300-220">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="e3300-221">Konformitäts Aufzeichnung für Teams-Zertifizierungsprogramme</span><span class="sxs-lookup"><span data-stu-id="e3300-221">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="e3300-222">Neben der Veröffentlichung öffentlich verfügbarer APIs, die Partnern die Entwicklung und Integration von CCaaS-Lösungen in Teams ermöglichen, haben wir das Zertifizierungsprogramm für die Compliance-Aufzeichnung für Microsoft Teams entwickelt, um Kunden die Gewissheit zu bieten, dass die Lösung jedes teilnehmenden Partners getestet und überprüft wurde, um die Qualität, Kompatibilität und Zuverlässigkeit zu gewährleisten, die Sie von Microsoft-Lösungen erwarten.</span><span class="sxs-lookup"><span data-stu-id="e3300-222">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="e3300-223">Die folgenden Partner haben Ihre Lösung für Microsoft Teams zertifiziert.</span><span class="sxs-lookup"><span data-stu-id="e3300-223">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="e3300-224">Partner</span><span class="sxs-lookup"><span data-stu-id="e3300-224">Partner</span></span>|<span data-ttu-id="e3300-225">Lösungs Website</span><span class="sxs-lookup"><span data-stu-id="e3300-225">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="e3300-226">Schön</span><span class="sxs-lookup"><span data-stu-id="e3300-226">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="e3300-227">Die folgenden Partner sind dabei, Ihre Lösung für Microsoft Teams zu zertifizieren.</span><span class="sxs-lookup"><span data-stu-id="e3300-227">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="e3300-228">Partner</span><span class="sxs-lookup"><span data-stu-id="e3300-228">Partner</span></span>|<span data-ttu-id="e3300-229">Lösungs Website</span><span class="sxs-lookup"><span data-stu-id="e3300-229">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="e3300-230">ASC-Technologien</span><span class="sxs-lookup"><span data-stu-id="e3300-230">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="e3300-231">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="e3300-231">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="e3300-232">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="e3300-232">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="e3300-233">Dubber</span><span class="sxs-lookup"><span data-stu-id="e3300-233">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="e3300-234">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="e3300-234">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="e3300-235">Luware</span><span class="sxs-lookup"><span data-stu-id="e3300-235">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="e3300-236">Numonix</span><span class="sxs-lookup"><span data-stu-id="e3300-236">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="e3300-237">Oak-Innovation</span><span class="sxs-lookup"><span data-stu-id="e3300-237">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="e3300-238">Rotes Feld</span><span class="sxs-lookup"><span data-stu-id="e3300-238">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="e3300-239">Verint</span><span class="sxs-lookup"><span data-stu-id="e3300-239">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="e3300-240">Diese Liste wird aktualisiert, wenn weitere Partner teilnehmen und die Zertifizierungskriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e3300-240">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e3300-241">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e3300-241">Next steps</span></span>

<span data-ttu-id="e3300-242">Wenn Sie ein Anbieter sind und versuchen, dem Zertifizierungsprogramm beizutreten, senden Sie  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@Microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="e3300-242">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
