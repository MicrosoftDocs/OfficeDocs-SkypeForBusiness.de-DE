---
title: Einrichten der automatischen Antwort für Teams Android-Geräte
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Erfahren Sie, wie Sie das Feature für die automatische Antwort für Android Teams mit PowerShell einrichten.
ms.openlocfilehash: e25b0694b54d1047c64ecaba026380ac9c4a9949
ms.sourcegitcommit: 5e9a8d3cdb72b57adfb842200159c5d753b70ecb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2022
ms.locfileid: "62329100"
---
# <a name="set-up-auto-answer-for-teams-android-devices"></a>Einrichten der automatischen Antwort für Teams Android-Geräte

Dieser Artikel hilft Ihnen beim Einrichten der Funktion für die automatische Antwort auf Teams Android-Geräten. Mit der automatischen Antwort können Personen in Ihrer Organisation mit Administratorrechten ihre Geräteeinstellungen ändern, um eingehende Besprechungs-Einladungen automatisch zu akzeptieren und Anrufe automatisch mit Videoanrufen zu akzeptieren.

## <a name="enable-auto-answer-with-powershell"></a>Aktivieren der automatischen Antwort mit PowerShell

Verwenden Sie die folgenden Attribute, um die automatische Antwort auf Teams Android-Geräten zu aktivieren:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Aktivieren der automatischen Antwort für eingehende Besprechungs-Einladungen

Sie verwenden **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** , um die automatische Antwort für eingehende Besprechungs-Einladungen zu aktivieren. Die automatische Antwort **ist standardmäßig** deaktiviert. Diese Richtlinie gilt nur für eingehende Besprechungs-Einladungen und unterstützt keine anderen Anruftypen. Weitere [Informationen zum Cmdlet finden Sie unter Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) .

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Festlegen des Geräte-Anmeldemodus

Sie verwenden **Set-CsTeamsIPPhonePolicy -SignInMode**, um den Anmeldemodus für das Gerät festzulegen, um das Verhalten beim Anmelden bei einem Teams. Weitere [Informationen zum Cmdlet finden Sie unter Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) .

Es gibt drei Optionen für den Anmeldemodus:

- **UserSignIn:** Ermöglicht es einem einzelnen Teams, die Benutzerfreundlichkeit auf dem Smartphone zu verbessern.
- **CommonAreaPhoneSignIn:** Ermöglicht eine gemeinsame Umgebung für Telefone auf dem Handy.
- **MeetingSignIn:** Ermöglicht eine Besprechungsraumerfahrung auf dem Telefon.

Die folgende Richtlinie legt z. B. den Anmeldemodus auf eine Besprechungsraumerfahrung fest.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Konfigurieren von Geräteeinstellungen

Nach dem Aktivieren der automatischen Antwort können Benutzer mit Administratorberechtigungen die Funktion in ihren Geräteeinstellungen aktivieren. Um das Feature auf Geräteebene zu aktivieren, müssen Sie Einladungen für eingehende Besprechungen **automatisch annehmen aktivieren**. Sie können auch Die automatische Annahme **mit Video aktivieren**. Beide Einstellungen sind standardmäßig deaktiviert.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft-Support: Anrufe und Geräte](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)