---
title: Konfigurieren Sie mehrerer Notfall Zahlen in Skype für Unternehmen
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
ms.openlocfilehash: 64f9368b5d6eaac1c2f872ebf48152514cc99b34
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372685"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="f4731-103">Konfigurieren Sie mehrerer Notfall Zahlen in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="f4731-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="f4731-104">Lesen Sie in diesem Thema erfahren, wie mehrere Notfall Nummern in Skype für Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f4731-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="f4731-105">Skype für Business Server unterstützt jetzt mehrere Notfall Nummern für einen Client an.</span><span class="sxs-lookup"><span data-stu-id="f4731-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="f4731-106">Mehrere Notfall Nummern ist ein neues Feature in der Juni 2016 kumulative Update.</span><span class="sxs-lookup"><span data-stu-id="f4731-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="f4731-107">Bevor Sie Ihre Umgebung zur Unterstützung von mehreren Notfall Nummern konfigurieren, müssen Sie unbedingt lesen [für mehrere Notfall Zahlen in Skype für Business Server planen](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="f4731-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f4731-108">Wenn Sie noch nicht auf die November 2016 aktualisiert haben kumulative Update finden Sie unter [Updates für Skype für Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="f4731-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="f4731-109">Mit der November 2016 erhöht sich Kumulatives Update, die Anzahl der Notfall Nummern für den Support von 5 bis 100.</span><span class="sxs-lookup"><span data-stu-id="f4731-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="f4731-110">Konfigurieren mehrerer Notrufnummern</span><span class="sxs-lookup"><span data-stu-id="f4731-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="f4731-111">Um mehrere Notfall Nummern zu konfigurieren, verwenden Sie das Cmdlet "New-CsEmergencyNumber", und geben Sie den Parameter EmergencyNumbers mit den Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f4731-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="f4731-112">Eine vollständige Beschreibung aller Speicherort Richtlinie Parameter, wie PSTN-Verwendung und Standort erforderlich sind finden Sie unter [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f4731-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="f4731-113">Der folgende Befehl erstellt über das Cmdlet „New-CsEmergency“ eine neue Notrufnummer mit der Wählzeichenfolge „911“:</span><span class="sxs-lookup"><span data-stu-id="f4731-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="f4731-114">Der nächste Befehl ordnet die Nummer der angegebenen Standortrichtlinie zu, indem er den „EmergencyNumbers“-Parameter im Cmdlet „Set-CsLocationPolicy“ angibt:</span><span class="sxs-lookup"><span data-stu-id="f4731-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

<span data-ttu-id="f4731-115">Im nächsten Beispiel wird eine Notrufnummer mit einer einzigen Wählmaske (112) erstellt:</span><span class="sxs-lookup"><span data-stu-id="f4731-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

<span data-ttu-id="f4731-116">Der nächste Befehl erstellt eine Notrufnummer mit mehreren DFÜ-Masken:</span><span class="sxs-lookup"><span data-stu-id="f4731-116">The next command creates an emergency number with multiple dial masks:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

<span data-ttu-id="f4731-117">Im nächsten Beispiel werden mehrere Notrufnummern mit mehreren Wählmasken hinzugefügt, und anschließend werden die Notrufnummern der angegebenen Standortrichtlinie zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="f4731-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

<span data-ttu-id="f4731-118">Im nächsten Beispiel werden mehrere Notrufnummern für Notfalleinrichtungen konfiguriert, die sowohl 911 als auch 450 verwenden: </span><span class="sxs-lookup"><span data-stu-id="f4731-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 

```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="f4731-119">Im nächsten Beispiel werden mehrere Notrufnummern für die Stadt London konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="f4731-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="f4731-120">Im nächsten Beispiel werden mehrere Notrufnummern für Indien konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="f4731-120">The next example configures multiple emergency numbers for India:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="f4731-121">Im nächsten Beispiel wird ein vorhandener Eintrag mit der Wählzeichenfolge „911“ und den Wählmasken „112“ und „999“ entfernt:</span><span class="sxs-lookup"><span data-stu-id="f4731-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


