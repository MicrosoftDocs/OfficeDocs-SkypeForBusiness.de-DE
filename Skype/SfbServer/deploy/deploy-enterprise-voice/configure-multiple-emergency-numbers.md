---
title: Konfigurieren mehrerer Notrufnummern in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 4/21/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: In diesem Thema erfahren Sie, wie Sie in Skype for Business Server 2015 mehrere Notrufnummern konfigurieren.
ms.openlocfilehash: ad2f048294b7eeef6d675fdf80884ae13cc75a61
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a><span data-ttu-id="13ad4-103">Konfigurieren mehrerer Notrufnummern in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="13ad4-103">Configure multiple emergency numbers in Skype for Business 2015</span></span>
 
<span data-ttu-id="13ad4-104">In diesem Thema erfahren Sie, wie Sie in Skype for Business Server 2015 mehrere Notrufnummern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="13ad4-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="13ad4-105">Skype für Business Server unterstützt jetzt mehrere Notfall Nummern für einen Client an.</span><span class="sxs-lookup"><span data-stu-id="13ad4-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="13ad4-106">Mehrere Notfall Nummern ist ein neues Feature in der Juni 2016 kumulative Update.</span><span class="sxs-lookup"><span data-stu-id="13ad4-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="13ad4-107">Bevor Sie Ihre Umgebung zur Unterstützung von mehreren Notfall Nummern konfigurieren, müssen Sie [mehrere Notfall Zahlen in Skype für Business Server 2015 planen](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="13ad4-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="13ad4-108">Wenn Sie noch nicht auf die November 2016 aktualisiert haben kumulative Update finden Sie unter [Updates für Skype für Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="13ad4-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="13ad4-109">Mit der November 2016 erhöht sich Kumulatives Update, die Anzahl der Notfall Nummern für den Support von 5 bis 100.</span><span class="sxs-lookup"><span data-stu-id="13ad4-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 
  
## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="13ad4-110">Konfigurieren mehrerer Notrufnummern</span><span class="sxs-lookup"><span data-stu-id="13ad4-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="13ad4-111">Um mehrere Notfall Nummern zu konfigurieren, verwenden Sie das Cmdlet "New-CsEmergencyNumber", und geben Sie den Parameter EmergencyNumbers mit den Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="13ad4-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="13ad4-112">Eine vollständige Beschreibung aller Speicherort Richtlinie Parameter, wie PSTN-Verwendung und Standort erforderlich sind finden Sie unter [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="13ad4-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>
  
<span data-ttu-id="13ad4-113">Der folgende Befehl erstellt über das Cmdlet „New-CsEmergency“ eine neue Notrufnummer mit der Wählzeichenfolge „911“:</span><span class="sxs-lookup"><span data-stu-id="13ad4-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 

```

<span data-ttu-id="13ad4-114">Der nächste Befehl ordnet die Nummer der angegebenen Standortrichtlinie zu, indem er den „EmergencyNumbers“-Parameter im Cmdlet „Set-CsLocationPolicy“ angibt:</span><span class="sxs-lookup"><span data-stu-id="13ad4-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

<span data-ttu-id="13ad4-115">Im nächsten Beispiel wird eine Notrufnummer mit einer einzigen Wählmaske (112) erstellt:</span><span class="sxs-lookup"><span data-stu-id="13ad4-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

<span data-ttu-id="13ad4-116">Der nächste Befehl erstellt eine Notrufnummer mit mehreren DFÜ-Masken:</span><span class="sxs-lookup"><span data-stu-id="13ad4-116">The next command creates an emergency number with multiple dial masks:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

<span data-ttu-id="13ad4-117">Im nächsten Beispiel werden mehrere Notrufnummern mit mehreren Wählmasken hinzugefügt, und anschließend werden die Notrufnummern der angegebenen Standortrichtlinie zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="13ad4-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

<span data-ttu-id="13ad4-118">Im nächsten Beispiel werden mehrere Notrufnummern für Notfalleinrichtungen konfiguriert, die sowohl 911 als auch 450 verwenden: </span><span class="sxs-lookup"><span data-stu-id="13ad4-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="13ad4-119">Im nächsten Beispiel werden mehrere Notrufnummern für die Stadt London konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="13ad4-119">The next example configures multiple emergency numbers for the city of London:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

<span data-ttu-id="13ad4-120">Im nächsten Beispiel werden mehrere Notrufnummern für Indien konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="13ad4-120">The next example configures multiple emergency numbers for India:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

<span data-ttu-id="13ad4-121">Im nächsten Beispiel wird ein vorhandener Eintrag mit der Wählzeichenfolge „911“ und den Wählmasken „112“ und „999“ entfernt:</span><span class="sxs-lookup"><span data-stu-id="13ad4-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```


