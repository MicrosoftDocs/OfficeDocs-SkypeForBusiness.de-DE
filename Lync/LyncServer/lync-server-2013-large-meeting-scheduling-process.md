---
title: 'Lync Server 2013: Planungsprozess für große Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11e24f6131ace7323a407d739e2174b24b57a7e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Planungsprozess für große Besprechungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Da jeweils nur eine große Besprechung im dedizierten großen Besprechungs Pool unterstützt wird, wird die Implementierung eines umfangreichen Besprechungs Planungsprozesses empfohlen, um große Besprechungs Konflikte zu verhindern. Der Zweck dieses Planungsprozesses besteht darin, das Einrichten großer Besprechungen zu vereinfachen. Diese Funktion wird nicht direkt von lync Server-oder lync Server-Clients bereitgestellt. Eine Möglichkeit zum Implementieren eines solchen Prozesses besteht darin, das Ticket System des Support Teams Ihres Unternehmens zu verwenden, sofern verfügbar.

Für Organisatoren großer Besprechungen umfasst die Planung einer großen Besprechung die folgenden Schritte:

1.  Der Besprechungsorganisator oder die Stellvertretung bestimmt neben der Liste der Referenten die Zeit, die Dauer und die Größe einer bevorstehenden Besprechung. Wenn die erwartete Besprechungsgröße 250 Benutzer überschreitet oder die beste Benutzerfreundlichkeit für eine Besprechung mit weniger als 250 Benutzern sichergestellt wird, sendet der Organisator oder der Stellvertreter eine Anforderung für eine große Besprechung.

2.  Die Mitarbeiter der Zeitplanung prüfen, ob das angeforderte Datum und die angeforderte Uhrzeit verfügbar sind. Da wir nur eine einzelne große Besprechung im dedizierten Pool gleichzeitig unterstützen, muss das Planungs Personal den großen Besprechungs Kalender überprüfen, um zu bestimmen, ob eine andere Besprechung für das angeforderte Datum und die angeforderte Uhrzeit geplant ist. Wenn die angeforderte Zeit zur Verfügung steht, genehmigt das Personal die Besprechungsanfrage.

3.  Wenn die Anforderung genehmigt wird, verwendet das Planungs Personal (mithilfe von Anmeldeinformationen im dedizierten Pool) das Online Besprechungs-Add-in für lync 2013 mit Outlook, um eine Besprechung im dedizierten großen Besprechungs Pool einzurichten. Die URL, die für die Teilnahme an der Besprechung verwendet werden soll, wird dem anfordernden im Rahmen der Genehmigungsbenachrichtigung zur Verfügung gestellt.

4.  Der Besprechungsorganisator oder die Stellvertretung verwendet Outlook, um die bevorstehende Besprechung zu planen, wobei die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzugefügt wird. Der Besprechungsorganisator oder die Stellvertretung gibt dann die Benutzer an, die eingeladen werden sollen, und sendet die Besprechungseinladung aus.
    
    In der folgenden Abbildung wird ein typischer Anforderungs-und Genehmigungsworkflow zum Planen großer Besprechungen dargestellt.
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

