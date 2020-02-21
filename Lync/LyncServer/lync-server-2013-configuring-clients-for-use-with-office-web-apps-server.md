---
title: 'Lync Server 2013: Konfigurieren von Clients für die Verwendung mit Office-webapps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c1ad26366baef7de4a82896ef5bc35d28c08d89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Konfigurieren von Clients von lync Server 2013 für die Verwendung mit Office-webapps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-25_

Wenn Sie möchten, dass Benutzer die vollständigen Funktionen von Office-Webanwendungs Server nutzen können, sollten Sie diese Benutzer auf Microsoft lync 2013 aktualisieren. nur Benutzer von lync 2013 können beispielsweisedurch PowerPoint-Folien unabhängig von der tatsächlichen PowerPoint-Präsentation scrollen. (Das bedeutet, dass diese Benutzer jederzeit auf jeder Folie in der Präsentation suchen können, ohne die tatsächliche Präsentation in irgendeiner Weise zu stören.) Benutzer, die lync 2013 nicht verwenden, können weiterhin Online Konferenzen beitreten und die PowerPoint-Präsentation anzeigen; Sie können jedoch nicht unabhängig voneinander durch die Folien scrollen, Sie können auch keine Folienübergänge sehen oder eingebettete Videos anzeigen.

Beachten Sie, dass diese Funktionen immer für Benutzer von lync 2013 zur Verfügung stehen. Dies gilt auch dann, wenn der PowerPoint-Referent Microsoft lync 2010 ausführt. Wenn eine PowerPoint-Präsentation von einem Benutzer gehostet wird, der lync 2010 ausführt, wird lync Server 2013 mit Office-webapps Server koordinieren, um sicherzustellen, dass lync 2013 Benutzer die Office-webapps-Server Version dieser Präsentation anzeigen können. Office webapps Server stellt keine PowerPoint-Dienste für Benutzer bereit, die andere Clients als lync 2013 auszuführen. Diese Benutzer stellen stattdessen eine Verbindung mit dem Konferenzserver Dienst her und zeigen PowerPoint-Präsentationen auf die gleiche Weise wie in Microsoft lync Server 2010 an. Dies bedeutet auch, dass diese Benutzer nur Zugriff auf die mehr begrenzten Funktionen haben, die von lync Server 2010 angeboten werden.

Obwohl für Office-webapps Server keine Clientkonfiguration erforderlich ist (andere als das Upgrade von Benutzern auf lync 2013), wird empfohlen, dass die Konferenzteilnehmer ein Upgrade auf Internet Explorer 9 durchführen. Obwohl auf Konferenzen mit Internet Explorer 8 zugegriffen werden kann, gibt es einige Einschränkungen bei der Verwendung dieses Webbrowsers. Beispielsweise können Benutzer von Internet Explorer 8 nicht die Größe der PowerPoint-Stufe auf eine benutzerdefinierte Größe anpassen. Stattdessen sind Sie auf die Verwendung einer von drei vordefinierten Bühnengrößen limitiert. Ebenso können Internet Explorer 8 Benutzer keine Mediendateien wiedergeben.

</div>

<span> </span>

</div>

</div>

</div>

