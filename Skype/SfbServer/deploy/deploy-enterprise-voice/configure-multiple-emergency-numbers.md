---
title: Konfigurieren mehrerer Notrufnummern in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server konfigurieren.
ms.openlocfilehash: 0a2387576418aa2631095c46e970fdfac234ca4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303376"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Konfigurieren mehrerer Notrufnummern in Skype for Business

In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server konfigurieren.

Skype for Business Server unterstützt jetzt mehrere Notrufnummern für einen Client. Mehrere Notfallnummern sind eine neue Funktion, die im kumulativen Update vom Juni 2016 eingeführt wurde. Bevor Sie Ihre Umgebung für die Unterstützung mehrerer Notfallnummern konfigurieren, lesen Sie den [Plan für mehrere Notfallnummern in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Wenn Sie noch nicht auf das kumulative Update vom November 2016 aktualisiert haben, lesen Sie [Updates für Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Mit dem kumulativen Update vom November 2016 erhöht sich die Anzahl der Support-Notfallnummern von 5 auf 100. 

## <a name="configure-multiple-emergency-numbers"></a>Konfigurieren mehrerer Notrufnummern

Wenn Sie mehrere Notfallnummern konfigurieren möchten, verwenden Sie das Cmdlet New-CsEmergencyNumber, und geben Sie dann den EmergencyNumbers-Parameter mit den Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und [setCsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) an. Eine vollständige Beschreibung aller Parameter für Standortrichtlinien, wie etwa PSTN-Nutzung und Standort erforderlich, finden Sie unter [festlegen-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

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

Der nächste Befehl erstellt eine Notrufnummer mit mehreren Wähl Masken:

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


