---
title: Cloud Voice-Bereitstellung
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/13/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Praktische Anleitungen für die Bereitstellung von Cloud-VoIP-Funktionen in Microsoft Teams
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45528d71dc04b96d77b454d5db402648779c1ac9
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
#<a name="cloud-voice-deployment"></a><span data-ttu-id="12240-103">Cloud Voice-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="12240-103">Cloud voice deployment</span></span>

<span data-ttu-id="12240-104">Microsoft Teams, die Drehscheibe für Teamarbeit und Kommunikation in Office 365, bietet jetzt Funktionen für Audiokonferenzen und ein Telefonsystem mit Anrufplänen, um zusätzlichen Geschäftsanforderungen gerecht zu werden. Dazu wurde die Funktionalität der Besprechungen und Anrufe in Microsoft Teams erweitert, sodass jetzt auch externe Benutzer über das Telefonfestnetz teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="12240-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the Public Switched Telephone Network (PSTN).</span></span>
 
<span data-ttu-id="12240-105">Wir aktualisieren diese Seite, wenn im Lauf der Zeit zusätzliche Cloud-VoIP-Funktionen für Microsoft Teams veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="12240-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>


##<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="12240-106">Praktische Anleitungen für Audiokonferenzen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12240-106">Practical guidance for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="12240-107">Mit der Funktion für Audiokonferenzen in Office 365 können Teilnehmer mit einem beliebigen Telefon an Ihren Microsoft Teams-Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="12240-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="12240-108">Das bekommen Sie mit [Audiokonferenzen](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="12240-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

<span data-ttu-id="12240-109">Diese praktischen Anleitungen führen Sie durch das Framework der Office 365 FastTrack Customer Journey und seine drei Phasen (Konzeptionierung, Onboarding und Wertschöpfung), damit Sie eine erfolgreiche Implementierung von Audiokonferenzen planen, bereitstellen und verwenden können, mit der Sie dann positive Geschäftsergebnisse erzielen.</span><span class="sxs-lookup"><span data-stu-id="12240-109">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases, Envision, Onboard, and Drive Value, to help you plan, deliver, and operate an Audio Conferencing implementation towards succesful business outcomes.</span></span>

> [!TIP]
> <span data-ttu-id="12240-110">Sie erhalten hier Beispielergebnisse für die einzelnen Aktivitäten und die wichtigsten Diskussionspunkte.</span><span class="sxs-lookup"><span data-stu-id="12240-110">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="12240-111">Die Beispiele in diesem Dokument, die Sie als wiederverwendbare Vorlagen nutzen können, finden Sie in den mit „Tipp“ beschrifteten Kästen.</span><span class="sxs-lookup"><span data-stu-id="12240-111">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="12240-112">Der Hinweis „TBA“ (To Be Added, wird ergänzt) zeigt an, dass Sie hier Informationen als Teil Ihres Planungsprozesses eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="12240-112">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

##<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="12240-113">Praktische Anleitungen für Telefonsysteme mit Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12240-113">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="12240-114">Das Telefonsystem ist eine Office 365-Funktion, die das Verwalten von Anrufweiterleitung, Richtlinien und Benutzerbereitstellung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="12240-114">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="12240-115">Dazu gehören ein Verwaltungssystem für Telefonanrufe sowie Anrufweiterleitung und Anrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="12240-115">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="12240-116">Office 365-Anrufpläne werden als Add-On-Dienst für die Telefonsystemfunktion über Microsoft Teams und Skype for Business Online bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="12240-116">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="12240-117">Mit Anrufplänen erhalten die Mitarbeiter Ihres Unternehmens eine primäre Telefonnummer, über die sie außerhalb der Organisation Telefonanrufe über das Telefonfestnetz (Public Switched Telephone Network, PSTN) tätigen und erhalten können.</span><span class="sxs-lookup"><span data-stu-id="12240-117">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="12240-118">Weitere Informationen finden Sie unter [Das bietet Ihnen das Telefonsystem in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) und [Was sind Anrufpläne in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429).</span><span class="sxs-lookup"><span data-stu-id="12240-118">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>

<span data-ttu-id="12240-119">Diese praktischen Anleitungen führen Sie durch das Framework der Office 365 FastTrack Customer Journey und seine drei Phasen (Konzeptionierung, Onboarding und Wertschöpfung), damit Sie eine erfolgreiche Implementierung des Telefonsystems mit Anrufplänen planen, bereitstellen und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="12240-119">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases - Envision, Onboard, and Drive Value - to help you plan, deliver, and operate a successful Phone System with Calling Plans implementation.</span></span>

> [!TIP]
> <span data-ttu-id="12240-120">Sie erhalten hier Beispielergebnisse für die einzelnen Aktivitäten und die wichtigsten Diskussionspunkte.</span><span class="sxs-lookup"><span data-stu-id="12240-120">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="12240-121">Die Beispiele in diesem Dokument, die Sie als wiederverwendbare Vorlagen nutzen können, finden Sie in den mit „Tipp“ beschrifteten Kästen.</span><span class="sxs-lookup"><span data-stu-id="12240-121">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="12240-122">Der Hinweis „TBA“ (To Be Added, wird ergänzt) zeigt an, dass Sie hier Informationen als Teil Ihres Planungsprozesses eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="12240-122">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>