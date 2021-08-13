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
ms.openlocfilehash: e0a12bb63578e5070a079b6ab4561d67255f7199a0042066467fb40eafb54637
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300341"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Konfigurieren mehrerer Notrufnummern in Skype for Business

In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server konfigurieren.

Skype for Business Server unterstützt jetzt mehrere Notrufnummern für einen Client. Mehrere Notrufnummern sind ein neues Feature, das im kumulativen Update vom Juni 2016 eingeführt wurde. Bevor Sie Ihre Umgebung so konfigurieren, dass mehrere Notrufnummern unterstützt werden, lesen Sie ["Plan for multiple emergency numbers" in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)

> [!NOTE]
> Wenn Sie noch kein Upgrade auf das kumulative Update vom November 2016 durchgeführt haben, lesen Sie [updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). Mit dem kumulativen Update vom November 2016 erhöht sich die Anzahl der Support-Notrufnummern von 5 auf 100.

## <a name="configure-multiple-emergency-numbers"></a>Konfigurieren mehrerer Notrufnummern

Um mehrere Notrufnummern zu konfigurieren, verwenden Sie das Cmdlet New-CsEmergencyNumber und geben dann den Parameter "EmergencyNumbers" mit den Cmdlets ["New-CsLocationPolicy"](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und ["Set-CsLocationPolicy" an.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Eine vollständige Beschreibung aller Standortrichtlinienparameter, z. B. PSTN-Verwendung und erforderlicher Standort, finden Sie unter ["Set-CsLocationPolicy".](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)

Mit dem folgenden Befehl wird mithilfe des Cmdlets New-CsEmergency eine neue Notrufnummer mit der Wählzeichenfolge 911 erstellt:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

Der nächste Befehl ordnet die Nummer der angegebenen Standortrichtlinie zu, indem der Parameter "EmergencyNumbers" im Cmdlet Set-CsLocationPolicy angegeben wird:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

Im nächsten Beispiel wird eine Notrufnummer mit einer einzelnen Wählmaske erstellt, 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

Mit dem nächsten Befehl wird eine Notrufnummer mit mehreren Wählmasken erstellt:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

Im nächsten Beispiel werden mehrere Notrufnummern mit mehreren Wählmasken hinzugefügt, und anschließend werden die Notrufnummern der angegebenen Standortrichtlinie zugeordnet:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

Im nächsten Beispiel werden mehrere Notrufnummern für Gesundheitsdienstleister konfiguriert, die sowohl 911 als auch 450 verwenden:

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