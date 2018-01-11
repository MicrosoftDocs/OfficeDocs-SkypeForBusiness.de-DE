---
title: Wie sollte ich die angezeigten Rufnummern eingeben?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom: Calling Plans
description: "Erfahren Sie, wie Telefonnummern einrichten, wenn Sie diese zu Skype für Unternehmen port. "
ms.openlocfilehash: 1906fc98f47402ec740d71ff69b67b07392ae57d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="431f4-103">Wie sollte ich die angezeigten Rufnummern eingeben?</span><span class="sxs-lookup"><span data-stu-id="431f4-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="431f4-104">Wenn Sie Rufnummern portieren, müssen Sie diese im richtigen Format eingeben.</span><span class="sxs-lookup"><span data-stu-id="431f4-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="431f4-105">Jede Telefonnummer oder der Bereich der Telefonnummer muss separat in jeder Zeile eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="431f4-106">Wenn Sie einzelne Rufnummern eingeben:</span><span class="sxs-lookup"><span data-stu-id="431f4-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="431f4-107">Alle Sonderzeichen ignoriert (einschließlich Strich "-").</span><span class="sxs-lookup"><span data-stu-id="431f4-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="431f4-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="431f4-108">For example:</span></span>
    
  - <span data-ttu-id="431f4-109">Für eine Zahl 10: \*\* &amp; \\*(425\\*() (\\*&amp;4&amp;\\*()) (\\*250649\*\* wird auf **+14255550649**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-109">For a 10-digit number: **&amp;\\*(425\\*()(\\*&amp;4&amp;\\*())(\\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="431f4-110">Für eine Nummer 11: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** wird auf **+14255550649**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="431f4-111">Alle Tags werden ignoriert, wenn 10 oder 11 Ziffern vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="431f4-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="431f4-112">Beispielsweise ** \<Div > 4255551234\</div >** **+ 14255551234**werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="431f4-113">"-", Leerzeichen und Klammern werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="431f4-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="431f4-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="431f4-114">For example:</span></span>
    
  - <span data-ttu-id="431f4-115">Für eine Zahl 10: **(425) 555-6776** wird zu **+14255556776**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="431f4-116">Für eine Nummer 11: **1(425) 555-6776** wird auf **+14255556776**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="431f4-117">Alle Buchstaben werden als Sonderzeichen behandelt und eine Telefonnummer Ziffern 10 oder 11 Ziffer wird ignoriert, wenn werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="431f4-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="431f4-118">For example:</span></span>
    
  - <span data-ttu-id="431f4-119">Für eine Zahl 10: **14jaosia2reoij05jof55506ajfoj49isdjf** wird zu **+14255550649**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="431f4-120">Für eine Nummer 11: **1ade4jaoda2rfoij05ojof55506dsfoj49if** wird zu **+14255550649**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="431f4-121">Eine beliebige Kombination von Sonderzeichen, auch in anderen Sprachen werden korrigiert.</span><span class="sxs-lookup"><span data-stu-id="431f4-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="431f4-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="431f4-122">For example:</span></span> 
    
  - <span data-ttu-id="431f4-123">Für eine Zahl 10:**中文4中文2ajj5\*() (\*(5()... 551345** wird auf **+14555551345**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="431f4-124">Für eine Nummer 11:**中文4中文2$ a5\*() (\*(5()... 55 (.1345** wird auf **+14555551345**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="431f4-125">Wenn alle Zahlen weniger als 10 Ziffern oder mehr als 11 Ziffern enthalten, werden sie für den Benutzer an den richtigen hervorgehoben:</span><span class="sxs-lookup"><span data-stu-id="431f4-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="431f4-126">\*\*5551245\* \* wird hervorgehoben und behoben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="431f4-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="431f4-127">**1234567891011** wird hervorgehoben und korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="431f4-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="431f4-128">Ohne wird automatisch korrigiert werden alle Zahlen, die weniger als 10 Ziffern oder mehr als 11 Stellen mit keine Sonderzeichen sind hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="431f4-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="431f4-129">Für eine 7 Ziffer Zahl ohne Sonderzeichen, die eingegeben wird: **123456abcdefg7** wird hervorgehoben und behoben werden, müssen jedoch die Buchstaben werden nicht ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="431f4-130">Für 7 Ziffer Zahl mit Sonderzeichen, die eingegeben werden: **12345!@#$%^&amp;\*() – @# $% ^&amp;\*(7)** wird hervorgehoben werden, um korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="431f4-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="431f4-131">Sonderzeichen werden nicht ignoriert.</span><span class="sxs-lookup"><span data-stu-id="431f4-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="431f4-132">Wenn Sie einen Bereich von Rufnummern eingeben.</span><span class="sxs-lookup"><span data-stu-id="431f4-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="431f4-133">Nur zwei Telefonnummern sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="431f4-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="431f4-134">Die kleinere Anzahl muss die erste Zahl im Bereich.</span><span class="sxs-lookup"><span data-stu-id="431f4-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="431f4-135">Alle Sonderzeichen (mit Ausnahme der Strich "-") sind wie einzelne Zahlen behandelt.</span><span class="sxs-lookup"><span data-stu-id="431f4-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="431f4-136">Beispielsweise **(425) 555 0&amp;\\*(123-(1425) 5557899nm** wird zum behoben **+ 14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="431f4-136">For example, **(425)555 0&amp;\\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="431f4-137">Die "-" wird zur Trennung nur zweier Zahlen verwendet.</span><span class="sxs-lookup"><span data-stu-id="431f4-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="431f4-138">Es wird nicht unterstützt, um mehrere einschließen "-" in den Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="431f4-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="431f4-139">Beispielsweise sollte **(425) 555-0649-(425) 555-1115** eingegeben werden, als **(425) 5550649 - (425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="431f4-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="431f4-140">**Eine vollständige schrittweise Anleitung finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).**</span><span class="sxs-lookup"><span data-stu-id="431f4-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="431f4-141">Wenn Sie weitere Telefonnummern als dieser erhalten möchten müssen, wenden Sie [Unterstützung für Business-Produkte – Admin Hilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="431f4-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="431f4-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="431f4-142">Related topics</span></span>
[<span data-ttu-id="431f4-143">Transferring phone numbers common questions</span><span class="sxs-lookup"><span data-stu-id="431f4-143">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="431f4-144">Verschiedene Arten von Telefonnummern für den Aufruf von plant verwendet</span><span class="sxs-lookup"><span data-stu-id="431f4-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="431f4-145">Telefonnummern für Ihre Organisation verwalten</span><span class="sxs-lookup"><span data-stu-id="431f4-145">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="431f4-146">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="431f4-146">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="431f4-147">Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe</span><span class="sxs-lookup"><span data-stu-id="431f4-147">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)