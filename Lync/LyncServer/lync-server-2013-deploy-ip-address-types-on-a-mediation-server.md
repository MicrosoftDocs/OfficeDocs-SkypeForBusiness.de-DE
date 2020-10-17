---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver'
description: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver.'
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
ms.openlocfilehash: daa3be8d1ef12629dc185f98b95d2db0e565cf18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559781"
---
# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-07-28_

Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Vermittlungsserver bereitzustellen.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>So stellen Sie IP-Adresstypen auf einem Vermittlungsserver bereit

  - Klicken Sie im Topologie-Generator unter **Vermittlungs Pools**mit der rechten Maustaste auf den Server in einem Pool, und wählen Sie dann **Eigenschaften bearbeiten**aus. (Wählen Sie alternativ den Server und klicken Sie auf **Eigenschaften bearbeiten** im Menü **Aktion**.)

  - Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.
    
    **Das Dialogfeld "Eigenschaften bearbeiten" für den Vermittlungsserverpool**
    
    ![Lync Server allgemeine Eigenschaftenseite mit FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server allgemeine Eigenschaftenseite mit FQDN")
    
      - **Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.
        
        <div>
        

        > [!NOTE]  
        > Für IPv6-Konfigurationen wird diese Option empfohlen.

        
        </div>
    
      - **Dienstnutzung auf ausgewählte IP-Adressen beschränken**. Aktivieren Sie diese Option, um eine bestimmte IP-Adresse anzugeben, die auf dem neuen Server verwendet werden soll. Bei Auswahl dieser Option müssen Sie einen Wert für die "Primäre IP-Adresse" angeben.
    
      - **Primäre IP-Adresse**. Geben Sie eine IP-Adresse ein, die der Server bei allen Kommunikationsvorgängen außer beim Telefonfestnetz (PSTN) verwenden soll. Die hier eingegebene IP-Adresse muss in dem Format des ausgewählten Adresstyps stehen.
    
      - **PSTN-IP-Adresse**. Definieren Sie eine PSTN-IP-Adresse, wenn ein Vermittlungsserver eigenständig ist. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
        
        <div>
        

        > [!NOTE]  
        > Die Installation zusätzlicher Netzwerkschnittstellenkarten (NIC) s zur Unterstützung der Konfiguration von PSTN-IP-Adressen für lync Server 2013 wird für zusammengefasste Vermittlungsserver Rollen nicht unterstützt. Weitere Informationen zu unterstützten NIC-Konfigurationen für lync Server 2013 finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for lync Server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

