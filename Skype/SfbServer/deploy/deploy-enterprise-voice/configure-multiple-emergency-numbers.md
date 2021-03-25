---
title: Konfigurieren mehrerer Notrufnummern in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server konfigurieren.
ms.openlocfilehash: dc05e94e88b371bb9ee22568eff567e758311233
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111891"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Konfigurieren mehrerer Notrufnummern in Skype for Business

In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server konfigurieren.

Skype for Business Server unterstützt jetzt mehrere Notrufnummern für einen Client. Mehrere Notrufnummern sind ein neues Feature, das im kumulativen Update vom Juni 2016 eingeführt wurde. Bevor Sie Ihre Umgebung für die Unterstützung mehrerer Notrufnummern konfigurieren, lesen Sie [unbedingt Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Wenn Sie noch kein Upgrade auf das kumulative Update vom November 2016 durchgeführt haben, lesen Sie [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). Mit dem kumulativen Update vom November 2016 erhöht sich die Anzahl der Supportnotrufnummern von 5 auf 100.

## <a name="configure-multiple-emergency-numbers"></a>Konfigurieren mehrerer Notrufnummern

Zum Konfigurieren mehrerer Notrufnummern verwenden Sie das cmdlet New-CsEmergencyNumber und geben dann den Parameter EmergencyNumbers mit den [Cmdlets New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) an. Eine vollständige Beschreibung aller Standortrichtlinienparameter, z. B. pstN-Verwendung und Erforderlicher Speicherort, finden Sie unter [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

Der folgende Befehl erstellt eine neue Notrufnummer mit der Wählzeichenfolge 911 mithilfe des New-CsEmergency Cmdlets:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

Der nächste Befehl ordnet die Nummer der angegebenen Standortrichtlinie zu, indem der Parameter EmergencyNumbers im cmdlet Set-CsLocationPolicy wird:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

Im nächsten Beispiel wird eine Notrufnummer mit einer einzigen Wählmaske, 112, erstellt:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

Mit dem nächsten Befehl wird eine Notrufnummer mit mehreren Wählmasken erstellt:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

Das nächste Beispiel fügt mehrere Notrufnummern mit mehreren Wählmasken hinzu und ordnet die Notrufnummern dann der angegebenen Standortrichtlinie zu:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

Im nächsten Beispiel werden mehrere Notrufnummern für Gesundheitsanbieter konfiguriert, die sowohl 911 als auch 450 verwenden:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

Im nächsten Beispiel werden mehrere Notrufnummern für die Stadt London konfiguriert:

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

Im nächsten Beispiel werden mehrere Notrufnummern für Indien konfiguriert:

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

Im nächsten Beispiel wird ein vorhandener Eintrag mit der Wählzeichenfolge 911 und den Wählmasken 112 und 999 entfernt:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```