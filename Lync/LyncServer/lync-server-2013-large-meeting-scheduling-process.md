---
title: 'Lync Server 2013: Planungsprozess für große Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af97cdbd07603c420780a92fbbe0a03c8a4d0520
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Planungsprozess für große Besprechungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Da im dedizierten, umfangreichen Besprechungs Pool nur jeweils eine große Besprechung unterstützt wird, empfehlen wir die Implementierung eines umfangreichen Besprechungs Planungsprozesses, um große Besprechungs Konflikte zu vermeiden. Der Zweck dieses Planungsprozesses besteht darin, das Einrichten großer Besprechungen zu vereinfachen. Diese Funktion wird nicht direkt von lync Server-oder lync Server-Clients bereitgestellt. Eine Möglichkeit zur Implementierung eines solchen Prozesses besteht darin, das Ticketing-System Ihres Unternehmens zu verwenden, sofern verfügbar.

Für Organisatoren von umfangreichen Besprechungen müssen Sie die folgenden Schritte ausführen, um eine große Besprechung zu planen:

1.  Der Besprechungsorganisator oder die delegierte Person bestimmt den Zeitpunkt, die Dauer und den Umfang einer anstehenden Besprechung sowie die Liste der Referenten. Falls der erwartete Besprechungsumfang 250 Benutzer überschreitet, oder um die optimale Funktionalität für eine Besprechung mit weniger als 250 Benutzern sicherzustellen, reicht der Organisator oder die delegierte Person einen Antrag für eine große Besprechung ein.

2.  Die Planungsmitarbeiter überprüfen, ob der angeforderte Termin verfügbar ist. Da jeweils immer nur eine einzige große Besprechung im Pool unterstützt wird, müssen die Planungsmitarbeiter anhand des Kalenders für große Besprechungen feststellen, ob für den angeforderten Termin bereits eine andere Besprechung geplant ist. Falls der angeforderte Termin verfügbar ist, wird die Besprechungsanfrage genehmigt.

3.  Wenn die Anforderung genehmigt wurde, verwendet das Planungs Personal (mithilfe von Anmeldeinformationen im dedizierten Pool) das Online Besprechungs-Add-in für lync 2013 mit Outlook, um eine Besprechung im dedizierten groß Besprechungs Pool einzurichten. Die URL für die Teilnahme an der Besprechung wird dem Antragsteller im Rahmen des Genehmigungshinweises bereitgestellt.

4.  Der Besprechungsorganisator oder die delegierte Person plant mithilfe von Outlook die anstehende Besprechung und fügt die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzu. Der Besprechungsorganisator oder die delegierte Person legt dann die Benutzer fest, die eingeladen werden sollen, und versendet die Besprechungseinladung.
    
    Die folgende Abbildung zeigt einen typischen Anforderungs-und Genehmigungsworkflow für das Planen großer Besprechungen.
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d] (images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

