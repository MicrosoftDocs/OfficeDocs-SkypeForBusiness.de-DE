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
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="02808-103">Konfigurieren mehrerer Notrufnummern in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="02808-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="02808-104">In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="02808-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="02808-105">Skype for Business Server unterstützt jetzt mehrere Notrufnummern für einen Client.</span><span class="sxs-lookup"><span data-stu-id="02808-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="02808-106">Mehrere Notrufnummern sind ein neues Feature, das im kumulativen Update vom Juni 2016 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="02808-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="02808-107">Bevor Sie Ihre Umgebung so konfigurieren, dass mehrere Notrufnummern unterstützt werden, sollten Sie den [Plan für mehrere Notrufnummern in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="02808-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="02808-108">Wenn Sie noch nicht auf das kumulative Update vom November 2016 aktualisiert haben, lesen Sie [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="02808-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="02808-109">Mit dem kumulativen Update vom November 2016 steigt die Anzahl der Support Notrufnummern von 5 auf 100.</span><span class="sxs-lookup"><span data-stu-id="02808-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="02808-110">Konfigurieren mehrerer Notrufnummern</span><span class="sxs-lookup"><span data-stu-id="02808-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="02808-111">Um mehrere Notrufnummern zu konfigurieren, verwenden Sie das New-csemergencynumber "-Cmdlet, und geben Sie dann den Parameter" emergencynumbers "mit den Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und [setCsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) an.</span><span class="sxs-lookup"><span data-stu-id="02808-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="02808-112">Eine vollständige Beschreibung aller Standortrichtlinien Parameter, wie PSTN-Verwendung und-Speicherort erforderlich, finden Sie unter [Sets-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="02808-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="02808-113">Mit dem folgenden Befehl wird eine neue Notrufnummer mit Wählzeichenfolge 911 mithilfe des New-CsEmergency-Cmdlets erstellt:</span><span class="sxs-lookup"><span data-stu-id="02808-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="02808-114">Der nächste Befehl ordnet die Nummer der angegebenen ortungsrichtlinie zu, indem der Parameter "emergencynumbers" im CmdletSet-CsLocationPolicy angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="02808-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="02808-115">Im nächsten Beispiel wird eine Notrufnummer mit einer einzigen Wähl Maske 112 erstellt:</span><span class="sxs-lookup"><span data-stu-id="02808-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="02808-116">Mit dem nächsten Befehl wird eine Notrufnummer mit mehreren Wähl Masken erstellt:</span><span class="sxs-lookup"><span data-stu-id="02808-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="02808-117">Im nächsten Beispiel werden mehrere Notrufnummern mit mehreren Wähl Masken hinzugefügt, und dann werden die Notrufnummern mit der angegebenen ortungsrichtlinie verknüpft:</span><span class="sxs-lookup"><span data-stu-id="02808-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="02808-118">Im nächsten Beispiel werden mehrere Notrufnummern für Health Care Provider konfiguriert, die sowohl 911 als auch 450 verwenden:</span><span class="sxs-lookup"><span data-stu-id="02808-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="02808-119">Im nächsten Beispiel werden mehrere Notrufnummern für die Stadt London konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="02808-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="02808-120">Im nächsten Beispiel werden mehrere Notrufnummern für Indien konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="02808-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="02808-121">Im nächsten Beispiel wird ein vorhandener Eintrag mit Wählzeichenfolge 911 und Wähl Masken 112 und 999 entfernt:</span><span class="sxs-lookup"><span data-stu-id="02808-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
