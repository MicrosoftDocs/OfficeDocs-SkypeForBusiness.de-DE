---
title: Allgemeine Einstellungen des Vermittlungsservers – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 27a93cb0894f7791b689e4b8fcc3246ab6d9415d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979749"
---
# <a name="mediation-server-general-settings-expander"></a>Allgemeine Einstellungen des Vermittlungsservers – Erweiterung
 


## <a name="general-settings"></a>Allgemeine Einstellungen

Vollqualifizierter Domänenname (FQDN) des vermittlungsserverpool oder Vermittlungsserver. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.
  
Klicken Sie im Abschnitt **Zuordnungen** wählen Sie ein Edge-Server oder Pool für Edge-Server den vermittlungsserverpool oder Vermittlungsserver zuzuordnen. Sie wählen Sie die Kante, die der Vermittlungsserver Media-Komponenten für externe Benutzer Enterprise-VoIP verwendet werden soll.
  
Wenn Sie keine definiert einen Edge-Server zurzeit und Zuordnen des Vermittlungsservers mit einem Edge-Server, klicken Sie auf **neu** , und definieren den neuen Edge-Server oder Edge-Server-Pool definieren des Assistenten zum neuen Edge-Pools müssen.
  
## <a name="next-hop-settings"></a>Einstellungen für nächsten Hop

Sie geben Sie den vermittlungsserverpool oder Vermittlungsserver Nächster Hop, indem Sie den definierten Enterprise Edition-Front-End-Pool oder Standard Edition-Front-End-Server aus der Dropdown-Liste auswählen. Ein Director oder Director Pool ist keine gültige Auswahl für einen vermittlungsserverpool oder Vermittlungsserver Nächster Hop und nicht in der Liste angezeigt wird. Klicken Sie auf **OK** , um zu akzeptieren und Ihre Änderungen zu speichern. Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.
  
## <a name="pstn-gateway-settings"></a>Einstellungen für PSTN-Gateway

1. Definieren Sie PSTN-Gateways, die den vermittlungsserverpool oder Vermittlungsserver zugeordnet sind. Wenn Sie bereits Gateways definiert haben, werden sie zur Verfügung, die der Vermittlungsserver zugeordnet. Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktivieren, definieren Sie die überwachungsportbereich auf den Pool-Servern für Transport Layer Security (TLS). Standardmäßig ist dieser Port 5067. Wenn Sie **Aktivieren TCP-Port**auswählen, müssen Sie einen Port (TCP = Transmission Control Protocol) für den verbundenen Vermittlungsserver definieren. Dies ist eine optionale Einstellung, und verweisen Sie auf die Anforderungen Ihres Gateways oder PSTN-Anforderungen zu ermitteln, ob dies notwendig ist. Standardmäßig ist der Wert des TCP-Ports 5068.
    
2. Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung. 
    
3. Wenn Sie mehrere Trunks einen Vermittlungsserver zugeordnet haben, können Sie einen Standard-Trunk angeben, indem dem Trunk auswählen und dann auf **Als Standard**. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung eines Gateways als Standard aufzuheben. 
    

