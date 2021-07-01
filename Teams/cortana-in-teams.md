---
title: Cortana Sprachunterstützung in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Hier erfahren Sie, wie Cortana-Sprachunterstützung bei Teams
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
ms.openlocfilehash: 0b343a3f69d2b0f97f9d7d3054951719da2e9e43
ms.sourcegitcommit: b7da2655607a17cde9537ed9e00db29b4c1a68df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53219142"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana Sprachunterstützung in Teams

> [!Note]
> Cortana Sprachunterstützung wird in mobilen Microsoft Teams-Apps für iOS und Android und Microsoft Teams-Anzeigen für Benutzer in den USA, Großbritannien, Kanada, Indien und Australien unterstützt. Microsoft Teams-Räume auf Windows wird nur für Benutzer in den USA unterstützt. Cortana Sprachunterstützung ist derzeit für Mandanten von GCC, GCC-High, DoD und anderen Bildungsorganisationen als den USA nicht verfügbar. Cortana Sprachunterstützung in der mobilen Teams-App ist jetzt für EDU-Kunden in en-US verfügbar. Die Erweiterung auf weitere Sprachen und Regionen wird im Rahmen zukünftiger Versionen sein.

> [!Note]
> Cortana Sprachunterstützung in Microsoft Teams-Räume wird unter Preview veröffentlicht. In der Vorschauversion wird Cortana in den USA nur mit der Sprache EN-US auf Geräten mit angeschlossenen Mikrofonen von Unterem. unterstützt.

Cortana Sprachunterstützung in der mobilen Teams-App, in Microsoft Teams-Räume auf Windows und auf Microsoft Teams-Anzeigegeräten ermöglicht es Microsoft 365 Enterprise-Benutzern, die Kommunikation, Zusammenarbeit und Besprechungsaufgaben in natürlicher Sprache zu optimieren. Benutzer können mit Cortana sprechen, indem sie die Mikrofonschaltfläche auswählen, die sich oben rechts in der mobilen Teams-App befindet, oder indem sie &#8220;Cortana&#8221; im Microsoft Teams Raum sprechen oder eine Microsoft Teams verwenden. Um sich schnell freisprechend mit dem Team zu verbinden, und während sie unterwegs sind, können Benutzer Abfragen wie &#8220;Megan&#8221; oder &#8220;eine Nachricht an meine nächste Besprechungs-E-Mail senden&#8221;. Benutzer können an Besprechungen teilnehmen, indem sie sagen&#8220;an meiner nächsten Besprechung teilnehmen&#8221; und mithilfe von Sprachunterstützung Dateien freigeben, ihren Kalender überprüfen und vieles mehr. Diese Sprachunterstützungserfahrungen werden mithilfe von [Cortana-Diensten](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) der Unternehmensklasse übermittelt, die gemäß den Onlinedienstbedingungen [(OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)vollständig mit den Office 365-Datenschutz-, Sicherheits- und Compliance-Zusagen in Einklang stehen.

Die Abbildung zeigt das Senden eines Chats Cortana einem mobilen Gerät.

![Abfolge von mobilen Bildschirmen mit einer Cortana-Chatsitzung](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Administratorkontrolle und -beschränkungen

Cortana Sprachunterstützung in Teams wird mithilfe von Diensten übermittelt, die gemäß den Onlinedienstbedingungen (Ost) vollständig den Zusagen auf Office 365 Unternehmensebene hinsichtlich Datenschutz, Sicherheit und Compliance entsprechen. Das Feature wird für Mandanten standardmäßig aktiviert.

Mandantenadministratoren können mithilfe einer Richtlinie (TeamsCortanaPolicy) steuern, wer in ihrem Mandanten Cortana Sprachunterstützung in Teams verwenden kann. Diese Richtlinie wird entweder auf Benutzerkonto- oder Mandantenebene festgelegt. Administratoren können das Feld CortanaVoiceInvocationMode innerhalb dieses Richtliniensteuerelements verwenden, um festzustellen, ob Cortana deaktiviert ist, ob es nur über den Aufruf von Schaltflächen oder auch über den Aufruf eines Reaktivierungsworts aktiviert ist (gilt für Geräte, die dies unterstützen, z. B. die Microsoft Teams-Anzeige).

Administratoren können diese Richtlinie mithilfe der folgenden PowerShell-Cmdlets verwalten (die Richtlinie ist Microsoft Teams Admin Center derzeit nicht verfügbar).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221; erstellt, Cortana die Sprachunterstützung in Microsoft Teams deaktiviert ist.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Dieses Beispiel zeigt das Aktualisieren einer vorhandenen Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221; und das Aktivieren von Cortana-Sprachunterstützung in Microsoft Teams nur durch Aufruf der Schaltflächen. Benutzer können Ihr Mikrofon Cortana, indem sie die Schaltfläche Cortana Mikrofons im Teams. Der Reaktivierungsaufruf &#8220;Hey Cortana&#8221; oder &#8220;Cortana&#8221; wird deaktiviert.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

In diesem Beispiel wird gezeigt, wie die Richtlinie aktualisiert und Cortana Sprachunterstützung sowohl über die Pushschaltfläche als auch durch den Reaktivierungsaufruf aktiviert wird.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Zum Zeitpunkt der ersten Version für benutzer Microsoft 365 Enterprise in den USA in Englisch sind folgende Funktionen verfügbar:

- Die Teams mobilen App unterstützt die Aktivierung von Reaktivierungsworten nicht, wird aber in Zukunft unterstützt.  

- Microsoft Teams-Räume auf Windows- und Microsoft Teams-Anzeigegeräten unterstützen die Aktivierung von Reaktivierungsworten.

## <a name="user-control"></a>Benutzersteuerelement

Einzelne Benutzer können versuchen, Cortana Sprachunterstützung auf verschiedenen Geräten zu erhalten:

- Wählen Sie in der mobilen Teams Mikrofonschaltfläche aus.

- Wählen Sie die Mikrofonschaltfläche aus, oder sagen Cortana Mikrofon", Microsoft Teams-Räume.

- Sagen Sie "Cortana" auf Microsoft Teams-Geräten.

Sie können steuern, Cortana in Teams Gerät aktiviert ist, indem Sie eine Einstellung auf dem Gerät verwenden.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams mobile App oder die Microsoft Teams Anzeigen

  1. Öffnen Sie die Teams Mobile-App.

  2. Wählen **Sie Einstellungen**  >  **Cortana** aus.

  3. Verschieben Sie den Umschalter **auf Ein** **oder Aus.**

### <a name="microsoft-teams-display"></a>Microsoft Teams anzeigen

  1. Wechseln Sie zum Umgebungsbildschirm (Startbildschirm) des Microsoft Teams Bildschirms.

  2. Wählen Sie den Benutzer avatar und dann **Einstellungen** aus. Wenn Cortana aktiviert ist, sagen Sie " Cortana, gehe zu Einstellungen".

  3. Verschieben Sie den Umschalter **auf Ein** **oder Aus.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams-Räume auf Windows

Das Vornehmen von Änderungen auf Geräteebene ist verfügbar, Cortana auf Mandantenebene aktiviert ist. Cortana wird standardmäßig AUS freigegeben.

Zum Aktivieren Cortana auf Geräteebene müssen die folgenden XML-Attribute in der SkypeSettings-XML-Datei hinzugefügt werden:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Das Vornehmen von Änderungen auf Besprechungsebene ist verfügbar, Cortana auf Geräteebene aktiviert ist.

Um während Cortana Besprechung Sprachunterstützung zu aktivieren, verschieben Sie die Umschalt auf **Ein** oder **Aus.** Nachdem die Besprechung beendet wurde, Cortana Sie zu den auf Geräteebene festgelegten Einstellungen zurück.
