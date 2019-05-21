---
title: Wie sollte ich die Telefonnummern eingeben?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Hier erfahren Sie, wie Sie Telefonnummern einrichten, wenn Sie Sie in Skype for Business portieren. '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280530"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="d72cb-103">Wie sollte ich die Telefonnummern eingeben?</span><span class="sxs-lookup"><span data-stu-id="d72cb-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="d72cb-104">Wenn Sie Telefonnummern portieren, müssen Sie diese im richtigen Format eingeben.</span><span class="sxs-lookup"><span data-stu-id="d72cb-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d72cb-105">Jede Telefonnummer oder jeder Rufnummernbereich muss für jede Zeile separat eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d72cb-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="d72cb-106">Wenn Sie einzelne Telefonnummern eingeben:</span><span class="sxs-lookup"><span data-stu-id="d72cb-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="d72cb-107">Alle Sonderzeichen werden ignoriert (einschließlich Bindestrich "-").</span><span class="sxs-lookup"><span data-stu-id="d72cb-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="d72cb-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d72cb-108">For example:</span></span>
    
  - <span data-ttu-id="d72cb-109">Für eine 10-stellige Zahl: \*\* &amp; \*(\*425 ()\*&amp;(&amp;\*4 ())\*(250649\*\* wird auf **+ 14255550649**korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="d72cb-110">Für eine 11-stellige Zahl **:\*1 ()\*&amp;(&amp;\*42 ()\*&amp;(55550649** wird auf **+ 14255550649**korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="d72cb-111">Alle Tags werden ignoriert, wenn 10 oder 11 Ziffern vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d72cb-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="d72cb-112">Beispielsweise ist \*\* \<div> 4255551234\</div>\*\* **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="d72cb-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="d72cb-113">"-", Leerzeichen und Klammern werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="d72cb-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d72cb-114">For example:</span></span>
    
  - <span data-ttu-id="d72cb-115">Für eine 10-stellige Zahl: **(425) 555-6776** wird auf **+ 14255556776**korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="d72cb-116">Für eine 11-stellige Zahl: **1 (425) 555-6776** wird auf **+ 14255556776**korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="d72cb-117">Alle Buchstaben werden als Sonderzeichen behandelt und ignoriert, wenn eine 10-stellige oder eine 11-stellige Telefonnummer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d72cb-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="d72cb-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d72cb-118">For example:</span></span>
    
  - <span data-ttu-id="d72cb-119">Für eine 10-stellige Zahl: **14jaosia2reoij05jof55506ajfoj49isdjf** wird auf **+ 14255550649**korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="d72cb-120">Für eine 11-stellige Zahl: **1ade4jaoda2rfoij05ojof55506dsfoj49if** wird auf **+ 14255550649**korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="d72cb-121">Eine Kombination von Sonderzeichen, auch in anderen Sprachen, wird korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="d72cb-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d72cb-122">For example:</span></span> 
    
  - <span data-ttu-id="d72cb-123">Für eine 10-stellige Zahl:**中文 4\*中文2ajj5 ()\*((5 ()... 551345** wird auf **+ 14555551345**korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="d72cb-124">Für eine 11-stellige Zahl:**中文 4 中文 2 $\*A5 ()\*((5 ()... 55 (1345** wird auf **+ 14555551345**korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="d72cb-125">Wenn zahlen weniger als 10 Ziffern oder mehr als 11 Ziffern enthalten, werden diese hervorgehoben, damit der Benutzer Sie korrigieren kann:</span><span class="sxs-lookup"><span data-stu-id="d72cb-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="d72cb-126">\*\*5551245\* \* wird hervorgehoben und muss korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="d72cb-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="d72cb-127">**1234567891011** wird hervorgehoben und muss korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="d72cb-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="d72cb-128">Zahlen, die weniger als 10 Ziffern oder mehr als 11 Ziffern mit Sonderzeichen enthalten, werden hervorgehoben, ohne dass Sie automatisch korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="d72cb-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="d72cb-129">Für eine siebenstellige Zahl ohne eingegebene Sonderzeichen: **123456abcdefg7** wird hervorgehoben und muss korrigiert werden, aber die Buchstaben werden nicht ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="d72cb-130">Bei einer siebenstelligen Zahl mit Sonderzeichen, die eingegeben werden **: 12345! @ # $%&amp;\*^ ()--@ # $%&amp;\*^ () 7** wird hervorgehoben, um korrigiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="d72cb-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="d72cb-131">Die Sonderzeichen werden nicht ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="d72cb-132">Wenn Sie einen Bereich von Telefonnummern eingeben.</span><span class="sxs-lookup"><span data-stu-id="d72cb-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="d72cb-133">Nur zwei Telefonnummern sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d72cb-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="d72cb-134">Die kleinere Zahl muss die erste Zahl im Bereich sein.</span><span class="sxs-lookup"><span data-stu-id="d72cb-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="d72cb-135">Alle Sonderzeichen (mit Ausnahme des Bindestrichs "-") werden wie einzelne Zahlen behandelt.</span><span class="sxs-lookup"><span data-stu-id="d72cb-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="d72cb-136">Beispielsweise wird **(425) 555 0&amp;\*(123-(1425) 5557899nm** auf **+ 14255550123-+ 13202040659**korrigiert.</span><span class="sxs-lookup"><span data-stu-id="d72cb-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="d72cb-137">Das "-" wird verwendet, um nur die beiden Zahlen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="d72cb-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="d72cb-138">Es wird nicht unterstützt, mehrere "-" im Zahlenbereich einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="d72cb-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="d72cb-139">Beispielsweise sollte **(425) 555-0649-(425) 555-1115** als **(425) 5550649-(425) 5551115**eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d72cb-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="d72cb-140">**Eine vollständige Schritt-für-Schritt-Anleitung finden Sie unter [übertragen von Telefonnummern zu Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="d72cb-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="d72cb-141">Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="d72cb-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="d72cb-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d72cb-142">Related topics</span></span>
[<span data-ttu-id="d72cb-143">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="d72cb-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="d72cb-144">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="d72cb-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="d72cb-145">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="d72cb-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="d72cb-146">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="d72cb-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="d72cb-147">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d72cb-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 