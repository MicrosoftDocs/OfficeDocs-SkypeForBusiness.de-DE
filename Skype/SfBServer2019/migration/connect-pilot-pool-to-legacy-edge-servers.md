---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Bereitstellung von Skype for Business Server 2019 müssen Sie eine Föderations Route für Ihre Website konfigurieren. Um die von der Legacy Installation verwendete Föderations Route verwenden zu können, muss Skype for Business Server 2019 so konfiguriert sein, dass Sie diese Route verwenden kann.
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239224"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Verbinden des Pilotpools mit Edgeservern der Vorversion

Nach der Bereitstellung von Skype for Business Server 2019 müssen Sie eine Föderations Route für Ihre Website konfigurieren. Um die von der Legacy Installation verwendete Föderations Route verwenden zu können, muss Skype for Business Server 2019 so konfiguriert sein, dass Sie diese Route verwenden kann. 
  
Wenn Sie die Skype for Business Server 2019-Website für die Verwendung des Directors und des Edge-Servers der Legacy Bereitstellung aktivieren möchten, verwenden Sie den Topologie-Generator, um den Legacy-Edge-Pool zu verknüpfen.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>So ordnen Sie den Legacy-Edge-Pool mithilfe des Topologie-Generators zu

1. Öffnen Sie den Topologie-Generator. 
    
2. Wählen Sie Ihre Website aus, die sich direkt unterhalb des **Skype for Business Server** -Knotens befindet. 
    
3. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.
    
4. Wählen Sie im linken Bereich **Föderations Route**aus.
    
5. Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann den Legacy-Director oder den Legacy-Edgeserver aus, wenn kein Director aufgeführt ist.
  
6. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
7. Navigieren Sie im Topologie-Generator unter dem 2019-Knoten von Skype for Business Server zu den Front-End-Pools **Standard Edition Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
8. Aktivieren Sie unter **Zuordnungen**das Kontrollkästchen neben **Edge-Pool zuordnen (für Medienkomponenten)**. 
    
9. Wählen Sie in der Liste den Legacy-Edgeserver aus. 
  
10. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
11. Wählen Sie im **Topologie-Generator**den obersten Knoten, **Skype for Business Server**.
    
12. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **weiter**.
    
13. Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen**.
    

