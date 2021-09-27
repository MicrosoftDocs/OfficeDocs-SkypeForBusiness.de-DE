---
title: Eingehende Anrufe in Microsoft Teams blockieren
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: 6388c65e5f2c8600c263153b1a943bf485670fe4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631429"
---
# <a name="block-inbound-calls"></a>Blockieren eingehender Anrufe

Microsoft-Anrufpläne, Direct Routing und Telefonieanbieter unterstützen alle das Blockieren eingehender Anrufe aus dem öffentlichen Telefonnetz (PSTN). Mit dieser Funktion kann ein Administrator eine Liste von Nummernmustern auf globaler Ebene des Mandanten definieren, sodass die Anrufer-ID jedes eingehenden PSTN-Anrufs an den Mandanten mit der Liste auf Übereinstimmung geprüft werden kann. Wenn eine Übereinstimmung erfolgt, wird ein eingehender Anruf abgelehnt.

Diese Funktion zum Blockieren eingehender Anrufe funktioniert nur bei eingehenden Anrufen, die aus dem PSTN stammen, und funktioniert nur auf globaler Mandantenebene. Einzelne Teams-Benutzer können diese Liste nicht bearbeiten. Der Teams-Client ermöglicht es einzelnen Benutzern, PSTN-Anrufe zu blockieren. Informationen dazu, wie Ihre Endbenutzer die Anrufblockierung implementieren können, finden Sie unter [Anrufeinstellungen in Teams verwalten](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).

>[!NOTE]
> Blockierte Anrufer können geringfügig unterschiedliche Verhaltensweisen aufweisen, nachdem sie blockiert wurden. Das Verhalten basiert darauf, wie der Betreiber des blockierten Anrufers die Benachrichtigung behandelt, dass der Anruf nicht erfolgreich abgeschlossen werden darf. Beispiele für Netzbetreibernachrichten können besagen, dass der Anruf nicht über die gewählte Nummer abgeschlossen werden kann, oder der Anruf wird einfach beendet.

## <a name="call-blocking-admin-controls-and-information"></a>Administratorsteuerelemente und Informationen zum Blockieren von Anrufen

Admin-Steuerelemente zum Blockieren von Nummern werden nur mit PowerShell bereitgestellt. Nummernblockmuster werden als Muster für reguläre Ausdrücke definiert. Die Reihenfolge der Ausdrücke ist unwichtig – das erste übereinstimmende Muster in der Liste führt zur Sperrung des Anrufs. Es kann bis zu 24 Stunden dauern, bis eine neue Nummer oder ein neues Muster in der Liste blockierter Anrufer hinzugefügt oder entfernt wird, und bis das Muster aktiv wird.

## <a name="call-blocking-powershell-commands"></a>Anrufblockierende PowerShell-Befehle

Sie verwalten Zahlenmuster mit den Cmdlets **New-**, **Get-**, **Set-** und **Remove-CsInboundBlockedNumberPattern**. Sie können ein bestimmtes Muster mithilfe dieser Cmdlets verwalten, einschließlich der Möglichkeit, die Aktivierung eines bestimmten Musters umzuschalten.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) gibt eine Liste aller blockierten Nummernmuster wieder, die der Mandantenliste hinzugefügt wurden, einschließlich Name, Beschreibung, Aktiviert (Wahr/Falsch) und das jeweilige Muster.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) fügt der Mandantenliste ein blockiertes Nummernmuster hinzu.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) entfernt ein blockiertes Nummernmuster aus der Mandantenliste.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) ändert einen oder mehrere Parameter eines gesperrten Nummernmusters in der Mandantenliste.

Das Anzeigen und Aktivieren der gesamten Anrufblockierungsfunktion wird über die Cmdlets **Get-** und **Set-CsTenantBlockingCallingNumbers** verwaltet.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) gibt die Parameter für eingehende Blocknummern und die Parameter für eingehende ausgenommene Nummernmuster für die globale Liste blockierter Nummern zurück. Dieses Cmdlet gibt auch zurück, ob die Blockierung aktiviert wurde (True oder False). Es gibt eine einzelne globale Mandantenrichtlinie, die nur manuell geändert werden kann, außer das Feature ein- oder auszuschalten.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) ermöglicht das Ändern der globalen vom Mandanten blockierten Anrufe, sodass sie auf Mandantenebene ein- und ausgeschaltet werden.

### <a name="examples"></a>Beispiele

#### <a name="block-a-number"></a>Eine Telefonnummer blockieren

Im folgenden Beispiel möchte der Mandantenadministrator alle Anrufe blockieren, die aus dem Nummernkreis 1 (312) 555-0000 bis 1 (312) 555-9999 kommen. Das Nummernmuster wird so erstellt, dass sowohl Nummern im Bereich mit + vorangestelltem als auch Nummern im Bereich ohne + vorangestelltem übereinstimmen. Sie müssen die Symbole – und () nicht in die Telefonnummern einfügen, da das System diese Symbole vor dem Abgleich entfernt.  Um das Zahlenmuster einzuschalten, wird der Parameter **Enabled** auf True gesetzt. Um dieses spezielle Zahlenmuster zu deaktivieren, setzen Sie den Parameter auf False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

Im nächsten Beispiel möchte der Mandantenadministrator alle Anrufe blockieren, die von der Nummer 1 (412) 555-1234 kommen. Um das Zahlenmuster einzuschalten, wird der Parameter **Enabled** auf True gesetzt.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

Beim Erstellen eines neuen Musters wird das Muster standardmäßig als aktiviert hinzugefügt. Die Beschreibung ist ein optionales Feld, um weitere Informationen bereitzustellen.

Wir empfehlen Ihnen, einen aussagekräftigen Namen anzugeben, der es leicht verständlich macht, warum das Muster hinzugefügt wurde. Wenn Sie Spam-Nummern einfach blockieren, sollten Sie die Regel genauso benennen wie das Nummernmuster, das abgeglichen wird, und bei Bedarf zusätzliche Informationen in die Beschreibung einfügen.

Muster werden mit regulären Ausdrücken (RegEx) abgeglichen. Weitere Informationen finden Sie unter [Regex verwenden](#using-regex).

Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu. 

#### <a name="allow-a-number"></a>Eine Telefonnummer zulassen

Sie können einer Nummer erlauben, anzurufen, indem Sie das gesperrte Nummernmuster entfernen. Im folgenden Beispiel möchte der Mandantenadministrator 1 (412) 555-1234 wieder erlauben, Anrufe zu tätigen.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
Wenn die Identität nicht bekannt ist, verwenden Sie das Cmdlet **Get-CsInboundBlockedNumberPattern**, um zuerst das richtige Muster zu suchen und die Identität zu notieren. Führen Sie dann das Cmdlet **Remove-CsInboundBlockedNumberPattern** aus und übergeben Sie den entsprechenden Identitätswert.

Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.

#### <a name="view-all-number-patterns"></a>Alle Nummernmuster anzeigen

Durch Ausführen dieses Cmdlets wird eine Liste aller für einen Mandanten eingegebene blockierte Nummern wiedergegeben:

```powershell
Get-CsInboundBlockedNumberPattern
```

Verwenden Sie integrierte PowerShell-Filterfunktionen, um die wiedergegebenen Werte nach Bedarf zu analysieren.

## <a name="add-number-exceptions"></a>Ausnahmen für Telefonnummern hinzufügen

Sie können Ausnahmen zu blockierten Zahlenmustern hinzufügen, indem Sie die Cmdlets **New-**, **Get-**, **Set-** und **Remove-CsInboundExemptNumberPattern** verwenden.

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) fügt der Mandantenliste ein Nummernausnahmemuster hinzu. 
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) gibt eine Liste aller Nummernausnahmemuster zurück, die der Mandantenliste hinzugefügt wurden.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) ändert einen oder mehrere Parameter in ein Nummernausnahmemuster in der Mandantenliste.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) entfernt ein Nummernausnahmemuster aus der Mandantenliste.

### <a name="examples"></a>Beispiele

#### <a name="add-a-number-exception"></a>Nummernausnahme hinzufügen

Im folgenden Beispiel möchte der Mandantenadministrator den Rufnummern 1 (312) 555-8882 und 1 (312) 555-8883 erlauben, den Mandant anzurufen, auch wenn diese beiden Rufnummern im gesperrten Bereich liegen im obigen Beispiel. Um dies zu ermöglichen, wird ein neues Nummernausnahmemuster wie folgt erstellt:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Um das Zahlenmuster einzuschalten, wird der Parameter **Enabled** auf True gesetzt. Um dieses spezielle Zahlenmuster zu deaktivieren, setzen Sie den Parameter auf False.


#### <a name="view-all-number-exceptions"></a>Alle Nummernausnahmen anzeigen

In diesem Beispiel ist der Parameter **Identität** optional. Wenn der Parameter **Identität** nicht angegeben ist, gibt dieses Cmdlet eine Liste aller für einen Mandanten eingegebenen Nummernausnahmemuster wieder.
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>Nummernausnahme ändern

Mit dem Cmdlet **Set-CsInboundExemptNumberPattern** können Sie einen oder mehrere Parameter für eine bestimmte Zahlenmusteridentität ändern. In diesem Beispiel ist der Parameter **Identität** erforderlich.
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Zahlenausnahme ändern

Das Cmdlet **Remove-CsInboundExemptNumberPattern** entfernt das angegebene Zahlenmuster aus der Mandantenliste. In diesem Beispiel ist der Parameter **Identität** erforderlich. 

Wenn die Identität nicht bekannt ist, verwenden Sie das Cmdlet **Get-CsInboundExemptNumberPattern**, um zuerst das richtige Muster zu suchen und die Identität zu notieren. Führen Sie dann das Cmdlet **Remove-CsInboundExemptNumberPattern** aus und übergeben Sie den entsprechenden Identitätswert.Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Testen, ob eine Zahl blockiert ist

Verwenden Sie das Cmdlet **Test-CsInboundBlockedNumberPattern**, um zu überprüfen, ob eine Zahl im Mandanten blockiert ist.
 
Der Parameter **PhoneNumber** ist erforderlich und sollte eine numerische Zeichenfolge ohne zusätzliche Zeichen wie +, - oder () sein. Der resultierende Parameter **IsNumberBlocked** gibt den Wert True zurück, wenn die Nummer im Mieter blockiert ist; der Parameter gibt False zurück, wenn er nicht blockiert ist.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Beispiele

In diesen Beispielen sehen Sie, dass die Telefonnummer 1 (312) 555-8884 gesperrt ist, da sie sich im oben gesperrten Bereich befindet, während die Telefonnummer 1 (312) 555-8883 wie sie anrufen darf sollte auf der oben geschaffenen Ausnahme basieren.

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

## <a name="using-regex"></a>Verwenden von Regex

Der Mustervergleich zum Blockieren von Anrufern erfolgt mithilfe von Regex. Mehrere Tools sind online verfügbar, um eine RegEx-Musterübereinstimmung zu überprüfen. Wenn Sie mit RegEx-Mustern nicht vertraut sind, empfehlen wir Ihnen, sich etwas Zeit zu nehmen, um sich mit den Grundlagen vertraut zu machen. Um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten, verwenden Sie ein Tool zum Überprüfen von Musterübereinstimmungen, bevor Sie Ihrem Mandanten neue Übereinstimmungen mit blockierten Nummern hinzufügen.