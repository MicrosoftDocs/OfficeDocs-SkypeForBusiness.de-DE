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
description: Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten, und es enthält auch Informationen zu Koexistenztests.
ms.openlocfilehash: e1d89dc2081918d87f73cd3c6908fff0c388e6700d00af6dcd72161a2ccc9ece
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303409"
---
# <a name="migration-process"></a>Migrationsprozess

Das empfohlene und unterstützte Migrationsverfahren für Skype for Business Server 2019 ist parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten, und es enthält auch Informationen zu Koexistenztests.
  
## <a name="side-by-side-migration"></a>Parallele Migration

Am besten wenden Sie für jede Migration das Verfahren der parallelen Migration an. Bei einer parallelen Migration stellen Sie einen neuen Server mit Skype for Business Server 2019 zusammen mit einem entsprechenden Server bereit, auf dem eine frühere Version ausgeführt wird, und übertragen dann Vorgänge auf den neuen Server. Wenn ein Rollback auf die vorherige Version erforderlich ist, müssen Sie die Vorgänge nur wieder auf die ursprünglichen Server umschalten. Bedenken Sie, dass in diesem Fall neue Besprechungen, die mit aktualisierten Clients geplant wurden, nicht funktionieren und dass auch für die Clients ein Downgrade erforderlich wäre.
  
## <a name="coexistence-testing"></a>Koexistenztest

Nachdem Sie Skype for Business Server 2019 parallel zur vorherigen Version bereitgestellt haben, stellt die Bereitstellung einen Koexistenzteststatus von Skype for Business Server 2019 und der vorherigen Version dar. In diesem Status ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden können, jeder Standort verwalten werden kann und die Clients mit Benutzern der aktuellen und der Vorgängerversion kommunizieren können. Vor dem Migrieren aller Benutzer sollten Sie unbedingt den Status jeder Bereitstellung festgestellt und sich vergewissert haben, dass jede Bereitstellung ordnungsgemäß funktioniert. In der Regel besteht die Koexistenztestphase während der Pilottests von Skype for Business Server 2019. Ältere Benutzer werden für einen bestimmten Zeitraum zu Skype for Business Server 2019 verschoben, um sicherzustellen, dass die Anwendungskompatibilität sowie Features und Funktionen ordnungsgemäß funktionieren. Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von Skype for Business Server 2019 verschoben, und die älteren Pools und Anwendungen der vorherigen Version werden eingestellt.
  
