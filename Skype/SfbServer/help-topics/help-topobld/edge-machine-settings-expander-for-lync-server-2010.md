---
title: Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
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
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Um die Eigenschaften für Edgeserver Computer als einzelne Edgeserver oder als Mitgliedscomputer in einer Edgepool zu bearbeiten, konfigurieren Sie die Konfigurationseinstellungen für Server Name und IP-Adresse:'
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218926"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
 
Um die Eigenschaften für Edgeserver Computer als einzelne Edgeserver oder als Mitgliedscomputer in einer Edgepool zu bearbeiten, konfigurieren Sie die Konfigurationseinstellungen für **Server Name und IP-Adresse** :
  
- **Interner Name oder FQDN**: Geben Sie den Namen des Computers ein, auf den im DNS (Domain Name System) verwiesen wird. 
    
- **Interne IPv4-Adresse**: Geben Sie die IPv4-Adresse der internen Netzwerkschnittstellenkarte (NIC) für diesen Computer ein.
    
- Sie konfigurieren die **Zugriffs-Edgedienst** **externe IPv4-Adresse** , die diesem Computer zugeordnet ist.
    
    > [!IMPORTANT]
    > Wenn Sie für die Edgeserver Konfiguration eine einzelne IP-Adresse ausgewählt haben, können Sie nur die externe IPv4-Adresse für die Zugriffs-Edgedienst bearbeiten. Die anderen Edge-Dienste haben dieselbe IPv4-Adresse wie die Zugriffs-Edgedienst. 
  
- Wenn Sie zum Bearbeiten zur Verfügung stehen, konfigurieren Sie die **Webkonferenzdienst** **externe IPv4-Adresse** , die diesem Computer zugeordnet ist.
    
- Wenn Sie zum Bearbeiten zur Verfügung stehen, konfigurieren Sie die **A/V-Edgedienst** **externe IPv4-Adresse** , die diesem Computer zugeordnet ist.
    
- Wenn Sie zum Bearbeiten zur Verfügung stehen, konfigurieren Sie die **NAT-aktivierte öffentliche IPv4-Adresse** , die diesem Computer zugeordnet ist.
    
    > [!IMPORTANT]
    > Die Konfigurationseigenschaft für die **NAT-fähige öffentliche IPv4-Adresse** steht nur zur Bearbeitung zur Verfügung, wenn Sie die Netzwerkadressübersetzung (Network Address Translation, NAT) für die A/V-Edgedienst bereitgestellt haben.
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

