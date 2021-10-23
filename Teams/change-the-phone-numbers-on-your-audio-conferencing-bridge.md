---
title: Ändern der Telefonnummern auf der Audiokonferenzbrücke
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Erfahren Sie die Schritte zum Zuweisen einer neuen Servicetelefonnummer zu Ihrer Konferenzbrücke, um die Abdeckung für Ihre Benutzer zu erweitern.
ms.openlocfilehash: f39a963759e768f4fab70d2a06e6d90b480699e0
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536716"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke

Wenn Sie **Lizenzen für Audiokonferenzen erwerben,** hostigt Microsoft Ihre Audiokonferenzbrücke für Ihre Organisation. Die Audiokonferenzbrücke gibt Einwahltelefonnummern von verschiedenen Standorten aus, damit Sie von den Besprechungsorganisatoren und -teilnehmern über ein Telefon an Skype for Business- oder Microsoft Teams-Besprechungen teilnehmen können.
  
Zusätzlich zu den Telefonnummern, die Ihrer Konferenzbrücke bereits [](./getting-service-phone-numbers.md) zugewiesen sind, können Sie zusätzliche Servicenummern (gebührenpflichtige und gebührenfreie Telefonnummern für Audiokonferenzen) von anderen Standorten erhalten und diese dann der Konferenzbrücke zuweisen, damit Sie die Abdeckung für Ihre Benutzer erweitern können.
  
> [!NOTE]
> Um eine Rufnummer für ein Konferenzbrücke zuweisen/aufheben können, muss die Rufnummer eine *Servicenummer* sein. Sie können den Typ Telefon der Nummer sehen, indem Sie im Microsoft Teams Admin Center zu Sprachanrufnummern navigieren und in der Spalte  >   **Zahlentyp** nachschauen. Microsoft 365 oder Office 365 Guthaben für Kommunikationen muss zuerst eingerichtet werden, damit sich Benutzer unter einer gebührenfreien Nummer in die Brücke einwählen können.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Schritte zum Zuweisen einer neuen Servicetelefonnummer zu Ihrer Konferenzbrücke

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Schritt 1 - Zuweisen der neuen Telefonnummer zu Ihrer Audiokonferenzbrücke

 **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich **zu**  >  **Sprachanrufnummern Telefon .**

2. Wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**.

3. Erweitern Sie **auf der** Seite Bearbeiten unter **Zugewiesen an** die Dropdownliste, und wählen Sie **Konferenzbrücke Übernehmen**  >  **aus.**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Schritt 2 – Ändern der Standardtelefonnummer für Ihre Konferenzbrücke (optional)

Die Standardtelefonnummer Ihrer Konferenzbrücke definiert die Anrufer-ID, die verwendet wird, wenn ein ausgehender Anruf von einem Teilnehmer oder Organisator innerhalb einer Besprechung abgestellt wird.

Es kann nur eine gebührenpflichtige Servicenummer als Standardnummer für Ihre Konferenzbrücke festgelegt werden. **gebührenfreie Servicenummern können nicht** als Standardnummer für Ihre Konferenzbrücke festgelegt werden. Wenn Sie eine gebührenpflichtige Servicenummer zuweisen und diese als neue Standardnummer für Ihre Audiokonferenzbrücke festlegen möchten, führen Sie die folgenden Schritte aus:

 **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **Konferenzbrücken**  >  **für Besprechungen.**

2. Markieren Sie die gebührenpflichtige Servicenummer, die Sie als Standard konfigurieren möchten.

3. Wählen Sie **Als Standard** aus.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Schritt 3 – Ändern der Standardtelefonnummern, die in den Besprechungseinrufen von Benutzern enthalten sind (optional)

Bei den Standardtelefonnummern eines Benutzers handelt es sich um die Nummern, die beim Planen einer Besprechung in den Besprechungseinrufen enthalten sind. Weitere Informationen, einschließlich der Zugewiesene Standardtelefonnummern für neue Benutzer, finden Sie unter Festlegen der Telefonnummern für Einladungen [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) oder Festlegen der Telefonnummern, die in Einladungen in [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)enthalten sind.

 **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich **zu** Benutzer, und klicken Sie in der Liste auf den Anzeigenamen des gewünschten Benutzers.

2. Klicken Sie **neben Audiokonferenz** auf **Bearbeiten**.

3. Wählen **Sie unter** **Gebührenpflichtige** Nummer oder Gebührenfreie Nummer die Nummer aus der Dropdownliste aus, und klicken Sie auf **Übernehmen**.

Nachdem die Änderungen übernommen wurden, werden die neuen Standardtelefonnummern in die Besprechungseinrufe der Organisatoren aufgenommen, wenn sie das nächste Mal eine neue Besprechung planen.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Schritt 4 – Aktualisieren vorhandener Besprechungs-Einladungen von Benutzern mithilfe des Meeting Migration Service (optional)

Für die nächsten beiden Schritte müssen Sie mit der Windows PowerShell.
  
Wenn Sie die Standardtelefonnummern aktualisiert haben, die in den Besprechungseinrufen für einige oder alle Ihrer Benutzer enthalten sind, können Sie optional Besprechungseinrufe aktualisieren, die bereits an Benutzer in Ihrer Organisation gesendet wurden, bevor ihre Standardtelefonnummern mithilfe des Meeting Migration Service geändert wurden. Weitere Informationen finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Führen Sie Meeting Migration Service (MMS) für die Benutzer aus, deren Standardtelefonnummern in Schritt 2 geändert wurden. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Sie können auch den Status der Besprechungsmigration anzeigen. Alle Besprechungen werden neu geplant, sobald keine Vorgänge mit dem Status  *Ausstehend*  oder *In Bearbeitung*  mehr vorhanden sind.

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Schritte zum Aufheben der Zuweisung einer Servicetelefonnummer für eine Konferenzbrücke


Wenn Sie die Nummer einer Konferenzbrücke wieder zuweisen, können die Benutzer nicht mehr über diese Telefonnummer an Besprechungen teilnehmen. Da sich die Telefonnummer ändert, ist es wichtig, alle Benutzer zu aktualisieren, die eine Telefonnummer als Standardnummer haben können (falls vorhanden) und ihre vorhandenen Besprechungseinrufe zu aktualisieren, bevor die Nummer von der Audiokonferenzbrücke entfernt wird.

Wenn die Telefonnummer entfernt wird, ohne die Benutzer und ihre Besprechungen zu aktualisieren, können die vorhandenen Besprechungsteilnehmer eine Telefonnummer enthalten, die für die Teilnahme an Besprechungen nicht funktioniert.

Für die ersten drei Schritte müssen Sie mit der Windows PowerShell. Wenn Sie wissen möchten, wie Dies geht, klicken Sie auf Wissen, wie [sie mit einem Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Schritt 1 – Aktualisieren von Benutzern, deren Telefonnummer als Standardnummer nicht zugewiesen werden soll

Ersetzen Sie die gebührenpflichtige oder gebührenfreie Standardnummer für alle Benutzer, deren Nummer als Standardnummer nicht zugewiesen werden soll, und beginnen Sie mit dem Neuplanen ihrer Besprechungen. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Sie können auch die gebührenpflichtige oder gebührenfreie Standardnummer von Benutzern im admin center Microsoft Teams ändern. Dadurch werden ihre Besprechungen jedoch nicht automatisch neu berechnet. 
 
 Weitere Informationen finden Sie unter Festlegen der In Einladungen enthaltenen Telefonnummern [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) oder Festlegen der Telefonnummern, die in Einladungen in Skype for Business Online [enthalten sind.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > Je nach Größe Ihrer Organisation kann es eine Weile dauern, bis dieser Vorgang abgeschlossen ist.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Schritt 2 - Anzeigen des Status der Besprechungsmigration mit Windows PowerShell

Alle Besprechungen werden neu geplant, sobald  keine Vorgänge mit dem Status Ausstehend oder In *Bearbeitung mehr ausgeführt* werden.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Weitere Informationen zu Meeting Migration Service finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Schritt 3 - Aufheben der Zuweisung der alten Telefonnummer zur Audiokonferenzbrücke

Verwenden des Unregister-CsOnlineDialInConferencingServiceNumber-Cmdlets zum Aufheben der Registrierung einer gebührenpflichtigen oder gebührenfreien Nummer von einer Konferenzbrücke

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```
Hinweis: Um die ID der Konferenzbrücke zu finden, führen Sie die folgende PowerShell aus: Get-CsOnlineDialInConferencingBridge.


   > [!IMPORTANT]
   > Nachdem die Zuweisung einer Telefonnummer zu einer Audiokonferenzbrücke aufgehoben wurde, ist die Telefonnummer nicht mehr für die Teilnahme der Benutzer an neuen oder bestehenden Besprechungen verfügbar.

### <a name="save-time-and-automate"></a>Zeit sparen und Automatisieren

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
    > Der oben verwendete Standort muss mit den Kontaktinformationen der Benutzer übereinstimmen, die in der Gruppe Microsoft 365 Admin Center.

## <a name="troubleshooting"></a>Problembehandlung

**Die Schaltfläche "Zuweisen" ist nicht verfügbar**

Sie möchten die Zuweisen einer Nummer wieder aufnehmen, doch die Schaltfläche ist nicht verfügbar. Wenn Sie mit der Maus darauf zeigen, werden Sie an den Support mit der folgenden Meldung umgeleitet: "Standardnummern oder freigegebene Nummern können nicht von der Brücke entfernt _werden. Wenden Sie sich an den Support, um die Zuzuweisen von dedizierten gebührenpflichtigen Nummern auf "_ zu bitten.

Um weitere Informationen zu den Brücke(en) zu erhalten, führen Sie die folgende Powershell aus:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Das Ergebnis sollte, abgesehen von anderen Informationen wie Identity, Name und Region, auch die DefaultServiceNumber enthalten.

**Beispiel:** Zum Unzuweisen wird die DefaultServiceNumber-8005551234
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Informationen zu Windows PowerShell

Mit Windows PowerShell können Sie Benutzer und deren Berechtigungen verwalten. Windows PowerShell können Ihnen dabei helfen, Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Administrationspunkt zu verwalten, der Ihre tägliche Arbeit vereinfachen kann, insbesondere, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell hat gegenüber der ausschließlichen Verwendung des Microsoft 365 Admin Center beispielsweise, wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen, viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Verwandte Themen
[Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md)
