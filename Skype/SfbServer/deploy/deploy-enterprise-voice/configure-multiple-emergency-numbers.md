---
title: Konfigurieren Sie mehrerer Notfall Zahlen in Skype für Unternehmen
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Lesen Sie in diesem Thema erfahren, wie mehrere Notfall Nummern in Skype für Business Server konfigurieren.
ms.openlocfilehash: 26d533b277bd8d57166cd65c7326b0e80739bf4e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885547"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Konfigurieren Sie mehrerer Notfall Zahlen in Skype für Unternehmen

Lesen Sie in diesem Thema erfahren, wie mehrere Notfall Nummern in Skype für Business Server konfigurieren.

Skype für Business Server unterstützt jetzt mehrere Notfall Nummern für einen Client an. Mehrere Notfall Nummern ist ein neues Feature in der Juni 2016 kumulative Update. Bevor Sie Ihre Umgebung zur Unterstützung von mehreren Notfall Nummern konfigurieren, müssen Sie unbedingt lesen [für mehrere Notfall Zahlen in Skype für Business Server planen](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Wenn Sie noch nicht auf die November 2016 aktualisiert haben kumulative Update finden Sie unter [Updates für Skype für Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Mit der November 2016 erhöht sich Kumulatives Update, die Anzahl der Notfall Nummern für den Support von 5 bis 100. 

## <a name="configure-multiple-emergency-numbers"></a>Konfigurieren mehrerer Notrufnummern

Um mehrere Notfall Nummern zu konfigurieren, verwenden Sie das Cmdlet "New-CsEmergencyNumber", und geben Sie den Parameter EmergencyNumbers mit den Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Eine vollständige Beschreibung aller Speicherort Richtlinie Parameter, wie PSTN-Verwendung und Standort erforderlich sind finden Sie unter [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

Der folgende Befehl erstellt über das Cmdlet „New-CsEmergency“ eine neue Notrufnummer mit der Wählzeichenfolge „911“:

```
> $a = New-CsEmergencyNumber -DialString 911 
```

Der nächste Befehl ordnet die Nummer der angegebenen Standortrichtlinie zu, indem er den „EmergencyNumbers“-Parameter im Cmdlet „Set-CsLocationPolicy“ angibt:

```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

Im nächsten Beispiel wird eine Notrufnummer mit einer einzigen Wählmaske (112) erstellt:

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

Der nächste Befehl erstellt eine Notrufnummer mit mehreren DFÜ-Masken:

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

Im nächsten Beispiel werden mehrere Notrufnummern mit mehreren Wählmasken hinzugefügt, und anschließend werden die Notrufnummern der angegebenen Standortrichtlinie zugeordnet:

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

Im nächsten Beispiel werden mehrere Notrufnummern für Notfalleinrichtungen konfiguriert, die sowohl 911 als auch 450 verwenden:  

```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

Im nächsten Beispiel werden mehrere Notrufnummern für die Stadt London konfiguriert:

```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

Im nächsten Beispiel werden mehrere Notrufnummern für Indien konfiguriert:

```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

Im nächsten Beispiel wird ein vorhandener Eintrag mit der Wählzeichenfolge „911“ und den Wählmasken „112“ und „999“ entfernt:

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


