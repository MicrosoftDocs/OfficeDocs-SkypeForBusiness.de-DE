---
title: Migrationsprozess
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist eine parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten und auch Informationen zum Testen der Koexistenz enthält.
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752637"
---
# <a name="migration-process"></a>Migrationsprozess

Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist eine parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten und auch Informationen zum Testen der Koexistenz enthält.
  
## <a name="side-by-side-migration"></a>Parallele Migration

Am besten wenden Sie für jede Migration das Verfahren der parallelen Migration an. Bei einer parallelen Migration stellen Sie einen neuen Server mit Skype for Business Server 2019 neben einem entsprechenden Server bereit, auf dem eine frühere Version ausgeführt wird, und dann Vorgänge auf den neuen Server übertragen. Wenn ein Rollback auf die vorherige Version erforderlich ist, müssen Sie die Vorgänge nur wieder auf die ursprünglichen Server verschieben. Bedenken Sie, dass in diesem Fall neue Besprechungen, die mit aktualisierten Clients geplant wurden, nicht funktionieren und dass auch für die Clients ein Downgrade erforderlich wäre.
  
## <a name="coexistence-testing"></a>Koexistenztest

Nachdem Sie Skype for Business Server 2019 parallel zur vorherigen Version bereitgestellt haben, stellt die Bereitstellung den Status Test der Koexistenz von Skype for Business Server 2019 und der vorherigen Version dar. In diesem Status ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden können, jeder Standort verwalten werden kann und die Clients mit Benutzern der aktuellen und der Vorgängerversion kommunizieren können. Vor dem Migrieren aller Benutzer sollten Sie unbedingt den Status jeder Bereitstellung festgestellt und sich vergewissert haben, dass jede Bereitstellung ordnungsgemäß funktioniert. In der Regel besteht die Testphase der Koexistenz während der Pilottests von Skype for Business Server 2019. Ältere Benutzer werden für einen bestimmten Zeitraum auf Skype for Business Server 2019 verschoben, um sicherzustellen, dass die Anwendungskompatibilität und die Funktionen und Funktionen ordnungsgemäß funktionieren. Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von Skype for Business Server 2019 verschoben, und die älteren Pools und Anwendungen der vorherigen Version werden zurückgezogen.
  
