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
description: 'Zusammenfassung: Erfahren Sie, wie Sie Voicemail escape in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.'
ms.openlocfilehash: f94a9e78d5f1b88644691d43b7c24169e6122e6188f7ee45c095521230b6be3f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279423"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Konfigurieren von Voicemail escape in Skype for Business

**Zusammenfassung:** Erfahren Sie, wie Sie Voicemail escape in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.

Wenn ein Benutzer das gleichzeitige Klingeln an ein Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an die persönliche Voicemail des Benutzers weitergeleitet, wenn das Mobiltelefon ausgeschaltet, nicht genügend Akku oder außerhalb des Bereichs ist. Mit Skype for Business Server können Benutzer geschäftsbezogene Anrufe an ihr Voicemailsystem des Unternehmens weiterleiten lassen. Insbesondere kann ein Timer konfiguriert werden, und wenn der Anruf innerhalb des festgelegten Zeitraums von der Voicemail des Netzbetreibers angenommen wird, trennt Skype for Business Server die Verbindung mit dem Voicemailsystem des Netzbetreibers (und der persönlichen Voicemail des Benutzers), während die verbleibenden Endpunkte des Benutzers im Unternehmenssystem weiterhin klingeln. Auf diese Weise wird der Anrufer automatisch an die Voicemail des Benutzers weitergeleitet.

Diese Konfiguration wird mithilfe des Cmdlets **"set-CsVoicePolicy"** der Skype for Business Server Verwaltungsshell auf VoIP-Richtlinienebene mit den folgenden Parametern ausgeführt.

### <a name="to-configure-voice-mail-escape"></a>So konfigurieren Sie Voicemail escape

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**

2. Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:

   - **EnableVoicemailEscapeTimer** – Aktiviert oder deaktiviert den Escape-Timer.

   - **PSTNVoicemailEscapeTimer** – Gibt den Zeitüberschreitungswert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden, und der Wert kan zwischen 0 und 8000 Millisekunden liegen.

## <a name="example"></a>Beispiel

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Siehe auch

[Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)