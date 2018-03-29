---
title: Konfigurieren von Voicemail Escape in Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Zusammenfassung: Erfahren Sie, wie mithilfe der Skype für Business Server-Verwaltungsshell des Wechsels der Voicemail in Skype für Business Server 2015 konfigurieren.'
ms.openlocfilehash: 07586f38127b2831ecdb2900f005ff43b4184292
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a>Konfigurieren von Voicemail Escape in Skype for Business 2015
 
**Zusammenfassung:** Erfahren Sie, wie mithilfe der Skype für Business Server-Verwaltungsshell des Wechsels der Voicemail in Skype für Business Server 2015 konfigurieren.
  
Wenn ein Benutzer Gleichzeitiges Klingeln an ein Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an den Benutzer Persönliche Voicemail weitergeleitet werden, wenn das Mobiltelefon deaktiviert, nicht genügend Batterie oder außerhalb des gültigen Bereichs aktiviert ist. Mit Skype für Business Server können Benutzer Ihre geschäftliche Anrufe an ihre corporate Voicemail-System weitergeleitet wurden. Ein Zeitgebers konfiguriert werden kann, insbesondere wenn von der Netzbetreiber Voicemail innerhalb des Bereichs definierte Zeit der Anruf entgegengenommen wurde, wird Skype für Business Server aus der Netzbetreiber Voicemail-Systems (und persönliche Voicemail des Benutzers), während des Benutzers getrennt verbleibenden Endpunkte in der corporate System weiter angeboten werden soll. Auf diese Weise ist der Anrufer automatisch an den Benutzer im Unternehmen Voicemail weitergeleitet.
  
Diese Konfiguration erfolgt mithilfe der Skype für Business Server-Verwaltungsshell-Cmdlet **Set-CsVoicePolicy**auf Ebene der VoIP-Richtlinie mit den folgenden Parametern.
  
### <a name="to-configure-voice-mail-escape"></a>So konfigurieren Sie Voicemail Escape

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:
    
   - **EnableVoicemailEscapeTimer**: Aktiviert oder deaktiviert den Escape-Timer.
    
   - **PSTNVoicemailEscapeTimer**: Gibt den Timeoutwert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden und der Wert kann zwischen 0 und 8000 Millisekunden liegen.
    
## <a name="example"></a>Beispiel

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000

Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

```

## <a name="see-also"></a>Siehe auch

#### 

[Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und-Berechtigungen](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

