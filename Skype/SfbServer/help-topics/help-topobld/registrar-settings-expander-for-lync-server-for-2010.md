---
title: Registrierungseinstellungen für Lync Server für 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Sie bearbeiten die Einstellungen für Flexibilität und konfigurieren Sie die folgenden Eigenschaften:'
ms.openlocfilehash: d02462b03b7255860695e373af276a69d92956e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910249"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Registrierungseinstellungen für Lync Server für 2010 – Erweiterung
 
Sie bearbeiten die Einstellungen für **Flexibilität** und konfigurieren Sie die folgenden Eigenschaften:
  
- Wählen Sie **zugeordneter Sicherungsregistrierungsstellen-Pool** aus der Liste aus.
    
    Aktivieren Sie optional das Kontrollkästchen **Automatisches Failover und Failback für VoIP** .
    
    Konfigurieren der **VoIP-Fehler Erkennung Intervall (s)** und **VoIP Failback Intervall (s)**. Standardmäßig sind die Intervalle 120 für die Erkennung von VoIP-Fehlern und 240 Sekunden für VoIP Failback.
    
    > [!CAUTION]
    > Die Anzahl der Sekunden an, denen Sie für die Intervalle Failover und Failback definieren sollten sorgfältig getestet werden, um sicherzustellen, dass die Resiliency wie erwartet funktioniert. Festlegen des Intervalls auf Niedrig (d. h., kleiner als 120 Sekunden) oder das Failover und Failback festlegen zu stark möglicherweise in den tatsächlichen Failover und Failback funktioniert nicht wie erwartet. 
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

