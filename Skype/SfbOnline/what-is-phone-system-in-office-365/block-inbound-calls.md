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
ms.openlocfilehash: 16a646af3e456bb68a2a582cad7d6b742100c650
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820915"
---
# <a name="block-inbound-calls"></a>Blockieren eingehender Anrufe

Skype for Business Online-Anrufpläne unterstützen jetzt das Blockieren eingehender Anrufe aus dem öffentlichen Telefonnetz (PSTN). Dieses Feature ermöglicht es, eine globale Mandantenliste mit Zahlenmustern zu definieren, damit die Anrufer-ID jedes eingehenden PSTN-Anrufs an den Mandanten mit der Liste auf eine Übereinstimmung überprüft werden kann. Wenn eine Übereinstimmung vorgenommen wird, wird ein eingehender Anruf abgelehnt.

Dieses Feature zum Blockieren eingehender Anrufe funktioniert nur bei eingehenden Anrufen, die aus dem PSTN stammen, und funktioniert nur auf Mandanten-globaler Basis. Sie steht pro Benutzer nicht zur Verfügung.  

Dieses Feature ist für Direct Routing noch nicht verfügbar.

>[!NOTE]
> Blockierte Anrufer können ein geringfügig anderes Verhalten erleben, wenn sie blockiert wurden. Das Verhalten basiert darauf, wie der Netzbetreiber des blockierten Anrufers die Benachrichtigung verarbeitet, dass der Anruf nicht erfolgreich abgeschlossen werden kann. Beispiele hierfür sind eine Nachricht des Netzbetreibers, die besagt, dass der Anruf nicht als gewählt abgeschlossen werden kann, oder einfach den Anruf ablassen.

## <a name="call-blocking-admin-controls-and-information"></a>Anrufblockierung von Administratorsteuerelementen und -informationen

Administratorsteuerelemente zum Blockieren von Nummern werden nur mithilfe von PowerShell bereitgestellt. Nummernblockmuster sind als Reguläre Ausdrucksmuster definiert. Die Reihenfolge der Ausdrücke ist unwichtig – das erste Muster, das in der Liste übereinstimmen, führt dazu, dass der Aufruf blockiert wird. Es kann bis zu 24 Stunden dauern, bis eine neue Nummer oder ein neues Muster zur Liste blockierter Anrufer hinzugefügt oder entfernt wird, bis das Muster aktiv wird.

## <a name="call-blocking-powershell-commands"></a>Befehle zum Blockieren von Aufrufen von PowerShell

Zahlenmuster werden über die Befehle ```CsInboundBlockedNumberPattern``` ```New``` , , und ```Get``` ```Set``` ```Remove``` verwaltet. Sie können ein bestimmtes Muster mithilfe dieser Cmdlets verwalten, einschließlich der Möglichkeit, die Aktivierung eines bestimmten Musters umschalten.
- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) gibt eine Liste aller zur Mandantenliste hinzugefügten blockierten Zahlenmuster zurück, einschließlich Name, Beschreibung, Aktiviert (Wahr/Falsch) und Muster für jedes.
- ["New-CsInboundBlockedNumberPattern" fügt](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) der Mandantenliste ein blockiertes Zahlenmuster hinzu.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) entfernt ein blockiertes Zahlenmuster aus der Mandantenliste.
- ["Set-CsInboundBlockedNumberPattern"](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) ändert einen oder mehrere Parameter eines blockierten Zahlenmusters in der Mandantenliste.

Das Anzeigen und Aktivieren des gesamten Anrufblockerfeatures wird über die ```CsTenantBlockingCallingNumbers``` Befehle und ```Get``` . ```Set```

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) gibt die Parameter für die globale Liste blockierter Zahlen zurück, einschließlich "Enabled" (True/False). Es gibt eine einzige globale Mandantenrichtlinie, die nur zum Aktivieren oder Deaktivieren des Features manuell geändert werden kann.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) ermöglicht das Ändern der blockierten Anrufe des globalen Mandanten auf Mandantenebene.

### <a name="examples"></a>Beispiele

#### <a name="block-a-number"></a>Blockieren einer Zahl

In diesem Beispiel sind die ```-Enabled``` Parameter und die Parameter ```-Description``` optional:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

Durch das Erstellen eines neuen Musters wird das Muster standardmäßig aktiviert. Die Beschreibung ist ein optionales Feld, das weitere Informationen enthält.

Es wird empfohlen, einen aussagekräftigen Namen ein geben, um zu verstehen, warum das Muster hinzugefügt wurde. Wenn Sie Spamnummern einfach blockieren möchten, sollten Sie erwägen, die Regel auf dieselbe Weise wie das übereinstimmende Zahlenmuster zu benennen, und fügen Sie bei Bedarf zusätzliche Informationen zur Beschreibung hinzu.

Muster werden mithilfe von Reguläre Ausdrücke (Regex) abgestimmt. Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation ein.

#### <a name="allow-a-number"></a>Zulassen einer Zahl

In diesem Beispiel ist ```-Identity``` der Parameter erforderlich:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Wenn die Identität nicht bekannt ist, verwenden Sie das Cmdlet, um zuerst das richtige Muster zu finden ```Get-CsInboundBlockedNumberPattern``` und die Identität zu notieren. Führen Sie dann das ```Remove-CsTenantBlockedNumberPattern``` Cmdlet aus, und übergeben Sie den entsprechenden Identitätswert.

Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation ein.

#### <a name="view-all-number-patterns"></a>Anzeigen aller Zahlenmuster

Durch Ausführen dieses Cmdlets wird eine Liste aller blockierten Nummern zurückgegeben, die für einen Mandanten eingegeben werden:

```powershell
Get-CsInboundBlockedNumberPattern
```

Verwenden Sie die integrierten PowerShell-Filterfähigkeiten, um die zurückgegebenen Werte nach Bedarf zu analysieren.

## <a name="add-number-exceptions"></a>Hinzufügen von Zahlenausnahmen

Sie können Ausnahmen zu blockierten Zahlenmustern mithilfe der ```CsTenantBlockNumberExceptionPattern``` ```New``` Befehle, ```Get``` , und ```Set``` ```Remove``` hinzufügen.

- ["New-CsTenantBlockedNumberExceptionPattern" fügt](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) der Mandantenliste ein Nummernausnahmemuster hinzu. 
- ["Get-CsTenantBlockedNumberExceptionPattern" gibt](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) eine Liste aller Zur Mandantenliste hinzugefügten Nummernausnahmemuster zurück.
- ["Set-CsTenantBlockedNumberExceptionPattern"](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) ändert einen oder mehrere Parameter in ein Nummernausnahmemuster in der Mandantenliste.
- ["Remove-CsTenantBlockedNumberExceptionPattern" entfernt](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) ein Nummernausnahmemuster aus der Mandantenliste.

### <a name="examples"></a>Beispiele

#### <a name="add-a-number-exception"></a>Hinzufügen einer Zahlenausnahme

In diesem Beispiel wird ein neues Nummernausnahmemuster erstellt und das Muster standardmäßig als aktiviert hinzugefügt. Die ```-Enabled``` Parameter und die Parameter sind ```-Description``` optional.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Alle Zahlenausnahmen anzeigen

In diesem Beispiel ist der Parameter "-Identity" optional. Wenn der Parameter nicht angegeben ist, gibt dieses Cmdlet eine Liste aller Nummernausnahmemuster zurück, die ```-Identity``` für einen Mandanten eingegeben wurden.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Ändern einer Zahlenausnahme

In diesem Beispiel ist der Parameter "-Identity" obligatorisch. Mit ```Set-CsTenantBlockedNumberExceptionPattern``` dem Cmdlet können Sie einen oder mehrere Parameter für eine bestimmte Zahlenmusteridentität ändern.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Entfernen einer Zahlenausnahme

In diesem Beispiel ist ```-Identity``` der Parameter erforderlich. Mit diesem Cmdlet wird das angegebene Zahlenmuster aus der Mandantenliste entfernt.  Wenn die Identität nicht bekannt ist, verwenden Sie das Cmdlet, um zuerst das richtige Muster zu finden ```Get-CsInboundBlockedNumberPattern``` und die Identität zu notieren. Führen Sie dann das ```Remove-CsTenantBlockedNumberExceptionPattern``` Cmdlet aus, und übergeben Sie den entsprechenden Identitätswert.Lassen Sie vor dem Testen und Überprüfen Zeit für die Replikation ein.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testen, ob eine Nummer blockiert ist

Verwenden Sie ```Test-CsInboundBlockedNumberPattern``` das Cmdlet, um zu überprüfen, ob eine Nummer im Mandanten blockiert ist.
 
In diesem Beispiel sind die ```-Phonenumber``` Parameter und die Parameter ```-Tenant``` erforderlich. Der ```-PhoneNumber``` Parameter sollte eine numerische Zeichenfolge ohne zusätzliche Zeichen wie +oder -sein. In TRPS ist ```-Tenant parameter``` dies optional. Der resultierende Parameter gibt den Wert "True" zurück, wenn die Zahl im Mandanten blockiert ist, und "False", wenn ```isNumberBlocked``` sie nicht blockiert ist.

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

Wie bereits erwähnt, erfolgt der Musterabgleich zum Blockieren von Anrufern mithilfe von Regex. Online stehen mehrere Tools zur Überprüfung einer Regex-Muster-Übereinstimmung zur Verfügung. Wenn Sie mit Regex-Mustern nicht vertraut sind, sollten Sie sich etwas Zeit nehmen, um sich mit den Grundlagen vertraut zu machen. Um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten, verwenden Sie ein Tool zum Überprüfen von Muster übereinstimmungen, bevor Sie Ihrem Mandanten neue Übereinstimmungen mit blockierten Nummern hinzufügen. 

## <a name="related-topics"></a>Verwandte Themen

- [Einrichten Ihres Computers zum Verwalten von Skype for Business Online mithilfe Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
