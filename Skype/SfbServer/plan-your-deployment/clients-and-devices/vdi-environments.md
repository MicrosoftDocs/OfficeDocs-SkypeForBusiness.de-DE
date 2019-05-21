---
title: Planen für Skype for Business in VDI-Umgebungen
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: In diesem Thema werden Planungsüberlegungen zur Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remote Desktop erläutert.
ms.openlocfilehash: 958c13821eea46be91d51d7399722d2af433ccf0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277286"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planen für Skype for Business in VDI-Umgebungen
 
In diesem Thema werden Planungsüberlegungen zur Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remote Desktop erläutert. 
  
Eine VDI-Umgebung (Virtual Desktop Infrastructure) wird in einigen Organisationen verwendet, in denen Sicherheit und Complianceprobleme besonders sensibel sind. Die Benutzer arbeiten über Remotedesktopdienste oder eine ähnliche Remoteverbindung auf einem virtuellen Desktop mit allen ihren Desktopanwendungen und -dateien. Die Verwendung von Skype for Business mit vollständiger Audio-und Videoübertragung auf einer solchen Verbindung erfordert eine starke Belastung der Audio-und Videoverarbeitung auf dem Client, der auf einem virtuellen Desktop verwaltet wird. Zusätzliche VDI-Plug-in-Software steht zur Verfügung, die die Verarbeitung an den lokalen Computer des Endbenutzers abwälzt und die Auslastung des virtuellen Desktops verringert.
  
Für die VDI-Plug-in-Komponente, die von Microsoft, Citrix oder VMware angeboten wird, stehen drei Lösungen zur Verfügung. Für neue Bereitstellungen empfiehlt Microsoft die Verwendung der Citrix HDX Realtime Optimization Pack-Lösung oder des VMware Horizon Virtualization Pack. Das ursprüngliche lync-VDI-Plug-in wird für den Rest des Lebenszyklus weiterhin unterstützt.
  
- Das **lync-VDI-Plug-in** wurde für lync 2013 entwickelt und ist entweder mit dem lync 2013-oder Skype for Business 2015-Client kompatibel, der auf einem virtuellen Desktop ausgeführt wird. It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop. Für das Plug-in muss kein Skype for Business-Client auf dem lokalen Computer oder Thin Client installiert werden, auf dem Windows 7-, Windows 8-oder Windows Server 2008-Betriebssysteme ausgeführt werden müssen. (Thin Client-Geräte, die diese Betriebssysteme verwenden und von Microsoft unterstützt werden, sind: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP T610 und HP t5740e.) Dieses Plug-in wird weiterhin unterstützt, aber es sind keine zukünftigen Updates geplant. For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.
    
- Das **Citrix Realtime Optimization Pack** baut auf dem lync-VDI-Plug-in auf und funktioniert mit lync 2013-oder Skype for Business 2016-Clients auf einem virtuellen Desktop. Es wurde gemeinsam von Citrix und Microsoft als Verbesserung des ursprünglichen VDI-Plug-Ins entwickelt. Es kann auf Clients unter Windows- und Nicht-Windows-Betriebssystemen (einschließlich Windows 10, Mac und Linux) installiert werden. Es besteht aus zwei Komponenten: dem Realtime-Connector (der auf dem virtuellen Desktop installiert ist) und dem Echt Zeit Medienmodul (das auf dem lokalen Computer des Endbenutzers installiert ist). Diese beiden Komponenten ermöglichen es dem lokalen Computer des Benutzers, den Skype for Business-Client auf dem virtuellen Desktop zu verwenden, wobei die A/V-Verarbeitung auf den lokalen Computer verschoben wird. Für Citrix-basierte virtuelle Desktopumgebungen wird Citrix RealTime Optimization Pack empfohlen, für das weitere Unterstützung geplant ist.
    
- Das **VMware Horizon Virtualization Pack** für Skype for Business, das in Zusammenarbeit mit VMware entwickelt wurde, ermöglicht Ihnen, Skype for Business auf einem virtuellen Desktop zu liefern, während Sie eine hervorragende Benutzererfahrung bieten. Die Lösung funktioniert durch die Nutzung eines medienmoduls auf dem Client zum Erstellen einer optimierten Lösung, wobei der Clientendpunkt Medien Entlastungs Funktionen für Audio-und Videoanrufe bereitstellt. Diese Lösung, die Audio-und Videoübertragungen direkt zwischen Endpunkten für einzelne Zusammenarbeit bereitstellen oder an eine zentrale Multipoint-Steuereinheit (MCU) für mehrteilige Konferenzgespräche oder Besprechungen übertragen kann.
    
> [!NOTE]
> Die Skype for Business Basic-Clients werden nicht vom Citrix HDX Realtime Optimization Pack oder dem VMware Horizon Virtualization Pack unterstützt. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Das Citrix VDI-Umgebungs-Plug-in (eine Funktion von XenApp und XenDesktop) ist mit lync 2013 und Skype for Business 2015 und 2016 (vollständige Clients, die ein beliebiges Klick-und-Los-Installationsprogramm ausführen, oder MSI-Installationsprogramme, die nach Januar 2017 PU verfügbar sind) kompatibel, die auf einer virtuellen Desktop. Die gesamte Funktion basiert auf dem Microsoft lync VDI-Plug-in, funktioniert aber mit einer größeren Auswahl an Clientbetriebssystemen, einschließlich Windows 10, Macintosh und Linux.
  
Eine vollständige Liste der Features und unterstützten Technologien finden Sie auf der Citrix-Website unter Bereitstellen von [Microsoft Skype for Business für XenApp-und XenDesktop-Benutzer](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Weitere Informationen finden Sie unter folgenden Links:
  
- Citrix [HDX Realtime Optimization Pack 2,1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Technische Übersicht](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business-Funktionsunterstützung](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMware Horizon-Virtualisierungs-Paket
<a name="Citrix_RT"> </a>

Die VDI-Umgebungs Lösung von VMware ist mit Skype for Business 2015 und 2016 vollständigen Clients kompatibel, die auf einem virtuellen Desktop installiert sind. Die gesamte Funktion basiert auf dem Microsoft lync VDI-Plug-in, funktioniert aber mit einer größeren Auswahl an Clientbetriebssystemen, einschließlich Windows 10, Macintosh und Linux. 
  
Eine vollständige Erläuterung der Features und unterstützten Technologien finden Sie auf der VMware-Website unter den folgenden Links:
  
- [Neuerungen in VMware Horizon 7,4 &amp; Horizon Client 4,7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon Virtualization Pack für Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business mit VMware Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Lync VDI-Plug-In von Microsoft
<a name="Citrix_RT"> </a>

Bei der Microsoft lync VDI-Plug-in-Lösung muss sich der Benutzer auf einem Windows-Computer oder einem Thin-Client befinden und das lync VDI-Plug-in von Microsoft installieren, um Audio/Video-Streams vom Client auf dem virtuellen Desktop zu verarbeiten. Die Benutzer führen die folgenden Schritte aus:
  
1. Verbinden eines Audio-/Video-Geräts (beispielsweise eines Headsets oder einer Kamera) mit einem lokalen Computer
    
2. Stellen Sie eine Verbindung mit einem virtuellen Remote Desktop mit einem lync 2013-oder Skype for Business 2015-Client her.
    
3. Geben Sie die Anmeldeinformationen für Skype for Business auf dem virtuellen Desktop ein.
    
4. Geben Sie die Benutzeranmeldeinformationen erneut ein, um eine Verbindung mit dem lync VDI-Plug-in auf dem lokalen Windows-Computer oder Thin Client herzustellen.
    
Wenn eine Verbindung hergestellt ist, können die Benutzer Audio- und Videoanrufe tätigen und empfangen. Der Datenverkehr im Netzwerk und die Last des virtuellen Desktops werden minimiert, da die Audio-/Videoverarbeitung auf dem lokalen Computer stattfindet.
  
Das Microsoft lync-VDI-Plug-in wird nur unter bestimmten Windows-Betriebssystemen unterstützt und unterstützt nur lync 2013-oder Skype for Business 2015-Clients. Weitere Details zu den unterstützten Technologien und zu Einschränkungen finden Sie unter [Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen](vdi-environments.md#Supported_virt).
  
Weitere Informationen finden Sie unter folgenden Links:
  
- [Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen](vdi-environments.md#Supported_virt)
    
- [Voraussetzungen für das Lync VDI-Plug-In](vdi-environments.md#VDI_prereq)
    
- [Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix Knowledge Center-Artikel [CTX138408](https://support.citrix.com/article/CTX138408)
    
Das Microsoft VDI-Plug-in ist verfügbar unter [Microsoft lync VDI 2013-Plugin (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) oder [Microsoft lync VDI 2013-Plug-in (64-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Dieses Plug-in wird mit dem Skype for Business 2015-Client trotz des Namens unterstützt.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen
<a name="Supported_virt"> </a>

Das lync VDI-Plug-in ermöglicht Audio-und Videoanrufe nach unterstützten Virtualisierungstechnologien. Gemäß Standardtelefonvorschriften ist auch Unterstützung für E911 enthalten. In den folgenden Abschnitten werden die Virtualisierungstechnologien beschrieben, die vom lync-VDI-Plug-in und den bekannten Funktionseinschränkungen unterstützt werden.
  
#### <a name="support-for-virtualization-technologies"></a>Unterstützung für Virtualisierungstechnologien

Das lync-VDI-Plug-in unterstützt vollständige Desktop-Remotesitzungen im Szenario des persönlichen virtuellen Desktops, jedoch nicht im Szenario der Remotedesktopsitzung. Diese Szenarien können wie folgt beschrieben werden:
  
- **Unterstützt: Personalisierte virtuelle Desktops oder virtuelle Desktopinfrastruktur (Virtual Desktop Infrastructure, VDI).** In diesem Szenario melden sich die einzelnen Benutzer bei einem anpassbaren virtuellen Desktop an und können Dateien auf dem Desktop speichern, die sitzungsübergreifend bestehen bleiben. Microsoft Remote Desktop Services und VMware Horizon View sind Beispielimplementierungen, die für die Verwendung mit Skype for Business 2015 getestet wurden. Eine weitere validierte Implementierung ist Citrix XenDesktop. Informationen zu herstellerspezifischen VDI-Umgebungen und Clienthardware, die von Microsoft getestet wurden, finden Sie unter [für Microsoft lync qualifizierte Infrastruktur](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Nicht unterstützt: Remotedesktopsitzungen.** In diesem Szenario melden sich die einzelnen Benutzer bei einer allgemeinen virtuellen Desktopsitzung an, die nicht angepasst werden kann. Beispiele sind Microsoft Remote Desktop Sitzungen (RDSH) und Citrix XenApp, kombiniert mit Citrix Receiver.
    
Das lync-VDI-Plug-in unterstützt keine anderen Virtualisierungstechnologien wie Application Virtualization, was die Verwendung einer Anwendung ermöglicht, ohne dass die vollständige Anwendung lokal installiert werden muss. Zu den Beispielimplementierungen gehören Citrix XenApp und Microsoft Application Virtualization (App-V). Anwendungsstreaming, Anwendungsremoting und gemischte Virtualisierungsmodi (zum Beispiel Anwendungsremoting in vollem Desktopremoting) werden nicht unterstützt.
  
Das lync-VDI-Plug-in wurde für die Verwendung von plattformunabhängigen APIs mit dem Namen Dynamic Virtual Channels (DVCs) entwickelt. Informationen zu nicht ausdrücklich unterstützten Szenarien finden Sie in den Supportaussagen des VDI-Lösungsanbieters.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Voraussetzungen für das Lync VDI-Plug-In
<a name="VDI_prereq"> </a>

In einer VDI-Umgebung müssen die virtuellen Computer und der lokale Computer des Benutzers die in diesem Abschnitt beschriebenen Anforderungen erfüllen.
  
> [!NOTE]
>  Informationen zum Installieren und Bereitstellen der Umgebung erhalten Sie vom Anbieter Ihrer Virtualisierungslösung. Allgemeine Informationen zum Bereitstelleneiner virtualisierten Umgebung, die auf Hyper-v und Remotedesktopdiensten basiert, finden Sie in den folgenden Artikeln in der Microsoft-Bibliothek: [Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Dienste in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Virtuelle Computer müssen mit Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Service Packs konfiguriert sein.
  
Der lokale Computer des Benutzers muss die folgenden Voraussetzungen erfüllen:
  
- Der Benutzer muss sich in Skype for Business Server oder lync Server 2013 befinden.
    
- Auf dem lokalen Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1 oder Windows 8 ausgeführt werden.
    
- Wenn Sie die Remote Desktop Dienste verwenden, wählen Sie das 32-Bit oder das 64-Bit-lync-VDI-Plug-in aus, um dem Betriebssystem des lokalen Computers zu entsprechen. Es ist nicht notwendig, dass sowohl auf dem lokalen Computer als auch in der virtuellen Maschine 32-Bit- oder 64-Bit-Betriebssysteme installiert sind. Wenn Sie eine andere Virtualisierungslösung oder -plattform verwenden, informieren Sie sich über die Anforderungen des jeweiligen Anbieters.
    
- Auf dem lokalen Computer muss die [neueste Version des Remotedesktopclients](https://go.microsoft.com/fwlink/p/?LinkId=268032)ausgeführt werden. Installieren Sie die neuesten Updates des Remotedesktopdienste-Clients von Microsoft oder der neuesten Remote Desktop-Client Software Ihres Virtualisierungslösung-Anbieters. 
    
- Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist. Informationen zum Konfigurieren dieser Einstellungen für die Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt "so konfigurieren Sie die Einstellungen für Remotedesktopverbindung". 
    
Das Microsoft VDI-Plug-in ist verfügbar unter [Microsoft lync VDI 2013-Plugin (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) oder [Microsoft lync VDI 2013-Plug-in (64-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Bekannte Funktionseinschränkungen
<a name="VDI_prereq"> </a>

Die folgenden Einschränkungen sind bekannt, wenn Sie den Skype for Business 2015-Client in einer VDI-Umgebung verwenden:
  
Es gibt nur begrenzte Unterstützung für die Anonymisierungs Funktionen für Anruf Delegierungen und Reaktionsgruppen-Agents.
  
Folgende Features werden nicht unterstützt:
  
- Integrierte Optimierungsseiten für Audio- und Videogeräte
    
- Mehransicht für Video
    
- Aufzeichnen von Konversationen
    
- Anonymes teilnehmen an Besprechungen (also teilnehmen an Skype for Business-Besprechungen, die von einer Organisation gehostet werden, die nicht mit Ihrer Organisation in Verbindung steht).
    
- Verwenden des lync-VDI-Plug-ins zusammen mit einem lync Phone Edition-Gerät.
    
- Anrufkontinuität im Fall eines Netzwerkausfalls
    
- Features für benutzerdefinierte Klingeltöne und Wartemusik
    
Das lync-VDI-Plug-in wird in einer Office 365-Umgebung nicht unterstützt.
  
> [!NOTE]
> Citrix RealTime Optimization Pack unterstützt Office 365. In Citrix-basierten virtuellen Umgebungen lesen Sie die Citrix-Dokumentation zur [technischen Übersicht](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) für die Liste der unterstützten Features und Versionen.
  
## <a name="see-also"></a>Siehe auch
<a name="Citrix_RT"> </a>

[Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

