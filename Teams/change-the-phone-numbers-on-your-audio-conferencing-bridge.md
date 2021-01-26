---
title: Ändern von Telefonnummern für die Audiokonferenzbrücke
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Hier erfahren Sie die Schritte zum Zuweisen einer neuen Servicetelefonnummer zu Ihrer Konferenzbrücke, um die Abdeckung für Ihre Benutzer zu erweitern.
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918751"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke

Wenn Sie Lizenzen **für Audiokonferenzen** erwerben, hostt Microsoft Ihre Audiokonferenzbrücke für Ihre Organisation. Über die Audiokonferenzbrücke werden Einwahltelefonnummern von verschiedenen Standorten aus verteilt, sodass Besprechungsorganisatoren und -teilnehmer über ein Telefon an Skype for Business- oder Microsoft Teams-Besprechungen teilnehmen können.
  
Zusätzlich zu den Telefonnummern, die Ihrer Konferenzbrücke bereits [](/microsoftteams/getting-service-phone-numbers) zugewiesen sind, können Sie von anderen Standorten zusätzliche Servicenummern (gebührenpflichtige und gebührenfreie Telefonnummern für Audiokonferenzen) erhalten und diese dann der Konferenzbrücke zuweisen, damit Sie die Abdeckung für Ihre Benutzer erweitern können.
  
> [!NOTE]
> Um eine Rufnummer für ein Konferenzbrücke zuweisen/aufheben können, muss die Rufnummer eine *Servicenummer* sein. Sie können den Typ der Nummer sehen, indem Sie im Microsoft Teams Admin Center zu den Sprachtelefonnummern navigieren und in der Spalte "Zahlentyp"  >   nachschauen.  Microsoft 365- oder Office 365-Guthaben für Kommunikationen muss zuerst eingerichtet sein, damit sich Benutzer unter einer gebührenfreien Nummer in die Brücke einwählen können.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Schritte zum Zuweisen einer neuen Servicetelefonnummer zu Ihrer Konferenzbrücke

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Schritt 1 - Zuweisen der neuen Telefonnummer zu Ihrer Audiokonferenzbrücke

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **"Voice**  >  **phone numbers".**

2. Wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie auf **"Bearbeiten".**

3. Erweitern Sie **auf der Seite "Bearbeiten"** unter **"Zugewiesen an"** das Dropdown, und wählen Sie **"Konferenzbrücke**  >  **übernehmen" aus.**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Schritt 2 – Ändern der Standardtelefonnummer ihrer Konferenzbrücke (optional)

Die Standardtelefonnummer Ihrer Konferenzbrücke definiert die Anrufer-ID, die verwendet wird, wenn ein ausgehender Anruf von einem Teilnehmer oder Organisator innerhalb einer Besprechung eingestellt wird.

Es kann nur eine gebührenpflichtige Servicenummer als Standardnummer für Ihre Konferenzbrücke festgelegt werden. **gebührenfreie Servicenummern können nicht** als Standardnummer Ihrer Konferenzbrücke festgelegt werden. Wenn Sie eine gebührenpflichtige Servicenummer zuweisen und diese als neue Standardnummer für Ihre Audiokonferenzbrücke festlegen möchten, führen Sie die folgenden Schritte aus:

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu den **Brücken** der  >  **Konferenzkonferenz für Besprechungen.**

2. Markieren Sie die gebührenpflichtige Servicenummer, die Sie als Standard konfigurieren möchten.

3. Wählen Sie **Als Standard** aus.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Schritt 3 – Ändern der Standardtelefonnummern, die in den Besprechungseinrufen von Benutzern enthalten sind (optional)

Die Standardtelefonnummern eines Benutzers sind die Nummern, die in den Besprechungseinrufen enthalten sind, wenn er eine Besprechung plant. Weitere Informationen, z. B. wie die Standardtelefonnummern neuen Benutzern zugewiesen werden, finden Sie unter "Festlegen der Telefonnummern, die in Einladungen [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) enthalten sind" oder "Festlegen der Telefonnummern, die in Einladungen in Skype for Business [Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)enthalten sind".

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich **zu** "Benutzer", und klicken Sie auf den Anzeigenamen des gewünschten Benutzers in der Liste.

2. Klicken Sie **neben Audiokonferenzen** auf **"Bearbeiten".**

3. Wählen Sie unter **"Gebührenpflichtige Nummer" oder "Gebührenfreie Nummer"** die Nummer aus der Dropdownliste aus, und klicken Sie auf  "Übernehmen". 

Nachdem die Änderungen übernommen wurden, werden die neuen Standardtelefonnummern in die Besprechungseinrufe der Organisatoren aufgenommen, wenn sie das nächste Mal eine neue Besprechung planen.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Schritt 4 – Aktualisieren vorhandener Besprechungsteilnehmer von Benutzern mithilfe des Meeting Migration Service (optional)

Für die nächsten beiden Schritte müssen Sie mit der Windows PowerShell.
  
Wenn Sie die Standardtelefonnummern aktualisiert haben, die in den Besprechungseinrufen für einige oder alle Benutzer enthalten sind, können Sie optional Besprechungseinrufe aktualisieren, die bereits vor der Änderung der Standardtelefonnummern mithilfe des Meeting Migration Service an Benutzer in Ihrer Organisation gesendet wurden. Weitere Informationen finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Führen Sie Meeting Migration Service (MMS) für die Benutzer aus, deren Standardtelefonnummern in Schritt 2 geändert wurden. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Sie können auch den Status der Besprechungsmigration anzeigen. Alle Besprechungen werden neu geplant, sobald keine Vorgänge mit dem Status  *Ausstehend*  oder *In Bearbeitung*  mehr vorhanden sind.

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Schritte zum Aufheben der Zuweisung einer Servicetelefonnummer für eine Konferenzbrücke


Wenn Sie die Telefonnummer einer Konferenzbrücke zuweisen, können die Benutzer nicht mehr an Besprechungen teilnehmen, die diese Telefonnummer verwenden. Da sich die Telefonnummer ändert, ist es wichtig, alle Benutzer zu aktualisieren, die eine Telefonnummer als Standardnummer haben könnten (sofern vorhanden) und ihre vorhandenen Besprechungseinrufe zu aktualisieren, bevor die Telefonnummer von der Audiokonferenzbrücke entfernt wird.

Wenn die Telefonnummer entfernt wird, ohne die Benutzer und ihre Besprechungen zu aktualisieren, können die vorhandenen Besprechungsteilnehmer eine Telefonnummer enthalten, die für die Teilnahme an besprechungen nicht mehr funktioniert.

Für die ersten drei Schritte müssen Sie mit der Windows PowerShell. Wenn Sie wissen möchten, wie Sie dazu vor gehen, klicken Sie auf "Wissen, [wie sie mit ihren Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Schritt 1: Aktualisieren von Benutzern, deren Telefonnummer als Standardnummer nicht zugewiesen werden soll

Ersetzen Sie die gebührenpflichtige oder gebührenfreie Standardnummer für alle Benutzer, deren Nummer als Standardnummer nicht zugewiesen werden soll, und beginnen Sie mit dem Neuplanen ihrer Besprechungen. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Sie können auch die gebührenpflichtige oder gebührenfreie Standardnummer von Benutzern im Microsoft Teams Admin Center ändern. Dadurch werden ihre Besprechungen jedoch nicht automatisch neu berechnet. 
 
 Weitere Informationen finden Sie unter "Festlegen der in Einladungen [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) enthaltenen Telefonnummern" oder "Festlegen der Telefonnummern, die in Einladungen in Skype for Business Online enthalten [sind".](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > Je nach Größe Ihrer Organisation kann es eine Weile dauern, bis dieser Vorgang abgeschlossen ist.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Schritt 2 - Anzeigen des Status der Besprechungsmigration mit Windows PowerShell

Alle Besprechungen werden neu geplant, sobald keine Vorgänge im Status *"Ausstehend"* oder "In *Bearbeitung"* mehr ausgeführt werden.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Weitere Informationen zu Meeting Migration Service finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Schritt 3 - Aufheben der Zuweisung der alten Telefonnummer zur Audiokonferenzbrücke

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

2. Wenn es sich bei der Telefonnummer um eine gebührenfreie Nummer handelt, wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie auf **"Los".** Wenn es sich bei der Telefonnummer [](https://go.microsoft.com/fwlink/?linkid=2091806) um eine gebührenpflichtige Nummer handelt, wenden Sie sich bitte an den Microsoft-Support, damit die Telefonnummer nicht zugewiesen wird.

3. Wenn es sich bei der Telefonnummer um eine gebührenfreie Nummer handelt, klicken Sie im **Bestätigungsfenster** auf "Ja".

   > [!IMPORTANT]
   > Nachdem die Zuweisung einer Telefonnummer zu einer Audiokonferenzbrücke aufgehoben wurde, ist die Telefonnummer nicht mehr für die Teilnahme der Benutzer an neuen oder bestehenden Besprechungen verfügbar.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>So überprüfen Sie, ob Windows PowerShell bereit ist

 Mit diesen Schritten wird überprüft, ob Sie Windows PowerShell 3.0 oder höher ausführen.

1. Geben Sie im **Menü Start** > **Windows PowerShell** ein.

2. Geben Sie _Get-Host_ im **Windows PowerShell** -Fenster ein, um die Version zu überprüfen.

3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) zum Herunterladen und Aktualisieren von Windows PowerShell Version 4.0.
Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.

4. Sie müssen auch das Windows PowerShell für Skype for Business Online installieren, mit dem Sie eine Remote-Windows PowerShell erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul wird nur auf 64-Bit-Computern unterstützt und kann aus dem Microsoft Download Center unter [Windows PowerShell Module für Skype for Business Online heruntergeladen werden.](https://go.microsoft.com/fwlink/?LinkId=294688)
Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.

Weitere Informationen finden Sie unter "Verbinden mit allen [Microsoft 365- oder Office 365-Diensten in](https://technet.microsoft.com/library/dn568015.aspx)einem einzigen Windows PowerShell".

### <a name="to-start-windows-powershell"></a>So starten Sie Windows PowerShell

 **Starten einer Windows PowerShell-Sitzung**

1. Vom **Start Menu** > **Windows PowerShell**.

2. Stellen  Sie Windows PowerShell A0 eine Verbindung mit Microsoft 365 oder Office 365 herstellen, indem Sie dies ausführen:

> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
>
> Wenn Sie die neueste öffentliche Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie Skype for Business Online Connector nicht installieren.

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
Weitere Informationen zum Starten von Windows PowerShell finden Sie unter "Herstellen einer Verbindung mit allen [Microsoft 365- oder Office 365-Diensten in](https://technet.microsoft.com/library/dn568015.aspx) einem einzigen Windows PowerShell-Fenster" oder "Herstellen einer Verbindung mit Skype for Business Online mithilfe von [Windows PowerShell".](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)

### <a name="save-time-and-automate"></a>Zeit sparen und Automatisieren

Um Zeit zu sparen, indem Sie diesen Prozess automatisieren, können Sie die [Cmdlets "Set-CsOnlineDialInConferencingUser"](https://go.microsoft.com/fwlink/?LinkId=617688) oder **"Set-CsOnlineDialInConferencingUserDefaultNumber"** verwenden.

- Mit dem Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) können Sie die gebührenpflichtige oder gebührenfreie Standardnummer für spezifische Benutzer ändern.

  - Führen Sie Folgendes aus, um die gebührenfreie Standardnummer für einen Benutzer zu ändern:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Ändern Sie mit dem Cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** die gebührenpflichtige oder gebührenfreie Nummer für Benutzer auf Basis ihrer ursprünglichen Standardnummer oder ihres Standorts.

    > [!NOTE]
    > Die BridgeID finden Sie mithilfe von **Get-CsOnlineDialInConferencingBridge**.

  - So ändern Sie die gebührenpflichtige Standardnummer für alle Benutzer bis auf einen in 8005551234:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Führen Sie Folgendes aus, um die gebührenfreie Standardnummer aller Benutzer mit der gebührenfreien Standardnummer 8005551234 in 8005551239 zu ändern und die Besprechungen der Benutzer automatisch neu zu planen:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Führen Sie Folgendes aus, um die gebührenfreie Standardnummer aller Benutzer in den USA in 8005551234 zu ändern und ihre Besprechungen automatisch neu zu planen:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > Der oben verwendete Standort muss mit den Kontaktinformationen der Benutzer übereinstimmen, die im Microsoft 365 Admin Center festgelegt sind.

## <a name="troubleshooting"></a>Problembehandlung

**Schaltfläche "Zuweisen" ist nicht verfügbar**

Sie möchten die Zuweisen einer Nummer wieder aufnehmen, die Schaltfläche ist jedoch nicht verfügbar. Wenn Sie mit der Maus darüber fahren, werden Sie umgeleitet, um sich mit der folgenden Meldung an den Support zu wenden: "Standardnummern oder freigegebene Nummern können nicht von der Brücke entfernt _werden. Wenden Sie sich an den Support, um die Zuzuweisen von dedizierten gebührenpflichtigen Nummern auf den 1._

Führen Sie die folgende Powershell aus, um weitere Informationen zu den Bridge(en) zu erhalten:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Das Ergebnis sollte, abgesehen von anderen Informationen wie "Identity", "Name" und "Region", auch die "DefaultServiceNumber" enthalten.

**Beispiel:** Zum Unzuweisen der DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Informationen zu Windows PowerShell

Mit Windows PowerShell können Sie Benutzer und deren Berechtigungen verwalten. Windows PowerShell können Ihnen helfen, Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Administrationspunkt zu verwalten, der Ihre tägliche Arbeit vereinfachen kann, insbesondere, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell hat gegenüber der ausschließlichen Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Die besten Methoden zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Verwandte Themen
[Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md)
