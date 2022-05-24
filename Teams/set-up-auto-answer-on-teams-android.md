---
title: Einrichten der automatischen Antwort für Teams Android Geräte
author: mkbond007
ms.author: mabond
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
description: Erfahren Sie, wie Sie das Feature für die automatische Antwort für Microsoft Teams-Räume auf Android und Teams Videotelefongeräten mit PowerShell einrichten.
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646594"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Einrichten der automatischen Antwort für Microsoft Teams-Räume auf Android- und Teams Videotelefongeräten

Dieser Artikel hilft Ihnen beim Einrichten der Funktion für die automatische Antwort auf Microsoft Teams-Räume auf Android- und Teams Videotelefongeräten. Mit der automatischen Antwort können Personen in Ihrer Organisation mit Administratorrechten ihre Geräteeinstellungen ändern, um eingehende Besprechungseinladungen automatisch anzunehmen und Anrufe mit Video automatisch anzunehmen.

## <a name="enable-auto-answer-with-powershell"></a>Aktivieren der automatischen Antwort mit PowerShell

Verwenden Sie die folgenden Attribute, um die automatische Antwort auf Microsoft Teams-Räume auf Android- und Teams Videotelefongeräten zu aktivieren:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Automatische Antwort für eingehende Besprechungseinladungen aktivieren

Sie verwenden **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** , um die automatische Antwort für eingehende Besprechungseinladungen zu aktivieren. Die automatische Antwort ist standardmäßig **deaktiviert** . Diese Richtlinie gilt nur für eingehende Besprechungseinladungen und unterstützt keine anderen Anruftypen. Weitere Informationen zum Cmdlet finden Sie unter ["Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) ".

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Festlegen des Geräteanmeldungsmodus

Sie verwenden **Set-CsTeamsIPPhonePolicy -SignInMode**, um den Anmeldemodus für das Gerät festzulegen, um das Verhalten bei der Anmeldung bei Teams zu bestimmen. Weitere Informationen zum Cmdlet finden Sie unter [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) .

Es gibt drei Optionen für den Anmeldemodus:

- **UserSignIn:** Ermöglicht einem einzelnen Benutzer Teams Erfahrung auf dem Telefon.
- **CommonAreaPhoneSignIn:** Ermöglicht eine Telefonerfahrung im einheitlichen Bereich auf dem Telefon.
- **MeetingSignIn:** Ermöglicht eine Besprechungsraumerfahrung auf dem Telefon.

Die folgende Richtlinie legt beispielsweise den Anmeldemodus auf eine Besprechungsraumumgebung fest.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Konfigurieren von Geräteeinstellungen

Nach dem Aktivieren der automatischen Antwort können Benutzer mit Administratorberechtigungen das Feature in ihren Geräteeinstellungen aktivieren. Um das Feature auf Geräteebene zu aktivieren, müssen Sie die automatische **Annahme eingehender Besprechungseinladungen** aktivieren. Sie können die **automatische Annahme auch mit Video** aktivieren. Beide Einstellungen sind standardmäßig deaktiviert.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft-Support: Anrufe und Geräte](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
