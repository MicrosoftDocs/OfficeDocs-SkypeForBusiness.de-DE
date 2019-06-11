---
title: 'Lync Server 2013: Bearbeiten des Entwurfs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 601c313231a26341c3c4cf8a4897d11872dec9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>Bearbeiten des Entwurfs in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Nach Beantwortung der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen der Website bearbeiten. Machen Sie hierzu auf der Seite **Globale Topologie** einen Doppelklick auf den Standort, den Sie bearbeiten möchten.

Das Planungs Tool zeigt die Standorttopologie für die ausgewählte Website an. Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:

![Standorttopologie des Planungstools] (images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Standorttopologie des Planungstools")

  - Standorttopologie - Die aktuell angezeigte Seite mit einer optischen Übersicht der empfohlenen Topologie.

  - Edge-Netzwerkdiagramm – auf der Seite "Edge-Netzwerkdiagramm" werden die meisten Aufgaben im Planungs Tool vom Designer ausgeführt. Das Diagramm zeigt die Netzwerkkonfiguration für eine empfohlene lync Server 2013-Topologie mit bearbeitbaren Einträgen für IP-Adressen und FQDNs für Server, Pool sowie Hardware-und DNS-Lastenausgleichssysteme (Domain Name System) an.

  - Edgeverwaltungsbericht - Der Edgeverwaltungsbericht umfasst insgesamt vier Berichte:
    
    ![Seite "Edge-Administrator Bericht] " (images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Seite \"Edge-Administrator Bericht") "  
    
      - Zusammenfassungsbericht – Ein allgemeiner Bericht zu den Einstellungen der Edgenetzwerkkonfiguration. Wenn Sie auf der Seite **Edge-Netzwerkdiagramm** die TCP-IP- und FQDN-Werte der Topologie in die der tatsächlichen Bereitstellung ändern, werden diese Adressen und Namen hier dargestellt. Andernfalls wird hier der Standardtext angezeigt.
    
      - Zertifikatbericht - Der Zertifikatbericht führt den Antragstellernamen und alternative Antragstellernamen für die Zertifikate auf, die für die Topologie benötigt werden.
    
      - Firewallbericht - Im Firewallbericht werden Informationen aufgeführt, die zum Konfigurieren von Umkreisfirewalls in der Infrastruktur benötigt werden. Diese umfassen die IP-Adressen (entweder die Standardwerte oder die bearbeiteten Werte), Serverrolle, Quell-IP und Port, Ziel-IP und Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.
    
      - DNS-Bericht - Im DNS-Bericht werden Informationen zu den DNS-Einträgen aufgeführt, die Sie erstellen müssen. Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.

  - Standortzusammenfassung – Die Standortzusammenfassung liefert einen Überblick über die Auswahl, die entweder bei den anfänglichen Fragen oder durch Angeben der Werte in **Websites entwerfen** getroffen wurde. Es werden auch Kapazitätsinformationen angezeigt.
    
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

