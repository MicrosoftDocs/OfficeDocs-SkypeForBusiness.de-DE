---
title: Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Um die Eigenschaften unter "Externe Einstellungen" zu definieren, konfigurieren Sie Folgendes:'
ms.openlocfilehash: 763fed345ec3d53496be216dbd94e26825c2766b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828918"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
 
Um die Eigenschaften unter **"Externe Einstellungen"** zu definieren, konfigurieren Sie Folgendes:
  
Aktivieren Sie das Kontrollkästchen **Separate FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren,** wenn Sie unterschiedliche Pool-FQDNs und IP-Adressen für Webkonferenzen und Audio/Video definieren möchten.
  
> [!NOTE]
> Wenn Sie das Kontrollkästchen für separate FQDN- und IP-Adressen nicht aktivieren möchten, müssen Sie unterschiedliche Ports für jeden der drei vom Edgeserver bereitgestellten Dienste bereitstellen. Der einzige vollqualifizierte Domänenname, der konfiguriert werden soll, ist der FQDN, der dem Zugriffs-Edgedienst zugeordnet ist. 
  
Aktivieren Sie das Kontrollkästchen **"A/V-Edgedienst ist NAT aktiviert",** wenn der A/V-Edgedienst eine NAT-IP-Adresse (Network Address Translation) und -Konfiguration verwenden soll.
  
Für die aktivierten Edgedienste geben Sie einen **Pool-FQDN** und einen Port unter **Ports** ein.
  
- Definieren Sie den FQDN des **Zugriffs-Edgedienstpools** und einen Port, der den Dienst eindeutig identifiziert.
    
- Definieren Sie den FQDN des **Webkonferenz-Edgedienstpools** (wenn separateR FQDN und die IP-Adresse für Webkonferenzen und A/V nicht aktiviert sind) und einen Port, der den Dienst eindeutig identifiziert.
    
- Definieren Sie den FQDN des **A/V-Edgedienstpools** (wenn separate FQDN und IP-Adresse für Webkonferenzen und A/V nicht aktiviert sind) und einen Port, der den Dienst eindeutig identifiziert.
    
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

