---
title: Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Um die Eigenschaften unter "Externe Einstellungen" zu definieren, konfigurieren Sie Folgendes:'
ms.openlocfilehash: 6075fab9dbc820b725beec8be4a674a828b4c7d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807095"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
 
Um die Eigenschaften unter **"Externe Einstellungen" zu definieren,** konfigurieren Sie Folgendes:
  
Aktivieren Sie das Kontrollkästchen **"Separate FQDN** und IP-Adresse für Webkonferenzen und A/V aktivieren", wenn Sie unterschiedliche Pool-FQDN- und -IP-Adressen für Webkonferenzen und Audio/Video definieren möchten.
  
> [!NOTE]
> Wenn Sie das Kontrollkästchen für separate FQDN- und IP-Adressen nicht aktivieren, müssen Sie für jeden der drei vom Edgeserver bereitgestellten Dienste unterschiedliche Ports angeben. Der einzige vollqualifizierte Domänenname, der konfiguriert werden soll, ist der dem Zugriffs-Edgedienst zugeordnete FQDN. 
  
Aktivieren Sie das NAT-aktivierte Kontrollkästchen für den **A/V-Edgedienst,** wenn der A/V-Edgedienst eine NAT-IP-Adresse und -Konfiguration (Network Address Translation) verwenden soll.
  
Geben Sie für die aktivierten Edgedienste einen **Pool-FQDN** und einen Port unter **"Ports" ein.**
  
- Definieren Sie den FQDN **des Zugriffs-Edgedienstpools** und einen Port, der den Dienst eindeutig identifiziert.
    
- Definieren  Sie den FQDN des Webkonferenz-Edgedienstpools (wenn separater FQDN und die separate IP-Adresse für Webkonferenzen und A/V nicht aktiviert sind) und einen Port, der den Dienst eindeutig identifiziert.
    
- Definieren Sie den FQDN des **A/V-Edgedienstpools** (wenn separater FQDN und die separate IP-Adresse für Webkonferenzen und A/V nicht aktiviert sind) und einen Port, der den Dienst eindeutig identifiziert.
    
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

