---
title: Konfigurieren von IP-Adresstypen in Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Zusammenfassung: Überprüfen der Faktoren für den IP-Adresse unter vor der Implementierung von Skype für Business Server 2015.'
ms.openlocfilehash: adebab15a0c10310b25af30f6e933625df61dc3d
ms.sourcegitcommit: a612ebe25e06c2cb090f776325712caf3cf3b943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2018
ms.locfileid: "19630147"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Konfigurieren von IP-Adresstypen in Skype for Business
 
**Zusammenfassung:** Überprüfen Sie vor der Implementierung von Skype für Business Server 2015 Faktoren für die IP-Adresse unten.
  
Sie stellen IP-Adresstypen mithilfe des Topologie-Einstellungen, die Sie im Topologie-Generator konfigurieren bereit. In diesem Abschnitt wird beschrieben, wie IP-Adresstypen auf Front-End-Servern und Vermittlungsservern Edge-Server bereitstellen.
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Bereitstellen von IP-Adresstypen auf einem Front-End-Server

Führen Sie Topologie-Generator verwenden, die Schritte in das folgende Verfahren zum Bereitstellen von IP-Adresstypen auf einem Front-End-Server.
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>So stellen Sie IP-Adressentypen auf einem Front-End-Server bereit

1. Klicken Sie unter **Enterprise Edition-Front-End-Pools** mit der rechten Maustaste auf den Server in einem Pool und wählen Sie anschließend **Eigenschaften bearbeiten**. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)
    
2. Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für eine Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.
    
   **Bearbeiten Sie im Dialogfeld Eigenschaften für den Front-End-Server-pool**

  - **Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird. 
    
    > [!NOTE]
    > Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen. 
  
  - **Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für **Primäre IP-Adresse** angeben.
    
  - **Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikationsvorgänge mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
    
  - **PSTN-IP-Adresse**. Geben Sie eine PSTN-IP-Adresse an, wenn auf dem Front-End-Server ein Vermittlungsserver angeordnet wird. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
    
    > [!NOTE]
    > Die Installation von zusätzlichen Netzwerkschnittstellenkarten (NICs) zur Unterstützung von PSTN-IP-Adresskonfiguration auf Front-End-Servern wird nicht unterstützt. Weitere Informationen zu unterstützten NIC-Konfigurationen für Skype für Business Server finden Sie unter [Server Hardware Platforms für Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver

Führen Sie Topologie-Generator verwenden, die Schritte in das folgende Verfahren zum Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver.
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>So stellen Sie IP-Adresstypen auf einem Vermittlungsserver bereit

- Klicken Sie im Topologie-Generator unter **vermittlungspools**mit der rechten Maustaste des Servers in einem Pool, und wählen Sie dann auf **Eigenschaften bearbeiten**. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)
    
- Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für eine Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.
    
   **Bearbeiten Sie im Dialogfeld Eigenschaften für den vermittlungsserverpool**

  - **Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird. 
    
    > [!NOTE]
    > Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen. 
  
  - **Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für „Primäre IP-Adresse“ angeben.
    
  - **Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikationsvorgänge mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
    
  - **PSTN-IP-Adresse**. Geben Sie eine PSTN-IP-Adresse an, wenn auf dem Front-End-Server ein Vermittlungsserver angeordnet wird. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
    
    > [!NOTE]
    > Die Installation von zusätzlichen Netzwerkschnittstellenkarten (NICs) zur Unterstützung der Konfiguration der PSTN-IP-Adresse in den eigenständigen Vermittlungsserver wird nicht unterstützt. Weitere Informationen zu unterstützten NIC-Konfigurationen für Skype für Business Server finden Sie unter [Server Hardware Platforms für Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). 
  
## <a name="deploy-ip-address-types-on-an-edge-server"></a>Bereitstellen von IP-Adresstypen auf einem Edgeserver

Führen Sie Topologie-Generator verwenden, die folgenden Schritte aus:
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>So stellen Sie IP-Adresstypen auf dem Edgeserver bereit

1. Im Topologie-Generator unter **edgepools**mit der rechten Maustaste des Servers in einem Pool, und wählen Sie dann auf **Eigenschaften bearbeiten**. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)
    
2. Wählen Sie im Fenster **Eigenschaften bearbeiten** die IP-Adresskonfiguration, die Sie unterstützen möchten.    

3. Für jeden Adresstyp, den Sie auswählen, müssen Sie die geeigneten internen und externen Adressen auswählen.
    