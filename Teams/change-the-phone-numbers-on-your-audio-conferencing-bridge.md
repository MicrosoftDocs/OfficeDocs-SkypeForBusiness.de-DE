---
title: Ändern von Telefonnummern auf der Audiokonferenzbrücke
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
description: Erfahren Sie, wie Sie Ihrer Konferenzbrücke eine neue Diensttelefonnummer zuweisen müssen, um die Abdeckung für Ihre Benutzer zu erweitern.
ms.openlocfilehash: e2e1aa3d5626f6592f22e0850a8c7419d7549b38
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569187"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke

Wenn Sie Lizenzen **für Audiokonferenzen erwerben,** hosten Sie Ihre Audiokonferenzbrücke für Ihre Organisation. Die Audiokonferenzbrücke gibt Einwahltelefonnummern von verschiedenen Standorten aus, sodass Besprechungsorganisatoren und Teilnehmer sie verwenden können, um über ein Telefon an Skype for Business- oder Microsoft Teams-Besprechungen teilzunehmen.
  
Zusätzlich zu den Telefonnummern, die Ihrer Konferenzbrücke bereits [](/microsoftteams/getting-service-phone-numbers) zugewiesen sind, können Sie zusätzliche Servicenummern (gebührenpflichtige und gebührenfreie Nummern, die für Audiokonferenzen verwendet werden) von anderen Standorten erhalten und diese dann der Konferenzbrücke zuweisen, damit Sie die Abdeckung für Ihre Benutzer erweitern können.
  
> [!NOTE]
> Um eine Rufnummer für ein Konferenzbrücke zuweisen/aufheben können, muss die Rufnummer eine *Servicenummer* sein. Sie können den Typ der Nummer sehen, indem Sie im Microsoft Teams Admin Center zu Voice Phone-Nummern navigieren und in der Spalte  >   **Zahlentyp** nachschauen. Microsoft 365- oder Office 365-Guthaben für Kommunikationen müssen zuerst eingerichtet werden, damit Benutzer sich unter einer gebührenfreien Rufnummer in die Brücke einwählen können.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Schritte zum Zuweisen einer neuen Servicetelefonnummer zu Ihrer Konferenzbrücke

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Schritt 1 - Zuweisen der neuen Telefonnummer zu Ihrer Audiokonferenzbrücke

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **Voice**  >  **phone numbers**.

2. Wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten.**

3. Erweitern Sie **auf der** Seite Bearbeiten unter **Zugewiesen an** die Dropdownliste, und wählen Sie **Konferenzbrücke**  >  **übernehmen aus.**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Schritt 2 : Ändern der Standardtelefonnummer der Konferenzbrücke (optional)

Die Standardtelefonnummer Ihrer Konferenzbrücke definiert die Anrufer-ID, die verwendet wird, wenn ein ausgehender Anruf von einem Teilnehmer oder Organisator innerhalb einer Besprechung platziert wird.

Es kann nur eine Servicemautnummer als Standardnummer für Ihre Konferenzbrücke festgelegt werden. **gebührenfreie Servicenummern können nicht** als Standardnummer Ihrer Konferenzbrücke festgelegt werden. Wenn Sie eine Servicemautnummer zuweisen und diese als neue Standardnummer für Ihre Audiokonferenzbrücke festlegen möchten, führen Sie die folgenden Schritte aus:

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu  >  **Besprechungskonferenzbrücken.**

2. Markieren Sie die Servicemautnummer, die Sie als Standard konfigurieren möchten.

3. Wählen Sie **Als Standard** aus.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Schritt 3 : Ändern der Standardtelefonnummern, die in den Besprechungseinlädungen von Benutzern enthalten sind (optional)

Die Standardtelefonnummern eines Benutzers sind die Telefonnummern, die in den Besprechungseinlästen enthalten sind, wenn er eine Besprechung plant. Weitere Informationen, einschließlich der Art und Weise, wie die Standardtelefonnummern neuen Benutzern zugewiesen werden, finden Sie unter Festlegen der Telefonnummern, die in Einladungen [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) enthalten sind, oder Festlegen der Telefonnummern, die in Einladungen in Skype for Business Online enthalten [sind.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **Benutzer,** und klicken Sie auf den Anzeigenamen des gewünschten Benutzers in der Liste.

2. Klicken Sie **neben Audiokonferenz auf** **Bearbeiten.**

3. Wählen **Sie unter** Gebührenfreie Nummer oder **gebührenfreie Nummer** die Nummer aus der Dropdownliste aus, und klicken Sie auf **Übernehmen.**

Nachdem die Änderungen angewendet wurden, werden die neuen Standardtelefonnummern in die Besprechungseinlädungen der Organisatoren einbezogen, wenn sie das nächste Mal eine neue Besprechung planen.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Schritt 4 : Aktualisieren vorhandener Besprechungs einladen von Benutzern mithilfe des Besprechungsmigrationsdiensts (optional)

Für die nächsten beiden Schritte müssen Sie mit der Windows PowerShell.
  
Wenn Sie die Standardtelefonnummern aktualisiert haben, die in den Besprechungseinrufen für einige oder alle Ihrer Benutzer enthalten sind, können Sie optional Besprechungs einladen, die bereits an Benutzer in Ihrer Organisation gesendet wurden, bevor ihre Standardtelefonnummern mithilfe des Besprechungsmigrationsdiensts geändert wurden. Weitere Informationen finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Führen Sie Meeting Migration Service (MMS) für die Benutzer aus, deren Standardtelefonnummern in Schritt 2 geändert wurden. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Sie können auch den Status der Besprechungsmigration anzeigen. Alle Besprechungen werden neu geplant, sobald keine Vorgänge mit dem Status  *Ausstehend*  oder *In Bearbeitung*  mehr vorhanden sind.

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Schritte zum Aufheben der Zuweisung einer Servicetelefonnummer für eine Konferenzbrücke


Wenn Sie die Zuweisung einer Telefonnummer von einer Konferenzbrücke auflöst, können Benutzer nicht mehr mit dieser Telefonnummer an Besprechungen teilnehmen. Da sich die Telefonnummer ändert, ist es wichtig, alle Benutzer zu aktualisieren, die über eine Telefonnummer als Standardnummer verfügen könnten (sofern vorhanden), und ihre vorhandenen Besprechungseinlände zu aktualisieren, bevor die Telefonnummer von der Audiokonferenzbrücke nicht zugewiesen wird.

Wenn die Telefonnummer entfernt wird, ohne die Benutzer und ihre Besprechungen zu aktualisieren, können ihre vorhandenen Besprechungsbesprechungen eine Telefonnummer enthalten, die für die Teilnahme an ihren Besprechungen nicht funktioniert.

Für die ersten drei Schritte müssen Sie mit der Windows PowerShell. Wenn Sie wissen möchten, wie Sie dies tun können, klicken Sie auf Möchten Sie wissen, [wie sie mit Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Schritt 1 : Aktualisieren von Benutzern, deren Telefonnummer als Standardnummer nicht zugewiesen werden soll

Ersetzen Sie die standardmäßige gebührenpflichtige oder gebührenfreie Nummer für alle Benutzer, deren Nummer als Standardnummer nicht zugewiesen werden soll, und beginnen Sie mit dem Neuplanen ihrer Besprechungen. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Sie können auch die standardmäßige gebührenpflichtige oder gebührenfreie Benutzeranzahl im Microsoft Teams Admin Center ändern. Dadurch werden ihre Besprechungen jedoch nicht automatisch neu berechnet. 
 
 Weitere Informationen finden Sie unter Festlegen der Telefonnummern, die in Einladungen [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) enthalten sind, oder Festlegen der Telefonnummern, die in Einladungen in Skype for Business Online enthalten [sind.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > Je nach Größe Ihrer Organisation kann es eine Weile dauern, bis dieser Vorgang abgeschlossen ist.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Schritt 2 - Anzeigen des Status der Besprechungsmigration mit Windows PowerShell

Alle Besprechungen werden neu geplant, sobald keine Vorgänge im Status *"Ausstehend"* oder *"In Bearbeitung" angezeigt* werden.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Weitere Informationen zu Meeting Migration Service finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Schritt 3 - Aufheben der Zuweisung der alten Telefonnummer zur Audiokonferenzbrücke

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

2. Wenn es sich bei der Telefonnummer um eine gebührenfreie Nummer handelt, wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie auf **Los.** Wenn es sich bei der Telefonnummer [](https://go.microsoft.com/fwlink/?linkid=2091806) um eine gebührenpflichtige Nummer handelt, wenden Sie sich an den Microsoft-Support, damit die Telefonnummer nicht zugewiesen wird.

3. Wenn es sich bei der Telefonnummer um eine gebührenfreie Nummer handelt, klicken **Sie** im Bestätigungsfenster auf Ja.

   > [!IMPORTANT]
   > Nachdem die Zuweisung einer Telefonnummer zu einer Audiokonferenzbrücke aufgehoben wurde, ist die Telefonnummer nicht mehr für die Teilnahme der Benutzer an neuen oder bestehenden Besprechungen verfügbar.

### <a name="save-time-and-automate"></a>Zeit sparen und automatisieren

Um Zeit zu sparen, indem Sie diesen Prozess automatisieren, können Sie die [Cmdlets Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) oder **Set-CsOnlineDialInConferencingUserDefaultNumber** verwenden.

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
    > Der oben verwendete Speicherort muss den Kontaktinformationen der Benutzer entsprechen, die im Microsoft 365 Admin Center festgelegt sind.

## <a name="troubleshooting"></a>Problembehandlung

**Schaltfläche "Zuweisen nicht zuweisen" ist nicht verfügbar**

Sie möchten die Zuzuweisende Nummer aufheben, aber die Schaltfläche ist nicht verfügbar. Wenn Sie mit der Maus darauf zeigen, werden Sie umgeleitet, um den Support mit der folgenden Meldung zu kontaktieren: "Standard- oder freigegebene Nummern können nicht von der Brücke entfernt _werden. Wenden Sie sich an den Support, um die Zuzuweisen von dedizierten Gebührennummern zu entsenden._".

Um weitere Informationen zu den Bridge(en) zu erhalten, führen Sie die folgende Powershell aus:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Das Ergebnis sollte neben anderen Informationen wie Identität, Name und Region auch die DefaultServiceNumber enthalten.

**Beispiel**, um die Zuzuweisende Zuzuweisende Zuzuweisen, die DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Informationen zu Windows PowerShell

Mit Windows PowerShell können Sie Benutzer und deren Berechtigungen verwalten. Windows PowerShell können Ihnen helfen, Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Verwaltungspunkt zu verwalten, der Ihre tägliche Arbeit vereinfachen kann, insbesondere, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Verwandte Themen
[Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md)
