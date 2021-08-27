---
title: Migration zu Skype for Business Server 2019
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
description: Die Themen in diesem Abschnitt führen Sie durch den Prozess der Migration zu Skype for Business Server 2019.
ms.openlocfilehash: 6eb192c11ec8d1f44539e3bd5180249d85180d2b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587977"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migration zu Skype for Business Server 2019

Die Themen in diesem Abschnitt führen Sie durch den Prozess der Migration zu Skype for Business Server 2019. Dieser Artikel behandelt die Migration von Lync Server 2013 oder Skype for Business Server 2015 zu Skype for Business Server 2019.

> [!IMPORTANT]
> Im gesamten Inhalt wird der Begriff *Legacy* verwendet, um auf die ältere Lync Server 2013 oder Skype for Business Server 2015 zu verweisen, die Sie zu Skype for Business Server 2019 migrieren.
  
> [!IMPORTANT]
> In diesem Leitfaden werden die Schritte beschrieben, die im Allgemeinen erforderlich sind, um die einzelnen Migrationsphasen auszuführen. Sie behandelt nicht jede mögliche Legacybereitstellungstopologie oder jedes mögliche Migrationsszenario. Daher müssen Sie möglicherweise nicht jeden beschriebenen Schritt ausführen oder je nach Bereitstellung zusätzliche Schritte ausführen. Dieses Handbuch enthält auch Beispiele für Überprüfungsschritte. Diese Überprüfungsschritte helfen Ihnen zu verstehen, wonach Sie suchen müssen, um sicherzustellen, dass jede Phase während der Migration erfolgreich abgeschlossen wird. Passen Sie diese Überprüfungsschritte an Ihren spezifischen Migrationsprozess an. 
  
Dieses Handbuch enthält Informationen, die speziell auf die Aktualisierung Ihrer vorhandenen Bereitstellung eingehen. Die Änderung Ihrer vorhandenen Topologie wird darin nicht behandelt. In diesem Handbuch wird nicht die Implementierung neuer Funktionen behandelt. Wenn ein detailliertes Verfahren an anderer Stelle dokumentiert ist, führt Sie dieses Handbuch zum Artikel- oder Artikelabschnitt. 
  
In diesem Artikel werden Ausdrücke definiert, die in der folgenden Liste angegeben sind.
  
**Migration:** Verschieben Der Produktionsbereitstellung von Lync Server 2013 oder Skype for Business Server 2015 auf Skype for Business Server 2019.
    
**Koexistenz:** Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu Skype for Business Server 2019 migriert wurden, und andere Funktionen bleiben auf einer früheren Version.
    
**Interoperabilität:** Die Fähigkeit Ihrer Bereitstellung, während der Koexistenz erfolgreich zu arbeiten.

**Legacy:** Das System, von dem Sie absteigen, entweder Lync Server 2013 oder Skype for Business Server 2015.
    
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Vorbereiten der Migration](before-you-begin-the-migration.md)
    
- [Phase 1: Planen der Migration](phase-1-plan-your-migration.md)
    
- [Phase 2: Vorbereitung der Migration](phase-2-prepare-for-migration.md)
    
- [Phase 3: Bereitstellen des Pilotpools](phase-3-deploy-pilot-pool.md)
    
- [Phase 4: Verschieben von Testbenutzern in den Pilotpool](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Phase 5: Hinzufügen von Edgeservern zum Pilotpool](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Phase 7: Aufgaben nach der Migration abschließen](phase-7-complete-post-migration-tasks.md)
    
- [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md)
    

