---
title: Direktes Beantworten von Anrufen aus der automatischen Telefonzentrale und der Anrufwarteschleife aus Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Beschreibt Cloud-Telefonzentralen und Aufrufen von Warteschlangen, und erläutert, wie Sie diese Aufrufe in Teams beantworten können.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a94f8220cca2058e993f73241e62ff3ad0ea4f2
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914544"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="43711-103">Direktes Beantworten von Anrufen aus der automatischen Telefonzentrale und der Anrufwarteschleife aus Teams</span><span class="sxs-lookup"><span data-stu-id="43711-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="43711-104">Teams Benutzer können empfangen und Anrufe von Cloud-Telefonzentralen und Warteschlangen direkt von ihrem Client Teams Anruf beantworten.</span><span class="sxs-lookup"><span data-stu-id="43711-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="43711-105">Für Benutzer von Teams die automatische Telefonzentrale-Funktion ist jetzt erhältlich, und die Anruf-Warteschlange-Funktion ist in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="43711-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="43711-106">Was sind automatische um-Telefonzentralen und Warteschlangen aufrufen?</span><span class="sxs-lookup"><span data-stu-id="43711-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="43711-107">Cloud-Telefonzentralen bieten eine Reihe von Ansagen oder einer Audiodatei, die anstelle einer human Operator Anrufer hören, wenn sie zu einer Organisation anrufen.</span><span class="sxs-lookup"><span data-stu-id="43711-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="43711-108">Bei einer automatischen Telefonzentrale können die Anrufer durch das Menüsystem navigieren, Anrufe einleiten oder Benutzer suchen, indem sie eine Wähltastatur eines Telefons (MFV) oder Spracheingaben mit Spracherkennung verwenden.</span><span class="sxs-lookup"><span data-stu-id="43711-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="43711-109">Cloud Anruf Warteschlangen enthalten Ansage, die verwendet werden, wenn jemand anruft eine angegebene Rufnummer für Ihre Organisation die Möglichkeit, die Anrufe automatisch gehalten wird und die Möglichkeit, suchen Sie für den nächsten verfügbaren Anruf-Agent den Anruf beim Menschen Anruf behandeln Anhören von Musik in der Warteschleife.</span><span class="sxs-lookup"><span data-stu-id="43711-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="43711-110">Sie können einzelne oder mehrere Anruf Warteschlangen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="43711-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="43711-111">Behandeln von einem Anruf automatische Telefonzentrale oder ein Anruf Warteschlange</span><span class="sxs-lookup"><span data-stu-id="43711-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="43711-112">Benutzer können eingehende Anrufe von einer automatischen Telefonzentrale oder ein Anruf Warteschlange unterscheiden, bevor sie den Anruf annehmen.</span><span class="sxs-lookup"><span data-stu-id="43711-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="43711-113">Jeden Anruf wird zusammen mit den Namen und/oder die Nummer des Anrufers Informationen, die der Anrufer versucht hat, zu erreichen, den Benutzern ermöglicht, eines besseren Kontexts zum Umgang mit des Anrufers enthalten.</span><span class="sxs-lookup"><span data-stu-id="43711-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="43711-114">Die folgende Abbildung zeigt, wie ein Anruf von eine automatische Telefonzentrale oder ein Anruf Warteschlange, die einem Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="43711-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Benachrichtigung über eingehende Anrufe](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="43711-116">Nachdem ein automatische Telefonzentrale oder ein Anruf-Warteschlange Anruf entgegengenommen wurde, kann der Benutzer den Anruf wie alle anderen Anruf & #x 2014 verarbeiten; Sie können hinzufügen oder einer Konferenz in einem anderen Benutzer oder den Anruf an eine andere Person weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="43711-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="43711-117">Darüber hinaus werden basierend auf der Konfiguration des Benutzers Auto attendant Anrufe weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="43711-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="43711-118">Anruf Warteschlange Anrufe werden nicht weitergeleitet, je nach Konfiguration des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="43711-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="43711-119">Dadurch wird sichergestellt, Anrufer verbleiben in der Warteschlange, bis ein Agent den Anruf entgegennehmen kann, und der Aufrufer ist nicht unerwartet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="43711-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="43711-120">Unterstützte clients</span><span class="sxs-lookup"><span data-stu-id="43711-120">Supported clients</span></span>

<span data-ttu-id="43711-121">Unterstützung für die automatische Telefonzentrale und Anruf Warteschlange Anrufe ist in die folgenden Clients verfügbar:</span><span class="sxs-lookup"><span data-stu-id="43711-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="43711-122">Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="43711-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="43711-123">Microsoft Teams Mac-Client</span><span class="sxs-lookup"><span data-stu-id="43711-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="43711-124">Microsoft-Teams, iPhone-app</span><span class="sxs-lookup"><span data-stu-id="43711-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="43711-125">Microsoft-Teams, Android-app</span><span class="sxs-lookup"><span data-stu-id="43711-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="43711-126">Konfigurieren der Auto Attendant, und rufen Warteschlange-Unterstützung für Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="43711-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="43711-127">Um-Telefonzentrale erhalten, und rufen Sie Warteschlange Anrufe für Microsoft-Teams, müssen Sie Ihre Interoperabilität Richtlinie konfigurieren und Aktualisieren der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="43711-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="43711-128">Überprüfen Sie die [Migration und Interoperabilität für Organisationen mit Teams zusammen mit Skype für Unternehmen](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="43711-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="43711-129">Wenn Sie keinen automatischen Telefonzentrale und/oder Anruf Warteschlange konfiguriert und dazu möchten, finden Sie unter [Einrichten einer Cloud-Telefonzentrale](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) und [Erstellen einer Cloud-Anruf-Warteschlange](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span><span class="sxs-lookup"><span data-stu-id="43711-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) and [Create a Cloud call queue](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

## <a name="related-topics"></a><span data-ttu-id="43711-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="43711-130">Related topics</span></span>

-   [<span data-ttu-id="43711-131">Was ist Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="43711-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="43711-132">Erstellen einer Cloud-Anruf-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="43711-132">Create a Cloud call queue</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [<span data-ttu-id="43711-133">Was sind automatische Telefonzentralen Cloud?</span><span class="sxs-lookup"><span data-stu-id="43711-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="43711-134">Richten Sie eine Cloud-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="43711-134">Set up a Cloud auto attendant</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

