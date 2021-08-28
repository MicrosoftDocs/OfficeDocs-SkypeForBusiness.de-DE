---
title: Festlegen der Anrufer-ID für einen Benutzer
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Erfahren Sie mehr über Microsoft 365 und Office 365 Standardanrufer-ID (die zugewiesene Telefonnummer eines Benutzers), auch bekannt als Anruferleitungs-ID. Sie können die Anrufer-ID eines Benutzers ändern oder blockieren.
ms.openlocfilehash: 9a69cf864cbf57d7ebf82ae079f88a888d3fc9f0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613584"
---
# <a name="set-the-caller-id-for-a-user"></a>Festlegen der Anrufer-ID für einen Benutzer

Telefonsystem in Microsoft 365 stellt eine standardmäßige Anrufer-ID fest, bei der es sich um die dem Benutzer zugewiesene Telefonnummer handelt. Sie können die Anrufer-ID (die auch als Anruferleitungs-ID bezeichnet wird) für einen Benutzer ändern oder blockieren. Weitere Informationen zur Verwendung der Anrufer-ID in Ihrer Organisation finden Sie unter Verwendung der [Anrufer-ID in Ihrer Organisation.](how-can-caller-id-be-used-in-your-organization.md)
  
Standardmäßig sind die folgenden Anrufer-ID-Einstellungen **deaktiviert.** Dies bedeutet, Teams die Telefonnummer des Benutzers angezeigt wird, wenn dieser einen Anruf bei einem PSTN-Telefon anruft. Sie können diese Einstellungen wie folgt ändern:
  
- **Ausgehende Anrufer-ID** Sie können die Anrufer-ID eines Benutzers, bei der es sich standardmäßig um die Telefonnummer des Benutzers handelt, durch eine andere Telefonnummer ersetzen. So können Sie beispielsweise die Anrufer-ID des Benutzers von seiner Telefonnummer zu einer Haupttelefonnummer für Ihr Unternehmen oder zu einer Haupttelefonnummer für die Rechtsabteilung ändern. Darüber hinaus können Sie die Anruf-ID-Nummer auf eine beliebige Online-Servicenummer (gebührenpflichtig oder gebührenfrei) oder auf eine lokale Telefonnummer über Direct Routing festlegen, die einem Ressourcenkonto zugewiesen ist, das von einer automatische Telefonzentrale- oder Anrufwarteschleife verwendet wird.
    
  > [!NOTE]
  > Wenn Sie den Parameter *Service verwenden möchten,* müssen Sie eine gültige Dienstnummer angeben.
  > Sie müssen die PowerShell-Cmdlets New-CsCallingLineIdentity oder Set-CsCallingLineIdentity im Teams PowerShell-Modul 2.3.1 oder höher für die Kontonummer der Ressource verwenden, wenn sie nicht in der Dropdownliste angezeigt wird.
  
- **Blockieren der ausgehenden Anrufer-ID** Sie können blockieren, dass die ausgehende Anrufer-ID bei ausgehenden PSTN-Anrufen eines Benutzers gesendet wird. Dadurch wird die Anzeige der Telefonnummer am Telefon der angerufenen Person blockiert.
    
- **Eingehende Anrufer-ID blockieren.** Sie können für einen Benutzer blockieren, dass er bei eingehenden PSTN-Anrufen die Anrufer-ID erhält.

- **Legen Sie den Namen einer Anrufparty (CNAM) fest.** Für Ihre Microsoft Teams können Sie bei ausgehenden PSTN-Anrufen CNAM senden.
    
> [!IMPORTANT]
> Bei Notrufen wird immer die Telefonnummer des Benutzers (Anrufer-ID) gesendet. 
  

  
Weitere Informationen zu diesen Einstellungen und deren Verwendung finden Sie unter Verwendung der [Anrufer-ID in Ihrer Organisation.](how-can-caller-id-be-used-in-your-organization.md)
  
## <a name="set-your-caller-id-policy-settings"></a>Festlegen Ihrer Anrufer-ID-Richtlinieneinstellungen

> [!NOTE]
> Verwenden Sie die PowerShell-Cmdlets New-CsCallingLineIdentity oder Set-CsCallingLineIdentity im Teams PowerShell-Modul 2.3.1 oder höher, um die Anrufer-ID auf die Telefonnummer eines Ressourcenkontos und den Namen des Anrufers zu setzen. (Diese Optionen sind derzeit nicht im Microsoft Teams Admin Center verfügbar.) 

Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus:

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>Anzeigen, Erstellen und Anwenden von Richtlinieneinstellungen

1. Führen Sie zum Anzeigen aller Anrufer-ID-Richtlinieneinstellungen in Ihrer Organisation:

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   Weitere Informationen finden Sie unter [Get-CsCallingLineIdentity.](/powershell/module/skype/Get-CsCallingLineIdentity)
    
2. Verwenden Sie zum Erstellen einer neuen Anrufer-ID-Richtlinie für Ihre Organisation das New-CsCallingIdentity-Cmdlet:
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    In allen Fällen sollte das Feld "Servicenummer" kein "+" enthalten.

   Weitere Informationen finden Sie unter [New-CsCallingLineIdentity.](/powershell/module/skype/New-CsCallingLineIdentity)
    
3. Wenden Sie die neue Richtlinie an, die Sie mithilfe des cmdlets Grant-CsCallingIdentity erstellt haben. Im folgenden Beispiel wird beispielsweise die neue Richtlinie auf den Benutzer Amos Marble angewendet.
    
     ```PowerShell
     Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   Weitere Informationen finden Sie unter [Grant-CsCallingLineIdentity-Cmdlet.](/powershell/module/skype/Grant-CsCallingLineIdentity)
    

4. Wenn Sie die eingehende Anrufer-ID blockieren möchten, führen Sie dies aus:
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   Weitere Informationen finden Sie unter [Set-CsCallingLineIdentity.](/powershell/module/skype/Set-CsCallingLineIdentity)
    
5. Um die von Ihnen erstellte Richtlinieneinstellung auf einen Benutzer in Ihrer Organisation anzuwenden, führen Sie die
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   Weitere Informationen finden Sie unter [Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)

6. So erstellen Sie eine neue Anrufer-ID-Richtlinie, die die Anrufer-ID auf die Telefonnummer des angegebenen Ressourcenkontos und den Namen der Anrufergruppe auf Contoso legt:

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das [Cmdlet Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und dann das [Grant-CsCallingLineIdentity-Cmdlet](/powershell/module/skype/Grant-CsCallingLineIdentity) verwenden, um die Einstellungen auf Ihre Benutzer anzuwenden.
    
### <a name="remove-a-policy-setting"></a>Entfernen einer Richtlinieneinstellung

Führen Sie Folgendes aus, um eine Richtlinie für Ihre Organisation zu entfernen:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Führen Sie Folgendes aus, um eine Richtlinie für einen Benutzer zu entfernen:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Ihre Microsoft 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
- [Eine Einführung in Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center gegenüber Geschwindigkeit, Einfachheit und Produktivität viele Vorteile, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
- [Beste Möglichkeiten zum Verwalten von Microsoft 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](./phone-number-calling-plans/port-order-overview.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Mehr über Telefonnummer-ID und Name des Anrufers](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
