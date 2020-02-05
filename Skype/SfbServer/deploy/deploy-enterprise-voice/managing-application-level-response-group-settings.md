---
title: Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Verwalten von Einstellungen für die Reaktionsgruppe auf Anwendungsebene, beispielsweise in Skype for Business Server Enterprise-VoIP, wie Musik-in-halten-und Begrüssungs Einstellungen.
ms.openlocfilehash: 99a3d6bc82cffd39608d2da0be013d4fbb8389e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767108"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Skype for Business
 
Verwalten von Einstellungen für die Reaktionsgruppe auf Anwendungsebene, beispielsweise in Skype for Business Server Enterprise-VoIP, wie Musik-in-halten-und Begrüssungs Einstellungen.
  
Zu den Einstellungen auf Anwendungsebene für die Anwendung der Reaktionsgruppe gehören die standardmäßige Musik-in-situ-Konfiguration, die standardmäßige Musik-in-halten-Audiodatei, die Kulanzzeit für den Agent-Rückruf und die Konfiguration des Anruf Kontexts. Pro Pool können Sie nur eine Gruppe von Einstellungen auf Anwendungsebene definieren. Verwenden Sie zum Anzeigen der Einstellungen auf Anwendungsebene das Cmdlet **Get-CsRgsConfiguration**. Wenn Sie die Einstellungen auf Anwendungsebene ändern möchten, verwenden Sie das Cmdlet **Set-CsRgsConfiguration**.
  
Die Standard-Wartemusik wird wiedergegeben, wenn ein Anruf in der Warteschleife platziert wird, und auch nur dann, wenn keine benutzerdefinierte Wartemusik definiert wurde. Der Anrufkontext ist nur für Warteschleifen verfügbar, die interaktiven Workflows zugeordnet sind. Wenn der Anrufkontext aktiviert ist, kann ein Agent Informationen wie die Wartezeit des Anrufers oder Fragen und Antworten zu einem Workflow anzeigen, wenn der Anruf empfangen wird.
  
### <a name="to-modify-response-group-application-level-settings"></a>So ändern Sie die Einstellungen der Reaktionsgruppe auf Anwendungsebene

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Beispiel:
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Wenn Sie eine Audiodatei angeben möchten, die als Standard-Wartemusik verwendet werden soll, müssen Sie zunächst die Audiodatei importieren. Beispiel:
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Siehe auch

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Satz-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Importieren-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
