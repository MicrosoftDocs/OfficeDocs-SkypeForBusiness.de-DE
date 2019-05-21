---
title: Konfigurieren der Voicemail-escapefunktion in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Escape-Voicemail in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.'
ms.openlocfilehash: 89c449f538fee2f5230cb66a664317cada723220
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289083"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Konfigurieren der Voicemail-escapefunktion in Skype for Business

**Zusammenfassung:** Hier erfahren Sie, wie Sie die Escape-Voicemail in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.

Wenn ein Benutzer das gleichzeitige Klingeln auf einem Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an die persönliche Voicemail des Benutzers weitergeleitet, wenn das Mobiltelefon ausgeschaltet ist, der Akku nicht mehr zur verweilen oder außerhalb des gültigen Bereichs liegt. Mit Skype for Business Server können die Benutzer entscheiden, dass unternehmensbezogene Anrufe an das Voicemailsystem Ihres Unternehmens weitergeleitet werden. Insbesondere kann ein Zeitgeber konfiguriert werden, und wenn der Anruf von der Voicemail des Netzbetreibers innerhalb des definierten Zeitraums beantwortet wird, trennt sich Skype for Business Server vom Voicemailsystem des Netzbetreibers (und der persönlichen Voicemail des Benutzers), während die verbleibende Endpunkte im Unternehmenssystem Klingeln weiterhin. Auf diese Weise wird der Anrufer automatisch an die Firmen-Voicemail des Benutzers weitergeleitet.

Diese Konfiguration wird mit dem Cmdlet "Skype for Business Server-Verwaltungsshell", " **Satz-CsVoicePolicy**", auf der VoIP-Richtlinienebene mit den folgenden Parametern ausgeführt.

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

