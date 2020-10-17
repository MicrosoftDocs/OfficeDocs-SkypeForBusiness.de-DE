---
title: 'Lync Server 2013: Bearbeiten des Entwurfs'
description: 'Lync Server 2013: Bearbeiten des Designs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20462c1c1813551159e8eeb3b255bd9069e3cce1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570621"
---
# <a name="editing-the-design-in-lync-server-2013"></a>Bearbeiten des Entwurfs in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Nach Abschluss der ersten Interview Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen für die Website bearbeiten. Doppelklicken Sie hierzu auf der Seite **Globale Topologie** auf den Standort, den Sie bearbeiten möchten.

Das Planungs Tool zeigt die Standorttopologie für den ausgewählten Standort an. Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:

![Planungs Tool-Standorttopologie](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planungs Tool-Standorttopologie")

  - Standorttopologie – Die aktuell angezeigte Seite mit einer optischen Übersicht der empfohlenen Topologie.

  - Edge-Netzwerkdiagramm – die Seite "Netzplandiagramm für Edge" ist der Ort, an dem der Designer den Großteil der Arbeit im Planungs Tool ausführt. Das Diagramm zeigt die Netzwerkkonfiguration für eine empfohlene lync Server 2013 Topologie mit editierbaren Einträgen für IP-Adressen und FQDNs für Server, Pools und sowohl Hardware-als auch Domain Name System (DNS) Lastenausgleich an.

  - Edgeverwaltungsbericht – Der Edgeverwaltungsbericht umfasst insgesamt vier Berichte:
    
    ![Seite "Edge-Administrator Bericht"](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Seite "Edge-Administrator Bericht"")  
    
      - Zusammenfassungsbericht – Ein allgemeiner Bericht zu den Einstellungen der Edgenetzwerkkonfiguration. Wenn Sie die Werte auf der Seite **Netzwerkdiagramm für Edge** mit der Topologie TCP/IP und FQDN von, die in der eigentlichen Bereitstellung verwendet werden, bearbeiten, werden diese Adressen und Namen hier dargestellt. Andernfalls wird der Standardtext angezeigt.
    
      - Zertifikatbericht – Der Zertifikatbericht führt den Antragstellernamen und alternative Antragstellernamen für die Zertifikate auf, die für die Topologie benötigt werden.
    
      - Firewallbericht – Im Firewallbericht werden Informationen aufgeführt, die zum Konfigurieren von Umkreisfirewalls in der Infrastruktur benötigt werden. Dies umfasst die IP-Adressen (entweder die Standardwerte oder bearbeiteten Werte), Serverrolle, Quell-IP und Port, Ziel-IP und Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.
    
      - DNS-Bericht – der DNS-Bericht enthält relevante Informationen zu den DNS-Einträgen, die Sie erstellen müssen. Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.

  - Website Zusammenfassung – die Website Zusammenfassung enthält eine Übersicht über die Auswahl, die Sie entweder bei der Beantwortung der anfänglichen Interview Fragen oder beim Ausfüllen der Werte in **Design Websites**getroffen haben. Kapazitätsinformationen werden ebenfalls angezeigt.
    
    <div>
    

    > [!NOTE]  
    > Die Informationen auf der Seite mit der Standortzusammenfassung sind auf den jeweiligen Entwurf zugeschnitten und enthält möglicherweise nicht alle Abschnitte oder Informationen, die hier besprochen werden.

    
    </div>

<div>

## <a name="see-also"></a>Siehe auch


[Bearbeiten des Netzwerk Konfigurations Diagramms in lync Server 2013](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

