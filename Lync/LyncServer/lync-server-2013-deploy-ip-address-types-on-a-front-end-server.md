---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Front-End-Server'
description: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Front-End-Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57d27cbc6ae23af1f15e28b19e1871c0aaf35dde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559791"
---
# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>Bereitstellen von IP-Adresstypen auf einem Front-End-Server für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-07-28_

Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Front-End-Server bereitzustellen.

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>So stellen Sie IP-Adressentypen auf einem Front-End-Server bereit

1.  Klicken Sie unter **Enterprise Edition-Front-End-Pools** mit der rechten Maustaste auf den Server in einem Pool und wählen Sie anschließend **Eigenschaften bearbeiten**. (Wählen Sie alternativ den Server und klicken Sie auf **Eigenschaften bearbeiten** im Menü **Aktion**.)

2.  Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.
    
    **Dialogfeld "Eigenschaften bearbeiten" für den Front-End-Server-Pool**
    
    ![Front-End-Server Dialogfeld ' Eigenschaften bearbeiten '](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front-End-Server Dialogfeld ' Eigenschaften bearbeiten '")
    
      - **Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.
        
        <div>
        

        > [!NOTE]  
        > Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.

        
        </div>
    
      - **Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für **Primäre IP-Adresse** angeben.
    
      - **Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikation mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.
    
      - **PSTN-IP-Adresse**. Die Installation zusätzlicher Netzwerkschnittstellenkarten (NIC) s zur Unterstützung der Konfiguration von PSTN-IP-Adressen für lync Server 2013 wird für zusammengefasste Vermittlungsserver Rollen nicht unterstützt. Weitere Informationen zu unterstützten NIC-Konfigurationen für lync Server 2013 finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

