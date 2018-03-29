---
title: Server hinzufügen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Zum Hinzufügen eines neuen Servers zu einem vorhandenen Pool von Servern, eine der folgenden pooltypen:'
ms.openlocfilehash: 609fbb28900ac67e0a4e1e2a400f1eebb29b2ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="add-server"></a>Server hinzufügen
 
Zum Hinzufügen eines neuen Servers zu einem vorhandenen Pool von Servern, eine der folgenden pooltypen:
  
- Enterprise Edition-Front-End-Server
    
- Director-server
    
- Vermittlungsserver
    
- A/v-Konferenzserver
    
- Vertrauenswürdiger Anwendungsserver
    
Jede der neuen Poolserver verfügt über verschiedene Anforderungen. Legen Sie in den folgenden Abschnitten die Server, auf dem Sie den vorhandenen Pool hinzufügen möchten, und geben Sie die Informationen für jeden Servertyp definierten angefordert. Sie bieten die angeforderte Informationen, um den neuen Poolserver definieren.
  
 **Enterprise Edition-Front-End-Server**
  
- Vollqualifizierter Domänenname (FQDN) des neuen Servers wie er im Domain Name System (DNS) definiert ist.
    
- Wählen Sie **Alle konfigurierte IP-Adressen verwenden**, was bedeutet, dass alle IP-Adressen auf dem Computer definierten verwendet werden kann. Alternativ können Sie **Service-Verwendung einschränken ausgewählten IP-Adressen** auswählen und geben Sie eine bestimmte Adresse auf dem neuen Server. IP-Adresse des ist die einzige IP-Adresse für gehostete Dienste reagieren soll.
    
- Definieren Sie eine **PSTN-IP-Adresse** aus, wenn Sie einen Vermittlungsserver auf dem Front-End-Server verbunden ist.
    
- Wählen Sie **IPv6 aktivieren,** um IPv6 für diesen Server zu aktivieren.
    
 **Director-server**
  
- DNS-der FQDN des neuen Servers gemäß Definition.
    
- Wählen Sie **Alle konfigurierte IP-Adressen verwenden**, was bedeutet, dass alle IP-Adressen auf dem Computer definierten verwendet wird. Alternativ wählen Sie die **Verwendung von Grenzwert ausgewählten IP-Adressen** und geben Sie eine bestimmte IP-Adresse auf dem neuen Server. IP-Adresse des ist die einzige IP-Adresse für gehostete Dienste reagieren soll.
    
 **Vermittlungsserver**
  
- DNS-der FQDN des neuen Servers gemäß Definition.
    
- Wählen Sie **Alle konfigurierte IP-Adressen verwenden**, was bedeutet, dass alle IP-Adressen auf dem Computer definierten verwendet werden kann. Alternativ wählen Sie **Service-Verwendung einschränken ausgewählten IP-Adressen** und geben eine bestimmte IP-Adresse auf dem neuen Server als primäre IP-Adresse und ein Geben Sie eine IP-Adresse public switched Telephone Network, (PSTN) IP-Adresse. Die IP-Adressen eingegeben werden die einzige IP-Adresse der für die festgelegten Dienste reagieren soll.
    
    > [!NOTE]
    > Für den Vermittlungsserver ist die IP-Adresse für die primäre IP-Adresse und die PSTN-IP-Adresse eingegeben standardmäßig identisch. Die IP-Adressen können separat definiert werden, wenn Sie auf der gleichen Netzwerkschnittstelle dedizierten Netzwerkschnittstellen oder separate IP-Adressen verwenden werden. Wenn Sie zwei Netzwerkschnittstellen, einen für die LAN-Verbindung und einen für die PSTN-Verbindung verfügen, müssen Sie unterschiedliche IP-Adressen zuweisen. 
  
 **A/v-Konferenzserver**
  
- DNS-der FQDN des neuen Servers gemäß Definition.
    
- Wählen Sie **Alle konfigurierte IP-Adressen verwenden**, was bedeutet, dass alle IP-Adressen auf dem Computer definierten verwendet werden kann. Alternativ können Sie **Service-Verwendung einschränken ausgewählten IP-Adressen** auswählen und geben Sie eine bestimmte Adresse auf dem neuen Server. IP-Adresse des ist die einzige IP-Adresse für gehostete Dienste reagieren soll.
    
 **Vertrauenswürdiger Anwendungsserver**
  
- DNS-der FQDN des neuen Servers gemäß Definition.
    

