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
- NOCSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'So fügen Sie einen neuen Server zu einem vorhandenen Pool von Servern hinzu, wobei es sich um einen der folgenden Pools handelt:'
ms.openlocfilehash: d4f4afc0d4a7cb6fafe47de95c648aa1769027e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820647"
---
# <a name="add-server"></a>Hinzufügen des Servers
 
So fügen Sie einen neuen Server zu einem vorhandenen Pool von Servern hinzu, wobei es sich um einen der folgenden Pools handelt:
  
- Enterprise Edition-Front-End-Server
    
- Director-Server
    
- Vermittlungsserver
    
- Audio/Video Konferenz Server
    
- Vertrauenswürdiger Anwendungsserver
    
Jeder der neuen Pool Server hat andere Anforderungen. Suchen Sie in den folgenden Abschnitten nach dem Typ des Servers, den Sie dem vorhandenen Pool hinzufügen, und geben Sie die angeforderten Informationen an, wie Sie für die einzelnen Servertypen definiert sind. Sie geben die angeforderten Informationen an, um den neuen Pool Server zu definieren.
  
 **Enterprise Edition-Front-End-Server**
  
- Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des neuen Servers, wie er im DNS (Domain Name System) definiert ist.
    
- Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet werden kann. Alternativ können Sie die Option **Dienst Verwendung auf ausgewählte IP-Adressen einschränken** auswählen und eine bestimmte Adresse auf dem neuen Server eingeben. Die eingegebene IP-Adresse ist die einzige IP-Adresse, die auf die gehosteten Dienste reagiert.
    
- Definieren Sie eine **PSTN-IP-Adresse** , wenn sich ein Vermittlungsserver auf dem Front-End-Server befindet.
    
- Wählen Sie **IPv6 aktivieren** aus, um IPv6 für diesen Server zu aktivieren.
    
  **Director-Server**
  
- Der FQDN des neuen Servers, wie er in DNS definiert ist.
    
- Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet wird. Sie können auch die Option **Dienstnutzung auf ausgewählte IP-Adressen einschränken** und eine bestimmte IP-Adresse auf dem neuen Server eingeben. Die eingegebene IP-Adresse ist die einzige IP-Adresse, die auf die gehosteten Dienste reagiert.
    
  **Vermittlungsserver**
  
- Der FQDN des neuen Servers, wie er in DNS definiert ist.
    
- Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet werden kann. Sie können auch die Option **Dienstnutzung auf ausgewählte IP-Adressen einschränken** und eine bestimmte IP-Adresse auf dem neuen Server als primäre IP-Adresse eingeben und eine IP-Adresse für die IP-Adresse des öffentlich geschalteten Telefonnetzwerks (PSTN) eingeben. Die eingegebenen IP-Adressen sind die einzige IP-Adresse, die auf die angegebenen Dienste reagiert.
    
    > [!NOTE]
    > Für den Vermittlungs Server ist die IP-Adresse, die für die primäre IP-Adresse und die PSTN-IP-Adresse eingegeben wurde, standardmäßig identisch. Die IP-Adressen können separat definiert werden, wenn Sie dedizierte Netzwerkschnittstellen oder getrennte IP-Adressen auf derselben Netzwerkschnittstelle verwenden. Wenn Sie über zwei Netzwerkschnittstellen verfügen, eine für die lokale Netzwerkverbindung und eine für die PSTN-Verbindung, müssen Sie unterschiedliche IP-Adressen zuweisen. 
  
  **Audio/Video Konferenz Server**
  
- Der FQDN des neuen Servers, wie er in DNS definiert ist.
    
- Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet werden kann. Alternativ können Sie die Option **Dienst Verwendung auf ausgewählte IP-Adressen einschränken** auswählen und eine bestimmte Adresse auf dem neuen Server eingeben. Die eingegebene IP-Adresse ist die einzige IP-Adresse, die auf die gehosteten Dienste reagiert.
    
  **Vertrauenswürdiger Anwendungsserver**
  
- Der FQDN des neuen Servers, wie er in DNS definiert ist.
    

