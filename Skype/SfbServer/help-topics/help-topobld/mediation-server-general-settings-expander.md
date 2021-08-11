---
title: Allgemeine Einstellungen des Vermittlungsservers – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 9ad2517641a4a7bbfe0d353497331ef8fade52c24099cc770477530dc6021b99
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283407"
---
# <a name="mediation-server-general-settings-expander"></a>Allgemeine Einstellungen des Vermittlungsservers – Erweiterung
 


## <a name="general-settings"></a>Allgemeine Einstellungen

Vollqualifizierter Domänenname (FQDN) des Vermittlungsserverpools oder Vermittlungsservers. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.
  
Im Abschnitt **Zuordnungen** wählen Sie einen Edgeserver oder Edgeserverpool aus, der dem Vermittlungsserverpool oder Vermittlungsserver zugeordnet werden soll. Sie wählen den Edgeserver aus, den die Medienkomponenten des Vermittlungsservers für externe Benutzer Enterprise-VoIP verwenden.
  
Wenn gegenwärtig kein Edgeserver definiert ist und der Vermittlungsserver einem Edgeserver zugeordnet werden muss, klicken Sie auf **Neu**, und definieren Sie den neuen Edgeserver oder Edgeserverpool im Assistenten zum Definieren des neuen Edgeserverpools.
  
## <a name="next-hop-settings"></a>Einstellungen für nächsten Hop

Zum Angeben des nächsten Hops eines Vermittlungsserverpools oder Vermittlungsservers wählen Sie den definierten Front-End-Pool der Enterprise Edition oder den Front-End-Server der Standard Edition aus der Dropdownliste aus. Ein Director oder Director-Pool kann nicht als nächster Hop für einen Vermittlungsserverpool oder Vermittlungsserver ausgewählt werden und wird daher nicht in der Liste aufgeführt. Klicken Sie auf **"OK",** um die Änderungen zu akzeptieren und zu speichern. Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.
  
## <a name="pstn-gateway-settings"></a>Einstellungen für PSTN-Gateway

1. Sie definieren PSTN-Gateways, die dem Vermittlungsserverpool oder Vermittlungsserver zugeordnet werden. Wenn bereits Gateways definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung. Wenn Sie die Kollokation des Vermittlungsservers aktivieren, müssen Sie den Überwachungsport der Poolserver für Transport Layer Security (TLS) festlegen. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den verbundenen Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.
    
2. Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung. 
    
3. Falls einem Vermittlungsserver mehr als ein Trunk zugeordnet ist, können Sie einen Trunk als Standard angeben, indem Sie den Trunk auswählen und auf **Als Standardeinstellung festlegen** klicken. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben. 
    

