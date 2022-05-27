---
title: Ändern von Telefonnummern auf Audiokonferenz Brücke
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Erfahren Sie, welche Schritte erforderlich sind, um Ihrer Konferenzbrücke eine neue Diensttelefonnummer zuzuweisen, um die Abdeckung für Ihre Benutzer zu erweitern.
ms.openlocfilehash: 0433577334dca5f84854ba1cdc14b81e4ec37e63
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674777"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke

Wenn Sie **Audiokonferenz-Lizenzen** erwerben, hosten Microsoft Ihre Audiokonferenzbrücke für Ihre Organisation. Die Audiokonferenzbrücke gibt Einwahltelefonnummern von verschiedenen Orten aus, sodass Besprechungsorganisatoren und Teilnehmer diese verwenden können, um per Telefon an Skype for Business oder Microsoft Teams Besprechungen teilzunehmen.

Zusätzlich zu den Telefonnummern, die Ihrer Konferenzbrücke bereits zugewiesen sind, können Sie [zusätzliche Servicenummern](./getting-service-phone-numbers.md) (gebührenpflichtige und gebührenfreie Telefonnummern, die für Audiokonferenzen verwendet werden) von anderen Standorten abrufen und diese dann der Konferenzbrücke zuweisen, damit Sie die Abdeckung für Ihre Benutzer erweitern können.

> [!NOTE]
> Um eine Rufnummer für ein Konferenzbrücke zuweisen/aufheben können, muss die Rufnummer eine *Servicenummer* sein. Sie können die Art der Nummer anzeigen, die sie ist, indem Sie im Microsoft Teams Admin Center zu **VoIP** >  **Telefon Nummern** navigieren und in der Spalte **"Zahlentyp"** nachschauen. Microsoft 365 oder Office 365 Guthaben für Kommunikationen müssen zuerst eingerichtet werden, damit Benutzer sich über eine gebührenfreie Nummer in die Brücke einwählen können.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Schritte zum Zuweisen einer neuen Servicetelefonnummer zu Ihrer Konferenzbrücke

> [!NOTE]
> Sofern nicht anders angegeben, müssen alle diese Schritte im Microsoft Teams Admin Center ausgeführt werden.

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Schritt 1 - Zuweisen der neuen Telefonnummer zu Ihrer Audiokonferenzbrücke

1. Wechseln Sie im linken Navigationsbereich zu **"VoIP** >  **Telefon Nummern**".

2. Wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie auf **"Bearbeiten"**.

3. Erweitern Sie auf der Seite **"Bearbeiten"** unter **"Zugewiesen an**" die Dropdownliste, und wählen Sie dann **"Konferenzbrücke** > **übernehmen"** aus.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Schritt 2 : Ändern der Standardtelefonnummer Ihrer Konferenzbrücke (optional)

Die Standardtelefonnummer Ihrer Konferenzbrücke definiert die Anrufer-ID, die verwendet wird, wenn ein ausgehender Anruf von einem Teilnehmer oder organisator innerhalb einer Besprechung getätigt wird.

Nur eine gebührenpflichtige Servicenummer kann als Standardnummer für Ihre Konferenzbrücke festgelegt werden. **gebührenfreie Servicenummern können nicht als Standardnummer Ihrer Konferenzbrücke festgelegt werden**. Wenn Sie eine gebührenpflichtige Dienstnummer zuweisen und diese als neue Standardnummer für Ihre Audiokonferenzbrücke festlegen möchten, führen Sie die folgenden Schritte aus:

1. Wechseln Sie im linken Navigationsbereich zu **den Brücken der Besprechungskonferenz** > .

2. Markieren Sie die gebührenpflichtige Dienstnummer, die Sie als Standard konfigurieren möchten.

3. Wählen Sie **Als Standard** aus.

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Schritt 3: Ändern der Standardtelefonnummern, die in den Besprechungseinladungen von Benutzern enthalten sind (optional)

Weitere Informationen finden [Sie unter Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten sind](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> Sie können Telefonnummern auch festlegen, indem Sie sie der *TeamsAudioconferencingpolicy* hinzufügen und die Richtlinie Ihren Benutzern zuweisen. Gebührenpflichtige und gebührenfreie Telefonnummern, die der Richtlinie hinzugefügt wurden, haben Vorrang vor den Telefonnummern, die über den Einstellungsbereich für Audiokonferenzen einzeln für Benutzer festgelegt werden. Wenn der *Teamsaudioconferencingpolicy* keine Telefonnummern hinzugefügt werden, wird die individuell für Benutzer über den Bereich "Audiokonferenzeinstellungen" festgelegte Telefonnummer in Microsoft Teams Besprechungsanfragen angezeigt. [Audiokonferenz Richtlinieneinstellungen für gebührenpflichtige und gebührenfreie Nummern](audio-conferencing-toll-free-numbers-policy.md) enthält weitere Informationen.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Schritt 4: Aktualisieren vorhandener Besprechungseinladungen von Benutzern mithilfe des Besprechungsmigrationsdiensts (optional)

Für die nächsten beiden Schritte müssen Sie mit Windows PowerShell beginnen.

Wenn Sie die Standardtelefonnummern aktualisiert haben, die in den Besprechungseinladungen für einige oder alle Benutzer enthalten sind, können Sie optional Besprechungseinladungen aktualisieren, die bereits an Benutzer in Ihrer Organisation gesendet wurden, bevor ihre Standardtelefonnummern mithilfe des Besprechungsmigrationsdiensts geändert wurden. Weitere Informationen finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

- Führen Sie Meeting Migration Service (MMS) für die Benutzer aus, deren Standardtelefonnummern in Schritt 2 geändert wurden. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Sie können auch den Status der Besprechungsmigration anzeigen. Alle Besprechungen werden neu geplant, sobald keine Vorgänge mit dem Status  *Ausstehend*  oder *In Bearbeitung*  mehr vorhanden sind.

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Schritte zum Aufheben der Zuweisung einer Servicetelefonnummer für eine Konferenzbrücke

Wenn Sie die Zuweisung einer Telefonnummer von einer Konferenzbrücke aufheben, können Benutzer nicht mehr mit dieser Telefonnummer an Besprechungen teilnehmen. Da sich die Telefonnummer ändert, ist es wichtig, alle Benutzer, die über eine Telefonnummer verfügen könnten, als Standardnummer (falls vorhanden) zu aktualisieren und ihre vorhandenen Besprechungseinladungen zu aktualisieren, bevor die Telefonnummer von der Audiokonferenzbrücke nicht zugewiesen wird.

Wenn die Telefonnummer entfernt wird, ohne die Benutzer und ihre Besprechungen zu aktualisieren, könnten ihre vorhandenen Besprechungseinladungen eine Telefonnummer enthalten, die für die Teilnahme an ihren Besprechungen nicht funktioniert.

Für die ersten drei Schritte müssen Sie mit Windows PowerShell beginnen. Wenn Sie wissen möchten, wie dies funktioniert, klicken [Sie auf "Möchten Sie wissen, wie sie mit Windows PowerShell verwalten?"](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Schritt 1: Aktualisieren von Benutzern, deren Telefonnummer nicht zugewiesen werden soll, als eine ihrer Standardnummern

Ersetzen Sie die gebührenpflichtige oder gebührenfreie Standardnummer für alle Benutzer, deren Nummer als Standardnummer nicht zugewiesen werden soll, und beginnen Sie mit der Neuplanung ihrer Besprechungen. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >Sie können auch die standardmäßige gebührenpflichtige oder gebührenfreie Anzahl von Benutzern im Microsoft Teams Admin Center ändern. Dadurch werden ihre Besprechungen jedoch nicht automatisch neu berechnet.

 Weitere Informationen finden Sie unter [Festlegen der in Einladungen enthaltenen Telefonnummern in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) oder [Festlegen der Telefonnummern, die in Einladungen in Skype for Business Online enthalten sind](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > Je nach Größe Ihrer Organisation kann es eine Weile dauern, bis dieser Vorgang abgeschlossen ist.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Schritt 2 - Anzeigen des Status der Besprechungsmigration mit Windows PowerShell

Alle Besprechungen werden neu geplant, sobald keine Vorgänge im Status *"Ausstehend* " oder " *In Bearbeitung"* vorhanden sind.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Weitere Informationen zu Meeting Migration Service finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Schritt 3 - Aufheben der Zuweisung der alten Telefonnummer zur Audiokonferenzbrücke

Verwenden Sie das cmdlet Unregister-CsOnlineDialInConferencingServiceNumber, um die Registrierung einer gebührenpflichtigen oder gebührenfreien Nummer von einer Konferenzbrücke aufzuheben.

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

Hinweis: Führen Sie die folgende PowerShell aus, um die Konferenzbrücke-ID zu finden: Get-CsOnlineDialInConferencingBridge.

   > [!IMPORTANT]
   > Nachdem die Zuweisung einer Telefonnummer zu einer Audiokonferenzbrücke aufgehoben wurde, ist die Telefonnummer nicht mehr für die Teilnahme der Benutzer an neuen oder bestehenden Besprechungen verfügbar.

### <a name="save-time-and-automate"></a>Zeit sparen und automatisieren

Um Zeit zu sparen, indem Sie diesen Prozess automatisieren, können Sie die [Cmdlets Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) oder **Set-CsOnlineDialInConferencingUserDefaultNumber** verwenden.

- Mit dem Cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) können Sie die gebührenpflichtige oder gebührenfreie Standardnummer für spezifische Benutzer ändern.

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
    > Der oben verwendete Speicherort muss mit den Kontaktinformationen der Benutzer übereinstimmen, die im Microsoft 365 Admin Center festgelegt sind.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="the-unassign-button-isnt-available"></a>Die Schaltfläche "Zuweisung aufheben" ist nicht verfügbar.

Sie möchten die Zuweisung einer Nummer aufheben, aber die Schaltfläche ist nicht verfügbar. Wenn Sie mit dem Mauszeiger darauf zeigen, werden Sie mit der folgenden Meldung an den Support weitergeleitet: "Standardnummern oder freigegebene Nummern können von der Brücke nicht aufgehoben werden. Wenden Sie sich an den Support, um die Zuweisung dedizierter gebührenpflichtige Nummern aufzuheben."

Um weitere Informationen zu den Brücke(n) zu erhalten, führen Sie die folgende PowerShell aus:

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Das Ergebnis sollte neben anderen Informationen wie "Identity", "Name" und "Region" auch "DefaultServiceNumber" enthalten.

**Beispiel**: Um die Zuweisung aufzuheben, wird die DefaultServiceNumber "8005551234"

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234
```

## <a name="about-windows-powershell"></a>Informationen zu Windows PowerShell

Mit Windows PowerShell können Sie Benutzer und deren Berechtigungen verwalten. Windows PowerShell können Ihnen dabei helfen, Microsoft 365 oder Office 365 und Skype for Business Online mithilfe eines einzigen Verwaltungspunkts zu verwalten, der Ihre tägliche Arbeit vereinfachen kann, insbesondere wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

- [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell hat viele Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

- [Beste Methoden zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Verwandte Themen

[Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md)
