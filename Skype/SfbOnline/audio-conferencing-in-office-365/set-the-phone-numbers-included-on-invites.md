---
title: Einrichten der in Einladungen enthaltenen Telefonnummern in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Führen Sie die Schritte zum Erstellen einer Standardtelefonnummer für Anrufer aus, um an einer Skype for Business Online-Besprechung teilzunehmen. '
ms.openlocfilehash: c6a8c9c3b3d21a64ad54d84ed8bfab22044f9cf5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680372"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="4f026-103">Einrichten der in Einladungen enthaltenen Telefonnummern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f026-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="4f026-104">Informationen zum Einladen von Telefonnummern für Besprechungen in Microsoft Teams finden Sie unter [Einrichten der Telefonnummern, die in Einladungen in Microsoft Teams enthalten sind](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span><span class="sxs-lookup"><span data-stu-id="4f026-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="4f026-105">Audiokonferenzen in Office 365 ermöglicht es Benutzern in Ihrer Organisation, Skype for Business-Besprechungen zu erstellen und Benutzern dann das Einwählen in diese Besprechungen mithilfe eines Telefons zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4f026-105">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="4f026-106">In Office 365 haben Sie die Möglichkeit, eine Microsoft-Audiokonferenz-Brücke oder eine Audio-Konferenzbrücke eines Drittanbieters zu verwenden, die von einem zugelassenen Audiokonferenz-Anbieter (ACP) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="4f026-106">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f026-107">Es gibt keine Ressource, die eine Liste aller Einwahlnummern für Audiokonferenzen enthält.</span><span class="sxs-lookup"><span data-stu-id="4f026-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="4f026-108">Wenn Sie feststellen möchten, ob Einwahlnummern in Ihrem Land/Ihrer Region verfügbar sind, verwenden Sie die **Skype for Business Admin Center** > **-sprach** > **Nummern**, klicken Sie auf **neue Service Nummern** **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="4f026-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="4f026-109">Verwenden Sie die Listen für **Land/Region**, **Bundesland/Region** und **Ort** , um Ihre Suche zu filtern. #a0 auch wenn Sie nach gebührenfreien Servicenummern suchen, wählen Sie **gebührenfrei** in der Liste **Bundesland/Region** .</span><span class="sxs-lookup"><span data-stu-id="4f026-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="4f026-p103">Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4f026-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f026-112">Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="4f026-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="4f026-113">Festlegen der standardmäßigen Einwahl Telefonnummer für einen Besprechungsorganisator</span><span class="sxs-lookup"><span data-stu-id="4f026-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="4f026-114">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f026-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="4f026-115">Wählen Sie **Admin Center** > **Skype for Business** aus.</span><span class="sxs-lookup"><span data-stu-id="4f026-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="4f026-116">Wählen Sie **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="4f026-116">Choose **Users**.</span></span>
    
    ![Zeigt das Auswählen von Benutzern im Skype for Business Admin Center](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="4f026-118">Wählen Sie die Benutzer aus, die Sie bearbeiten möchten:</span><span class="sxs-lookup"><span data-stu-id="4f026-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="4f026-119">Wenn Sie einen einzelnen Benutzer auswählen möchten, wählen Sie den Namen des Benutzers aus.</span><span class="sxs-lookup"><span data-stu-id="4f026-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="4f026-120">Um alle Benutzer auf der Seite auszuwählen, aktivieren Sie das Kontrollkästchen neben **Anzeigename** oben in der Liste.</span><span class="sxs-lookup"><span data-stu-id="4f026-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="4f026-121">Wenn Sie mehrere Benutzer auswählen möchten, aktivieren Sie das Kontrollkästchen neben dem Namen der einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4f026-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="4f026-122">Wählen Sie im rechten Bereich **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="4f026-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="4f026-124">Wählen Sie **Audiokonferenzen**aus.</span><span class="sxs-lookup"><span data-stu-id="4f026-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="4f026-125">Wählen Sie auf der Seite **Eigenschaften** in der Liste **Anbietername** den Anbieter für den Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4f026-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="4f026-126">Füllen Sie je nach Anbieter die folgenden Felder aus.</span><span class="sxs-lookup"><span data-stu-id="4f026-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="4f026-127">**Microsoft ist der Anbieter**: Verwenden Sie die standardmäßige **gebührenpflichtige Nummer** und die Standard **mäßige gebührenfreie** Nummernliste, um die Standardnummern für den Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4f026-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="4f026-128">Ihrer Konferenzbrücke muss mindestens eine gebührenfreie Nummer zugewiesen werden, bevor diese als gebührenfreie Standardnummer für einen Benutzer konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4f026-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="4f026-129">Informationen zum Abrufen einer gebührenfreien Nummer finden Sie unter [Abrufen von Service-Telefonnummern für Skype for Business](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="4f026-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="4f026-130">**Eine Drittpartei ist der Anbieter**: Verwenden Sie die Felder **gebührenpflichtige Nummer** und **gebührenfreie Nummer** , um die Nummern für den Benutzer einzugeben.</span><span class="sxs-lookup"><span data-stu-id="4f026-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="4f026-131">Zurücksetzen von Audiokonferenz-Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="4f026-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="4f026-132">Wählen Sie im **Skype for Business Admin Center**die Option **Audio conferencing** (Audiokonferenz) aus.</span><span class="sxs-lookup"><span data-stu-id="4f026-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="4f026-133">Wählen Sie oben auf der Seite die Option **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="4f026-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="4f026-134">Wählen Sie die Benutzer aus, die Sie zurücksetzen möchten, und klicken Sie dann im Bereich "Aktion" auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="4f026-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="4f026-135">Wenn Sie die Konferenzeinstellungen eines Benutzers ändern, wird standardmäßig eine e-Mail-Nachricht an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="4f026-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="4f026-136">Wie Sie diese Einstellung ändern können, erfahren Sie unter [Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="4f026-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4f026-137">Wenn Sie die Einstellungen für die Audiokonferenz eines Benutzers ändern, müssen wiederkehrende und zukünftige Skype for Business-Besprechungen aktualisiert und an die Teilnehmer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4f026-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4f026-138">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="4f026-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4f026-139">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) nutzen.</span><span class="sxs-lookup"><span data-stu-id="4f026-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="4f026-140">Mit dem Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) können Sie die gebührenpflichtige oder gebührenfreie Standardnummer für spezifische Benutzer ändern.</span><span class="sxs-lookup"><span data-stu-id="4f026-140">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="4f026-141">Führen Sie Folgendes aus, um die gebührenfreie Standardnummer für einen Benutzer zu ändern:</span><span class="sxs-lookup"><span data-stu-id="4f026-141">To change the default toll-free number for a user, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="4f026-142">Ändern Sie mit dem Cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** die gebührenpflichtige oder gebührenfreie Nummer für Benutzer auf Basis ihrer ursprünglichen Standardnummer oder ihres Standorts.</span><span class="sxs-lookup"><span data-stu-id="4f026-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f026-143">Verwenden Sie das Cmdlet **Get-CsOnlineDialInConferencingBridge** , um die Brücke zu finden.</span><span class="sxs-lookup"><span data-stu-id="4f026-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="4f026-144">Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer für alle Benutzer bis auf einen auf +18005551234 festzulegen:</span><span class="sxs-lookup"><span data-stu-id="4f026-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="4f026-145">Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer aller Benutzer, deren standardmäßige gebührenfreie Telefonnummer +18005551234 lautet, in +18005551239 zu ändern:</span><span class="sxs-lookup"><span data-stu-id="4f026-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="4f026-146">Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer aller Benutzer in den USA auf +18005551234 festzulegen:</span><span class="sxs-lookup"><span data-stu-id="4f026-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="4f026-147">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="4f026-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="4f026-p107">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4f026-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4f026-151">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f026-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4f026-152">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="4f026-152">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4f026-153">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4f026-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4f026-154">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4f026-154">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4f026-155">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f026-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4f026-156">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f026-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4f026-157">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f026-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="4f026-158">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4f026-158">Related topics</span></span>

[<span data-ttu-id="4f026-159">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="4f026-159">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
