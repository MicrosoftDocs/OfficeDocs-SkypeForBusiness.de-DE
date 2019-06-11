---
title: 'Lync Server 2013: Definieren des Bereichs der E9-1-1-Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff32a71ec9b724bad9efee68784d284a71b8f385
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Definieren des Bereichs der E9-1-1-Bereitstellung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

Bevor Sie Microsoft lync Server 2013 für E9-1-1 konfigurieren, müssen Sie Ihre E9-1-1-Bereitstellung planen. Stellen Sie sich die folgenden Fragen:

  - **Worin bestehen die Richtlinien und Vorschriften in Ihrer Organisation im Hinblick auf E9-1-1?**  
    Die gesetzlichen E9-1-1-Anforderungen für Nebenstellenanlagen (im E9-1-1-Jargon als „Telefonsysteme mit mehreren Leitungen“ oder „Mehrleitungstelefonsysteme“ bezeichnet) unterscheiden sich von Staat zu Staat. Wenden Sie sich an Ihr Rechtsteam, um sich mit den Verpflichtungen vertraut zu machen, die möglicherweise für Ihre Bereitstellung von lync Server in ihren relevanten Regionen gelten.

<!-- end list -->

  - **Welche Bereiche innerhalb Ihres Unternehmens müssen für E9-1-1 aktiviert werden?**  
    Sie können E9-1-1 innerhalb des gesamten Unternehmens oder für ausgewählte Standorte aktivieren. Beispielsweise können für Büros in verschiedenen Staaten unterschiedliche E9-1-1-Anforderungen gelten und Standorte außerhalb der USA können ausgeschlossen werden.

<!-- end list -->

  - **Wie möchten Sie E9-1-1-Zweigstellen bereitstellen?**  
    Sie müssen mit dem Konzept der VoIP-Ausfallsicherheit für Zweigstellenstandorte vertraut sein, wenn Sie E9-1-1 in einer Zweigstelle bereitstellen. Wenn Sie über zentralisierte E-9-1-1-SIP-Trunks verfügen und ein WAN-Ausfall auftritt, können Clients, die sich anmelden, möglicherweise keinen Standort vom standortinformationsdienst abrufen oder eine Verbindung mit dem Notdienste-Dienstanbieter herstellen. Lync Server bietet verschiedene Strategien für die Behandlung von VoIP-Flexibilität in Zweigniederlassungen, einschließlich: mit belastbaren Datennetzwerken, Bereitstellungeines SIP-Trunks an jeder Verzweigung oder durch Drücken von Notrufen beim Ausfall des lokalen Gateways. Ausführliche Informationen finden Sie unter [Planen der sprach Sicherheit in der Zweigstelle in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **Planen Sie die Aktivierung von E9-1-1 für Benutzer außerhalb des Netzwerks?**  
    Die automatische Standorterfassung steht nur für Clients zur Verfügung, die sich im Netzwerk der Organisation befinden, sodass Ihre Organisation entscheiden muss, ob Sie E9-1-1-Anrufe unterstützt, die von lync-Clients außerhalb des Lokals getätigt werden. Möchten Sie beispielsweise Benutzern die Möglichkeit geben, Notrufe zu tätigen, wenn Sie von zu Hause oder von einem Kundenstandort aus arbeiten? Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet, kann der Client so konfiguriert werden, dass er den Benutzer zur Eingabe eines Speicherorts auffordert. Da diese vom Benutzer bereitgestellten Speicherorte jedoch nicht mit dem Master Street Address Guide (MSAG) vorab validiert werden können, muss der Dienstanbieter für Notrufdienste die Gültigkeit des Standorts mit dem Anrufer vor dem Routing bestätigen. der Anruf an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP).
    
    <div>
    

    > [!NOTE]  
    > Lync-Clients von Benutzern, die mit VPN eine Verbindung mit dem Netzwerk Ihrer Organisation herstellen, können interne IP-Adressinformationen aufnehmen, doch da diese Adressen nicht zur Identifizierung des tatsächlichen Standorts des Benutzers verwendet werden können, ist es wichtig, dass VPN-Subnetze von der Standortinformationsdienst

    
    </div>

<!-- end list -->

  - **Möchten Sie eine Weiterleitung von Notrufen an Standorte außerhalb der USA bereitstellen?**  
    Eine Notrufweiterleitung kann beispielsweise für Unternehmensbereiche bereitgestellt werden, für die kein Anbieter einer Notrufunterstützung zur Verfügung steht (beispielsweise an internationalen Standorten). Erstellen Sie hierzu einen neuen Standort, und weisen Sie den Standorten, die auf eine PSTN-Verwendung verweisen, bei der der Anruf durch das lokale Gateway weitergeleitet wird, VoIP-Richtlinien zu.

</div>

<span> </span>

</div>

</div>

</div>

