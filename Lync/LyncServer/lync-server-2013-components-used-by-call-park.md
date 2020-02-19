---
title: 'Lync Server 2013: vom Parken von Anrufen verwendete Komponenten'
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
ms.openlocfilehash: 3b4a833736368fe6060dad4fbb62e6a528e91b6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Für das Parken von Anrufen in lync Server 2013 verwendete Komponenten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-13_

Das Anwendung zum Parken von Anrufen wird automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen. Sie können das Parken von Anrufen durch Konfigurieren der VoIP-Richtlinie aktivieren. Die folgenden lync Server 2013 Komponenten unterstützen das Anwendung zum Parken von anrufen:

  - **Anwendungsdienst**   Anwendungsdienst bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen wie der Anwendung zum Parken von anrufen. Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server installiert.

  - **Anwendung zum Parken von Anrufen**   das Anwendung zum Parken von anrufen ist eine der Unified Communications-Anwendungen, die von Anwendungsdienst gehostet werden. Sie wird automatisch bei der Bereitstellung von Enterprise-VoIP einbezogen. Parken von Parks anrufen und Anrufe abrufen und Orbits für das Parken von Anrufen verwalten.

  - **Music-on Hold-Datei**   wenn Music in enabled ist, wird die Musikdatei wiedergegeben, während ein Anruf geparkt wird. Wenn die Anwendung zum Parken von Anrufen installiert ist, wird eine standardmäßige Musikdatei hinzugefügt.

  - **Dateispeicher**   der Anwendung zum Parken von Anrufen verwendet Dateispeicher, um benutzerdefinierte Audiodateien zu speichern.

  - **Lync Server-Systemsteuerung**   Sie können lync Server-Systemsteuerung verwenden, um die Orbit-Tabelle für das Parken von Anrufen zu konfigurieren und die Funktion zum Parken von Anrufen für Benutzer zu aktivieren.

  - **Lync Server-Verwaltungsshell**   alle Anwendung zum Parken von Anrufen Konfiguration können mithilfe von lync Server-Verwaltungsshell-Cmdlets ausgeführt werden.

</div>

<span> </span>

</div>

</div>

</div>

