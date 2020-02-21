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
ms.openlocfilehash: 46cca998a35a7519675cd787f5887f2a65d491c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Konfigurieren von Webfarm-FQDNs für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-29_

Wenn Sie die Konfiguration der Standard Edition-Server, Front-End-Pool, Director oder Directorpool im Topologie-Generator definiert haben, konfigurieren Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für externe Webdienste. Während des Anmeldeprozesses eines Clients, der in der Standard Edition-Server oder Front-End-Pool verwaltet wird, werden die konfigurierten FQDNs der Webdienste über die in-Band-Bereitstellung gesendet. Wenn Sie die URL für externe Webdienste hinzufügen oder ändern müssen, verwenden Sie den Topologie-Generator, um die Webdienstkonfiguration mit dem Verfahren in diesem Thema zu konfigurieren oder neu zu konfigurieren.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>So konfigurieren Sie einen externen Pool-FQDN für Webdienste

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Klicken Sie im Topologie-Generator in der Konsolenstruktur unter **Standard Edition-Front-End**, **Enterprise Edition-Front-End**und **Directors**mit der rechten Maustaste auf den Namen des Pools, den Sie bearbeiten möchten, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Fügen Sie im Abschnitt **Webdienste** den **externen Webdienste-FQDN**hinzu, oder bearbeiten Sie ihn.

4.  Überprüfen und Anpassen der **Überwachungs Ports** für http und HTTPS. Die Standardeinstellungen sind:
    
      - **Abhör-Ports:** HTTP 8080, HTTPS 4443
    
      - **Veröffentlichte Ports:** HTTP 80, HTTPS 443
    
    Dabei handelt es sich bei den **abhörenden Ports** um den Port, für den die externen Webdienste für den Empfang von Anforderungen vom Reverseproxy konfiguriert werden, und die **veröffentlichten** Ports sind die Ports, die extern vom Reverseproxy veröffentlicht werden und den Clients während der in-Band-Bereitstellung mitgeteilt werden.

5.  Wenn Sie Ihre Ergänzungen und Updates abgeschlossen haben, klicken Sie auf **OK** , um den Vorgang fortzusetzen.

6.  Klicken Sie mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **veröffentlichen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Nachdem die Veröffentlichung erfolgreich abgeschlossen wurde, wird möglicherweise ein Link angezeigt, in dem Sie darüber informiert werden, dass zusätzliche Schritte ausgeführt werden müssen. Wenn Sie auf den Link klicken, wird eine Liste der Server geöffnet, die von den im Topologie-Generator vorgenommenen Änderungen betroffen sind, sodass Sie den lync Server-Bereitstellungs-Assistenten auf jedem aufgelisteten Server erneut ausführen müssen, um die Konfiguration für hinzugefügte, entfernte oder geänderte Komponenten zu aktualisieren.

    
    </div>

7.  Wiederholen Sie diese Schritte für jeden Standard Edition-Server, Front-End-Pool, Director oder Directorpool in der Organisation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

