---
title: Legen Sie das Telefon, die Zahlen enthalten auf invites
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 8cc9b90d37e1a30c995547035fb2815aad89b7cf
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="c4ae5-103">Legen Sie das Telefon, die Zahlen enthalten auf invites</span><span class="sxs-lookup"><span data-stu-id="c4ae5-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="c4ae5-104">Audiokonferenzen in Office 365 ermöglicht Benutzern in Ihrer Organisation Skype für Geschäfts- und Microsoft-Teams, Besprechungen erstellen, und klicken Sie dann zulassen, dass Benutzer in diesen treffen mit einem Telefon einwählen.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business and Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="c4ae5-105">In Office 365 verfügen Sie über die Möglichkeit, eine audiokonferenzbrücke von Microsoft oder einem Drittanbieter-audiokonferenzbrücke, die von einem Provider genehmigte Audiokonferenzen (ACP) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c4ae5-106">Es ist keine Ressource, die eine Auflistung aller die Einwahlnummern für Audiokonferenzen enthält.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-106">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="c4ae5-107">Wenn Sie suchen, um festzustellen, ob in Ihrer Stadt oder Land/Region-Einwahl Telefonnummern vorhanden sind, verwenden Sie die **Skype für Business Administrationscenter** > **VoIP** > **Telefonnummern**, klicken Sie auf neue Dienst Nummern **dann **Hinzufügen** **.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-107">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="c4ae5-108">Verwenden Sie die Listen für **Land/Region**, Bundesland/Kanton **** und **Ort** Ihrer Suche. Filtern > auch, wenn Sie für gebührenfreie kostenlosen Service Zahlen suchen, wählen Sie **gebührenfreie Rufnummer** aus **Bundesland/Kanton** Liste.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-108">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="c4ae5-p103">Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c4ae5-111">Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-111">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="c4ae5-112">Konfiguration der Standard-Einwahlnummer für Besprechungsorganisatoren</span><span class="sxs-lookup"><span data-stu-id="c4ae5-112">Setting the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="c4ae5-113">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c4ae5-114">Wählen Sie **Admin Center** > **Skype for Business** aus.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-114">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c4ae5-115">Wählen Sie **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-115">Choose **Users**.</span></span>
    
    ![Zeigt die Auswahl von Benutzern in der Skype für Business Administrationscenter](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="c4ae5-117">Wählen Sie die Benutzer, den, die Sie bearbeiten möchten:</span><span class="sxs-lookup"><span data-stu-id="c4ae5-117">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="c4ae5-118">Um einen einzelnen Benutzer auszuwählen, wählen Sie den Namen des Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-118">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="c4ae5-119">Wenn alle Benutzer auf der Seite auswählen möchten, aktivieren Sie das neben **Anzeigename** am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-119">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="c4ae5-120">Um mehrere Benutzer auszuwählen, wählen Sie das Kontrollkästchen neben dem Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-120">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="c4ae5-121">Wählen Sie im rechten Bereich **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-121">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="c4ae5-123">Wählen Sie **Audiokonferenzen**.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-123">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="c4ae5-124">Wählen Sie auf der Seite **Eigenschaften** in der Liste **ProviderName** den Anbieter für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-124">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="c4ae5-125">Füllen Sie je nach dem Anbieter für die folgenden Felder aus.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-125">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="c4ae5-126">**Microsoft ist der Dienstanbieter**: Verwenden Sie die **Standardnummer gebührenpflichtige** und **gebührenfreie Standardnummer** enthält, um die Standard-Zahlen für den Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-126">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4ae5-127">Mindestens eine gebührenfreie Nummer muss Ihre Konferenzbrücke zugewiesen werden, bevor es als die standardmäßige gebührenfreie Telefonnummer eines Benutzers festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-127">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="c4ae5-128">Wenn Sie eine gebührenfreie Telefonnummer erhalten möchten, finden Sie unter [Getting Service Rufnummern für Skype für Unternehmen und die Microsoft-Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="c4ae5-128">To get a toll-free number, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="c4ae5-129">**Ein Drittanbieter ist der Dienstanbieter**: Verwenden Sie die Felder **die gebührenpflichtige Telefonnummer** und **gebührenfreie Nummer** die Zahlen für den Benutzer eingeben.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-129">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>
    
## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="c4ae5-130">Zurücksetzen von Audiokonferenz-Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="c4ae5-130">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="c4ae5-131">Wählen Sie im **Skype for Business Admin Center**die Option **Audio conferencing** (Audiokonferenz) aus.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-131">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="c4ae5-132">Wählen Sie oben auf der Seite die Option **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-132">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="c4ae5-133">Wählen Sie die Benutzer, den, die Sie zurücksetzen möchten, und klicken Sie dann im Bereich Aktion auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-133">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="c4ae5-134">Standardmäßig wird beim Ändern von Einstellungen für einen Benutzer, eine e-Mail an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-134">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="c4ae5-135">Um dies zu ändern, finden Sie unter [Aktivieren oder deaktivieren Sie e-Mails senden, wenn Audiokonferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="c4ae5-135">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c4ae5-136">Wenn Sie die Audiokonferenzeinstellungen eines Benutzers ändern, müssen Besprechungsserien und zukünftige Skype for Business- und Microsoft Teams-Besprechungen aktualisiert und an die Teilnehmer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-136">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c4ae5-137">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="c4ae5-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c4ae5-138">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) nutzen.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-138">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="c4ae5-139">Mit dem Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) können Sie die gebührenpflichtige oder gebührenfreie Standardnummer für spezifische Benutzer ändern.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-139">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="c4ae5-140">Führen Sie Folgendes aus, um die gebührenfreie Standardnummer für einen Benutzer zu ändern:</span><span class="sxs-lookup"><span data-stu-id="c4ae5-140">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="c4ae5-141">Ändern Sie mit dem Cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** die gebührenpflichtige oder gebührenfreie Nummer für Benutzer auf Basis ihrer ursprünglichen Standardnummer oder ihres Standorts.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-141">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4ae5-142">Die BridgeID finden Sie mithilfe von **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-142">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="c4ae5-143">Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer für alle Benutzer bis auf einen auf +18005551234 festzulegen:</span><span class="sxs-lookup"><span data-stu-id="c4ae5-143">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="c4ae5-144">Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer aller Benutzer, deren standardmäßige gebührenfreie Telefonnummer +18005551234 lautet, in +18005551239 zu ändern:</span><span class="sxs-lookup"><span data-stu-id="c4ae5-144">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="c4ae5-145">Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer aller Benutzer in den USA auf +18005551234 festzulegen:</span><span class="sxs-lookup"><span data-stu-id="c4ae5-145">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="c4ae5-146">Weitere Informationen zu Windows PowerShell finden möchten?</span><span class="sxs-lookup"><span data-stu-id="c4ae5-146">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="c4ae5-p107">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c4ae5-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c4ae5-150">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c4ae5-150">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c4ae5-151">Warum müssen Sie mithilfe von Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ae5-151">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c4ae5-p108">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c4ae5-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c4ae5-154">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ae5-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c4ae5-155">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c4ae5-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c4ae5-156">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c4ae5-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="c4ae5-157">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c4ae5-157">Related topics</span></span>

[<span data-ttu-id="c4ae5-158">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4ae5-158">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

