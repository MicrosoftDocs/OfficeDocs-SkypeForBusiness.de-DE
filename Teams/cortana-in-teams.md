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
description: Erfahren Sie, wie Sie Die Sprachunterstützung von Cortana in Teams verwenden.
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
ms.openlocfilehash: 820689e2bcfa190afefda9d161c787c6be9a7da0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118474"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana-Sprachunterstützung in Teams

> [!Note]
> Cortana-Sprachunterstützung wird nur in mobilen Microsoft Teams iOS- und Android-Apps, Microsoft Teams-Räumen unter Windows und auf Microsoft Teams-Bildschirmen unterstützt, und dies nur für Benutzer in den USA. Sie ist derzeit nicht für GCC-, GCC-High-, DoD-, EDU-Mandanten verfügbar. Die Erweiterung auf weitere Sprachen und Regionen wird im Rahmen zukünftiger Versionen geschehen.

> [!Note]
> Die Sprachunterstützung von Cortana in Microsoft Teams Rooms wird unter Vorschau veröffentlicht. In der Vorschauversion wird Cortana nur in den USA mit der Sprache EN-US auf Geräten unterstützt, auf denen die Mikrofone von Rally angeschlossen sind.

Mithilfe der Sprachunterstützung von Cortana in der mobilen Microsoft Teams-App, in Microsoft Teams-Räumen unter Windows und auf Microsoft Teams-Anzeigegeräten können Benutzer von Microsoft 365 Enterprise Kommunikation, Zusammenarbeit und besprechungsbezogene Aufgaben mithilfe der gesprochenen natürlichen Sprache optimieren. Benutzer können mit Cortana sprechen, indem sie die Mikrofonschaltfläche oben rechts in der mobilen Microsoft Teams-App auswählen oder &#8220;Cortana&#8221; im Microsoft Teams-Raum oder bei Verwendung einer Microsoft Teams-Anzeige sagen. Um schnell und frei und unterwegs eine Verbindung mit seinem Team herzustellen, können Benutzer Abfragen wie &#8220;anrufen Megan&#8221; oder &#8220;eine Nachricht an meine nächste Besprechungssitzung senden&#8221;. Benutzer können auch an Besprechungen teilnehmen, indem &#8220;an meiner nächsten Besprechung teilnehmen&#8221; und sprachunterstützung verwenden, um Dateien zu teilen, ihren Kalender zu überprüfen und vieles mehr. Diese Sprachunterstützungserfahrungen werden mithilfe von [Cortana-Diensten](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) auf Unternehmensqualität geliefert, die den Datenschutz-, Sicherheits- und Compliancezusagen von Office 365 vollständig entsprechen, wie in den [Onlinedienstbedingungen (OST) widergespiegelt.](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

Die Abbildung zeigt das Senden eines Chats mit Cortana auf einem mobilen Gerät.

![eine Abfolge mobiler Bildschirme mit einer Cortana-Chatsitzung](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Administratorsteuerelement und -beschränkungen

Cortana-Sprachunterstützung in Teams wird mithilfe von Diensten übermittelt, die den Datenschutz-, Sicherheits- und Compliancezusagen von Office 365 auf Unternehmensebene vollständig entsprechen, wie in den Onlinedienstbedingungen (OST) widergespiegelt. Das Feature wird standardmäßig für Mandanten aktiviert.

Mandantenadministratoren können mithilfe einer Richtlinie (TeamsCortanaPolicy) steuern, wer in ihrem Mandanten Cortana-Sprachunterstützung in Teams verwenden kann. Diese Richtlinie kann entweder auf Benutzerkonten- oder Mandantenebene festgelegt werden. Administratoren können das Feld CortanaVoiceInvocationMode innerhalb dieses Richtliniensteuerelements verwenden, um zu ermitteln, ob Cortana deaktiviert ist, nur mit Push-Button-Aufruf aktiviert ist oder ob auch ein Aufruf von Wörtern aktiviert ist (gilt für Geräte, die die Funktion unterstützen, z. B. die Microsoft Teams-Anzeige).

Administratoren können die folgenden PowerShell-Cmdlets verwenden, um diese Richtlinie zu verwalten (die Richtlinie ist derzeit im Microsoft Teams Admin Center nicht verfügbar).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Mit dem folgenden Befehl wird z. B. eine neue Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221;, in der die Sprachunterstützung von Cortana in Microsoft Teams deaktiviert ist.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

In diesem Beispiel wird das Aktualisieren einer vorhandenen Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221; und die Aktivierung der Cortana-Sprachunterstützung in Microsoft Teams nur mit dem Aufruf von Schaltflächen veranschaulicht. Benutzer können Cortana aufrufen, indem sie die Cortana-Mikrofonschaltfläche in Teams auswählen. Der Aufruf von &#8220;(&#8221; Von Hey Cortana&#8221; oder &#8220;Cortana&#8221;) wird deaktiviert.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

In diesem Beispiel wird gezeigt, wie Sie die Richtlinie aktualisieren und Die Sprachunterstützung von Cortana sowohl mit der Schaltfläche "Push" als auch "Word-Aufruf aktivieren" aktivieren.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Zum Zeitpunkt der ersten Version für Microsoft 365 Enterprise-Benutzer in den USA in Englisch sind die folgenden Funktionen verfügbar:

- Die mobile Teams-App unterstützt die Aktivierung von Wake Word nicht, wird aber in Zukunft unterstützt.  

- Microsoft Teams-Räume auf Windows- und Microsoft Teams-Anzeigegeräten unterstützen die Aktivierung von Wörtern.

## <a name="user-control"></a>Benutzersteuerelement

Einzelne Benutzer können die Sprachunterstützung von Cortana auf verschiedenen Geräten ausprobieren:

- Wählen Sie die Mikrofonschaltfläche in der mobilen Teams-App aus.

- Wählen Sie die Mikrofonschaltfläche aus, oder sagen Sie "Cortana" in Microsoft Teams Rooms.

- Sagen Sie "Cortana" auf Microsoft Teams-Anzeigegeräten.

Sie können steuern, ob Cortana in Teams für Ihr Gerät aktiviert ist, indem Sie eine Einstellung auf dem Gerät verwenden.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Mobile Microsoft Teams-App oder Microsoft Teams-Anzeige

  1. Öffnen Sie die mobile Teams-App.

  2. Wählen **Sie Einstellungen** Cortana  >  **aus.**

  3. Bewegen Sie den Umschalter **Ein** oder **Aus.**

### <a name="microsoft-teams-display"></a>Anzeigen von Microsoft Teams

  1. Wechseln Sie zum Umgebungsbildschirm (Startbildschirm) der Microsoft Teams-Anzeige.

  2. Wählen Sie den Benutzer avatar und dann **Einstellungen aus.** Wenn Cortana aktiviert ist, sagen Sie "Cortana, wechseln Sie zu Einstellungen".

  3. Bewegen Sie den Umschalter **Ein** oder **Aus.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams-Räume unter Windows

Änderungen auf Geräteebene sind verfügbar, wenn Cortana auf Mandantenebene aktiviert ist. Cortana wird standardmäßig AUS veröffentlicht.

Damit Cortana auf Geräteebene aktiviert werden kann, müssen diese XML-Attribute in der SkypeSettings-XML-Datei hinzugefügt werden:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Änderungen auf Besprechungsebene sind verfügbar, wenn Cortana auf Geräteebene aktiviert ist.

Um die Sprachunterstützung von Cortana während einer Besprechung zu aktivieren, verschieben Sie die Umschalte **Ein** oder **Aus.** Sobald die Besprechung endet, kehrt Cortana zum Einstellungssatz auf Geräteebene zurück.