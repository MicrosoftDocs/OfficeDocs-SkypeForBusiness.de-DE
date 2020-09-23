---
title: Hinzufügen des Servers
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
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'So fügen Sie einem vorhandenen Serverpool der folgenden Pooltypen einen neuen Server hinzu:'
ms.openlocfilehash: 5e6d1772b1cb18fe8c392e3ad9fa4f131415e522
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216406"
---
# <a name="add-server"></a>Hinzufügen des Servers
 
So fügen Sie einem vorhandenen Serverpool der folgenden Pooltypen einen neuen Server hinzu:
  
- Front-End-Server der Enterprise Edition
    
- Director-Server
    
- Vermittlungsserver
    
- Audio-Video-Konferenzserver
    
- Vertrauenswürdiger Anwendungsserver
    
Jeder der neuen Poolserver hat unterschiedliche Anforderungen. Bestimmen Sie in den folgenden Abschnitten den Servertyp, den Sie dem vorhandenen Pool hinzufügen, und geben Sie die angeforderten Informationen zum jeweiligen Servertyp an. Die bereitgestellten Informationen werden zum Definieren des neuen Poolservers verwendet.
  
 **Front-End-Server der Enterprise Edition**
  
- Vollqualifizierter Domänenname des neuen Servers gemäß der DNS-Definition (Domain Name System).
    
- Wählen Sie **Alle konfigurierten IP-Adressen verwenden** aus, was bedeutet, dass Sie beliebige auf dem Computer definierte IP-Adressen verwenden können. Sie können auch **Dienstverwendung auf ausgewählte IP-Adressen begrenzen** auswählen und für den neuen Server eine bestimmte Adresse eingeben. Die eingegebene IP-Adresse ist die einzige, die für die gehosteten Dienste antwortet.
    
- Geben Sie eine **PSTN-IP-Adresse** an, wenn auf dem Front-End-Server ein Vermittlungsserver verbunden ist.
    
- Wählen Sie die Option **IPv6 aktivieren**, um IPv6 für diesen Server zu aktivieren.
    
  **Director-Server**
  
- Der vollqualifizierte Domänenname des neuen Servers gemäß der DNS-Definition.
    
- Wählen Sie **Alle konfigurierten IP-Adressen verwenden** aus, was bedeutet, dass Sie beliebige auf dem Computer definierte IP-Adressen verwenden. Sie können auch **Dienstverwendung auf ausgewählte IP-Adressen begrenzen** auswählen und für den neuen Server eine bestimmte IP-Adresse eingeben. Die eingegebene IP-Adresse ist die einzige, die für die gehosteten Dienste antwortet.
    
  **Vermittlungsserver**
  
- Der vollqualifizierte Domänenname des neuen Servers gemäß der DNS-Definition.
    
- Wählen Sie **Alle konfigurierten IP-Adressen verwenden** aus, was bedeutet, dass Sie beliebige auf dem Computer definierte IP-Adressen verwenden können. Alternativ können Sie **Dienstverwendung auf ausgewählte IP-Adressen begrenzen** auswählen und eine bestimmte IP-Adresse für den neuen Server als primäre IP-Adresse sowie eine IP-Adresse für das PSTN (Public Switched Telephone Network, Telefonfestnetz) eingeben. Die eingegebene IP-Adressen sind die einzigen, die für die vorgesehenen Dienste antworten.
    
    > [!NOTE]
    > Beim Vermittlungsserver sind die als primäre IP-Adresse und PSTN-IP-Adresse eingegebenen IP-Adressen identisch. Die IP-Adressen können gesondert definiert werden, wenn Sie dedizierte Netzwerkschnittstellen oder separate IP-Adressen für dieselbe Netzwerkschnittstellen verwenden. Wenn Sie über zwei Netzwerkschnittstellen verfügen (eine für die lokale Netzwerkverbindung und eine für die PSTN-Verbindung), müssen Sie zwei unterschiedliche IP-Adressen zuweisen. 
  
  **Audio/Video-Konferenzserver**
  
- Der vollqualifizierte Domänenname des neuen Servers gemäß der DNS-Definition.
    
- Wählen Sie **Alle konfigurierten IP-Adressen verwenden** aus, was bedeutet, dass Sie beliebige auf dem Computer definierte IP-Adressen verwenden können. Sie können auch **Dienstverwendung auf ausgewählte IP-Adressen begrenzen** auswählen und für den neuen Server eine bestimmte Adresse eingeben. Die eingegebene IP-Adresse ist die einzige, die für die gehosteten Dienste antwortet.
    
  **Vertrauenswürdiger Anwendungsserver**
  
- Der vollqualifizierte Domänenname des neuen Servers gemäß der DNS-Definition.
    

