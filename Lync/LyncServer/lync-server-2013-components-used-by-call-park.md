---
title: 'Lync Server 2013: Komponenten für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae458d7ef3245e366e4f2bdd61f192401909213b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Komponenten für das Parken von Anrufen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-13_

Die Anwendung Parken wird automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen. Sie aktivieren den Anruf Park durch Konfigurieren der VoIP-Richtlinie. Die folgenden lync Server 2013-Komponenten unterstützen die Anwendung für den Parken von anrufen:

  - **Application Service**   Application Service stellt eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen bereit, beispielsweise die Anwendung für den Parken von anrufen. Der Anwendungsdienst wird auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server automatisch installiert.

  - **Anwendung für den Park anrufen**   die Anwendung "Parken" ist eine der Unified Communications-Anwendungen, die vom Anwendungsdienst gehostet werden. Sie wird automatisch bei der Bereitstellung von Enterprise-VoIP integriert. Rufen Sie Parkplätze an, ruft Anrufe ab und verwaltet die Orbits des Anruf Parks.

  - **Music-on-halte-Datei**   wenn Musik aktiviert ist, wird die Musikdatei wiedergegeben, während ein Anruf abgestellt wird. Eine Standard-Musikdatei ist enthalten, wenn die Anwendung für den Parken von Anrufen installiert ist.

  - **Dateispeicher**   die Anwendung des Anruf Parks verwendet den Dateispeicher, um benutzerdefinierte Audiodateien zu speichern.

  - **Lync Server-System**   Steuerung Sie können die lync Server-Systemsteuerung verwenden, um die Orbit-Tabelle des Anruf Parks zu konfigurieren und den Anruf Park für Benutzer zu aktivieren.

  - **Lync Server-Verwaltungsshell**   alle Einstellungen für die Anruf Park Anwendung können mithilfe der lync Server-Verwaltungsshell-Cmdlets ausgeführt werden.

</div>

<span> </span>

</div>

</div>

</div>

