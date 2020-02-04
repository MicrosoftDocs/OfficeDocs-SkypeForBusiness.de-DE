---
title: Mehr über Telefonnummer-ID und Name des Anrufers
ms.author: tonysmit
author: tonysmit
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
- NOCSH
ms.custom:
- Calling Plans
description: Erfahren Sie, warum Sie eine autorisierte Person hinzufügen müssen, die Änderungen am Konto vornehmen kann, wenn Sie den Assistenten für neue lokale Nummern Port Reihenfolge verwenden.
ms.openlocfilehash: a687bc1aca8a47b349415d4a0cc2dc9f61f81884
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708801"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="f89b3-103">Mehr über Telefonnummer-ID und Name des Anrufers</span><span class="sxs-lookup"><span data-stu-id="f89b3-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="f89b3-104">Die Rufnummernanzeige, wie Sie in der Regel genannt wird, besteht tatsächlich aus zwei identifizierbaren Informationen:</span><span class="sxs-lookup"><span data-stu-id="f89b3-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="f89b3-105">Eine Telefonnummer (in der Regel als gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx oder Anruf Leitungskennung bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="f89b3-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="f89b3-106">Name des anrufenden Teilnehmers (in der Regel als CNAM bezeichnet), der bis zu 15 Zeichen lang sein kann.</span><span class="sxs-lookup"><span data-stu-id="f89b3-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="f89b3-107">Wenn ein Anruf durchgeführt wird, wird die gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx (Telefonnummer) an den Netzbetreiber des Ziels weitergeleitet (auch als Terminierungs Unternehmen bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="f89b3-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="f89b3-108">Die CNAM-Informationen für den Anruf werden möglicherweise mit dem Anruf weitergeleitet, da dies davon abhängt, wie das Land CNAM implementiert hat (wenn überhaupt).</span><span class="sxs-lookup"><span data-stu-id="f89b3-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="f89b3-109">Die Zuverlässigkeit der CNAM-Zustellung mit dem Anruf variiert je nach Land und Netzbetreibern, die den Anruf entweder als Vermittler und/oder als abschließender Beförderer abwickeln.</span><span class="sxs-lookup"><span data-stu-id="f89b3-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="f89b3-110">Gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx #a0 CNAM-Übertragung liegt in der Verantwortung des abschließenden Netzbetreibers, sofern der abschließende Netzbetreiber gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx #a1 CNAM-Funktionalität unterstützen und für beide Werte aktuelle Datensätze bereitstellen muss.</span><span class="sxs-lookup"><span data-stu-id="f89b3-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="f89b3-111">Microsoft stellt beim Aufrufen von Anrufen zuverlässige gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx-Werte bereit, diese Werte werden aber möglicherweise nicht intakt gehalten, wenn Sie einen Vermittler oder den abschließenden Netzbetreiber durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="f89b3-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="f89b3-112">Im Fall, dass der gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx-Wert vom zwischengeschalteten oder abschließenden Netzbetreiber geändert, ausgelassen oder gekürzt wird, hat Microsoft bei der Behebung derartiger Probleme im öffentlichen Telefonnetz wenig bis gar keinen Rückgriff.</span><span class="sxs-lookup"><span data-stu-id="f89b3-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="f89b3-113">Inkonsistenzen in CNAM können durch Verzögerungen bei zwischen-oder endnetzern verursacht werden, die CNAM-Informationen in autorisierenden Datenbanken aktualisieren, wie dies in den Vereinigten Staaten der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="f89b3-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="f89b3-114">In Ländern, in denen es keine autorisierende Datenbank für CNAM gibt, können einzelne Carrier-Praktiken auch Probleme mit CNAM-Informationen verursachen, die mit dem Anruf intakt sind.</span><span class="sxs-lookup"><span data-stu-id="f89b3-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="f89b3-115">Microsoft unterstützt derzeit keine Ursprungs CNAM-Informationen in anderen Ländern als den Vereinigten Staaten. "</span><span class="sxs-lookup"><span data-stu-id="f89b3-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="f89b3-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f89b3-116">Related topics</span></span>


