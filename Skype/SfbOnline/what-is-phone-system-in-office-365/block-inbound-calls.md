---
title: Blockieren eingehender Anrufe in Skype for Business Online
ms.author: v-cichur
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
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: ff1dfa87d6b88cdcab46a6ea080b2aa8b61d3ba757ab922ae04f2b4b2d2aa70d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342540"
---
# <a name="block-inbound-calls"></a>Blockieren eingehender Anrufe

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Online-Anrufpläne unterstützen jetzt das Blockieren eingehender Anrufe aus dem öffentlichen Telefonnetz (PSTN). Mit diesem Feature kann eine globale Mandantenliste mit Nummernmustern definiert werden, damit die Anrufer-ID jedes eingehenden PSTN-Anrufs an den Mandanten auf eine Übereinstimmung hin überprüft werden kann. Wenn eine Übereinstimmung vorgenommen wird, wird ein eingehender Anruf abgelehnt.

Diese Funktion zum Blockieren eingehender Anrufe funktioniert nur bei eingehenden Anrufen, die aus dem PSTN stammen, und funktioniert nur auf Mandanten-global. Sie steht pro Benutzer nicht zur Verfügung.  

Dieses Feature ist für Direct-Routing noch nicht verfügbar.

>[!NOTE]
> Blockierte Anrufer können ein leicht anderes Verhalten erleben, wenn sie blockiert wurden. Das Verhalten basiert darauf, wie der Netzbetreiber des blockierten Anrufers die Benachrichtigung verarbeitet, dass der Anruf nicht erfolgreich abgeschlossen werden kann. Beispiele hierfür sind eine Meldung des Netzbetreibers, die besagt, dass der Anruf nicht als gewählt abgeschlossen werden kann, oder dass der Anruf einfach beendet werden kann.

## <a name="call-blocking-admin-controls-and-information"></a>Blockieren von Administratorsteuerelementen und -informationen für Anrufe

Administratorsteuerelemente zum Blockieren von Nummern werden nur mithilfe von PowerShell bereitgestellt. Zahlenblockmuster sind als reguläre Ausdrucksmuster definiert. Die Reihenfolge der Ausdrücke ist unwichtig – das erste Muster, das in der Liste abgesenert wurde, führt dazu, dass der Aufruf blockiert wird. Es kann bis zu 24 Stunden dauern, bis eine neue Nummer oder ein neues Muster in der Liste blockierter Anrufer hinzugefügt oder entfernt wird, bis das Muster aktiv wird.

## <a name="call-blocking-powershell-commands"></a>Blockieren von PowerShell-Befehlen für Anrufe

Zahlenmuster werden mit den ```CsInboundBlockedNumberPattern``` Befehlen ```New``` , , ```Get``` und ```Set``` ```Remove``` verwaltet. Sie können ein bestimmtes Muster mithilfe dieser Cmdlets verwalten, einschließlich der Möglichkeit, die Aktivierung eines bestimmten Musters umschalten.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) gibt eine Liste aller blockierten Zahlenmuster zurück, die zur Mandantenliste hinzugefügt wurden, einschließlich Name, Beschreibung, Aktiviert (Wahr/Falsch) und Muster für jeden.
- [New-CsInboundBlockedNumberPattern fügt](/powershell/module/skype/new-csinboundblockednumberpattern) der Mandantenliste ein Muster für blockierte Zahlen hinzu.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) entfernt ein blockiertes Zahlenmuster aus der Mandantenliste.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) ändert einen oder mehrere Parameter eines Musters blockierter Zahlen in der Mandantenliste.

Das Anzeigen und Aktivieren des gesamten Anrufblockerfeatures wird über die ```CsTenantBlockingCallingNumbers``` Befehle und ```Get``` ```Set``` verwaltet.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) gibt die Parameter für die globale Liste blockierter Zahlen zurück, einschließlich Enabled (True/False). Es gibt eine einzige globale Mandantenrichtlinie, die nur zum Aktivieren oder Deaktivieren des Features manuell geändert werden kann.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) ermöglicht das Ändern der blockierten Anrufe des globalen Mandanten, damit diese auf Mandantenebene aktiviert und deaktiviert werden.

### <a name="examples"></a>Beispiele

#### <a name="block-a-number"></a>Blockieren einer Zahl

In diesem Beispiel sind die ```-Enabled``` Parameter und ```-Description``` optional:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

Durch das Erstellen eines neuen Musters wird das Muster standardmäßig aktiviert. Die Beschreibung ist ein optionales Feld, das weitere Informationen enthält.

Es wird empfohlen, einen aussagekräftigen Namen ein geben, um zu verstehen, warum das Muster hinzugefügt wurde. Falls Sie Spamnummern einfach blockieren, sollten Sie erwägen, die Regel wie das übereinstimmende Zahlenmuster zu benennen und der Beschreibung bei Bedarf zusätzliche Informationen hinzuzufügen.

Muster werden mithilfe von reguläre Ausdrücke (Regex) abgestimmt. Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.

#### <a name="allow-a-number"></a>Nummer zulassen

In diesem Beispiel ist ```-Identity``` der -Parameter erforderlich:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Wenn die Identität nicht bekannt ist, verwenden Sie das Cmdlet, um zuerst das richtige Muster zu finden ```Get-CsInboundBlockedNumberPattern``` und sich die Identität zu notieren. Führen Sie dann das ```Remove-CsTenantBlockedNumberPattern``` Cmdlet aus, und übergeben Sie den entsprechenden Identitätswert.

Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.

#### <a name="view-all-number-patterns"></a>Anzeigen aller Zahlenmuster

Wenn Sie dieses Cmdlet ausführen, wird eine Liste aller blockierten Nummern zurückgegeben, die für einen Mandanten eingegeben wurden:

```powershell
Get-CsInboundBlockedNumberPattern
```

Verwenden Sie die integrierten PowerShell-Filterfunktionen, um die zurückgegebenen Werte wie erforderlich zu analysieren.

## <a name="add-number-exceptions"></a>Hinzufügen von Nummernausnahmen

Ausnahmen zu blockierten Zahlenmustern können Sie mit den Befehlen ```CsTenantBlockNumberExceptionPattern``` ```New``` , , und ```Get``` ```Set``` ```Remove``` hinzufügen.

- [New-CsTenantBlockedNumberExceptionPattern fügt](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) der Mandantenliste ein Nummernausnahmemuster hinzu. 
- [Get-CsTenantBlockedNumberExceptionPattern gibt](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) eine Liste aller Zahlenausnahmemuster zurück, die der Mandantenliste hinzugefügt wurden.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) ändert einen oder mehrere Parameter in ein Nummernausnahmemuster in der Mandantenliste.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) entfernt ein Nummernausnahmemuster aus der Mandantenliste.

### <a name="examples"></a>Beispiele

#### <a name="add-a-number-exception"></a>Hinzufügen einer Zahlenausnahme

In diesem Beispiel wird ein neues Nummernausnahmemuster erstellt und das Muster standardmäßig als aktiviert hinzugefügt. Die ```-Enabled``` Parameter und sind ```-Description``` optional.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Alle Zahlenausnahmen anzeigen

In diesem Beispiel ist der Parameter -Identity optional. Wenn der -Parameter nicht angegeben ist, gibt dieses Cmdlet eine Liste aller Zahlenausnahmemuster zurück, die ```-Identity``` für einen Mandanten eingegeben wurden.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Ändern einer Zahlenausnahme

In diesem Beispiel ist der Parameter -Identity obligatorisch. Mit ```Set-CsTenantBlockedNumberExceptionPattern``` dem Cmdlet können Sie Parameter für eine bestimmte Zahlenmusteridentität ändern.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Entfernen einer Zahlenausnahme

In diesem Beispiel ist ```-Identity``` der -Parameter erforderlich. Dieses Cmdlet entfernt das angegebene Zahlenmuster aus der Mandantenliste.  Wenn die Identität nicht bekannt ist, verwenden Sie das Cmdlet, um zuerst das richtige Muster zu finden ```Get-CsInboundBlockedNumberPattern``` und sich die Identität zu notieren. Führen Sie dann das ```Remove-CsTenantBlockedNumberExceptionPattern``` Cmdlet aus, und übergeben Sie den entsprechenden Identitätswert.Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testen, ob eine Nummer blockiert ist

Verwenden Sie ```Test-CsInboundBlockedNumberPattern``` das Cmdlet, um zu überprüfen, ob eine Nummer im Mandanten blockiert ist.
 
In diesem Beispiel sind die ```-Phonenumber``` Parameter und ```-Tenant``` erforderlich. Der -Parameter sollte eine numerische Zeichenfolge ohne zusätzliche Zeichen wie ```-PhoneNumber``` + oder - sein. In TRPS ist ```-Tenant parameter``` optional. Der resultierende Parameter gibt den Wert True zurück, wenn die Zahl im Mandanten blockiert ist, und False, wenn ```isNumberBlocked``` sie nicht blockiert ist.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Wahr        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Falsch        |         |

## <a name="a-note-about-regex"></a>Hinweis zu Regex

Wie bereits erwähnt, erfolgt der Musterabgleich zum Blockieren von Anrufern mithilfe von Regex. Online stehen mehrere Tools zur Überprüfung einer Regex-Muster übereinstimmung zur Verfügung. Wenn Sie mit Regex-Mustern nicht vertraut sind, sollten Sie sich etwas Zeit nehmen, um sich mit den Grundlagen vertraut zu machen. Um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten, verwenden Sie ein Tool zum Überprüfen von Musterdingingen, bevor Sie Ihrem Mandanten neue Übereinstimmungen mit blockierten Nummern hinzufügen. 

## <a name="related-topics"></a>Verwandte Themen

- [Einrichten Ihres Computers zum Verwalten von Skype for Business Online mithilfe von Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
