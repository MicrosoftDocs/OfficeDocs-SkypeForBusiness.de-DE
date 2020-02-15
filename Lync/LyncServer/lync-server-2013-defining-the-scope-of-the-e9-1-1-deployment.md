---
title: 'Lync Server 2013: Definieren des Bereichs der E9-1-1-Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be9dee7f4e79492e62e04441b6fa56d4e04ff45a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Definieren des Bereichs der E9-1-1-Bereitstellung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-06_

Bevor Sie Microsoft lync Server 2013 für E9-1-1 konfigurieren, müssen Sie die E9-1-1-Bereitstellung planen. Stellen Sie sich die folgenden Fragen:

  - **Worin bestehen die Richtlinien und Vorschriften in Ihrer Organisation im Hinblick auf E9-1-1?**  
    Die gesetzlichen E9-1-1-Anforderungen für Nebenstellenanlagen (im E9-1-1-Jargon als "Telefonsysteme mit mehreren Leitungen" oder "Mehrleitungstelefonsystemen" bezeichnet) unterscheiden sich von Staat zu Staat. Sie sollten sich mit Ihrem Rechtsteam in Kenntnis setzen, um die Verpflichtungen zu verstehen, die für Ihre Bereitstellung von lync Server in ihren relevanten Regionen gelten können.

<!-- end list -->

  - **Welche Bereiche innerhalb Ihres Unternehmens müssen für E9-1-1 aktiviert werden?**  
    Sie können E9-1-1 innerhalb des gesamten Unternehmens oder für ausgewählte Standorte aktivieren. Beispielsweise können für Büros in verschiedenen Staaten unterschiedliche E9-1-1-Anforderungen gelten, und Standorte außerhalb der USA können ausgeschlossen werden.

<!-- end list -->

  - **Wie möchten Sie E9-1-1-Zweigstellen bereitstellen?**  
    Sie müssen mit dem Konzept der VoIP-Ausfallsicherheit für Zweigstellenstandorte vertraut sein, wenn Sie E9-1-1 in einer Zweigstelle bereitstellen. Wenn Sie über zentralisierte E-9-1-1-SIP-Trunks verfügen und ein WAN-Ausfall auftritt, können Clients, die sich anmelden, möglicherweise keinen Standort aus Standortinformationsdienst abrufen oder eine Verbindung mit dem Dienstanbieter für Notdienste herstellen. Lync Server bietet verschiedene Strategien für die Handhabung von VoIP-Ausfallsicherheit in Zweigstellen, darunter: belastbare Datennetzwerke, Bereitstellungeines SIP-Trunks in jeder Filiale oder Pushen von Notrufen beim Ausfall des lokalen Gateways. Ausführliche Informationen finden Sie unter [Planning for Branch-Site Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **Planen Sie die Aktivierung von E9-1-1 für Benutzer außerhalb des Netzwerks?**  
    Eine automatische Standorterkennung ist nur für Clients verfügbar, die sich innerhalb des Netzwerks der Organisation befinden. Ihre Organisation muss daher entscheiden, ob E9-1-1-Anrufe von Lync-Clients, die sich nicht vor Ort befinden, unterstützt werden sollen. Möchten Sie es Benutzern beispielsweise ermöglichen, Notrufe zu tätigen, wenn sie von zu Hause aus oder bei einem Kunden arbeiten? Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet, kann der Client den Benutzer zur Angabe eines Standorts auffordern. Da diese von den Benutzern angegebenen Standorte jedoch nicht vorab mit der MSAG (Master Street Address Guide)-Datenbank abgeglichen werden können, muss eine verantwortliche Person beim Anbieter für die Notrufunterstützung die Gültigkeit des Standorts in einem Gespräch mit dem Anrufer überprüfen, bevor der Anruf an die Rettungsleitstelle weitergeleitet wird.
    
    <div>
    

    > [!NOTE]  
    > Lync-Clients von Benutzern, die über VPN eine Verbindung mit dem Netzwerk Ihrer Organisation herstellen, können interne IP-Adressinformationen abholen, aber da diese Adressen nicht zum Identifizieren des tatsächlichen Standorts des Benutzers verwendet werden können, ist es wichtig, dass VPN-Subnetze aus dem ausgeschlossen werden. Standortinformationsdienst.

    
    </div>

<!-- end list -->

  - **Möchten Sie eine Weiterleitung von Notrufen an Standorte außerhalb der USA bereitstellen?**  
    Eine Notrufweiterleitung kann beispielsweise für Unternehmensbereiche bereitgestellt werden, für die kein Anbieter für die Notrufunterstützung zur Verfügung steht (beispielsweise an internationalen Standorten). Erstellen Sie hierzu einen neuen Standort, und weisen Sie den Standorten VoIP-Richtlinien zu, die auf eine PSTN-Verwendung verweisen, bei der der Anruf durch das lokale Gateway weitergeleitet wird.

</div>

<span> </span>

</div>

</div>

</div>

