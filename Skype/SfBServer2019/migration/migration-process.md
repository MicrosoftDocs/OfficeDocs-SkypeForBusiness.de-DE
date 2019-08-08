---
title: Migrationsvorgang
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist eine parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten, und Sie enthält auch Informationen zum Testen der Koexistenz.
ms.openlocfilehash: 6ef8a70aa436663b7ff88723800375eeef620b6d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237779"
---
# <a name="migration-process"></a>Migrationsvorgang

Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist eine parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten, und Sie enthält auch Informationen zum Testen der Koexistenz.
  
## <a name="side-by-side-migration"></a>Parallele Migration

In fast jeder Migration sollten Sie den parallelen Migrationspfad verwenden. Bei einer parallelen Migration stellen Sie einen neuen Server mit Skype for Business Server 2019 neben einem entsprechenden Server bereit, auf dem eine vorherige Version ausgeführt wird, und übertragen dann Vorgänge auf den neuen Server. Wenn es erforderlich ist, auf die vorherige Version zurückzusetzen, müssen Sie die Vorgänge nur zurück zu den ursprünglichen Servern verschieben. Beachten Sie, dass in dieser Situation alle neuen Besprechungen, die mit aktualisierten Clients geplant sind, nicht funktionieren, und die Clients müssten ebenfalls heruntergestuft werden.
  
## <a name="coexistence-testing"></a>Koexistenz testen

Nachdem Sie Skype for Business Server 2019 parallel zur vorherigen Version bereitgestellt haben, stellt die Bereitstellung einen Teststatus für Koexistenz von Skype for Business Server 2019 und der vorherigen Version dar. In diesem Zustand ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden, jeder Standort verwaltet werden kann und Clients mit aktuellen und älteren Benutzern kommunizieren können. Vor der Migration aller Benutzer ist es sehr wichtig, dass Sie den Zustand jeder Bereitstellung verstehen und sicherstellen, dass jede Bereitstellung funktionsfähig ist und ordnungsgemäß funktioniert. In der Regel gibt es während des Testversuchs von Skype for Business Server 2019 die Koexistenz-Testphase. Ältere Benutzer werden für einen bestimmten Zeitraum in Skype for Business Server 2019 verschoben, um sicherzustellen, dass die Anwendungskompatibilität und die Features und Funktionen ordnungsgemäß funktionieren. Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von Skype for Business Server 2019 verschoben, und die Legacy Pools und-Anwendungen der vorherigen Version werden eingestellt.
  
