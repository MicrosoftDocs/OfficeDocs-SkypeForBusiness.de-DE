---
title: "Festlegen der Anrufer-ID für einen Benutzer"
ms.author: tonysmit
author: tonysmit
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
description: "Das Telefonsystem in Office 365 bietet eine standardmäßige Anrufer-ID, die Ihnen zugewiesenen Telefonnummer des Benutzers ist. Sie können ändern oder die Anrufer-ID (auch als eine aufrufen Linie ID bezeichnet) für einen Benutzer sperren. Weitere Informationen zum Anrufer-ID in Ihrer Organisation verwenden, indem Sie wechseln Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation."
---

# Festlegen der Anrufer-ID für einen Benutzer

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](c7323490-d9b7-421a-aa76-5bd485f80583.md#MT_Footer).  
  
Das Telefonsystem in Office 365 bietet eine standardmäßige Anrufer-ID, die Ihnen zugewiesenen Telefonnummer des Benutzers ist. Sie können ändern oder die Anrufer-ID (auch als eine aufrufen Linie ID bezeichnet) für einen Benutzer sperren. Weitere Informationen zum Anrufer-ID in Ihrer Organisation verwenden, indem Sie wechseln [Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Sie können keine eingehenden Anrufe derzeit in Skype für Business Online blockieren. 
  
Es gibt Einstellungen, die Sie ändern können:
  
> [!NOTE]
> Dies **gilt nicht** für lokale Organisationen mit Lync oder Skype for Business Server.
  
- **Ändern der ausgehenden Anrufer-ID**: Sie können die Anrufer-ID eines Benutzers - standardmäßig die Telefonnummer des Benutzers - durch eine andere Telefonnummer ersetzen. Sie können beispielsweise die Anrufer-ID des Benutzers von der Telefonnummer des Benutzers in eine Haupttelefonnummer für Ihr Unternehmen ändern, oder Sie können die Anruferleitungs-ID von der Telefonnummer des Benutzers in eine Haupttelefonnummer für die Rechtsabteilung ändern. Sie können die Anruf-ID-Nummer in jede Online- **Service** nummer (gebührenpflichtig oder gebührenfrei) ändern.
    
    > [!NOTE]
    > Wenn Sie den Parameter  _Service_ verwenden möchten, müssen Sie eine gültige Dienstnummer festlegen.
  
- **Blockieren von deren ausgehenden Anrufer-ID** Sie können die ausgehenden Anrufer-ID bei ausgehenden PSTN-Anrufen eines Benutzers gesendet blockieren. Auf diese Weise blockiert ihre Telefonnummer angezeigt wird, auf dem Mobiltelefon einer Person aufgerufen wird.
    
- **Blockieren ihrer eingehenden Anrufer-ID** Sie können einen Benutzer aus, die Anrufer-ID auf alle eingehenden PSTN-Anrufe empfangen blockieren.
    
> [!IMPORTANT]
> Bei Notrufen wird immer die Telefonnummer des Benutzers (Anrufer-ID) gesendet. 
  
Standardmäßig sind alle diese Anrufer-ID-Einstellungen **deaktiviert**. Dies bedeutet, dass die Telefonnummer des Skype for Business Online-Benutzers zu sehen ist, wenn der Benutzer einen Anruf bei einem PSTN-Telefon tätigt.
  
Weitere Informationen zu diesen Einstellungen und zu ihrer Verwendung finden Sie [Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation](how-can-caller-id-be-used-in-your-organization.md).
  
## Festlegen Ihrer Anrufer-ID-Richtlinieneinstellungen

> [!NOTE]
> Für alle die Anrufer-ID-Einstellungen in Skype for Business Online müssen Sie Windows PowerShell und Sie **kann nicht verwendet werden**, die **Skype für Business-Verwaltungskonsole** verwenden.
  
### Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
1. Zum Überprüfen, ob Version 3.0 oder höher ausgeführt wird, gehen Sie wie folgt vor: Klicken Sie im Startmenü **** auf **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
    Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
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
    
### Anzeigen aller Anrufer-ID-Richtlinieneinstellungen in Ihrer Organisation

- Wenn alle Einstellungen Richtlinie Anrufer-ID in Ihrer Organisation anzeigen möchten, führen Sie Folgendes aus:
    
  - 
  ```
  Get-CsCallingLineIdentity |fl
  ```

    [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx)finden Sie weitere Beispiele und Details.
    
### Erstellen einer neuen Anrufer-ID-Richtlinie für Ihre Organisation

- Führen Sie zum Erstellen einer neuen Anrufer-ID-Richtlinie, die die Anrufer-ID für anonyme legt fest:
    
  - 
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

    [Neu-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)finden Sie weitere Beispiele und Details.
    
- Um die neue Richtlinie erstellten auf Amos Marble anwenden möchten, führen Sie Folgendes aus:
    
  - 
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```

    Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)-Cmdlet.
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden das Cmdlet " [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) " So ändern Sie die vorhandene Richtlinie, und verwenden Sie dann das Cmdlet[Erteilen-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) zum Anwenden die Einstellungen für Ihre Benutzer.
  
### Festlegen, dass die eingehende Anrufer-ID blockiert wird

- Um die eingehenden Anrufer-ID, blockieren möchten, führen Sie Folgendes aus:
    
  - 
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```

    [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)finden Sie weitere Beispiele und Details.
    
- Um die richtlinieneinstellung erstellten auf ein Benutzer in Ihrer Organisation anwenden möchten, führen Sie Folgendes aus:
    
  - 
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```

    Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)-Cmdlet.
    
### Entfernen einer Anrufer-ID-Richtlinie

Führen Sie Folgendes aus, um eine Richtlinie für Ihre Organisation zu entfernen:
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```

Führen Sie Folgendes aus, um eine Richtlinie für einen Benutzer zu entfernen:
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```

## Möchten Sie mehr über Windows PowerShell erfahren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Verwandte Themen

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)
  
[Audio-Konferenzen Grußformeln durchführen Periode](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

