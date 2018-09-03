---
title: Automatische Telefonzentralen-Spracheinstellung für Audiokonferenzen in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
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
description: Wählen Sie die Audiokonferenz-Telefonzentralen-Sprache für eine Audiokonferenznummer in Skype for Business Online.
ms.openlocfilehash: fe0abceba1f01b148f1a81163525be0750ef4980
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779075"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="763d6-103">Automatische Telefonzentralen-Spracheinstellung für Audiokonferenzen in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="763d6-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="763d6-104">Informationen zum Festlegen der automatischen Telefonzentralensprache in Microsoft Teams finden Sie unter [Einrichten von automatischen Telefonzentralensprachen für Audiokonferenzen in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span><span class="sxs-lookup"><span data-stu-id="763d6-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="763d6-105">Die automatische Audiokonferenz-Telefonzentrale für Skype for Business kann Anrufer in verschiedenen Sprachen begrüßen, wenn sie an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="763d6-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="763d6-106">Wählen Sie eine primäre Sprache und bis zu vier sekundäre Sprachen.</span><span class="sxs-lookup"><span data-stu-id="763d6-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="763d6-107">Ihre primär festgelegte Sprache wird zuerst verwendet, die sekundären Sprachen werden in der Reihenfolge der Auswahl von der automatischen Telefonzentrale verwendet.</span><span class="sxs-lookup"><span data-stu-id="763d6-107">The primary language that you set will be used first and the secondary languages will be used in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="763d6-108">Sie können die Sprachen nur für inländische Einwahlnummern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="763d6-108">You can configure the languages on domestic dial-in access numbers only.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="763d6-109">Legen Sie die Sprachen für die automatische Telefonzentrale fest</span><span class="sxs-lookup"><span data-stu-id="763d6-109">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="763d6-110">Sie müssen ein [globaler Office 365-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) oder [Skype for Business-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) zum Ausführen dieses Schritts sein.</span><span class="sxs-lookup"><span data-stu-id="763d6-110">You must be an [Office 365 global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="763d6-111">Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz), und klicken Sie dann auf **Microsoft Bridge**.</span><span class="sxs-lookup"><span data-stu-id="763d6-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="763d6-112">Wählen Sie die Audiokonferenz-Telefonnummer aus der Liste aus, und klicken Sie im Aktionsbereich auf **Sprachen festlegen**.</span><span class="sxs-lookup"><span data-stu-id="763d6-112">Select the phone number from the list, and in the Action pane, click **Unassign**.</span></span> 
    
3. <span data-ttu-id="763d6-113">Klicken Sie auf der Seite **Sprachen festlegen** auf **Primäre Sprache**, um die vollständige Liste der verfügbaren Sprachen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="763d6-113">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="763d6-114">Wenn Sie möchten, klicken Sie auf die **Sekundären Sprachen**-Liste um sekundäre Sprache auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="763d6-114">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="763d6-115">Die primär und sekundär unterstützten Sprachen werden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="763d6-115">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="763d6-116">Die Reihenfolge, in der Sie sie in den Listen auswählen, entspricht der Reihenfolge der Sprachen, die den Anrufern angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="763d6-116">The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.</span></span> 
  
4. <span data-ttu-id="763d6-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="763d6-117">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="763d6-118">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="763d6-118">Want else should I know?</span></span>

- <span data-ttu-id="763d6-119">Unter [Unterstützte Sprachen für Audiokonferenzen](/MicrosoftTeams/audio-conferencing-supported-languages) finden Sie eine Liste der für Audiokonferenzen unterstützten Sprachen.</span><span class="sxs-lookup"><span data-stu-id="763d6-119">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="763d6-120">Sprachen können für dedizierte, aber nicht für freigegebene Telefonnummern festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="763d6-120">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="763d6-121">Eine Liste der Länder/Regionen in der Audiokonferenzen in Office 365 mit Microsoft als Anbieter verfügbar ist, finden Sie unter [Rufnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="763d6-121">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="763d6-122">Wollen Sie Windows PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="763d6-122">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="763d6-123">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie die Cmdlets [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) und[Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) nutzen.</span><span class="sxs-lookup"><span data-stu-id="763d6-123">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689)and [Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.</span></span>
  
<span data-ttu-id="763d6-124">Weitere Informationen finden Sie unter [Benutzung von Windows PowerShell für allgemeine Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)</span><span class="sxs-lookup"><span data-stu-id="763d6-124">To learn more, see [Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="763d6-125">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="763d6-125">Related topics</span></span>

[<span data-ttu-id="763d6-126">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="763d6-126">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
