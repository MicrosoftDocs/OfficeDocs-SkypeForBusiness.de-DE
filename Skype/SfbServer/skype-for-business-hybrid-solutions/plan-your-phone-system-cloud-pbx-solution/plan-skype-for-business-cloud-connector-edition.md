---
title: Planen für die Skype for Business Cloud Connector-Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Hier erhalten Sie Informationen zu Skype for Business Cloud Connector Edition, einem als Paket zusammengesetzten Satz von virtuellen Maschinen (VMs), die eine lokale PSTN-Anbindung mit dem Telefonsystem in Office 365 (Cloud-PBX) implementieren.
ms.openlocfilehash: 5c175a09a83d8fb5fe3267329c63075b450a9b1f
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2018
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planen für die Skype for Business Cloud Connector-Edition
 
Hier erhalten Sie Informationen zu Skype for Business Cloud Connector Edition, einem als Paket zusammengesetzten Satz von virtuellen Maschinen (VMs), die eine lokale PSTN-Anbindung mit dem Telefonsystem in Office 365 (Cloud-PBX) implementieren. 
  
Cloud Connector Edition möglicherweise die richtige Lösung für Ihre Organisation, wenn Sie nicht bereits einer vorhandenen Lync Server oder Skype für Business Server-Bereitstellung verfügen. Wenn Sie weiterhin das Telefonsystem in Office 365-Lösung für Ihr Unternehmen geeignet ist untersuchen sind, finden Sie unter [Planen von Ihrem Telefonsystem in Office 365 (PBX) zu Cloud-Lösung](plan-your-phone-system-cloud-pbx-solution.md). 
  
In diesem Dokument erläutert Cloud Connector Edition-Anforderungen und unterstützten Topologien und hilft Ihnen bei der Planung Ihrer bereitstellungs Cloud Connector Edition. Achten Sie darauf, dass Sie dieses Thema lesen, bevor Sie Ihre Cloud-Connector-Umgebung konfigurieren. Wenn Sie bereit sind, bereitstellen und Konfigurieren von Cloud-Connector Edition finden Sie [Konfigurieren und Verwalten von Skype für Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md). 
  
Cloud Connector Edition 2.1 ist jetzt verfügbar. Wenn Sie noch nicht auf 2.1 aktualisiert haben, finden Sie unter [Upgrade auf eine neue Version von Cloud-Connector](upgrade-to-a-new-version-of-cloud-connector.md). Finden Sie die Installationsdatei unter [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller). 
  
> [!NOTE]
> Microsoft unterstützt die vorherige Version der Cloud Connector Edition für 60 Tage nach der Veröffentlichung einer neuen Version. Microsoft unterstützt Version 2.0.1 nach der Veröffentlichung von Version 2.1 60 Tage lang, damit Sie Zeit zum Aktualisieren haben. Alle Versionen vor Version 2.0.1 werden nicht mehr unterstützt. 
  
Cloud Connector Edition ist eine hybride anbietet, der eine Reihe von gepackte virtuellen Computern (VMs) besteht, die PSTN-Anbindung: lokal mit Telefonsystem in Office 365 zu implementieren. Durch eine minimale Skype für Business Server-Topologie in einer virtualisierten Umgebung bereitstellen, können Benutzer in Ihrer Organisation, die sich in der Cloud befinden PBX-Dienste von Microsoft-Cloud empfangen, aber PSTN-Anbindung über die vorhandenen lokalen VoIP bereitgestellt wird Infrastruktur. 
  
![Topologiediagramm, in dem das Cloud PBX-Gateway und die Herstellung der Verbindung von Cloud PBX mit einer lokalen Bereitstellung von Skype for Business dargestellt wird.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)
  
Da Sie mit Cloud Connector die Möglichkeit haben, die Dienste des Telefonsystems in Office 365 in eine vorhandene Telefonieumgebung (z. B. PBX, analoge Geräte und Callcenter) zu integrieren, können Sie eine phasenweise Migration von der vorhandenen Telefonielösung zum Telefonsystem in Office 365 implementieren. 
  
Nehmen wir zum Beispiel an, Ihre Firma hat ein anspruchsvolles Callcenter mit bestimmten Funktionen, die das Telefonsystem in Office 365 nicht bietet. Sie können für die Callcenterbenutzer weiter die vorhandene Lösung verwenden, während Sie die anderen Benutzer nach Office 365 übertragen. 
  
Cloud Connector ermöglicht die Weiterleitung zwischen den lokal verwalteten Benutzern und den online verwalteten Benutzern, und Sie können wahlweise Ihren eigenen PSTN-Anbieter mit dem Telefonsystem in Office 365 verwenden.
  
Berücksichtigen Sie beim Planen der Bereitstellung Cloud Connector Edition Folgendes: 
  
- Um Cloud Connector verwenden, um die Cloud VoIP-Lösungen nutzen, müssen Sie für ein Office 365-Mandanten zu registrieren, die in Office 365 Telefonsystem enthält. Wenn Sie noch nicht über Office 365-Mandanten verfügen Sie können erfahren Sie, wie sich hier anmelden: [Office 365 für Unternehmen](https://products.office.com/en-us/business/office). Beachten Sie, dass Sie benötigen, um für einen Plan registrieren, der Skype für Business Online enthält.
    
- Zum Registrieren von Cloud-Connector Appliances mit der Skype für Business Onlinedienst, und verschiedene Cmdlets ausführen, erfordert Cloud Connector 2.0 und höher ein dediziertes Office 365-Konto mit der Skype für Business Mandanten Administratorrechte. Cloud Connector-Versionen vor 2.0 erfordern ein dediziertes Office 365-Konto mit den Rechten eines globalen Mandantenadministrators.
    
- Cloud-Connector erfordert eine vollständige Skype für Business Server-Bereitstellung lokale nicht. 
    
    Derzeit Cloud Connector kann nicht mit Lync koexistieren oder Skype für Unternehmen lokalen Server. Wenn Sie vorhandene Lync oder Skype für Unternehmensbenutzer zu Office 365 zu verschieben und beibehalten möchten Bereitstellen von lokalen Telefonie für Benutzer, sollten Sie Telefonsystem in Office 365 mit lokalen-Diensten, die über eine vorhandene Skype für Business Server-Bereitstellung. Weitere Informationen finden Sie unter [Ihrem Telefonsystem in Office 365 (PBX) zu Cloud-Lösung planen](plan-your-phone-system-cloud-pbx-solution.md) und [Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server planen](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Wenn Sie einen vorherigen Skype für Business oder Lync Server-Bereitstellung hatte, und Sie das Schema erweitert, müssen Sie nicht, um das Schema für die Bereitstellung Cloud Connector zu bereinigen, solange Sie alle Skype für Business oder Lync Server-Komponenten aus der Umgebung entfernt haben. 
    
- Ihre Benutzer werden online verwaltet.
    
- Wenn Ihre Organisation Verzeichnissynchronisierung (DirSync) konfiguriert hat, müssen alle Konten von Benutzern, die für Hybridtelefonie geplant sind, zuerst in Ihrer lokalen Bereitstellung erstellt und dann mit der Cloud synchronisiert werden.
    
- Falls erforderlich, können Sie Ihren aktuellen PSTN-Betreiber behalten.
    
- Wenn Sie Benutzern in der Cloud Connector einwahlkonferenzen bereitstellen möchten, können Sie die PSTN-Konferenz von Microsoft oder von Audiokonferenzen (ACP) Anbieter Partnern erwerben.
    
- Cloud Connector 2.0 und höher unterstützt jetzt Medienumgehung. Die medienumgehung kann ein Client zum Senden von Medien direkt an den nächsten Hop (Public Switched Telephone Network, PSTN) – Session Border Controller (SBC) oder ein Gateway – und die Cloud Connector Edition-Komponente aus dem Medienpfad auszuschließen. Weitere Informationen finden Sie unter [Plan für Medien in der Cloud Connector Edition umgehen](plan-for-media-bypass-in-cloud-connector-edition.md).
    
- Cloud Connector 2.1 und höher unterstützt das Überwachen von Cloud Connector mithilfe von Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Monitor Cloud Connector mit Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)
    
- Cloud-Connector steht in alle Länder, in denen Office 365 Enterprise E5 verfügbar. Allerdings aufgrund von verschiedenen Vorschriften Cloud Connector kann nicht konfiguriert werden, wenn der Mandant Speicherort auf eine der folgenden Länder festgelegt ist: Algerien, Bangladesch, Botsuana, Brunei, Kamerun, Côte d ' Ivoire, Ghana, Libanon, Macau, Mauritius, Namibia, Paraguay, Senegal.
    
Dieses Thema enthält die folgenden Abschnitte:
  
- [Cloud-Connector Edition-Komponenten](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)
    
- [Cloud-Connector Edition-Topologien](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)
    
- [Anforderungen für die Bereitstellung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)
    
- [Informationen, die Sie benötigen, um vor der Bereitstellung zu erfassen](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)
    
- [Hinweise zum Wählplan](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)
    
- [Überlegungen zur hohen Verfügbarkeit](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)
    
- [Cloud Connector-Mediendatenverkehr](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)
    
- [Überwachung und Problembehandlung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)
    
- [Weitere Informationen](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)
    
## <a name="cloud-connector-edition-components"></a>Cloud Connector Edition – Komponenten
<a name="BKMK_Components"> </a>

Mit Cloud Connector Edition, Sie eine Reihe von gepackte VMs, die eine minimale Skype für Business Server-Topologie enthalten bereitstellen – bestehend aus einer Edge-Komponente, Mediation Komponente und eine zentrale Verwaltung Store (CMS)-Rolle. Sie installieren auch einen Domänencontroller, der für die interne Funktionsfähigkeit der Cloud-Verbindung erforderlich ist. Für hybride mit Ihrem Office 365-Mandanten, die Skype für Business Online Services enthält, werden diese Dienste konfiguriert.
  
![Cloud Connector Edition – Komponenten](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)
  
Cloud Connectorkomponenten bieten die folgenden Funktionen:
  
- **Edge-Komponente** - Kommunikation zwischen der lokalen Topologie und die Onlinedienste durchläuft die Edge-Komponente, die umfasst die folgenden Komponenten:
    
  - **Zugriffs-Edgeservers** - SIP-routing zwischen der lokalen Bereitstellung und Skype für Business Online bietet.
    
  - **Mediarelay** - bietet routing von Medien zwischen der Komponente Mediation und andere Media-Endpunkte.
    
  - **Media Relayauthentifizierung / MRAS** -Token für den Zugriff auf Mediarelay generiert.
    
- **Ausgangsrouting** - bietet Lastenausgleich des VoIP-Datenverkehrs zwischen Gateways oder an einer Cloud-Connector Appliance SBCs angeschlossen sein. Die Anrufe werden gleichmäßig auf alle mit der Cloud Connector-Appliance verbundenen Gateways oder SBCs verteilt.
    
    Enthält das routing an Gateways basierend auf Richtlinien. Nur globale Richtlinien, die auf Ziel (ausgehend) PSTN-Nummern basieren werden unterstützt.
    
- **Rolle des zentralen Management Verwaltungsspeicher (CMS)** - enthält Konfigurationsspeichers für die topologiekomponenten, einschließlich CMS Datei übertragen.
    
- **Replikat des zentralen Management Store (CMS)** - Konfigurationsinformationen aus der globalen CMS-Datenbank auf dem Server, CMS Rolle synchronisiert.
    
- **Domänencontroller** - Cloud-Connector Active Directory Domain Services zum Speichern der globalen Einstellungen und Gruppen Cloud Connector Komponenten bereitgestellt, erforderlich sind. Für jede Appliance Cloud-Connector wird einer Gesamtstruktur erstellt werden. Der Domänencontroller muss keine Verbindungen mit der Produktion Active Directory verfügen. Die Active Directory-Dienste umfassen:
    
  - Active Directory-Domänendienste
    
  - Active Directory-Zertifikatdienste zum Erstellen interner Zertifikate
    
- **Mediation Komponente** - Protokoll der Medien und implementiert SIP-Gateway-Zuordnung zwischen Skype für Geschäfts- und PSTN-Gateways. Enthält ein Replikat des zentralen Verwaltungsspeichers, die Konfiguration aus der globalen CMS-Datenbank synchronisiert.
    
## <a name="cloud-connector-edition-topologies"></a>Cloud Connector Edition – Topologien
<a name="BKMK_Topologies"> </a>

Im Rahmen dieser Erläuterungen ist von PSTN-Standorten die Rede. Eine PSTN-Website ist eine Kombination von Cloud-Connector Appliances und am selben Speicherort und zu allgemeinen PSTN-Gateways für diese Verbindung bereitgestellt. PSTN-Standorte bieten Ihnen folgende Möglichkeiten:
  
- Verbindungen zu den Gateways herstellen, die Ihren Benutzern am nächsten sind
    
- Skalierbarkeit durch die Bereitstellung mehrerer Cloud Connector Appliances in eine oder mehrere PSTN-Websites zuzulassen.
    
- Zulassen von hoher Verfügbarkeit durch die Bereitstellung mehrerer Cloud Connector Appliances in einer einzelnen PSTN-Website.
    
In diesem Thema werden PSTN-Standorte vorgestellt. Weitere Informationen zur Planung der PSTN-Websites finden Sie unter [Planen von Cloud Connector Edition PSTN-Websites](plan-for-cloud-connector-edition-pstn-sites.md).
  
Sie können die folgenden Cloud Connector Topologien bereitstellen:
  
- Eine einzelne Cloud Connector Edition Appliance pro PSTN-Website. Diese Topologie wird nur für Evaluierungszwecke empfohlen, da sie keine hohe Verfügbarkeit bietet.
    
- Mehrere Cloud Connector Edition-Geräte pro PSTN-Website, um hohe Verfügbarkeit bereitzustellen. 
    
- Mehrere PSTN-Websites mit mehreren Cloud Connector Edition Appliances Skalierbarkeit mit hoher Verfügbarkeit bereitzustellen. Sie können bis zu 200 Standorte bereitstellen.
    
Beim Planen Ihrer Topologie sollten Sie Folgendes beachten:
  
- Mit Cloud Connector 2.0 und höher kann einem PSTN-Standort bis zu 16 Cloud Connector Appliances verfügen. Vorherige Versionen unterstützen bis zu vier Appliances pro Standort. 
    
- Es gibt zwei Arten von Hardwarekonfigurationen mit Cloud Connector getestet: 
    
  - Die größere Version ist in der Lage, große Mengen von Anrufen gleichzeitig zu verarbeiten. Sie wird in jeder Art von Produktionsumgebung unterstützt.
    
  - Die kleinere Version ist dafür gedacht, auf Hardware mit geringerer Leistungsfähigkeit ausgeführt zu werden. Sie kann für Prüfzwecke oder für Standorte mit geringerem Anrufaufkommen verwendet werden. Aber auch wenn Sie eine kleinere Version von Cloud Connector einsetzen, müssen Sie dennoch die Hardwareanforderungen der Produktionsklasse berücksichtigen (zum Beispiel doppelte Stromversorgung).
    
- Wenn Sie die Cloud Connector Version 2.0 oder höher haben, und Sie die maximale Konfiguration von 16 Einheiten (mit größeren Hardware) bereitstellen, kann Ihre Website PSTN bis zu 8.000 gleichzeitige Anrufe verarbeiten. Wenn Sie die kleinere Version bereitstellen, werden maximal 800 gleichzeitige Anrufe unterstützt. 
    
    Außerdem müssen Sie einen Teil der Appliances für hohe Verfügbarkeit verwenden. Die Mindestkonfiguration sieht eine für hohe Verfügbarkeit reservierte Appliance vor.
    
  - Mit Version 2 Wenn Sie eine 15 + 1-Konfiguration bereitstellen kann Ihrer Website PSTN bis zu 7.500 gleichzeitige Anrufe behandeln.
    
  - Wenn Sie eine frühere Version verwenden und die maximale 3+1-Konfiguration (mit leistungsstärkerer Hardware) bereitstellen, kann Ihr PSTN-Standort bis zu 1.500 Anrufe gleichzeitig verarbeiten. Wenn Sie die kleinere Version bereitstellen, werden maximal 150 Anrufe unterstützt.
    
-  Falls Sie noch mehr Anrufe pro PSTN-Standort verarbeiten möchten, können Sie die Zahl der Anrufe heraufsetzen, indem Sie an einem Ort zusätzliche PSTN-Standorte bereitstellen.
    
> [!NOTE]
> Sofern nicht angegeben, wird davon ausgegangen der Diagramme und die unten stehenden Beispiele beziehen die Verwendung der größeren Version von Cloud-Connector. 
  
### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Einzelne Cloud Connector-Appliance an einem einzelnen PSTN-Standort

Das folgende Diagramm zeigt eine einzelne Cloud Connector Edition Appliance innerhalb einer einzelnen PSTN-Website. Beachten Sie, dass Cloud-Konnektor besteht aus vier virtuelle Computer auf einem physischen Hostcomputer, der in einem Umkreisnetzwerk aus Sicherheitsgründen ist installiert.
  
![Ein Cloud Connector mit einem Festnetzstandort](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)
  
### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Mehrere Cloud Connector-Appliances an einem einzelnen PSTN-Standort

 Skalierbarkeit und hohe Verfügbarkeit Zwecke können Sie mehrere Cloud Connector Editionen innerhalb einer einzelnen PSTN-Website verfügen, wie in der folgenden Abbildung dargestellt. Beachten Sie dabei Folgendes:
  
- Die Anrufe werden auf die verschiedenen Cloud Connector-Instanzen in einem Pool verteilt, wobei die Verteilung nach dem Zufallsprinzip erfolgt.
    
- Bei Ihrer Kapazitätsplanung müssen Sie berücksichtigen, dass die Last auch dann noch bewältigt werden muss, wenn eine oder mehrere Cloud Connector-Instanzen offline sind. Mit der folgenden Berechnung können Sie ermitteln, wie viele Anrufe verarbeitet werden können:
    
  - **n+1 Boxen**. N + 1-Knoten Unterstützung für die größeren Version von Cloud-Connector, 500\*N gleichzeitige Anrufe mit 99,8 % Verfügbarkeit.
    
    N + 1-Knoten Unterstützung für die kleinere Version von Cloud-Connector, 50\*N gleichzeitige Anrufe mit 99,8 % Verfügbarkeit.
    
  - **n+2 Boxen**. N + 2 Feldern Unterstützung für die größeren Version von Cloud-Connector, 500\*N gleichzeitige Anrufe mit Verfügbarkeit von 99,9 %.
    
    N + 2 Feldern Unterstützung für die kleinere Version von Cloud-Connector, 50\*N gleichzeitige Anrufe mit Verfügbarkeit von 99,9 %.
    
![Zwei Cloud Connectors im Rahmen eines Festnetzstandorts](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)
  
### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Mehrere PSTN-Standorte mit einer oder mehreren Cloud Connector-Instanzen pro Standort

Alternativ können Sie sich für mehrere PSTN-Standorte mit einer oder mehreren Cloud Connector Edition-Instanzen pro Standort entscheiden. Wenn Ihre Website PSTN gleichzeitige Anrufe erreicht, können Sie eine andere PSTN-Website, um die Last zu bewältigen hinzufügen.
  
Die Verwendung mehrerer PSTN-Standorte bietet Ihnen außerdem die Möglichkeit, Verbindungen zu den Gateways herzustellen, die Ihren Nutzern am nächsten sind. Nehmen wir einmal an, Sie haben PSTN-Gateways in Seattle und in Amsterdam. Sie können also zwei PSTN-Gateways – eins in Seattle und eins in Amsterdam – bereitstellen und Nutzer dem PSTN-Standort zuweisen, der ihnen näher ist. Dadurch werden Nutzer aus Seattle dann an den PSTN-Standort und die Gateways in Seattle und Nutzer aus Amsterdam an den PSTN-Standort und die Gateways in Amsterdam weitergeleitet:
  
![Cloud Connector Edition im Rahmen von zwei Festnetzstandorten](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)
  
## <a name="requirements-for-deployment"></a>Anforderungen für die Bereitstellung
<a name="BKMK_Requirements"> </a>

Vor der Bereitstellung von Cloud-Connector Edition, stellen Sie sicher, dass Sie für Ihre Umgebung Folgendes sein:
  
- **Für den Host-** Cloud Connector VMs muss auf dedizierter Hardware, die die Hyper-V-Rolle aktiviert ist mit Windows Server 2012 R2 Datacenter Edition (auf Englisch) bereitgestellt werden.
    
    Für Version 2.0 und höher muss die Netzwerkkarte des Hostcomputers, die an den Unternehmensnetzwerk-Switch für Skype for Business gebunden ist, mit einer IP-Adresse im gleichen Subnetz wie die Cloud Connector-Computer im Unternehmensnetzwerk konfiguriert sein.  
    
- Für Versionen 2.1 und höher muss die Host-Anwendung .NET Framework 4.6.1 oder höher installiert sein. 
    
- **Für die virtuellen Computer-** Ein Bild mit Windows Server 2012 R2 ISO (auf Englisch) (ISO). ISO wird für die virtuellen Computer, auf denen Skype für Business Cloud Connector Edition ausgeführt wird, in VHDs konvertiert werden soll.
    
- Die erforderliche Hardware zur Unterstützung der Installation der VMs 4 für jede Cloud Connector Edition in Ihrer Bereitstellung. Die folgenden Konfigurationen werden empfohlen:
    
  - 64-Bit-Dualprozessor, sechs core (12 realen Kerne) 2,50 Gigahertz (GHz) oder höher
    
  - 64 GB EEC-RAM  
    
  - Vier Festplatten mit 600 GB (oder mehr),10.000 U/min, 128 MB Cache, 6 GB/s SAS in RAID-5-Konfiguration
    
  - Drei 1-GB/s-RJ45-Netzwerkadapter mit hohem Durchsatz
    
- Wenn Sie kleinere Version von Cloud-Connector Edition bereitstellen, der bis zu 50 gleichzeitige Anrufe unterstützt, benötigen Sie die folgende Hardware:
    
  - Intel i7 4790 QuadCore mit Grafikeinheit Intel 4600 Graphics (High-End-Grafik ist nicht erforderlich)
    
  - 32 GB DDR3-1600, Non-ECC
    
  - 2: 1 TB 7.200 U/min SATA III (6 GBit/s) in RAID 0
    
  - 2: 1 GBit/s Ethernet (RJ45)
    
- Wenn auf dem Hostcomputer ein Proxyserver zum Surfen im Internet erforderlich ist, sollten Sie die folgenden Konfigurationsänderungen vornehmen:
    
  - Um den Proxy zu umgehen, geben Sie WinHTTP-Proxyeinstellungen festlegen mit Ihren Proxy-Server und eine Umgehungsliste, einschließlich der "192.168.213. \*"Netzwerk durch Ihre Cloud Connector Unternehmensleitungen Dienste und Skype für Business Corpnet Subnetz verwendet wird, wie in der Datei CloudConnector.ini definiert. Andernfalls wird Management-Konnektivität fehl und zu verhindern, dass die Bereitstellung und die automatische Wiederherstellung der Verbindung Cloud. Im folgenden finden Sie einen Winhttp Konfiguration Beispielbefehl: Netsh Winhttp Proxy "10.10.10.175:8080" Umgehungsliste festlegen = "\*Local; 1. \*; 172.20. \*; 192.168.218. \*'\<lokale\>".
    
  - Geben Sie Proxyeinstellungen pro Computer und nicht pro Benutzer an. Andernfalls werden Cloud Connector Downloads fehl. Sie können Proxyeinstellungen wie folgt mit einer Registrierungsänderung oder mit einer Gruppenrichtlinieneinstellung pro Computer angeben:
    
  - **Registrierung:** HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Einstellungen] ProxySettingsPerUser 00000000
    
  - **-Gruppenrichtlinie:** Computer\>Administrative Vorlagen\>Windows-Komponenten\> Internet Explorer: Stellen Sie Proxyeinstellungen pro Computer (nicht pro Benutzer)
    
- Qualifizierte PBX/qualifizierter Trunk oder qualifizierter SBC/qualifiziertes Gateway (Empfohlen werden mindestens zwei Gateways.)
    
    Cloud Connector unterstützt die gleichen Session Border Controller (SBCs), die für Skype for Business zertifiziert sind. Weitere Informationen finden Sie unter [Telefonie-Infrastruktur für Skype für Unternehmen](https://technet.microsoft.com/en-us/office/dn947483.aspx). 
    
- Ein lokaler Server-Administratorkonto mit Berechtigungen zum Installieren und Konfigurieren von Hyper-V auf den Hostservern. Das Konto muss über Administratorberechtigungen auf dem lokalen Server verfügen, auf dem Hyper-V installiert und konfiguriert ist.
    
- Im Zuge der Bereitstellung werden Sie aufgefordert, ein Domänenadministratorkonto mit Berechtigungen zum Erstellen und Veröffentlichen der Topologie in der Cloud Connector-Domäne anzulegen.  
    
- Die externen DNS-Einträge, die in der im Installationspaket enthaltenen Datei „CloudConnector.ini“ definiert sind:
    
  - Externe DNS-Eintrag für den Zugriffs-edgedienst der Edge-Komponente; beispielsweise ap.\<Domänennamen\>. Pro PSTN-Standort benötigen Sie einen Eintrag. Dieser Eintrag muss die IP-Adressen der alle Ränder für diese Website enthalten.
    
- Ein Office 365-Mandanten mit allen erforderlichen DNS- und SRV-Einträge erstellt werden soll.
    
    > [!IMPORTANT]
    > Wenn Sie Ihrem Mandanten mit Cloud Connector Edition, die Verwendung von Standard-Domänensuffix, integrieren. "onmicrosoft.com" dargestellt, wie eine SIP-Domäne für Ihre Organisation wird nicht unterstützt. > Kann nicht Sip verwendet werden. \<Domänennamen\> als Namen für Ihre Cloud-Connector-Zugriffs-Edgeserver Proxy Schnittstelle, da diese DNS-Eintrag von Office 365 verwendet wird. 
  
- Ein von einer öffentlichen Zertifizierungsstelle (CA) erhaltenes Zertifikat für den externen Edgeserver.
    
- Firewallregeln, um den Datenverkehr über die erforderlichen Ports zuzulassen, wurden fertiggestellt. 
    
- Eine Internet-Verbindung für den Hostcomputer und den virtuellen Computern. Cloud-Connector werden einige Software aus dem Internet heruntergeladen. aus diesem Grund erforderlich Gateway und DNS-Server-Informationen, damit die Cloud Connector-Hostcomputer und virtuelle Computer mit dem Internet verbinden und die benötigte Software herunterladen können.
    
- Ein Remote-PowerShell-Modul für einen Mandanten ist auf der Hostmaschine installiert.
    
- Die Anmeldeinformationen des Office 365 Skype for Business-Administrators zum Ausführen von Remote-PowerShell 
    
    > [!IMPORTANT]
    > Für das Administratorkonto darf die mehrstufige Authentifizierung NICHT aktiviert sein.  
  
> [!NOTE]
> Bereitstellung von Cloud-Connector wird nur auf der Microsoft Hyper-V virtualisierten-Plattform unterstützt. Andere Plattformen (zum Beispiel VMware und Amazon Web Services) werden nicht unterstützt. 
  
> [!NOTE]
> Die Mindestanforderungen an die Hardware Anleitung zum Ausführen von Cloud-Connector basiert auf grundlegende Hardwarekapazität (Kerne, MHz, Gigabyte usw.) mit einem Puffer immateriellen Leistung Hörvermögen in die Architektur von einem beliebigen Computer verborgen. Microsoft hat schlechtesten Groß-/Kleinschreibung Auslastungstests auf dem Markt verfügbaren Hardware die minimale Anleitung meeting ausführen. Media Quality und Systemleistung überprüft werden. Offizielle Cloud Connector Appliance Microsoft-Partnern müssen bestimmte Hardware Implementierungen Cloud Connector auf dem sie unabhängig voneinander Leistung getestet haben, und sie Standby die Eignung ihrer Hardware Load und QoE-Anforderungen erfüllt. 
  
> [!NOTE]
> Von AudioCodes und Sonus hergestellte Geräte enthalten geänderten Code und können mit Servern unter Windows Server Standard Edition betrieben werden. Diese Geräte werden unterstützt. 
  
## <a name="information-you-need-to-gather-before-deployment"></a>Informationen, die Sie benötigen, um vor der Bereitstellung zu erfassen
<a name="BKMK_PlanDeployment"> </a>

Bevor Sie mit der Bereitstellung beginnen, müssen Sie die Größe Ihrer Bereitstellung, die betreffenden SIP-Domänen sowie die Konfigurationsinformationen für jeden PSTN-Standort, den Sie bereitstellen möchten, bestimmen. Zunächst nehmen Sie folgenden Schritt vor:
  
- Identifizieren der SIP-Domänen, die von dieser Bereitstellung basierend auf der SIP-URIs in Ihrem Unternehmen verwendeten bereitgestellt werden. 
    
- Ermitteln Sie die Anzahl der PSTN-Standorte, die Sie bereitstellen müssen.
    
- Stellen Sie sicher, dass Sie haben die Hardware erforderlich, um die vier VMs unterstützen Sie für jede Cloud Connector Edition installieren können. 
    
Für jede PSTN-Website, die Sie bereitstellen möchten, müssen Sie:
  
- Namen für alle Komponenten in jede Appliance Cloud-Connector erstellen (siehe [Determine Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).
    
- Definieren Sie Portbereiche (siehe auch [Ports und Protokolle](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).  
    
- Erstellen Sie externe DNS-Einträge für die Edgekomponente (siehe [Anforderungen für die Bereitstellung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).
    
- Bestimmen Sie die Zertifikatanforderungen für die Edgekomponente (siehe auch [Zertifikatanforderungen](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).
    
### <a name="ports-and-protocols"></a>Ports und Protokolle
<a name="BKMB_Ports"> </a>

Beim Definieren von Medienportbereichen sollten Sie Folgendes berücksichtigen:
  
- Verwenden Sie Clients immer Portbereich 50000 zu 50019 für Mediendatenverkehr – in diesem Bereich ist in Skype für Business Online vordefiniert und kann nicht geändert werden.
    
- Die Vermittlungskomponente verwendet für den Mediendatenverkehr standardmäßig einen Portbereich von 49152 bis 57500. Jedoch über interne Firewall die Verbindung hergestellt wird, und aus Sicherheitsgründen können Sie diesen Portbereich in Ihrer Topologie beschränkt. Pro Anruf benötigen Sie bis zu vier Ports. Falls Sie die Anzahl der Ports zwischen der Vermittlungskomponente und dem PSTN-Gateway begrenzen möchten, müssen Sie den entsprechenden Portbereich auf dem Gateway ebenfalls konfigurieren.
    
- Sie müssen die Cloud-Connector in einem Umkreisnetzwerk bereitstellen. Auf diese Weise sind Sie durch zwei Firewalls geschützt: 
    
  - Bei der ersten Firewall handelt es sich um eine externe Firewall zwischen dem Internet und Ihrem Umkreisnetzwerk.
    
  - Die zweite Firewall ist zwischen dem Umkreisnetzwerk und dem internen Netzwerk intern. 
    
    Ihre Clients können sich im Internet oder im internen Netzwerk befinden:  
    
  - Bei Internetclients erfolgt die Verbindung zu Ihrem PSTN über die externe Firewall mithilfe der Edgekomponente.
    
  - Über die interne Firewall für die Mediation Komponente in das Umkreisnetzwerk, die Datenverkehr SBC oder PSTN-Gateway eine Verbindung herstellt, werden Clients im internen Netzwerk verbunden. 
    
    Das bedeutet, dass Sie in beiden Firewalls Ports öffnen müssen.  
    
In den folgenden Tabellen werden Ports und Portbereiche im Hinblick auf die externen und internen Firewalls beschrieben.
  
Diese Tabelle stellt die Ports und Portbereiche dar, mit denen die Kommunikation zwischen Clients im internen Netzwerk und der Vermittlungskomponente hergestellt werden kann:
  
**Interne firewall**



|**Quell-IP**|**Ziel-IP-**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Cloud Connector Mediation Komponente  <br/> |SBC/PSTN-Gateway  <br/> |Beliebig  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN-Gateway  <br/> |Cloud Connector Mediation Komponente  <br/> |Beliebig  <br/> |TCP 5068/TLS 5067  <br/> |
|Cloud Connector Mediation Komponente  <br/> |SBC/PSTN-Gateway  <br/> |UDP 49 152 57 500  <br/> |Alle\*\*\*  <br/> |
|SBC/PSTN-Gateway  <br/> |Cloud Connector Mediation Komponente  <br/> |Alle\*\*\*  <br/> |UDP 49 152 57 500  <br/> |
|Cloud Connector Mediation Komponente  <br/> |Interne Clients  <br/> |TCP 49 152 57 500\*  <br/> |TCP 50.000-50.019  <br/> (Optional)  <br/> |
|Cloud Connector Mediation Komponente  <br/> |Interne Clients  <br/> |UDP 49 152 57 500\*  <br/> |TCP 50000–50019  <br/> |
|Interne Clients  <br/> |Cloud Connector Mediation Komponente  <br/> |TCP 50.000-50.019  <br/> |TCP 49 152 57 500\*  <br/> |
|Interne Clients  <br/> |Cloud Connector Mediation Komponente  <br/> |TCP 50000–50019  <br/> |UDP 49 152-57 500\*  <br/> |
   
\*Dies ist der Standardportbereich auf der Mediation Komponente. Um einen optimalen Anruffluss zu gewährleisten, sind vier Ports pro Anruf notwendig.
  
\*\*Dieser Port muss auf dem SBC/PSTN-Gateway konfiguriert sein. 5060 ist ein Beispiel. An Ihrem SBC/PSTN-Gateway können Sie auch andere Ports konfigurieren.
  
\*\*\*Beachten Sie, dass Sie auch den Portbereich auf Ihrer SBC-Gateway einschränken können, wenn vom Hersteller SBC-Gateway zugelassen.
  
Aus Sicherheitsgründen können Sie den Portbereich für die Komponente Mediation beschränken, mit dem Cmdlet [Set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .
  
Der folgende Befehl beschränkt beispielsweise die Anzahl der Ports, die die Komponente Mediation (an-und Abmelden) für Mediendatenverkehr zu 50 000-51 000 für Audio verwendet werden soll. Mit dieser Konfiguration kann die Vermittlungskomponente 250 Anrufe gleichzeitig verarbeiten. Beachten Sie, dass es ratsam sein kann, diesen Bereich auch am SBC/PSTN-Gateway zu begrenzen:
  
```
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Zum Abrufen des Namens der Komponente Mediation und Standardports angezeigt wird, können Sie das Cmdlet " [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) " wie folgt verwenden:
  
```
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

In der folgenden Tabelle werden die Ports und Portbereiche für die Kommunikation zwischen der Cloud Connector Edge-Komponente mit dem externen Firewall dargestellt. Bei den Angaben handelt es sich um Mindestempfehlungen.
  
In diesem Fall alle Mediendatenverkehr mit dem Internet fließt über die Online-Schnittstelle wie folgt: Benutzer Endpunkt –\>Online Edge--\>Cloud Connector Edge:
  
**Externe Firewall - Mindestkonfiguration**



|**Quell-IP**|**Ziel-IP-**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Beliebig  <br/> |Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP 80  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |Beliebig  <br/> |UDP 53  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP 53  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Beliebig  <br/> |Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
|Beliebig  <br/> |Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
   
Die nächste Tabelle zeigt die Ports und Portbereiche für die Kommunikation zwischen der Cloud Connector Edge Komponente der externen Firewall zu aktivieren. Diese Tabelle zeigt die empfohlene Lösung.
  
In diesem Fall kann alle Mediendatenverkehr für den Endpunkt in das Internet direkt an die Cloud Connector Edge-Komponente übertragen werden. Der Medienpfad werden Benutzer Endpunkt -\> Cloud Connector Edge.
  
> [!NOTE]
> Diese Lösung kann nicht verwendet werden, falls sich der Benutzerendpunkt hinter einer symmetrischen NAT befindet. 
  
**Externe Firewall - Konfiguration empfohlen**


|**Quell-IP**|**Ziel-IP-**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Beliebig  <br/> |Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP 80  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |Beliebig  <br/> |UDP 53  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP 53  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |TCP 50.000-59.999  <br/> |Beliebig  <br/> |
|Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |UDP 3478; UDP 50000–59999  <br/> |Beliebig  <br/> |
|Beliebig  <br/> |Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |TCP 443; TCP 50000–59999  <br/> |
|Beliebig  <br/> |Externe Schnittstelle des Cloud Connector Edgeservers  <br/> |Beliebig  <br/> |UDP 3478; UDP 50000–59999  <br/> |
   
### <a name="host-internet-connectivity-requirements"></a>Anforderungen für die Internetkonnektivität des Hosts
<a name="BKMB_Ports"> </a>

Das Hostsystem muss externe Ressourcen, um erfolgreich installieren, aktualisieren und Verwalten von Cloud-Connector erreichen. Die folgende Tabelle zeigt die erforderlichen Ziele und Ports zwischen dem Hostcomputer und externen Ressourcen. 
  
|Richtung  <br/> |Quell-IP  <br/> |Ziel-IP  <br/> |Quellport  <br/> |Zielport  <br/> |Protokoll  <br/> |Verwendungszweck  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ausgehend  <br/> |Cloud Connector Host IP-Adressen  <br/> |Beliebig  <br/> |Beliebig  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Ausgehend  <br/> |Cloud Connector Host IP-Adressen  <br/> |Beliebig  <br/> |Beliebig  <br/> |80, 443  <br/> |TCP  <br/> |Zertifikatssperrliste (CRL)  <br/> |
|Ausgehend  <br/> |Cloud Connectorr Host IP-Adressen  <br/> |Beliebig  <br/> |Beliebig  <br/> |80, 443  <br/> |TCP  <br/> |Cloud-Connector-update  <br/> Skype for Business Online  <br/> Administrator-PowerShell  <br/> Windows Update  <br/> |
   
Wenn restriktivere Regeln erforderlich sind, finden Sie unter den folgenden URLs zum Thema Whitelists weitere Informationen:
  
- [Die URLs für Zertifikatsperrlisten](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) in [Office 365-URLs und IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- Windows Update: [Gewusst wie: Konfigurieren einer Firewall für Softwareupdates](https://technet.microsoft.com/en-us/library/bb693717.aspx)
    
- Skype für Business Online Admin PowerShell: \*. online.lync.com
    
    Wenn Sie einen Proxyausschluss für dieses Ziel benötigen, müssen Sie ihn der WinHTTP-Umgehungsliste hinzufügen.
    
- Cloud-Connector-Update: [Downloadcenter](https://aka.ms/CloudConnectorInstaller) [https://go.microsoft.com](https://go.microsoft.com), und[http://download.microsoft.com](http://download.microsoft.com)
    
### <a name="dns-name-resolution-for-the-edge-component"></a>DNS-Namensauflösung für die Edgekomponente
<a name="BKMB_Ports"> </a>

Die Edge-Komponente muss die externen Namen von Office 365-Dienste und anderer Komponenten Cloud Connector die internen Namen auflösen. 
  
Jeder Edge-Komponente ist ein Multihoming-Computer mit externen und internen internetbasierte Schnittstellen. Cloud-Connector wird DNS-Server auf der Domänencontroller-Komponente im Umkreisnetzwerk bereitgestellt. So aktivieren Sie die Cloud Connector DNS-Server zum Auflösen der externer Names durch das Festlegen einer DNS-Zone mit mindestens einen DNS-A-Einträge für externe Abfragen, die Namen verweisen müssen aber können Sie die Edge-Server auf dem DNS-Server im Umkreisnetzwerk für alle Namen Auflösungen zeigen Suchvorgänge mit anderen öffentlichen DNS-Servern. 
  
Wenn Sie in der INI-Datei den FQDN für Gateways aus demselben Domänenbereich wie dem Ihrer SIP-Domäne zuweisen, wird die autoritative Zone für diese SIP-Domäne im DNS-Server innerhalb des Umkreises erstellt. Wenn Edge-Server auf diesen DNS-Server zum Auflösen von Namen verwiesen wird, wird die _sipfederationtls nie Edge aufgelöst werden. \<Ihre Domäne\> DNS-Eintrag für Anruffluss erforderlich ist. In diesem Fall empfiehlt es sich, dass Sie einen DNS-Server, auf die externe edgeschnittstelle zum Internet Namenssuche auflösen bereitstellen und jede Edge-Komponente muss eine Hostdatei zum Auflösen von anderen Komponentennamen Cloud-Connector in IP-Adressen verwenden.
  
> [!NOTE]
> Aus Sicherheitsgründen wird empfohlen, dass Sie den Cloud Connector DNS-Server nicht mit internen Servern in der Produktionsdomäne für die namensauflösung zeigen. 
  
### <a name="determine-deployment-parameters"></a>Bereitstellungsparameter festlegen
<a name="BKMK_SiteParams"> </a>

Zunächst müssen Sie folgende allgemeine Bereitstellungsparameter festlegen:
  

|**Element**|**Beschreibung**|**Notizen**|
|:-----|:-----|:-----|
|SIP-Domänen  <br/> |SIP-URI des von Benutzern von Unternehmen verwendet. Geben Sie alle SIP-Domänen an, die von dieser Bereitstellung bedient werden sollen. Sie können mehrere SIP-Domänen eintragen.  <br/> ||
|Anzahl der PSTN-Standorte  <br/> |Anzahl der PSTN-Standorte, die Sie bereitstellen möchten.  <br/> ||
   
Für jeden PSTN-Standort, den Sie bereitstellen möchten, müssen Sie die folgenden Informationen sammeln, bevor Sie mit der Bereitstellung beginnen. Sie müssen diese Informationen beim Aktualisieren der CloudConnector.ini-Datei bereitstellen.
  
Beachten Sie beim Konfigurieren der Gateway-Informationen Folgendes:
  
- Wenn Sie nur ein Gateway haben, entfernen Sie den Abschnitt für das zweite Gateway in der .ini-Datei. Wenn Sie mehr als zwei Gateways haben, orientieren Sie sich am vorhandenen Format, um neue Gateways hinzuzufügen.
    
- Stellen Sie sicher, dass die IP-Adresse und den Port, der die Gateway(s) richtig sind.
    
- Behalten Sie das sekundäre Gateway oder fügen Sie zusätzliche Gateways hinzu, um die hohe Verfügbarkeit auf der PSTN-Gateway-Ebene zu gewährleisten.
    
(Optional) Zum Einschränken der ausgehenden Rufnummern aktualisieren Sie den LocalRoute-Wert.
  


|**Websiteparameter**|**Beschreibung**|**Notizen**|
|:-----|:-----|:-----|
|Virtuelle Maschine – Domänenname  <br/> |Der Domänenname für die internen Komponenten des Cloud-Connector. Diese Domäne muss sich von der Produktionsdomäne unterscheiden. Der Name muss für sämtliche Cloud Connector-Appliances verwendet werden.  <br/> Name in INI-Datei: "VirtualMachineDomain"  <br/> |Eine .local-Domäne wird bevorzugt.   <br/> |
|Connector-Domänencontrollername Cloud  <br/> |Name des Domänencontrollers   <br/> Name in INI-Datei: "ServerName"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Cloud-Connector Domain Controller IP-Subnetz Maske  <br/> |IP-Adresse des Domänencontrollers   <br/> Name in INI-Datei: "IP"  <br/> ||
|O365-Onlinedienst-FQDNs  <br/> |Muss die Standardvorlage in den meisten Fällen für die weltweite O365-Instanz.  <br/> Name in INI-Datei: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Skype für Business Websitename; beispielsweise, Seattle.  <br/> Name in INI-Datei: "Websitename '"  <br/> Für Version 1.4.1 und höher muss der Standortname für jeden Standort eindeutig sein und mit dem in Office 365 definierten PSTN-Standort (sofern vorhanden) übereinstimmen. Beachten Sie, dass bei der Registrierung der ersten Appliance an einem Standort automatisch PSTN-Standorte erstellt werden.  <br/> ||
|HardwareType  <br/> Version 1.4.1 und höher  <br/> |Hardwaretyp. Der Standardwert ist „Normal“. Sie können diesen Wert aber auch auf „Minimum“ festlegen.  <br/> ||
|Landesvorwahl  <br/> |Telefonvorwahl des Landes  <br/> Name in INI-Datei: "CountryCode"  <br/> ||
|Ort  <br/> |Ort (optional)  <br/> Name in INI-Datei: "Stadt"  <br/> ||
|Bundesland/Kanton  <br/> |Bundesland (optional)  <br/> Name in INI-Datei: "Status"  <br/> ||
|Basis-VM-IP-Adresse  <br/> |Die IP-Adresse der Basis temporäre VM, die zum Erstellen der VHDX für alle Cloud Connector virtuelle Computer verwendet werden. Diese IP muss sich in dem Umkreissubnetz des Unternehmensnetzwerks befinden, das im nächsten Schritt definiert wird, und benötigt Internetzugriff. Achten Sie darauf, das Standardgateway des Unternehmens und den ins Internet routbaren DNS-Server zu definieren.  <br/> Name in INI-Datei: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 und höher  <br/> |Die Adresse des Windows Server Update Services (WSUS) – ein Intranetserver zum Hosten von Updates von Microsoft Update.  <br/> Sie müssen keine Angabe machen, wenn WSUS nicht benötigt wird.   <br/> ||
|Subnetzmaske für internes Netzwerk  <br/> |Cloud-Connector konfiguriert ein IP-Netzwerk für die interne Kommunikation zwischen den Komponenten von Cloud-Connector. Der Edge muss außerdem mit einem anderen Subnetz verbunden sein, das Internetkonnektivität zulässt.  <br/> Name in INI-Datei: "CorpnetIPPrefixLength" unter "Parameter für einen Pool von VM-Netzwerk"  <br/> ||
|Subnetzmaske für externes Netzwerk   <br/> |Für das externe Netzwerk der Edgekomponente.  <br/> Name in INI-Datei: "InternetIPPrefix" unter "Parameter für einen Pool von VM-Netzwerk"  <br/> ||
|Switch-Name für internes Netzwerk  <br/> |Name für Switches, der für das interne Netzwerk Cloud Connector verwendet werden soll.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in INI-Datei: "CorpnetSwitchName" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Switch-Name für externes Netzwerk  <br/> |Name für Switches, der für das externe Connector Cloud-Netzwerk verwendet wird.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in INI-Datei: "InternetSwitchName" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Standardgateway für internes Netzwerk  <br/> |Dieses Gateway muss ermöglichen den Zugriff auf das Internet (Internet erfordert zudem die Einstellung des DNS-Servers) und wird für interne Schnittstellen Cloud Connector Komponenten konfiguriert werden.  <br/> Name in INI-Datei: "CorpnetDefaultGateway" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Standardgateway für die externe Schnittstelle der Edgekomponente  <br/> |Wird auf der externen Schnittstelle der Edgekomponente konfiguriert.  <br/> Name in INI-Datei: "InternetDefaultGateway" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|DNS-Server für internes Netzwerk  <br/> |Wird auf der internen Schnittstelle der temporären VM konfiguriert. Muss namensauflösung für Internet-Namen enthalten. Ohne einen DNS-Server Internetzugang schlägt fehl und Bereitstellung wird nicht abgeschlossen.  <br/> Name in INI-Datei: "CorpnetDNSIPAddress" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|DNS-Server für externe Schnittstelle der Edgekomponente  <br/> |Wird auf der externen Schnittstelle der Edge konfiguriert.  <br/> Name in INI-Datei: "InternetDNSIPAddress" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Management-Switch-Name  <br/> |Management Befehlszeilenoption ist eine temporäre, die automatisch erstellt und, für die Konfiguration von Cloud-Connector während der Bereitstellung verwendet werden. Nach der Bereitstellung wird er automatisch getrennt. Es muss ein anderes Subnetz aus anderen Netzwerken, die in der Cloud Connector verwendet.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in INI-Datei: "ManagementSwitchName" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Managementsubnetzadresse/-subnetzmaske  <br/> |Management Subnetz ist eine temporäre Subnetz, die automatisch erstellt und, für die Konfiguration von Cloud-Connector während der Bereitstellung verwendet werden. Nach der Bereitstellung wird es automatisch entfernt. Es muss ein anderes Subnetz aus anderen Netzwerken, die in der Cloud Connector verwendet.  <br/> Namen in INI-Datei: "ManagementIPPrefix" und "ManagementIPPrefixLength" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Zentralen Verwaltungsspeicher (CMS) Computer  <br/> |Ein einzelner FQDN wird für den zentralen Verwaltungsspeicher (CMS) verwendet. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in INI-Datei: "ServerName" unter "Parameter für primären zentralen-Verwaltungsdienst  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> (CMS-Poolname = Servername)  <br/> |
|CMS-Maschine – IP-Adresse  <br/> |IP-Adresse für CMS-Server (intern im Umkreisnetzwerk).  <br/> Name in INI-Datei: "IP" unter "Parameter für primären zentralen-Verwaltungsdienst  <br/> ||
|Name Dateifreigabe   <br/> |Freigabenamen für Skype für Geschäftsdaten (beispielsweise CmsFileStore) Replikation auf CMS-Server erstellt werden.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in INI-Datei: "CmsFileStore" unter "Parameter für primären zentralen-Verwaltungsdienst  <br/> ||
|Mediation Komponente Poolnamen  <br/> |Pool-Name des Vermittlungsservers-Komponente. Tragen Sie nur den NetBIOS-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in INI-Datei: "PoolName" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Mediation Komponentenname  <br/> |Name der Vermittlungskomponente 1. Geben Sie nur den NetBIOS-Namen ein; zum Erstellen des FQDN wird die AD-Domäne verwendet.   <br/> Name in INI-Datei: "ServerName" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Mediation Komponente Computer IP-Adresse  <br/> |Interne Corpnet IP für Mediation Komponente (intern im Umkreisnetzwerk).  <br/> Name in INI-Datei: "IP" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> ||
|Interner Name des Edgepools  <br/> |Pool-Name des Edge-Komponente. Tragen Sie nur den NetBIOS-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in INI-Datei: "InternalPoolName" unter "Parameter für einen Pool von Edge-Server"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Interner Name des Edgeservers  <br/> |Komponentenname der Edgekomponente. Geben Sie nur den NetBIOS-Namen ein; zum Erstellen des FQDN wird die AD-Domäne verwendet.   <br/> Name in INI-Datei: "InternalServerName" unter "Parameter für einen Pool von Edge-Server"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Interne IP des Edgeservers   <br/> |Interne Umkreisnetzwerk Netzwerk IP des Edge-Komponente zur Kommunikation mit anderen Komponenten von Cloud-Connector.  <br/> Name in INI-Datei: "InternalServerIPs" unter "Parameter für einen Pool von Edge-Server"  <br/> ||
|Externer Name des Zugriffspools  <br/> |Name des Zugriffs-Edgediensts, z. B. AP. Dieser Name muss mit dem für das SSL-Zertifikat vorgesehenen Namen übereinstimmen. Geben Sie nur den NetBIOS-Namen ein. Zum Erstellen des FQDN wird der Name der SIP-Domäne verwendet. Einen externen Pool-Name wird für alle Edge-Komponenten im Pool verwendet werden. Ein Pool von Zugriffs-Edgeserver ist pro PSTN-Website erforderlich.  <br/> Name in INI-Datei: "ExternalSIPPoolName" unter "Parameter für einen Pool von Edge-Server"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> "sip-" ist reserviert und kann daher nicht als Namen verwendet werden.  <br/> Der generierte FQDN-Name muss mit dem für das SSL-Zertifikat bereitgestellten Namen übereinstimmen.   <br/> |
|Externe IP-Adresse des Zugriffs-Edgeservers  <br/> |Externe IP des Edge-Komponente - entweder öffentliche IP-Adresse, wenn keine NAT verfügbar ist oder übersetzt IP (Bitte angeben beide Adressen bei zugeordnet).  <br/> Name in INI-Datei: "ExternalSIPIPs" unter "Parameter für einen Pool von Edge-Server"  <br/> ||
|Mediarelay-Name  <br/> |Name des Audio/Video-Mediarelay-Edgediensts, z. B. MR. Ein externer Poolname wird für alle Edgekomponenten in dem Pool verwendet. Ein Mediarelay Edge-Pool ist pro PSTN-Website erforderlich.  <br/> Name in INI-Datei: "ExternalMRFQDNPoolName" unter "Parameter für einen Pool von Edge-Server"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Externe IP-Adresse des Media Relay Rands  <br/> |Derzeit nur eine IP wird, unterstützt, also die gleiche IP-Adresse als Zugriffs-Edgeservers, öffentlich "oder" zugeordnete IP (Bitte angeben beide Adressen bei zugeordnet). Die gleiche Adresse als Edge-Komponente externe IP des Zugriffs-Edgeservers kann entsprechen. Beachten Sie, wenn Edge hinter NAT-Gerät ist, müssen Sie auch den Wert für den nächsten Parameter angeben.  <br/> Name in INI-Datei: "ExternalMRIPs" unter "Parameter für einen Pool von Edge-Server"  <br/> ||
|Externe IP des Media Relay Edge (wenn Edge hinter NAT-Gerät ist)  <br/> |Wenn sich der Edge hinter der NAT befindet, müssen Sie auch die öffentliche Adresse des NAT-Geräts angeben.  <br/> Name in INI-Datei: "ExternalMRPublicIPs" unter "Parameter für einen Pool von Edge-Server"  <br/> ||
|VoIP-Gateway 1 Hersteller und Modell  <br/> |Geben Sie den Hersteller und Modell des SBC-VoIP-Gateways. Beachten Sie, dass Sie ein Gerät oder einen SIP-Trunk aus der Liste der getesteten Geräte unter verbinden können [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|VoIP-Gateway 2 Stellen und Modell (kopieren diese Zeile aus, wenn Sie mehr als 2 Gateways verwenden)  <br/> |Geben Sie den Hersteller und Modell des VoIP-Gateways. Beachten Sie, dass Sie ein Gerät, aus der Liste der getesteten Geräte unter anschließen können [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|Namen von VoIP-Gateway 1  <br/> |Wird zusammen mit der AD-Domäne verwendet, um den FQDN des Computers zu erstellen. Erforderlich, falls eine TLS-Verbindung zwischen der Vermittlungskomponente und dem VoIP-Gateway hergestellt werden soll. Wenn Sie nicht vorhaben, FQDN verwenden – beispielsweise TLS ist nicht erforderlich oder VoIP-Gateway unterstützt keine Verbindung mit der FQDN (nur IP) – Geben Sie an.  <br/> ||
|VoIP-Gateway 2 Name (Kopie dieser Zeile, wenn Sie mehr als 2 Gateways verwenden)  <br/> |Wird zusammen mit der AD-Domäne verwendet, um den FQDN des Computers zu erstellen. Erforderlich, falls eine TLS-Verbindung zwischen Vermittlungskomponente und VoIP-Gateway hergestellt werden soll. Wenn Sie nicht vorhaben, FQDN verwenden – beispielsweise TLS ist nicht erforderlich oder VoIP-Gateway unterstützt keine Verbindung mit der FQDN (nur IP) – Geben Sie an.  <br/> ||
|IP-Adresse für VoIP-Gateway 1  <br/> |IP-Adresse des VoIP-Gateways  <br/> ||
|VoIP-Gateway 2 IP-Adresse (Kopie dieser Zeile, wenn Sie mehr als 2 Gateways verwenden)  <br/> |IP-Adresse des VoIP-Gateways  <br/> ||
|VoIP-Gateway 1 Port # (Kopie dieser Zeile, wenn Sie mehr als 2 Gateways verwenden)  <br/> |Nummer des Ports, den der VoIP-Gateway-SIP-Trunk überwacht, z. B. 5060  <br/> ||
|VoIP-Gateway 2 Port #  <br/> |Nummer des Ports, den der VoIP-Gateway-SIP-Trunk überwacht, z. B. 5060  <br/> ||
|VoIP-Gateway 1-Protokoll für die SIP-Datenverkehr  <br/> |TCP oder TLS  <br/> ||
|VoIP-Gateway-2-Protokoll für den SIP-Datenverkehr (Kopie dieser Zeile, wenn Sie mehr als 2 Gateways verwenden)  <br/> |TCP oder TLS  <br/> ||
|Externer Medienportbereich für Datenverkehr von der bzw. zur Edgekomponente  <br/> |TCP/UDP-Port-Bereich für Mediendatenverkehr zum und vom externen Schnittstelle des Edgeservers. Muss immer über 50 000 starten. Weitere Informationen finden Sie unter "Ports und Protokolle".  <br/> |50000 59 999  <br/> |
|Medienportbereich zu/aus der Mediation Komponente über die interne Firewall kommunizieren.  <br/> |UDP-Portbereich an, der die Mediation Komponente für die Kommunikation mit Clients und -Gateways (Empfehlung 4 Ports pro Anruf) verwendet wird.  <br/> ||
|Medienportbereich zu/aus Skype für Business-Client über die interne Firewall kommunizieren  <br/> |Beachten Sie bei der Planung, dass dies nicht geändert werden kann. Ports in der internen Firewall für die Kommunikation zwischen Skype für Business Clients innerhalb des internen Netzwerks und mit der Komponente Mediation geöffnet werden müssen.  <br/> |50000–50019  <br/> |
|Kennwort für das öffentliche Zertifikat  <br/> |Muss im Skript angegeben sein  <br/> ||
|Administratorkennwort für den sicheren Modus  <br/> Nur Version 1.4.2  <br/> |Administratorkennwort für den sicheren Modus und die CC-Domäne  <br/> ||
|Connector-Domänenadministrator Cloud-Kennwort  <br/> Nur Version 1.4.2  <br/> |Kennwort für die Cloud Connector Domänenadministrator (anders Ihrer Produktionsdomäne). Der Benutzername lautet „Administrator“. Sie können den Benutzernamen nicht ändern.  <br/> ||
|Administratorkennwort virtuelle Maschinen  <br/> Nur Version 1.4.2  <br/> |Wird im Zuge der Bereitstellung verwendet, um das Verwaltungsnetzwerk zu konfigurieren.  <br/> Der Benutzername lautet „Administrator“. Sie können den Benutzernamen nicht ändern.   <br/> ||
|CABackupFile  <br/> Version 2.0 und höher  <br/> |Verwendet zum Speichern von Dienst der Zertifizierungsstelle aus Active Directory-Server für eine Datei bei der Bereitstellung von mehreren Appliances in einer Cloud-Connector-Website. Sie sicher, dass werden das gleiche Kennwort für alle Einheiten innerhalb einer Cloud-Connector-Website verwenden, um die Sicherungsdatei Zertifizierungsstelle auf neue importieren Appliance erfolgreich hinzugefügt.  <br/> ||
|Nur Version 2.0  <br/> Version 2.0 und höher   <br/> |Wird für den Cloud Connector-Verwaltungsdienst verwendet und benötigt Zugriff auf das Cloud Connector-Standortverzeichnis. Achten Sie darauf, für alle Appliances an einem Cloud Connector-Standort das gleiche Kennwort zu verwenden.   <br/> ||
|Office 365-Mandantenadministrator  <br/> | Das Konto wird von Cloud Connector verwendet, um Mandanteneinstellungen für Cloud Connector zu aktualisieren und zu verwalten: <br/>  Version 2.0 und höher: Anmeldeinformationen für einen dedizierten Office 365-Konto mit Skype für Business Administratorrechte. <br/>  Versionen vor 2.0: Anmeldeinformationen für ein dediziertes Office 365-Konto mit den Rechten eines globalen Mandantenadministrators <br/> ||
|Aktivieren von REFER-Unterstützung  <br/> |Dadurch wird festgelegt, ob „SIP REFER-Unterstützung“ in der Trunk-Konfiguration zu Ihrer IP/PBX aktiviert oder deaktiviert ist. Der Standardwert ist „TRUE“ (WAHR). Sofern Ihr IP/PBX-Gateway „REFER-Unterstützung“ unterstützt, belassen Sie die Einstellung auf „WAHR“. Wenn nicht, muss dieser Wert in „FALSE“ (FALSCH) geändert werden. Wenn Sie nicht sicher sind, ob Ihre Gateway REFER unterstützt, finden Sie [qualifizierten IP-PBXs und Gateways](https://technet.microsoft.com/en-us/office/dn788945).  <br/> ||
|EnableFastFailoverTimer  <br/> Version 2.0 und höher  <br/> |Mit dem Standardwert "True", werden Wenn ausgehende Anrufe vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden sie zum nächsten verfügbaren Gateway weitergeleitet werden; Wenn es keine zusätzlichen Trunks sind wird der Anruf automatisch gelöscht werden.  <br/> Wenn in einer Organisation langsame Netzwerke und Gatewayreaktionen vorliegen oder der Aufbau von Anrufen mehr als zehn Sekunden in Anspruch nimmt, kann dies dazu führen, dass Anrufe unnötig getrennt werden.   <br/> Platzieren von Anrufen an einigen Ländern kann beispielsweise die Vereinigte Arabische Emirate oder Afghanistan Anruf einrichten Prozesses dauern mehr als 10 Sekunden. Sie benötigen, ändern Sie den Wert auf false festgelegt, wenn Sie ähnliche Probleme auftreten. Vergessen Sie nicht die entsprechende Einstellung auf den verbundenen SBC oder das Gateway zu ändern.  <br/> Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „True“.  <br/> ||
|ForwardCallHistory  <br/> Version 2.0 und höher  <br/> | Dieser Parameter wird verwendet, um SIP-Header zu aktivieren, mit deren Hilfe der anfängliche Anrufer in Szenarien mit gleichzeitigem Klingeln, Anrufweiterleitung und Anrufdurchstellung gemeldet wird. Wenn Sie den Parameter auf „True“ festlegen, werden zwei SIP-Header aktiviert:<br/>  Referred-By <br/>  Referred-By <br/>  Die Kopfzeile "History-Info" wird für die SIP-Anforderungen der Zielversion und "Package-Lösung(en) einen standard Mechanismus für das Erfassen der Anforderung Verlaufsinformationen zum Aktivieren einer Vielzahl von Diensten für Netzwerke und Endbenutzer" ([RFC 4244 - Abschnitt 1.1](http://www.ietf.org/rfc/rfc4244.txt)). Für die Cloud Connector-Trunkschnittstellen wird diese in Szenarien mit gleichzeitigem Klingeln und Anrufweiterleitung verwendet.  <br/>  Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „False“.<br/> ||
|PAI weiterleiten  <br/> Version 2.0 und höher  <br/> |Pai des ist eine private Erweiterung SIP, mit dem SIP-Server die Identität der authentifizierte Benutzer anfordern kann. Für die SIP-Trunk-Dienstanbieter kann PAI für Bill zum Zwecke verwendet werden, die "History-Info" und weitergeleitet von Kopfzeilen nicht vorhanden sind. Beim Weiterleiten P-Asserted-Identity in der Konfiguration aktiviert ist, wird der Vermittlungsserver PAI-Kopfzeilen mit SIP weiterleiten &amp; Tel URI von Cloud-Connector auf dem SIP-Trunk. Der Vermittlungsserver wird PAI-Kopfzeilen mit tel-URI weiterleiten &amp; e. 164-Nummern, die nur für die SIP-Trunk an Cloud-Konnektor empfangen. Der Vermittlungsserver werden auch alle Privacy-Header in beide Richtungen empfangen weiterleiten. Wenn der SIP-Anforderung gesendet vom Vermittlungsserver eine private Kopfzeile des Formulars - umfasst "Privacy: Id" in Verbindung mit dem PAI-Header, klicken Sie dann die bestätigte Identität beibehalten werden sollten private außerhalb der vertrauenswürdigen Domäne von Netzwerk.  <br/> Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „False“.  <br/> ||
   
### <a name="certificate-requirements"></a>Zertifikatanforderungen
<a name="BKMK_Certs"> </a>

Für jede Edgekomponente wird ein Zertifikat von einer öffentlichen Zertifizierungsstelle benötigt. Die Zertifikate müssen mit einem exportierbaren privaten Schlüssel versehen sein, der zwischen Edgekomponenten kopiert wird. Um die Zertifikatanforderungen zu erfüllen, müssen Sie sich für eine der folgenden Optionen entscheiden und den Antragstellernamen (Subject Name, SN) sowie den alternativen Antragstellernamen (Subject Alternative Name, SAN) für das Zertifikat angeben.
  
 **Wenn Sie über eine einzige SIP-Domäne verfügen:**
  
- **Option 1.** Der Antragstellername muss den Poolnamen enthalten, den Sie den Edgekomponenten zugewiesen haben. Beachten Sie, dass der Antragstellername sip.sipdomain.com werden kann, da dieser Name für die online Skype für Business Edge-Komponente reserviert ist. Der alternative Antragstellername muss „sip.sipdomain.com“ enthalten sowie den Namen des Zugriffs-Edgepools:
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, 
acessedgepoolnameforsite1.sipdomain.com 

  ```

- 
    
    **Option 2.** Wenn Sie ein einzelnes Platzhalterzertifikat auf allen Servern der Edge-Pool verwenden Sie bereitstellen möchten, können Platzhalter SAN-Eintrag des \*. sipdomain.com anstelle der Edge-Pool-Name im Zertifikat. Der Antragstellername kann der Zugriffs-Edgepoolname eines der bereitgestellten Edgepools sein:
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com

  ```

    > [!NOTE]
    > Sie müssen einen externen DNS-Eintrag für Sip nicht erstellen. \<Sipdomain\>.com, da dieser Name zu Office 365-Bereitstellung gehört. 
  
> [!NOTE]
> Wenn Sie ein einzelnes Zertifikat für alle in Ihrer Organisation bereitgestellten Edgepools verwenden möchten und kein Zertifikat mit Platzhaltern wie in Option 2 definiert nutzen können, dann müssen Sie den FQDN für alle bereitgestellten Edgepools im Namen für den alternativen Antragstellernamen in das Zertifikat einschließen.  
  
 **Wenn Sie über mehrere SIP-Domänen verfügen:**
  
Sie müssen für jede SIP-Domäne „sip.sipdomain.com“ sowie den Namen der Zugriffs-Edgepools für jede Domäne hinzufügen (dies kann ein einzelner physischer Pool mit unterschiedlichen Namen sein). Hier ist ein Beispiel für SN- und SAN-Einträge in einem Szenario mit mehreren SIP-Domänen: 
  
- **Option 1.** Der Antragstellername muss den Poolnamen enthalten, den Sie für edgekomponenten zugewiesen. Beachten Sie, dass der Antragstellername sip.sipdomain.com werden kann, da dieser Name für die online Skype für Business Edge-Komponente reserviert ist. Der alternative Antragstellername muss „sip.sipdomain.com“ enthalten sowie den Namen des Zugriffs-Edgepools:
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com,
 sip.sipdomain2.com, acessedgepoolnameforsite1.sipdomain1.com 

  ```

- 
    
    **Option 2.** Wenn Sie ein einzelnes Platzhalterzertifikat auf allen Servern der Edge-Pool verwenden Sie bereitstellen möchten, können Platzhalter SAN-Eintrag des \*. sipdomain.com anstelle der Edge-Pool-Name im Zertifikat. Der Antragstellername kann der Zugriffs-Edgepoolname eines der bereitgestellten Edgepools sein:
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com, SAN = *.sipdomain1.com 
  ```

    > [!NOTE]
    > Sie müssen einen externen DNS-Eintrag für Sip nicht erstellen. \<Sipdomain\>.com, da dieser Name zu Office 365-Bereitstellung gehört. 
  
Für die Bereitstellung können Sie folgende Tabelle verwenden:
  
|**Option**|**Beschreibung**|**Notizen**|
|:-----|:-----|:-----|
|Welche Option möchten Sie für Ihre Bereitstellung verwenden?  <br/> |Option 1 oder 2  <br/> ||
|SN  <br/> |Geben Sie den SN für Ihr Zertifikat an.  <br/> ||
|SAN  <br/> |Geben Sie den SAN für Ihr Zertifikat an.  <br/> ||
   
Wenn Sie zwischen dem Gateway und dem Vermittlungsserver TLS verwenden, müssen Sie sich das Stammzertifikat oder die vollständige Zertifikatkette für das Zertifikat besorgen, das dem Gateway zugewiesen ist.
  
## <a name="dial-plan-considerations"></a>Hinweise zum Wählplan
<a name="BKMK_DailPlan"> </a>

Sie müssen für Cloud Connector einen Onlinewählplan verwenden. Weitere Informationen zum Konfigurieren einer online Wählplan, finden Sie unter [Was sind Wählpläne PSTN aufrufen?](https://support.office.com/en-US/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b)
  
## <a name="high-availability-considerations"></a>Überlegungen zur hohen Verfügbarkeit
<a name="BKMK_HA"> </a>

Wenn Sie für hohe Verfügbarkeit Cloud Connector Edition bereitstellen, stellen Sie mindestens zwei Einheiten, die als Sicherung für miteinander fungieren bereit. Jede Appliance umfasst vier Komponenten: Edge, Mediation, zentralen Management Store (CMS) und dem Domänencontroller.
  
Wenn eine Komponente innerhalb einer Appliance ausfällt, im Allgemeinen Cloud Connector Edition können weiterhin Anrufe verarbeiten, jedoch müssen Sie Folgendes berücksichtigen:
  
- **Überlegungen zu Vermittlungs-, CMS- und Domänencontrollerkomponente**
    
    Wird davon ausgegangen Sie, dass die CMS oder Domain Controller-Komponente in einer Appliance ausfällt. Die Appliance kann weiterhin eingehende und ausgehende Anrufe verarbeiten – Wenn Sie eine Komponente Mediation neu starten, wenn der Domänencontroller oder CMS-Komponente nicht erreichbar ist, Mediation werden jedoch nicht funktionieren. Das gleiche gilt für die CMS-Komponente neu gestartet, wenn der Domänencontroller ausgefallen ist. 
    
    **Empfehlung:** Überprüfen Sie vor dem Neustart Komponenten, die Verfügbarkeit von anderen Komponenten in der Appliance.
    
- **Überlegungen zur Edgekomponente**
    
    Wenn die Edgekomponente einer Appliance nicht verfügbar ist, unterscheidet sich das Verhalten für eingehende und ausgehende Anrufe wie folgt:
    
  - **Rufen Sie ausgehend**– einen Anruf von Ihrer Benutzer in das Internet mit einem PSTN-Netzwerk.
    
    Der Mechanismus zur Anrufverteilung in der Cloud stellt fest, dass eine Edgekomponente ausgefallen ist, und leitet alle Anrufe an eine andere Appliance weiter. Der ausgehende Anruf ist also erfolgreich.
    
  - **Rufen Sie eingehende**– einen Anruf aus dem PSTN-Netzwerk an ein Benutzer, der in einem lokalen Netzwerk oder im Internet ist.
    
     Wenn die Edgekomponente der Appliance, die den Anruf angenommen hat, nicht funktioniert, sind eingehende Anrufe an diese Appliance nicht erfolgreich, weil die Vermittlungskomponente den Anruf nicht an die Edgekomponente der anderen Appliance umleiten kann.
    
    **Empfehlung:** Verfügen Sie monitoring-System. Wenn Sie eine Störung der Edge-Komponente identifiziert haben, fahren Sie alle Komponenten in der Appliance die Edge-Komponente ist, in dem nicht verfügbar.
    
## <a name="cloud-connector-media-flow"></a>Cloud Connector-Mediendatenverkehr
<a name="BKMK_MediaFlow"> </a>

Die folgenden Diagramme beschreiben den Ablauf des eines ausgehenden und eingehenden Anrufs über Cloud Connector Edition. Die Diagramme veranschaulichen, wie eine Verbindung hergestellt wird.
  
Im ersten Diagramm tätigt ein interner Nutzer einen Anruf und geht dabei wie folgt vor:
  
1. Dave – ein Benutzer, der online verwaltet wird, sich jetzt aber im internen Netzwerk befindet – ruft einen externen Festnetzbenutzer an.
    
2. SIP-Datenverkehr Routen zu Skype für Business Online.
    
3. Skype für Business Online führt eine umgekehrte Anzahl Suche die Anzahl der. Die Anzahl Reverse-Lookup ein Fehler auftritt, da diese Nummer nicht für jeden, der Skype für Unternehmensorganisation gehört.
    
4. Der Anruf wird an die Edgekomponente weitergeleitet (zunächst SIP und Mediendatenverkehr über Online Edge; die Mediendaten gelangen dann über die interne Firewall zur Vermittlungskomponente).
    
5. Sofern diese Route vorhanden ist, überträgt die Edgekomponente die Daten an die Vermittlungskomponente im Umkreisnetzwerk.
    
6. Die Vermittlungskomponente leitet den Datenverkehr schließlich an das PSTN-Gateway weiter.
    
![Ausgehender Mediendatenfluss für Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)
  
Im nächsten Diagramm erhält ein interner Benutzer einen Anruf:
  
1. Das PSTN-Gateway empfängt einen Anruf für Benutzer Dave, der online verwaltet wird, sich jetzt aber im internen Netzwerk befindet.
    
2. Der SIP-Datenverkehr wird an die Vermittlungskomponente weitergeleitet.
    
3. Die Komponente Mediation sendet SIP-Datenverkehr an den Edge-Komponente, und klicken Sie dann er wechselt zu Skype für Business Online.
    
4. Skype für Business Online führt einen Reverse Anzahl Lookup die Anzahl der und feststellt, dass diese Benutzer Dave ist.
    
5. Die SIP-Signale werden an alle Geräte von Dave gesendet.
    
6. Der Mediendatenverkehr zwischen Gateway und Vermittlungskomponente sowie zwischen Vermittlungskomponente und Endpunkt wird hergestellt.
    
![Eingehender Mediendatenfluss für Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)
  
## <a name="monitoring-and-troubleshooting"></a>Überwachung und Problembehandlung
<a name="BKMK_Monitor"> </a>

Der Mechanismus für Überwachung und Problembehandlung wird mit jeder Cloud Connector-Appliance automatisch installiert. Der Mechanismus erkennt die folgenden Ereignisse:
  
- Eine oder mehrere virtuelle Maschinen einer Cloud Connector-Appliance sind nicht mit einem internen Switch oder einem virtuellen Internetswitch verbunden.
    
- Eine oder mehrere virtuelle Maschinen einer Cloud Connector-Appliance wurden gespeichert oder beendet.
    
- Dienste werden nicht ausgeführt. 
    
  Wenn eines der folgenden Ereignisse erkannt wurde, wird die gesamte Cloud Connector Appliance ein Ausgleich vorgenommen und zu verhindern, dass den Versuch, Anrufe an eine fehlerhafte Einheit herzustellen als offline markiert. Die Cloud Connector-Funktionen für automatische Wiederherstellung stellen anschließend die Dienste wieder her und kennzeichnen die Appliance als online. Wenn die automatische Wiederherstellung aus irgendeinem Grund ein Fehler auftritt, finden Sie unter [Problembehandlung bei der Bereitstellung von Cloud-Connector](troubleshoot-your-cloud-connector-deployment.md).
    
  - In der virtuellen Maschine für den zentralen Verwaltungsspeicher:  
    
     - Master-Replikations-Agent von Skype for Business
    
     - Replikat-Replikations-Agent von Skype for Business
    
  - In der virtuellen Maschine für den Vermittlungsserver:
    
     - Replikat-Replikations-Agent von Skype for Business
    
     - Skype for Business Server-Vermittlung
    
  - In der virtuellen Maschine für den Edgeserver:
    
     - Replikat-Replikations-Agent von Skype for Business
    
     -  Skype for Business Server-Zugriffs-Edge
    
     - Audio-Video-Edge von Skype for Business Server
    
     - Audio-Video-Authentifizierung von Skype for Business Server
    
     - Webkonferenz-Edge von Skype for Business Server
    
- Eingehende Regel der Windows-Firewall für „CS RTCSRV“ auf dem Edge, „CS RTCMEDSRV“ auf dem Vermittlungsserver ist deaktiviert.
    
Cloud Connector 2.1 und höher unterstützt das Überwachen von Cloud Connector mithilfe von Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Monitor Cloud Connector mit Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)
  
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_MoreInfo"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen Sie Ihr Telefonsystem in Office 365 (PBX zu Cloud)-Lösung](plan-your-phone-system-cloud-pbx-solution.md)
    
- [Konfigurieren und Verwalten von Skype für Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)
    
- [Planen Sie für die medienumgehung in der Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
    
- [Die medienumgehung in der Cloud Connector Edition bereitstellen](deploy-media-bypass-in-cloud-connector.md)
    

