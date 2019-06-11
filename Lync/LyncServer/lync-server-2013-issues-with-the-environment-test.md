---
title: 'Lync Server 2013: Probleme mit dem Umgebungs Test'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed158c598b9dc5596df23cb845f0adac4c6fed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Probleme mit dem Umgebungs Test in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Bewährte Methoden Analyzer bietet eine Möglichkeit, um zu überprüfen, ob Ihre lync Server 2013-Umgebung eine unterstützte Konfiguration ist. Im Rahmen der Active Directory-Domänendienst Überprüfung führt Best Practices Analyzer folgende Schritte aus:

  - Überprüft die Active Directory-Domänendienste-Gesamtstruktur und die Schemavorbereitung.

  - Gibt die Anzahl der Active Directory-Domänendienste-Websites und-Domänen in der Bereitstellung an.

  - Überprüft die Gesamtstruktur und die Domänenebenen.

  - Überprüft die Version des Domänencontrollers.

  - Identifiziert den Domänen-, Konfigurations-und Schemanamenskontext.

  - Gibt die Anzahl der aktivierten Benutzer an.

  - Überprüft, wo die globalen Einstellungen für Active Directory-Domänendienste gespeichert sind.

  - Überprüft, ob die Dienstverbindungspunkte für lync Server SKP sind.

  - Identifiziert die Datenbankversion.

<div>

## <a name="resolving-issues-with-the-environment"></a>Beheben von Problemen mit der Umgebung

Wenn der Umgebungs Test Probleme mit Ihrer Umgebung gefunden hat, werden diese Probleme wahrscheinlich durch Probleme mit Ihrer Active Directory-Konfiguration oder der Softwareebene verursacht, die auf bestimmten Servern ausgeführt wird. Wenn beispielsweise Best Practices Analyzer alle Domänencontroller in Ihrer Umgebung identifiziert, die Windows Server 2000 ausführen, wird eine Warnung ausgegeben, und Sie müssen diese Domänencontroller auf eine unterstützte Version von Windows Server aktualisieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

