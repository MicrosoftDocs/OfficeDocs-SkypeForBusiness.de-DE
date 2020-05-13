---
title: 'Lync Server 2013: unterstützte Technologien für Virtualisierung und bekannte Einschränkungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0968f79b8c9aedc3dc2d2318a2e8abf5c51531d7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Unterstützte Virtualisierungstechnologie und bekannte Einschränkungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-02-06_

Das lync VDI-Plug-in ermöglicht Audio-und Videoanrufe für unterstützte Virtualisierungstechnologie. Dadurch werden die für Microsoft lync Server 2010 in der [Client-Virtualisierung in Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) Whitepaper beschriebenen Funktionen erweitert. In Übereinstimmung mit den standardmäßigen Telefon Richtlinien ist auch die Unterstützung für E911 enthalten. In den folgenden Abschnitten werden die Virtualisierungstechnologien beschrieben, die vom lync VDI-Plug-in und den bekannten Funktionseinschränkungen unterstützt werden.

<div>

## <a name="support-for-virtualization-technologies"></a>Unterstützung für Virtualisierungs-Technologien

Das lync VDI-Plug-in unterstützt vollständiges Desktop-Remoting im Szenario für persönliche virtuelle Desktops, jedoch nicht im Szenario mit Remotedesktopsitzungen. Diese Szenarien können wie folgt beschrieben werden:

  - **Unterstützt: Personalisierte virtuelle Desktops oder virtuelle Desktopinfrastruktur (VDI).**     In diesem Szenario meldet sich jeder Benutzer bei einem anpassbaren virtuellen Desktop an und kann Dateien auf dem Desktop speichern, die in mehreren Sitzungen gespeichert sind. Microsoft Remote Desktop Dienste, VMware Horizon View und Citrix XenDesktop sind Implementierungen, die für die Verwendung mit lync getestet wurden. Informationen zu anbieterspezifischen VDI-Umgebungen und Clienthardware, die von Microsoft getestet wurden, finden Sie unter [für Microsoft lync qualifizierte Infrastruktur](https://go.microsoft.com/fwlink/?linkid=313435).

  - **Nicht unterstützt: Remote Desktop Sitzungen.**     In diesem Szenario meldet sich jeder Benutzer bei einer generischen virtuellen Desktopsitzung an, die nicht angepasst werden kann. Zu den Beispielimplementierungen Gehören Microsoft Remote Desktop Sitzungen (RDSH) und Citrix XenApp in Kombination mit Citrix Receiver.

Das lync VDI-Plug-in unterstützt keine anderen Virtualisierungstechnologien wie Application Virtualization, die die Verwendung einer Anwendung ermöglichen, ohne dass die vollständige Anwendung lokal installiert werden muss. Zu den Beispielimplementierungen Gehören Citrix XenApp und Microsoft Application Virtualization (App-V). Anwendungsstreaming, Anwendungs Remoting und gemischte Virtualisierungs Modi (beispielsweise Anwendungs Remoting in vollständigem Desktop-Remoting) werden nicht unterstützt.

Um Erweiterbarkeit zu ermöglichen, wurde das lync VDI-Plug-in für die Verwendung plattformunabhängiger APIs mit dem Namen Dynamic Virtual Channels (DVCs) entwickelt. Informationen zu Szenarien, die nicht explizit von lync unterstützt werden, finden Sie unter Support Statements from the VDI Solution Provider.

</div>

<div>

## <a name="known-feature-limitations"></a>Bekannte Funktionseinschränkungen

Im folgenden sind bekannte Einschränkungen beim Verwenden von lync 2013 in einer VDI-Umgebung bekannt:

  - Es gibt nur eine beschränkte Unterstützung für Anonymisierungs Funktionen für die Anrufdelegierung und den Reaktionsgruppen-Agent.

  - Folgende Features werden nicht unterstützt:
    
      - Integrierte Optimierungsseiten für Audio- und Videogeräte
    
      - Video mit mehreren Ansichten.
    
      - Aufzeichnen von Konversationen
    
      - Remote Desktop Dienste (RDS).
    
      - Anonymes Hinzufügen von Besprechungen (also beitreten von lync-Besprechungen, die von einer Organisation gehostet werden, die nicht mit Ihrer Organisation verbunden ist).
    
      - Verwenden des lync VDI-Plug-ins zusammen mit einem lync Phone Edition-Gerät.
    
      - Anrufkontinuität im Fall eines Netzwerkausfalls
    
      - Angepasste Klingeltöne und Features für die Musik Aufbewahrung.

  - Das lync VDI-Plug-in wird in einer Microsoft 365-oder Office 365-Umgebung nicht unterstützt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

