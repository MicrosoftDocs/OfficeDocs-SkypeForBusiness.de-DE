---
title: Finden Sie unter ändern und eine Konferenz-ID, die einem Benutzer in Skype für Business Online zugewiesenen zurücksetzen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, wie eine Konferenz-ID eines Benutzers in Skype für Business Online zugewiesen und was die Konferenz-IDs-Parameter werden soll. '
ms.openlocfilehash: eb7d42fa88c54b917e89eb97ce9f52bd03af4935
ms.sourcegitcommit: 3d3a296f225ecbbee0b4cea67664ad7ab31ed1c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "30535959"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="86722-103">Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="86722-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="86722-104">Informationen zu Benutzerkonferenz-IDs in Microsoft-Teams finden Sie unter [Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Microsoft Teams  zugewiesen wurde](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="86722-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="86722-105">Eine Konferenz-ID wird einem Skype for Business-Benutzer automatisch zugewiesen, wenn er in Office 365 für Audiokonferenzen eingerichtet ist und Microsoft als Audiokonferenzanbieter verwendet.</span><span class="sxs-lookup"><span data-stu-id="86722-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="86722-106">Die Konferenz-ID zugewiesen wird in der besprechungseinladung gesendet, wenn die Besprechung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="86722-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="86722-107">Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="86722-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="86722-108">Zwar eine Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten, und es eine bestimmte Anzahl festgelegt werden soll, oder wenn Ihre Benutzer können nicht merken oder ihre Konferenz-ID. verloren haben</span><span class="sxs-lookup"><span data-stu-id="86722-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="86722-109">Sie können das **Skype for Business Administrationscenter**  und Windows PowerShell verwenden, um die Konferenz-ID für solche Benutzer anzuzeigen, zu ändern oder zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="86722-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="86722-110">Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält.</span><span class="sxs-lookup"><span data-stu-id="86722-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="86722-111">Weitere Informationen zum Zurücksetzen einer Konferenz-Organisator-PIN, [finden Sie hier](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="86722-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="86722-112">Anzeigen und Zurücksetzen der Konferenz-IDs</span><span class="sxs-lookup"><span data-stu-id="86722-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="86722-113">So zeigen Sie die Konferenz-ID an.</span><span class="sxs-lookup"><span data-stu-id="86722-113">To view the conference ID</span></span>

<span data-ttu-id="86722-114">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="86722-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="86722-115">Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="86722-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="86722-116">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="86722-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="86722-117">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="86722-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="86722-118">Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer aus, der die Konferenz-ID benötigt.</span><span class="sxs-lookup"><span data-stu-id="86722-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="86722-119">Sehen Sie auf der Aktions-Seie unter **Konferenz-ID**.</span><span class="sxs-lookup"><span data-stu-id="86722-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="86722-120">Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und audio Telefonnummern durch Klicken auf den Link **Konferenz Informationen per e-Mail senden** , nachdem Sie den Benutzer auf der Seite **Benutzer** auswählen enthält.</span><span class="sxs-lookup"><span data-stu-id="86722-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="86722-121">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="86722-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="86722-122">Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="86722-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="86722-123">Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="86722-123">To do so, run:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="86722-124">So setzen Sie die Konferenz-ID zurück.</span><span class="sxs-lookup"><span data-stu-id="86722-124">To reset the conference ID</span></span>

<span data-ttu-id="86722-125">Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="86722-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="86722-126">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="86722-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="86722-127">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="86722-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="86722-128">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="86722-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="86722-129">In der **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, klicken Sie im Aktionsbereich unter **Konferenz-ID**, klicken Sie auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="86722-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="86722-130">In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="86722-130">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="86722-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="86722-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="86722-132">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="86722-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="86722-133">Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="86722-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="86722-134">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="86722-134">To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="86722-135">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="86722-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="86722-136">Nachdem eine neue Konferenz-ID erstellt wird oder eine zurückgesetzt wird, kann nicht die alte Konferenz-ID BSSID verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86722-136">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="86722-137">Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="86722-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="86722-138">Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="86722-138">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="86722-139">Informationen zum Herunterladen, installieren und Ausführen des Tools finden Sie unter: [Meeting Aktualisierungstool für Skype für Unternehmen und Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Besprechung Migrationstool (64-Bit)](https://go.microsoft.com/fwlink/?LinkID=626047)und [Skype für Online Business Besprechung Migration Tool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="86722-139">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="86722-140">Weitere Informationen zum Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="86722-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="86722-141">Die Konferenz-ID muss die Länge in Ziffern legen Sie für die audiokonferenzbrücke erfüllen.</span><span class="sxs-lookup"><span data-stu-id="86722-141">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="86722-142">Sie können nicht alphabetische oder Sonderzeichen im Konferenz-IDs verwenden. nur Zahlen können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86722-142">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="86722-143">Die Konferenz-ID für alle Ihre audiokonferenzbenutzer werden standardmäßig 7 Ziffern, und die Anzahl der Nachkommastellen kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="86722-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="86722-144">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="86722-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="86722-p109">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="86722-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="86722-148">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="86722-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="86722-149">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="86722-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="86722-p110">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="86722-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="86722-152">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="86722-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="86722-153">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="86722-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="86722-154">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="86722-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="86722-155">See Also</span><span class="sxs-lookup"><span data-stu-id="86722-155">Related topics</span></span>

[<span data-ttu-id="86722-156">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="86722-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

