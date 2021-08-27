---
title: Verbinden des Pilotpools mit Legacy-Edgeservern
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
description: Nach der Bereitstellung von Skype for Business Server 2019 müssen Sie eine Verbundroute für Ihren Standort konfigurieren. Um die Verbundroute zu verwenden, die von der Legacyinstallation verwendet wird, muss Skype for Business Server 2019 für die Verwendung dieser Route konfiguriert sein.
ms.openlocfilehash: a5f5da34300d993f59d4de5e2eb0b47cc58eff0e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607462"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Verbinden des Pilotpools mit Legacy-Edgeservern

Nach der Bereitstellung von Skype for Business Server 2019 müssen Sie eine Verbundroute für Ihren Standort konfigurieren. Um die Verbundroute zu verwenden, die von der Legacyinstallation verwendet wird, muss Skype for Business Server 2019 für die Verwendung dieser Route konfiguriert sein. 
  
Um den Standort Skype for Business Server 2019 für die Verwendung des Director- und Edgeservers der Legacybereitstellung zu aktivieren, verwenden Sie den Topologie-Generator, um den älteren Edgepool zuzuordnen.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu

1. Öffnen Sie den Topologie-Generator. 
    
2. Wählen Sie Ihre Website aus, die sich direkt unterhalb des **knotens Skype for Business Server** befindet. 
    
3. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.
    
4. Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.
    
5. Wählen Sie unter **Standortverbundroutenzuweisung** **SIP-Partnerverbund aktivieren** aus, und wählen Sie dann den Legacy-Director oder den Legacy-Edgeserver aus, wenn kein Director aufgeführt ist.
  
6. Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
7. Navigieren Sie im Topologie-Generator unter dem Knoten Skype for Business Server 2019 zum **Standard Edition Server** oder **Enterprise Edition Front-End-Pools,** klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **"Eigenschaften bearbeiten".**
    
8. Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)**. 
    
9. Wählen Sie in der Liste den Edgeserver der Vorversion aus. 
  
10. Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
11. Wählen Sie im **Topologie-Generator** den obersten Knoten **aus, Skype for Business Server**.
    
12. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.
    
13. Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.
    

