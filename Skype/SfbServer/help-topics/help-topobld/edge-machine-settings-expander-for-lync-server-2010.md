---
title: Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
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
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Zum Bearbeiten der Eigenschaften für Edgeservercomputer als einzelner Edgeserver oder als Mitgliedscomputer in einem Edgepool konfigurieren Sie Die Konfigurationseinstellungen für Servernamen und IP-Adressen:'
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807135"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
 
Zum Bearbeiten der Eigenschaften für Edgeservercomputer als einzelner Edgeserver oder als Mitgliedscomputer in einem Edgepool konfigurieren Sie Die Konfigurationseinstellungen für Servernamen und **IP-Adressen:**
  
- **Interner Name oder FQDN:** Geben Sie den Namen des Computers so ein, wie er im Dns (Domain Name System) referenziert wird. 
    
- **Interne IPv4-Adresse:** Geben Sie die IPv4-Adresse der internen Netzwerkschnittstellenkarte (NIC) für diesen Computer ein.
    
- Sie konfigurieren die externe **IPv4-Adresse des Zugriffs-Edgediensts,** die diesem Computer zugeordnet ist. 
    
    > [!IMPORTANT]
    > Wenn Sie eine einzelne IP-Adresse für die Edgeserverkonfiguration verwenden möchten, können Sie nur die externe IPv4-Adresse für den Zugriffs-Edgedienst bearbeiten. Die anderen Edgedienste verwenden dieselbe IPv4-Adresse wie der Zugriffs-Edgedienst. 
  
- Wenn für die Bearbeitung verfügbar, konfigurieren Sie die externe **IPv4-Adresse** des Webkonferenzdiensts, die diesem Computer zugeordnet ist. 
    
- Wenn für die Bearbeitung verfügbar, konfigurieren Sie die externe **IPv4-Adresse** des **A/V-Edgediensts,** die diesem Computer zugeordnet ist.
    
- Falls für die Bearbeitung verfügbar, konfigurieren Sie die **NAT-aktivierte öffentliche IPv4-Adresse,** die diesem Computer zugeordnet ist.
    
    > [!IMPORTANT]
    > Die Konfigurationseigenschaft für NAT-aktivierte öffentliche **IPv4-Adressen** kann nur bearbeitet werden, wenn Sie die Netzwerkadressenübersetzung (Network Address Translation, NAT) für den A/V-Edgedienst bereitstellen möchten.
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

