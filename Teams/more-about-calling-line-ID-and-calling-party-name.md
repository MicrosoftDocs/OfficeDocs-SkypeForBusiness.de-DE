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
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Mehr über Telefonnummer-ID und Name des Anrufers

Die Rufnummernanzeige, wie Sie in der Regel genannt wird, besteht tatsächlich aus zwei identifizierbaren Informationen:
    - Eine Telefonnummer (in der Regel als gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx oder Anruf Leitungskennung bezeichnet) 
    - Name des anrufenden Teilnehmers (in der Regel als CNAM bezeichnet), der bis zu 15 Zeichen lang sein kann. 

Wenn ein Anruf durchgeführt wird, wird die gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx (Telefonnummer) an den Netzbetreiber des Ziels weitergeleitet (auch als Terminierungs Unternehmen bezeichnet). Die CNAM-Informationen für den Anruf werden möglicherweise mit dem Anruf weitergeleitet, da dies davon abhängt, wie das Land CNAM implementiert hat (wenn überhaupt). Die Zuverlässigkeit der CNAM-Zustellung mit dem Anruf variiert je nach Land und Netzbetreibern, die den Anruf entweder als Vermittler und/oder als abschließender Beförderer abwickeln. 

Gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx & CNAM-Übertragung liegt in der Verantwortung des abschließenden Netzbetreibers, sofern der abschließende Netzbetreiber gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx & CNAM-Funktionalität unterstützen und für beide Werte aktuelle Datensätze bereitstellen muss. Microsoft stellt beim Aufrufen von Anrufen zuverlässige gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx-Werte bereit, diese Werte werden aber möglicherweise nicht intakt gehalten, wenn Sie einen Vermittler oder den abschließenden Netzbetreiber durchlaufen. Im Fall, dass der gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx-Wert vom zwischengeschalteten oder abschließenden Netzbetreiber geändert, ausgelassen oder gekürzt wird, hat Microsoft bei der Behebung derartiger Probleme im öffentlichen Telefonnetz wenig bis gar keinen Rückgriff.

Inkonsistenzen in CNAM können durch Verzögerungen bei zwischen-oder endnetzern verursacht werden, die CNAM-Informationen in autorisierenden Datenbanken aktualisieren, wie dies in den Vereinigten Staaten der Fall ist. In Ländern, in denen es keine autorisierende Datenbank für CNAM gibt, können einzelne Carrier-Methoden auch Probleme mit CNAM-Informationen verursachen, die mit dem Anruf intakt sind. Microsoft unterstützt derzeit keine Ursprungs CNAM-Informationen in anderen Ländern als den Vereinigten Staaten. "

## <a name="related-topics"></a>Verwandte Themen


