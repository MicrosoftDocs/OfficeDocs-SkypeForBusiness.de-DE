---
title: 'Lync Server 2013: Topologien für IP-Telefone'
description: 'Lync Server 2013: Topologien für IP-Telefone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a151a83a69e1f7e14dcbed8d8ab1038157fa839
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549131"
---
# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologien für IP-Telefone in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-21_

In diesem Abschnitt erhalten Sie einen Überblick über den Prozess der Verbindungsherstellung. Erklärt werden außerdem die Unterschiede zwischen dem Herstellen einer Verbindung über ein IP-Telefon in einem internen Netzwerk und dem gleichen Vorgang in einem externen Netzwerk.

<div>


> [!NOTE]  
> Lync Server bietet Unterstützung für die folgenden IP-Telefone: das Mobiltelefon Aastra 6721ip, das Aastra 6725ip-Telefon, das HP 4110-IP-Telefon (Telefon im öffentlichen Bereich), das HP 4120-IP-Telefon (Schreibtisch Telefon), das IP-Telefon mit Polycom-Konsole, das IP-Telefon mit Polycom CX500 und das Polycom IP-Konferenztelefon von Polycom CX3000. Von diesen Telefonen können alle außer dem Polycom CX700 lync Phone Edition ausführen.



</div>

Im folgenden Diagramm werden alle Komponenten beschrieben, die an der Geräteanbindung innerhalb einer Unternehmensumgebung beteiligt sind.

**Interne Topologie**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> Die obige Abbildung ist eine logische Darstellung und keine physische. Beispielsweise befindet sich Active Directory-Domänendienste (AD DS) selten auf demselben Computer wie alle lync Server-Komponenten. Der Benutzerspeicher kann sich auf dem Back-End-Server oder auf den Archivierungs- und Monitoring Servern befinden. Die lync Server-Verwaltungsshell-, Webserver-und Updatedienste sind Teil der Front-End-Server Rolle.



</div>

Das folgende Diagramm zeigt einen Überblick über die Komponenten, die beteiligt sind, wenn das Gerät sich außerhalb des Unternehmensnetzwerks befindet.

**Externe Topologie**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> Der Geräteupdate-Webdienst stellt eine externe und eine interne Website bereit, hier wird jedoch nur die externe gezeigt.<BR>Der Standort der Registrierungsstelle und die URL des Geräteupdate-Webdiensts für die Organisation müssen in DNS veröffentlicht werden, wenn Zugriff durch externe Benutzer unterstützt werden soll. Außerdem muss der Edgeserver bereitgestellt und korrekt konfiguriert werden, damit externe Kommunikation vom Gerät zur Unternehmensumgebung und zurück möglich ist. Dies wird im obigen Diagramm nicht dargestellt, da die Edgebereitstellung nicht spezifisch für die Geräteanbindung ist.



</div>

</div>

<span> </span>

</div>

</div>

</div>

