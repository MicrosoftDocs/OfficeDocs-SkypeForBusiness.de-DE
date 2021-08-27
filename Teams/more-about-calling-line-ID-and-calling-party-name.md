---
title: Mehr über Telefonnummer-ID und Name des Anrufers
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: Weitere Informationen finden Sie unter Anrufleitungs-ID und Anrufername.
ms.openlocfilehash: 13167e41a5e104e198c557af90ed121e90abcf55
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617241"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Mehr über Telefonnummer-ID und Name des Anrufers

CallerID besteht aus zwei Informationen, die dem Benutzer angezeigt werden:

- Eine Telefonnummer (in der Regel als RUFNUMMER oder Anrufleitungs-ID bezeichnet).

- Name der Anrufer (üblicherweise auch als "CNAM" bezeichnet). 

Wenn ein Anruf erfolgt, wird die RUFNUMMER (Telefonnummer) an den Netzbetreiber des Ziels (auch als Endanbieter bekannt) geroutet. Die CNAM-Informationen für den Anruf können mit dem Anruf geroutet werden oder nicht, da diese Informationen davon abhängig sind, wie CNAM (falls überhaupt) im Land implementiert wurde. Die Zuverlässigkeit der CNAM-Übermittlung mit dem Anruf variiert je nach Land und Netzbetreiber, die den Anruf verarbeiten – entweder als Zwischenanbieter oder als endendes Netzbetreiber. 

CLID & CNAM-Übertragung liegt in der Verantwortung des beendenden Netzbetreibers. Der endende Netzbetreiber muss die CNAM& CLID-Funktionen unterstützen und aktuelle Datensätze für beide Werte bereitstellen. Microsoft stellt bei Anrufen zuverlässig CLID-Werte zur Verfügung, die jedoch möglicherweise nicht beibehalten werden, sobald sie über einen zwischengeschalteten Netzbetreiber oder endenden Netzbetreiber übergeben werden. Wenn der CLID-Wert vom zwischengeschalteten oder beendenden Netzbetreiber geändert, weggelassen oder abgeschnitten wird, hat Microsoft nur wenige bis gar keine Möglichkeit, solche Probleme im öffentlichen Telefonnetz zu beheben.

Inkonsistenzen in CNAM können verursacht werden, wenn die mittleren oder endenden Netzbetreiber die Aktualisierung der CNAM-Informationen in autoritativen Datenbanken verzögern , wie dies für die VEREINIGTEN Staaten der Fall ist. In Ländern, in denen es keine autoritativen Datenbanken für CNAM gibt, können einzelne Methoden des Netzbetreibers ebenfalls Probleme verursachen, wenn CNAM-Informationen mit dem Anruf intakt werden. Microsoft unterstützt zurzeit keine CNAM-Informationen aus anderen Ländern als den USA.

## <a name="related-topics"></a>Verwandte Themen


