---
title: Konfigurieren mehrerer Notrufnummern in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 4/21/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: In diesem Thema erfahren Sie, wie Sie in Skype for Business Server 2015 mehrere Notrufnummern konfigurieren.
ms.openlocfilehash: 98d9bbef92f5f3894fb288c01e474288f9f7bb4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a>Konfigurieren mehrerer Notrufnummern in Skype for Business Server 2015
 
In diesem Thema erfahren Sie, wie Sie in Skype for Business Server 2015 mehrere Notrufnummern konfigurieren.
  
Skype für Business Server unterstützt jetzt mehrere Notfall Nummern für einen Client an. Mehrere Notfall Nummern ist ein neues Feature in der Juni 2016 kumulative Update. Bevor Sie Ihre Umgebung zur Unterstützung von mehreren Notfall Nummern konfigurieren, müssen Sie [mehrere Notfall Zahlen in Skype für Business Server 2015 planen](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)lesen.
  
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


