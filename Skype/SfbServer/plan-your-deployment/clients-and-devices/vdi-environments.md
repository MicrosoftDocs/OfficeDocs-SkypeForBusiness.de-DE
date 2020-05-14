---
title: Planen von Skype for Business in VDI-Umgebungen
author: lanachin
ms.author: v-lanac
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
description: In diesem Thema werden Planungsüberlegungen für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remote Desktop erläutert.
ms.openlocfilehash: 6886eab8a13db852e0aa86b63d08aa33f82fdaed
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219525"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planen von Skype for Business in VDI-Umgebungen
 
In diesem Thema werden Planungsüberlegungen für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remote Desktop erläutert. 
  
Eine VDI-Umgebung (Virtual Desktop Infrastructure) wird in einigen Organisationen verwendet, in denen Sicherheits-und Compliance-Probleme besonders sensibel sind. Ihre Benutzer erledigen Ihre Arbeit auf einem virtuellen Desktop mit allen ihren Desktopanwendungen und Dateien mithilfe von Remotedesktopdiensten oder einer ähnlichen Remoteverbindung. Das Verwenden von Skype for Business mit vollständigem Audio-und Videomaterial in einer solchen Verbindung erfordert hohe Lasten der Audio-und Videoverarbeitung auf dem Client, der auf einem virtuellen Desktop verwaltet wird. Es steht eine zusätzliche VDI-Plug-in-Software zur Verfügung, die diese Verarbeitung auf den lokalen Computer des Endbenutzers abgibt und die Last auf dem virtuellen Desktop reduziert.
  
Für die VDI-Plug-in-Komponente, die von Microsoft, Citrix oder VMware angeboten wird, stehen drei Lösungen zur Verfügung. Für neue Bereitstellungen empfiehlt Microsoft, entweder die Citrix HDX Realtime Optimization Pack-Lösung oder das VMware Horizon Virtualization Pack zu verwenden. Das ursprüngliche lync VDI-Plug-in wird weiterhin für den Rest seines Lebenszyklus unterstützt.
  
- Das **lync VDI-Plug-in** wurde für lync 2013 entwickelt und ist entweder mit dem lync 2013-oder Skype for Business 2015-Client kompatibel, der auf einem virtuellen Desktop läuft. Es handelt sich um eine eigenständige Anwendung, die auf dem lokalen Computer installiert wird und die Verwendung lokaler Audio-und Videogeräte mit einem Client auf einem virtuellen Desktop ermöglicht. Für das Plug-in muss kein Skype for Business Client auf dem lokalen Computer oder Thin Client installiert werden, der Windows 7-, Windows 8-oder Windows Server 2008-Betriebssysteme ausführen muss. (Thin Client-Geräte, die diese Betriebssysteme verwenden und von Microsoft unterstützt werden, umfassen: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP T610 und HP t5740e.) Dieses Plug-in wird weiterhin unterstützt, aber es sind keine zukünftigen Updates geplant. Für Citrix-basierte virtuelle Umgebungen wird das Citrix Realtime Optimization Pack empfohlen.
    
- Das **Citrix Realtime Optimization Pack** baut auf dem lync VDI-Plug-in auf und kann mit lync 2013-oder Skype for Business 2016-Clients auf einem virtuellen Desktop verwendet werden. Es wurde von Citrix und Microsoft gemeinsam entwickelt, um das ursprüngliche VDI-Plug-in zu verbessern. Es kann auf Clients mit Windows-und nicht-Windows-Betriebssystemen (einschließlich Windows 10, Mac und Linux) installiert werden. Es besteht aus zwei Komponenten: dem Realtime-Connector (der auf dem virtuellen Desktop installiert ist) und dem Realtime Media Engine (der auf dem lokalen Computer des Endbenutzers installiert ist). Diese beiden Komponenten ermöglichen dem lokalen Computer des Benutzers, den auf dem virtuellen Desktop ausgeführten Skype for Business Client zu verwenden, wobei die A/V-Verarbeitung auf den lokalen Computer verschoben wird. Für Citrix-basierte virtuelle Desktopumgebungen wird das Citrix Realtime Optimization Pack empfohlen, und weitere Unterstützung ist geplant.
    
- Mit dem **VMware Horizon Virtualization Pack** für Skype for Business, das in Zusammenarbeit mit VMware entwickelt wurde, können Sie Skype for Business auf einem virtuellen Desktop bereitstellen und gleichzeitig eine großartige Benutzeroberfläche bieten. Die Lösung funktioniert durch die Nutzung eines medienmoduls auf dem Client, um eine optimierte Lösung zu erstellen, wobei der Clientendpunkt Medien abladungs Funktionen für Audio-und Videoanrufe bereitstellt. Diese Lösung, die Audio und Video entweder direkt zwischen den Endpunkten für eine einzelne Zusammenarbeit bereitstellen oder an eine zentrale Multipoint-Steuereinheit (MCU) für mehrteilige Telefonkonferenzen oder Besprechungen ablegen kann.
    
> [!NOTE]
> Die Skype for Business Basic-Clients werden mit dem Citrix HDX Realtime Optimization Pack oder dem VMware Horizon Virtualization Pack nicht unterstützt. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX Realtime Optimization Pack
<a name="Citrix_RT"> </a>

Das Plug-in für die Citrix-VDI-Umgebung (ein Feature von XenApp und XenDesktop) ist mit lync 2013 und Skype for Business 2015 und 2016 (vollständige Clients, die ein beliebiges Click-to-Run-Installationsprogramm ausführen, oder MSI-Installationsprogramme, die auf einem virtuellen Desktop installiert sind, nach Januar 2017 PU) kompatibel. Die gesamte Funktion basiert auf dem Microsoft lync VDI-Plug-in, funktioniert jedoch auf einer größeren Vielzahl von Clientbetriebssystemen, einschließlich Windows 10, Macintosh und Linux.
  
Eine vollständige Liste der Features und unterstützten Technologien finden Sie auf der Citrix-Website unter [Delivering Microsoft Skype for Business to XenApp and XenDesktop users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Lesen Sie die folgenden Links, um weitere Informationen zu erhalten:
  
- Citrix [HDX Realtime Optimization Pack 2,1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Technische Übersicht](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Unterstützung von CTX200279 Skype for Business-Features](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMware Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

Die VDI-Umgebungs Lösung von VMware ist mit Skype for Business 2015-und 2016-vollständigen Clients kompatibel, die auf einem virtuellen Desktop installiert sind. Die gesamte Funktion basiert auf dem Microsoft lync VDI-Plug-in, funktioniert jedoch auf einer größeren Vielzahl von Clientbetriebssystemen, einschließlich Windows 10, Macintosh und Linux. 
  
Eine umfassende Erläuterung der Features und unterstützten Technologien finden Sie auf der VMware-Website unter den folgenden Links:
  
- [Neuerungen in VMware Horizon 7,4 &amp; Horizon Client 4,7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon Virtualization Pack für Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business mit VMware Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft lync VDI-Plug-in
<a name="Citrix_RT"> </a>

Mit der Microsoft lync VDI-Plug-in-Lösung muss sich der Benutzer auf einem Windows-Computer oder Thin-Client befinden und das Microsoft-Modul lync VDI installiert haben, um Audio/Video-Streams vom Client auf dem virtuellen Desktop zu verarbeiten. Ein Benutzer wird Folgendes tun:
  
1. Schließen Sie ein Audio/Video-Gerät (wie ein Headset oder eine Kamera) an einen lokalen Computer an.
    
2. Stellen Sie eine Verbindung mit einem virtuellen Remote Desktop mit einem lync 2013-oder Skype for Business 2015-Client her.
    
3. Geben Sie Anmeldeinformationen für Skype for Business auf dem virtuellen Desktop ein.
    
4. Geben Sie die Benutzeranmeldeinformationen erneut ein, um eine Verbindung mit dem lync VDI-Plug-in auf dem lokalen Windows-Computer oder Thin Client herzustellen.
    
Nachdem eine Verbindung hergestellt wurde, ist der Benutzer bereit, Audio-und Videoanrufe zu tätigen und zu empfangen. Der Datenverkehr im Netzwerk und die Last auf dem virtuellen Desktop werden minimiert, da der lokale Computer die Audio-und Videoverarbeitung verarbeitet.
  
Das lync VDI-Plug-in von Microsoft wird nur auf bestimmten Windows-Betriebssystemen unterstützt und unterstützt nur lync 2013-oder Skype for Business 2015-Clients. Weitere Informationen zu unterstützten Technologien und Einschränkungen finden Sie unter [Supported Virtualization Technologies and known Limitations](vdi-environments.md#Supported_virt) .
  
Lesen Sie die folgenden Links, um weitere Informationen zu erhalten:
  
- [Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen](vdi-environments.md#Supported_virt)
    
- [Voraussetzungen für lync VDI-Plug-ins](vdi-environments.md#VDI_prereq)
    
- [Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix Knowledge Center-Artikel [CTX138408](https://support.citrix.com/article/CTX138408)
    
Das Microsoft VDI-Plugin steht unter [Microsoft lync VDI 2013 Plugin (32 Bit)](https://www.microsoft.com/download/details.aspx?id=35457) oder [Microsoft lync VDI 2013 Plugin (64 Bit)](https://www.microsoft.com/download/details.aspx?id=35454)zur Verfügung. Dieses Plugin wird mit dem Skype for Business 2015-Client trotz des Namens unterstützt.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen
<a name="Supported_virt"> </a>

Das lync VDI-Plug-in ermöglicht Audio-und Videoanrufe für unterstützte Virtualisierungstechnologie. In Übereinstimmung mit den standardmäßigen Telefon Richtlinien ist auch die Unterstützung für E911 enthalten. In den folgenden Abschnitten werden die Virtualisierungstechnologien beschrieben, die vom lync VDI-Plug-in und den bekannten Funktionseinschränkungen unterstützt werden.
  
#### <a name="support-for-virtualization-technologies"></a>Unterstützung für Virtualisierungs-Technologien

Das lync VDI-Plug-in unterstützt vollständige Desktop-Remotesitzungen im Szenario für persönliche virtuelle Desktops, jedoch nicht im Szenario mit Remotedesktopsitzungen. Diese Szenarien können wie folgt beschrieben werden:
  
- **Unterstützt: Personalisierte virtuelle Desktops oder virtuelle Desktopinfrastruktur (VDI).** In diesem Szenario meldet sich jeder Benutzer bei einem anpassbaren virtuellen Desktop an und kann Dateien auf dem Desktop speichern, die in mehreren Sitzungen gespeichert sind. Microsoft Remote Desktop Dienste und VMware Horizon View sind Beispielimplementierungen, die für die Verwendung mit Skype for Business 2015 getestet wurden. Andere Implementierungen, die eine Überprüfung durchlaufen, umfassen Citrix XenDesktop. Informationen zu anbieterspezifischen VDI-Umgebungen und Clienthardware, die von Microsoft getestet wurden, finden Sie unter [für Microsoft lync qualifizierte Infrastruktur](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Nicht unterstützt: Remote Desktop Sitzungen.** In diesem Szenario meldet sich jeder Benutzer bei einer generischen virtuellen Desktopsitzung an, die nicht angepasst werden kann. Beispiele hierfür sind Microsoft Remote Desktop Sitzungen (RDSH) und Citrix XenApp in Kombination mit Citrix Receiver.
    
Das lync VDI-Plug-in unterstützt keine anderen Virtualisierungstechnologien wie Application Virtualization, die die Verwendung einer Anwendung ermöglichen, ohne dass die vollständige Anwendung lokal installiert werden muss. Zu den Beispielimplementierungen Gehören Citrix XenApp und Microsoft Application Virtualization (App-V). Anwendungsstreaming, Anwendungs Remoting und gemischte Virtualisierungs Modi (beispielsweise Anwendungs Remoting in vollständigem Desktop-Remoting) werden nicht unterstützt.
  
Das lync VDI-Plug-in wurde für die Verwendung plattformunabhängiger APIs mit dem Namen Dynamic Virtual Channels (DVCs) entwickelt. Informationen zu Szenarien, die nicht explizit unterstützt werden, finden Sie unter Support Statements vom VDI-Lösungsanbieter.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Voraussetzungen für lync VDI-Plug-ins
<a name="VDI_prereq"> </a>

In einer VDI-Umgebung müssen die virtuellen Computer und der lokale Computer des Benutzers die in diesem Abschnitt beschriebenen Anforderungen erfüllen.
  
> [!NOTE]
>  Ihr Anbieter für die Virtualisierungslösung kann Details zur Installation und Bereitstellung seiner Umgebung bereitstellen. Allgemeine Informationen zum Bereitstelleneiner virtualisierten Umgebung, die auf Hyper-v und Remotedesktopdiensten basiert, finden Sie in den folgenden Artikeln in der Microsoft-Bibliothek: [Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Dienste in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Virtuelle Computer müssen mit Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Service Packs konfiguriert werden.
  
Der lokale Computer des Benutzers muss die folgenden Anforderungen erfüllen:
  
- Der Benutzer muss in Skype for Business Server oder lync Server 2013 verwaltet werden.
    
- Auf dem lokalen Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1 oder Windows 8 installiert sein.
    
- Wenn Sie Remote Desktop Dienste verwenden, wählen Sie das 32-Bit-oder 64-Bit-lync-VDI-VDI-Plug-in entsprechend dem Betriebssystem des lokalen Computers aus. Es ist nicht erforderlich, dass sowohl auf dem lokalen Computer als auch auf dem virtuellen Computer 32-Bit-oder 64-Bit-Betriebssysteme vorhanden sind. Wenn Sie eine andere Virtualisierungslösung oder Plattform verwenden, lesen Sie die Anforderungen Ihres Anbieters.
    
- Auf dem lokalen Computer muss die [neueste Version des Remotedesktopclients](https://go.microsoft.com/fwlink/p/?LinkId=268032)installiert sein. Installieren Sie die neuesten Updates des Remotedesktopdienste-Clients von Microsoft oder die neueste Remote Desktop-Client Software von Ihrem Anbieter für die Virtualisierung. 
    
- Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist. Informationen zum Konfigurieren dieser Einstellungen für die Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt "so konfigurieren Sie Einstellungen für die Remotedesktopverbindung". 
    
Das Microsoft VDI-Plugin steht unter [Microsoft lync VDI 2013 Plugin (32 Bit)](https://www.microsoft.com/download/details.aspx?id=35457) oder [Microsoft lync VDI 2013 Plugin (64 Bit)](https://www.microsoft.com/download/details.aspx?id=35454)zur Verfügung.
  
#### <a name="known-feature-limitations"></a>Bekannte Funktionseinschränkungen
<a name="VDI_prereq"> </a>

Die folgenden Einschränkungen sind bekannt, wenn Sie den Skype for Business 2015-Client in einer VDI-Umgebung verwenden:
  
Es gibt nur eine beschränkte Unterstützung für Anonymisierungs Funktionen für die Anrufdelegierung und den Reaktionsgruppen-Agent.
  
Folgende Features werden nicht unterstützt:
  
- Integrierte Optimierungsseiten für Audio- und Videogeräte
    
- Video mit mehreren Ansichten.
    
- Aufzeichnen von Konversationen
    
- Anonyme Teilnahme an Besprechungen (also Beitritt Skype for Business Besprechungen, die von einer Organisation gehostet werden, die nicht mit Ihrer Organisation verbunden ist).
    
- Verwenden des lync VDI-Plug-ins zusammen mit einem lync Phone Edition-Gerät.
    
- Anrufkontinuität im Fall eines Netzwerkausfalls
    
- Angepasste Klingeltöne und Features für die Musik Aufbewahrung.
    
Das lync VDI-Plug-in wird in Microsoft 365-oder Office 365-Umgebungen nicht unterstützt.
  
> [!NOTE]
> Das Citrix Realtime Optimization Pack unterstützt Microsoft 365 und Office 365. Für Citrix-basierte virtuelle Umgebungen lesen Sie Citrix [technische](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) Übersichtsdokumentation zur Liste der unterstützten Features und Versionen.
  
## <a name="see-also"></a>Siehe auch
<a name="Citrix_RT"> </a>

[Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

