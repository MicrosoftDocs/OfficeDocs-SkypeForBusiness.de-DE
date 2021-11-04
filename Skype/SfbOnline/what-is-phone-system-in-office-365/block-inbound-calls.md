---
title: Eingehende Anrufe in Skype for Business Online blockieren
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: 6fa72103448d20d9c659eff32735fa5d14389509
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751394"
---
# <a name="block-inbound-calls"></a>Blockieren eingehender Anrufe

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business-Online-Anrufpläne unterstützen jetzt das Blockieren eingehender Anrufe aus dem öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN). Mit diesem Feature kann eine globale Mandantenliste mit Nummernmustern definiert werden,, sodass die Anrufer-ID jedes eingehenden PSTN-Anrufs an den Mandanten anhand der Liste auf eine Übereinstimmung überprüft werden kann. Wenn eine Übereinstimmung erfolgt, wird ein eingehender Anruf abgelehnt.

Dieses Feature zum Blockieren eingehender Anrufe funktioniert nur bei eingehenden Anrufen, die aus dem PSTN stammen, und funktioniert nur auf Mandanten-globaler Basis. Nicht auf Pro-Benutzer-Basis verfügbar.  

Diese Funktion ist für Direct Routing noch nicht verfügbar.

>[!NOTE]
> Blockierte Anrufer können ein etwas anderes Verhalten erfahren, wenn sie blockiert wurden. Das Verhalten basiert darauf, wie der Betreiber des blockierten Anrufers die Benachrichtigung behandelt, dass der Anruf nicht erfolgreich abgeschlossen werden darf. Beispiele für Netzbetreibernachrichten können besagen, dass der Anruf nicht über die gewählte Nummer abgeschlossen werden kann, oder der Anruf wird einfach beendet.

## <a name="call-blocking-admin-controls-and-information"></a>Administratorsteuerelemente und Informationen zum Blockieren von Anrufen

Admin-Steuerelemente zum Blockieren von Nummern werden nur mit PowerShell bereitgestellt. Nummernblockmuster werden als Muster für reguläre Ausdrücke definiert. Die Reihenfolge der Ausdrücke ist unwichtig – das erste übereinstimmende Muster in der Liste führt zur Sperrung des Anrufs. Es kann bis zu 24 Stunden dauern, bis eine neue Nummer oder ein neues Muster in der Liste blockierter Anrufer hinzugefügt oder entfernt wird, und bis das Muster aktiv wird.

## <a name="call-blocking-powershell-commands"></a>Anrufblockierende PowerShell-Befehle

Zahlenmuster werden über die ```CsInboundBlockedNumberPattern``` Befehle ```New```, ```Get```, ```Set```und ```Remove``` verwaltet. Sie können ein bestimmtes Muster mithilfe dieser Cmdlets verwalten, einschließlich der Möglichkeit, die Aktivierung eines bestimmten Musters umzuschalten.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) gibt eine Liste aller blockierten Nummernmuster wieder, die der Mandantenliste hinzugefügt wurden, einschließlich Name, Beschreibung, Aktiviert (Wahr/Falsch) und das jeweilige Muster.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) fügt der Mandantenliste ein blockiertes Nummernmuster hinzu.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) entfernt ein blockiertes Nummernmuster aus der Mandantenliste.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) ändert einen oder mehrere Parameter eines gesperrten Nummernmusters in der Mandantenliste.

Das Anzeigen und Aktivieren der gesamten Anrufblockierungsfunktion wird über die ```CsTenantBlockingCallingNumbers``` Befehle ```Get``` und ```Set``` verwaltet.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) gibt die Parameter für die globale Liste der blockierten Nummern einschließlich Enabled (True/False) zurück. Es gibt eine einzelne globale Mandantenrichtlinie, die nur manuell geändert werden kann, außer das Feature ein- oder auszuschalten.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) ermöglicht das Ändern der globalen vom Mandanten blockierten Anrufe, sodass sie auf Mandantenebene ein- und ausgeschaltet werden.

### <a name="examples"></a>Beispiele

#### <a name="block-a-number"></a>Eine Telefonnummer blockieren

In diesem Beispiel sind die Parameter ```-Enabled``` und ```-Description``` optional:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

Beim Erstellen eines neuen Musters wird das Muster standardmäßig als aktiviert hinzugefügt. Die Beschreibung ist ein optionales Feld, um weitere Informationen bereitzustellen.

Wir empfehlen Ihnen, einen aussagekräftigen Namen anzugeben, der es leicht verständlich macht, warum das Muster hinzugefügt wurde. Wenn Sie Spam-Nummern einfach blockieren, sollten Sie die Regel genauso benennen wie das Nummernmuster, das abgeglichen wird, und bei Bedarf zusätzliche Informationen in die Beschreibung einfügen.

Muster werden mit regulären Ausdrücken (RegEx) abgeglichen. Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.

#### <a name="allow-a-number"></a>Eine Telefonnummer zulassen

In diesem Beispiel ist der Parameter ```-Identity``` erforderlich:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Wenn die Identität nicht bekannt ist, verwenden Sie das Cmdlet ```Get-CsInboundBlockedNumberPattern```, um zuerst das richtige Muster zu finden und die Identität zu notieren. Führen Sie dann das Cmdlet ```Remove-CsTenantBlockedNumberPattern``` aus und übergeben Sie den entsprechenden Identitätswert.

Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.

#### <a name="view-all-number-patterns"></a>Alle Nummernmuster anzeigen

Durch Ausführen dieses Cmdlets wird eine Liste aller für einen Mandanten eingegebene blockierte Nummern wiedergegeben:

```powershell
Get-CsInboundBlockedNumberPattern
```

Verwenden Sie integrierte PowerShell-Filterfunktionen, um die wiedergegebenen Werte nach Bedarf zu analysieren.

## <a name="add-number-exceptions"></a>Ausnahmen für Telefonnummern hinzufügen

Sie können mit den Befehlen ```CsTenantBlockNumberExceptionPattern``` ```New```, ```Get```, ```Set``` und ```Remove``` Ausnahmen zu blockierten Zahlenmustern hinzufügen.

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) fügt der Mandantenliste ein Nummernausnahmemuster hinzu. 
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) gibt eine Liste aller Nummernausnahmemuster wieder, die der Mandantenliste hinzugefügt wurden.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) ändert einen oder mehrere Parameter in ein Nummernausnahmemuster in der Mandantenliste.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) entfernt ein Nummernausnahmemuster aus der Mandantenliste.

### <a name="examples"></a>Beispiele

#### <a name="add-a-number-exception"></a>Nummernausnahme hinzufügen

In diesem Beispiel wird ein neues Nummernausnahmemuster erstellt und das Muster standardmäßig als aktiviert hinzugefügt. Die Parameter ```-Enabled``` und ```-Description``` sind optional.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Alle Nummernausnahmen anzeigen

In diesem Beispiel ist der Parameter -Identität optional. Wenn der Parameter ```-Identity``` nicht angegeben wird, gibt dieses Cmdlet eine Liste aller Nummernausnahmemuster zurück, die für einen Mandanten eingegeben wurden.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Nummernausnahme ändern

In diesem Beispiel ist der Parameter -Identität obligatorisch. Mit dem Cmdlet ```Set-CsTenantBlockedNumberExceptionPattern``` können Sie einen oder mehrere Parameter für eine bestimmte Zahlenmusteridentität ändern.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Zahlenausnahme ändern

In diesem Beispiel ist der Parameter ```-Identity``` erforderlich. Mit diesem Cmdlet wird das angegebene Nummernmuster aus der Mandantenliste entfernt.  Wenn die Identität nicht bekannt ist, verwenden Sie das Cmdlet ```Get-CsInboundBlockedNumberPattern```, um zuerst das richtige Muster zu finden und die Identität zu notieren. Führen Sie dann das Cmdlet ```Remove-CsTenantBlockedNumberExceptionPattern``` aus und übergeben Sie den entsprechenden Identitätswert.Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testen, ob eine Zahl blockiert ist

Verwenden Sie das Cmdlet ```Test-CsInboundBlockedNumberPattern```, um zu überprüfen, ob eine Nummer im Mandanten blockiert ist.
 
In diesem Beispiel sind die Parameter ```-Phonenumber``` und ```-Tenant``` erforderlich. Der Parameter ```-PhoneNumber``` sollte eine numerische Zeichenfolge ohne zusätzliche Zeichen wie + oder - sein. Bei TRPS ist ```-Tenant parameter``` optional. Der resultierende Parameter ```isNumberBlocked``` gibt den Wert True zurück, wenn die Nummer im Mandanten blockiert ist, und False, wenn sie nicht blockiert ist.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |ErrorMessage |
|---------|---------|---------|
|200    | Wahr        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |ErrorMessage |
|---------|---------|---------|
|200    | Falsch        |         |

## <a name="a-note-about-regex"></a>Ein Hinweis zu RegEx

Wie bereits erwähnt, erfolgt der Musterabgleich zum Blockieren von Anrufern mithilfe von RegEx. Mehrere Tools sind online verfügbar, um eine RegEx-Musterübereinstimmung zu überprüfen. Wenn Sie mit RegEx-Mustern nicht vertraut sind, empfehlen wir Ihnen, sich etwas Zeit zu nehmen, um sich mit den Grundlagen vertraut zu machen. Um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten, verwenden Sie ein Tool zum Überprüfen von Musterübereinstimmungen, bevor Sie Ihrem Mandanten neue Übereinstimmungen mit blockierten Nummern hinzufügen. 

## <a name="related-topics"></a>Verwandte Themen

- [Richten Sie Ihren Computer ein, um Skype for Business Online mithilfe von Windows PowerShell zu verwalten](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
