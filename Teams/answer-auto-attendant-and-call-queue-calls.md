---
title: Annehmen einer automatischen Telefonzentrale und Anruf Warteschlangen Anrufe
ms.reviewer: waseemh
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Beschreibt automatische Cloud-Telefonzentralen und Anrufwarteschlangen und erläutert, wie Sie diese Anrufe in Teams annehmen können.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ea09e005dea2a89cb23b55a8ac59eaf491df460
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582822"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="fc914-103">Direktes Beantworten von Anrufen aus der automatischen Telefonzentrale und der Anrufwarteschleife aus Teams</span><span class="sxs-lookup"><span data-stu-id="fc914-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="fc914-104">Benutzer von Teams können Anrufe von automatischen Cloud-Telefonzentralen empfangen und annehmen sowie Warteschlangen direkt von Ihrem Team-Client aus anrufen.</span><span class="sxs-lookup"><span data-stu-id="fc914-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="fc914-105">Was sind automatische Telefonzentralen und Anrufwarteschlangen?</span><span class="sxs-lookup"><span data-stu-id="fc914-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="fc914-106">Automatische Cloud-Telefonzentralen bieten eine Reihe von Sprachansagen oder eine Audiodatei, die Anrufer hören, anstatt einen menschlichen Operator zu hören, wenn Sie sich in eine Organisation einwählen.</span><span class="sxs-lookup"><span data-stu-id="fc914-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="fc914-107">Bei einer automatischen Telefonzentrale können die Anrufer durch das Menüsystem navigieren, Anrufe einleiten oder Benutzer suchen, indem sie eine Wähltastatur eines Telefons (MFV) oder Spracheingaben mit Spracherkennung verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc914-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="fc914-p102">Cloudanrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Telefonisten zu suchen, um den Anruf zu entgegenzunehmen, während die Anrufe gehalten werden und die Anrufer dabei Musik hören. Sie können einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc914-p102">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="fc914-110">Behandeln einer automatischen Telefonzentrale oder eines Anruf Warteschlangen Anrufs</span><span class="sxs-lookup"><span data-stu-id="fc914-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="fc914-111">Benutzer können eingehende Anrufe von einer automatischen Telefonzentrale oder Anrufwarteschlange unterscheiden, bevor Sie den Anruf annehmen.</span><span class="sxs-lookup"><span data-stu-id="fc914-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="fc914-112">Zusammen mit dem Namen und/oder der Nummer des Anrufers enthält jeder Anrufinformationen darüber, wer der Anrufer zu erreichen versucht hat, sodass die Benutzer einen besseren Kontext für die Adressierung des Anrufers erhalten.</span><span class="sxs-lookup"><span data-stu-id="fc914-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="fc914-113">Die folgende Abbildung zeigt, wie ein eingehender Anruf von einer automatischen Telefonzentrale oder einer Anrufwarteschlange für einen Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fc914-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Screenshot einer Benachrichtigung über eingehende Anrufe](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="fc914-115">Sobald eine automatische Telefonzentrale oder ein Anruf Warteschlangen Anruf beantwortet wurde, kann der Benutzer den Anruf wie jeden anderen Anruf verarbeiten, &#x2014; er einem anderen Benutzer hinzufügen oder eine Konferenz durchführen oder den Anruf an eine andere Person übertragen kann.</span><span class="sxs-lookup"><span data-stu-id="fc914-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="fc914-116">Darüber hinaus werden Anrufe an die automatische Telefonzentrale basierend auf der Konfiguration des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fc914-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="fc914-117">Anruf Warteschlangen Anrufe werden nicht basierend auf der Konfiguration des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fc914-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="fc914-118">Dadurch wird sichergestellt, dass Anrufer in der Warteschlange verbleiben, bis ein Agent den Anruf annehmen kann und der Anrufer nicht unerwartet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="fc914-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="fc914-119">Unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="fc914-119">Supported clients</span></span>

<span data-ttu-id="fc914-120">Unterstützung für automatische Telefonzentrale und Anruf Warteschlangen Anrufe steht in den folgenden Clients zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="fc914-120">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="fc914-121">Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="fc914-121">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="fc914-122">Microsoft Teams Mac-Client</span><span class="sxs-lookup"><span data-stu-id="fc914-122">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="fc914-123">Microsoft Teams-iPhone-App</span><span class="sxs-lookup"><span data-stu-id="fc914-123">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="fc914-124">Microsoft Teams Android-App</span><span class="sxs-lookup"><span data-stu-id="fc914-124">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="fc914-125">Konfigurieren der automatischen Telefonzentrale und der Unterstützung der Anrufwarteschlange für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc914-125">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="fc914-126">Wenn Sie die automatische Telefonzentrale und die Anruf Warteschlangen Anrufe in Microsoft Teams empfangen möchten, müssen Sie Ihre Interoperabilitätsrichtlinie und die Upgrade-Richtlinie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fc914-126">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="fc914-127">Bitte überprüfen Sie [Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="fc914-127">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="fc914-128">Wenn Sie keine automatische Telefonzentrale und/oder keine Anrufwarteschlange konfiguriert haben und dies tun möchten, lesen Sie [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md) und [Erstellen einer Cloud-Anrufwarteschlange](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="fc914-128">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc914-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fc914-129">Related topics</span></span>

-    [<span data-ttu-id="fc914-130">Was ist das Telefon System in Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="fc914-130">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="fc914-131">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="fc914-131">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="fc914-132">Was sind automatische Cloudtelefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="fc914-132">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="fc914-133">Einrichten einer automatischen Cloudtelefonzentrale</span><span class="sxs-lookup"><span data-stu-id="fc914-133">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

