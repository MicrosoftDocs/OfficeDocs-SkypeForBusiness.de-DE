---
title: Planen für Skype for Business in VDI-Umgebungen
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/9/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: In diesem Thema werden Planungsaspekte für die Verwendung von Skype für Unternehmen beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop.
ms.openlocfilehash: facf154940b7a82ddc41ac07b87a8af1a5313f5e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planen für Skype for Business in VDI-Umgebungen
 
In diesem Thema werden Planungsaspekte für die Verwendung von Skype für Unternehmen beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop. 
  
Eine VDI-Umgebung (Virtual Desktop Infrastructure) wird in einigen Organisationen verwendet, in denen Sicherheit und Complianceprobleme besonders sensibel sind. Die Benutzer arbeiten über Remotedesktopdienste oder eine ähnliche Remoteverbindung auf einem virtuellen Desktop mit allen ihren Desktopanwendungen und -dateien. Verwendung von Skype für Unternehmen mit vollständigen Audio- und Videodaten bei einer Verbindung kann es muss mit dem starker Auslastung von Audio und Video Verarbeitung auf dem Client auf einem virtuellen Desktop verwaltet. Zusätzlicher VDI-Plug-in-Software verfügbar ist, die die Verarbeitung auf dem lokalen Computer des Endbenutzers verlagert und reduziert die Last auf dem virtuellen Desktop.
  
Es sind drei Lösungen für die VDI-Plug-in-Komponente, angeboten von Microsoft, Citrix oder VMWare verfügbar. Für die neue Bereitstellung empfiehlt Microsoft die Verwendung der Lösung Citrix HDX-Echtzeit Optimization Pack oder das VMWare Horizont Virtualisierung Pack. Die ursprünglichen Lync VDI-Plug-in wird für den Rest des Lebenszyklus weiterhin unterstützt.
  
- Das **Lync VDI-Plug-in** für Lync 2013 entwickelt wurde und ist kompatibel mit dem Lync 2013 oder Skype für Business 2015-Client auf einem virtuellen Computer ausgeführt. Es handelt sich um eine eigenständige Anwendung, die auf dem lokalen Computer installiert wird und die Verwendung lokaler Audio- und Videogeräte mit einem Client auf einem virtuellen Desktop ermöglicht. Das plug-in erfordert keinen Skype für Business-Client installiert werden soll, auf dem lokalen Computer oder thin-Client, der Betriebssystem Windows 7, Windows 8 oder Windows Server 2008 ausgeführt werden muss. (Thin-Client-Geräte verwenden diesen Betriebssystemen und von Microsoft unterstützt einschließen: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 und HP t5740e.) Mit diesem plug-in wird weiterhin unterstützt, jedoch keine zukünftige Updates geplant werden. Für Citrix-basierte virtuelle Umgebungen wird Citrix RealTime Optimization Pack empfohlen.
    
- Das **Citrix Echtzeit Optimization Pack** basiert auf dem Lync-VDI-Plug-in und arbeitet mit Lync 2013 oder Skype Business 2016 Clients auf einem virtuellen Computer. Es wurde gemeinsam von Citrix und Microsoft als Verbesserung des ursprünglichen VDI-Plug-Ins entwickelt. Es kann auf Clients unter Windows- und Nicht-Windows-Betriebssystemen (einschließlich Windows 10, Mac und Linux) installiert werden. Es besteht aus zwei Komponenten: der Echtzeit-Verbindung (die auf dem virtuellen Desktop installiert ist) und das Datenbankmodul der Echtzeit-Medien (die auf dem lokalen Computer des Endbenutzers installiert ist). Diese zwei Komponenten können lokale Computer des Benutzers mithilfe der Skype für Business-Client auf dem virtuellen Desktop mit dem A / V-Verarbeitung auf dem lokalen Computer verschoben. Für Citrix-basierte virtuelle Desktopumgebungen wird Citrix RealTime Optimization Pack empfohlen, für das weitere Unterstützung geplant ist.
    
- Das **VMWare Horizont Virtualisierung Pack** für Skype für Unternehmen, bei der Zusammenarbeit mit VMWare entwickelt können Sie Skype für Unternehmen in einer virtuellen Desktop anzubieten, und einen größeren Benutzerkomfort übermitteln. Die Lösung funktioniert durch die Nutzung von einer Medien-Modul auf dem Client eine optimierte Lösung, mit der Bereitstellung von Medien Clientendpunkt erstellen Abladung von Funktionen für Audio-und Videoanrufe. Diese Lösung, die übermitteln Audio und Video entweder direkt zwischen den Endpunkten für die Zusammenarbeit mit Angebot oder Abladung von an einem zentralen Multipoint Control Unit (MCU) für Konferenzen mit mehreren Teilnehmern Telefonkonferenzen oder Besprechungen kann.
    
> [!NOTE]
> Die Skype für grundlegende 2015 Business oder 2016 Clients werden mit Citrix HDX-Echtzeit Optimization Pack oder das VMWare Horizont Virtualisierung Pack nicht unterstützt. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Citrix VDI-Umgebung-Plug-in (ein Feature von XenApp und XenDesktop) ist kompatibel mit Lync 2013 und Skype für Business 2015 und 2016 (vollständige Clients verwenden alle klicken Sie zum Ausführen der Installer oder MSI-Installer nach Januar 2017 PU veröffentlicht)-Clients, die auf einem virtuellen installiert Desktop. Seine Funktionalität basiert auf der Microsoft Lync-VDI-Plug-in, funktioniert aber auf einer größeren Anzahl von Client-Betriebssysteme, einschließlich Windows 10, Macintosh- und Linux.
  
Eine vollständige Liste der Features und unterstützten Technologien kann auf der Website Citrix zur [Bereitstellung von Microsoft Skype für Unternehmen XenApp und XenDesktop Benutzer](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)gefunden werden.
  
Weitere Informationen finden Sie unter folgenden Links:
  
- Citrix [HDX-Echtzeit Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Technische Übersicht](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype für die Unterstützung von Business](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Horizon VMWare Virtualisierung Pack
<a name="Citrix_RT"> </a>

VMWare VDI-Umgebung Lösung ist kompatibel mit Skype für Business 2015 und 2016 vollständige Clients, die auf einem virtuellen Computer installiert. Seine Funktionalität basiert auf der Microsoft Lync-VDI-Plug-in, funktioniert aber auf einer größeren Anzahl von Client-Betriebssysteme, einschließlich Windows 10, Macintosh- und Linux. 
  
Eine umfassende Erläuterung der Features und unterstützten Technologien finden Sie auf der VMWare-Website unter den folgenden Links:
  
- [Neuigkeiten in VMware Horizont 7.4 &amp; Horizont Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon Virtualisierung Pack für Skype für Unternehmen](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype für Unternehmen mit VMWare Horizont](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Lync VDI-Plug-In von Microsoft
<a name="Citrix_RT"> </a>

Der Benutzer hat bei der Microsoft Lync-VDI-Plug-in-Lösung auf einem Windows-Computer oder thin-Client und von Microsoft Lync-VDI-Plug-in zur Verarbeitung von a/v-Streams vom Client auf dem virtuellen Desktop installiert haben. Die Benutzer führen die folgenden Schritte aus:
  
1. Verbinden eines Audio-/Video-Geräts (beispielsweise eines Headsets oder einer Kamera) mit einem lokalen Computer
    
2. Eine Verbindung mit einem virtuellen Remotedesktop mit einem Lync 2013 oder Skype für Business 2015 Client.
    
3. Geben Sie Anmeldeinformationen für Skype für Unternehmen, auf dem virtuellen Desktop.
    
4. Geben Sie Anmeldeinformationen des Benutzers zum Herstellen einer Verbindungs mit der Lync-VDI-Plug-in auf dem lokalen Windows-Computer oder thin-Client erneut ein.
    
Wenn eine Verbindung hergestellt ist, können die Benutzer Audio- und Videoanrufe tätigen und empfangen. Der Datenverkehr im Netzwerk und die Last des virtuellen Desktops werden minimiert, da die Audio-/Videoverarbeitung auf dem lokalen Computer stattfindet.
  
Microsoft Lync-VDI-Plug-in wird nur auf bestimmten Windows-Betriebssystemen unterstützt und nur Lync 2013 oder Skype für Business 2015 Clients unterstützt. Weitere Details zu den unterstützten Technologien und zu Einschränkungen finden Sie unter [Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen](vdi-environments.md#Supported_virt).
  
Weitere Informationen finden Sie unter folgenden Links:
  
- [Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen](vdi-environments.md#Supported_virt)
    
- [Voraussetzungen für das Lync VDI-Plug-In](vdi-environments.md#VDI_prereq)
    
- [Bereitstellen des Lync VDI-Plug-in mit Skype für Business Server 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix Knowledge Center Artikel [CTX138408](https://support.citrix.com/article/CTX138408)
    
Der Microsoft VDI-Plug-in ist unter [2013 für Microsoft Lync VDI-Plug-in (32 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) oder [2013 für Microsoft Lync VDI-Plug-in (64 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)verfügbar. Diese-Plug-in wird mit der Skype für trotz des Namens der Business 2015-Client unterstützt.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen
<a name="Supported_virt"> </a>

Das Lync VDI-Plug-in ermöglicht Audio- und Videogeräte für unterstützte Virtualisierungstechnologien aufrufen. Gemäß Standardtelefonvorschriften ist auch Unterstützung für E911 enthalten. In den folgenden Abschnitten wird beschrieben, die Virtualisierungstechnologien, die durch das Lync VDI-Plug-in und die bekannte Einschränkungen unterstützt werden.
  
#### <a name="support-for-virtualization-technologies"></a>Unterstützung für Virtualisierungstechnologien

Das Lync VDI-Plug-in unterstützt Vollbildansicht Remotesitzungen im persönlichen virtuellen desktop Szenario, aber nicht in der Remotedesktopsitzung-Szenario. Diese Szenarien können wie folgt beschrieben werden:
  
- **Unterstützt: Personalisierte virtuelle Desktops oder virtuelle Desktopinfrastruktur (Virtual Desktop Infrastructure, VDI).** In diesem Szenario melden sich die einzelnen Benutzer bei einem anpassbaren virtuellen Desktop an und können Dateien auf dem Desktop speichern, die sitzungsübergreifend bestehen bleiben. Microsoft Remote Desktop Services und VMware Horizont Ansicht sind Beispiel-Implementierungen, die für die Verwendung mit Skype für Business 2015 getestet wurden. Eine weitere validierte Implementierung ist Citrix XenDesktop. Informationen zu herstellerspezifischen VDI-Umgebung und Client-Hardware, die von Microsoft getestet wurden, finden Sie unter [Infrastruktur für Microsoft Lync qualifizierte](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Nicht unterstützt: Remotedesktopsitzungen.** In diesem Szenario melden sich die einzelnen Benutzer bei einer allgemeinen virtuellen Desktopsitzung an, die nicht angepasst werden kann. Beispiele für Microsoft Remote Desktop Sitzungen (RDSH) und Citrix XenApp in Kombination mit Citrix Empfänger.
    
Das Lync VDI-Plug-in unterstützt keine anderen Virtualisierungstechnologie wie Anwendungsvirtualisierung, die die Verwendung einer Anwendung ermöglicht, ohne Installation von die vollständige Anwendung lokal. Zu den Beispielimplementierungen gehören Citrix XenApp und Microsoft Application Virtualization (App-V). Anwendungsstreaming, Anwendungsremoting und gemischte Virtualisierungsmodi (zum Beispiel Anwendungsremoting in vollem Desktopremoting) werden nicht unterstützt.
  
Das Lync VDI-Plug-in wurde entwickelt, Plattform-unabhängige APIs, so genannte dynamischen virtuellen Kanälen (DVCs) verwenden. Informationen zu nicht ausdrücklich unterstützten Szenarien finden Sie in den Supportaussagen des VDI-Lösungsanbieters.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Voraussetzungen für das Lync VDI-Plug-In
<a name="VDI_prereq"> </a>

In einer VDI-Umgebung müssen die virtuellen Computer und lokalen Computer des Benutzers, die in diesem Abschnitt beschriebenen Anforderungen erfüllen.
  
> [!NOTE]
>  Informationen zum Installieren und Bereitstellen der Umgebung erhalten Sie vom Anbieter Ihrer Virtualisierungslösung. Allgemeine Informationen zur Bereitstellung einer virtualisierten Umgebung basierend auf Hyper-V und Remote Desktop Services finden Sie unter den folgenden Artikeln in der Microsoft TechNet Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Services in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Virtuelle Computer muss mit Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Servicepacks konfiguriert sein.
  
Lokale Computer des Benutzers muss die folgenden Anforderungen erfüllen:
  
- Der Benutzer muss in Skype für Business Server 2015 oder Lync Server 2013 verwaltet werden.
    
- Der lokale Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1 oder Windows 8 ausgeführt werden.
    
- Wenn Sie Remote Desktop Services verwenden, wählen Sie die 32-Bit oder 64-Bit-Lync-VDI-Plug-in mit Betriebssystem des lokalen Computers übereinstimmt. Es ist nicht notwendig, dass sowohl auf dem lokalen Computer als auch in der virtuellen Maschine 32-Bit- oder 64-Bit-Betriebssysteme installiert sind. Wenn Sie eine andere Virtualisierungslösung oder -plattform verwenden, informieren Sie sich über die Anforderungen des jeweiligen Anbieters.
    
- Der lokale Computer muss die [neueste Version von Remotedesktop-Clients](https://go.microsoft.com/fwlink/p/?LinkId=268032)ausgeführt werden. Installieren Sie die neuesten Updates von Remote Desktop Services Client von Microsoft oder die neueste remote desktop Clientsoftware vom Lösungsanbieter Virtualisierung. 
    
- Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist. Zum Konfigurieren dieser Einstellungen für Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt "So"konfigurieren Sie Einstellungen der Remotedesktopverbindung. 
    
Der Microsoft VDI-Plug-in ist unter [2013 für Microsoft Lync VDI-Plug-in (32 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) oder [2013 für Microsoft Lync VDI-Plug-in (64 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)verfügbar.
  
#### <a name="known-feature-limitations"></a>Bekannte Funktionseinschränkungen
<a name="VDI_prereq"> </a>

Die folgenden Einschränkungen bekanntermaßen bei Verwendung der Skype für Business 2015 Client in einer VDI-Umgebung:
  
Eingeschränkte Unterstützung für die Anrufdelegierung und Antwort Gruppe Agentenanonymisierung Features ist vorhanden.
  
Folgende Features werden nicht unterstützt:
  
- Integrierte Optimierungsseiten für Audio- und Videogeräte
    
- Mehransicht für Video
    
- Aufzeichnen von Konversationen
    
- Teilnehmen an Besprechungen anonym (d. h., Skype für Business Besprechungen, die von einer Organisation, die nicht Verbund ist mit Ihrer Organisation gehostet beitreten).
    
- Verwenden die Lync-VDI-Plug-in, zusammen mit einem Lync Phone Edition-Gerät.
    
- Anrufkontinuität im Fall eines Netzwerkausfalls
    
- Features für benutzerdefinierte Klingeltöne und Wartemusik
    
Das Lync VDI-Plug-in wird in einer Office 365-Umgebung nicht unterstützt.
  
> [!NOTE]
> Citrix RealTime Optimization Pack unterstützt Office 365. Überprüfen Sie für Citrix-basierten virtuellen Umgebungen Citrix [Technische Übersicht über die](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) Dokumentation für die Liste der unterstützten Funktionen und Versionen.
  
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="Citrix_RT"> </a>

[Bereitstellen des Lync VDI-Plug-in mit Skype für Business Server 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

