---
title: 'Lync Server 2013: Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen'
TOCTitle: Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204982(v=OCS.15)
ms:contentKeyID: 49294329
ms.date: 02/06/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2017-02-06_

Das Lync-VDI-Plug-In ermöglicht Audio- und Videoanrufe für unterstützte Virtualisierungstechnologien. Damit wird die Funktionalität erweitert, die für Microsoft Lync Server 2010 im Whitepaper [Clientvirtualisierung in Microsoft Lync 2010](http://go.microsoft.com/fwlink/?linkid=330447) aufgeführt ist. Unter Einhaltung von Standardtelefonvorschriften ist auch eine Unterstützung für E911 enthalten. In den folgenden Abschnitten sind die vom Lync-VDI-Plug-In unterstützen Virtualisierungstechnologien und die bekannten Funktionseinschränkungen beschrieben.

## Unterstützung für Virtualisierungstechnologien

Das Lync-VDI-Plug-In unterstützt ein vollständiges Desktop-Remoting im persönlichen virtuellen Desktopszenario, nicht aber im Szenario einer Remotedesktopsitzung. Diese Szenarios können wie folgt beschrieben werden:

  - **Unterstützt: Personalisierte virtuelle Desktops oder virtuelle Desktopinfrastruktur (VDI).**   In diesem Szenario meldet sich jeder Benutzer bei einem anpassbaren virtuellen Desktop an und kann Dateien auf dem Desktop speichern, die sitzungsübergreifend bestehen bleiben. Microsoft-Remotedesktopdienste, VMware Horizon View und Citrix XenDesktop sind Implementierungen, die für die Verwendung mit Lync getestet wurden. Informationen zu anbieterspezifischen VDI-Umgebungen und Clienthardware, die von Microsoft getestet wurden, finden Sie unter [Qualifizierte Infrastruktur für Microsoft Lync](http://go.microsoft.com/fwlink/?linkid=313435).

  - **Nicht unterstützt: Remotedesktopsitzungen.**   In diesem Szenario meldet sich jeder Benutzer bei einer allgemeinen virtuellen Desktopsitzung an, die nicht angepasst werden kann. Zu den Beispielimplementierungen gehören Microsoft-Remotedesktopsitzungen (RDSH) und Citrix XenApp in Kombination mit Citrix Receiver.

Das Lync-VDI-Plug-In bietet keine Unterstützung für andere Virtualisierungstechnologien wie Anwendungsvirtualisierung, die die Verwendung einer Anwendung ermöglicht, ohne die volle Anwendung lokal installieren zu müssen. Zu den Beispielimplementierungen gehören Citrix XenApp und Microsoft Application Virtualization (App-V). Anwendungsstreaming, Anwendungsremoting und gemischte Virtualisierungsmodi (zum Beispiel Anwendungsremoting in vollem Desktopremoting) werden nicht unterstützt.

Um eine Erweiterbarkeit zu ermöglichen, wurde das Lync-VDI-Plug-In für die Verwendung plattformunabhängiger APIs namens Dynamic Virtual Channels (DVCs) entwickelt. Informationen zu Szenarios, die nicht ausdrücklich von Lync unterstützt werden, finden Sie in den Supportaussagen vom VDI-Lösungsanbieter.

## Bekannte Funktionseinschränkungen

Folgende Einschränkungen sind für die Verwendung von Lync 2013 in einer VDI-Umgebung bekannt:

  - Es gibt nur eine eingeschränkte Unterstützung für die Anrufdelegierung und Features zur Anonymisierung von Reaktionsgruppenagents.

  - Folgende Features werden nicht unterstützt:
    
      - Integrierte Optimierungsseiten für Audio- und Videogeräte
    
      - Mehransicht für Video
    
      - Aufzeichnen von Konversationen
    
      - Anonyme Teilnahme an Besprechungen (d. h. Lync-Besprechungen, die von einer Organisation gehostet sind, die nicht mit Ihrer Organisation im Verbund stehen)
    
      - Verwenden des Lync-VDI-Plug-Ins in Verbindung mit einem Lync Phone Edition-Gerät.
    
      - Anrufkontinuität im Fall eines Netzwerkausfalls
    
      - Features für benutzerdefinierte Klingeltöne und Wartemusik

  - Das Lync-VDI-Plug-In wird nicht in einer Office 365-Umgebung unterstützt.

