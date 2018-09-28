---
title: Aktivieren der Aufzeichnung des Benutzernamens beim Teilnehmen an einer Besprechung in Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Hier erfahren Sie, wie Sie die Möglichkeit zum Aufzeichnen des Benutzernamens beim Teilnehmen an einer Besprechung in Microsoft Teams aktivieren oder deaktivieren.
ms.openlocfilehash: bf58498ed6c00f69a32d2391d24a6c5bef1e1df7
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347530"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="3830a-103">Aktivieren der Aufzeichnung des Benutzernamens beim Teilnehmen an einer Besprechung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3830a-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="3830a-p101">Bei der Konfiguration von Einwahlkonferenzen in Skype for Business Online erhalten Sie Telefonnummern sowie eine so genannte Einwahl- oder Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen, bei der bzw. denen sich um fest zugeordnete oder gemeinsam genutzte Telefonnummern handeln kann.</span><span class="sxs-lookup"><span data-stu-id="3830a-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="3830a-p102">Die Konferenzbrücke nimmt den Anruf eines Benutzers an, der sich mit einem Telefon in eine Besprechung einwählt. Die Konferenzbrücke nimmt den Anruf an und gibt Sprachansagen einer automatischen Telefonzentrale aus. Je nach den festgelegten Einstellungen gibt sie Benachrichtigungen wieder und fordert Anrufer auf, ihren Namen aufzuzeichnen. Zudem richtet sie die PIN-Sicherheit für die Organisatoren der Besprechung ein. Der Organisator der Besprechung erhält PINs, damit er eine Besprechung starten kann. Sie können in Ihren Einstellungen jedoch festlegen, dass zum Start einer Besprechung keine PIN erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3830a-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="3830a-110">Festlegen, ob Anrufer ihren Namen aufzeichnen sollen</span><span class="sxs-lookup"><span data-stu-id="3830a-110">Set whether callers should record their name</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="3830a-112">Verwenden des Microsoft-Teams und Skype for Business-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="3830a-112">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="3830a-113">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="3830a-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="3830a-114">Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf.</span><span class="sxs-lookup"><span data-stu-id="3830a-114">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="3830a-115">Aktivieren oder Deaktivieren von **Besprechungseintrag und Benachrichtigungen zu beenden**.</span><span class="sxs-lookup"><span data-stu-id="3830a-115">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="3830a-116">Wenn Benachrichtigungen zu aktivieren, wählen Sie **Namen oder Telefonnummern** unter **Entry/Exit Ankündigung Typ**, und klicken Sie dann auf aktivieren **bitten Sie ihren Namen aufzeichnen müssen vor der Teilnahme an einer Besprechung Anrufer.**</span><span class="sxs-lookup"><span data-stu-id="3830a-116">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="3830a-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3830a-117">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3830a-118">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="3830a-118">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="3830a-p103">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3830a-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3830a-122">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="3830a-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="3830a-123">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3830a-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="3830a-124">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="3830a-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3830a-125">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3830a-125">Related topics</span></span>

[<span data-ttu-id="3830a-126">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="3830a-126">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
