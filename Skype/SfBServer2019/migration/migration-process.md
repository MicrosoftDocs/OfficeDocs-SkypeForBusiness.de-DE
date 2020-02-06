---
title: Migrationsvorgang
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist eine parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten, und Sie enthält auch Informationen zum Testen der Koexistenz.
ms.openlocfilehash: 7d8ce6513535871939894092850ad0526b1b6a63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813413"
---
# <a name="migration-process"></a>Migrationsvorgang

Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist eine parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten, und Sie enthält auch Informationen zum Testen der Koexistenz.
  
## <a name="side-by-side-migration"></a>Parallele Migration

In fast jeder Migration sollten Sie den parallelen Migrationspfad verwenden. Bei einer parallelen Migration stellen Sie einen neuen Server mit Skype for Business Server 2019 neben einem entsprechenden Server bereit, auf dem eine vorherige Version ausgeführt wird, und übertragen dann Vorgänge auf den neuen Server. Wenn es erforderlich ist, auf die vorherige Version zurückzusetzen, müssen Sie die Vorgänge nur zurück zu den ursprünglichen Servern verschieben. Beachten Sie, dass in dieser Situation alle neuen Besprechungen, die mit aktualisierten Clients geplant sind, nicht funktionieren, und die Clients müssten ebenfalls heruntergestuft werden.
  
## <a name="coexistence-testing"></a>Koexistenz testen

Nachdem Sie Skype for Business Server 2019 parallel zur vorherigen Version bereitgestellt haben, stellt die Bereitstellung einen Teststatus für Koexistenz von Skype for Business Server 2019 und der vorherigen Version dar. In diesem Zustand ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden, jeder Standort verwaltet werden kann und Clients mit aktuellen und älteren Benutzern kommunizieren können. Vor der Migration aller Benutzer ist es sehr wichtig, dass Sie den Zustand jeder Bereitstellung verstehen und sicherstellen, dass jede Bereitstellung funktionsfähig ist und ordnungsgemäß funktioniert. In der Regel gibt es während des Testversuchs von Skype for Business Server 2019 die Koexistenz-Testphase. Ältere Benutzer werden für einen bestimmten Zeitraum in Skype for Business Server 2019 verschoben, um sicherzustellen, dass die Anwendungskompatibilität und die Features und Funktionen ordnungsgemäß funktionieren. Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von Skype for Business Server 2019 verschoben, und die Legacy Pools und-Anwendungen der vorherigen Version werden eingestellt.
  
