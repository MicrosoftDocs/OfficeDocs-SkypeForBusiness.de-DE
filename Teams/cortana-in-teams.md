---
title: Cortana-Sprachunterstützung in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Erfahren Sie, wie Sie Cortana-Sprachunterstützung bei Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886734"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana-Sprachunterstützung in Teams

> [!Note]
> Cortana-Sprachunterstützung wird in Microsoft Teams mobilen Apps für iOS und Android sowie Microsoft Teams-Anzeigen für Benutzer in den USA, Großbritannien, Kanada, Indien und Australien unterstützt.  Microsoft Teams-Räume auf Windows wird nur für Benutzer in den USA unterstützt. Cortana-Sprachunterstützung ist derzeit für Mandanten von GCC, GCC, DoD, EDU nicht verfügbar. Die Erweiterung auf weitere Sprachen und Regionen wird im Rahmen zukünftiger Versionen sein.

> [!Note]
> Cortana-Sprachunterstützung in Microsoft Teams-Räume wird unter Vorschau veröffentlicht. In der Preview-Version wird Cortana nur in den USA mit der Sprache EN-US auf Geräten mit angeschlossenen Mikrofonen aus Der Usa unterstützt.

Cortana-Sprachunterstützung in der mobilen Teams-App, in Microsoft Teams-Räume auf Windows und auf Microsoft Teams-Anzeigegeräten ermöglicht es Microsoft 365 Enterprise-Benutzern, kommunikations-, zusammenarbeits- und besprechungsbezogene Aufgaben in natürlicher Sprache zu optimieren. Benutzer können mit Cortana sprechen, indem sie die Mikrofonschaltfläche oben rechts in der mobilen Teams-App auswählen &#8220;oder im Microsoft Teams-Raum&#8221; Cortana&#8221; sagen oder einen Microsoft Teams verwenden. Um sich schnell freisprechend mit dem Team zu verbinden, und während sie unterwegs sind, können Benutzer Abfragen wie &#8220;Megan&#8221; oder &#8220;eine Nachricht an meine nächste Besprechungs-E-Mail senden&#8221;. Benutzer können an Besprechungen teilnehmen, indem sie sagen&#8220;an meiner nächsten Besprechung teilnehmen&#8221; und mithilfe von Sprachunterstützung Dateien freigeben, ihren Kalender überprüfen und vieles mehr. Diese Sprachunterstützungserfahrungen werden mithilfe von [Cortana-Diensten](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) der Unternehmensklasse übermittelt, die gemäß den Nutzungsbedingungen für [Onlinedienste (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)vollständig den Datenschutz-, Sicherheits- und Compliance-Zusagen von Office 365 entsprechen.

Die Abbildung zeigt das Senden eines Chats mit Cortana auf einem Mobilgerät.

![Abfolge von mobilen Bildschirmen mit einer Cortana-Chatsitzung](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Administratorkontrolle und -beschränkungen

Cortana-Sprachunterstützung in Teams wird mithilfe von Diensten übermittelt, die gemäß den Nutzungsbedingungen für Onlinedienste (OST) vollständig den Zusagen auf Office 365 Unternehmensebene hinsichtlich Datenschutz, Sicherheit und Compliance entsprechen. Das Feature wird für Mandanten standardmäßig aktiviert.

Mandantenadministratoren können mithilfe einer Richtlinie (TeamsCortanaPolicy) steuern, wer in ihrem Mandanten Cortana-Sprachunterstützung in Teams verwenden kann. Diese Richtlinie kann auf Benutzerkonto- oder Mandantenebene festgelegt werden. Administratoren können das Feld CortanaVoiceInvocationMode innerhalb dieses Richtliniensteuerelements verwenden, um festzustellen, ob Cortana deaktiviert ist, nur per Push-Schaltflächenaufruf oder auch durch Reaktivierung des Wortaufrufs aktiviert wird (gilt für Geräte, die diese Funktion unterstützen, z. B. die Microsoft Teams-Anzeige).

Administratoren können diese Richtlinie mithilfe der folgenden PowerShell-Cmdlets verwalten (die Richtlinie ist Microsoft Teams Admin Center derzeit nicht verfügbar).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Mit dem folgenden Befehl wird z. B. eine neue Richtlinie mit dem &#8220;EmployeeCortanaPolicy&#8221; mit deaktivierter Cortana-Sprachunterstützung in Microsoft Teams erstellt.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Dieses Beispiel zeigt das Aktualisieren einer vorhandenen Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221; und das Aktivieren der Cortana-Sprachunterstützung in Microsoft Teams nur mit dem Aufruf von Schaltflächen. Benutzer können Cortana aufrufen, indem sie die Cortana-Mikrofonschaltfläche im Teams. Der Reaktivierungsaufruf &#8220;Hey Cortana&#8221; oder &#8220;Cortana&#8221;) ist deaktiviert.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

In diesem Beispiel wird gezeigt, wie die Richtlinie aktualisiert und Cortana-Sprachunterstützung aktiviert wird, indem sowohl der Aufruf der Taste als auch das Reaktivierungswort aktiviert wird.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Zum Zeitpunkt der ersten Version für benutzer Microsoft 365 Enterprise in den USA in Englisch sind folgende Funktionen verfügbar:

- Die Teams mobilen App unterstützt die Aktivierung von Reaktivierungsworten nicht, wird aber in Zukunft unterstützt.  

- Microsoft Teams-Räume auf Windows- und Microsoft Teams-Anzeigegeräten unterstützen die Aktivierung von Reaktivierungsworten.

## <a name="user-control"></a>Benutzersteuerelement

Einzelne Benutzer können Cortana-Sprachunterstützung auf verschiedenen Geräten ausprobieren:

- Wählen Sie in der mobilen Teams Mikrofonschaltfläche aus.

- Wählen Sie die Mikrofonschaltfläche aus, oder sagen Sie "Cortana" Microsoft Teams-Räume.

- Sagen Sie auf Ihren Microsoft Teams "Cortana".

Sie können steuern, ob Cortana in Teams für Ihr Gerät aktiviert ist, indem Sie eine Einstellung auf dem Gerät verwenden.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams mobile App oder die Microsoft Teams Anzeigen

  1. Öffnen Sie die Teams Mobile-App.

  2. Wählen **Sie Einstellungen** Cortana  >  **aus.**

  3. Verschieben Sie den Umschalter **auf Ein** **oder Aus.**

### <a name="microsoft-teams-display"></a>Microsoft Teams anzeigen

  1. Wechseln Sie zum Umgebungsbildschirm (Startbildschirm) des Microsoft Teams Bildschirms.

  2. Wählen Sie den Benutzer avatar und dann **Einstellungen** aus. Wenn Cortana aktiviert ist, sagen Sie: "Cortana, gehe zu Einstellungen".

  3. Verschieben Sie den Umschalter **auf Ein** **oder Aus.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams-Räume auf Windows

Änderungen auf Geräteebene sind verfügbar, wenn Cortana auf Mandantenebene aktiviert ist. Cortana wird standardmäßig deaktiviert.

Um Cortana auf Geräteebene zu aktivieren, müssen die folgenden XML-Attribute in der SkypeSettings-XML-Datei hinzugefügt werden:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Änderungen auf Besprechungsebene sind verfügbar, wenn Cortana auf Geräteebene aktiviert ist.

Um Cortana-Sprachunterstützung während einer Besprechung zu aktivieren, bewegen Sie den Umschalter **auf Ein** oder **Aus.** Sobald die Besprechung beendet ist, kehrt Cortana zu den auf Geräteebene festgelegten Einstellungen zurück.
