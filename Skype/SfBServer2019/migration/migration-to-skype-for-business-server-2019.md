---
title: Migration zu Skype for Business Server 2019
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
description: Die Themen in diesem Abschnitt führen Sie durch den Prozess der Migration zu Skype for Business Server 2019.
ms.openlocfilehash: 51c3be10b90198e1abe24172aa35ab167e871739
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813403"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migration zu Skype for Business Server 2019

Die Themen in diesem Abschnitt führen Sie durch den Prozess der Migration zu Skype for Business Server 2019. Dieser Artikel behandelt die Migration von lync Server 2013 oder Skype for Business Server 2015 zu Skype for Business Server 2019.

> [!IMPORTANT]
> Im gesamten Inhalt verwenden wir den Begriff *Legacy* , um auf den Legacy-lync Server 2013 oder Skype for Business Server 2015 zu verweisen, den Sie zu Skype for Business Server 2019 migrieren.
  
> [!IMPORTANT]
> In diesem Leitfaden werden die Schritte beschrieben, die in der Regel für die einzelnen Migrationsphasen erforderlich sind. Sie bezieht sich nicht auf jede mögliche Legacy Bereitstellungstopologie oder alle möglichen Migrationsszenarien. Daher müssen Sie möglicherweise nicht alle beschriebenen Schritte ausführen, oder Sie müssen abhängig von Ihrer Bereitstellung möglicherweise zusätzliche Schritte ausführen. Dieses Handbuch enthält auch Beispiele für Überprüfungsschritte. Diese Überprüfungsschritte werden bereitgestellt, um Ihnen zu verdeutlichen, was Sie suchen müssen, um sicherzustellen, dass jede Phase erfolgreich abgeschlossen wird, während Sie Ihre Migration fortführen. Passen Sie diese Überprüfungsschritte an den jeweiligen Migrationsprozess an. 
  
Dieses Handbuch enthält Informationen, die speziell für das Upgrade Ihrer vorhandenen Bereitstellung gelten. Es wird nicht erläutert, wie Sie Ihre vorhandene Topologie ändern. In diesem Leitfaden wird die Implementierung neuer Features nicht behandelt. Wenn eine detaillierte Prozedur an anderer Stelle dokumentiert wird, werden Sie in diesem Leitfaden zum Artikel-oder Artikel Abschnitt weitergeleitet. 
  
In diesem Artikel werden die in der folgenden Liste angegebenen Ausdrücke definiert.
  
**Migration:** Verschieben der Produktionsbereitstellung von lync Server 2013 oder Skype for Business Server 2015 auf Skype for Business Server 2019.
    
**Koexistenz:** Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen in Skype for Business Server 2019 migriert wurden und andere Funktionen weiterhin auf einer früheren Version verbleiben.
    
**Interoperabilität:** Die Möglichkeit, dass Ihre Bereitstellung während des Zeitraums der Koexistenz erfolgreich ausgeführt werden kann.

**Legacy:** Das System, von dem Sie die Migration fortführen, also entweder lync Server 2013 oder Skype for Business Server 2015.
    
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Vorbereiten der Migration](before-you-begin-the-migration.md)
    
- [Phase 1: Planen der Migration](phase-1-plan-your-migration.md)
    
- [Phase 2: Vorbereitung der Migration](phase-2-prepare-for-migration.md)
    
- [Phase 3: Bereitstellen des Pilotpools](phase-3-deploy-pilot-pool.md)
    
- [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Phase 5: Hinzufügen von Edgeservern zum Pilotpool](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Phase 7: Aufgaben nach der Migration abschließen](phase-7-complete-post-migration-tasks.md)
    
- [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md)
    

