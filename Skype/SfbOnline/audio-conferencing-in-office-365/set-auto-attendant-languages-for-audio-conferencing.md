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
description: Wählen Sie die Audiokonferenz-Telefonzentralen-Sprache für eine Audiokonferenznummer in Skype for Business Online.
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163901"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="95f6a-103">Automatische Telefonzentralen-Spracheinstellung für Audiokonferenzen in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95f6a-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="95f6a-104">Informationen zum Festlegen der automatischen Telefonzentralensprache in Microsoft Teams finden Sie unter [Einrichten von automatischen Telefonzentralensprachen für Audiokonferenzen in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span><span class="sxs-lookup"><span data-stu-id="95f6a-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="95f6a-105">Die automatische Audiokonferenz-Telefonzentrale für Skype for Business kann Anrufer in verschiedenen Sprachen begrüßen, wenn sie an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="95f6a-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="95f6a-p101">Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span><span class="sxs-lookup"><span data-stu-id="95f6a-p101">Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="95f6a-108">Sie können nur die Sprachen der Audiokonferenz-Nummern ändern, die der dedizierten Kategorie entsprechen.</span><span class="sxs-lookup"><span data-stu-id="95f6a-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="95f6a-109">Die Sprachen der freigegebenen Audiokonferenz-Nummer können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="95f6a-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="95f6a-110">Legen Sie die Sprachen für die automatische Telefonzentrale fest</span><span class="sxs-lookup"><span data-stu-id="95f6a-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="95f6a-111">Sie müssen ein [globaler Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) oder ein [Skype for Business-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) sein, um diesen Schritt ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="95f6a-111">You must be a [global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="95f6a-112">Wechseln Sie im **Skype for Business Admin Center**im linken Navigationsbereich zu **Legacy Portal**.</span><span class="sxs-lookup"><span data-stu-id="95f6a-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="95f6a-113">Wählen Sie im Legacy Portal **Audio Conferencing**aus, und klicken Sie dann auf **Microsoft Bridge**.</span><span class="sxs-lookup"><span data-stu-id="95f6a-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="95f6a-114">Wählen Sie die Telefonnummer für Audiokonferenzen in der Liste aus, und klicken Sie im Bereich "Aktion" auf **Sprachen festlegen**.</span><span class="sxs-lookup"><span data-stu-id="95f6a-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="95f6a-115">Es ist nur möglich, die Sprachen für dedizierte Audiokonferenz-Nummern zu ändern.</span><span class="sxs-lookup"><span data-stu-id="95f6a-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="95f6a-116">Klicken Sie auf der Seite **Sprachen festlegen** auf **Primäre Sprache**, um die vollständige Liste der verfügbaren Sprachen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="95f6a-116">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="95f6a-117">Wenn Sie möchten, klicken Sie auf die **Sekundären Sprachen**-Liste um sekundäre Sprache auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="95f6a-117">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="95f6a-118">Die primär und sekundär unterstützten Sprachen werden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="95f6a-118">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="95f6a-119">Die Reihenfolge, in der Sie Sie in den Listen auswählen, ist die Reihenfolge der für die Anrufer vorgestellten Sprachen.</span><span class="sxs-lookup"><span data-stu-id="95f6a-119">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="95f6a-120">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="95f6a-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="95f6a-121">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="95f6a-121">Want else should I know?</span></span>

- <span data-ttu-id="95f6a-122">Unter [Unterstützte Sprachen für Audiokonferenzen](/MicrosoftTeams/audio-conferencing-supported-languages) finden Sie eine Liste der für Audiokonferenzen unterstützten Sprachen.</span><span class="sxs-lookup"><span data-stu-id="95f6a-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="95f6a-123">Sprachen können für dedizierte, aber nicht für freigegebene Telefonnummern festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="95f6a-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="95f6a-124">Eine Liste der Länder/Regionen, in denen Audiokonferenzen in Microsoft 365 oder Office 365 mit Microsoft als Anbieter verfügbar sind, finden Sie unter [Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="95f6a-124">To see a list of countries/regions in which Audio Conferencing in Microsoft 365 or Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="95f6a-125">Wollen Sie Windows PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="95f6a-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="95f6a-126">Um diesen Schritt zu automatisieren, können Sie die Cmdlets " [Satz-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) " und " [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) " verwenden.</span><span class="sxs-lookup"><span data-stu-id="95f6a-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) and [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.</span></span>
  
<span data-ttu-id="95f6a-127">Weitere Informationen finden Sie unter [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)</span><span class="sxs-lookup"><span data-stu-id="95f6a-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="95f6a-128">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="95f6a-128">Related topics</span></span>

[<span data-ttu-id="95f6a-129">Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="95f6a-129">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
