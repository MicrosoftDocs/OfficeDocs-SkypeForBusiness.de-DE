---
title: Weitere Informationen zum Aufrufen von Zeile-ID und Aufrufen von Anrufernamens
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Hier erfahren Sie, warum Sie autorisierte Personen hinzufügen, die Änderungen an das Konto vornehmen können, wenn Sie den Assistenten für neue lokale Anzahl Port Reihenfolge verwenden müssen.
ms.openlocfilehash: 1174ba5837bb91c3251232ab48fa63c343425ac1
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="c5a93-103">Weitere Informationen zum Aufrufen von Zeile-ID und Aufrufen von Anrufernamens</span><span class="sxs-lookup"><span data-stu-id="c5a93-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="c5a93-104">CallerID, wie er in der Regel, bezeichnet wird besteht aus zwei Benutzern wahrgenommenen identifizierbare Teile der Informationen:</span><span class="sxs-lookup"><span data-stu-id="c5a93-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="c5a93-105">Eine Telefonnummer ein (normalerweise um als CLID oder Aufruf von Zeile ID bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="c5a93-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="c5a93-106">Aufrufen von Namen ein (normalerweise als CNAM bezeichnet), der bis zu 15 Zeichen lang sein kann.</span><span class="sxs-lookup"><span data-stu-id="c5a93-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="c5a93-107">Wenn ein Aufruf ausgeführt wird, wird die CLID (Telefonnummer) an das Ziel des Netzbetreibers (auch bekannt als der Abbruch Netzbetreiber) weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c5a93-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="c5a93-108">Die CNAM-Informationen für den Anruf kann oder kann nicht mit der Anruf weitergeleitet werden, wie dies hängt wie das Land CNAM (falls überhaupt) implementiert hat.</span><span class="sxs-lookup"><span data-stu-id="c5a93-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="c5a93-109">Die Zuverlässigkeit der Lieferung mithilfe des Aufrufs CNAM variiert je nach Land und Netzbetreibern, die den Anruf entweder als Mittler behandeln und/oder einen Abbruch Netzbetreiber.</span><span class="sxs-lookup"><span data-stu-id="c5a93-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="c5a93-110">CLID & CNAM Übertragung ist der Verantwortung der Abbruch Netzbetreiber, soweit der Abbruch Netzbetreiber unterstützen CLID & CNAM Funktionen als auch muss auf dem aktuellen Stand Datensätze für beide Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="c5a93-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="c5a93-111">Microsoft bietet zuverlässig CLID-Werte bei Anrufen, aber diese Werte möglicherweise nicht werden beibehalten, wenn sie über eine zwischengeschaltete Netzbetreiber oder der Abbruch Netzbetreiber übergeben.</span><span class="sxs-lookup"><span data-stu-id="c5a93-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="c5a93-112">In der Ereignisprozedur der Wert CLID geändert, ausgelassen oder, indem der Netzbetreiber zwischengeschaltete oder Abbruch gekürzt, hat Microsoft leider wenig Hintergrundgeräuschen Anspruch in die Behebung solcher Probleme in das öffentliche Telefonnetz.</span><span class="sxs-lookup"><span data-stu-id="c5a93-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="c5a93-113">Inkonsistenzen in CNAM können durch Verzögerungen bei der anspruchsvolleren oder Abbruch Netzbetreibern aktualisieren CNAM Info in autorisierende Datenbanken wie in den USA die Groß-/Kleinschreibung verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="c5a93-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="c5a93-114">In Ländern, in denen keine autorisierende Datenbank für CNAM vorhanden ist, einzelne Netzbetreiber Methoden können auch Probleme mit CNAM Informationen in intakt mit den Anruf eingeht.</span><span class="sxs-lookup"><span data-stu-id="c5a93-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="c5a93-115">Microsoft unterstützt derzeit ursprünglichen CNAM Informationen in Länder außer den USA nicht."</span><span class="sxs-lookup"><span data-stu-id="c5a93-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="c5a93-116">See Also</span><span class="sxs-lookup"><span data-stu-id="c5a93-116">Related topics</span></span>


