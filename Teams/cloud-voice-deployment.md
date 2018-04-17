---
title: Cloud Voice-Bereitstellung
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/10/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Praktische Anleitungen für die Bereitstellung von Cloud-VoIP-Funktionen in Microsoft Teams
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4828cb7c27c53387e0efae800167cef1b53dd4b6
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="cf705-103">Cloud Voice-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="cf705-103">Cloud voice deployment</span></span>

<span data-ttu-id="cf705-104">Microsoft-Teams, die-Hub für Zusammenarbeit und Kommunikation in Office 365, bietet jetzt Audiokonferenzen und Telefonsystem mit Aufrufen plant Funktionen bereit, mit zusätzlichen Anforderungen gerecht durch Erweitern der Besprechung Teams und Aufrufen von Erfahrung eingeschlossen externe Parteien, die über das öffentliche Telefonfestnetz (PSTN) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="cf705-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>
 
<span data-ttu-id="cf705-105">Wir aktualisieren diese Seite, wenn im Lauf der Zeit zusätzliche Cloud-VoIP-Funktionen für Microsoft Teams veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="cf705-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="cf705-106">Audiokonferenzen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf705-106">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="cf705-107">Mit der Funktion für Audiokonferenzen in Office 365 können Teilnehmer mit einem beliebigen Telefon an Ihren Microsoft Teams-Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="cf705-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="cf705-108">Das bekommen Sie mit [Audiokonferenzen](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf705-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="cf705-109">Telefonsystem mit Aufrufen von Plänen in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="cf705-109">Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="cf705-110">Das Telefonsystem ist eine Office 365-Funktion, die das Verwalten von Anrufweiterleitung, Richtlinien und Benutzerbereitstellung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="cf705-110">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="cf705-111">Dazu gehören ein Verwaltungssystem für Telefonanrufe sowie Anrufweiterleitung und Anrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="cf705-111">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="cf705-112">Office 365-Anrufpläne werden als Add-On-Dienst für die Telefonsystemfunktion über Microsoft Teams und Skype for Business Online bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cf705-112">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="cf705-113">Aufrufen von Plänen finden Sie die Personen in Ihrem Unternehmen mit eine primäre Rufnummer number und ermöglicht ihnen das tätigen und Entgegennehmen von Anrufen außerhalb Ihrer Organisation über das Telefonfestnetz.</span><span class="sxs-lookup"><span data-stu-id="cf705-113">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="cf705-114">Weitere Informationen finden Sie unter [Das bietet Ihnen das Telefonsystem in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) und [Was sind Anrufpläne in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429).</span><span class="sxs-lookup"><span data-stu-id="cf705-114">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>


## <a name="practical-guidance-for-audio-conferencing-and-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="cf705-115">Ihnen praktische Leitfäden für Audiokonferenzen und Telefonsystem mit Aufrufen in Microsoft-Teams, Pläne</span><span class="sxs-lookup"><span data-stu-id="cf705-115">Practical guidance for Audio Conferencing and Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="cf705-116">Diese Ihnen praktische Leitfäden wird mithilfe des Office 365 schnelle Kunden Reise Frameworks organisiert und drei Phasen&mdash;Ermitteln übergeordneter Faktoren, integriert, und der Wert Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="cf705-116">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="cf705-117">Es wurde beim Planen, bereitstellen und Aufrufen plant die Implementierung einer erfolgreichen Audiokonferenzen oder Telefonsystem effektives unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="cf705-117">It's intended to help you plan, deliver, and operate a successful Audio Conferencing or Phone System with Calling Plans implementation.</span></span>

|<span data-ttu-id="cf705-118">Ausblick</span><span class="sxs-lookup"><span data-stu-id="cf705-118">Envision</span></span>  |<span data-ttu-id="cf705-119">Onboarding</span><span class="sxs-lookup"><span data-stu-id="cf705-119">Onboard</span></span>  |<span data-ttu-id="cf705-120">Höhere Wertschöpfung erzielen</span><span class="sxs-lookup"><span data-stu-id="cf705-120">Drive Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cf705-121">Meine Erfolg definieren</span><span class="sxs-lookup"><span data-stu-id="cf705-121">Define my success</span></span> <br> <span data-ttu-id="cf705-122">Meine Service treffe</span><span class="sxs-lookup"><span data-stu-id="cf705-122">Make my service decisions</span></span> <br> <span data-ttu-id="cf705-123">Meine Umgebung bewerten</span><span class="sxs-lookup"><span data-stu-id="cf705-123">Evaluate my environment</span></span> <br> <span data-ttu-id="cf705-124">Planen der Verwaltung von Meine service</span><span class="sxs-lookup"><span data-stu-id="cf705-124">Plan my service management</span></span> <br> <span data-ttu-id="cf705-125">Planen von meiner Benutzer-Erlebnis</span><span class="sxs-lookup"><span data-stu-id="cf705-125">Plan my users' experience</span></span> <br> <span data-ttu-id="cf705-126">Dokumentieren Sie meine Erfolg</span><span class="sxs-lookup"><span data-stu-id="cf705-126">Document my success plan</span></span>    | <span data-ttu-id="cf705-127">Meine Service vorbereiten</span><span class="sxs-lookup"><span data-stu-id="cf705-127">Prepare my service</span></span> <br> <span data-ttu-id="cf705-128">Vorbereiten der Benutzer</span><span class="sxs-lookup"><span data-stu-id="cf705-128">Prepare my users</span></span> <br> <span data-ttu-id="cf705-129">Stellen Sie meine Dienst</span><span class="sxs-lookup"><span data-stu-id="cf705-129">Deploy my service</span></span>  <br> <br> <br> <br>     | <span data-ttu-id="cf705-130">Meine Dienst betreiben</span><span class="sxs-lookup"><span data-stu-id="cf705-130">Operate my service</span></span> <br> <span data-ttu-id="cf705-131">Meine Service zu verbessern</span><span class="sxs-lookup"><span data-stu-id="cf705-131">Enhance my service</span></span> <br> <br> <br> <br> <br>      |

<span data-ttu-id="cf705-132">Der Inhalt in einer sortierten und Weise dargestellt wird, und ist darauf ausgelegt, die Sie über eine End-to-End-Bereitstellung Weg von seinem Anfang bis zu bringen.</span><span class="sxs-lookup"><span data-stu-id="cf705-132">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="cf705-133">Wenn Sie bereits aktiv bereitstellen, empfehlen wir noch Ihnen auf die entsprechenden Abschnitten Inhalte zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="cf705-133">If you're already actively deploying, we still encourage you to reference the applicable content areas.</span></span>



> [!TIP]
> <span data-ttu-id="cf705-134">In diesem Ihnen praktische Leitfäden sind wir bereit, dass für jede Aktivität und wichtige Diskussion wird ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="cf705-134">In this practical guidance, we're providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="cf705-135">Die Beispiele in diesem Dokument werden in Tipp Legenden eingeschlossen, und sie dienen als eine Vorlage, die Sie wiederverwenden können.</span><span class="sxs-lookup"><span data-stu-id="cf705-135">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="cf705-136">Der Hinweis „TBA“ (To Be Added, wird ergänzt) zeigt an, dass Sie hier Informationen als Teil Ihres Planungsprozesses eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="cf705-136">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>