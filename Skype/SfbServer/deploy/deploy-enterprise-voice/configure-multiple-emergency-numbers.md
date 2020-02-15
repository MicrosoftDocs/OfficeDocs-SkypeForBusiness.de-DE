---
title: Konfigurieren mehrerer Notrufnummern in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027796"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Konfigurieren mehrerer Notrufnummern in Skype for Business

In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server konfigurieren.

Skype for Business Server unterstützt jetzt mehrere Notrufnummern für einen Client. Mehrere Notrufnummern sind ein neues Feature, das im kumulativen Update vom Juni 2016 eingeführt wurde. Bevor Sie Ihre Umgebung so konfigurieren, dass mehrere Notrufnummern unterstützt werden, sollten Sie den [Plan für mehrere Notrufnummern in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)lesen.

> [!NOTE]
> Wenn Sie noch nicht auf das kumulative Update vom November 2016 aktualisiert haben, lesen Sie [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). Mit dem kumulativen Update vom November 2016 steigt die Anzahl der Support Notrufnummern von 5 auf 100.

## <a name="configure-multiple-emergency-numbers"></a>Konfigurieren mehrerer Notrufnummern

Um mehrere Notrufnummern zu konfigurieren, verwenden Sie das New-csemergencynumber "-Cmdlet, und geben Sie dann den Parameter" emergencynumbers "mit den Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und [setCsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) an. Eine vollständige Beschreibung aller Standortrichtlinien Parameter, wie PSTN-Verwendung und-Speicherort erforderlich, finden Sie unter [Sets-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

Mit dem folgenden Befehl wird eine neue Notrufnummer mit Wählzeichenfolge 911 mithilfe des New-CsEmergency-Cmdlets erstellt:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

Der nächste Befehl ordnet die Nummer der angegebenen ortungsrichtlinie zu, indem der Parameter "emergencynumbers" im CmdletSet-CsLocationPolicy angegeben wird:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

Im nächsten Beispiel wird eine Notrufnummer mit einer einzigen Wähl Maske 112 erstellt:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

Mit dem nächsten Befehl wird eine Notrufnummer mit mehreren Wähl Masken erstellt:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

Im nächsten Beispiel werden mehrere Notrufnummern mit mehreren Wähl Masken hinzugefügt, und dann werden die Notrufnummern mit der angegebenen ortungsrichtlinie verknüpft:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

Im nächsten Beispiel werden mehrere Notrufnummern für Health Care Provider konfiguriert, die sowohl 911 als auch 450 verwenden:

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

Im nächsten Beispiel wird ein vorhandener Eintrag mit Wählzeichenfolge 911 und Wähl Masken 112 und 999 entfernt:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
