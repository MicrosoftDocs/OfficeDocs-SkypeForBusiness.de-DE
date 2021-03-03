---
title: Konfigurieren von Voicemail escape in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Zusammenfassung: Informationen zum Konfigurieren von Voicemail escape in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell.'
ms.openlocfilehash: c6326360a0e49715feb7e9f9c3c123ec42b9c330
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824925"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Konfigurieren von Voicemail escape in Skype for Business

**Zusammenfassung:** Erfahren Sie, wie Sie Voicemail escape in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.

Wenn ein Benutzer gleichzeitiges Klingeln an ein Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an die persönliche Voicemail des Benutzers geroutet, wenn das Mobiltelefon ausgeschaltet ist, der Akkustand ausgeschaltet oder nicht mehr in Reichweite ist. Mit Skype for Business Server können Benutzer unternehmensbezogene Anrufe an ihr Voicemailsystem des Unternehmens weiter routen lassen. Insbesondere kann ein Timer konfiguriert werden, und wenn der Anruf innerhalb des festgelegten Zeitbereichs von der Voicemail des Netzbetreibers beantwortet wird, trennt Skype for Business Server die Verbindung mit dem Voicemailsystem des Netzbetreibers (und der persönlichen Voicemail des Benutzers), während die verbleibenden Endpunkte des Benutzers im Unternehmenssystem weiter klingeln. Auf diese Weise wird der Anrufer automatisch an die Voicemail des Unternehmens des Benutzers geroutet.

Diese Konfiguration wird mit dem Skype for Business Server Management Shell-Cmdlet **"Set-CsVoicePolicy"** auf der Ebene der Sprachrichtlinie mit den folgenden Parametern ausgeführt.

### <a name="to-configure-voice-mail-escape"></a>So konfigurieren Sie Voicemail escape

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**

2. Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:

   - **EnableVoicemailEscapeTimer** – Aktiviert oder deaktiviert den Escape-Timer.

   - **PSTNVoicemailEscapeTimer** – Gibt den Zeitüberschreitungswert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden, und der Wert kan zwischen 0 und 8000 Millisekunden liegen.

## <a name="example"></a>Beispiel

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Siehe auch

[Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

