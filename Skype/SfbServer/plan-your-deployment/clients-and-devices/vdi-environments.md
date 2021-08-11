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
ms.openlocfilehash: 84a7c289b9c2cc284209861dca35921142fd87e16b3de3b1e42b6c82fb2b8eba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318758"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planen von Skype for Business in VDI-Umgebungen
 
In diesem Thema werden Planungsüberlegungen für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop erläutert. 
  
Eine Virtual Desktop Infrastructure (VDI)-Umgebung wird in einigen Organisationen verwendet, in denen Sicherheits- und Complianceprobleme besonders sensibel sind. Ihre Benutzer erledigen ihre Arbeit auf einem virtuellen Desktop mit all ihren Desktopanwendungen und Dateien über Remotedesktopdienste oder eine ähnliche Remoteverbindung. Die Verwendung von Skype for Business mit vollständigem Audio und Video auf einer solchen Verbindung erfordert eine hohe Audio- und Videoverarbeitung auf dem Client, der auf einem virtuellen Desktop verwaltet wird. Es steht zusätzliche VDI-Plug-In-Software zur Verfügung, die diese Verarbeitung auf den lokalen Computer des Endbenutzers auslädt und die Last auf dem virtuellen Desktop reduziert.
  
Für die VDI-Plug-In-Komponente stehen drei Lösungen zur Verfügung, die von Microsoft, Citrix oder VMWare angeboten werden. Für neue Bereitstellungen empfiehlt Microsoft die Verwendung der Citrix HDX RealTime Optimization Pack-Lösung oder des VMWare Horizon Virtualization Pack. Das ursprüngliche Lync VDI-Plug-In wird für den restlichen Lebenszyklus weiterhin unterstützt.
  
- Das **Lync VDI-Plug-In** wurde für Lync 2013 entwickelt und ist entweder mit dem Lync 2013- oder Skype for Business 2015-Client kompatibel, der auf einem virtuellen Desktop ausgeführt wird. Es handelt sich um eine eigenständige Anwendung, die auf dem lokalen Computer installiert wird und die Verwendung lokaler Audio- und Videogeräte mit einem Client auf einem virtuellen Desktop ermöglicht. Für das Plug-In muss kein Skype for Business-Client auf dem lokalen Computer oder dem Thin Client installiert werden, der Windows 7-, Windows 8- oder Windows Server 2008-Betriebssystemen ausführen muss. (Thin Client-Geräte, die diese Betriebssysteme verwenden und von Microsoft unterstützt werden, umfassen: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 und HP t5740e.) Dieses Plug-In wird weiterhin unterstützt, zukünftige Updates sind jedoch nicht geplant. Für Citrix-basierte virtuelle Umgebungen wird das Citrix RealTime Optimization Pack empfohlen.
    
- Citrix **RealTime Optimization Pack** basiert auf dem Lync VDI-Plug-In und funktioniert mit Lync 2013- oder Skype for Business 2016-Clients auf einem virtuellen Desktop. Es wurde von Citrix und Microsoft gemeinsam entwickelt, um das ursprüngliche VDI-Plug-In zu verbessern. Es kann auf Clients mit Windows und nicht Windows Betriebssystemen installiert werden (einschließlich Windows 10, Mac und Linux). Es besteht aus zwei Komponenten: dem RealTime Connector (der auf dem virtuellen Desktop installiert ist) und dem RealTime Media Engine (das auf dem lokalen Computer des Endbenutzers installiert ist). Diese beiden Komponenten ermöglichen es dem lokalen Computer des Benutzers, den Skype for Business Client zu verwenden, der auf dem virtuellen Desktop ausgeführt wird, wobei die A/V-Verarbeitung auf den lokalen Computer verschoben wird. Für Citrix-basierte virtuelle Desktopumgebungen wird das Citrix RealTime Optimization Pack empfohlen, und weitere Unterstützung ist geplant.
    
- Mit dem **VMWare Horizon Virtualization Pack** für Skype for Business, das in Zusammenarbeit mit VMWare entwickelt wurde, können Sie Skype for Business auf einem virtuellen Desktop bereitstellen und gleichzeitig eine hervorragende Benutzererfahrung bereitstellen. Die Lösung verwendet ein Medienmodul auf dem Client, um eine optimierte Lösung zu erstellen, wobei der Clientendpunkt Medien-Offload-Funktionen für Audio- und Videoanrufe bereitstellt. Diese Lösung kann Audio- und Videodaten entweder direkt zwischen Endpunkten für die Einzelzusammenarbeit bereitstellen oder an eine zentrale Multipoint Control Unit (MCU) für Konferenzanrufe oder Besprechungen mit mehreren Teilnehmern auslagern.
    
> [!NOTE]
> Die Skype for Business Basic-Clients werden mit dem Citrix HDX RealTime Optimization Pack oder dem VMWare Horizon Virtualization Pack nicht unterstützt. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Citrixs VDI-Umgebungs-Plug-In (eine Funktion von XenApp und XenDesktop) ist kompatibel mit Lync 2013- und Skype for Business 2015- und 2016-Clients (Vollständige Clients mit einem klick zum Ausführen des Installationsprogramms oder MSI-Installationsprogramme, die nach dem PU vom Januar 2017 veröffentlicht wurden), die auf einem virtuellen Desktop installiert sind. Die allgemeine Funktionsweise basiert auf dem Microsoft Lync VDI-Plug-In, funktioniert jedoch auf einer größeren Vielfalt von Clientbetriebssystemen, einschließlich Windows 10, Macintosh und Linux.
  
Eine vollständige Liste der Features und unterstützten Technologien finden Sie auf der Citrix-Website unter [Delivering Microsoft Skype for Business to XenApp and XenDesktop Users.](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)
  
Weitere Informationen finden Sie unter den folgenden Links:
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Technische Übersicht](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business-Featureunterstützung](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

Die VDI-Umgebungslösung von VMWare ist mit Skype for Business 2015- und 2016 Full-Clients kompatibel, die auf einem virtuellen Desktop installiert sind. Die allgemeine Funktionsweise basiert auf dem Microsoft Lync VDI-Plug-In, funktioniert jedoch auf einer größeren Vielfalt von Clientbetriebssystemen, einschließlich Windows 10, Macintosh und Linux. 
  
Eine vollständige Erläuterung der Features und unterstützten Technologien finden Sie auf der VMWare-Website unter den folgenden Links:
  
- [Neuigkeiten in VMware Horizon 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon Virtualization Pack für Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business mit VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Lync VDI-Plug-In von Microsoft
<a name="Citrix_RT"> </a>

Mit der Microsoft Lync VDI-Plug-In-Lösung muss sich der Benutzer auf einem Windows Computer oder einem Thin Client befinden und das Lync VDI-Plug-In von Microsoft installiert haben, um Audio-/Videostreams vom Client auf dem virtuellen Desktop zu verarbeiten. Ein Benutzer führt Folgendes aus:
  
1. Verbinden ein Audio-/Videogerät (z. B. ein Headset oder eine Kamera) auf einem lokalen Computer an.
    
2. Verbinden auf einem virtuellen Remotedesktop mit einem Lync 2013- oder Skype for Business 2015-Client.
    
3. Geben Sie Anmeldeinformationen für Skype for Business auf dem virtuellen Desktop ein.
    
4. Geben Sie erneut Benutzeranmeldeinformationen ein, um eine Verbindung mit dem Lync VDI-Plug-In auf dem lokalen Windows Computer oder dem Thin Client herzustellen.
    
Nachdem eine Verbindung hergestellt wurde, kann der Benutzer Audio- und Videoanrufe tätigen und empfangen. Der Datenverkehr im Netzwerk und die Last auf dem virtuellen Desktop werden minimiert, da der lokale Computer die Audio-/Videoverarbeitung verarbeitet.
  
Das Lync VDI-Plug-In von Microsoft wird nur auf bestimmten Windows Betriebssystemen unterstützt und unterstützt nur Lync 2013- oder Skype for Business 2015-Clients. Weitere Informationen zu unterstützten Technologien und Einschränkungen finden Sie unter ["Unterstützte Virtualisierungstechnologien" und bekannte Einschränkungen.](vdi-environments.md#Supported_virt)
  
Weitere Informationen finden Sie unter den folgenden Links:
  
- [Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen](vdi-environments.md#Supported_virt)
    
- [Voraussetzungen für Das Lync VDI-Plug-In](vdi-environments.md#VDI_prereq)
    
- [Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix Knowledge Center-Artikel [CTX138408](https://support.citrix.com/article/CTX138408)
    
Das Microsoft VDI-Plug-In ist im [Microsoft Lync VDI 2013-Plug-In (32 Bit)](https://www.microsoft.com/download/details.aspx?id=35457) oder [im Microsoft Lync VDI 2013-Plug-In (64 Bit)](https://www.microsoft.com/download/details.aspx?id=35454)verfügbar. Dieses Plug-In wird trotz des Namens mit dem Skype for Business 2015-Client unterstützt.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen
<a name="Supported_virt"> </a>

Das Lync VDI-Plug-In ermöglicht Audio- und Videoanrufe für unterstützte Virtualisierungstechnologien. In Übereinstimmung mit den standardtelefonrechtlichen Bestimmungen ist auch Unterstützung für E911 enthalten. In den folgenden Abschnitten werden die Virtualisierungstechnologien beschrieben, die vom Lync VDI-Plug-In unterstützt werden, sowie die bekannten Funktionseinschränkungen.
  
#### <a name="support-for-virtualization-technologies"></a>Unterstützung für Virtualisierungstechnologien

Das Lync VDI-Plug-In unterstützt vollständige Desktop-Remotesitzungen im persönlichen virtuellen Desktopszenario, jedoch nicht im Remotedesktop-Sitzungsszenario. Diese Szenarien können wie folgt beschrieben werden:
  
- **Unterstützt: Personalisierte virtuelle Desktops oder virtuelle Desktopinfrastruktur (Virtual Desktop Infrastructure, VDI).** In diesem Szenario meldet sich jeder Benutzer bei einem anpassbaren virtuellen Desktop an und kann Dateien auf dem Desktop speichern, die sitzungsübergreifend bestehen bleiben. Microsoft-Remotedesktop Dienste und VMware Horizon View sind Beispielimplementierungen, die für die Verwendung mit Skype for Business 2015 getestet wurden. Weitere Implementierungen, die einer Überprüfung unterzogen werden, sind Citrix XenDesktop. Informationen zu anbieterspezifischen VDI-Umgebungen und Clienthardware, die von Microsoft getestet wurden, finden Sie unter ["Für Microsoft Lync qualifizierte Infrastruktur".](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)
    
- **Nicht unterstützt: Remotedesktopsitzungen.** In diesem Szenario meldet sich jeder Benutzer bei einer generischen virtuellen Desktopsitzung an, die nicht angepasst werden kann. Beispiele sind Microsoft-Remotedesktop Sitzungen (RDSH) und Citrix XenApp in Kombination mit Citrix Receiver.
    
Das Lync VDI-Plug-In unterstützt keine anderen Virtualisierungstechnologien, z. B. Anwendungsvirtualisierung, die die Verwendung einer Anwendung ermöglicht, ohne dass die vollständige Anwendung lokal installiert werden muss. Beispielimplementierungen sind Citrix XenApp und Microsoft Application Virtualization (App-V). Anwendungsstreaming, Anwendungsremoting und gemischte Virtualisierungsmodi (z. B. Anwendungsremoting im vollständigen Desktopremoting) werden nicht unterstützt.
  
Das Lync VDI-Plug-In wurde für die Verwendung plattformunabhängiger APIs namens Dynamic Virtual Channels (DVCs) entwickelt. Szenarien, die nicht explizit unterstützt werden, finden Sie in den Supportanweisungen des VDI-Lösungsanbieters.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Voraussetzungen für Das Lync VDI-Plug-In
<a name="VDI_prereq"> </a>

In einer VDI-Umgebung müssen die virtuellen Computer und der lokale Computer des Benutzers die in diesem Abschnitt beschriebenen Anforderungen erfüllen.
  
> [!NOTE]
>  Ihr Virtualisierungslösungsanbieter kann Details zur Installation und Bereitstellung seiner Umgebung bereitstellen. Allgemeine Informationen zum Bereitstellen einer virtualisierten Umgebung basierend auf Hyper-V und Remotedesktopdiensten finden Sie in den folgenden Artikeln in der [Microsoft-Bibliothek: Hyper-V](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753637(v=ws.10)), [Remotedesktopdienste in Windows Server 2008 R2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd736539(v=ws.10)) 
  
Virtuelle Computer müssen mit Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Service Packs konfiguriert werden.
  
Der lokale Computer des Benutzers muss die folgenden Anforderungen erfüllen:
  
- Der Benutzer muss auf Skype for Business Server oder Lync Server 2013 verwaltet werden.
    
- Auf dem lokalen Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1 oder Windows 8 ausgeführt werden.
    
- Wenn Sie Remotedesktopdienste verwenden, wählen Sie das 32-Bit- oder 64-Bit-Lync VDI-Plug-In aus, um es mit dem Betriebssystem des lokalen Computers abzugleichen. Es ist nicht erforderlich, dass sowohl der lokale als auch der virtuelle Computer über 32-Bit- oder 64-Bit-Betriebssysteme verfügen. Wenn Sie eine andere Virtualisierungslösung oder Plattform verwenden, lesen Sie die Anforderungen Ihres Anbieters.
    
- Auf dem lokalen Computer muss die [neueste Version des Remotedesktopclients](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)ausgeführt werden. Installieren Sie die neuesten Updates des Remotedesktopdienste-Clients von Microsoft oder die neueste Remotedesktopclientsoftware von Ihrem Virtualisierungslösungsanbieter. 
    
- Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist. Informationen zum Konfigurieren dieser Einstellungen für die Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt "So konfigurieren Sie Einstellungen für die Remotedesktopverbindung". 
    
Das Microsoft VDI-Plug-In ist im [Microsoft Lync VDI 2013-Plug-In (32 Bit)](https://www.microsoft.com/download/details.aspx?id=35457) oder [im Microsoft Lync VDI 2013-Plug-In (64 Bit)](https://www.microsoft.com/download/details.aspx?id=35454)verfügbar.
  
#### <a name="known-feature-limitations"></a>Bekannte Featureeinschränkungen
<a name="VDI_prereq"> </a>

Die folgenden Einschränkungen sind bekannt, wenn Sie den Skype for Business 2015-Client in einer VDI-Umgebung verwenden:
  
Es gibt eingeschränkte Unterstützung für Die Anonymisierungsfeatures für Anrufdelegierung und Reaktionsgruppen-Agent.
  
Folgende Features werden nicht unterstützt:
  
- Integrierte Optimierungsseiten für Audio- und Videogeräte
    
- Video mit mehreren Ansichten.
    
- Aufzeichnen von Konversationen
    
- Anonym an Besprechungen teilnehmen (d. b. Skype for Business Besprechungen teilnehmen, die von einer Organisation gehostet werden, die nicht mit Ihrer Organisation verbunden ist).
    
- Verwenden des Lync VDI-Plug-Ins zusammen mit einem Lync Telefon Edition-Gerät.
    
- Anrufkontinuität im Fall eines Netzwerkausfalls
    
- Benutzerdefinierte Klingeltöne und Features für die Wartemusik.
    
Das Lync VDI-Plug-In wird in Microsoft 365- oder Office 365-Umgebungen nicht unterstützt.
  
> [!NOTE]
> Citrix RealTime Optimization Pack unterstützt Microsoft 365 und Office 365. Informationen zu Citrix-basierten virtuellen Umgebungen finden Sie in der [Technical Overview-Dokumentation](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) von Citrix, um eine Liste der unterstützten Features und Versionen zu erhalten.
  
## <a name="see-also"></a>Siehe auch
<a name="Citrix_RT"> </a>

[Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)