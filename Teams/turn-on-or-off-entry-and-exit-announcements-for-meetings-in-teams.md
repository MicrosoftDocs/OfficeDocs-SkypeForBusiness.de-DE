---
title: Aktivieren oder Deaktivieren von Ankündigungen bei Zu- oder Abgang für Besprechungen in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Hier erfahren Sie, wie Sie Ankündigungen bei Zu- oder Abgang in einer Microsoft Teams-Besprechung aktivieren oder deaktivieren. '
ms.openlocfilehash: a646718d861737435244ee43c7206402f602f63c
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012457"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="ce741-103">Aktivieren oder Deaktivieren von Ankündigungen bei Zu- oder Abgang für Besprechungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce741-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="ce741-104">Beim Einrichten von Audiokonferenzen in Office 365 erhalten Sie eine Audiokonferenzbrücke.</span><span class="sxs-lookup"><span data-stu-id="ce741-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="ce741-105">Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, die Teilnehmer zum Einwählen in eine Microsoft Teams-Besprechung verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce741-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="ce741-106">Die Konferenzbrücke nimmt einen Anruf eines Benutzers an, der sich über ein Telefon in eine Besprechung einwählt.</span><span class="sxs-lookup"><span data-stu-id="ce741-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="ce741-107">Die Konferenzbrücke antwortet dem Anrufer mit Sprachansagen einer automatischen Telefonzentrale und kann dann, abhängig von Ihren Einstellungen, Benachrichtigungen abspielen, Anrufer auffordern, ihren Namen aufzuzeichnen und die PIN-Sicherheit einrichten.</span><span class="sxs-lookup"><span data-stu-id="ce741-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="ce741-108">Microsoft Teams-Besprechungsorganisatoren erhalten eine PIN, mit der sie eine Besprechung starten können, falls dies über die Microsoft Teams-App nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="ce741-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="ce741-109">Sie können jedoch festlegen, dass zum Starten einer Besprechung keine PIN erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ce741-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="ce741-110">Festlegen von Optionen für die Besprechungsteilnahme</span><span class="sxs-lookup"><span data-stu-id="ce741-110">Setting meeting join options</span></span>

1. <span data-ttu-id="ce741-111">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="ce741-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ce741-112">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="ce741-112">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="ce741-113">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).</span><span class="sxs-lookup"><span data-stu-id="ce741-113">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="ce741-114">Diese Option ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ce741-114">This is selected by default.</span></span> <span data-ttu-id="ce741-115">Wenn Sie sie deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="ce741-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="ce741-116">Wählen Sie unter **Entry/exit announcement type** (Typ der Ankündigung für Zu- und Abgänge) die Option **Namen oder Telefonnummern** oder **Tones** (Töne) aus.</span><span class="sxs-lookup"><span data-stu-id="ce741-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="ce741-117">Wenn Sie **Namen oder Telefonnummern** ausgewählt haben, aktivieren oder deaktivieren Sie **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**.</span><span class="sxs-lookup"><span data-stu-id="ce741-117">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="ce741-118">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ce741-118">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ce741-119">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="ce741-119">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ce741-p104">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ce741-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ce741-123">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="ce741-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ce741-124">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce741-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="ce741-125">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="ce741-125">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ce741-126">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ce741-126">Related topics</span></span>

[<span data-ttu-id="ce741-127">Allgemeine Fragen zu Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="ce741-127">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
