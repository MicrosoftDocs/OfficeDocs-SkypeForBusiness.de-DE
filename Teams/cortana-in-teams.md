---
title: Cortana Sprachunterstützung in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 'Erfahren Sie, wie Cortana-Sprachunterstützung bei Teams'
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
---

# <a name="cortana-voice-assistance-in-teams"></a>Cortana Sprachunterstützung in Teams

> [!Note]
> Cortana Sprachunterstützung wird in mobilen Microsoft Teams-Apps für iOS und Android und Microsoft Teams-Anzeigen für Benutzer in den USA, Großbritannien, Kanada, Indien und Australien unterstützt. Microsoft Teams-Räume auf Windows wird nur für Geräte unterstützt, für die das Locale auf "en-us" festgelegt ist. Cortana-Sprachunterstützung ist derzeit für Mandanten von GCC, GCC-High, DoD und nicht in den USA verfügbaren EDU-Mandanten nicht verfügbar. Cortana Sprachunterstützung in der mobilen Teams-App ist jetzt für EDU-Kunden in en-US verfügbar. Die Erweiterung auf weitere Sprachen und Regionen wird im Rahmen zukünftiger Versionen sein.


Cortana Sprachunterstützung in der mobilen Teams-App Microsoft Teams-Räume auf Windows-Geräten und auf Microsoft Teams-Anzeigegeräten Microsoft 365 Enterprise  benutzer zum Optimieren der Kommunikation, Zusammenarbeit und Besprechung von Aufgaben in gesprochener natürlicher Sprache. Benutzer können mit Cortana sprechen, indem sie die Mikrofonschaltfläche auswählen, die sich oben rechts in der mobilen Teams-App befindet, oder indem sie "Cortana" im Microsoft Teams Room oder bei Verwendung einer Microsoft Teams sagen. Wenn Sie schnell die Verbindung zu ihrem Team ohne Die Hand nehmen möchten und unterwegs sind, können Benutzer Abfragen wie "Megan anrufen" oder "Eine Nachricht an meine nächste Besprechung senden" sagen. Benutzer können an Besprechungen teilnehmen, indem sie "An meiner nächsten Besprechung teilnehmen" sagen und mithilfe von Sprachunterstützung Dateien freigeben, ihren Kalender überprüfen und vieles mehr. Diese Sprachunterstützungserfahrungen werden [mithilfe von Cortana-Diensten](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) auf Unternehmensklasse übermittelt, die gemäß den Onlinedienstbedingungen [(OST](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) vollständig den Datenschutz-, Sicherheits- und Compliance-Zusagen von Office 365 entsprechen.

## <a name="admin-control-and-limitations"></a>Administratorkontrolle und -beschränkungen

Cortana Sprachunterstützung in Teams wird mithilfe von Diensten übermittelt, die gemäß den Bedingungen für Onlinedienste (OST) in vollem Umfang den Zusagen auf Office 365 Unternehmensebene hinsichtlich Datenschutz, Sicherheit und Compliance entsprechen. Das Feature wird für Mandanten standardmäßig aktiviert.

Mandantenadministratoren können mithilfe einer Richtlinie (TeamsCortanaPolicy) steuern, wer in ihrem Mandanten Cortana Sprachunterstützung in Teams verwenden kann. Diese Richtlinie wird entweder auf Benutzerkonto- oder Mandantenebene festgelegt. Administratoren können das Feld CortanaVoiceInvocationMode innerhalb dieses Richtliniensteuerelements verwenden, um festzustellen, ob Cortana deaktiviert ist, ob es nur über den Aufruf von Schaltflächen oder auch über den Reaktivierungsaufruf von Wörtern aktiviert ist (gilt für Geräte, die dies unterstützen, z. B. die Microsoft Teams-Anzeige).

Administratoren können die folgenden PowerShell-Cmdlets verwenden, um diese Richtlinie zu verwalten (die Richtlinie ist derzeit im Microsoft Teams Admin Center nicht verfügbar).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Mit dem folgenden Befehl wird z. B. eine neue Richtlinie mit dem Namen "EmployeeCortanaPolicy" erstellt, Cortana Sprachunterstützung in Microsoft Teams deaktiviert ist.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Dieses Beispiel zeigt das Aktualisieren einer vorhandenen Richtlinie mit dem Namen "EmployeeCortanaPolicy" und das Aktivieren Cortana Sprachunterstützung in Microsoft Teams nur mit dem Aufruf über die Schaltfläche. Benutzer können Ihr Mikrofon Cortana, indem sie die Schaltfläche Cortana Mikrofons im Teams. Der Aufruf von Reaktivierungszeichen ("Hey Cortana" oder "Cortana") wird deaktiviert.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Dieses Beispiel zeigt die Aktualisierung der Richtlinie und Cortana Sprachunterstützung durch Drücken und Reaktivierung des Worts.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Zum Zeitpunkt der ersten Version für Microsoft 365 Enterprise Benutzer in den USA in Englisch sind die folgenden Funktionen verfügbar:

- Die Teams mobilen App unterstützt nicht die Aktivierung von Reaktivierungsworten, wird aber in Zukunft unterstützt.  

- Microsoft Teams-Räume auf Windows- und Microsoft Teams-Anzeigegeräten unterstützen die Aktivierung von Reaktivierungsworten.

## <a name="user-control"></a>Benutzersteuerelement

Einzelne Benutzer können versuchen, Cortana Sprachunterstützung auf verschiedenen Geräten zu erhalten:

- Wählen Sie in der mobilen Teams Mikrofonschaltfläche aus.

- Wählen Sie die Mikrofonschaltfläche aus, oder sagen Cortana Mikrofon", Microsoft Teams-Räume.

- Sagen Sie "Cortana" auf Microsoft Teams-Geräten.

Sie können steuern, Cortana in Teams Gerät aktiviert ist, indem Sie eine Einstellung auf dem Gerät verwenden.

![zeigt die Entwicklung mobiler Fenster an, wenn Sie Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams-Räume auf Windows

Änderungen auf Geräteebene sind nur verfügbar, Cortana auf Mandantenebene aktiviert ist. 

Auf Geräteebene können Sie die Cortana für die Verwendung auf zwei verschiedene Arten konfigurieren. Sie können beide Optionen oder beide gleichzeitig aktivieren: 
- Durch Tippen auf ein Mikrofon, das als "Cortana _" bezeichnet wird, um zu sprechen_
- Indem Sie "Hey, Cortana" sagen, das Cortana _Sprachaktivierung genannt wird_

Cortana _Push to talk_ ist standardmäßig aktiviert, wenn Ihr Raum mit einer der folgenden Sprachen eingerichtet ist: en-au (Australien), en-ca (Canada), en-gb (United Kingdom), en-in (India), en-us (Usa). [Weitere Informationen.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana Symbol wird die Schaltfläche _Präsentieren unter dem_ Symbol Mehr _..._ in ihrer Teams Raumkonsole. Verwenden Sie PowerShell Cortana _um push to talk zu deaktivieren_.[ Weitere Informationen.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Zum Aktivieren Cortana _Sprachaktivierung_ müssen die folgenden Bedingungen erfüllt sein:
- ein Cortana Gerät muss mit Ihrem Raum Teams sein. Eine Liste der zertifizierten Geräte finden Sie am Ende dieses Artikels.
- der Teams Room muss mit einer der folgenden Sprachen eingerichtet werden: en-au (Australien), en-ca (Kanada), en-gb (United Kingdom), en-in (Indien), en-us (Vereinigte Staaten). Weitere Sprachen werden zu einem späteren Zeitpunkt zur Verfügung stehen.
- muss eine der folgenden Konfigurationsänderungen vorgenommen werden:
  - aktivieren Sie das Feature im Teams Admin Center [Weitere Informationen.](/microsoftteams/rooms/rooms-manage)
  - Fügen Sie der SKYPESettings-XML-Datei das folgende XML-Attribut hinzu:

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
Auf Besprechungsebene sind Änderungen nur verfügbar, Cortana _die Sprachaktivierung_ auf Geräteebene aktiviert ist.  Um die Cortana _Sprachaktivierung während_ einer Besprechung zu aktivieren, bewegen Sie den Umschalter auf **Ein** oder **Aus**, um die Sprachaktivierung zu deaktivieren. Sobald die Besprechung beendet ist, Cortana sie zu den auf Geräteebene festgelegten Einstellungen zurück.


Das Vornehmen von Änderungen auf Besprechungsebene ist verfügbar, Cortana auf Geräteebene aktiviert ist.

Um die Cortana _während einer Besprechung_ zu aktivieren, bewegen Sie den Umschalter **auf Ein** oder **Aus**. Sobald die Besprechung beendet ist, Cortana sie zu den auf Geräteebene festgelegten Einstellungen zurück.


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana Geräte für die Teams-Räume
Cortana _Sprachaktivierung_ kann aktiviert werden, wenn Sie ein Lenovo Hub 500 verwenden oder wenn eines dieser Geräte mit Ihrem Raum verbunden ist:
- Jabra Ausschnur 50 
- Mikrofone aus Mikrofonen von Mikrofonen aus Mikrofonen
- Bose Video Bar VB1

