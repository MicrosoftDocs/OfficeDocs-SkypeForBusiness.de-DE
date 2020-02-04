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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Konfigurieren Sie die folgenden Optionen, um die Eigenschaften unter externe Einstellungen zu definieren:'
ms.openlocfilehash: 2936c910f2cfc1d7e9106e2dca7477f5e1d2860e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684758"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
 
Konfigurieren Sie die folgenden Optionen, um die Eigenschaften unter **externe Einstellungen**zu definieren:
  
Aktivieren Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** , wenn Sie einen eindeutigen Pool-FQDN und IP-Adressen für Webkonferenzen und Audio/Video definieren möchten.
  
> [!NOTE]
> Wenn Sie das Kontrollkästchen für getrennte FQDN-und IP-Adressen nicht aktivieren möchten, müssen Sie für jeden der drei Dienste, die vom Edgeserver bereitgestellt werden, unterschiedliche Ports angeben. Der einzige vollqualifizierte Domänenname, der konfiguriert werden soll, ist der FQDN, der dem Access Edge-Dienst zugeordnet ist. 
  
Aktivieren Sie das Kontrollkästchen **a/v-Edgedienst ist NAT-fähig** , wenn der a/v-Edgedienst eine IP-Adresse und-Konfiguration für Netzwerkadressübersetzung (Network Address Translation, NAT) verwenden soll.
  
Für die aktivierten Edge-Dienste geben Sie einen **Pool-FQDN** und einen Port unter **Ports** ein.
  
- Definieren Sie den FQDN des **Access Edge-Service** Pools und einen Port, der den Dienst eindeutig identifiziert.
    
- Definieren Sie den FQDN des **Web Conferencing Edge-Service** Pools (wenn separater FQDN und IP-Adresse für Webkonferenzen aktiviert sind und a/V nicht ausgewählt ist) und einen Port, der den Dienst eindeutig identifiziert.
    
- Definieren Sie den FQDN des **A/v-Edge-Service** Pools (wenn separater FQDN und IP-Adresse für Webkonferenzen aktiviert sind und a/v nicht ausgewählt ist) und einen Port, der den Dienst eindeutig identifiziert.
    
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

