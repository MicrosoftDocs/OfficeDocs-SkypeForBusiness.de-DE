---
title: Mehr über Telefonnummer-ID und Name des Anrufers
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Erfahren Sie, warum Sie eine autorisierte Person hinzufügen müssen, die Änderungen am Konto vornehmen kann, wenn Sie den Assistenten für neue lokale Nummern Port Reihenfolge verwenden.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255398"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="57000-103">Mehr über Telefonnummer-ID und Name des Anrufers</span><span class="sxs-lookup"><span data-stu-id="57000-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="57000-104">Die Rufnummernanzeige, wie Sie in der Regel genannt wird, besteht tatsächlich aus zwei identifizierbaren Informationen:</span><span class="sxs-lookup"><span data-stu-id="57000-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="57000-105">Eine Telefonnummer (in der Regel als gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx oder Anruf Leitungskennung bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="57000-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="57000-106">Name des anrufenden Teilnehmers (in der Regel als CNAM bezeichnet), der bis zu 15 Zeichen lang sein kann.</span><span class="sxs-lookup"><span data-stu-id="57000-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="57000-107">Wenn ein Anruf durchgeführt wird, wird die gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx (Telefonnummer) an den Netzbetreiber des Ziels weitergeleitet (auch als Terminierungs Unternehmen bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="57000-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="57000-108">Die CNAM-Informationen für den Anruf werden möglicherweise mit dem Anruf weitergeleitet, da dies davon abhängt, wie das Land CNAM implementiert hat (wenn überhaupt).</span><span class="sxs-lookup"><span data-stu-id="57000-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="57000-109">Die Zuverlässigkeit der CNAM-Zustellung mit dem Anruf variiert je nach Land und Netzbetreibern, die den Anruf entweder als Vermittler und/oder als abschließender Beförderer abwickeln.</span><span class="sxs-lookup"><span data-stu-id="57000-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="57000-110">Gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx & CNAM-Übertragung liegt in der Verantwortung des abschließenden Netzbetreibers, sofern der abschließende Netzbetreiber gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx & CNAM-Funktionalität unterstützen und für beide Werte aktuelle Datensätze bereitstellen muss.</span><span class="sxs-lookup"><span data-stu-id="57000-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="57000-111">Microsoft stellt beim Aufrufen von Anrufen zuverlässige gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx-Werte bereit, diese Werte werden aber möglicherweise nicht intakt gehalten, wenn Sie einen Vermittler oder den abschließenden Netzbetreiber durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="57000-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="57000-112">Im Fall, dass der gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx-Wert vom zwischengeschalteten oder abschließenden Netzbetreiber geändert, ausgelassen oder gekürzt wird, hat Microsoft bei der Behebung derartiger Probleme im öffentlichen Telefonnetz wenig bis gar keinen Rückgriff.</span><span class="sxs-lookup"><span data-stu-id="57000-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="57000-113">Inkonsistenzen in CNAM können durch Verzögerungen bei zwischen-oder endnetzern verursacht werden, die CNAM-Informationen in autorisierenden Datenbanken aktualisieren, wie dies in den Vereinigten Staaten der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="57000-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="57000-114">In Ländern, in denen es keine autorisierende Datenbank für CNAM gibt, können einzelne Carrier-Methoden auch Probleme mit CNAM-Informationen verursachen, die mit dem Anruf intakt sind.</span><span class="sxs-lookup"><span data-stu-id="57000-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="57000-115">Microsoft unterstützt derzeit keine Ursprungs CNAM-Informationen in anderen Ländern als den Vereinigten Staaten. "</span><span class="sxs-lookup"><span data-stu-id="57000-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="57000-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="57000-116">Related topics</span></span>


