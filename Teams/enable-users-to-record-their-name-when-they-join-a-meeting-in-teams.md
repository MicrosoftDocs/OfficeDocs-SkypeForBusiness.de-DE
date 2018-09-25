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
ms.openlocfilehash: 8583ca92de2544946eb898d128e423b6df62cb24
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012937"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="321eb-103">Aktivieren der Aufzeichnung des Benutzernamens beim Teilnehmen an einer Besprechung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321eb-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="321eb-p101">Bei der Konfiguration von Einwahlkonferenzen in Skype for Business Online erhalten Sie Telefonnummern sowie eine so genannte Einwahl- oder Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen, bei der bzw. denen sich um fest zugeordnete oder gemeinsam genutzte Telefonnummern handeln kann.</span><span class="sxs-lookup"><span data-stu-id="321eb-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="321eb-p102">Die Konferenzbrücke nimmt den Anruf eines Benutzers an, der sich mit einem Telefon in eine Besprechung einwählt. Die Konferenzbrücke nimmt den Anruf an und gibt Sprachansagen einer automatischen Telefonzentrale aus. Je nach den festgelegten Einstellungen gibt sie Benachrichtigungen wieder und fordert Anrufer auf, ihren Namen aufzuzeichnen. Zudem richtet sie die PIN-Sicherheit für die Organisatoren der Besprechung ein. Der Organisator der Besprechung erhält PINs, damit er eine Besprechung starten kann. Sie können in Ihren Einstellungen jedoch festlegen, dass zum Start einer Besprechung keine PIN erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="321eb-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="321eb-110">Festlegen, ob Anrufer ihren Namen aufzeichnen sollen</span><span class="sxs-lookup"><span data-stu-id="321eb-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="321eb-111">Wechseln Sie in der Microsoft-Teams & Skype für Business-Verwaltungskonsole im linken Navigationsbereich zu **Besprechungen** > **Konferenz Brücken**.</span><span class="sxs-lookup"><span data-stu-id="321eb-111">In the Microsoft Teams & Skype for Business Admin Center, in the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="321eb-112">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="321eb-112">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="321eb-113">Aktivieren oder deaktivieren Sie die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).</span><span class="sxs-lookup"><span data-stu-id="321eb-113">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="321eb-114">Wenn Sie Benachrichtigungen aktivieren, wählen Sie unter **Entry/exit announcement type** (Typ der Ankündigung für Zu- und Abgänge) die Option **Namen oder Telefonnummern** aus. Aktivieren Sie dann **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**.</span><span class="sxs-lookup"><span data-stu-id="321eb-114">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="321eb-115">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="321eb-115">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="321eb-116">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="321eb-116">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="321eb-p103">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="321eb-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="321eb-120">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="321eb-120">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="321eb-121">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="321eb-121">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="321eb-122">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="321eb-122">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="321eb-123">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="321eb-123">Related topics</span></span>

[<span data-ttu-id="321eb-124">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="321eb-124">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
