---
title: Aktivieren oder Deaktivieren von Eingabe-und Beendigungs Ankündigungen für Besprechungen in Teams
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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Der Administrator kann erfahren, wie Sie in einer Microsoft Teams-Besprechung ein-und Ausstiegs Ankündigungen aktivieren oder deaktivieren.
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372204"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="b7287-103">Aktivieren oder Deaktivieren von Ankündigungen bei Zu- oder Abgang für Besprechungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7287-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="b7287-104">Wenn Sie Audio-Conferencing in Microsoft 365 oder Office 365 einrichten, erhalten Sie eine Audiokonferenz-Brücke.</span><span class="sxs-lookup"><span data-stu-id="b7287-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="b7287-105">Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, die Teilnehmer zum Einwählen in eine Microsoft Teams-Besprechung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7287-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="b7287-106">Die Konferenzbrücke nimmt einen Anruf eines Benutzers an, der sich über ein Telefon in eine Besprechung einwählt.</span><span class="sxs-lookup"><span data-stu-id="b7287-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="b7287-107">Die Konferenzbrücke antwortet dem Anrufer mit Sprachansagen einer automatischen Telefonzentrale und kann dann, abhängig von Ihren Einstellungen, Benachrichtigungen abspielen, Anrufer auffordern, ihren Namen aufzuzeichnen und die PIN-Sicherheit einrichten.</span><span class="sxs-lookup"><span data-stu-id="b7287-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="b7287-108">Microsoft Teams-Besprechungsorganisatoren erhalten eine PIN, mit der sie eine Besprechung starten können, falls dies über die Microsoft Teams-App nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="b7287-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="b7287-109">Sie können jedoch festlegen, dass zum Starten einer Besprechung keine PIN erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b7287-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="b7287-110">Festlegen von Optionen für die Besprechungsteilnahme</span><span class="sxs-lookup"><span data-stu-id="b7287-110">Setting meeting join options</span></span>

<span data-ttu-id="b7287-111">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="b7287-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="b7287-112">Sie müssen ein Team Dienstadministrator sein, um diese Änderungen vornehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="b7287-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="b7287-113">Informationen zum Abrufen von Administratorrollen und-Berechtigungen finden Sie unter [Verwenden von Teams-Administratorrollen zum Verwalten von Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) .</span><span class="sxs-lookup"><span data-stu-id="b7287-113">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="b7287-114">Melden Sie sich beim Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="b7287-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="b7287-115">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="b7287-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="b7287-116">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="b7287-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="b7287-117">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).</span><span class="sxs-lookup"><span data-stu-id="b7287-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="b7287-118">Diese Option ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="b7287-118">This is selected by default.</span></span> <span data-ttu-id="b7287-119">Wenn Sie sie deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="b7287-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="b7287-120">Unter **Einstieg/Ausstieg-Ansagetyp** wählen Sie **Namen oder Telefonnummern** oder **Töne**.</span><span class="sxs-lookup"><span data-stu-id="b7287-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b7287-121">Standardmäßig können externe Teilnehmer die Telefonnummern von Einwahl Teilnehmern nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="b7287-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="b7287-122">Wenn Sie die Vertraulichkeit dieser Telefonnummern wahren wollen, wählen Sie **Töne** für **Typ der Ankündigungen von Ein-/Ausgängen** aus (dies verhindert, dass die Nummern von Teams ausgelesen werden).</span><span class="sxs-lookup"><span data-stu-id="b7287-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="b7287-123">Wenn Sie **Namen oder Telefonnummern** ausgewählt haben, aktivieren oder deaktivieren Sie **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**.</span><span class="sxs-lookup"><span data-stu-id="b7287-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="b7287-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b7287-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b7287-125">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="b7287-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="b7287-126">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b7287-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b7287-127">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b7287-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b7287-128">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b7287-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="b7287-129">Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7287-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="b7287-130">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7287-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="b7287-131">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b7287-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b7287-132">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b7287-132">Related topics</span></span>

[<span data-ttu-id="b7287-133">Allgemeine Fragen zu Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="b7287-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
