---
title: Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke
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
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Wenn Sie Lizenzen für Audiokonferenzen erwerben, hostet Microsoft Ihre Audiokonferenzbrücke für Ihre Organisation. Die Audiokonferenzbrücke gibt Einwahlnummern von verschiedenen Standorten aus, damit die Besprechungsorganisatoren und die Teilnehmer über ein Telefon an Skype for Business- oder Microsoft Teams-Besprechungen teilnehmen können.
ms.openlocfilehash: a37e7d00123dee76b512bb9a20874301e84a8406
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "33995159"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke

Wenn Sie **Audiokonferenzen** Lizenzen kaufen, Microsoft Ihre audiokonferenzbrücke für Ihre Organisation gehostet werden. Die audiokonferenzbrücke bietet out-Einwahl Telefonnummern aus unterschiedlichen Standorten, damit meeting-Organisatoren und Teilnehmer können sie Skype für Business oder Microsoft-Teams, Besprechungen, die mit einem Telefon beitreten.
  
Neben die Telefonnummern, die Konferenzbrücke bereits zugewiesen, Sie können [zusätzliche Service Zahlen abrufen](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (gebührenpflichtige und gebührenfreie Nummern für die Audiokonferenz verwendet) aus anderen Speicherorten, und weisen Sie anschließend zu Live Meeting-Brücke damit Sie können Erweitern Sie Abdeckung für Ihre Benutzer.
  
> [!NOTE]
> Um eine Rufnummer für ein Konferenzbrücke zuweisen/aufheben können, muss die Rufnummer eine *Servicenummer*sein. Sie können den Typ der Zahl ist, navigieren Sie zur **VoIP**finden Sie unter > **Telefonnummern** in der Vorgängerversion Portal und in der Spalte **' Zahl '** interessieren. Office 365 Communications haben muss zuerst eingerichtet werden, damit Benutzer in eine gebührenfreie Telefonnummer-Brücke einwählen können.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Schritte zum Zuweisen einer neuen Servicetelefonnummer zu Ihrer Konferenzbrücke

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Schritt 1 - Zuweisen der neuen Telefonnummer zu Ihrer Audiokonferenzbrücke

1. Melden Sie sich bei Office 365 mit Ihrem Geschäftskonto an.

2. Navigieren Sie zum **Microsoft 365 Administrationscenter** > **Admin zentriert** > **Teams & Skype** > **Legacy-Portal** > **VoIP** > **Rufnummern**.

3. Wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie im Aktionsbereich auf **Zuweisen**.

4. Klicken Sie auf der Seite **Zuweisen** auf **Speichern**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Schritt 2: Ändern der Standardrufnummer der Ihrer Konferenzbrücke (optional)

Die Standardrufnummer der Ihrer Konferenzbrücke definiert die Anrufer-ID, die verwendet wird, wenn ein Teilnehmer oder der Organisator aus innerhalb einer Besprechung ein ausgehender Anruf platziert wird.

Nur eine Service gebührenpflichtige Nummer kann als die Standardnummer für Ihre Konferenzbrücke festgelegt werden. **gebührenfreie Nummern Service können nicht als die Standardanzahl zulässiger Ihrer Konferenzbrücke festgelegt werden**. Wenn Sie eine Dienst gebührenpflichtige Nummer zuweisen und es als die neue Standardnummer für Ihre audiokonferenzbrücke festlegen möchten, führen Sie diese Schritte aus:

1. Melden Sie sich bei Office 365 mit Ihrem Geschäftskonto an.

2. Navigieren Sie zum **Microsoft 365 Administrationscenter** > **Admin zentriert** > **Teams & Skype** > **Besprechungen** > **Konferenz Brücken**.

3. Markieren Sie den Dienst die gebührenpflichtige Telefonnummer, den Sie als Standard konfigurieren möchten.

4. Wählen Sie **Als Standard** aus.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Schritt 3: Ändern der Standard-Telefonnummern, die in der Besprechung enthalten sind lädt der Benutzer (optional)

Die Standard-Telefonnummern eines Benutzers sind invites diejenigen aus, die auf ihre Besprechung enthalten sind, wenn sie eine Besprechung planen. Weitere Informationen, einschließlich wie Rufnummern ohne Authentifizierung für neue Benutzer zugewiesen werden finden Sie unter [Legen Sie das Telefon, den Zahlen auf enthalten in Microsoft-Teams, lädt](set-the-phone-numbers-included-on-invites-in-teams.md) oder [gewählte Nummern auf enthalten in Skype für Business Online invites Telefonnummern](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zu der **Microsoft-365-Verwaltungskonsole** > **Admin zentriert** > **Teams & Skype** > **Legacy-Portal** > **Audiokonferenzen** > **Benutzer**, und wählen Sie die Benutzer in der Liste.

3. Klicken Sie im Aktionsbereich auf **Bearbeiten**.

4. Wählen Sie unter **Gebührenpflichtige Standardnummer** oder **Gebührenfreie Standardnummer** die Nummer in der Liste aus, und klicken Sie auf **Speichern**.

Nach dem Speichern der Änderungen sind die neuen Standardtelefonnummern in den Besprechungseinladungen der Organisatoren enthalten, wenn diese zum nächsten Mal eine neue Besprechung planen.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Schritt 4: Aktualisieren einer vorhandenen Besprechung zum Einladen von Benutzern mithilfe der Besprechung Migration Service (optional)

Für die nächsten beiden Schritte müssen Sie Windows PowerShell zu starten.
  
Wenn Sie das Standard-Telefon Zahlen, die möglicherweise in der Besprechung eingeladen werden für einige oder alle Benutzer aktualisiert, können Sie optional Meeting-Einladungen, die bereits für Benutzer in Ihrer Organisation gesendet wurden, bevor die Standard-Rufnummern mit geändert wurden Aktualisieren der Migration Meeting-Dienst. Weitere Informationen finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Führen Sie Meeting Migration Service (MMS) für die Benutzer aus, deren Standardtelefonnummern in Schritt 2 geändert wurden. Führen Sie dazu den folgenden Befehl aus:

```
    Start-CsExMeetingMigration user@contoso.com
```

- Sie können auch den Status der Besprechungsmigration anzeigen. Alle Besprechungen werden neu geplant, sobald keine Vorgänge mit dem Status  *Ausstehend*  oder *In Bearbeitung*  mehr vorhanden sind.

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Schritte zum Aufheben der Zuweisung einer Servicetelefonnummer für eine Konferenzbrücke


Wenn Sie eine Telefonnummer aus einer Konferenzbrücke aufheben, wird nicht Benutzer alle von der angegebenen Telefonnummer an Besprechungen teilnehmen können. Da die Telefonnummer geändert wird, ist es wichtig, um alle Benutzer zu aktualisieren, die über eine Rufnummer als ihrer Standardrufnummer verfügen konnte (falls vorhanden) und zum Aktualisieren ihrer vorhandenen meeting Einladungen, bevor die Telefonnummer der audiokonferenzbrücke aufgehoben wird.

Wenn die Rufnummer entfernt wird, ohne die Benutzer und ihre Besprechungen zu aktualisieren, werden beim ihrer vorhandenen meeting-Einladungen konnte eine Rufnummer enthalten, die für die Teilnahme an einer Besprechung nicht funktionsfähig.

Für die ersten drei Schritte müssen Sie Windows PowerShell zu starten. Um herauszufinden, wie Sie dies tun, klicken Sie auf [möchten Sie wissen, wie Sie mit Windows PowerShell verwalten?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Schritt 1 - Update Benutzer mit der Rufnummer nicht zugewiesene als eines der ihre Standard-Zahlen ist

Ersetzen Sie die standardmäßige gebührenpflichtige oder gebührenfreie Telefonnummer für alle Benutzer die Zahl haben, die nicht als eine Standardnummer zugewiesen sein, und Starten des neu zu ihren Besprechungen planen. Führen Sie dazu den folgenden Befehl aus:

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Sie können auch die gebührenpflichtige oder die gebührenfreie Standardnummer von Benutzern im Skype for Business Admin Center ändern. Dadurch werden aber ihre Besprechungen nicht automatisch neu geplant. 
 
 Weitere Informationen finden Sie unter [Legen Sie das Telefon, den Zahlen auf enthalten in Microsoft-Teams, lädt](set-the-phone-numbers-included-on-invites-in-teams.md) oder [gewählte Nummern auf enthalten in Skype für Business Online invites Telefonnummern](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > Je nach Größe Ihrer Organisation kann es eine Weile dauern, bis dieser Vorgang abgeschlossen ist.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Schritt 2 - Anzeigen des Status der Besprechungsmigration mit Windows PowerShell

Alle Besprechungen werden neu geplant werden, nachdem es keine Vorgänge im Zustand *ausstehenden* oder *In Bearbeitung sind* .

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Weitere Informationen zu Meeting Migration Service finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Schritt 3 - Aufheben der Zuweisung der alten Telefonnummer zur Audiokonferenzbrücke

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zu der **Microsoft-365-Verwaltungskonsole** > **Admin zentriert** > **Teams & Skype** > **Legacy-Portal** > **VoIP** > **Rufnummern**.

3. Ist die Telefonnummer eine gebührenfreie Telefonnummer, wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie im Bereich Aktion aus, klicken Sie auf **Zuweisung entfernen**. Wenn die Rufnummer ein gebührenpflichtige Nummer ist, wenden Sie sich an den [Support von Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) , um die Rufnummer nicht zugewiesen haben.

4. Wenn die Telefonnummer eine gebührenfreie Fre Zahl ist, klicken Sie auf **Ja** klicken Sie im Bestätigungsfenster zur.

   > [!IMPORTANT]
   > Nachdem die Zuweisung einer Telefonnummer zu einer Audiokonferenzbrücke aufgehoben wurde, ist die Telefonnummer nicht mehr für die Teilnahme der Benutzer an neuen oder bestehenden Besprechungen verfügbar.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>So überprüfen Sie, ob Windows PowerShell bereit ist

 Diese Schritte überprüfen Sie, dass Sie Windows PowerShell, Version 3.0 oder höher ausgeführt werden.

1. Geben Sie im **Menü Start** > **Windows PowerShell**ein.

2. Geben Sie _Get-Host_ im **Windows PowerShell** -Fenster ein, um die Version zu überprüfen.

3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.

4. Außerdem müssen Sie das Windows PowerShell-Modul für Skype für Business Online installieren, mit dem Sie eine remote Windows PowerShell-Sitzung zu erstellen, die mit Skype für Business Online eine Verbindung herstellt. In diesem Modul wird nur auf 64-Bit-Computern unterstützt und kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype für Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)heruntergeladen werden.
Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.

Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>So starten Sie Windows PowerShell

 **Starten einer Windows PowerShell-Sitzung**

1. From the **Start Menu** > **Windows PowerShell**.

2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Sparen Sie Zeit und automatisieren

Um Zeit sparen, indem Sie diesen Prozess automatisieren, können Sie das [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) oder **Set-CsOnlineDialInConferencingUserDefaultNumber** -Cmdlets verwenden.

- Mit dem Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) können Sie die gebührenpflichtige oder gebührenfreie Standardnummer für spezifische Benutzer ändern.

  - Führen Sie Folgendes aus, um die gebührenfreie Standardnummer für einen Benutzer zu ändern:

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Ändern Sie mit dem Cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** die gebührenpflichtige oder gebührenfreie Nummer für Benutzer auf Basis ihrer ursprünglichen Standardnummer oder ihres Standorts.

    > [!NOTE]
    > Die BridgeID finden Sie mithilfe von **Get-CsOnlineDialInConferencingBridge**.

  - So ändern Sie die gebührenpflichtige Standardnummer für alle Benutzer bis auf einen in 8005551234:

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Führen Sie Folgendes aus, um die gebührenfreie Standardnummer aller Benutzer mit der gebührenfreien Standardnummer 8005551234 in 8005551239 zu ändern und die Besprechungen der Benutzer automatisch neu zu planen:

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Führen Sie Folgendes aus, um die gebührenfreie Standardnummer aller Benutzer in den USA in 8005551234 zu ändern und ihre Besprechungen automatisch neu zu planen:

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > Der Speicherort, der über Anforderungen verwendet wird, die Kontaktinformationen der Benutzer entspricht, die in der Microsoft-365-Verwaltungskonsole festgelegt ist.

## <a name="troubleshooting"></a>Problembehandlung

**Aufheben der Zuweisung Schaltfläche ist deaktiviert, ausgehend**

Aufheben der Zuweisung einer Zahl verwendet werden soll, aber die Schaltfläche ist abgeblendet skalierten und beim hoovering darüber, werden Sie umgeleitet zum Kontaktieren des Supports mit der folgenden Meldung _"Standard oder freigegebenen Zahlen Can´t nicht aus der Brücke zugewiesen werden. Dedizierte gebührenpflichtige oder Aufheben der Zuweisung, wenden Sie sich an Support._".

Um weitere Informationen zu den Bridge(s) zu erhalten, führen Sie die folgenden Powershell aus:
```
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Das Ergebnis, reservieren andere Informationen wie Identität, Namen und Region, sollten auch die DefaultServiceNumber enthalten.

**Beispiel**zum Aufheben der Zuweisung, die DefaultServiceNumber "8005551234"
```
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName “Conference Bridge” -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Informationen zu Windows PowerShell

Mit Windows PowerShell können Sie Benutzer und deren Berechtigungen verwalten. Windows PowerShell können Sie das Verwalten von Office 365 und Skype für Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, insbesondere dann, wenn Sie mehrere Aufgaben zu tun haben. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur mit dem Microsoft 365 Administrationscenter wie wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Verwandte Themen
[Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md)
