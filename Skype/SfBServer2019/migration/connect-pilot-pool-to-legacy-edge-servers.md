---
title: Verbinden des pilotpools mit Edgeservern der Vorgängerversion
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Bereitstellung von Skype für Business Server 2019, müssen Sie eine der partnerverbundroute des Standorts für Ihre Website zu konfigurieren. Um die partnerverbundroute verwenden, die von der Vorversion Installation verwendet wird, muss Skype für Business Server 2019 konfiguriert sein, um diese Route verwendet werden.
ms.openlocfilehash: 6766034cf54fd867c9b270324cb1db8ad2d644d5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030567"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Verbinden des pilotpools mit Edgeservern der Vorgängerversion

Nach der Bereitstellung von Skype für Business Server 2019, müssen Sie eine der partnerverbundroute des Standorts für Ihre Website zu konfigurieren. Um die partnerverbundroute verwenden, die von der Vorversion Installation verwendet wird, muss Skype für Business Server 2019 konfiguriert sein, um diese Route verwendet werden. 
  
Verwenden Sie zum Aktivieren der Skype für Business Server 2019 Standort den Director und Edgeserver der Bereitstellung der Vorversion verwenden Topologie-Generator edgepool der Vorgängerversion zuordnen.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Edgepool der Vorgängerversion mithilfe des Topologie-Generator zuordnen

1. Topologie-Generator zu öffnen. 
    
2. Wählen Sie Ihren Standort, der direkt unterhalb des Knotens **Skype für Business Server** ist. 
    
3. Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.
    
4. Wählen Sie im linken Bereich die Option **partnerverbundroute**aus.
    
5. Klicken Sie unter **Zuweisung der partnerverbundroute Route**wählen Sie **SIP-Partnerverbund aktivieren**aus, und wählen Sie dann die Vorversion Director oder Edgeserver der Vorversion Wenn kein Director aufgeführt ist.
  
6. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
7. Navigieren Sie im Topologie-Generator unter der Skype für Business Server 2019-Knoten zu der **Standard Edition-Server** oder **Enterprise Edition-Front-End-Pools**, mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
8. Wählen Sie unter **Zuordnungen**das Kontrollkästchen neben **edgepool zuordnen (für Medienkomponenten)**. 
    
9. Wählen Sie aus der Liste Edgeserver der Vorversion aus. 
  
10. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
11. Wählen Sie im **Topologie-Generator**den obersten Knoten, **Skype für Business Server**aus.
    
12. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.
    
13. Wenn der **Veröffentlichen-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    

