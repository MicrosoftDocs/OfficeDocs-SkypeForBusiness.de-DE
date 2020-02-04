---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab30a2153dc7dbf5a15557f6eeaf3b6cb65f68f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-07-28_

Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Vermittlungs Server bereitzustellen.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>So stellen Sie IP-Adresstypen auf einem Vermittlungsserver bereit

  - Klicken Sie im Topologie-Generator unter **Vermittlungs Pools**mit der rechten Maustaste auf den Server in einem Pool, und wählen Sie dann **Eigenschaften bearbeiten**aus. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)

  - Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für eine Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.
    
    **Das Dialogfeld „Eigenschaften bearbeiten“ für den Vermittlungsserverpool**
    
    ![Seite "Allgemeine Eigenschaften" von lync Server mit FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Seite "Allgemeine Eigenschaften" von lync Server mit FQDN")
    
      - **Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.
        
        <div>
        

        > [!NOTE]  
        > Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.

        
        </div>
    
      - **Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für „Primäre IP-Adresse“ angeben.
    
      - **Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikationsvorgänge mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
    
      - **PSTN-IP-Adresse**. Definieren Sie eine PSTN-IP-Adresse, wenn ein Vermittlungs Server eigenständig ist. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
        
        <div>
        

        > [!NOTE]  
        > Die Installation zusätzlicher Netzwerkschnittstellenkarten (NIC) s zur Unterstützung der Konfiguration der PSTN-IP-Adresse für lync Server 2013 wird in den Serverrollen für festgestellten Vermittlungsserver nicht unterstützt. Weitere Informationen zu unterstützten NIC-Konfigurationen für lync Server 2013 finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardwareplattformen für lync Server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

