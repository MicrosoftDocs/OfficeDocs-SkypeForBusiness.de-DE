---
title: Anzeigen, Ändern und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie einem Benutzer in Skype for Business eine Konferenz-ID zuweisen und wie die Parameter der Konferenz-ID lauten sollten. '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252308"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="a08d8-103">Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="a08d8-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="a08d8-104">Informationen zu Benutzerkonferenz-IDs in Microsoft-Teams finden Sie unter [Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Microsoft Teams  zugewiesen wurde](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a08d8-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="a08d8-105">Eine Konferenz-ID wird einem Skype for Business-Benutzer automatisch zugewiesen, wenn er in Office 365 für Audiokonferenzen eingerichtet ist und Microsoft als Audiokonferenzanbieter verwendet.</span><span class="sxs-lookup"><span data-stu-id="a08d8-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="a08d8-106">Die zugewiesene Konferenz-ID wird in der Besprechungseinladung gesendet, wenn die Besprechung geplant wird.</span><span class="sxs-lookup"><span data-stu-id="a08d8-106">The conference ID assigned can be either a static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="a08d8-107">Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a08d8-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="a08d8-108">Obwohl eine Konferenz-ID automatisch erstellt und einem Benutzer zugewiesen wird, kann es jedoch geschehen, dass ein Benutzer diese nicht verwenden und sie durch eine bestimmte Zahl ersetzen möchte, oder Ihr Benutzer kann sich seine Konferenz-ID nicht merken oder hat sie verloren.</span><span class="sxs-lookup"><span data-stu-id="a08d8-108">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="a08d8-109">Sie können das **Skype for Business Administrationscenter**  und Windows PowerShell verwenden, um die Konferenz-ID für solche Benutzer anzuzeigen, zu ändern oder zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="a08d8-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="a08d8-110">Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält.</span><span class="sxs-lookup"><span data-stu-id="a08d8-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="a08d8-111">Weitere Informationen zum Zurücksetzen einer Konferenz-Organisator-PIN, [finden Sie hier](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="a08d8-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="a08d8-112">Anzeigen und Zurücksetzen der Konferenz-IDs</span><span class="sxs-lookup"><span data-stu-id="a08d8-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="a08d8-113">Um die Konferenz-ID anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="a08d8-113">To reset the meeting conference ID</span></span>

<span data-ttu-id="a08d8-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admincenters**</span><span class="sxs-lookup"><span data-stu-id="a08d8-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="a08d8-115">Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="a08d8-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="a08d8-116">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="a08d8-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="a08d8-117">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a08d8-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="a08d8-118">Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer aus, der die Konferenz-ID benötigt.</span><span class="sxs-lookup"><span data-stu-id="a08d8-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="a08d8-119">Sehen Sie auf der Aktions-Seie unter **Konferenz-ID**.</span><span class="sxs-lookup"><span data-stu-id="a08d8-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a08d8-120">Sie können alle Konferenzinformationen in einer E-Mail mit der Konferenz-ID und den Audio-Telefonnummern an den Benutzer senden, indem Sie nach Auswahl des Benutzers auf den Link **  Konferenzinformationen per E-Mail senden** klicken, nachdem Sie den Benutzer auf der Seite ** Benutzer** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a08d8-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>

<span data-ttu-id="a08d8-121">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a08d8-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a08d8-122">Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a08d8-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="a08d8-123">Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a08d8-123">To do so:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="a08d8-124">Um die Konferenz-ID zurückzusetzen</span><span class="sxs-lookup"><span data-stu-id="a08d8-124">To reset the meeting conference ID</span></span>

<span data-ttu-id="a08d8-125">Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="a08d8-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="a08d8-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admincenters**</span><span class="sxs-lookup"><span data-stu-id="a08d8-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="a08d8-127">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="a08d8-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="a08d8-128">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a08d8-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="a08d8-129">Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, klicken Sie im Aktionsbereich unter **Konferenz-ID**auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="a08d8-129">In the **Skype for Business admin center**> **Dial-in conferencing**, in the Action page under **Conference ID** click **Reset**.</span></span>

4. <span data-ttu-id="a08d8-130">Im Fenster **Konferenz-ID zurücksetzen?** klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a08d8-130">In the ** Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="a08d8-131">Eine Konferenz-ID wird automatisch erstellt und eine E-Mail mit der neuen Konferenz-ID wird an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="a08d8-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="a08d8-132">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a08d8-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a08d8-133">Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="a08d8-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="a08d8-134">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a08d8-134">To do this, run the following command:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="a08d8-135">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="a08d8-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="a08d8-136">Nachdem eine neue Konferenz-ID erstellt oder eine zurückgesetzt wurde, kann die alte Konferenz-ID von den Anrufern nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a08d8-136">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a08d8-137">Informieren Sie Benutzer von Plänen deren vorhandene Besprechungs-Einladungen neu zu planen, um sicher zu stellen, dass die neue Konferenz-ID den Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a08d8-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="a08d8-138">Die Benutzer können das Skype for Business Meeting-Migrationstool für ihre vorhandenen Meetings aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a08d8-138">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="a08d8-139">Informationen zum Herunterladen, Installieren und Ausführen des Skype for Business Meeting-Updatetools finden Sie unter: [Meeting-Updatetool für Skype for Business und Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting-Migrationstool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), und  [Skype for Business Online, Meeting-Migrationstool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="a08d8-139">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

- <span data-ttu-id="a08d8-140">Sehen Sie [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) um mehr über cmdlet zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="a08d8-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="a08d8-141">Die Konferenz-ID muss die in der Audiokonferenz-Brücke festgelegte Länge an Ziffern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a08d8-141">The conference ID must meet the length in digits set on the dial-in conferencing bridge.</span></span> <span data-ttu-id="a08d8-142">Konferenz-IDs dürfen keine Buchstaben und Sonderzeichen, sondern nur Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a08d8-142">You can't use Alphabetic and special characters in conference IDs only numbers can be used.</span></span>

- <span data-ttu-id="a08d8-143">Die Länge der Konferenz-ID für Benutzer von Audiokonferenzen ist standardmäßig auf 7 Ziffern festgelegt. Die Zahl der Stellen kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a08d8-143">The conference ID for all of your dial-in conferencing users will be 7 digits by default. And the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a08d8-144">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="a08d8-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a08d8-p109">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a08d8-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="a08d8-148">Eine Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a08d8-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="a08d8-149">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="a08d8-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="a08d8-p110">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a08d8-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="a08d8-152">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a08d8-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="a08d8-153">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a08d8-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="a08d8-154">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a08d8-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="a08d8-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a08d8-155">Related topics</span></span>

[<span data-ttu-id="a08d8-156">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="a08d8-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

