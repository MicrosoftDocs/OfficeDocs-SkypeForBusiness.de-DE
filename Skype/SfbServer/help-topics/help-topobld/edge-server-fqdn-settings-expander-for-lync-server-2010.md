---
title: Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Konfigurieren Sie zum Definieren der Eigenschaften unter externe Einstellungen Folgendes:'
ms.openlocfilehash: 2de4b562d5b6a8b8ef9707d603fe5f4667893ba4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218246"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
 
Konfigurieren Sie zum Definieren der Eigenschaften unter **externe Einstellungen**Folgendes:
  
Aktivieren Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** , wenn Sie einen eindeutigen Pool-FQDN und IP-Adressen für Webkonferenzen und Audio/Video definieren möchten.
  
> [!NOTE]
> Wenn Sie das Kontrollkästchen für separate FQDN-und IP-Adressen nicht aktivieren möchten, müssen Sie für jeden der drei vom Edgeserver bereitgestellten Dienste unterschiedliche Ports bereitstellen. Der einzige vollqualifizierte Domänenname, der konfiguriert werden soll, ist der dem Zugriffs-Edgedienst zugeordnete FQDN. 
  
Aktivieren Sie das Kontrollkästchen **A/V-Edgedienst ist NAT aktiviert** , wenn die A/V-Edgedienst eine NAT-IP-Adresse (Network Address Translation, Netzwerkadressübersetzung) und-Konfiguration verwenden soll.
  
Für die aktivierten Edge-Dienste geben Sie einen **Pool-FQDN** und einen Port unter **Ports** ein.
  
- Definieren Sie den FQDN des **Zugriffs-Edgedienst** Pools und einen Port, mit dem der Dienst eindeutig identifiziert wird.
    
- Definieren Sie den FQDN des **Webkonferenz-Edgedienst** Pools (wenn unterschiedlicher FQDN und IP-Adresse für Webkonferenzen aktiviert ist und a/V nicht ausgewählt ist) und einen Port, der den Dienst eindeutig identifiziert.
    
- Definieren Sie den FQDN des **A/V-Edgedienst** Pools (wenn unterschiedlicher FQDN und IP-Adresse für Webkonferenzen aktiviert ist und a/V nicht ausgewählt ist) und einen Port, der den Dienst eindeutig identifiziert.
    
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

