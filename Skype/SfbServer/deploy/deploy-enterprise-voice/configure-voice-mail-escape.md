---
title: Konfigurieren von Voicemail-Escape in Skype for Business
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
description: 'Zusammenfassung: Informationen zum Konfigurieren der Voicemail-Escape in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell.'
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106371"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Konfigurieren von Voicemail-Escape in Skype for Business

**Zusammenfassung:** Erfahren Sie, wie Sie voicemail escape in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.

Wenn ein Benutzer gleichzeitiges Klingeln an ein Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an die persönliche Voicemail des Benutzers geroutet, wenn das Mobiltelefon ausgeschaltet, nicht mit Strom oder nicht in Reichweite ist. Mit Skype for Business Server können Benutzer entscheiden, dass geschäftsbezogene Anrufe an ihr Voicemailsystem des Unternehmens geroutet werden. Insbesondere kann ein Zeitgeber konfiguriert werden, und wenn der Anruf von der Voicemail des Netzbetreibers innerhalb des festgelegten Zeitraumes beantwortet wird, trennt Skype for Business Server die Verbindung vom Voicemailsystem des Netzbetreibers (und der persönlichen Voicemail des Benutzers), während die verbleibenden Endpunkte des Benutzers im Unternehmenssystem weiterhin klingeln. Auf diese Weise wird der Anrufer automatisch an die Voicemail des Benutzers geroutet.

Diese Konfiguration wird mithilfe des Skype for Business Server Management Shell-Cmdlets **Set-CsVoicePolicy** auf Der Ebene der Voicerichtlinien mit den folgenden Parametern ausgeführt.

### <a name="to-configure-voice-mail-escape"></a>So konfigurieren Sie voicemail escape

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

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