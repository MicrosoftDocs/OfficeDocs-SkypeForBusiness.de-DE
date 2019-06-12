---
title: Voraussetzungen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74603ed20fe144ca89d3ac13bc00fef0e7d6ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>Voraussetzungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-19_

Es gibt verschiedene Hardware-, Software-und Systemkonfigurations Anforderungen, die Sie zum Ausführen des lync Server 2013-Stress-und-Leistungstools benötigen.

<div>

## <a name="client-hardware-requirements"></a>Client Hardware Anforderungen

Zum Ausführen des lync Server 2013-Leistungs-und Leistungstools für die lync Server 2013-Bereitstellung benötigen Sie für jeden 4.500-Benutzer, dessen Auslastung Sie simulieren möchten, mindestens einen dedizierten Computer, der die folgenden minimalen Hardwareanforderungen erfüllt:

  - 1 Gigabitnetzwerkadapter

  - 8 GB Arbeitsspeicher

  - 2 Dual-Core-Prozessoren (Central Processing Units, CPUs)

</div>

<div>

## <a name="client-software-requirements"></a>Client Software Anforderungen

Die unterstützten Betriebssysteme sind für das Ausführen des lync Server 2013-Stress-und-Leistungstools auf Ihrer lync Server 2013-Bereitstellung:

  - Betriebssystem Windows Server 2012

  - Windows Server 2008-Betriebssystem (64-Bit-Edition)

Ihr Clientcomputer muss die folgenden Softwareanforderungen erfüllen:

  - Sie müssen die [Microsoft .NET Framework 4,5](http://go.microsoft.com/fwlink/?linkid=143212) -Runtime installiert haben.

  - Unter Windows Server 2008/Windows Server 2012 muss das Feature "Desktop Experience" aktiviert sein.

  - Sie müssen das [Microsoft Visual C++ 2012 Redistributable Package](http://go.microsoft.com/fwlink/?linkid=143216) (x64) installiert haben.

  - Eine vollständig konfigurierte lync Server 2013-Bereitstellung.

<div>


> [!IMPORTANT]  
> Microsoft Unified Communications Managed API (UCMA) 4,0-Bibliotheken sind im Installationspaket enthalten, daher ist UCMA nicht erforderlich und sollte nicht auf Clientcomputern installiert werden.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Konfigurationsanforderungen

Die Computer, auf denen das Stress-und Leistungs Tool lync Server 2013 ausgeführt wird, müssen entsprechend den folgenden Anforderungen konfiguriert sein:

1.  Sie müssen als Mitglied der Gruppe "Domänen" oder "lokale Administratoren" angemeldet sein.

2.  Das lync Server 2013-Stress-und-Leistungs Tool (LyncPerfTool. exe) kann nicht auf einem Computer ausgeführt werden, auf dem ebenfalls lync Server 2013-Komponenten ausgeführt werden.

3.  Sie müssen das lync Server 2013-Benutzer Erstellungstool (UserProvisioningTool. exe) auf dem Front-End-Server oder auf dem Standard Edition-Server ausführen, auf dem sich die Benutzerkonten befinden. Wenn das Tool mehrmals ausgeführt wird, muss jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, über eine eindeutige Telefonnummer verfügen.

4.  Die Größe der Auslagerungsdatei sollte vom System verwaltet werden, oder Sie sollte mindestens 1,5 mal so viel RAM auf dem System aufweisen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

