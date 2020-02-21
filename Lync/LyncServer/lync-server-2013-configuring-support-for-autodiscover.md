---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für die AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bbb9007562dfecdc4f38b6cf8ac3f1579094ed6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Konfigurieren der Unterstützung für die AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-21_

Der **AutoErmittlungsdienst** für lync Server-Webdienste erschien zunächst im lync Server 2010 kumulativen Update: November 2011. Dieses Update wurde von der ersten Version von lync Mobile-Clients begleitet. Der AutoErmittlungsdienst hat die Mobilitätsdienste verfügbar gemacht, die als MCX-Dienst bezeichnet werden.

Der AutoErmittlungsdienst fungiert als ein einzelner Standort für alle Clients, um Informationen darüber anzufordern, welche Dienste und Features verfügbar sind, und wie Sie mit den Vermittlern Kontakt aufnehmen können – entweder durch einen vollqualifizierten Domänennamen oder eine webuniform Resource Locator-Referenz. Die AutoErmittlung macht eine Reihe von Features verfügbar, und jeder Client stellt Anforderungen basierend auf den Features, die der Client verwenden kann, zur Verfügung. Beispielsweise verwendet ein Desktop lync 2013-Client autodiscvoer, um die externen Webdienste zu ermitteln, verwendet jedoch nicht die Mobilitätsdienste (MCX). Um Ihre Clients ordnungsgemäß zu definieren und zu aktivieren, um die verfügbaren Features zu verwenden, sollten die Szenarien definiert werden, die es einem Client ermöglichen, Auto Ermittlungs Einträge effektiv zu finden und zu verwenden. Für die Verwendung von autodoscover erfordert die Bereitstellung, dass ein Reverseproxy die lync Server-Webdienste veröffentlicht, dass DNS-Einträge so konfiguriert sind, dass DNS-Abfragen für den lync Server AutoErmittlungsdienst und lync Server Webdienste aufgelöst werden und dass die Zertifikatdienste für Ihr spezifisches Szenario ordnungsgemäß konfiguriert sind.

<div>


> [!TIP]  
> Technische Details zu den Elementen in der Anforderung/Antwort der AutoErmittlung finden Sie unter <A href="lync-server-2013-understanding-autodiscover.md">Understanding AutoErmittlung in lync Server 2013</A>.



</div>

Die folgenden Informationen und Tabellen definieren pro Szenario, welche Konfigurationen (falls vorhanden) Sie implementieren müssen, um die vollständige und effektive Verwendung des AutoErmittlungsdiensts bereitzustellen. Die Informationen in den folgenden Themen sind spezifisch für Microsoft lync Server 2013. Informationen zum Planen der Mobilität für lync Server 2010 finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113). Informationen zum Bereitstellen von Mobilität für lync Server 2010 finden Sie unter[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von DNS für die AutoErmittlung in lync Server 2013](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Konfigurieren von Zertifikaten für die AutoErmittlung in lync Server 2013](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Konfigurieren eines Reverse-Proxys für die AutoErmittlung in lync Server 2013](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Konfigurieren der AutoErmittlung in lync Server 2013 für hybridbereitstellungen](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

