---
title: Migrationsvorgang
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten, und es enthält auch Informationen zu Koexistenztests.
ms.openlocfilehash: 4ca0e8d1362c05e87c4ec347115f7e45457c55d1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613390"
---
# <a name="migration-process"></a>Migrationsvorgang

Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten, und es enthält auch Informationen zu Koexistenztests.
  
## <a name="side-by-side-migration"></a>Parallele Migration

Am besten wenden Sie für jede Migration das Verfahren der parallelen Migration an. Bei einer parallelen Migration stellen Sie einen neuen Server mit Skype for Business Server 2019 zusammen mit einem entsprechenden Server bereit, auf dem eine frühere Version ausgeführt wird, und übertragen dann Vorgänge auf den neuen Server. Wenn ein Rollback auf die vorherige Version erforderlich ist, müssen Sie die Vorgänge nur wieder auf die ursprünglichen Server umschalten. Bedenken Sie, dass in diesem Fall neue Besprechungen, die mit aktualisierten Clients geplant wurden, nicht funktionieren und dass auch für die Clients ein Downgrade erforderlich wäre.
  
## <a name="coexistence-testing"></a>Koexistenztest

Nachdem Sie Skype for Business Server 2019 parallel zur vorherigen Version bereitgestellt haben, stellt die Bereitstellung einen Koexistenzteststatus von Skype for Business Server 2019 und der vorherigen Version dar. In diesem Status ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden können, jeder Standort verwalten werden kann und die Clients mit Benutzern der aktuellen und der Vorgängerversion kommunizieren können. Vor dem Migrieren aller Benutzer sollten Sie unbedingt den Status jeder Bereitstellung festgestellt und sich vergewissert haben, dass jede Bereitstellung ordnungsgemäß funktioniert. In der Regel besteht die Koexistenztestphase während der Pilottests von Skype for Business Server 2019. Ältere Benutzer werden für einen bestimmten Zeitraum zu Skype for Business Server 2019 verschoben, um sicherzustellen, dass die Anwendungskompatibilität sowie Features und Funktionen ordnungsgemäß funktionieren. Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von Skype for Business Server 2019 verschoben, und die älteren Pools und Anwendungen der vorherigen Version werden eingestellt.
  
