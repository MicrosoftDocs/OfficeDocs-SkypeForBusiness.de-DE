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
# <a name="managing-application-level-response-group-settings-in-skype-for-business-2015"></a>Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Skype for Business 2015
 
Verwalten von auf Anwendungsebene reaktionsgruppeneinstellungen, wie Musik halten und Rückruf Einstellungen in Skype für Business Server Enterprise-VoIP.
  
Anwendungsebene Einstellungen für die Anwendung "Reaktionsgruppe" umfassen die Standardkonfiguration für die Musik halten, die standardmäßige Musik halten Audiodatei, die Agents bei Kulanzfrist und der anrufkontextkonfiguration. Pro Pool können Sie nur eine Gruppe von Einstellungen auf Anwendungsebene definieren. Verwenden Sie das Cmdlet **Get-CsRgsConfiguration** aus, um Einstellungen auf Anwendungsebene anzuzeigen. Um die Einstellungen auf Anwendungsebene ändern möchten, verwenden Sie das Cmdlet " **Set-CsRgsConfiguration** ".
  
Die Standard-Wartemusik wird wiedergegeben, wenn ein Anruf in der Warteschleife platziert wird, und auch nur dann, wenn keine benutzerdefinierte Wartemusik definiert wurde. Der Anrufkontext ist nur für Warteschleifen verfügbar, die interaktiven Workflows zugeordnet sind. Wenn der Anrufkontext aktiviert ist, kann ein Agent Informationen wie die Wartezeit des Anrufers oder Fragen und Antworten zu einem Workflow anzeigen, wenn der Anruf empfangen wird.
  
### <a name="to-modify-response-group-application-level-settings"></a>So ändern Sie reaktionsgruppeneinstellungen auf Anwendungsebene

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Beispiel:
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Wenn Sie eine Audiodatei angeben möchten, die als Standard-Wartemusik verwendet werden soll, müssen Sie zunächst die Audiodatei importieren. Beispiel:
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Siehe auch

#### 

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)

