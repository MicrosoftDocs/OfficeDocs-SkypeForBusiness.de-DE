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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686441"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana-Sprachunterstützung in Teams

> [!Note]
> Cortana-VoIP-Unterstützung wird in Microsoft Teams IOS-und Android-mobilen apps, Microsoft Teams-Räumen unter Windows und auf Microsoft Teams-Displays nur für Benutzer in den Vereinigten Staaten unterstützt. Sie ist derzeit nicht für gcc-, gcc-höchst-, DoD-, edu-Mandanten verfügbar. Die Erweiterung auf weitere Sprachen und Regionen erfolgt in zukünftigen Versionen.

> [!Note]
> Cortana Voice-Unterstützung in Microsoft Teams Rooms wird unter Vorschau veröffentlicht. In der Preview-Version wird Cortana nur in den USA mit der Sprache en-US auf Geräten unterstützt, die Rallye-Mikrofone verbunden haben.

Cortana-VoIP-Unterstützung in der mobilen Teams-APP, in Microsoft Teams-Räumen unter Windows und auf Microsoft Teams-Anzeigegeräten können Microsoft 365 Enterprise-Benutzer die Kommunikation, Zusammenarbeit und Besprechungs bezogene Aufgaben mithilfe der gesprochenen natürlichen Sprache rationalisieren. Benutzer können mit Cortana sprechen, indem Sie die Schaltfläche Mikrofon in der oberen rechten Ecke der mobilen App für Teams auswählen oder indem Sie &#8220;Cortana&#8221; im Microsoft Teams-Chatroom oder bei Verwendung einer Microsoft Teams-Anzeige sagen. Damit Sie schnell und einfach mit Ihrem Team in Kontakt treten können, können Benutzer Abfragen wie &#8220;Megan&#8221; anrufen oder &#8220;eine Nachricht an meine nächste Besprechungs&#8221; senden. Benutzer können auch an Besprechungen teilnehmen, indem Sie &#8220;teilnehmen an meiner nächsten Besprechung&#8221; und die Sprachunterstützung verwenden, um Dateien freizugeben, Ihren Kalender zu überprüfen und vieles mehr. Diese sprach Unterstützungsfunktionen werden mithilfe von [Cortana Enterprise-Services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 entsprechen, wie Sie in den [Online Services-Bedingungen (Ost)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)widergespiegelt werden.

Das Bild zeigt das Senden eines Chats mithilfe von Cortana auf einem mobilen Gerät.

![eine Sequenz von mobilen Bildschirmen mit einer Cortana-Chat-Sitzung](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Administratorsteuerung und Einschränkungen

Cortana-VoIP-Unterstützung in Teams wird mithilfe von Diensten bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 auf Unternehmensebene entsprechen, wie Sie in den Online Services-Bedingungen (Ost) widergespiegelt werden. Das Feature wird standardmäßig für Mandanten aktiviert.

Mandantenadministratoren können steuern, wer in Ihrem Mandanten Cortana-VoIP-Unterstützung in Teams mithilfe einer Richtlinie (TeamsCortanaPolicy) verwenden kann. Diese Richtlinie kann entweder auf Ebene des Benutzerkontos oder auf Mandantenebene eingestellt werden. Administratoren können das CortanaVoiceInvocationMode-Feld in diesem Richtliniensteuerelement verwenden, um zu ermitteln, ob Cortana deaktiviert ist, nur mit nur einem Push-Button-Aufruf aktiviert ist, oder aber auch mit Wake-Word-Aufruf (gilt für Geräte, die es unterstützen, wie die Microsoft Teams-Anzeige).

Administratoren können die folgenden PowerShell-Cmdlets zum Verwalten dieser Richtlinie verwenden (die Richtlinie steht derzeit im Microsoft Teams Admin Center nicht zur Verfügung).

- [Neu – CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

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

Zu dem Zeitpunkt, an dem die erste Version für Microsoft 365 Enterprise-Benutzer in den USA in Englisch verfügbar ist, stehen die folgenden Funktionen zur Verfügung:

- Die Mobile Teams-App unterstützt nicht die Aktivierung von Aktivierungs Word, wird aber in Zukunft unterstützt.  

- Microsoft Teams Rooms auf Anzeigegeräten für Windows und Microsoft Teams unterstützen die Aktivierung von Aktivierungs Word.

## <a name="user-control"></a>Benutzersteuerelement

Einzelne Benutzer können Cortana-Sprachunterstützung auf verschiedenen Geräten ausprobieren:

- Wählen Sie die Schaltfläche Mikrofon in der mobilen Teams-App aus.

- Wählen Sie die Schaltfläche Mikrofon aus, oder sagen Sie "Cortana" in den Microsoft Teams-Räumen.

- Sagen Sie "Cortana" auf den Microsoft Teams-Anzeigegeräten.

Sie können steuern, ob Cortana in Teams für Ihr Gerät aktiviert ist, indem Sie eine Einstellung auf dem Gerät verwenden.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Mobile Teams-APP oder Microsoft Teams-Anzeige

  1. Öffnen Sie die Mobile Teams-app.

  2. Wählen Sie **Einstellungen**  >  **Cortana** aus.

  3. Verschieben Sie die Umschaltfläche **ein** -oder **ausschalten**.

### <a name="microsoft-teams-display"></a>Microsoft Teams-Anzeige

  1. Wechseln Sie zum Bildschirm Ambient (Home) der Microsoft Teams-Anzeige.

  2. Wählen Sie den Avatar des Benutzers aus, und wählen Sie dann **Einstellungen** aus. Wenn Cortana aktiviert ist, sagen Sie "Cortana, wechseln Sie zu Einstellungen."

  3. Verschieben Sie die Umschaltfläche **ein** -oder **ausschalten**.
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams-Räume unter Windows

Änderungen auf Geräteebene sind verfügbar, wenn Cortana auf Mandantenebene aktiviert ist. Cortana wird standardmäßig deaktiviert.

Um Cortana auf Geräteebene zu aktivieren, müssen diese XML-Attribute in der SkypeSettings-XML-Datei hinzugefügt werden:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Änderungen auf Besprechungs Ebene sind verfügbar, wenn Cortana auf Geräteebene aktiviert ist.

Um die Cortana-Sprachunterstützung während einer Besprechung zu aktivieren, verschieben Sie **die Umschaltfläche** ein-oder **ausschalten**. Sobald die Besprechung beendet ist, kehrt Cortana zu den Einstellungen für die Geräteebene zurück.
