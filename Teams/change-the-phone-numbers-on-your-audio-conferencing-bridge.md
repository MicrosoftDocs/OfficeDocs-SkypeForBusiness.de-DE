---
title: Ändern von Telefonnummern auf der Audiokonferenz-Brücke
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
description: Informieren Sie sich über die Schritte, die erforderlich sind, um ihrer Konferenzbrücke eine neue Dienst Telefonnummer zuzuweisen, um die Abdeckung für Ihre Benutzer zu erweitern.
ms.openlocfilehash: 571b7a9c14db1601e0a4b94740395ad087808a49
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139074"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke

Wenn Sie **Audiokonferenz-** Lizenzen kaufen, hostet Microsoft Ihre Audiokonferenz-Brücke für Ihre Organisation. Die Audiokonferenz-Brücke gibt Einwahlnummern von verschiedenen Standorten aus, sodass Besprechungsorganisatoren und Teilnehmer Sie verwenden können, um mit einem Telefon an Skype for Business-oder Microsoft Teams-Besprechungen teilzunehmen.
  
Zusätzlich zu den Telefonnummern, die ihrer Konferenzbrücke bereits zugewiesen sind, können Sie [zusätzliche Servicenummern](/microsoftteams/getting-service-phone-numbers) (gebührenpflichtige und gebührenfreie Nummern, die für Audiokonferenzen verwendet werden) von anderen Standorten abrufen und dann der Konferenzbrücke zuweisen, damit Sie die Abdeckung für Ihre Benutzer erweitern können.
  
> [!NOTE]
> Um eine Rufnummer für ein Konferenzbrücke zuweisen/aufheben können, muss die Rufnummer eine *Servicenummer*sein. Sie können den Typ der Zahl sehen, indem Sie im Legacy- **Portal zu** > **Telefonnummern** navigieren und in der Spalte " **Zahlentyp** " suchen. Office 365 Communications haben muss zuerst eingerichtet werden, damit Benutzer in eine gebührenfreie Telefonnummer-Brücke einwählen können.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Schritte zum Zuweisen einer neuen Servicetelefonnummer zu Ihrer Konferenzbrücke

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Schritt 1 - Zuweisen der neuen Telefonnummer zu Ihrer Audiokonferenzbrücke

1. Melden Sie sich bei Office 365 mit Ihrem Geschäftskonto an.

2. Wechseln Sie zu **Microsoft 365 Admin Center** > -Teams für**Admin** > **& Skype** > **Legacy Portal** > -**VoIP** > -**Telefonnummern**.

3. Wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie im Aktionsbereich auf **Zuweisen**.

4. Klicken Sie auf der Seite **Zuweisen** auf **Speichern**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Schritt 2 – Ändern der Standardtelefonnummer ihrer Konferenzbrücke (optional)

Die Standardtelefonnummer ihrer Konferenzbrücke definiert die Rufnummernanzeige, die verwendet wird, wenn ein ausgehender Anruf von einem Teilnehmer oder vom Organisator innerhalb einer Besprechung abgestellt wird.

Nur eine Dienst gebührenpflichtige Nummer kann als Standardnummer für Ihre Konferenzbrücke eingestellt werden. **Dienst gebührenfreie Nummern können nicht als Standardnummer ihrer Konferenzbrücke eingestellt werden**. Führen Sie die folgenden Schritte aus, wenn Sie eine Dienst gebührenpflichtige Nummer zuweisen und diese als neue Standardnummer für Ihre Audiokonferenz-Brücke festlegen möchten:

1. Melden Sie sich bei Office 365 mit Ihrem Geschäftskonto an.

2. Wechseln Sie **zu Microsoft 365 Admin Center** > -Teams für**Admin** > **Center & Skype** > -**Konferenz Brücken**für**Besprechungen** > .

3. Heben Sie die Dienst Gebühren Nummer auf, die Sie als Standard festlegen möchten.

4. Wählen Sie **Als Standard** aus.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Schritt 3 – Ändern der standardmäßigen Telefonnummern, die in den Besprechungseinladungen der Benutzer enthalten sind (optional)

Die standardmäßigen Telefonnummern eines Benutzers sind diejenigen, die in den Besprechungseinladungen enthalten sind, wenn Sie eine Besprechung planen. Weitere Informationen dazu, wie die defaul-Telefonnummern neuen Benutzern zugewiesen werden, finden Sie unter [Einrichten der Telefonnummern, die in Einladungen in Microsoft Teams enthalten](set-the-phone-numbers-included-on-invites-in-teams.md) sind, oder [Festlegung der Telefonnummern, die in Einladungen in Skype for Business Online enthalten](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)sind.
  
1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

2. Wechseln Sie zu den **Microsoft 365 Admin Center** > **Admin Center** > **Teams & Skype** > **Legacy Portal** > **-Audiokonferenz** > -**Benutzer**, und wählen Sie die Benutzer in der Liste aus.

3. Klicken Sie im Aktionsbereich auf **Bearbeiten**.

4. Wählen Sie unter **Gebührenpflichtige Standardnummer** oder **Gebührenfreie Standardnummer** die Nummer in der Liste aus, und klicken Sie auf **Speichern**.

Nach dem Speichern der Änderungen sind die neuen Standardtelefonnummern in den Besprechungseinladungen der Organisatoren enthalten, wenn diese zum nächsten Mal eine neue Besprechung planen.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Schritt 4 – Aktualisieren vorhandener Besprechungseinladungen von Benutzern mithilfe des Besprechungs Migrations Diensts (optional)

In den nächsten beiden Schritten müssen Sie Windows PowerShell starten.
  
Wenn Sie die Standardtelefon Nummern, die in den Besprechungseinladungen für einige oder alle Benutzer Inlcuded sind, aktualisiert haben, können Sie optional Besprechungseinladungen aktualisieren, die bereits an Benutzer in Ihrer Organisation gesendet wurden, bevor Ihre Standard Telefonnummern mithilfe des Besprechungs Migrations Diensts geändert wurden. Weitere Informationen finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Führen Sie Meeting Migration Service (MMS) für die Benutzer aus, deren Standardtelefonnummern in Schritt 2 geändert wurden. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Sie können auch den Status der Besprechungsmigration anzeigen. Alle Besprechungen werden neu geplant, sobald keine Vorgänge mit dem Status  *Ausstehend*  oder *In Bearbeitung*  mehr vorhanden sind.

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Schritte zum Aufheben der Zuweisung einer Servicetelefonnummer für eine Konferenzbrücke


Wenn Sie die Zuweisung einer Telefonnummer von einer Konferenzbrücke aufheben, können die Benutzer nicht mehr an Besprechungen mit dieser Telefonnummer teilnehmen. Da sich die Telefonnummer ändert, ist es wichtig, alle Benutzer zu aktualisieren, die eine Telefonnummer als Standardnummer (sofern vorhanden) aufweisen können, und Ihre vorhandenen Besprechungseinladungen zu aktualisieren, bevor die Telefonnummer von der Audiokonferenz-Brücke nicht zugewiesen wird.

Wenn die Telefonnummer entfernt wird, ohne die Benutzer und Ihre Besprechungen zu aktualisieren, können Ihre vorhandenen Besprechungseinladungen eine Telefonnummer enthalten, die nicht für die Teilnahme an Besprechungen funktioniert.

In den ersten drei Schritten müssen Sie Windows PowerShell starten. Klicken Sie auf [möchten Sie wissen, wie Sie mit Windows PowerShell verwalten](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell) können, um zu erfahren, wie dies geht.

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Schritt 1 – Aktualisieren von Benutzern, deren Telefonnummer als Standardnummer nicht zugewiesen ist

Ersetzen Sie die standardmäßige gebührenpflichtige oder gebührenfreie Nummer für alle Benutzer, denen die Nummer als Standardnummer zugewiesen werden soll, und starten Sie den Prozess der Umplanung ihrer Besprechungen. Führen Sie dazu den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Sie können auch die gebührenpflichtige oder die gebührenfreie Standardnummer von Benutzern im Skype for Business Admin Center ändern. Dadurch werden aber ihre Besprechungen nicht automatisch neu geplant. 
 
 Weitere Informationen finden Sie unter [Einrichten der Telefonnummern, die in Einladungen in Microsoft Teams enthalten sind](set-the-phone-numbers-included-on-invites-in-teams.md) , oder [Festlegung der Telefonnummern, die in Einladungen in Skype for Business Online enthalten](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)sind.

  > [!NOTE]
  > Je nach Größe Ihrer Organisation kann es eine Weile dauern, bis dieser Vorgang abgeschlossen ist.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Schritt 2 - Anzeigen des Status der Besprechungsmigration mit Windows PowerShell

Alle Besprechungen werden neu geplant, sobald keine Vorgänge im Status *Ausstehend* oder *in Bearbeitung* sind.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Weitere Informationen zu Meeting Migration Service finden Sie unter [Einrichten des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Schritt 3 - Aufheben der Zuweisung der alten Telefonnummer zur Audiokonferenzbrücke

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Wechseln Sie zu den **Microsoft 365 Admin Center** > **Admin Center** > **Teams & Skype** > **Legacy Portal** > -**VoIP** > -**Telefonnummern**.

3. Wenn es sich bei der Telefonnummer um eine gebührenfreie Nummer handelt, wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie im Bereich "Aktion" auf **Zuweisung**aufheben. Wenn es sich bei der Telefonnummer um eine gebührenpflichtige Nummer handelt, wenden Sie sich an den [Microsoft-Support](https://go.microsoft.com/fwlink/?linkid=2091806) , damit die Telefonnummer nicht zugewiesen ist.

4. Wenn es sich bei der Telefonnummer um eine gebührenpflichtige Nummer handelt, klicken Sie im Bestätigungsfenster auf **Ja** .

   > [!IMPORTANT]
   > Nachdem die Zuweisung einer Telefonnummer zu einer Audiokonferenzbrücke aufgehoben wurde, ist die Telefonnummer nicht mehr für die Teilnahme der Benutzer an neuen oder bestehenden Besprechungen verfügbar.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>So überprüfen Sie, ob Windows PowerShell bereit ist

 Mit den folgenden Schritten wird überprüft, ob Sie Windows PowerShell, Version 3,0 oder höher, ausführen.

1. Geben Sie im **Menü Start** > **Windows PowerShell**ein.

2. Geben Sie _Get-Host_ im **Windows PowerShell** -Fenster ein, um die Version zu überprüfen.

3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .
Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.

4. Außerdem müssen Sie das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul wird nur auf 64-Bit-Computern unterstützt und kann aus dem Microsoft Download Center unter [Windows PowerShell Module für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)heruntergeladen werden.
Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.

Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>So starten Sie Windows PowerShell

 **Starten einer Windows PowerShell-Sitzung**

1. Vom **Start Menu** > **Windows PowerShell**.

2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype for Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Zeitersparnis und Automatisierung

Um Zeit zu sparen, indem Sie diesen Prozess automatisieren, können Sie die Cmdlets " [csonlinedialinconferencinguser zeigt](https://go.microsoft.com/fwlink/?LinkId=617688) " oder " **Satz-CsOnlineDialInConferencingUserDefaultNumber** " verwenden.

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
    > Der oben verwendete Standort muss mit den Kontaktinformationen der Benutzer übereinstimmen, die im Microsoft 365 Admin Center festgelegten sind.

## <a name="troubleshooting"></a>Problembehandlung

**Die Schaltfläche "Zuordnung aufheben" ist abgeblendet**

Sie möchten die Zuweisung einer Zahl aufheben, aber die Schaltfläche ist abgeblendet, und wenn Sie sich während des staubsaugens darüber informieren, werden Sie an den Support mit der folgenden Meldung weitergeleitet: _"Standard-oder freigegebene Nummern können nicht von der Brücke zugewiesen werden. Wenn Sie die Zuweisung von gebührenpflichtigen Nummern aufheben möchten, wenden Sie sich bitte an den Support._"

Wenn Sie weitere Informationen zu den Brücken erhalten möchten, führen Sie die folgende PowerShell aus:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Das Ergebnis sollte neben anderen Informationen wie Identität, Name und Region auch die DefaultServiceNumber enthalten.

**Beispiel**: Wenn Sie die Zuweisung aufheben möchten, wird die DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Informationen zu Windows PowerShell

Mit Windows PowerShell können Sie Benutzer und deren Berechtigungen verwalten. Windows PowerShell kann Ihnen bei der Verwaltung von Office 365 und Skype for Business Online helfen, indem Sie eine zentrale Verwaltungsstelle verwenden, die Ihre tägliche Arbeit vereinfacht, insbesondere dann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Verwandte Themen
[Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md)
