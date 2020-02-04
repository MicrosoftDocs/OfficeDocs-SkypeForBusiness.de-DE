---
title: Registrierungseinstellungen für Lync Server für 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Sie bearbeiten die Einstellungen für die Widerstandsfähigkeit und konfigurieren die folgenden Eigenschaften:'
ms.openlocfilehash: 31a8504aecbc14ae2c81ad27a3aaeedbe9e40b66
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684418"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Registrierungseinstellungen für Lync Server für 2010 – Erweiterung
 
Sie bearbeiten die Einstellungen für die **Widerstandsfähigkeit** und konfigurieren die folgenden Eigenschaften:
  
- Wählen Sie in der Liste den **zugehörigen sicherungsregistrierungspool** aus.
    
    Aktivieren Sie optional das Kontrollkästchen **Automatisches Failover und Failback für VoIP** .
    
    Konfigurieren Sie das **Erkennungsintervall für Sprachfehler (SEK)** und das **sprach-Failback-Intervall (SEK)**. Standardmäßig sind die Intervalle 120 Sekunden für die Sprachfehler Erkennung und 240 Sekunden für sprach-Failback.
    
    > [!CAUTION]
    > Die Anzahl der Sekunden, die Sie für die Failover-und Failback-Intervalle definieren, sollten sorgfältig getestet werden, um sicherzustellen, dass die Widerstandsfähigkeit wie erwartet funktioniert. Wenn Sie das Intervall auf "gering" (also weniger als 120 Sekunden) oder das Failover und die Failback-Einstellung zu eng festlegen, kann dies zu einem tatsächlichen Failover und Failback führen, die nicht erwartungsgemäß funktionieren. 
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

