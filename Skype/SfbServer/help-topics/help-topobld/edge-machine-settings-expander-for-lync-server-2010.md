---
title: Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
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
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Um die Eigenschaften für Edgeservercomputer als einzelne Edgeserver oder als Mitgliedscomputer in einem Edgepool zu bearbeiten, konfigurieren Sie die Konfigurationseinstellungen für Servername und IP-Adresse:'
ms.openlocfilehash: 81fb33a2217431cd908156dab95e36cca0675f23
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604944"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
 
Um die Eigenschaften für Edgeservercomputer als einzelne Edgeserver oder als Mitgliedscomputer in einem Edgepool zu bearbeiten, konfigurieren Sie die Konfigurationseinstellungen für **Servername und IP-Adresse:**
  
- **Interner Name oder FQDN:** Geben Sie den Namen des Computers ein, auf den im Dns (Domain Name System) verwiesen wird. 
    
- **Interne IPv4-Adresse:** Geben Sie die IPv4-Adresse der internen Netzwerkschnittstellenkarte (NIC) für diesen Computer ein.
    
- Sie konfigurieren die diesem Computer zugeordnete **externe IPv4-Adresse** des **Zugriffs-Edgediensts.**
    
    > [!IMPORTANT]
    > Wenn Sie eine einzelne IP-Adresse für die Edgeserverkonfiguration verwendet haben, können Sie nur die externe IPv4-Adresse für den Zugriffs-Edgedienst bearbeiten. Die anderen Edgedienste verwenden dieselbe IPv4-Adresse wie der Zugriffs-Edgedienst. 
  
- Falls zur Bearbeitung verfügbar, konfigurieren Sie die diesem Computer zugeordnete **externe IPv4-Adresse** des **Webkonferenzdiensts.**
    
- Falls zur Bearbeitung verfügbar, konfigurieren Sie die diesem Computer zugeordnete **externe IPv4-Adresse** des **A/V-Edgediensts.**
    
- Wenn für die Bearbeitung verfügbar, konfigurieren Sie die **NAT-aktivierte öffentliche IPv4-Adresse, die** diesem Computer zugeordnet ist.
    
    > [!IMPORTANT]
    > Die Konfigurationseigenschaft für **NAT-aktivierte öffentliche IPv4-Adresse** kann nur bearbeitet werden, wenn Sie die Netzwerkadressübersetzung (Network Address Translation, NAT) für den A/V-Edgedienst bereitgestellt haben.
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

