---
title: Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Verwalten von auf Anwendungsebene reaktionsgruppeneinstellungen, wie Musik halten und Rückruf Einstellungen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: c202ce60f23594389c7f49f0108f7d03cb1deef5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business-2015"></a><span data-ttu-id="753f3-103">Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="753f3-103">Managing application-level Response Group settings in Skype for Business 2015</span></span>
 
<span data-ttu-id="753f3-104">Verwalten von auf Anwendungsebene reaktionsgruppeneinstellungen, wie Musik halten und Rückruf Einstellungen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="753f3-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="753f3-105">Anwendungsebene Einstellungen für die Anwendung "Reaktionsgruppe" umfassen die Standardkonfiguration für die Musik halten, die standardmäßige Musik halten Audiodatei, die Agents bei Kulanzfrist und der anrufkontextkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="753f3-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="753f3-106">Pro Pool können Sie nur eine Gruppe von Einstellungen auf Anwendungsebene definieren.</span><span class="sxs-lookup"><span data-stu-id="753f3-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="753f3-107">Verwenden Sie das Cmdlet **Get-CsRgsConfiguration** aus, um Einstellungen auf Anwendungsebene anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="753f3-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="753f3-108">Um die Einstellungen auf Anwendungsebene ändern möchten, verwenden Sie das Cmdlet " **Set-CsRgsConfiguration** ".</span><span class="sxs-lookup"><span data-stu-id="753f3-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="753f3-p102">Die Standard-Wartemusik wird wiedergegeben, wenn ein Anruf in der Warteschleife platziert wird, und auch nur dann, wenn keine benutzerdefinierte Wartemusik definiert wurde. Der Anrufkontext ist nur für Warteschleifen verfügbar, die interaktiven Workflows zugeordnet sind. Wenn der Anrufkontext aktiviert ist, kann ein Agent Informationen wie die Wartezeit des Anrufers oder Fragen und Antworten zu einem Workflow anzeigen, wenn der Anruf empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="753f3-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="753f3-112">So ändern Sie reaktionsgruppeneinstellungen auf Anwendungsebene</span><span class="sxs-lookup"><span data-stu-id="753f3-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="753f3-113">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="753f3-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="753f3-114">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="753f3-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="753f3-115">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="753f3-115">At the command line, run:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="753f3-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="753f3-116">For example:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="753f3-p103">Wenn Sie eine Audiodatei angeben möchten, die als Standard-Wartemusik verwendet werden soll, müssen Sie zunächst die Audiodatei importieren. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="753f3-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="753f3-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="753f3-119">See also</span></span>

#### 

[<span data-ttu-id="753f3-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="753f3-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="753f3-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="753f3-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="753f3-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="753f3-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)

