---
title: Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Zum Bearbeiten der Eigenschaften für Edge-Server-Computer als einen einzigen Edge-Server oder als Mitgliedscomputer in einem edgepool, konfigurieren Sie Servername und IP-Adresse Konfigurationseinstellungen:'
ms.openlocfilehash: f0125ba8d9c7ff181aff0a29f69a5077b1ad0818
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891540"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
 
Zum Bearbeiten der Eigenschaften für Edge-Server-Computer als einen einzigen Edge-Server oder als Mitgliedscomputer in einem edgepool, konfigurieren Sie **Servername und IP-Adresskonfiguration** Einstellungen:
  
- **Interner Name oder FQDN**: Geben Sie den Namen des Computers ein, wie er im Domain Name System (DNS) verwiesen wird. 
    
- **Interne IPv4-Adresse**: Geben Sie die IPv4-Adresse der internen Netzwerkkarte (NIC) für diesen Computer ein.
    
- Sie konfigurieren die **Zugriffs-edgedienst** - **externe IPv4-Adresse** , die diesem Computer zugeordnet
    
    > [!IMPORTANT]
    > Wenn Sie eine einzelne IP-Adresse für die Konfiguration der Edge-Server verwenden ausgewählt haben, werden Sie nur die externe IPv4-Adresse für den Zugriffs-Edgeservers Dienst bearbeiten sein. Der Edge-Dienste nutzen die gleiche IPv4-Adresse als Zugriffs-edgediensts. 
  
- Konfigurieren Sie die **-Webkonferenzdienst** - **externe IPv4-Adresse** , die diesem Computer zugeordnet Falls zur Bearbeitung verfügbar
    
- Wenn zur Bearbeitung verfügbar, Sie konfigurieren die **A / V-edgedienst** **externe IPv4-Adresse** , die diesem Computer zugeordnet
    
- Falls zur Bearbeitung verfügbar, konfigurieren Sie die **NAT-aktivierte öffentliche IPv4-Adresse** , die diesem Computer zugeordnet.
    
    > [!IMPORTANT]
    > Die Konfigurationseigenschaft für **NAT-aktivierte öffentliche IPv4-Adresse** stehen nur zur Verfügung, bearbeiten, wenn Sie ausgewählt haben, geben Sie die Netzwerkadressübersetzung (NAT) für den A / V-edgedienst
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

