---
title: Migrationsvorgang
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Das empfohlene und unterstützte Migrationsverfahren für Skype für Business Server 2019 ist Side-by-Side-Migration. In diesem Thema wird beschrieben, warum Sie sollten Side-by-Side-Migration und enthält außerdem Informationen zum Testen der Koexistenz.
ms.openlocfilehash: e14226721cbc09bd1f0ac66b47dbd1710712eb17
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231616"
---
# <a name="migration-process"></a>Migrationsvorgang

Das empfohlene und unterstützte Migrationsverfahren für Skype für Business Server 2019 ist Side-by-Side-Migration. In diesem Thema wird beschrieben, warum Sie sollten Side-by-Side-Migration und enthält außerdem Informationen zum Testen der Koexistenz.
  
## <a name="side-by-side-migration"></a>Side-By-Side-Migration

In fast jeder Migration sollten Sie den Side-by-Side Migrationspfad verwenden. Bei der Migration Side-by-Side Bereitstellen eines neues Servers mit Skype für Business Server 2019 zusammen mit einem entsprechenden Server, der eine frühere Version ausgeführt wird, und klicken Sie dann auf den neuen Server übertragen Vorgänge. Wenn es erforderlich sind, um einen Rollback auf die vorherige Version wird, müssen Sie nur Vorgänge wieder auf die ursprünglichen Server verschoben. Beachten Sie, dass alle neuen Besprechungen, die mit aktualisierten Clients ist in dieser Situation nicht funktionsfähig, und die Clients auch Downgrade werden muss.
  
## <a name="coexistence-testing"></a>Koexistenztest

Nachdem Sie Skype für Business Server 2019 parallel mit der vorherigen Version bereitgestellt haben, stellt die Bereitstellung einer Koexistenz Zustand des Skype für Business Server 2019 und die vorherige Version testen. Klicken Sie in diesem Status ist es wichtig zu testen, und stellen Sie sicher, dass die Dienste gestartet sind, kann jeder Standort verwaltet werden und können mit Benutzern von aktuellen und ältere Clients kommunizieren. Vor der Migration aller Benutzer ist es sehr wichtig, dass Sie den Status der einzelnen Bereitstellungen verstehen, und stellen Sie sicher, dass jede Bereitstellung funktionsfähig und betriebsbereit ist. In der Regel ist die Koexistenz Testphase in der gesamten der Pilottests für Skype für Business Server 2019 vorhanden. Bestehende Benutzer werden verschoben und Skype für Business Server 2019 für eine bestimmte Zeitspanne um sicherzustellen, dass diese Anwendungskompatibilität und Features und Funktionen arbeiten ordnungsgemäß. Nach der Pilottests, Benutzer und Anwendungen auf die Version von Skype für Business Server 2019 und die alten Pools verschoben werden, und Anwendungen der vorherigen Version veraltet sind.
  
