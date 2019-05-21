---
title: Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Wenn Sie die Eigenschaften für Edgeserver-Computer als einzelnen Edgeserver oder als Mitgliedscomputer in einem Edge-Pool bearbeiten möchten, konfigurieren Sie die Konfigurationseinstellungen für Servername und IP-Adresse:'
ms.openlocfilehash: c9201cfde9f19391e1cee351de6d4efac00be9dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302336"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
 
Wenn Sie die Eigenschaften für Edgeserver-Computer als einzelnen Edgeserver oder als Mitgliedscomputer in einem Edge-Pool bearbeiten möchten, konfigurieren Sie die Konfigurationseinstellungen für **Servername und IP-Adresse** :
  
- **Interner Name oder FQDN**: Geben Sie den Namen des Computers ein, auf den im DNS (Domain Name System) Bezug genommen wird. 
    
- **Interne IPv4-Adresse**: Geben Sie die IPv4-Adresse der internen Netzwerkschnittstellenkarte (NIC) für diesen Computer ein.
    
- Sie konfigurieren die **externe IPv4-Adresse** des **Access Edge-Diensts** , die diesem Computer zugeordnet ist.
    
    > [!IMPORTANT]
    > Wenn Sie die Verwendung einer einzelnen IP-Adresse für die Edgeserver-Konfiguration ausgewählt haben, können Sie nur die externe IPv4-Adresse für den Access Edge-Dienst bearbeiten. Die anderen Edge-Dienste verwenden dieselbe IPv4-Adresse wie der Access-Edgedienst. 
  
- Wenn Sie zum Bearbeiten zur Verfügung stehen, konfigurieren Sie die **externe IPv4-Adresse** des Webkonferenz **Diensts** , die diesem Computer zugeordnet ist.
    
- Wenn Sie zum Bearbeiten zur Verfügung stehen, konfigurieren Sie die **externe IPv4-Adresse** des **A/V-Edgedienst** , die diesem Computer zugeordnet ist.
    
- Wenn Sie zum Bearbeiten zur Verfügung stehen, konfigurieren Sie die **NAT-fähige öffentliche IPv4-Adresse** , die diesem Computer zugeordnet ist.
    
    > [!IMPORTANT]
    > Die Konfigurationseigenschaft für **NAT-fähige öffentliche IPv4-Adressen** steht nur zur Bearbeitung zur Verfügung, wenn Sie für den A/V-Edgedienst Netzwerkadressübersetzung (Network Address Translation, NAT) bereitstellen.
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

