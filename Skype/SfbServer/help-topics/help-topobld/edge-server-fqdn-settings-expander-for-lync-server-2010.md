---
title: Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Um die Eigenschaften unter externe Einstellungen zu definieren, konfigurieren Sie Folgendes:'
ms.openlocfilehash: 3ebd98c17f7b32af72809375bd17e55514684e6d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203123"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
 
Um die Eigenschaften unter **externe Einstellungen**zu definieren, konfigurieren Sie Folgendes:
  
Wählen Sie aus der **Enable separaten FQDN und IP-Adressen für Webkonferenzen und A / V** das Kontrollkästchen, wenn Sie unterschiedliche Pool-FQDN und IP-definieren möchten Adressen für Webkonferenzen und Audio/Video.
  
> [!NOTE]
> Wenn Sie das Kontrollkästchen für separaten FQDN und IP-Adressen nicht zu aktivieren auswählen, müssen Sie unterschiedliche Ports für jede der drei Dienste von der Edge-Server angeben. Der einzige vollqualifizierten Domänennamen zu konfigurieren ist der vollqualifizierte Domänenname der Zugriffs-edgedienst zugeordnet. 
  
Wählen Sie aus der **A / V-edgedienst ist für NAT aktiviert** das Kontrollkästchen, wenn Sie möchten, dass den A / V-edgedienst, ein Netzwerk verwenden Adresse Netzwerkadressübersetzung (NAT) IP-Adresse und Konfiguration.
  
Für die aktivierten edgedienste Geben Sie einen **Pool-FQDN** und unter **Ports** einen port
  
- Definieren Sie den Pool-FQDN des **Zugriffs-edgedienst** und einen Port, der den Dienst eindeutig identifiziert wird.
    
- Definieren Sie den Pool-FQDN des **Webkonferenz-edgedienst** (wenn aktivieren, trennen Sie FQDN und IP-Adresse für Webkonferenzen und A / V nicht ausgewählt ist) und einen Port, die den Dienst eindeutig identifiziert wird.
    
- Definieren der **A / V-edgedienst** Pool-FQDN (wenn aktivieren, trennen Sie FQDN und IP-Adresse für Webkonferenzen und A / V nicht ausgewählt ist) und einen Port, die den Dienst eindeutig identifiziert wird.
    
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

