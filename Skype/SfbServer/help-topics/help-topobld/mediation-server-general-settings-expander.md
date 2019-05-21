---
title: Allgemeine Einstellungen des Vermittlungsservers – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 68ce332b0db24147121f66ed88725518abb2c464
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285694"
---
# <a name="mediation-server-general-settings-expander"></a>Allgemeine Einstellungen des Vermittlungsservers – Erweiterung
 


## <a name="general-settings"></a>Allgemeine Einstellungen

Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Vermittlungsserver Pools oder des Vermittlungsservers. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.
  
Im Abschnitt **Zuordnungen** wählen Sie einen Edgeserver oder Edgeserver-Pool aus, der dem vermittlungsserverpool oder Vermittlungsserver zugeordnet werden soll. Sie wählen den Edge aus, den die Medienkomponenten des Vermittlungsservers für externe Benutzer Enterprise-VoIP verwenden werden.
  
Wenn Sie noch keinen Edgeserver definiert haben und den Vermittlungsserver einem Edgeserver zuordnen müssen, klicken Sie auf **neu** , und definieren Sie im Assistenten zum Definieren des neuen Edge-Pools den neuen Edge-Server oder den Edge-Serverpool.
  
## <a name="next-hop-settings"></a>Einstellungen für nächsten Hop

Sie geben den vermittlungsserverpool oder den Vermittlungsserver nächsten Hop an, indem Sie den definierten Enterprise Edition-Front-End-Pool oder den Standard Edition-Front-End-Server aus der Dropdownliste auswählen. Ein Director-oder Director-Pool ist keine gültige Auswahl für einen vermittlungsserverpool oder Vermittlungsserver nächster Hop und wird nicht in der Liste angezeigt. Klicken Sie auf **OK** , um die Änderungen zu übernehmen und zu speichern. Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.
  
## <a name="pstn-gateway-settings"></a>Einstellungen für PSTN-Gateway

1. Sie definieren PSTN-Gateways, die dem vermittlungsserverpool oder Vermittlungsserver zugeordnet sind. Wenn Sie bereits Gateways definiert haben, stehen diese dem Vermittlungs Server zur Verfügung. Wenn Sie die Zusammenlegung des Vermittlungsservers aktivieren, definieren Sie den Überwachungs Portbereich auf den Pool Servern für TLS (Transport Layer Security). Standardmäßig ist dieser Port 5067. Wenn Sie **TCP-Port aktivieren**auswählen, müssen Sie einen TCP-Port (Transmission Control Protocol) für den beiliegenden Vermittlungs Server definieren. Hierbei handelt es sich um eine optionale Einstellung, und Sie sollten sich auf die Anforderungen Ihrer Gateway-oder PSTN-Anforderungen beziehen, um festzustellen, ob dies erforderlich ist. Standardmäßig ist der TCP-Port-Wert 5068.
    
2. Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung. 
    
3. Wenn einem Vermittlungs Server mehr als ein trunk zugeordnet ist, können Sie einen Standard trunk angeben, indem Sie den trunk auswählen und dann auf **Standard**festlegen klicken. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung eines Gateways als Standard aufzuheben. 
    

