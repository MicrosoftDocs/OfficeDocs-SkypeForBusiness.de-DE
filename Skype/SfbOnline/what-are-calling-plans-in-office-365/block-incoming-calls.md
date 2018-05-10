---
title: Blockieren Sie eingehende Anrufe in Skype Online für Unternehmen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 05/07/2018
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto: Skype for Business
localization_priority: Normal
ms.custom: Use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: 9a9ff446d7b95588f1d9c2460db1284de717e557
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
 # <a name="block-inbound-calls"></a>Eingehende Anrufe blockieren

Skype für Business Online aufrufen plant unterstützt jetzt die Blockierung von eingehende Anrufe aus dem öffentlichen Telefonfestnetz (PSTN). Dieses Feature ermöglicht, dass eine globale Liste Mandanten rufnummernmuster definiert werden, sodass die Anrufer-ID von jeder eingehende PSTN-Anruf, um den Mandanten für eine Übereinstimmung mit der Liste eingecheckt werden kann. Wenn eine Übereinstimmung vorliegt, wird ein eingehender Anruf zurückgewiesen. 

Dieses Feature zum Blockieren von eingehenden Anruf funktioniert nur für eingehende Anrufe, die aus dem PSTN stammen und funktioniert nur für einzelne globale Mandanten und ist nicht für jeden Benutzer einzeln verfügbar.

Dieses Feature ist noch nicht für die direkte Weiterleitung verfügbar.

>[Hinweis] Blockierte Anrufer können geringfügig Symptome auftreten, wenn sie blockiert wurden. Das Verhalten basiert auf wie der blockierten Anrufer Netzbetreiber die Benachrichtigung behandelt, die der Anruf nicht zulässig ist, erfolgreich ausgeführt werden. Beispiele Netzbetreiber Meldung an, der Anruf kann nicht abgeschlossen werden, wie gewählt, oder löschen einfach den Anruf.

## <a name="call-blocking-admin-controls-and-information"></a>Rufen Sie die blockierenden Admin-Steuerelemente und Informationen
Admin-Steuerelementen für blockierende Zahlen werden nur von PowerShell bereitgestellt. Block rufnummernmuster sind als Muster für reguläre Ausdrücke definiert. Die Reihenfolge der Ausdrücke ist nicht von Bedeutung – führt das erste in der Liste übereinstimmendes Muster zu den Anruf blockiert. Eine neue Nummer oder ein Muster hinzugefügt oder entfernt, in der Blockier-Anrufer Liste kann bis zu 24 Stunden dauern für das Muster aktiv wird.
## <a name="call-blocking-powershell-commands"></a>Rufen Sie die Blockierung von PowerShell-Befehlen

*InboundBlockedNumberPattern* Rufnummernmuster werden über die *CsInboundBlockedNumberPattern* Befehle **New**, **Abrufen**, **festlegen**und **Entfernen von**verwaltet.  

Sie können einem bestimmten Muster verwalten, indem Sie diese Cmdlets, einschließlich der Möglichkeit zum Umschalten der Aktivierungs von einem bestimmten Muster.
- *Get-CsInboundBlockedNumberPattern* Gibt eine Liste der alle blockierten rufnummernmuster einschließlich Name, Beschreibung, aktiviert (True/False), und das Muster für die einzelnen Mandanten Liste hinzugefügt.
- *Neue CsInboundBlockedNumberPattern* Fügt eine blockierte Nummernmuster zur Liste Mandanten.
- *Remove-CsInboundBlockedNumberPattern* Entfernt eine blockierte Nummernmuster aus der Liste Mandanten.
- *Set-CsInboundBlockedNumberPattern* Ändert mindestens einen Parameter, der eine blockierte Nummernmuster in der Liste Mandanten.
- *TenantBlockedCallingNumbers* Zum Anzeigen und Aktivierung von der Funktion zum Blockieren des gesamten Anruf wird über die CsTenantBlockingCallingNumbers Befehle abrufen und Festlegen von verwaltet. 
- *Get-CsTenantBlockedCallingNumbers* Gibt die Parameter für die globale gesperrten Liste einschließlich aktiviert (True/False) zurück. Es ist eine einzelne globale Mandanten-Richtlinie, die manuell als nicht geändert werden kann, um das Feature vollständig auf/deaktivieren.
- *Set-CsTenantBlockedCallingNumbers* Ermöglicht das Ändern der globalen Mandanten blockiert Anrufe ein-/ausschalten auf der Ebene der Mandanten aktiviert werden.

### <a name="examples"></a>Beispiele
#### <a name="blocking-a-number"></a>Blockieren einer Zahl

In diesem Beispiel wird die - aktiviert und - Beschreibung-Parameter sind optional:

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 Erstellen, die ein neues Muster das Muster als aktiviert, und die Beschreibung ist immer standardmäßig hinzugefügt wird und optionales Feld, um weitere Informationen bereitzustellen. 

Es wird empfohlen, dass Sie einen aussagekräftigen Namen zu verstehen, warum das Muster hinzugefügt wurde auf einfache Weise bereitstellen. Im Fall einfach blockierenden Spam Zahlen, benennen Sie die Regel die gleichen berücksichtigt als Nummernmuster, die verglichen, und fügen Sie zusätzliche Informationen in der Beschreibung nach Bedarf.

Muster werden mithilfe von regulären Ausdrücken (Regex) zugeordnet. Zeitpunkt vor dem Testen und Überprüfen der Replikation ermöglichen.

#### <a name="allowing-a-number"></a>Eine Zahl zulassen

In diesem Beispiel wird der Identitätsparameter erforderlich:`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`
 
Wenn die Identität nicht bekannt ist, verwenden Sie das Cmdlet *Get-CsInb UndBlockedNumberPattern* zuerst Suchen des richtigen Musters und beachten Sie die Identität. Führen Sie das Cmdlet *zu entfernen* , und übergeben Sie den entsprechenden Wert für die Identität.

Zeitpunkt vor dem Testen und Überprüfen der Replikation ermöglichen.
#### <a name="view-all-number-patterns"></a>Zeigt alle Anzahl Muster
Dieses Cmdlet gibt eine Liste aller eingegeben blockiert Zahlen für einen Mandanten zurück:`Get-CsInboundBlockedNumberPattern`

Mithilfe von integrierten PowerShell Fähigkeiten Filtern um nach Bedarf die zurückgegebenen Werte zu analysieren.

#### <a name="a-note-on-regex"></a>Ein Hinweis zu Regex
Wie bereits erwähnt, erfolgt die Mustervergleichs für das Blockieren von Anrufer mithilfe von regulären Ausdrücken (Regex). Es gibt mehrere Tools online zu helfen, eine Übereinstimmung mit einem Muster überprüft. Wenn Sie nicht mit Regex-Muster vertraut sind, wird empfohlen, dass Sie eine Weile dauern, machen Sie sich mit den Grundlagen vertraut, und verwenden Sie ein Tool für Mustervergleiche überprüfen, bevor Sie neue blockierte übereinstimmt Ihres Mandanten hinzufügen, um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten. 

## <a name="related-topics"></a>See Also
[Einrichten des Computers für Skype für das Business Online Management mithilfe von Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell )
