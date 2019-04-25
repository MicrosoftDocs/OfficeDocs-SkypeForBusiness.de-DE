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
ms.openlocfilehash: 846abfd5b6973a02ad1a7388b45a79ec709695a0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229867"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Mehr über Telefonnummer-ID und Name des Anrufers

CallerID, wie er in der Regel, bezeichnet wird besteht aus zwei Benutzern wahrgenommenen identifizierbare Teile der Informationen:
    - Eine Telefonnummer ein (normalerweise um als CLID oder Aufruf von Zeile ID bezeichnet) 
    - Aufrufen von Namen ein (normalerweise als CNAM bezeichnet), der bis zu 15 Zeichen lang sein kann. 

Wenn ein Aufruf ausgeführt wird, wird die CLID (Telefonnummer) an das Ziel des Netzbetreibers (auch bekannt als der Abbruch Netzbetreiber) weitergeleitet. Die CNAM-Informationen für den Anruf kann oder kann nicht mit der Anruf weitergeleitet werden, wie dies hängt wie das Land CNAM (falls überhaupt) implementiert hat. Die Zuverlässigkeit der Lieferung mithilfe des Aufrufs CNAM variiert je nach Land und Netzbetreibern, die den Anruf entweder als Mittler behandeln und/oder einen Abbruch Netzbetreiber. 

CLID & CNAM Übertragung ist der Verantwortung der Abbruch Netzbetreiber, soweit der Abbruch Netzbetreiber unterstützen CLID & CNAM Funktionen als auch muss auf dem aktuellen Stand Datensätze für beide Werte enthalten. Microsoft bietet zuverlässig CLID-Werte bei Anrufen, aber diese Werte möglicherweise nicht werden beibehalten, wenn sie über eine zwischengeschaltete Netzbetreiber oder der Abbruch Netzbetreiber übergeben. In der Ereignisprozedur der Wert CLID geändert, ausgelassen oder, indem der Netzbetreiber zwischengeschaltete oder Abbruch gekürzt, hat Microsoft leider wenig Hintergrundgeräuschen Anspruch in die Behebung solcher Probleme in das öffentliche Telefonnetz.

Inkonsistenzen in CNAM können durch Verzögerungen bei der anspruchsvolleren oder Abbruch Netzbetreibern aktualisieren CNAM Info in autorisierende Datenbanken wie in den USA die Groß-/Kleinschreibung verursacht werden. In Ländern, in denen keine autorisierende Datenbank für CNAM vorhanden ist, einzelne Netzbetreiber Methoden können auch Probleme mit CNAM Informationen in intakt mit den Anruf eingeht. Microsoft unterstützt derzeit ursprünglichen CNAM Informationen in Länder außer den USA nicht."

## <a name="related-topics"></a>Verwandte Themen


