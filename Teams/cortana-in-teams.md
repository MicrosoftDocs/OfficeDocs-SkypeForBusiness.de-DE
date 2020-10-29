---
title: Cortana-VoIP-Unterstützung in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Informationen zur Verwendung der Cortana-Sprachunterstützung für Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785389"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana-Sprachunterstützung in Teams

> [!Note]
> Cortana-VoIP-Unterstützung wird in den mobilen Microsoft Teams IOS-und Android-Apps sowie auf Microsoft Teams-Displays nur für Benutzer in den Vereinigten Staaten unterstützt. Sie ist derzeit nicht für gcc-, gcc-höchst-, DoD-, edu-Mandanten verfügbar. Die Erweiterung auf weitere Sprachen und Regionen erfolgt in zukünftigen Versionen.

Cortana-VoIP-Unterstützung in der mobilen Teams-APP und auf Anzeigegeräten von Microsoft Teams ermöglicht es Microsoft 365 Enterprise-Benutzern, Kommunikations-, Zusammenarbeits-und Besprechungs bezogene Aufgaben mithilfe der gesprochenen natürlichen Sprache zu rationalisieren. Benutzer können mit Cortana sprechen, indem Sie die Schaltfläche Mikrofon in der oberen rechten Ecke der mobilen App für Teams auswählen oder indem Sie in der Microsoft Teams-Anzeige &#8220;Cortana&#8221; sagen. Damit Sie schnell und einfach mit Ihrem Team in Kontakt treten können, können Benutzer Abfragen wie &#8220;Megan&#8221; anrufen oder &#8220;eine Nachricht an meine nächste Besprechungs&#8221; senden. Benutzer können auch an Besprechungen teilnehmen, indem Sie &#8220;teilnehmen an meiner nächsten Besprechung&#8221; und die Sprachunterstützung verwenden, um Dateien freizugeben, Ihren Kalender zu überprüfen und vieles mehr. Diese sprach Unterstützungsfunktionen werden mithilfe von [Cortana Enterprise-Services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 entsprechen, wie Sie in den [Online Services-Bedingungen (Ost)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)widergespiegelt werden.

Das Bild zeigt das Senden eines Chats mithilfe von Cortana auf einem mobilen Gerät.

![Abbildung zeigt eine Abfolge von mobilen Bildschirmen mit einer Cortana-Chat-Sitzung](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Administratorsteuerung und Einschränkungen

Cortana-VoIP-Unterstützung in Teams wird mithilfe von Diensten bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 auf Unternehmensebene entsprechen, wie Sie in den Online Services-Bedingungen (Ost) widergespiegelt werden. Das Feature wird standardmäßig für Mandanten aktiviert.

Mandantenadministratoren können steuern, wer in Ihrem Mandanten Cortana-VoIP-Unterstützung in Teams mithilfe einer Richtlinie (TeamsCortanaPolicy) verwenden kann. Diese Richtlinie kann entweder auf Ebene des Benutzerkontos oder auf Mandantenebene eingestellt werden. Administratoren können das CortanaVoiceInvocationMode-Feld in diesem Richtliniensteuerelement verwenden, um zu ermitteln, ob Cortana deaktiviert ist, nur mit dem Aufruf von Schaltflächen aufrufen oder mit Wake Word-Aufruf aktiviert ist (gilt für Geräte, die es unterstützen, wie die Microsoft Teams-Anzeige).

Administratoren können die folgenden PowerShell-Cmdlets zum Verwalten dieser Richtlinie verwenden (die Richtlinie steht derzeit im Microsoft Teams Admin Center nicht zur Verfügung).

- [Neu – CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Satz-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221;, in der Cortana-VoIP-Unterstützung in Microsoft Teams deaktiviert ist.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

In diesem Beispiel wird das Aktualisieren einer vorhandenen Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221; und das Aktivieren von Cortana-VoIP-Unterstützung in Microsoft Teams mit nur Tasten Aufruf veranschaulicht. Benutzer können Cortana aufrufen, indem Sie die Cortana MIC-Schaltfläche in Teams auswählen. Wake Word (&#8220;Hey Cortana&#8221; oder &#8220;Cortana&#8221;)-Aufruf wird deaktiviert.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

In diesem Beispiel wird die Aktualisierung der Richtlinie und die Aktivierung der Cortana-VoIP-Unterstützung sowohl beim Drücken als auch beim Aktivieren des Word-Aufrufs veranschaulicht.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> Zum Zeitpunkt der ersten Veröffentlichung für Microsoft 365 Enterprise-Benutzer in den USA in englischer Sprache unterstützt die Mobile Teams-App keine Aktivierung des Aktivierungs Worts, wird aber in Zukunft unterstützt. Die Wake Word-Aktivierung funktioniert auf den Anzeigegeräten von Microsoft Teams bei der ersten Version.

## <a name="user-control"></a>Benutzersteuerelement

Einzelne Benutzer können die Cortana-Sprachunterstützung in der mobilen Teams-App ausprobieren, indem Sie die Schaltfläche Mikrofon auswählen. Sie können Cortana-Sprachunterstützung auf Microsoft Teams-Anzeigegeräten ausprobieren, indem Sie einfach &#8220;Cortana. &#8221; Sie können auch steuern, ob Cortana in Teams für Ihr Gerät aktiviert ist, indem Sie eine Einstellung in der mobilen Teams-APP oder in der Microsoft Teams-Anzeige verwenden.

1. Öffnen Sie die Mobile Teams-APP, oder wechseln Sie zum Bildschirm Ambient (Home) der Microsoft Teams-Anzeige.

2. Wechseln Sie in der mobilen Teams-APP zu **Einstellungen** . Wählen Sie in der Microsoft Teams-Anzeige den Avatar des Benutzers aus, und wählen Sie dann Einstellungen aus. Wenn Cortana aktiviert ist, sagen Sie &#8220;Cortana, wechseln Sie zu Einstellungen. &#8221;

3. Wählen Sie **Cortana** aus.

4. Verschieben Sie den Umschalter auf **ein** oder **aus** , je nachdem, ob Sie Cortana-VoIP-Unterstützung auf dem Gerät wünschen.
