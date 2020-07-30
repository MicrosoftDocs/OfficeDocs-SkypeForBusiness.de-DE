---
title: Cortana-Sprachassistent in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Informationen zur Verwendung von Cortana Voice Assistant in Teams
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522316"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana-Sprachunterstützung in Teams

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> Cortana-VoIP-Unterstützung wird nur für Benutzer in den USA in den mobilen Microsoft Teams IOS-und Android-Apps unterstützt. Sie ist derzeit nicht für gcc-, gcc-höchst-, DoD-, edu-Mandanten verfügbar. Die Erweiterung auf weitere Sprachen und Regionen erfolgt in zukünftigen Versionen.

Cortana-VoIP-Unterstützung in der mobilen Teams-App ermöglicht es Microsoft 365 Enterprise-Benutzern, Kommunikations-, Zusammenarbeits-und Besprechungs bezogene Aufgaben mithilfe der gesprochenen natürlichen Sprache zu rationalisieren. Benutzer können mit Cortana sprechen, indem Sie auf die Schaltfläche Mikrofon klicken, die sich in der oberen rechten Ecke der Mobile-App für Teams befindet. Um schnell eine Verbindung mit Ihrem Team herzustellen, während Sie unterwegs sind, können Benutzer Abfragen wie "Megan anrufen" oder "eine Nachricht an meine nächste Besprechung senden" sagen. Benutzer können auch an Besprechungen teilnehmen, indem Sie "an meiner nächsten Besprechung teilnehmen" und die Sprachunterstützung verwenden, um Dateien freizugeben, Ihren Kalender zu überprüfen und vieles mehr. Diese sprach Unterstützungsfunktionen werden mithilfe von [Cortana Enterprise-Services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 entsprechen, wie Sie in den [Online Services-Bedingungen (Ost)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)widergespiegelt werden.

Das Bild zeigt das Senden eines Chats in Cortana auf einem mobilen Gerät.

![Abbildung zeigt eine Abfolge von mobilen Bildschirmen mit einer Cortana-Chat-Sitzung](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Administratorsteuerung und Einschränkungen

Cortana-VoIP-Unterstützung in Teams wird mithilfe von Diensten bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 auf Unternehmensebene entsprechen, wie Sie in den Online Services-Bedingungen (Ost) widergespiegelt werden. Das Feature wird standardmäßig für Mandanten aktiviert.

Mandantenadministratoren können steuern, wer in Ihrem Mandanten Cortana-VoIP-Unterstützung in Teams mithilfe einer Richtlinie (TeamsCortanaPolicy) verwenden kann. Diese Richtlinie kann entweder auf Ebene des Benutzerkontos oder auf Mandantenebene eingestellt werden. Administratoren können das CortanaVoiceInvocationMode-Feld in diesem Richtliniensteuerelement verwenden, um zu ermitteln, ob Cortana deaktiviert ist, nur mit einem Push-Schaltflächen Aufruf oder mit Wake Word-Aufruf aktiviert ist (gilt für Geräte, die das Programm unterstützen).

Administratoren können die folgenden PowerShell-Cmdlets zum Verwalten dieser Richtlinie verwenden (die Richtlinie steht derzeit im Microsoft Teams Admin Center nicht zur Verfügung).

- [Neu – CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Satz-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie mit dem Namen "EmployeeCortanaPolicy" erstellt, in der der Cortana-Sprachassistent in Microsoft Teams deaktiviert ist.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

In diesem Beispiel wird gezeigt, wie Sie eine vorhandene Richtlinie mit dem Namen "EmployeeCortanaPolicy" aktualisieren und den Cortana-Sprachassistenten in Microsoft Teams mit nur Tasten Aufruf aktivieren. Benutzer können Cortana aufrufen, indem Sie in Teams auf die Cortana MIC-Schaltfläche tippen. Wake Word ("Hey Cortana") Aufruf wird deaktiviert.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Dieses Beispiel zeigt, wie Sie die Richtlinie aktualisieren und den Cortana-Sprachassistenten sowohl mit der Schaltfläche als auch mit dem Wake-Word-Aufruf aktivieren.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> Zum Zeitpunkt der ersten Veröffentlichung für Microsoft 365 Enterprise-Benutzer in den USA in englischer Sprache unterstützt die Mobile Teams-App keine Aktivierung des Aktivierungs Worts, wird aber in Zukunft unterstützt.

## <a name="user-control"></a>Benutzersteuerelement

Einzelne Benutzer können die Cortana-Sprachunterstützung in der mobilen Mobile-App testen, indem Sie auf die Schaltfläche "Mikrofon" klicken. Sie können auch steuern, ob Cortana in Teams für Ihr Gerät mithilfe einer Einstellung in der mobilen Teams-App aktiviert ist.

1. Öffnen Sie die Mobile Teams-app.

2. Wechseln Sie zu **Einstellungen**.

3. Wählen Sie **Cortana**aus.

4. Verschieben Sie den Umschalter auf **ein** oder **aus**, je nachdem, ob Sie Cortana-VoIP-Unterstützung auf dem Gerät wünschen.
