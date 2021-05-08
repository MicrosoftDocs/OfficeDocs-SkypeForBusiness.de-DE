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
description: Erfahren Sie, warum Sie eine autorisierte Person hinzufügen müssen, die Änderungen am Konto vornehmen kann, wenn Sie den Assistenten Portierungsauftrag für neue lokale Rufnummer verwenden.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255398"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Mehr über Telefonnummer-ID und Name des Anrufers

Die Anrufer-ID (callerID), auf die normalerweise Verwiesen wird, besteht tatsächlich aus zwei benutzeridentifizierbaren Informationen:
    - Eine Telefonnummer (in der Regel als RUFNUMMER oder Anrufleitungs-ID bezeichnet) 
    - Der Name der Anrufepart (normalerweise als CNAM bezeichnet) kann bis zu 15 Zeichen lang sein. 

Wenn ein Anruf erfolgt, wird die RUFNUMMER (Telefonnummer) an den Netzbetreiber des Ziels (auch als Endanbieter bekannt) geroutet. Die CNAM-Informationen für den Anruf werden möglicherweise mit dem Anruf geroutet oder nicht, da dies davon abhängt, wie das Land CNAM implementiert hat (sofern überhaupt). Die Zuverlässigkeit der CNAM-Zustellung mit dem Anruf variiert je nach Land und Netzbetreiber, die den Anruf entweder als Zwischenanbieter und/oder als endenden Netzbetreiber behandeln. 

CLID & CNAM-Übertragung liegt in der Verantwortung des endenden Netzbetreibers, da der endende Netzbetreiber die CNAM-Funktionen von CLID & unterstützen und für beide Werte aktuelle Datensätze bereitstellen muss. Microsoft stellt bei Anrufen zuverlässig CLID-Werte zur Verfügung, die jedoch möglicherweise nicht beibehalten werden, sobald sie über einen zwischengeschalteten Netzbetreiber oder endenden Netzbetreiber übergeben werden. Unglücklicherweise hat Microsoft wenig bis gar keine Zeit, solche Probleme im öffentlichen Telefonnetz zu beheben, wenn der RUFNUMMERN-Wert vom zwischengeschalteten oder endenden Netzbetreiber geändert, weggelassen oder abgeschnitten wird.

Inkonsistenzen in CNAM können durch Verzögerungen bei zwischen oder endenden Netzbetreibern verursacht werden, die CNAM-Informationen in autoritativen Datenbanken aktualisieren, wie dies für die VEREINIGTEN Staaten der Fall ist. In Ländern, in denen es keine autoritative Datenbank für CNAM gibt, können einzelne Methoden des Netzbetreibers ebenfalls Probleme verursachen, wenn CNAM-Informationen mit dem Anruf intakt werden. Microsoft unterstützt zurzeit keine CNAM-Informationen aus anderen Ländern als den USA."

## <a name="related-topics"></a>Verwandte Themen


