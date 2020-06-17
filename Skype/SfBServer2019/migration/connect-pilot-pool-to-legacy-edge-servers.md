---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
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
description: Nachdem Sie Skype for Business Server 2019 bereitgestellt haben, müssen Sie eine partnerverbundroute für Ihre Website konfigurieren. Um die von der Legacy Installation verwendete Verbund Route verwenden zu können, muss Skype for Business Server 2019 für die Verwendung dieser Route konfiguriert sein.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753925"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Verbinden des Pilotpools mit Edgeservern der Vorversion

Nachdem Sie Skype for Business Server 2019 bereitgestellt haben, müssen Sie eine partnerverbundroute für Ihre Website konfigurieren. Um die von der Legacy Installation verwendete Verbund Route verwenden zu können, muss Skype for Business Server 2019 für die Verwendung dieser Route konfiguriert sein. 
  
Damit die Skype for Business Server 2019-Website den Director und Edgeserver der Legacy-Bereitstellung verwenden kann, ordnen Sie die Legacy Edgepool mithilfe des Topologie-Generators zu.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu

1. Öffnen Sie den Topologie-Generator. 
    
2. Wählen Sie Ihre Website aus, die sich direkt unterhalb des **Skype for Business Server** Knotens befindet. 
    
3. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.
    
4. Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.
    
5. Wählen Sie unter **Standort Verbund Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann Legacy Director oder Legacy Edgeserver aus, wenn kein Director aufgeführt ist.
  
6. Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
7. Navigieren Sie im Topologie-Generator unter dem Knoten Skype for Business Server 2019 zu den Front-End-Pools **Standard Edition-Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
8. Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)**. 
    
9. Wählen Sie in der Liste den Edgeserver der Vorversion aus. 
  
10. Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
11. Wählen Sie im **Topologie-Generator**den obersten Knoten **Skype for Business Server**aus.
    
12. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.
    
13. Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.
    

