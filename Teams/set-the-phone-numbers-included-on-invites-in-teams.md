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
ms.openlocfilehash: 859bf6f4a99f95c67123385c99061b1546eaa60c
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296271"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="1e05f-103">Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="1e05f-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="1e05f-104">Mit Audiokonferenzen in Office 365 können Benutzer in Ihrer Organisation Microsoft Teams-Besprechungen erstellen und Benutzern die telefonische Einwahl in die Besprechung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1e05f-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="1e05f-105">In Office 365 haben Sie die Möglichkeit, eine Microsoft-Audiokonferenzbrücke oder eine Audiokonferenzbrücke von einem Drittanbieter zu verwenden, die von einem genehmigten Audiokonferenzanbieter (ACP) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1e05f-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="1e05f-p102">Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1e05f-p102">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e05f-108">Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="1e05f-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="1e05f-109">Festlegen oder Ändern der Standardtelefonnummer für Audiokonferenzen für einen Besprechungsorganisator oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="1e05f-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="1e05f-111">Verwenden des Microsoft-Teams und Skype for Business-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="1e05f-111">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="1e05f-112">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="1e05f-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Zeigt die Auswahl von Benutzern in der Microsoft-Teams und Skype für Business Admin Center](media/teamsselectusers.png)

2. <span data-ttu-id="1e05f-114">Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1e05f-114">At the top of the page, click **Edit**.</span></span>

    ![Klicken Sie auf Bearbeiten in der Microsoft-Teams und Skype für Business Admin Center](media/teamsedituser.png)

3. <span data-ttu-id="1e05f-116">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1e05f-116">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Klicken Sie auf Bearbeiten neben Audiokonferenzen](media/teamseditaudioconf.png)

4. <span data-ttu-id="1e05f-118">Verwenden Sie die Felder **gebührenpflichtige** oder **gebührenfreie Nummer** , die Zahlen für den Benutzer eingeben.</span><span class="sxs-lookup"><span data-stu-id="1e05f-118">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="1e05f-119">Wenn Sie einen Benutzer Audiokonferenzen Einstellungen ändern, müssen sich wiederholenden und zukünftige Microsoft-Teams, Besprechungen aktualisiert und an die Teilnehmer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e05f-119">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="1e05f-120">Wollen Sie Windows PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="1e05f-120">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="1e05f-p103">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1e05f-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1e05f-124">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="1e05f-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1e05f-125">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e05f-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="1e05f-126">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="1e05f-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="1e05f-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1e05f-127">Related topics</span></span>

[<span data-ttu-id="1e05f-128">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="1e05f-128">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
