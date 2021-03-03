---
title: Planen von Skype for Business in VDI-Umgebungen
author: cichur
ms.author: v-cichur
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: In diesem Thema werden Planungsüberlegungen für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop erläutert.
ms.openlocfilehash: 66fe9dd0be2dd079597837b8d25c29b3f047b0c6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816105"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planen von Skype for Business in VDI-Umgebungen
 
In diesem Thema werden Planungsüberlegungen für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop erläutert. 
  
In einigen Organisationen, in denen Sicherheits- und Complianceprobleme besonders sensibel sind, wird eine Virtuelle Desktopinfrastrukturumgebung (Virtual Desktop Infrastructure, VDI) verwendet. Ihre Benutzer arbeiten auf einem virtuellen Desktop mit allen ihren Desktopanwendungen und Dateien über Remotedesktopdienste oder eine ähnliche Remoteverbindung. Die Verwendung von Skype for Business mit vollständigem Audio und Video in einer Verbindung wie dieser erfordert eine hohe Audio- und Videoverarbeitung auf dem Client, der auf einem virtuellen Desktop installiert ist. Es steht zusätzliche VDI-Plug-In-Software zur Verfügung, die diese Verarbeitung auf den lokalen Computer des Endbenutzers überlädt und die Last auf dem virtuellen Desktop reduziert.
  
Es gibt drei Lösungen für die VDI-Plug-In-Komponente, die von Microsoft, Citrix oder VMWare angeboten wird. Für neue Bereitstellungen empfiehlt Microsoft die Verwendung der Citrix HDX RealTime Optimization Pack-Lösung oder des VMWare Horizon Virtualization Pack. Das ursprüngliche Lync VDI-Plug-In wird für den Rest des Lebenszyklus weiterhin unterstützt.
  
- Das **Lync VDI-Plug-In** wurde für Lync 2013 entwickelt und ist kompatibel mit dem Lync 2013- oder Skype for Business 2015-Client, der auf einem virtuellen Desktop ausgeführt wird. Es ist eine eigenständige Anwendung, die auf dem lokalen Computer installiert wird und die Verwendung lokaler Audio- und Videogeräte mit einem Client auf einem virtuellen Desktop ermöglicht. Das Plug-in erfordert nicht, dass ein Skype for Business-Client auf dem lokalen Computer oder dem Thin Client installiert ist, auf dem Windows 7-, Windows 8- oder Windows Server 2008-Betriebssysteme ausgeführt werden müssen. (Thin Client-Geräte, die diese Betriebssysteme verwenden und von Microsoft unterstützt werden, umfassen: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 und HP t5740e.) Dieses Plug-In wird weiterhin unterstützt, es sind jedoch keine zukünftigen Updates geplant. Für Citrix-basierte virtuelle Umgebungen wird das Citrix RealTime Optimization Pack empfohlen.
    
- **Citrix RealTime Optimization Pack** basiert auf dem Lync VDI-Plug-In und kann mit Lync 2013- oder Skype for Business 2016-Clients auf einem virtuellen Desktop verwendet werden. Es wurde von Citrix und Microsoft gemeinsam entwickelt, um das ursprüngliche VDI-Plug-In zu verbessern. Sie kann auf Clients mit Windows und anderen Betriebssystemen (einschließlich Windows 10, Mac und Linux) installiert werden. Es besteht aus zwei Komponenten: dem RealTime Connector (der auf dem virtuellen Desktop installiert ist) und dem RealTime Media Engine (das auf dem lokalen Computer des Endbenutzers installiert ist). Diese beiden Komponenten ermöglichen es dem lokalen Computer des Benutzers, den Skype for Business-Client zu verwenden, der auf dem virtuellen Desktop ausgeführt wird, und die A/V-Verarbeitung wird auf den lokalen Computer verschoben. Für Citrix-basierte virtuelle Desktopumgebungen wird das Citrix RealTime Optimization Pack empfohlen, und weitere Unterstützung ist geplant.
    
- Mit **dem VMWare Horizon Virtualization Pack** für Skype for Business, das in Zusammenarbeit mit VMWare entwickelt wurde, können Sie Skype for Business auf einem virtuellen Desktop bereitstellen und gleichzeitig eine großartige Benutzererfahrung bieten. Die Lösung verwendet ein Medienmodul auf dem Client, um eine optimierte Lösung zu erstellen. Der Clientendpunkt bietet Funktionen für die Medienentladung für Audio- und Videoanrufe. Diese Lösung, die Audio und Video entweder direkt zwischen Endpunkten für eine 1:1-Zusammenarbeit bereitstellen oder an eine zentrale Multipoint Control Unit (MCU) für Konferenzanrufe oder Besprechungen mit mehrerenPartys ausliefern kann.
    
> [!NOTE]
> Die Skype for Business Basic-Clients werden mit dem Citrix HDX RealTime Optimization Pack oder dem VMWare Horizon Virtualization Pack nicht unterstützt. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Das Citrix VDI-Umgebungs-Plug-In (ein Feature von XenApp und XenDesktop) ist kompatibel mit Lync 2013 und Skype for Business 2015 und 2016 (vollständige Clients mit beliebigem Klick zum Ausführen des Installationsprogramms oder MSI-Installationsprogramme, die nach dem Januar 2017 PU veröffentlicht wurden), die auf einem virtuellen Desktop installiert sind. Die allgemeine Funktionsweise basiert auf dem Microsoft Lync VDI-Plug-In, funktioniert jedoch auf einer größeren Vielfalt von Clientbetriebssystemen, einschließlich Windows 10, Macintosh und Linux.
  
Eine vollständige Liste der Features und unterstützten Technologien finden Sie auf der Citrix-Website unter "Bereitstellen von Microsoft Skype for Business an [XenApp- und XenDesktop-Benutzer".](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)
  
Weitere Informationen finden Sie unter den folgenden Links:
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Technische Übersicht](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business Feature Support](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

Die VDI-Umgebungslösung von VMWare ist kompatibel mit Vollständigen Skype for Business 2015- und 2016-Clients, die auf einem virtuellen Desktop installiert sind. Die allgemeine Funktionsweise basiert auf dem Microsoft Lync VDI-Plug-In, funktioniert jedoch auf einer größeren Vielfalt von Clientbetriebssystemen, einschließlich Windows 10, Macintosh und Linux. 
  
Eine vollständige Diskussion über Features und unterstützte Technologien finden Sie auf der Website von VMWare unter den folgenden Links:
  
- [Neues in VMware Horizon 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon Virtualization Pack for Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business mit VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsofts Lync VDI-Plug-In
<a name="Citrix_RT"> </a>

Bei der Microsoft Lync VDI-Plug-In-Lösung muss sich der Benutzer auf einem Windows-Computer oder -Thin Client und das Lync VDI-Plug-In von Microsoft installieren, um Audio-/Videostreams vom Client auf dem virtuellen Desktop zu verarbeiten. Ein Benutzer hat:
  
1. Schließen Sie ein Audio-/Videogerät (z. B. ein Headset oder eine Kamera) an einen lokalen Computer an.
    
2. Stellen Sie über einen Lync 2013- oder Skype for Business 2015-Client eine Verbindung mit einem virtuellen Remotedesktop herzustellen.
    
3. Geben Sie die Anmeldeinformationen für Skype for Business auf dem virtuellen Desktop ein.
    
4. Geben Sie die Benutzeranmeldeinformationen erneut ein, um eine Verbindung mit dem Lync VDI-Plug-In auf dem lokalen Windows-Computer oder dem Thin Client herzustellen.
    
Nachdem eine Verbindung hergestellt wurde, ist der Benutzer bereit, Audio- und Videoanrufe zu machen und zu empfangen. Der Datenverkehr im Netzwerk und die Last auf dem virtuellen Desktop werden minimiert, da der lokale Computer die Audio-/Videoverarbeitung verarbeitet.
  
Das Lync VDI-Plug-In von Microsoft wird nur unter bestimmten Windows-Betriebssystemen unterstützt und unterstützt nur Lync 2013- oder Skype for Business 2015-Clients. Weitere [Informationen zu unterstützten Technologien](vdi-environments.md#Supported_virt) und Einschränkungen finden Sie unter "Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen".
  
Weitere Informationen finden Sie unter den folgenden Links:
  
- [Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen](vdi-environments.md#Supported_virt)
    
- [Voraussetzungen für das Lync VDI-Plug-In](vdi-environments.md#VDI_prereq)
    
- [Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix Knowledge Center-Artikel [CTX138408](https://support.citrix.com/article/CTX138408)
    
Das Microsoft VDI-Plug-In ist im [Microsoft Lync VDI 2013-Plug-In (32 Bit)](https://www.microsoft.com/download/details.aspx?id=35457) oder [im Microsoft Lync VDI 2013-Plug-In (64 Bit)](https://www.microsoft.com/download/details.aspx?id=35454)verfügbar. Dieses Plug-In wird trotz des Namens vom Skype for Business 2015-Client unterstützt.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen
<a name="Supported_virt"> </a>

Das Lync VDI-Plug-In ermöglicht Audio- und Videoanrufe für unterstützte Virtualisierungstechnologien. In Übereinstimmung mit den standardmäßigen Telefonbestimmungen ist auch Unterstützung für E911 enthalten. In den folgenden Abschnitten werden die Virtualisierungstechnologien beschrieben, die vom Lync VDI-Plug-In unterstützt werden, sowie die bekannten Featureeinschränkungen.
  
#### <a name="support-for-virtualization-technologies"></a>Unterstützung für Virtualisierungstechnologien

Das Lync VDI-Plug-In unterstützt vollständige Desktop-Remotesitzungen im Szenario für persönliche virtuelle Desktops, jedoch nicht im Remotedesktopsitzungsszenario. Diese Szenarien können wie folgt beschrieben werden:
  
- **Unterstützt: Personalisierte virtuelle Desktops oder Virtual Desktop Infrastructure (VDI).** In diesem Szenario meldet sich jeder Benutzer an einem anpassbaren virtuellen Desktop an und kann Dateien auf dem Desktop speichern, die sitzungsübergreifend beibehalten werden. Microsoft Remote Desktop Services und VMware Horizon View sind Beispielimplementierungsbeispiele, die für die Verwendung mit Skype for Business 2015 getestet wurden. Weitere Implementierungen, die einer Überprüfung unterzogen werden, sind Citrix XenDesktop. Informationen zu anbieterspezifischen VDI-Umgebungen und Clienthardware, die von Microsoft getestet wurden, finden Sie unter ["Für Microsoft Lync qualifizierte Infrastruktur".](https://go.microsoft.com/fwlink/?LinkID=313435)
    
- **Nicht unterstützt: Remotedesktopsitzungen.** In diesem Szenario meldet sich jeder Benutzer bei einer generischen virtuellen Desktopsitzung an, die nicht angepasst werden kann. Beispiele hierfür sind Microsoft Remote Desktop Sessions (RDSH) und Citrix XenApp in Kombination mit Citrix Receiver.
    
Das Lync VDI-Plug-In unterstützt keine anderen Virtualisierungstechnologien, z. B. Anwendungsvirtualisierung, die die Verwendung einer Anwendung ermöglicht, ohne dass die vollständige Anwendung lokal installiert werden muss. Beispiele für Implementierungen sind Citrix XenApp und Microsoft Application Virtualization (App-V). Anwendungsstreaming, Anwendungsremoting und gemischte Virtualisierungsmodi (z. B. Anwendungsremoting in vollständiger Desktopremoting) werden nicht unterstützt.
  
Das Lync VDI-Plug-In wurde für die Verwendung plattformunabhängiger APIs entwickelt, die als dynamische virtuelle Kanäle (Dynamic Virtual Channels, DVCs) bezeichnet werden. Szenarien, die nicht explizit unterstützt werden, finden Sie unter Supportanweisungen des VDI-Lösungsanbieters.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Voraussetzungen für das Lync VDI-Plug-In
<a name="VDI_prereq"> </a>

In einer VDI-Umgebung müssen die virtuellen Computer und der lokale Computer des Benutzers die in diesem Abschnitt beschriebenen Anforderungen erfüllen.
  
> [!NOTE]
>  Ihr Virtualisierungslösungsanbieter kann Details zur Installation und Bereitstellung der Umgebung bereitstellen. Allgemeine Informationen zur Bereitstellung einer virtualisierten Umgebung basierend auf Hyper-V und Remotedesktopdiensten finden Sie in den folgenden Artikeln in der Microsoft Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remotedesktopdienste in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Virtuelle Computer müssen mit Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Service Packs konfiguriert werden.
  
Der lokale Computer des Benutzers muss die folgenden Anforderungen erfüllen:
  
- Der Benutzer muss in Skype for Business Server oder Lync Server 2013 gespeichert sein.
    
- Auf dem lokalen Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1 oder Windows 8.
    
- Wenn Sie Remotedesktopdienste verwenden, wählen Sie das 32-Bit- oder 64-Bit-Lync-VDI-Plug-In aus, um dem Betriebssystem des lokalen Computers zu entsprechen. Es ist nicht erforderlich, dass sowohl der lokale Computer als auch der virtuelle Computer über 32-Bit- oder 64-Bit-Betriebssysteme verfügen. Wenn Sie eine andere Virtualisierungslösung oder Plattform verwenden, lesen Sie die Anforderungen Ihres Anbieters.
    
- Auf dem lokalen Computer muss die neueste [Version des Remotedesktopclients ausgeführt werden.](https://go.microsoft.com/fwlink/p/?LinkId=268032) Installieren Sie die neuesten Updates des Remotedesktopdiensteclients von Microsoft oder die neueste Remotedesktopclientsoftware von Ihrem Virtualisierungslösungsanbieter. 
    
- Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist. Informationen zum Konfigurieren dieser Einstellungen für die Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt, "So konfigurieren Sie Einstellungen für die Remotedesktopverbindung". 
    
Das Microsoft VDI-Plug-In ist im [Microsoft Lync VDI 2013-Plug-In (32 Bit)](https://www.microsoft.com/download/details.aspx?id=35457) oder [im Microsoft Lync VDI 2013-Plug-In (64 Bit)](https://www.microsoft.com/download/details.aspx?id=35454)verfügbar.
  
#### <a name="known-feature-limitations"></a>Bekannte Featureeinschränkungen
<a name="VDI_prereq"> </a>

Folgende Einschränkungen sind bekannt, wenn Sie den Skype for Business 2015-Client in einer VDI-Umgebung verwenden:
  
Es gibt eingeschränkte Unterstützung für Die Anrufdelegierung und die Anonymisierungsfeatures des Reaktionsgruppe-Agents.
  
Folgende Features werden nicht unterstützt:
  
- Integrierte Optimierungsseiten für Audio- und Videogeräte
    
- Video mit mehrfacher Ansicht.
    
- Aufzeichnen von Konversationen
    
- Anonyme Teilnahme an Besprechungen (d. h. Teilnahme an Skype for Business-Besprechungen, die von einer Organisation gehostet werden, die keinen Verbund mit Ihrer Organisation besteht).
    
- Verwenden des Lync VDI-Plug-Ins zusammen mit einem Lync Phone Edition-Gerät.
    
- Anrufkontinuität im Fall eines Netzwerkausfalls
    
- Angepasste Klingeltöne und Wartemusikfunktionen.
    
Das Lync VDI-Plug-In wird in Microsoft 365- oder Office 365-Umgebungen nicht unterstützt.
  
> [!NOTE]
> Das Citrix RealTime Optimization Pack unterstützt Microsoft 365 und Office 365. Informationen zu Citrix-basierten virtuellen Umgebungen finden Sie in der [Technischen](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) Übersichtsdokumentation von Citrix für die Liste der unterstützten Features und Versionen.
  
## <a name="see-also"></a>Siehe auch
<a name="Citrix_RT"> </a>

[Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

