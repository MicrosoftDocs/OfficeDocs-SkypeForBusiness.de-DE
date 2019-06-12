---
title: Direktes Beantworten von Anrufen aus der automatischen Telefonzentrale und der Anrufwarteschleife aus Teams
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Beschreibt automatische Cloud-Telefonzentralen und Anrufwarteschlangen und erläutert, wie Sie diese Anrufe in Teams annehmen können.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 855029001863b6603548c865d5f7bfb039261a18
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494832"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="21cc6-103">Direktes Beantworten von Anrufen aus der automatischen Telefonzentrale und der Anrufwarteschleife aus Teams</span><span class="sxs-lookup"><span data-stu-id="21cc6-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="21cc6-104">Benutzer von Teams können Anrufe von automatischen Cloud-Telefonzentralen empfangen und annehmen sowie Warteschlangen direkt von Ihrem Team-Client aus anrufen.</span><span class="sxs-lookup"><span data-stu-id="21cc6-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="21cc6-105">Für Benutzer von Teams ist das Feature für die automatische Telefonzentrale jetzt in der Regel verfügbar, und die Anruf Warteschlangenfunktion befindet sich in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="21cc6-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="21cc6-106">Was sind automatische Telefonzentralen und Anrufwarteschlangen?</span><span class="sxs-lookup"><span data-stu-id="21cc6-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="21cc6-107">Automatische Cloud-Telefonzentralen bieten eine Reihe von Sprachansagen oder eine Audiodatei, die Anrufer hören, anstatt einen menschlichen Operator zu hören, wenn Sie sich in eine Organisation einwählen.</span><span class="sxs-lookup"><span data-stu-id="21cc6-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="21cc6-108">Bei einer automatischen Telefonzentrale können die Anrufer durch das Menüsystem navigieren, Anrufe einleiten oder Benutzer suchen, indem sie eine Wähltastatur eines Telefons (MFV) oder Spracheingaben mit Spracherkennung verwenden.</span><span class="sxs-lookup"><span data-stu-id="21cc6-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="21cc6-109">Zu den Cloud-Anrufwarteschlangen gehören Begrüßungen, die verwendet werden, wenn sich jemand an eine Telefonnummer für Ihre Organisation anmeldet, die Möglichkeit, die Anrufe automatisch zu halten, und die Möglichkeit, nach dem nächsten verfügbaren Anruf Agenten zu suchen, um den Anruf zu führen, während die Anrufteilnehmer Musik hören in Wartestellung.</span><span class="sxs-lookup"><span data-stu-id="21cc6-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="21cc6-110">Sie können eine oder mehrere Anrufwarteschlangen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="21cc6-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="21cc6-111">Behandeln einer automatischen Telefonzentrale oder eines Anruf Warteschlangen Anrufs</span><span class="sxs-lookup"><span data-stu-id="21cc6-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="21cc6-112">Benutzer können eingehende Anrufe von einer automatischen Telefonzentrale oder Anrufwarteschlange unterscheiden, bevor Sie den Anruf annehmen.</span><span class="sxs-lookup"><span data-stu-id="21cc6-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="21cc6-113">Zusammen mit dem Namen und/oder der Nummer des Anrufers enthält jeder Anrufinformationen darüber, wer der Anrufer zu erreichen versucht hat, sodass die Benutzer einen besseren Kontext für die Adressierung des Anrufers erhalten.</span><span class="sxs-lookup"><span data-stu-id="21cc6-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="21cc6-114">Die folgende Abbildung zeigt, wie ein eingehender Anruf von einer automatischen Telefonzentrale oder einer Anrufwarteschlange für einen Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="21cc6-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Screenshot einer Benachrichtigung über eingehende Anrufe](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="21cc6-116">Sobald eine automatische Telefonzentrale oder ein Anruf Warteschlangen Anruf beantwortet wurde, kann der Benutzer den Anruf wie jeden anderen Anruf verarbeiten, #a0 er einem anderen Benutzer hinzufügen oder eine Konferenz durchführen oder den Anruf an eine andere Person übertragen kann.</span><span class="sxs-lookup"><span data-stu-id="21cc6-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="21cc6-117">Darüber hinaus werden Anrufe an die automatische Telefonzentrale basierend auf der Konfiguration des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="21cc6-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="21cc6-118">Anruf Warteschlangen Anrufe werden nicht basierend auf der Konfiguration des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="21cc6-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="21cc6-119">Dadurch wird sichergestellt, dass Anrufer in der Warteschlange verbleiben, bis ein Agent den Anruf annehmen kann und der Anrufer nicht unerwartet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="21cc6-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="21cc6-120">Unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="21cc6-120">Supported clients</span></span>

<span data-ttu-id="21cc6-121">Unterstützung für automatische Telefonzentrale und Anruf Warteschlangen Anrufe steht in den folgenden Clients zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="21cc6-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="21cc6-122">Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="21cc6-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="21cc6-123">Microsoft Teams Mac-Client</span><span class="sxs-lookup"><span data-stu-id="21cc6-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="21cc6-124">Microsoft Teams-iPhone-App</span><span class="sxs-lookup"><span data-stu-id="21cc6-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="21cc6-125">Microsoft Teams Android-App</span><span class="sxs-lookup"><span data-stu-id="21cc6-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="21cc6-126">Konfigurieren der automatischen Telefonzentrale und der Unterstützung der Anrufwarteschlange für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="21cc6-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="21cc6-127">Wenn Sie die automatische Telefonzentrale und die Anruf Warteschlangen Anrufe in Microsoft Teams empfangen möchten, müssen Sie Ihre Interoperabilitätsrichtlinie und die Upgrade-Richtlinie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="21cc6-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="21cc6-128">Bitte überprüfen Sie [Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="21cc6-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="21cc6-129">Wenn Sie keine automatische Telefonzentrale und/oder keine Anrufwarteschlange konfiguriert haben und dies tun möchten, lesen Sie [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md) und [Erstellen einer Cloud-Anrufwarteschlange](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="21cc6-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="21cc6-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="21cc6-130">Related topics</span></span>

-   [<span data-ttu-id="21cc6-131">Was ist das Telefon System in Office 365?</span><span class="sxs-lookup"><span data-stu-id="21cc6-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="21cc6-132">Erstellen einer Cloudanrufwarteschleife</span><span class="sxs-lookup"><span data-stu-id="21cc6-132">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-   [<span data-ttu-id="21cc6-133">Was sind automatische Cloudtelefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="21cc6-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="21cc6-134">Einrichten einer automatischen Cloudtelefonzentrale</span><span class="sxs-lookup"><span data-stu-id="21cc6-134">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

