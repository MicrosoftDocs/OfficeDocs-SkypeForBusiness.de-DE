---
title: Festlegen der Anrufer-ID für einen Benutzer
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Erfahren Sie mehr über die standardmäßige Anrufer-ID von Microsoft 365 und Office 365 (die zugewiesene Telefonnummer eines Benutzers), auch bekannt als Anrufleitungs-ID. Sie können die Anrufer-ID eines Benutzers ändern oder blockieren.
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569417"
---
# <a name="set-the-caller-id-for-a-user"></a>Festlegen der Anrufer-ID für einen Benutzer
Das Telefonsystem in Microsoft 365 und Office 365 stellt eine Standardanruf-ID zur Verwendung, die die vom Benutzer zugewiesene Telefonnummer ist. Sie können die Anrufer-ID (die auch als Anruferleitungs-ID bezeichnet wird) für einen Benutzer ändern oder blockieren. Weitere Informationen zur Verwendung der Anrufer-ID in Ihrer Organisation finden Sie unter So kann die [Anrufer-ID in Ihrer Organisation verwendet werden.](how-can-caller-id-be-used-in-your-organization.md)
  
> [!TIP]
> Sie können eingehende Anrufe derzeit in Skype for Business Online nicht blockieren. 
  
Es gibt Einstellungen, die Sie ändern können:
  
> [!NOTE]
> Dies **gilt nicht** für lokale Organisationen mit Lync oder Skype for Business Server.
  
- **Ändern der ausgehenden Anrufer-ID**: Sie können die Anrufer-ID eines Benutzers - standardmäßig die Telefonnummer des Benutzers - durch eine andere Telefonnummer ersetzen. Sie können beispielsweise die Anrufer-ID des Benutzers von der Telefonnummer des Benutzers in eine Haupttelefonnummer für Ihr Unternehmen ändern, oder Sie können die Anruferleitungs-ID von der Telefonnummer des Benutzers in eine Haupttelefonnummer für die Rechtsabteilung ändern. Sie können die Anruf-ID-Nummer in jede Online- **Service** nummer (gebührenpflichtig oder gebührenfrei) ändern.
    
    > [!NOTE]
    > Wenn Sie den Parameter  _Service_ verwenden möchten, müssen Sie eine gültige Dienstnummer festlegen.
  
- **Blockieren der ausgehenden Anrufer-ID** Sie können blockieren, dass die ausgehende Anrufer-ID für ausgehende PSTN-Anrufe eines Benutzers gesendet wird. Dadurch wird die Anzeige der Telefonnummer am Telefon der angerufenen Person blockiert.
    
- **Blockieren der eingehenden Anrufer-ID** Sie können einen Benutzer am Empfang der Anrufer-ID bei eingehenden PSTN-Anrufen blockieren.
    
> [!IMPORTANT]
> Bei Notrufen wird immer die Telefonnummer des Benutzers (Anrufer-ID) gesendet. 
  
Standardmäßig sind alle diese Anrufer-ID-Einstellungen **deaktiviert**. Dies bedeutet, dass die Telefonnummer des Skype for Business Online-Benutzers zu sehen ist, wenn der Benutzer einen Anruf bei einem PSTN-Telefon tätigt.
  
Weitere Informationen zu diesen Einstellungen und zu ihrer Verwendung finden Sie [Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Festlegen Ihrer Anrufer-ID-Richtlinieneinstellungen

> [!NOTE]
> Für alle Anrufer-ID-Einstellungen in Skype for Business Online müssen  Sie Windows PowerShell verwenden, und Sie können das **Skype for Business Admin Center nicht verwenden.** 
  
### <a name="start-powershell"></a>Starten von PowerShell

- Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Anzeigen aller Anrufer-ID-Richtlinieneinstellungen in Ihrer Organisation

- Führen Sie zum Anzeigen aller Anrufer-ID-Richtlinieneinstellungen in Ihrer Organisation aus:

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Weitere Beispiele und Details finden Sie unter [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Erstellen einer neuen Anrufer-ID-Richtlinie für Ihre Organisation


- Führen Sie zum Erstellen einer neuen Anrufer-ID-Richtlinie aus, die die Anrufer-ID auf anonym legt:
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > In allen Fällen sollte das Feld "Servicenummer" kein "+" enthalten.

  Weitere Beispiele und Details finden Sie unter [New-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793855.aspx)
    
- Führen Sie zum Anwenden der neuen Richtlinie, die Sie erstellt haben, auf Amos Marble aus:
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx)-Cmdlet.
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das [Cmdlet Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und dann das [Grant-CsCallingLineIdentity-Cmdlet](https://technet.microsoft.com/library/mt793857.aspx) verwenden, um die Einstellungen auf Ihre Benutzer anzuwenden.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Festlegen, dass die eingehende Anrufer-ID blockiert wird

- Führen Sie zum Blockieren der eingehenden Anrufer-ID aus:
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Weitere Beispiele und Details finden Sie unter [Set-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793854.aspx)
    
- Führen Sie zum Anwenden der von Ihnen erstellten Richtlinieneinstellung auf einen Benutzer in Ihrer Organisation aus:
    
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

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe, warum Sie microsoft Windows PowerShell Office 365 oder Office 365 verwalten möchten](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](/microsoftteams/transferring-phone-numbers-common-questions)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Mehr über Telefonnummer-ID und Name des Anrufers](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
