---
title: Blockieren eingehender Anrufe in Microsoft Teams
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631429"
---
# <a name="block-inbound-calls"></a>Blockieren eingehender Anrufe

Microsoft-Anrufpläne, Direktes Routing und Netzbetreiber unterstützen Verbinden blockieren eingehende Anrufe aus dem öffentlichen Telefonnetz (PSTN). Dieses Feature ermöglicht es einem Administrator, eine Liste von Nummernmustern auf globaler Mandantenebene zu definieren, damit die Anrufer-ID jedes eingehenden PSTN-Anrufs an den Mandanten mit der Liste auf Übereinstimmung überprüft werden kann. Wenn eine Übereinstimmung vorgenommen wird, wird ein eingehender Anruf abgelehnt.

Dieses Feature zum Blockieren eingehender Anrufe funktioniert nur bei eingehenden Anrufen, die aus dem PSTN stammen, und funktioniert nur auf globaler Mandantenebene. Einzelne Teams Benutzer können diese Liste nicht bearbeiten. Der Teams-Client ermöglicht es einzelnen Benutzern, PSTN-Anrufe zu blockieren. Informationen dazu, wie Ihre Endbenutzer die Anrufblockierung implementieren können, finden Sie unter [Verwalten von Anrufeinstellungen in Teams.](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

>[!NOTE]
> Blockierte Anrufer können ein leicht anderes Verhalten erleben, wenn sie blockiert wurden. Das Verhalten basiert darauf, wie der Netzbetreiber des blockierten Anrufers die Benachrichtigung verarbeitet, dass der Anruf nicht erfolgreich abgeschlossen werden kann. Beispiele hierfür sind eine Nachricht des Netzbetreibers, die besagt, dass der Anruf nicht als gewählt abgeschlossen werden kann, oder dass der Anruf einfach beendet werden kann.

## <a name="call-blocking-admin-controls-and-information"></a>Blockieren von Administratorsteuerelementen und -informationen für Anrufe

Administratorsteuerelemente zum Blockieren von Nummern werden nur mithilfe von PowerShell bereitgestellt. Zahlenblockmuster sind als reguläre Ausdrucksmuster definiert. Die Reihenfolge der Ausdrücke ist unwichtig – das erste Muster, das in der Liste abgesenert wurde, führt dazu, dass der Aufruf blockiert wird. Es kann bis zu 24 Stunden dauern, bis eine neue Nummer oder ein neues Muster in der Liste blockierter Anrufer hinzugefügt oder entfernt wird, bis das Muster aktiv wird.

## <a name="call-blocking-powershell-commands"></a>Blockieren von PowerShell-Befehlen für Anrufe

Sie verwalten Zahlenmuster mithilfe der **Cmdlets New-**, **Get-**, **Set-** und **Remove-CsInboundBlockedNumberPattern.** Sie können ein bestimmtes Muster mithilfe dieser Cmdlets verwalten, einschließlich der Möglichkeit, die Aktivierung eines bestimmten Musters umschalten.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) gibt eine Liste aller blockierten Zahlenmuster zurück, die zur Mandantenliste hinzugefügt wurden, einschließlich Name, Beschreibung, Aktiviert (Wahr/Falsch) und Muster für jeden.
- [New-CsInboundBlockedNumberPattern fügt](/powershell/module/skype/new-csinboundblockednumberpattern) der Mandantenliste ein Muster für blockierte Zahlen hinzu.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) entfernt ein blockiertes Zahlenmuster aus der Mandantenliste.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) ändert einen oder mehrere Parameter eines Musters blockierter Zahlen in der Mandantenliste.

Das Anzeigen und Aktivieren des gesamten Anrufblockerfeatures wird über die **Cmdlets Get-** und **Set-CsTenantBlockingCallingNumbers** verwaltet.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) gibt die Muster für eingehende Blocknummern und die Parameter für eingehende ausgenommene Zahlenmuster für die globale Liste blockierter Zahlen zurück. Dieses Cmdlet gibt auch zurück, ob Blockierung aktiviert wurde (Wahr oder Falsch). Es gibt eine einzelne globale Mandantenrichtlinie, die nur zum Aktivieren oder Deaktivieren des Features manuell geändert werden kann.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) ermöglicht das Ändern der blockierten Anrufe des globalen Mandanten, damit diese auf Mandantenebene aktiviert und deaktiviert werden.

### <a name="examples"></a>Beispiele

#### <a name="block-a-number"></a>Blockieren einer Zahl

Im folgenden Beispiel möchte der Mandantenadministrator alle Anrufe aus dem Nummernbereich 1 (312) 555-0000 bis 1 (312) 555-9999 blockieren. Das Zahlenmuster wird erstellt, damit sowohl Zahlen im Bereich mit + als auch Zahlen im Bereich ohne +Präfix übereinstimmen. Sie müssen die Symbole – und () nicht in die Telefonnummern verwenden, da das System diese Symbole vor dem Abgleich entfernt.  Zum Aktivieren des Zahlenmusters ist der **Parameter Enabled** auf True festgelegt. Um dieses bestimmte Zahlenmuster zu deaktivieren, legen Sie den -Parameter auf False..

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

Im nächsten Beispiel möchte der Mandantenadministrator alle Anrufe blockieren, die von der Nummer 1 (412) 555-1234 kommen. Zum Aktivieren des Zahlenmusters ist der **Parameter Enabled** auf True festgelegt.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

Durch das Erstellen eines neuen Musters wird das Muster standardmäßig aktiviert. Die Beschreibung ist ein optionales Feld, das weitere Informationen enthält.

Es wird empfohlen, einen aussagekräftigen Namen ein geben, um zu verstehen, warum das Muster hinzugefügt wurde. Falls Sie Spamnummern einfach blockieren, sollten Sie erwägen, die Regel wie das übereinstimmende Zahlenmuster zu benennen und der Beschreibung bei Bedarf zusätzliche Informationen hinzuzufügen.

Muster werden mithilfe von reguläre Ausdrücke (Regex) abgestimmt. Weitere Informationen finden Sie unter [Verwenden von Regex.](#using-regex)

Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu. 

#### <a name="allow-a-number"></a>Nummer zulassen

Sie können durch Entfernen des Musters für blockierte Nummern zulassen, dass eine Nummer anruft. Im folgenden Beispiel möchte der Mandantenadministrator 1 (412) 555-1234 erlauben, wieder Anrufe zu unternehmen.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
Wenn die Identität nicht bekannt ist, verwenden Sie das **Cmdlet Get-CsInboundBlockedNumberPattern,** um zuerst das richtige Muster zu suchen und sich die Identität zu notieren. Führen Sie dann das **Cmdlet Remove-CsInboundBlockedNumberPattern** aus, und übergeben Sie den entsprechenden Identitätswert.

Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.

#### <a name="view-all-number-patterns"></a>Anzeigen aller Zahlenmuster

Wenn Sie dieses Cmdlet ausführen, wird eine Liste aller blockierten Nummern zurückgegeben, die für einen Mandanten eingegeben wurden:

```powershell
Get-CsInboundBlockedNumberPattern
```

Verwenden Sie die integrierten PowerShell-Filterfunktionen, um die zurückgegebenen Werte wie erforderlich zu analysieren.

## <a name="add-number-exceptions"></a>Hinzufügen von Nummernausnahmen

Mithilfe der Cmdlets **New-**, **Get-**, **Set-** und **Remove-CsInboundExemptNumberPattern** können Sie Ausnahmen zu blockierten Zahlenmustern hinzufügen.

- [New-CsInboundExemptNumberPattern fügt](/powershell/module/skype/New-CsInboundExemptNumberPattern) der Mandantenliste ein Nummernausnahmemuster hinzu. 
- [Get-CsInboundExemptNumberPattern gibt](/powershell/module/skype/Get-CsInboundExemptNumberPattern) eine Liste aller Zahlenausnahmemuster zurück, die der Mandantenliste hinzugefügt wurden.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) ändert einen oder mehrere Parameter in ein Nummernausnahmemuster in der Mandantenliste.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) entfernt ein Nummernausnahmemuster aus der Mandantenliste.

### <a name="examples"></a>Beispiele

#### <a name="add-a-number-exception"></a>Hinzufügen einer Zahlenausnahme

Im folgenden Beispiel möchte der Mandantenadministrator den Telefonnummern 1 (312) 555-8882 und 1 (312) 555-8883 das Anrufen beim Mandanten gestatten, auch wenn sich diese beiden Telefonnummern in dem Bereich befinden, der im obigen Beispiel blockiert wurde. Um dies zu ermöglichen, wird ein neues Zahlenausnahmemuster wie folgt erstellt:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Zum Aktivieren des Zahlenmusters ist der **Parameter Enabled** auf True festgelegt. Um dieses bestimmte Zahlenmuster zu deaktivieren, legen Sie den -Parameter auf False..


#### <a name="view-all-number-exceptions"></a>Alle Zahlenausnahmen anzeigen

In diesem Beispiel ist der **Identity-Parameter** optional. Wenn der **Parameter Identity** nicht angegeben ist, gibt dieses Cmdlet eine Liste aller Zahlenausnahmemuster zurück, die für einen Mandanten eingegeben wurden.
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>Ändern einer Zahlenausnahme

Mit **dem Cmdlet Set-CsInboundExemptNumberPattern** können Sie einen oder mehrere Parameter für eine bestimmte Zahlenmusteridentität ändern. In diesem Beispiel ist der **Identity-Parameter** erforderlich.
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Entfernen einer Zahlenausnahme

Das **Cmdlet Remove-CsInboundExemptNumberPattern** entfernt das angegebene Zahlenmuster aus der Mandantenliste. In diesem Beispiel ist der **Identity-Parameter** erforderlich. 

Wenn die Identität nicht bekannt ist, verwenden Sie das **Cmdlet Get-CsInboundExemptNumberPattern,** um zuerst das richtige Muster zu finden und sich die Identität zu notieren. Führen Sie dann das **Cmdlet Remove-CsInboundExemptNumberPattern** aus, und übergeben Sie den entsprechenden Identitätswert.Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation zu.  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Testen, ob eine Nummer blockiert ist

Überprüfen Sie mit dem **Cmdlet Test-CsInboundBlockedNumberPattern,** ob eine Zahl im Mandanten blockiert wurde.
 
Der **Parameter PhoneNumber** ist erforderlich und sollte eine numerische Zeichenfolge ohne weitere Zeichen sein, z. B. +, - oder (). Der resultierende **IsNumberBlocked-Parameter** gibt den Wert True zurück, wenn die Zahl im Mandanten blockiert ist. Der -Parameter gibt "False" zurück, wenn er nicht blockiert ist.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Beispiele

In diesen Beispielen können Sie sehen, dass die Telefonnummer 1 (312) 555-8884 blockiert ist, da sie sich im oben genannten Bereich "Blockiert" befindet, während die Telefonnummer 1 (312) 555-8883 so anrufen kann, wie sie auf der Grundlage der oben erstellten Ausnahme basieren sollte.

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

Der Musterabgleich zum Blockieren von Anrufern erfolgt mithilfe von Regex. Online stehen mehrere Tools zur Überprüfung einer Regex-Muster übereinstimmung zur Verfügung. Wenn Sie mit Regex-Mustern nicht vertraut sind, sollten Sie sich etwas Zeit nehmen, um sich mit den Grundlagen vertraut zu machen. Um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten, verwenden Sie ein Tool zum Überprüfen von Muster übereinstimmungen, bevor Sie Ihrem Mandanten neue Übereinstimmungen mit blockierten Nummern hinzufügen.