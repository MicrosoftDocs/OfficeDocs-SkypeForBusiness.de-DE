---
title: 'Lync Server 2013: Konfigurieren von Webfarm-FQDNs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Konfigurieren von Webfarm-FQDNs für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-29_

Wenn Sie die Konfiguration des Standard Edition-Servers, des Front-End-Pools, des Director-oder Director-Pools in Topology Builder definiert haben, konfigurieren Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für externe Webdienste. Während des Anmeldeprozesses eines Clients, der sich im Standard Edition-Server oder-Front-End-Pool befindet, werden die konfigurierten Webdienste-FQDNs über die in-Band-Bereitstellung gesendet. Wenn Sie die externe Webdienste-URL hinzufügen oder ändern müssen, verwenden Sie den Topologie-Generator, um die Webdienstkonfiguration mithilfe des in diesem Thema beschriebenen Verfahrens zu konfigurieren oder neu zu konfigurieren.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>So konfigurieren Sie einen externen Pool-FQDN für Webdienste

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Klicken Sie im Topologie-Generator in der Konsolenstruktur unter **Front Ends der Standard Edition**, **Enterprise Edition-Front-Ends**und **Directors**mit der rechten Maustaste auf den Namen des Pools, den Sie bearbeiten möchten, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Fügen Sie im Abschnitt **Webdienst** den **FQDN externer Webdienste**hinzu, oder bearbeiten Sie ihn.

4.  Überprüfen und Anpassen der **Abhör Anschlüsse** für http und HTTPS Die Standardeinstellungen lauten wie folgt:
    
      - **Abhör Anschlüsse:** HTTP 8080, HTTPS 4443
    
      - **Veröffentlichte Ports:** HTTP 80, HTTPS 443
    
    Hierbei handelt **es sich um den Port** , in dem die externen Webdienste so konfiguriert werden, dass Sie Anforderungen vom Reverseproxy empfangen, und die **veröffentlichten** Ports sind die Ports, die extern vom Reverse-Proxy veröffentlicht werden und während der in-Band-Bereitstellung an Clients mitgeteilt werden.

5.  Wenn Sie Ihre Ergänzungen und Updates abgeschlossen haben, klicken Sie auf **OK** , um den Vorgang fortzusetzen.

6.  Klicken Sie mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **veröffentlichen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Nachdem die Veröffentlichung erfolgreich abgeschlossen wurde, wird möglicherweise ein Link angezeigt, der Sie darüber informiert, dass weitere Schritte ausgeführt werden müssen. Wenn Sie auf den Link klicken, wird eine Liste der Server geöffnet, die von den im Topologie-Generator vorgenommenen Änderungen betroffen sind, die erfordern, dass Sie den lync Server-Bereitstellungs-Assistenten auf jedem aufgelisteten Server erneut ausführen, um die Konfiguration für hinzugefügte, entfernte oder geänderte Komponenten zu aktualisieren.

    
    </div>

7.  Wiederholen Sie diese Schritte für jeden Standard Edition-Server, Front-End-Pool, Director-oder Director-Pool in der Organisation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

