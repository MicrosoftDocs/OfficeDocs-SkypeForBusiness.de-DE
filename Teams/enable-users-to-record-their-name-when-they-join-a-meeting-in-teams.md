---
title: Zulassen, dass Benutzer ihren Namen für eine Besprechung aufzeichnen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Hier erfahren Sie, wie Sie die Möglichkeit zum Aufzeichnen des Benutzernamens beim Teilnehmen an einer Besprechung in Microsoft Teams aktivieren oder deaktivieren.
ms.openlocfilehash: d7cab4fca4ad3e7732704da9837522d51314061d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691581"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="0891a-103">Aktivieren der Aufzeichnung des Benutzernamens beim Teilnehmen an einer Besprechung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0891a-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="0891a-p101">Wenn Sie Audio-Conferencing in Microsoft 365 oder Office 365 einrichten, erhalten Sie Telefonnummern und eine sogenannte Audiokonferenz-Brücke. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, die eine dedizierte oder freigegebene Telefonnummer sein können.</span><span class="sxs-lookup"><span data-stu-id="0891a-p101">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="0891a-p102">Die Konferenzbrücke nimmt den Anruf eines Benutzers an, der sich mit einem Telefon in eine Besprechung einwählt. Die Konferenzbrücke nimmt den Anruf an und gibt Sprachansagen einer automatischen Telefonzentrale aus. Je nach den festgelegten Einstellungen gibt sie Benachrichtigungen wieder und fordert Anrufer auf, ihren Namen aufzuzeichnen. Zudem richtet sie die PIN-Sicherheit für die Organisatoren der Besprechung ein. Der Organisator der Besprechung erhält PINs, damit er eine Besprechung starten kann. Sie können in Ihren Einstellungen jedoch festlegen, dass zum Start einer Besprechung keine PIN erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0891a-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="0891a-110">Festlegen, ob Anrufer ihren Namen aufzeichnen sollen</span><span class="sxs-lookup"><span data-stu-id="0891a-110">Set whether callers should record their name</span></span>

<span data-ttu-id="0891a-111">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="0891a-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0891a-112">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="0891a-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0891a-113">Klicken Sie oben auf der Seite **Konferenz Brücken** auf **Brücken Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="0891a-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="0891a-114">Aktivieren oder Deaktivieren von **Benachrichtigungen zur Besprechungs Eingabe und-Beendigung**</span><span class="sxs-lookup"><span data-stu-id="0891a-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="0891a-115">Wenn Sie Benachrichtigungen aktivieren, wählen Sie unter **Entry/Exit-Ankündigungs** **Namen oder Telefonnummern** aus, und aktivieren Sie dann die Option **Anrufer bitten, Ihren Namen aufzuzeichnen, bevor Sie an einer Besprechung teilnehmen.**</span><span class="sxs-lookup"><span data-stu-id="0891a-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="0891a-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0891a-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0891a-117">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="0891a-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0891a-118">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0891a-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0891a-119">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0891a-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="0891a-120">Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0891a-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0891a-121">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="0891a-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0891a-122">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0891a-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0891a-123">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0891a-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0891a-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0891a-124">Related topics</span></span>

[<span data-ttu-id="0891a-125">Testen oder kaufen von Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="0891a-125">Try or purchase Audio Conferencing</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
