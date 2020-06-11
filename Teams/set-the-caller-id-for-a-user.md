---
title: Festlegen der Anrufer-ID für einen Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Informieren Sie sich über die standardmäßige Rufnummernanzeige von Microsoft 365 und Office 365 (die zugewiesene Telefonnummer eines Benutzers), die auch als Anruf Leitungs-ID bezeichnet wird. Sie können die Rufnummernanzeige eines Benutzers ändern oder blockieren.
ms.openlocfilehash: 059e92f04f3d4a5df73ed9201f1f784f2bd01f30
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691121"
---
# <a name="set-the-caller-id-for-a-user"></a>Festlegen der Anrufer-ID für einen Benutzer
Das Telefon System in Microsoft 365 und Office 365 stellt eine Standard-Rufnummernanzeige für die zugewiesene Telefonnummer des Benutzers bereit. Sie können die Anrufer-ID (die auch als Anruferleitungs-ID bezeichnet wird) für einen Benutzer ändern oder blockieren. Weitere Informationen zur Verwendung der Rufnummernanzeige in Ihrer Organisation finden Sie unter [wie kann die Rufnummernanzeige in Ihrer Organisation verwendet werden](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Sie können eingehende Anrufe derzeit in Skype for Business Online nicht blockieren. 
  
Es gibt Einstellungen, die Sie ändern können:
  
> [!NOTE]
> Dies **gilt nicht** für lokale Organisationen mit Lync oder Skype for Business Server.
  
- **Ändern der ausgehenden Anrufer-ID**: Sie können die Anrufer-ID eines Benutzers - standardmäßig die Telefonnummer des Benutzers - durch eine andere Telefonnummer ersetzen. Sie können beispielsweise die Anrufer-ID des Benutzers von der Telefonnummer des Benutzers in eine Haupttelefonnummer für Ihr Unternehmen ändern, oder Sie können die Anruferleitungs-ID von der Telefonnummer des Benutzers in eine Haupttelefonnummer für die Rechtsabteilung ändern. Sie können die Anruf-ID-Nummer in jede Online- **Service** nummer (gebührenpflichtig oder gebührenfrei) ändern.
    
    > [!NOTE]
    > Wenn Sie den Parameter  _Service_ verwenden möchten, müssen Sie eine gültige Dienstnummer festlegen.
  
- **Blockieren der ausgehenden Anrufer-ID** Sie können verhindern, dass die ausgehende Rufnummernanzeige für ausgehende PSTN-Anrufe eines Benutzers gesendet wird. Dadurch wird die Anzeige der Telefonnummer am Telefon der angerufenen Person blockiert.
    
- **Blockieren der eingehenden Anrufer-ID** Sie können verhindern, dass ein Benutzer die Rufnummernanzeige bei eingehenden PSTN-anrufen empfängt.
    
> [!IMPORTANT]
> Bei Notrufen wird immer die Telefonnummer des Benutzers (Anrufer-ID) gesendet. 
  
Standardmäßig sind alle diese Anrufer-ID-Einstellungen **deaktiviert**. Dies bedeutet, dass die Telefonnummer des Skype for Business Online-Benutzers zu sehen ist, wenn der Benutzer einen Anruf bei einem PSTN-Telefon tätigt.
  
Weitere Informationen zu diesen Einstellungen und zu ihrer Verwendung finden Sie [Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Festlegen Ihrer Anrufer-ID-Richtlinieneinstellungen

> [!NOTE]
> Für alle Anrufer-ID-Einstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, und Sie können das **Skype for Business Admin Center** **nicht verwenden** . 
  
### <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
1. Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
    Wenn Sie weitere Informationen benötigen, lesen Sie [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
1. Vom **Start Menu** > **Windows PowerShell**.
    
2. Stellen Sie im **Windows PowerShell** -Fenster eine Verbindung mit Ihrem Microsoft 365 oder Office 365 her, indem Sie Folgendes ausführen:
    
   > [!NOTE]
   > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

Wenn Sie weitere Informationen zum Starten von Windows PowerShell benötigen, lesen Sie [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Einrichten Ihres Computers für Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Anzeigen aller Anrufer-ID-Richtlinieneinstellungen in Ihrer Organisation

- Wenn Sie alle Einstellungen für die Rufnummernanzeige in Ihrer Organisation anzeigen möchten, führen Sie Folgendes aus:

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Weitere Beispiele und Details finden Sie unter [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Erstellen einer neuen Anrufer-ID-Richtlinie für Ihre Organisation


- Führen Sie Folgendes aus, um eine neue Richtlinie für die Rufnummernanzeige zu erstellen, die die Rufnummernanzeige auf Anonymous festlegt:
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > In allen Fällen sollte das Feld "Servicenummer" kein "+" enthalten.

  Weitere Beispiele und Details finden Sie unter [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).
    
- Um die von Ihnen erstellte neue Richtlinie auf Amos Marble anzuwenden, führen Sie Folgendes aus:
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx)-Cmdlet.
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das Cmdlet " [festlegen-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) " verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und verwenden Sie dann das Cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) , um die Einstellungen auf die Benutzer anzuwenden.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Festlegen, dass die eingehende Anrufer-ID blockiert wird

- Um die eingehende Rufnummernanzeige zu blockieren, führen Sie Folgendes aus:
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Weitere Beispiele und Details finden Sie unter [Satz-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).
    
- Um die von Ihnen erstellte Richtlinieneinstellung auf einen Benutzer in Ihrer Organisation anzuwenden, führen Sie Folgendes aus:
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx)-Cmdlet.
    
### <a name="remove-a-caller-id-policy"></a>Entfernen einer Anrufer-ID-Richtlinie

Führen Sie Folgendes aus, um eine Richtlinie für Ihre Organisation zu entfernen:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Führen Sie Folgendes aus, um eine Richtlinie für einen Benutzer zu entfernen:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Microsoft 365 oder Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](/microsoftteams/transferring-phone-numbers-common-questions)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Mehr über Telefonnummer-ID und Name des Anrufers](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
