---
title: Voraussetzungen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d8f0ee6a50d40f938a9f2c6f731b0a4afa647ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>Voraussetzungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-19_

Es gibt verschiedene Hardware-, Software-und Systemkonfigurations Anforderungen, die Sie zum Ausführen des lync Server 2013 Stress-und Leistungstools benötigen.

<div>

## <a name="client-hardware-requirements"></a>Client Hardware Anforderungen

Um das Tool für die lync Server 2013 Spannung und Leistung in ihrer lync Server 2013-Bereitstellung auszuführen, benötigen Sie für jeden 4.500-Benutzer, dessen Auslastung Sie simulieren möchten, mindestens einen dedizierten Computer, der die folgenden minimalen Hardwareanforderungen erfüllt:

  - 1 Gigabit-Netzwerkadapter

  - 8 GB RAM

  - 2 Dual-Core-zentral Verarbeitungseinheiten (CPUs)

</div>

<div>

## <a name="client-software-requirements"></a>Client Software Anforderungen

Zum Ausführen des lync Server 2013 Stress and Performance-Tools in ihrer lync Server 2013-Bereitstellung sind die folgenden Betriebssysteme unterstützt:

  - Windows Server 2012 Betriebssystem

  - Windows Server 2008 Betriebssystem (64-Bit-Edition)

Der Clientcomputer muss die folgenden Softwareanforderungen erfüllen:

  - Sie müssen die [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) Laufzeit installiert haben.

  - In Windows Server 2008/Windows Server 2012 muss das Feature "Desktop Darstellung" aktiviert sein.

  - Sie müssen das [Microsoft Visual C++ 2012 Redistributable Package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installiert haben.

  - Eine vollständig konfigurierte lync Server 2013-Bereitstellung.

<div>


> [!IMPORTANT]  
> Verwaltete API von Microsoft Unified Communications (UCMA) 4,0-Bibliotheken sind im Installationspaket enthalten, daher ist UCMA nicht erforderlich und sollte nicht auf Clientcomputern installiert werden.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Konfigurationsanforderungen

Die Computer, auf denen das lync Server 2013 Stress-und Leistungs Tool ausgeführt wird, müssen entsprechend den folgenden Anforderungen konfiguriert werden:

1.  Sie müssen als Mitglied der Gruppe "Domänen" oder "lokale Administratoren" angemeldet sein.

2.  Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) kann nicht auf einem Computer ausgeführt werden, auf dem auch lync Server 2013 Komponenten ausgeführt werden.

3.  Sie müssen das lync Server 2013-Benutzer Erstellungstool (UserProvisioningTool.exe) auf der Front-End-Server oder auf dem Standard Edition-Server ausführen, in dem sich die Benutzerkonten befinden. Wenn das Tool mehrmals ausgeführt wird, muss jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, über eine eindeutige Telefonnummer verfügen.

4.  Die Größe der Auslagerungsdatei sollte vom System verwaltet werden oder sollte mindestens 1,5 mal so groß sein wie der RAM-Wert des Systems.

</div>

</div>

<span> </span>

</div>

</div>

</div>

