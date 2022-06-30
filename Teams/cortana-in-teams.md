---
title: Cortana-Sprachunterstützung in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Erfahren Sie, wie Sie die Cortana-Sprachunterstützung mit Teams verwenden.
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3c4ff65fb87bed077e1020764382314d5d15c62
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562434"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana-Sprachunterstützung in Teams

> [!NOTE]
> Cortana-Sprachunterstützung wird in mobilen Microsoft Teams-Apps für iOS und Android sowie in Microsoft Teams-Displays für Benutzer im USA, Großbritannien, Kanada, Indien und Australien unterstützt. Microsoft Teams-Räume unter Windows wird nur für Geräte unterstützt, deren Gebietsschema auf "en-us" festgelegt ist. Cortana-Sprachunterstützung ist derzeit für GCC-, GCC-High-, DoD- und Nicht-US EDU-Mandanten nicht verfügbar. Cortana-Sprachunterstützung in der mobilen Teams-App ist jetzt für EDU-Kunden in en-US verfügbar. Die Erweiterung auf weitere Sprachen und Regionen erfolgt im Rahmen zukünftiger Versionen.

Cortana-Sprachunterstützung in der mobilen Teams-App, auf Microsoft Teams-Räume unter Windows und auf Microsoft Teams-Anzeigegeräten ermöglicht es Microsoft 365 Enterprise Benutzern, Kommunikation, Zusammenarbeit und Besprechungsaufgaben mithilfe gesprochener natürlicher Sprache zu optimieren. Benutzer können mit Cortana sprechen, indem sie die Mikrofonschaltfläche oben rechts in der mobilen Teams-App auswählen oder "Cortana" im Microsoft Teams-Raum oder bei Verwendung einer Microsoft Teams-Anzeige sagen. Um sich schnell freihändig mit ihrem Team in Verbindung zu setzen, können Benutzer unterwegs Abfragen wie "Megan anrufen" oder "Eine Nachricht an meine nächste Besprechung senden" sagen. Benutzer können auch an Besprechungen teilnehmen, indem sie "an meiner nächsten Besprechung teilnehmen" sagen und sprachunterstützung verwenden, um Dateien freizugeben, ihren Kalender zu überprüfen und vieles mehr. Diese Sprachunterstützungsfunktionen werden mithilfe von [Diensten auf Unternehmensniveau von Cortana](/microsoft-365/admin/misc/cortana-integration) bereitgestellt, die den Datenschutz-, Sicherheits- und Complianceversprechen von Office 365 vollständig entsprechen, wie in den [Onlinedienstbedingungen (ONLINE Services Terms, OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true) widergespiegelt.

## <a name="admin-control-and-limitations"></a>Admin Kontrolle und Einschränkungen

Cortana-Sprachunterstützung in Teams wird mithilfe von Diensten bereitgestellt, die den in den Onlinedienstbedingungen (ONLINE Services Terms, OST) angegebenen Office 365 Zusagen für Datenschutz, Sicherheit und Compliance auf Unternehmensebene vollständig entsprechen. Das Feature ist standardmäßig für Mandanten aktiviert.

Mandantenadministratoren können mithilfe einer Richtlinie (TeamsCortanaPolicy) steuern, wer in ihrem Mandanten cortana-Sprachunterstützung in Teams verwenden kann. Diese Richtlinie wird entweder auf Benutzerkonto- oder Mandantenebene festgelegt. Administratoren können das Feld "CortanaVoiceInvocationMode" innerhalb dieses Richtliniensteuerelements verwenden, um zu bestimmen, ob Cortana deaktiviert, nur mit Aufruf per Knopfdruck oder auch mit Aktivierungswortaufruf aktiviert ist (gilt für Geräte, die es unterstützen, z. B. die Microsoft Teams-Anzeige).

Administratoren können die folgenden PowerShell-Cmdlets verwenden, um diese Richtlinie zu verwalten (die Richtlinie ist derzeit im Microsoft Teams Admin Center nicht verfügbar).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Der folgende Befehl erstellt beispielsweise eine neue Richtlinie mit dem Namen "EmployeeCortanaPolicy", bei der die Cortana-Sprachunterstützung in Microsoft Teams deaktiviert ist.

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Dieses Beispiel zeigt das Aktualisieren einer vorhandenen Richtlinie mit dem Namen "EmployeeCortanaPolicy" und das Aktivieren der Cortana-Sprachunterstützung in Microsoft Teams nur mit Aufruf per Knopfdruck. Benutzer können Cortana aufrufen, indem sie die Cortana-Mikrofonschaltfläche in Teams auswählen. Der Aktivierungswortaufruf ("Hey Cortana" oder "Cortana") wird deaktiviert.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

In diesem Beispiel wird gezeigt, wie Die Richtlinie aktualisiert und die Cortana-Sprachunterstützung sowohl mit einem Tastendruck als auch mit dem Reaktivieren des Wortaufrufs aktiviert wird.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Zum Zeitpunkt der ersten Veröffentlichung für Microsoft 365 Enterprise Benutzer in den USA in Englisch stehen folgende Funktionen zur Verfügung:

- Die mobile Teams-App unterstützt die Aktivierung von Wörtern nicht, wird aber in Zukunft unterstützt.

- Microsoft Teams-Räume auf Windows- und Microsoft Teams-Anzeigegeräten unterstützt die Aktivierung von Wörtern.

## <a name="user-control"></a>Benutzersteuerelement

Einzelne Benutzer können cortana-Sprachunterstützung auf verschiedenen Geräten ausprobieren:

- Wählen Sie die Mikrofonschaltfläche in der mobilen Teams-App aus.

- Wählen Sie die Mikrofontaste aus, oder sagen Sie in Microsoft Teams-Räume "Cortana".

- Sagen Sie "Cortana" auf Microsoft Teams zeigt Geräte an.

Sie können mithilfe einer Einstellung auf dem Gerät steuern, ob Cortana in Teams für Ihr Gerät aktiviert ist.

![zeigt die Entwicklung mobiler Fenster an, wenn Sie Cortana aktivieren.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams-Räume unter Windows

Änderungen auf Geräteebene sind nur verfügbar, wenn Cortana auf Mandantenebene aktiviert ist.

Auf Geräteebene können Sie Cortana für die Verwendung auf zwei verschiedene Arten konfigurieren. Sie können beide Optionen oder beides gleichzeitig aktivieren:

- Durch Tippen auf ein Mikrofon, das Cortana Push genannt wird _, um zu sprechen_
- Indem Sie "Hey, Cortana" sagen, was _als Cortana-Sprachaktivierung_ bezeichnet wird

Cortana _Push to talk_ ist standardmäßig aktiviert, wenn Ihr Raum mit einer der folgenden Sprachen eingerichtet ist: en-au (Australien), en-ca (Kanada), en-gb (Vereinigtes Königreich), en-in (Indien), en-us (USA). [Weitere Informationen.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Das Cortana-Symbol verschiebt die Schaltfläche _"Präsentieren_ " unter dem Menü _"Mehr..._ " in Ihrer Teams-Raumkonsole. Verwenden Sie PowerShell _, um Cortana Push zum Sprechen zu_ deaktivieren. [Weitere Informationen.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Um die _Cortana-Sprachaktivierung_ zu aktivieren, müssen die folgenden Bedingungen erfüllt sein:

- Ein cortana-zertifiziertes Gerät muss mit Ihrem Teams-Raum verbunden sein. Eine Liste der zertifizierten Geräte finden Sie am Ende dieses Artikels.
- Der Teams-Raum muss mit einer der folgenden Sprachen eingerichtet sein: en-au (Australien), en-ca (Kanada), en-gb (Vereinigtes Königreich), en-in (Indien), en-us (USA). Weitere Sprachen sind zu einem späteren Zeitpunkt verfügbar.
- Eine der folgenden Konfigurationsänderungen muss vorgenommen werden:
  - aktivieren Sie das Feature im Teams Admin Center [Weitere Informationen.](/microsoftteams/rooms/rooms-manage)
  - Fügen Sie der SkypeSettings-XML-Datei das folgende XML-Attribut hinzu:

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

Auf Besprechungsebene ist das Vornehmen von Änderungen nur verfügbar, wenn die _Cortana-Sprachaktivierung_ auf Geräteebene aktiviert ist.  Um die _Cortana-Sprachaktivierung_ während einer Besprechung zu aktivieren, schalten Sie die Umschaltfläche **ein** oder **aus** , um sie zu deaktivieren. Sobald die Besprechung beendet ist, kehrt Cortana zu den einstellungen auf Geräteebene zurück.

Änderungen auf Besprechungsebene sind verfügbar, wenn Cortana auf Geräteebene aktiviert ist.

Um die Cortana-Sprachaktivierung während einer Besprechung zu aktivieren, schalten Sie den Umschalter **ein** oder **aus**. Sobald die Besprechung beendet ist, kehrt Cortana zu den einstellungen auf Geräteebene zurück.

## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana-zertifizierte Geräte für Teams-Räume

Die _Cortana-Sprachaktivierung_ kann aktiviert werden, wenn Sie einen Lenovo Hub 500 verwenden oder wenn Eines der folgenden Geräte mit Ihrem Raum verbunden ist:

- Jabra Panacast 50
- Rallyemikrofone
- Bose Video Bar VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech
