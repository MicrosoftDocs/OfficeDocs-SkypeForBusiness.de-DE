---
title: Festlegen des Telefons, die Zahlen enthalten auf invites in Microsoft-Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Rufen Sie die Schritte zum Erstellen einer Standardrufnummer für Anrufer teilnehmen an einer Besprechung Microsoft-Teams. '
ms.openlocfilehash: 20dfd4255cd41e9f5aebf419f77307b30fe40042
ms.sourcegitcommit: 75e0c9e186dc167bad01f5b17ec9de8a682ee007
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2018
ms.locfileid: "26005521"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="59da0-103">Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="59da0-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="59da0-104">Audiokonferenzen in Office 365 ermöglicht Benutzern in Ihrer Organisation zum Erstellen von Microsoft-Teams, Besprechungen, und klicken Sie dann zulassen, dass Benutzer in diesen treffen mit einem Telefon einwählen.</span><span class="sxs-lookup"><span data-stu-id="59da0-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="59da0-p101">Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="59da0-p101">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="59da0-107">Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="59da0-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="59da0-108">Anfänglicher Zuweisung von Telefonnummern, die in der Besprechung enthalten sind invites für neue Benutzer</span><span class="sxs-lookup"><span data-stu-id="59da0-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="59da0-109">Die Telefonnummern, die Bestandteil der Besprechung erhalten invites von Benutzern für Audiokonferenzen definieren, indem Sie die Standard-Konferenzen gebührenpflichtige Telefonnummer und den Standard-Konferenzen gebührenfreie Telefonnummer Zahl Einstellungen des Benutzers aktiviert.</span><span class="sxs-lookup"><span data-stu-id="59da0-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="59da0-110">Jede Einstellung gibt an, welche gebührenpflichtige oder gebührenfreie Telefonnummer in der besprechungseinladung eines bestimmten Benutzers eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="59da0-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="59da0-111">Wie bereits erwähnt, enthält jede Besprechung einladen, eine gebührenpflichtige Nummer, eine optionale gebührenfreie Telefonnummer und ein Link, der die vollständige Liste der alle Zugriffsnummer für Einwahl Telefonnummern wird geöffnet, die Teilnahme an einer bestimmten Besprechung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="59da0-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="59da0-112">Für einen neuen Benutzer werden die standardmäßigen Conferencing gebührenfreie Nummern zugewiesen je nach Land, das in der Office 365-Profil des Benutzers festgelegt wird, wenn der Benutzer für die Audiokonferenz-Dienst aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="59da0-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="59da0-113">Befindet sich eine gebührenpflichtige Telefonnummer in die Konferenzbrücke, die das Land des Benutzers entspricht, wird diese Nummer automatisch als die gebührenpflichtige Standardnummer des Benutzers zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="59da0-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="59da0-114">Wenn nicht vorhanden ist, wird die Zahl, die als die gebührenpflichtige Standardanzahl zulässiger die Konferenzbrücke definiert ist als die gebührenpflichtige Standardnummer des Benutzers zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="59da0-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="59da0-115">Nachdem der Benutzer für die Audiokonferenz-Dienst aktiviert ist, können die standardmäßige gebührenpflichtigen und gebührenfreien Telefonnummern des Benutzers vom mandantenadministrator aus die Anfangswerte jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="59da0-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="59da0-116">Festlegen oder Ändern von Audiokonferenzen Standardrufnummer ein Organisator der Besprechung oder eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="59da0-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="59da0-118">Verwenden des Microsoft-Teams und Skype for Business-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="59da0-118">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="59da0-119">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="59da0-119">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Zeigt die Auswahl von Benutzern in der Microsoft-Teams und Skype für Business Admin Center](media/teamsselectusers.png)

2. <span data-ttu-id="59da0-121">Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="59da0-121">At the top of the page, click **Edit**.</span></span>

    ![Klicken Sie auf Bearbeiten in der Microsoft-Teams und Skype für Business Admin Center](media/teamsedituser.png)

3. <span data-ttu-id="59da0-123">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="59da0-123">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Klicken Sie auf Bearbeiten neben Audiokonferenzen](media/teamseditaudioconf.png)

4. <span data-ttu-id="59da0-125">Verwenden Sie die Felder **gebührenpflichtige** oder **gebührenfreie Nummer** , die Zahlen für den Benutzer eingeben.</span><span class="sxs-lookup"><span data-stu-id="59da0-125">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="59da0-126">Wenn Sie einen Benutzer Audiokonferenzen Einstellungen ändern, müssen sich wiederholenden und zukünftige Microsoft-Teams, Besprechungen aktualisiert und an die Teilnehmer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="59da0-126">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="59da0-127">Wollen Sie Windows PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="59da0-127">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="59da0-p104">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="59da0-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="59da0-131">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="59da0-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="59da0-132">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59da0-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="59da0-133">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="59da0-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="59da0-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="59da0-134">Related topics</span></span>

[<span data-ttu-id="59da0-135">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="59da0-135">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
