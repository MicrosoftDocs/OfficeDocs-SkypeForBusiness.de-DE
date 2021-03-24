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
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: fcf50f96f352cfb72ff3bd700f2118c3cda51dd7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092863"
---
# <a name="block-inbound-calls"></a>Blockieren eingehender Anrufe

Telefonsystem-Direct-Routing- und Anrufpläne unterstützen das Blockieren eingehender Anrufe aus dem öffentlichen Telefonnetz (PstN). Dieses Feature ermöglicht es, eine globale Mandantenliste mit Zahlenmustern zu definieren, damit die Anrufer-ID jedes eingehenden PSTN-Anrufs beim Mandanten mit der Liste für eine Übereinstimmung abgehakt werden kann. Wenn eine Übereinstimmung hergestellt wird, wird ein eingehender Anruf abgelehnt.

Dieses Feature zum Blockieren eingehender Anrufe funktioniert nur bei eingehenden Anrufen, die aus dem PSTN stammen, und funktioniert nur auf mandanten-globaler Basis. Sie ist nicht pro Benutzer verfügbar.  

>[!NOTE]
> Blockierte Anrufer können geringfügig unterschiedliche Verhaltensweisen haben, wenn sie blockiert wurden. Das Verhalten basiert darauf, wie der Netzbetreiber des blockierten Anrufers die Benachrichtigung verarbeitet, dass der Anruf nicht erfolgreich abgeschlossen werden darf. Beispiele hierfür können eine Netzbetreibernachricht sein, die besagt, dass der Anruf nicht als gewählt abgeschlossen werden kann, oder einfach den Anruf ablegen.

## <a name="call-blocking-admin-controls-and-information"></a>Anrufblockierung von Administratorsteuerelementen und -informationen

Administratorsteuerelemente zum Blockieren von Nummern werden nur mithilfe von PowerShell bereitgestellt. Zahlenblockmuster werden als Muster für reguläre Ausdrücke definiert. Die Reihenfolge der Ausdrücke ist unwichtig– das erste Muster, das in der Liste übereinstimmend ist, führt dazu, dass der Aufruf blockiert wird. Eine neue Nummer oder ein neues Muster, die in der Liste blockierter Anrufer hinzugefügt oder entfernt wird, kann bis zu 24 Stunden dauern, bis das Muster aktiv wird.

## <a name="call-blocking-powershell-commands"></a>Aufrufen blockierender PowerShell-Befehle

Sie verwalten Zahlenmuster mithilfe der **Cmdlets Neu**, **Get**, **Set**, **Remove**  - **CsInboundBlockedNumberPattern.** Sie können ein bestimmtes Muster mithilfe dieser Cmdlets verwalten, einschließlich der Möglichkeit, die Aktivierung eines bestimmten Musters umschalten zu können.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) gibt eine Liste aller blockierten Zahlenmuster zurück, die der Mandantenliste hinzugefügt wurden, einschließlich Name, Beschreibung, Aktiviert (Wahr/Falsch) und Muster für jedes.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) fügt der Mandantenliste ein blockiertes Zahlenmuster hinzu.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) entfernt ein blockiertes Zahlenmuster aus der Mandantenliste.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) ändert einen oder mehrere Parameter eines blockierten Zahlenmusters in der Mandantenliste.

Das Anzeigen und Aktivieren des gesamten Anrufblockierungsfeatures wird über die **Cmdlets Get**, **Set**  - **CsTenantBlockingCallingNumbers** verwaltet.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) gibt die Parameter für die globale Liste blockierter Zahlen zurück, einschließlich Aktiviert (True/False). Es gibt eine einzelne globale Mandantenrichtlinie, die nicht manuell geändert werden kann, als das Feature zu aktivieren oder zu deaktivieren.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) ermöglicht das Ändern der blockierten globalen Mandantenanrufe, um auf Mandantenebene aktiviert und deaktiviert zu werden.

### <a name="examples"></a>Beispiele

#### <a name="block-a-number"></a>Blockieren einer Zahl

In diesem Beispiel sind die **Parameter Aktiviert** und **Beschreibung** optional.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

Beim Erstellen eines neuen Musters wird das Muster standardmäßig aktiviert. Die Beschreibung ist ein optionales Feld, um weitere Informationen zu erhalten.

Es wird empfohlen, einen aussagekräftigen Namen zur Verfügung zu stellen, um leicht zu verstehen, warum das Muster hinzugefügt wurde. Wenn Sie Spamnummern einfach blockieren, sollten Sie die Regel mit dem übereinstimmenden Zahlenmuster benennen und bei Bedarf zusätzliche Informationen in die Beschreibung hinzufügen.

Muster werden mit regulären Ausdrücken (Regex) abgestimmt. Zeit für die Replikation zulassen, bevor Sie testen und überprüfen.

#### <a name="allow-a-number"></a>Zulassen einer Zahl

In diesem Beispiel ist der **Parameter Identität** erforderlich.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Wenn die Identität nicht bekannt ist, verwenden Sie das **Cmdlet Get-CsInboundBlockedNumberPattern,** um zuerst das richtige Muster zu finden und die Identität zu notieren. Führen Sie dann das **Cmdlet Remove-CsTenantBlockedNumberPattern** aus, und übergeben Sie den entsprechenden Identitätswert.

Zeit für die Replikation zulassen, bevor Sie testen und überprüfen.

#### <a name="view-all-number-patterns"></a>Anzeigen aller Zahlenmuster

Durch Ausführen dieses Cmdlets wird eine Liste aller blockierten Nummern zurückgegeben, die für einen Mandanten eingegeben werden:

```powershell
Get-CsInboundBlockedNumberPattern
```

Verwenden Sie integrierte PowerShell-Filterfunktionen, um die zurückgegebenen Werte nach Bedarf zu analysieren.

## <a name="add-number-exceptions"></a>Hinzufügen von Nummernausnahmen

Sie können Ausnahmen zu blockierten Zahlenmustern hinzufügen, indem Sie die Cmdlets **Neu**, **Get**, **Set**, **Remove**  - **CsTenantBlockNumberExceptionPattern** verwenden.

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) fügt der Mandantenliste ein Zahlenausnahmemuster hinzu. 
- [Get-CsTenantBlockedNumberExceptionPattern gibt](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) eine Liste aller Zahlenausnahmemuster zurück, die der Mandantenliste hinzugefügt wurden.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) ändert einen oder mehrere Parameter an ein Zahlenausnahmemuster in der Mandantenliste.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) entfernt ein Zahlenausnahmemuster aus der Mandantenliste.

### <a name="examples"></a>Beispiele

#### <a name="add-a-number-exception"></a>Hinzufügen einer Zahlenausnahme

In diesem Beispiel wird ein neues Zahlenausnahmemuster erstellt und standardmäßig als aktiviert hinzugefügt. Die **Parameter "Aktiviert"** **und "Beschreibung"** sind optional.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Alle Zahlenausnahmen anzeigen

In diesem Beispiel ist der **Parameter Identität** optional. Wenn der **Parameter Identität** nicht angegeben ist, gibt dieses Cmdlet eine Liste aller Zahlenausnahmemuster zurück, die für einen Mandanten eingegeben wurden.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Ändern einer Zahlenausnahme

In diesem Beispiel ist der **Parameter Identität** obligatorisch. Mit **dem Cmdlet Set-CsTenantBlockedNumberExceptionPattern** können Sie einen oder mehrere Parameter für eine bestimmte Zahlenmusteridentität ändern.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Entfernen einer Zahlenausnahme

In diesem Beispiel ist der **Parameter Identität** erforderlich. Dieses Cmdlet entfernt das angegebene Zahlenmuster aus der Mandantenliste.  Wenn die Identität nicht bekannt ist, verwenden Sie das **Cmdlet Get-CsInboundBlockedNumberPattern,** um zuerst das richtige Muster zu finden und die Identität zu notieren. Führen Sie dann das **Cmdlet Remove-CsTenantBlockedNumberExceptionPattern** aus, und übergeben Sie den entsprechenden Identitätswert.Zeit für die Replikation zulassen, bevor Sie testen und überprüfen.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testen, ob eine Zahl blockiert ist

Verwenden Sie **das Cmdlet Test-CsInboundBlockedNumberPattern,** um zu überprüfen, ob eine Zahl im Mandanten blockiert ist.
 
In diesem Beispiel sind die **Parameter PhoneNumber** und **Tenant** erforderlich. Der **Parameter PhoneNumber** sollte eine numerische Zeichenfolge ohne zusätzliche Zeichen wie +oder -sein. In TRPS ist der **Parameter Mandant** optional. Der resultierende **Parameter isNumberBlocked** gibt den Wert True zurück, wenn die Zahl im Mandanten blockiert ist, und False, wenn sie nicht blockiert ist.

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

## <a name="a-note-about-regex"></a>Eine Notiz über Regex

Wie bereits erwähnt, erfolgt der Musterabgleich zum Blockieren von Anrufern mithilfe von Regex. Mehrere Tools stehen online zur Verfügung, um eine Übereinstimmung mit dem Regex-Muster zu überprüfen. Wenn Sie mit Regex-Mustern nicht vertraut sind, empfiehlt es sich, sich etwas Zeit zu nehmen, um sich mit den Grundlagen vertraut zu machen. Um sicherzustellen, dass die erwarteten Ergebnisse angezeigt werden, verwenden Sie ein Tool zum Überprüfen von Muster übereinstimmungen, bevor Sie ihrem Mandanten neue Übereinstimmungen mit blockierten Zahlen hinzufügen.