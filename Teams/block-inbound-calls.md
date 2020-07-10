---
title: Blockieren von eingehenden Anrufen in Microsoft Teams
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094681"
---
# <a name="block-inbound-calls"></a>Eingehende Anrufe blockieren

Direkte Routing-und Anrufpläne für Telefonsysteme unterstützen das Blockieren von eingehenden Anrufen über das öffentlich geschaltete Telefonnetz (PSTN). Dieses Feature ermöglicht es, eine globale Mandantenliste mit Zahlen Mustern zu definieren, damit die Rufnummernanzeige jedes eingehenden PSTN-Anrufs für den Mandanten anhand der Liste für eine Übereinstimmung überprüft werden kann. Wenn eine Übereinstimmung erfolgt, wird ein eingehender Anruf abgelehnt.

Dieses Feature für eingehende Anrufe funktioniert nur bei eingehenden Anrufen, die aus dem PSTN stammen, und funktioniert nur auf Mandantenebene. Sie steht nicht für einzelne Benutzer zur Verfügung.  

>[!NOTE]
> Blockierte Anrufer können ein etwas anderes Verhalten erfahren, wenn Sie blockiert wurden. Das Verhalten hängt davon ab, wie der Netzbetreiber des blockierten Anrufers die Benachrichtigung verarbeitet, dass der Anruf nicht erfolgreich abgeschlossen werden darf. Zu den Beispielen kann eine Netzbetreiber Nachricht gehören, die besagt, dass der Anruf nicht wie gewählt durchgeführt werden kann, oder Sie können den Anruf einfach ablegen.

## <a name="call-blocking-admin-controls-and-information"></a>Anruf Blockierung von Administrator Steuerelementen und-Informationen

Administrator Steuerelemente für blockierende Nummern werden nur mithilfe von PowerShell bereitgestellt. Zahlenblock Muster werden als reguläre Ausdrucksmuster definiert. Die Reihenfolge der Ausdrücke ist unwichtig – das erste Muster, das in der Liste übereinstimmt, bewirkt, dass der Anruf blockiert wird. Eine neue Nummer oder ein Muster, das in der Liste der blockierten Anrufer hinzugefügt oder entfernt wird, kann bis zu 24 Stunden dauern, bis das Muster aktiv wird.

## <a name="call-blocking-powershell-commands"></a>PowerShell-Befehle zum Blockieren von Anrufen

Sie verwalten Zahlenmuster mithilfe der Cmdlets " **neu**", " **Abrufen** **", "CsInboundBlockedNumberPattern", "** **Entfernen**"  - **CsInboundBlockedNumberPattern** . Sie können ein bestimmtes Muster mithilfe dieser Cmdlets verwalten, einschließlich der Möglichkeit, die Aktivierung eines bestimmten Musters umzuschalten.

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) gibt eine Liste aller blockierten Zahlenmuster zurück, die der Mandantenliste hinzugefügt wurden, einschließlich Name, Beschreibung, aktiviert (wahr/falsch) und Muster für jeden.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) fügt der Mandantenliste ein blockiertes Zahlenmuster hinzu.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) entfernt ein blockiertes Zahlenmuster aus der Mandantenliste.
- Mit " [CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) " werden in der Mandantenliste mindestens ein Parameter eines blockierten Zahlen Musters geändert.

Das anzeigen und Aktivieren des gesamten Anruf Blockierungs Features wird über die Cmdlets **Get**, **Sets**  - **CsTenantBlockingCallingNumbers** verwaltet.

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) gibt die Parameter für die Liste der globalen blockierten Nummern einschließlich Enabled (wahr/falsch) zurück. Es gibt eine einzelne globale Mandanten Richtlinie, die nicht manuell anders geändert werden kann, als das Feature ein-oder auszuschalten.
- Mit " [CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) " können Sie ändern, dass die globalen Mandanten blockierten Anrufe auf Mandantenebene ein-und ausgeschaltet werden.

### <a name="examples"></a>Beispiele

#### <a name="block-a-number"></a>Blockieren einer Zahl

In diesem Beispiel sind die Parameter **Enabled** und **Description** optional.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

Beim Erstellen eines neuen Musters wird das Muster standardmäßig als aktiviert hinzugefügt. Die Beschreibung ist ein optionales Feld, in dem weitere Informationen bereitgestellt werden.

Wir empfehlen, dass Sie einen aussagekräftigen Namen angeben, um einfach zu verstehen, warum das Muster hinzugefügt wurde. Wenn Sie Spam-Nummern einfach blockieren, sollten Sie die Regel genauso benennen wie das Zahlenmuster, das verglichen wird, und bei Bedarf zusätzliche Informationen in der Beschreibung hinzufügen.

Muster werden mit regulären Ausdrücken (Regex) verglichen. Erlauben Sie Zeit für die Replikation, bevor Sie testen und überprüfen.

#### <a name="allow-a-number"></a>Zulassen einer Zahl

In diesem Beispiel ist der Parameter **Identity** erforderlich.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Wenn die Identität unbekannt ist, verwenden Sie das Cmdlet **Get-CsInboundBlockedNumberPattern** , um zuerst das richtige Muster zu finden und die Identität zu notieren. Führen Sie dann das Cmdlet **Remove-CsTenantBlockedNumberPattern** aus, und übergeben Sie den entsprechenden Identitätswert.

Erlauben Sie Zeit für die Replikation, bevor Sie testen und überprüfen.

#### <a name="view-all-number-patterns"></a>Anzeigen aller Zahlenmuster

Wenn Sie dieses Cmdlet ausführen, wird eine Liste aller blockierten Nummern zurückgegeben, die für einen Mandanten eingegeben werden:

```powershell
Get-CsInboundBlockedNumberPattern
```

Verwenden Sie integrierte PowerShell-Filterfähigkeiten, um die zurückgegebenen Werte nach Bedarf zu analysieren.

## <a name="add-number-exceptions"></a>Hinzufügen von Zahlen Ausnahmen

Sie können Ausnahmen zu blockierten Zahlen Mustern hinzufügen, indem Sie die Cmdlets **New**, **Get**, **Sets**, **Remove**  - **CsTenantBlockNumberExceptionPattern** verwenden.

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) fügt der Mandantenliste ein Zahlen Ausnahme Muster hinzu. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) gibt eine Liste aller Zahlen Ausnahme Muster zurück, die der Mandantenliste hinzugefügt wurden.
- Mit " [CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) " werden mindestens ein Parameter in der Mandantenliste in ein Zahlen Ausnahme Muster geändert.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) entfernt ein Zahlen Ausnahme Muster aus der Mandantenliste.

### <a name="examples"></a>Beispiele

#### <a name="add-a-number-exception"></a>Hinzufügen einer Zahlen Ausnahme

In diesem Beispiel wird ein neues Zahlen Ausnahme Muster erstellt, das standardmäßig als aktiviert hinzugefügt wird. Die Parameter **Enabled** und **Description** sind optional.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Alle Zahlen Ausnahmen anzeigen

In diesem Beispiel ist der Parameter **Identity** optional. Wenn der Parameter **Identity** nicht angegeben ist, gibt dieses Cmdlet eine Liste aller für einen Mandanten eingegebenen Zahlen Ausnahme Muster zurück.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Ändern einer Zahlen Ausnahme

In diesem Beispiel ist der Parameter **Identity** obligatorisch. Mit dem Cmdlet " **Satz-CsTenantBlockedNumberExceptionPattern** " können Sie einen oder mehrere Parameter für eine bestimmte Zahlenmuster Identität ändern.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Entfernen einer Zahlen Ausnahme

In diesem Beispiel ist der Parameter **Identity** erforderlich. Mit diesem Cmdlet wird das angegebene Zahlenmuster aus der Mandantenliste entfernt.  Wenn die Identität unbekannt ist, verwenden Sie das Cmdlet **Get-CsInboundBlockedNumberPattern** , um zuerst das richtige Muster zu finden und die Identität zu notieren. Führen Sie dann das Cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** aus, und übergeben Sie den entsprechenden Identitätswert.Erlauben Sie Zeit für die Replikation, bevor Sie testen und überprüfen.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testen, ob eine Zahl blockiert ist

Verwenden Sie das Cmdlet **Test-CsInboundBlockedNumberPattern** , um zu überprüfen, ob eine Zahl im Mandanten blockiert ist.
 
In diesem Beispiel **sind die Parameter** für die Telefonnummer und den **Mandanten** erforderlich. Der **Parameter** "Telefonnummer" sollte eine numerische Zeichenfolge ohne zusätzliche Zeichen wie + oder-sein. In TRPS ist der **Mandanten Parameter** optional. Der resultierende **isNumberBlocked** -Parameter gibt den Wert "true" zurück, wenn die Zahl im Mandanten blockiert ist, und false, wenn er nicht blockiert ist.

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

## <a name="a-note-about-regex"></a>Eine Notiz zu Regex

Wie bereits erwähnt, wird der Musterabgleich für das Blockieren von Aufrufen mithilfe von Regex ausgeführt. Es stehen mehrere Tools online zur Verfügung, mit denen Sie eine Regex-Musterübereinstimmung überprüfen können. Wenn Sie mit Regex-Mustern nicht vertraut sind, sollten Sie sich etwas Zeit nehmen, um sich mit den Grundlagen vertraut zu machen. Wenn Sie sicherstellen möchten, dass Sie die erwarteten Ergebnisse erzielen, verwenden Sie ein Tool zum Überprüfen von Musterübereinstimmungen, bevor Sie dem Mandanten neue blockierte Nummern Übereinstimmungen hinzufügen.
