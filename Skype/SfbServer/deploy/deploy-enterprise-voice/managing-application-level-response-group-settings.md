---
title: Verwalten von reaktionsgruppeneinstellungen auf Anwendungsebene in Skype für Unternehmen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Verwalten von auf Anwendungsebene reaktionsgruppeneinstellungen, wie Musik halten und Rückruf Einstellungen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 1aa3234860193cac40e6ca8a39323013847606fb
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012302"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Verwalten von reaktionsgruppeneinstellungen auf Anwendungsebene in Skype für Unternehmen
 
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

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)