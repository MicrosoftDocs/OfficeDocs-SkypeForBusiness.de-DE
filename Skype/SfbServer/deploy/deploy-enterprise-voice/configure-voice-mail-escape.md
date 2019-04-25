---
title: Konfigurieren des Wechsels der Voicemail in Skype für Unternehmen
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Zusammenfassung: Erfahren Sie, wie mithilfe der Skype für Business Server-Verwaltungsshell des Wechsels der Voicemail in Skype für Business Server konfigurieren.'
ms.openlocfilehash: 6c1c6977949eb45c28cce482f98be67295ee4eef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223508"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Konfigurieren des Wechsels der Voicemail in Skype für Unternehmen

**Zusammenfassung:** Hier erfahren Sie, wie Sie mithilfe der Skype für Business Server-Verwaltungsshell des Wechsels der Voicemail in Skype für Business Server konfigurieren.

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

[Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

