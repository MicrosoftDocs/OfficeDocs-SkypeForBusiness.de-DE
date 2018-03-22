---
title: Wie sollte ich die angezeigten Rufnummern eingeben?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: "Erfahren Sie, wie Telefonnummern einrichten, wenn Sie diese zu Skype für Unternehmen port. "
ms.openlocfilehash: a7364c5ebf72730179c6848dc79172f4f971ff6a
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="1f418-103">Wie sollte ich die angezeigten Rufnummern eingeben?</span><span class="sxs-lookup"><span data-stu-id="1f418-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="1f418-104">Wenn Sie Rufnummern portieren, müssen Sie diese im richtigen Format eingeben.</span><span class="sxs-lookup"><span data-stu-id="1f418-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1f418-105">Jede Telefonnummer oder der Bereich der Telefonnummer muss separat in jeder Zeile eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="1f418-106">Wenn Sie einzelne Rufnummern eingeben:</span><span class="sxs-lookup"><span data-stu-id="1f418-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="1f418-107">Alle Sonderzeichen ignoriert (einschließlich Strich "-").</span><span class="sxs-lookup"><span data-stu-id="1f418-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="1f418-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f418-108">For example:</span></span>
    
  - <span data-ttu-id="1f418-109">Für eine Zahl 10: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* wird auf **+14255550649**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="1f418-110">Für eine Nummer 11: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** wird auf **+14255550649**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="1f418-111">Alle Tags werden ignoriert, wenn 10 oder 11 Ziffern vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1f418-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="1f418-112">Beispielsweise ** \<Div > 4255551234\</div >** **+ 14255551234**werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="1f418-113">"-", Leerzeichen und Klammern werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1f418-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="1f418-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f418-114">For example:</span></span>
    
  - <span data-ttu-id="1f418-115">Für eine Zahl 10: **(425) 555-6776** wird zu **+14255556776**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="1f418-116">Für eine Nummer 11: **1(425) 555-6776** wird auf **+14255556776**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="1f418-117">Alle Buchstaben werden als Sonderzeichen behandelt und eine Telefonnummer Ziffern 10 oder 11 Ziffer wird ignoriert, wenn werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="1f418-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f418-118">For example:</span></span>
    
  - <span data-ttu-id="1f418-119">Für eine Zahl 10: **14jaosia2reoij05jof55506ajfoj49isdjf** wird zu **+14255550649**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="1f418-120">Für eine Nummer 11: **1ade4jaoda2rfoij05ojof55506dsfoj49if** wird zu **+14255550649**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="1f418-121">Eine beliebige Kombination von Sonderzeichen, auch in anderen Sprachen werden korrigiert.</span><span class="sxs-lookup"><span data-stu-id="1f418-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="1f418-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f418-122">For example:</span></span> 
    
  - <span data-ttu-id="1f418-123">Für eine Zahl 10:**中文4中文2ajj5\*() (\*(5()... 551345** wird auf **+14555551345**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="1f418-124">Für eine Nummer 11:**中文4中文2$ a5\*() (\*(5()... 55 (.1345** wird auf **+14555551345**korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="1f418-125">Wenn alle Zahlen weniger als 10 Ziffern oder mehr als 11 Ziffern enthalten, werden sie für den Benutzer an den richtigen hervorgehoben:</span><span class="sxs-lookup"><span data-stu-id="1f418-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="1f418-126">\*\*5551245\* \* wird hervorgehoben und behoben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1f418-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="1f418-127">**1234567891011** wird hervorgehoben und korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1f418-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="1f418-128">Ohne wird automatisch korrigiert werden alle Zahlen, die weniger als 10 Ziffern oder mehr als 11 Stellen mit keine Sonderzeichen sind hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="1f418-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="1f418-129">Für eine 7 Ziffer Zahl ohne Sonderzeichen, die eingegeben wird: **123456abcdefg7** wird hervorgehoben und behoben werden, müssen jedoch die Buchstaben werden nicht ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="1f418-130">Für 7 Ziffer Zahl mit Sonderzeichen, die eingegeben werden: **12345!@#$%^&amp;\*() – @# $% ^&amp;\*(7)** wird hervorgehoben werden, um korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f418-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="1f418-131">Sonderzeichen werden nicht ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1f418-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="1f418-132">Wenn Sie einen Bereich von Rufnummern eingeben.</span><span class="sxs-lookup"><span data-stu-id="1f418-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="1f418-133">Nur zwei Telefonnummern sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1f418-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="1f418-134">Die kleinere Anzahl muss die erste Zahl im Bereich.</span><span class="sxs-lookup"><span data-stu-id="1f418-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="1f418-135">Alle Sonderzeichen (mit Ausnahme der Strich "-") sind wie einzelne Zahlen behandelt.</span><span class="sxs-lookup"><span data-stu-id="1f418-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="1f418-136">Beispielsweise **(425) 555 0&amp;\*(123-(1425) 5557899nm** wird zum behoben **+ 14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="1f418-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="1f418-137">Die "-" wird zur Trennung nur zweier Zahlen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f418-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="1f418-138">Es wird nicht unterstützt, um mehrere einschließen "-" in den Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="1f418-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="1f418-139">Beispielsweise sollte **(425) 555-0649-(425) 555-1115** eingegeben werden, als **(425) 5550649 - (425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="1f418-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="1f418-140">**Eine vollständige schrittweise Anleitung finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).**</span><span class="sxs-lookup"><span data-stu-id="1f418-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="1f418-141">Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="1f418-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="1f418-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1f418-142">Related topics</span></span>
[<span data-ttu-id="1f418-143">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="1f418-143">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="1f418-144">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="1f418-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="1f418-145">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="1f418-145">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="1f418-146">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="1f418-146">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="1f418-147">Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe</span><span class="sxs-lookup"><span data-stu-id="1f418-147">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

## <a name="feedback"></a><span data-ttu-id="1f418-148">Feedback?</span><span class="sxs-lookup"><span data-stu-id="1f418-148">Feedback?</span></span>
<span data-ttu-id="1f418-149">Geben Sie Feedback zu Produkten oder uns Ihre Meinung kennen, finden Sie unter [Skype für Business Feedback](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="1f418-149">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>