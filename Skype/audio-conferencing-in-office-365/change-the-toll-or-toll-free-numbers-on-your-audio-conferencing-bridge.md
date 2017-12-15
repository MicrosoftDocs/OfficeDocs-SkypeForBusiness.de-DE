---
title: "Ändern der gebührenpflichtigen oder gebührenfreien Telefonnummern in Ihrer Audiokonferenzbrücke"
ms.author: tonysmit
author: tonysmit
ms.date: 11/29/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PSTNConferencingRemovePhoneNumberFromBridge
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
description: "Wenn Sie Lizenzen für Audiokonferenzen erwerben, hostet Microsoft Ihre Audiokonferenzbrücke für Ihre Organisation. Die Audiokonferenzbrücke gibt Einwahlnummern von verschiedenen Standorten aus, damit die Besprechungsorganisatoren und die Teilnehmer über ein Telefon an Skype for Business- oder Microsoft Teams-Besprechungen teilnehmen können."
---

# Ändern der gebührenpflichtigen oder gebührenfreien Telefonnummern in Ihrer Audiokonferenzbrücke

Wenn Sie Lizenzen für **Audiokonferenzen** erwerben, hostet Microsoft Ihre *Audiokonferenzbrücke*  für Ihre Organisation. Die Audiokonferenzbrücke gibt Einwahlnummern von verschiedenen Standorten aus, damit die Besprechungsorganisatoren und die Teilnehmer über ein Telefon an Skype for Business- oder Microsoft Teams-Besprechungen teilnehmen können.
  
Zusätzlich zu den Telefonnummern, die Ihrer Konferenzbrücke bereits zugewiesen sind, können Sie [Abrufen von Skype for Business-Leistungsnummern](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) (gebührenpflichtige und gebührenfreie Telefonnummern für Audiokonferenzen) von anderen Standorten beziehen und diese der Konferenzbrücke zuweisen. Dadurch können Sie das abgedeckte Gebiet für Ihre Benutzer erweitern.
  
> [!NOTE]
> Damit Sie eine Telefonnummer für eine Konferenzbrücke zuweisen bzw. die Zuweisung aufheben können, muss es sich bei der Telefonnummer um eine  *Servicenummer*  handeln. Sie können zu **VoIP** > **Telefonnummern** navigieren und in der Spalte **Nummerntyp** nachsehen, um welchen Nummerntyp es sich handelt.
  
## Schritte zum Zuweisen einer neuen Servicetelefonnummer zu Ihrer Konferenzbrücke

### Schritt 1 - Zuweisen der neuen Telefonnummer zu Ihrer Audiokonferenzbrücke

1. Melden Sie sich bei Office 365 mit Ihrem Geschäftskonto an.
    
2. Navigieren Sie zu **Office 365 Admin Center** > **Admin Center** > **Skype for Business** > **VoIP** > **Telefonnummern**.
    
3. Wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie im Aktionsbereich auf **Zuweisen**.
    
4. Klicken Sie auf der Seite **Zuweisen** auf **Speichern**.
    
    Für Ihre Konferenzbrücke kann nur eine gebührenpflichtige Servicenummer als Standardnummer festgelegt werden. **Gebührenfreie Servicenummern können nicht als Standardnummer für Ihre Konferenzbrücke festgelegt werden**. Wenn Sie eine gebührenpflichtige Servicenummer zuweisen und diese als neue Standardnummer für Ihre Audiokonferenzbrücke festlegen möchten, müssen Sie die Option **Diese Nummer als Standardnummer verwenden** auswählen.
    
    > [!NOTE]
    > Nachdem eine neue Telefonnummer zugewiesen wurde, ändert sich die Standardnummer für vorhandene Benutzer nicht, selbst wenn die Nummer als neue Standardnummer festgelegt wurde. Unter [Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md) finden Sie Informationen dazu, wie Sie die gebührenpflichtige oder eine gebührenfreie Standardnummer festlegen können, die den Besprechungseinladungen eines Organisators hinzugefügt wird.
  
### Schritt 2 - Ändern der Standardrufnummern, die in den Besprechungseinladungen von Benutzern enthalten sind (optional)

Bei den Standardtelefonnummern für Benutzer handelt es sich um die Nummern, die in ihren Besprechungseinladungen enthalten sind, wenn sie eine Besprechung planen. Weitere Informationen finden Sie unter [Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zu **Office 365 Admin Center** > **Admin Center** > **Skype for Business** > **Audio Conferencing** (Audiokonferenz) > **Benutzer**, und wählen Sie die Benutzer in der Liste aus.
    
3. Klicken Sie im Aktionsbereich auf **Bearbeiten**.
    
4. Wählen Sie unter **Gebührenpflichtige Standardnummer** oder **Gebührenfreie Standardnummer** die Nummer in der Liste aus, und klicken Sie auf **Speichern**.
    
Nach dem Speichern der Änderungen sind die neuen Standardtelefonnummern in den Besprechungseinladungen der Organisatoren enthalten, wenn diese zum nächsten Mal eine neue Besprechung planen.
  
### Schritt 3 - Aktualisieren vorhandener Besprechungseinladungen von Benutzern mit Meeting Migration Service (optional)

Für die nächsten beiden Schritte müssen Sie Windows PowerShell starten. Wie Sie dazu vorgehen müssen, erfahren Sie, wenn Sie [Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md#bk_PowerShell) klicken.
  
Mit Meeting Migration Service können Sie optional Besprechungseinladungen aktualisieren, die bereits vor der Änderung der Standardtelefonnummern an Benutzer in Ihrer Organisation gesendet wurden. Weitere Informationen finden Sie unter [Einrichten des Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md)﻿.
  
- Führen Sie Meeting Migration Service (MMS) für die Benutzer aus, deren Standardtelefonnummern in Schritt 2 geändert wurden. Führen Sie dazu den folgenden Befehl aus:
    
```
	Start-CsExMeetingMigration user@contoso.com

```

- Sie können auch den Status der Besprechungsmigration anzeigen. Alle Besprechungen werden neu geplant, sobald keine Vorgänge mit dem Status  *Ausstehend*  oder *In Bearbeitung*  mehr vorhanden sind.
    
```
	Get-CsMeetingMigrationStatus -SummaryOnly
```

## Schritte zum Aufheben der Zuweisung einer Servicetelefonnummer für eine Konferenzbrücke
<a name="bk_StartPowerShell"> </a>

Wenn Sie die Zuweisung einer Telefonnummer zu einer Konferenzbrücke aufheben, können die Benutzer nicht mehr über diese Telefonnummer an Besprechungen teilnehmen. Aufgrund der Telefonnummernänderung ist es wichtig, alle Benutzer zu aktualisieren, die eine Telefonnummer als Standardnummer haben können (falls vorhanden). Außerdem müssen Sie die vorhandenen Besprechungseinladungen dieser Benutzer aktualisieren, bevor die Zuweisung der Telefonnummer zur Audiokonferenzbrücke aufgehoben wird. 
  
Wenn die Rufnummer ohne Aktualisierung der Benutzer und ihrer Besprechungen entfernt wird, enthalten die vorhandenen Besprechungseinladungen dieser Benutzer möglicherweise eine Rufnummer, die für die Teilnahme an Besprechungen nicht mehr funktioniert.
  
Für die drei ersten Schritte müssen Sie Windows PowerShell starten. Wie Sie dazu vorgehen müssen, erfahren Sie, wenn Sie [Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md#bk_PowerShell) klicken.
  
### Schritt 1 - Aktualisieren von Benutzern, für die die Rufnummer, deren Zuweisung aufgehoben werden soll, als Standardnummer festgelegt ist

Ersetzen Sie die gebührenpflichtige oder gebührenfreie Standardnummer für alle Benutzer, für die die Nummer, deren Zuweisung aufgehoben werden soll, als Standardnummer festgelegt ist. Starten Sie den Prozess zum Neuplanen der Besprechungen dieser Benutzer. Führen Sie dazu den folgenden Befehl aus:
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

> [!NOTE]
> Je nach Größe Ihrer Organisation kann es eine Weile dauern, bis dieser Vorgang abgeschlossen ist. 
  
 **Sie können auch die gebührenpflichtige oder die gebührenfreie Standardnummer von Benutzern im Skype for Business Admin Center ändern. Dadurch werden aber ihre Besprechungen nicht automatisch neu geplant**. Weitere Informationen finden Sie unter[Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
### Schritt 2 - Anzeigen des Status der Besprechungsmigration mit Windows PowerShell

Alle Besprechungen werden neu geplant, sobald keine Vorgänge mit dem Status  *Ausstehend*  oder *In Bearbeitung*  mehr vorhanden sind.
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Weitere Informationen zu Meeting Migration Service finden Sie unter [Einrichten des Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
### Schritt 3 - Aufheben der Zuweisung der alten Telefonnummer zur Audiokonferenzbrücke

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zu **Office 365 Admin Center** > **Admin Center** > **Skype for Business** > **VoIP** > **Telefonnummern**.
    
3. Wählen Sie die Telefonnummer aus der Liste aus, und klicken Sie im Aktionsbereich auf **Zuweisung aufheben**.
    
4. Klicken Sie im Bestätigungsfenster auf **Ja**.
    
> [!IMPORTANT]
> Nachdem die Zuweisung einer Telefonnummer zu einer Audiokonferenzbrücke aufgehoben wurde, ist die Telefonnummer nicht mehr für die Teilnahme der Benutzer an neuen oder bestehenden Besprechungen verfügbar. 
  
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?
<a name="bk_PowerShell"> </a>

### So überprüfen Sie, ob Windows PowerShell bereit ist

 **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
  
1. Zum Überprüfen, ob Version 3.0 oder höher ausgeführt wird, gehen Sie wie folgt vor: Klicken Sie im Startmenü **** auf **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).
  
### So starten Sie Windows PowerShell

 **Starten einer Windows PowerShell-Sitzung**
  
1. Wechseln Sie über das Startmenü **** zu **Windows PowerShell**.
    
2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder[Herstellen der Verbindung zu Skype for Business Online mit Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
### Zeit sparen oder Automatisieren des Vorgangs

Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) oder **Set-CsOnlineDialInConferencingUserDefaultNumber** nutzen.
  
- Mit dem Cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) können Sie die gebührenpflichtige oder gebührenfreie Standardnummer für spezifische Benutzer ändern.
    
  - Führen Sie Folgendes aus, um die gebührenfreie Standardnummer für einen Benutzer zu ändern:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Ändern Sie mit dem Cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** die gebührenpflichtige oder gebührenfreie Nummer für Benutzer auf Basis ihrer ursprünglichen Standardnummer oder ihres Standorts.
    
    > [!NOTE]
    > Hinweis:Die BridgeID finden Sie mithilfe von **Get-CsOnlineDialInConferencingBridge**.
  
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
    > Der oben verwendete Standort muss mit den im Office 365 Admin Center festgelegten Kontaktinformationen der jeweiligen Benutzer übereinstimmen. 
  
### Weitere Informationen

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    

