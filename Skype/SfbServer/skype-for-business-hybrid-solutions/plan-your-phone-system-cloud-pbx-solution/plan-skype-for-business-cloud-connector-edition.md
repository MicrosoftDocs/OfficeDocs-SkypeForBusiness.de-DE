---
title: Planen von Skype for Business Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Hier finden Sie Informationen zu Skype for Business Cloud Connector Edition, eine Gruppe gepackter virtueller Computer (VMS), die eine lokale PSTN-Konnektivität mit dem Telefon System in Office 365 (Cloud PBX) implementieren.
ms.openlocfilehash: 9530fa2815dc491e6cda3579a801c3d5430f9b41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018146"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planen von Skype for Business Cloud Connector Edition

Hier finden Sie Informationen zu Skype for Business Cloud Connector Edition, eine Gruppe gepackter virtueller Computer (VMS), die eine lokale PSTN-Konnektivität mit dem Telefon System in Office 365 (Cloud PBX) implementieren.

Cloud Connector Edition ist möglicherweise die richtige Lösung für Ihre Organisation, wenn Sie noch nicht über eine vorhandene lync Server-oder Skype for Business Server-Bereitstellung verfügen. Wenn Sie noch untersuchen, welches Telefon System in Office 365 Lösung für Ihr Unternehmen geeignet ist, lesen Sie [Microsoft Telephony Solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions).

In diesem Dokument werden die Cloud Connector Edition-Anforderungen und unterstützten Topologien beschrieben, und Sie können Ihre Cloud Connector Edition-Bereitstellung planen. Lesen Sie dieses Thema, bevor Sie Ihre Cloud Connector-Umgebung konfigurieren. Wenn Sie bereit sind, Cloud Connector Edition bereitzustellen und zu konfigurieren, lesen Sie [Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

Cloud Connector Edition 2,1 ist jetzt verfügbar. Wenn Sie noch kein Upgrade auf 2,1 durchgeführt haben, lesen Sie [Upgrade auf eine neue Version von Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Sie finden die Installationsdatei unter [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).

> [!NOTE]
> Microsoft unterstützt die frühere Version von Cloud Connector Edition für 60 Tage nach der Veröffentlichung einer neuen Version. Microsoft unterstützt Version 2.0.1 für 60 Tage nach der Veröffentlichung von 2,1, damit Sie Zeit für ein Upgrade erhalten. Alle Vorgängerversionen von 2.0.1 werden nicht mehr unterstützt.

Cloud Connector Edition ist ein Hybrid Angebot, das aus einer Reihe von virtuellen Computern (VMS) besteht, die die lokale PSTN-Konnektivität mit dem Telefon System in Office 365 implementieren. Durch die Bereitstellung einer minimalen Skype for Business Server Topologie in einer virtualisierten Umgebung können Benutzer in Ihrer Organisation, die in der Cloud verwaltet werden, PBX-Dienste von der Microsoft-Cloud empfangen, die PSTN-Konnektivität wird jedoch über die vorhandene lokale VoIP-Verbindung bereitgestellt. Infrastruktur.

![Topologie-Diagramm mit Cloud PBX-Gateway, das Cloud PBX mit einer lokalen Bereitstellung von Skype for Business verbindet.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Da Cloud Connector die Integration von Telefonsystemen in Office 365 Diensten in Ihre vorhandene Telefonie-Umgebung ermöglicht (beispielsweise Nebenstellenanlage, analoge Geräte und Callcenter), können Sie eine phasenweise Migration von Ihrer vorhandenen Telefonielösung zu telefonieren implementieren. System in Office 365.

Nehmen Sie beispielsweise an, dass Ihr Unternehmen über ein ausgeklügeltes Callcenter mit spezifischen Funktionen verfügt, die das Telefon System in Office 365 nicht bereitstellt. Sie können die Benutzer des Callcenters mit der vorhandenen Lösung verlassen, aber andere Benutzer in Office 365 an das Telefon System verlagern.

Cloud Connector stellt eine Weiterleitung zwischen den lokal verwalteten Benutzern und online zur Verfügung, und Sie können Ihren eigenen PSTN-Anbieter mit Telefon System in Office 365 verwenden.

Berücksichtigen Sie beim Planen der Cloud Connector Edition-Bereitstellung Folgendes:

- Um Cloud Connector zum Nutzen von Cloud-VoIP-Lösungen nutzen zu können, müssen Sie sich für einen Office 365 Mandanten registrieren, der das Telefon System in Office 365 enthält. Wenn Sie noch nicht über einen Office 365-Mandanten verfügen, erfahren Sie hier, wie Sie sich anmelden können: [Office 365 for Business](https://products.office.com/business/office). Beachten Sie, dass Sie sich für einen Plan registrieren müssen, der Skype for Business Online enthält.

- Zum Registrieren von Cloud Connector-Appliances mit dem Skype for Business Online-Dienst und zum Ausführen verschiedener Cmdlets erfordert Cloud Connector 2,0 und höher ein dediziertes Office 365 Konto mit den Skype for Business Mandanten Administrator Rechten. Cloud Connector-Versionen vor 2,0 erfordern ein dediziertes Office 365 Konto mit globalen Mandanten Administrator Rechten.

- Cloud Connector erfordert keine vollständige lokale Skype for Business Server-Bereitstellung.

    Derzeit kann Cloud Connector nicht mit lync oder Skype for Business lokalen Servern nebeneinander existieren. Wenn Sie vorhandene lync-oder Skype for Business-Benutzer zu Office 365 migrieren und die lokale Telefonie für Ihre Benutzer bereitstellen möchten, sollten Sie das Telefon System in Office 365 mit lokaler Konnektivität in einer vorhandenen Skype for Business Server-Bereitstellung in Verbindung setzen. Weitere Informationen finden Sie unter [Plan Your Phone System in Office 365 (Cloud PBX) Solution](plan-your-phone-system-cloud-pbx-solution.md) und [Plan Phone System in Office 365 with on-premises PSTN Connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Wenn Sie eine frühere Skype for Business-oder lync Server-Bereitstellung hatten und das Schema erweitert haben, müssen Sie das Schema für die Cloud Connector-Bereitstellung nicht bereinigen, solange Sie alle Skype for Business-oder lync Server-Komponenten aus Ihrer Umgebung entfernt haben.

- Ihre Benutzer werden online verwaltet.

- Wenn Ihre Organisation die Verzeichnissynchronisierung (Dirsync) konfiguriert hat, müssen alle Konten von Benutzern, die für Hybrid VoIP geplant sind, zuerst in Ihrer lokalen Bereitstellung erstellt und dann mit der Cloud synchronisiert werden.

- Sie können Ihren aktuellen PSTN-Carrier bei Bedarf behalten.

- Wenn Sie Einwahlkonferenzen für Benutzer bereitstellen möchten, die in Cloud Connector gehostet werden, können Sie die Lizenz für PSTN-Konferenz Lizenzen kaufen oder das Angebot für Audio-Konferenz von Microsoft bezahlen.

- Die Lizenz für Audiokonferenzen (oder Pay as you go-Angebot) ist auch für die Anruf Eskalation erforderlich. Wenn ein Skype for Business Benutzer einen Anruf von einem externen PSTN-Benutzer erhält und einen weiteren Teilnehmer zu diesem Anruf hinzufügen möchte (den Anruf an eine Konferenz eskalieren), wird die Eskalation über den Microsoft-Audiokonferenzdienst ausgeführt.

- Cloud Connector 2,0 und höher unterstützt jetzt die medienumgehung. Durch die medienumgehung kann ein Client Medien direkt an den nächsten Hop (Public Switched Telephone Network, PSTN) – einen Gateway-oder Session Border Controller (SBC) – senden und die Cloud Connector Edition-Komponente aus dem Medienpfad entfernen. Weitere Informationen finden Sie unter [Plan for Media Bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2,1 und höher unterstützt Cloud Connector für die Überwachung mithilfe von Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md) .

- Cloud Connector steht in allen Ländern zur Verfügung, in denen Office 365 Enterprise E5 verfügbar ist.

Dieses Thema enthält die folgenden Abschnitte:

- [Cloud Connector Edition-Komponenten](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Cloud Connector Edition-Topologien](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Anforderungen für die Bereitstellung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informationen, die Sie vor der Bereitstellung erfassen müssen](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Überlegungen zu Wähleinstellungen](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Überlegungen zur hohen Verfügbarkeit](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Cloud Connector-Medienfluss](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Überwachung und Problembehandlung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Weitere Informationen](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Cloud Connector Edition-Komponenten
<a name="BKMK_Components"> </a>

Mit Cloud Connector Edition stellen Sie eine Gruppe von verpackten VMS bereit, die eine minimale Skype for Business Server Topologie enthalten, die aus einer Edge-Komponente, einer vermittlungskomponente und einer zentraler Verwaltungsspeicher (CMS)-Rolle besteht. Sie müssen auch einen Domänencontroller installieren, der für die interne Funktion von Cloud Connector erforderlich ist. Diese Dienste sind für eine Hybrid Konfiguration mit Ihrem Office 365-Mandanten konfiguriert, der Skype for Business Online Dienste enthält.

![Cloud Connector Edition-Komponenten](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Cloud Connector-Komponenten bieten die folgende Funktionalität:

- **Edge-Komponente** – die Kommunikation zwischen der lokalen Topologie und den Onlinediensten geht über die Edge-Komponente, die die folgenden Komponenten umfasst:

  - **Access Edge** – bietet SIP-Routing zwischen der lokalen Bereitstellung und Skype for Business Online.

  - **Medien Relay** – stellt das Routing von Medien zwischen der vermittlungskomponente und anderen Medien Endpunkten bereit.

  - **Media Relay Authentication/MRAS** -generiert Token für den Zugriff auf das Medien Relay.

- **Ausgehendes Routing** -ermöglicht den Lastenausgleich des VoIP-Datenverkehrs zwischen Gateways oder SBCS, die mit einer Cloud Connector-Appliance verbunden sind. Anrufe werden gleichmäßig zwischen allen Gateways oder SBCS aufgeteilt, die mit der Cloud Connector-Appliance verbunden sind.

    Bereitstellen von Routing an Gateways basierend auf Richtlinien. Es werden nur globale Richtlinien unterstützt, die auf Ziel (ausgehende) PSTN-Nummern basieren.

- **Zentraler Verwaltungsspeicher (CMS)-Rolle** umfasst den Konfigurationsspeicher für die Topologie-Komponenten, einschließlich der CMS-Dateiübertragung.

- **Zentraler Verwaltungsspeicher (CMS) Replica** – synchronisiert Konfigurationsinformationen aus der globalen CMS-DB auf dem CMS-Rollen Server.

- **Domänencontroller** – Cloud Connector Active Directory-Domänendienste zum Speichern aller globalen Einstellungen und Gruppen, die für die Bereitstellung von Cloud Connector-Komponenten erforderlich sind. Für jede Cloud Connector-Appliance wird eine Gesamtstruktur erstellt. Der Domänencontroller darf keine Verbindungen mit dem Produktions Active Directory haben. Active Directory Dienste umfassen Folgendes:

  - Active Directory Domain Services

  - Active Directory von Zertifikatdiensten zum ausgeben interner Zertifikate

- **Vermittlungskomponente** – Implementierung des SIP-und Mediengateway-Zuordnungs Protokolls zwischen Skype for Business-und PSTN-Gateways. Enthält ein CMS-Replikat, das die Konfiguration aus der globalen CMS-Datenbank synchronisiert.

## <a name="cloud-connector-edition-topologies"></a>Cloud Connector Edition-Topologien
<a name="BKMK_Topologies"> </a>

Im Rahmen dieser Diskussion wird auf PSTN-Standorte verwiesen. Ein PSTN-Standort ist eine Kombination von Cloud Connector-Appliances, die am gleichen Standort bereitgestellt werden und mit gemeinsamen PSTN-Gateways verbunden sind. PSTN-Standorte ermöglichen Folgendes:

- Bereitstellen von Konnektivität zu Gateways, die Ihren Benutzern am nächsten sind.

- Skalierbarkeit durch Bereitstellen mehrerer Cloud Connector-Appliances in einem oder mehreren PSTN-Standorten.

- Hohe Verfügbarkeit durch Bereitstellen mehrerer Cloud Connector-Appliances in einem einzigen PSTN-Standort.

In diesem Thema werden PSTN-Standorte vorgestellt. Weitere Informationen zum Planen Ihrer PSTN-Standorte finden Sie unter [Plan for Cloud Connector Edition PSTN Sites](plan-for-cloud-connector-edition-pstn-sites.md).

Sie können die folgenden Cloud Connector-Topologien bereitstellen:

- Eine einzelne Cloud Connector Edition-Appliance pro PSTN-Standort. Diese Topologie wird nur für Evaluierungszwecke empfohlen, da Sie keine hohe Verfügbarkeit bietet.

- Mehrere Cloud Connector Edition-Appliances pro PSTN-Standort, um eine hohe Verfügbarkeit bereitzustellen.

- Mehrere PSTN-Standorte mit mehreren Cloud Connector Edition-Appliances zur Bereitstellung von Skalierbarkeit mit hoher Verfügbarkeit. Sie können bis zu 200-Websites bereitstellen.

Berücksichtigen Sie beim Planen der Topologie Folgendes:

- Bei Cloud Connector 2,0 und höher kann ein PSTN-Standort bis zu 16 Cloud Connector-Appliances aufweisen. In früheren Versionen werden bis zu vier Appliances pro Standort unterstützt.

- Es gibt zwei Arten von Hardwarekonfigurationen, die mit Cloud Connector getestet wurden:

  - Die größere Version ist in der Lage, große Mengen gleichzeitiger Anrufe zu verarbeiten und wird in allen Arten von Produktionsumgebungen unterstützt.

  - Die kleinere Version ist für die Ausführung auf der unteren End-Hardware vorgesehen und kann für Evaluierungszwecke oder für Websites mit niedrigen Anrufvolumen verwendet werden. Wenn Sie eine kleinere Version von Cloud Connector bereitstellen, müssen Sie sich immer noch der Hardwareanforderungen der Produktions Klasse (beispielsweise duale Netzteile) bewusst sein.

- Wenn Sie über Cloud Connector Version 2,0 oder höher verfügen und die maximale Konfiguration von 16 Appliances (mit größerer Hardware) bereitstellen, kann Ihr PSTN-Standort bis zu 8.000 gleichzeitige Anrufe verarbeiten. Wenn Sie die kleinere Version bereitstellen, lautet der unterstützte Grenzwert 800.

    Sie müssen auch einige Appliances für hohe Verfügbarkeit reservieren. Die minimale Empfehlung besteht darin, dass eine Appliance für hohe Verfügbarkeit reserviert werden sollte.

  - Wenn Sie mit Version 2 eine 15 + 1-Konfiguration bereitstellen, kann Ihr PSTN-Standort bis zu 7.500 gleichzeitige Anrufe verarbeiten.

  - Wenn Sie über eine frühere Version verfügen und die maximale 3 +1-Konfiguration (mit größerer Hardware) bereitstellen, kann Ihr PSTN-Standort bis zu 1500 gleichzeitige Anrufe verarbeiten. Wenn Sie die kleinere Version bereitstellen, lautet der unterstützte Grenzwert 150.

-  Wenn Sie über mehr Anrufe pro PSTN-Standort verfügen müssen, können Sie durch die Bereitstellung zusätzlicher PSTN-Standorte am gleichen Speicherort eine horizontale Skalierung durchführen.

> [!NOTE]
> Sofern nicht anders angegeben, wird in den folgenden Diagrammen und Beispielen die Verwendung der größeren Version von Cloud Connector vorausgesetzt.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Einzelne Cloud Connector-Appliance in einem einzigen PSTN-Standort

Das folgende Diagramm zeigt eine einzelne Cloud Connector Edition-Appliance innerhalb eines einzelnen PSTN-Standorts. Beachten Sie, dass Cloud Connector aus vier VMS besteht, die aus Sicherheitsgründen auf einem physischen Hostcomputer in einem Umkreisnetzwerk installiert sind.

![Ein Cloud-Connector mit einem PSTN-Standort](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Mehrere Cloud Connector-Appliances in einem einzigen PSTN-Standort

 Für Skalierbarkeit und hohe Verfügbarkeit können Sie mehrere Cloud Connector-Editionen innerhalb eines einzelnen PSTN-Standorts verwenden, wie im folgenden Diagramm dargestellt. Dabei ist Folgendes zu berücksichtigen:

- Anrufe werden in zufälliger Reihenfolge zwischen Cloud-Konnektoren in einem Pool verteilt.

- Für Kapazitäts Planungszwecke müssen Sie die Möglichkeit berücksichtigen, die Last zu verarbeiten, wenn mindestens ein Cloud-Connector offline geht, basierend auf den folgenden Berechnungen:

  - **N + 1 Boxen.** Für die größere Version von Cloud Connector unterstützen n + 1-Boxen\*500 n gleichzeitige Anrufe mit einer Verfügbarkeit von 99,8%.

    Für die kleinere Version von Cloud Connector unterstützen n + 1-Boxen\*50 n gleichzeitige Anrufe mit einer Verfügbarkeit von 99,8%.

  - **N + 2 Felder.** Für die größere Version von Cloud Connector unterstützen n + 2-Boxen\*500 n gleichzeitige Anrufe mit einer Verfügbarkeit von 99,9%.

    Für die kleinere Version von Cloud Connector unterstützen n + 2-Boxen\*50 n gleichzeitige Anrufe mit einer Verfügbarkeit von 99,9%.

![Zwei Cloud-Konnektoren in einem PSTN-Standort](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Mehrere PSTN-Standorte mit mindestens einem Cloud Connector pro Standort

Sie können auch mehrere PSTN-Standorte mit einer oder mehreren Cloud Connector-Editionen an jedem Standort auswählen. Wenn Ihr PSTN-Standort den Grenzwert für gleichzeitige Anrufe erreicht, können Sie einen weiteren PSTN-Standort hinzufügen, um die Last zu verarbeiten.

Mit mehreren PSTN-Standorten können Sie auch Verbindungen zu Gateways bereitstellen, die Ihren Benutzern am nächsten sind. Nehmen Sie beispielsweise an, dass Sie über PSTN-Gateways in Seattle und Amsterdam verfügen. Sie können zwei PSTN-Standorte – eine in Seattle, eine in Amsterdam – bereitstellen und Benutzern die Verwendung des Ihnen am nächsten gelegenen PSTN-Standorts zuweisen. Benutzer aus Seattle werden an den PSTN-Standort und die Gateways in Seattle weitergeleitet, während Benutzer in Amsterdam an den PSTN-Standort in Amsterdam und an Gateways weitergeleitet werden:

![Cloud Connector Edition innerhalb von 2 PSTN-Standorten](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Anforderungen für die Bereitstellung
<a name="BKMK_Requirements"> </a>

Stellen Sie vor der Bereitstellung von Cloud Connector Edition sicher, dass Sie über Folgendes für Ihre Umgebung verfügen:

- **Für den Hostcomputer-** Die Cloud Connector-VMS müssen auf dedizierter Hardware bereitgestellt werden, auf der Windows Server 2012 R2 Datacenter Edition (Englisch) mit aktivierter Hyper-V-Rolle betrieben wird.

    Für die Version 2,0 und höher muss die Netzwerkkarte des Hostcomputers, die an den Skype for Business Corpnet Switch gebunden ist, über eine IP-Adresse verfügen, die im selben Subnetz wie die Cloud Connector-Unternehmensnetzwerk Computer konfiguriert ist.

- Für die Versionen 2,1 und höher muss die Host-Appliance .NET Framework 4.6.1 oder höher installiert haben.

- **Für die virtuellen Computer-** Ein Windows Server 2012 R2 ISO (Englisch)-Image (. ISO). Die ISO wird für die virtuellen Computer, auf denen Skype for Business Cloud Connector Edition ausgeführt wird, in virtuelle Festplatten konvertiert.

- Die erforderliche Hardware zur Unterstützung der Installation der vier VMs für jede Cloud Connector-Edition in Ihrer Bereitstellung. Die folgenden Konfigurationen werden empfohlen:

  - 64-Bit-Dualprozessor, sechs Kerne (12 reale Kerne), 2,50 Gigahertz (GHz) oder höher

  - 64 Gigabyte (GB) ECC-RAM

  - 4 600 GB (oder besser) 10K RPM 128M Cache SAS 6Gbps-Datenträger, konfiguriert in einer RAID 5-Konfiguration

  - Drei 1 Gbit/s-Netzwerkadapter mit hohem Durchsatz

- Wenn Sie sich für die Bereitstellung der kleineren Version von Cloud Connector Edition entscheiden, die bis zu 50 gleichzeitige Anrufe unterstützt, benötigen Sie die folgende Hardware:

  - Intel i7 4790 Quad-Core mit Intel 4600-Grafik (keine High-End-Grafiken erforderlich)

  - 32 GB DDR3-1600 nicht ECC

  - 2:1TB 7200RPM SATA III (6 Gbit/s) in RAID 0

  - Ethernet mit 2:1 Gbit/s (RJ45)

- Wenn auf dem Hostcomputer ein Proxy Server zum Durchsuchen des Internets erforderlich ist, müssen Sie die folgenden Konfigurationsänderungen vornehmen:

  - Geben Sie zum Umgehen des Proxys WinHTTP-Proxyeinstellungen an, die mit Ihrem Proxy Server festgelegt sind, und eine Umgehungsliste einschließlich der "192.168.213. \*"von ihren Cloud Connector-Verwaltungsdiensten verwendete Netzwerke und Skype for Business Corpnet-Subnetz gemäß Definition in ihrer" cloudconnector. ini-Datei. Andernfalls schlägt die Verwaltungs Konnektivität fehl, und die Bereitstellung und automatische Wiederherstellung von Cloud Connector werden verhindert. Es folgt ein Beispiel für WinHTTP-Konfigurationsbefehl: netsh WinHTTP-Proxy "10.10.10.175:8080" Bypass-List =\*". local; 1. \*; 172,20. \*; 192.168.218. \*"\<local\>".

  - Geben Sie Proxyeinstellungen pro Computer und nicht pro Benutzer an. Andernfalls tritt bei Cloud Connector-Downloads ein Fehler auf. Sie können Proxyeinstellungen pro Computer mit einer Registrierungsänderung oder mit der Gruppenrichtlinieneinstellung wie folgt angeben:

  - **Registrierung:** HKEY_LOCAL_MACHINE \software\policies\microsoft\windows\currentversion\internet Settings] ProxySettingsPerUser DWORD: 00000000

  - **Gruppenrichtlinie:** Computer\>administrative Vorlagen\>Windows Components\> Internet Explorer: Proxy Einstellungen pro Computer vornehmen (statt pro Benutzer)

- Qualifizierte PBX/trunk oder qualifizierte SBC/Gateways (mindestens zwei Gateways werden empfohlen).

    Cloud Connector unterstützt dieselben Session Border Controller (SBCS), die für Skype for Business zertifiziert sind. Weitere Informationen finden Sie unter [Telefonie-Infrastruktur für Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Ein lokales Server Administratorkonto mit Berechtigungen zum Installieren und Konfigurieren von Hyper-V auf den Hostservern. Das Konto muss über Administratorberechtigungen auf dem lokalen Server verfügen, auf dem Hyper-V installiert und konfiguriert ist.

- Während der Bereitstellung werden Sie aufgefordert, ein Domänenadministratorkonto mit Berechtigungen zum Erstellen und Veröffentlichen der Topologie in der Cloud Connector-Domäne zu erstellen.

- Die externen DNS-Einträge, die in der "cloudconnector. ini-Datei definiert sind, die im Installationspaket enthalten sind:

  - Externer DNS-Eintrag für Zugriffs-Edgedienst der Edge-Komponente; Beispiel: AP.\<Domain Name.\> Sie benötigen einen Eintrag pro PSTN-Standort. Dieser Datensatz muss IP-Adressen aller Ränder für diese Website enthalten.

- Ein Office 365-Mandant, für den alle erforderlichen DNS-und SRV-Einträge erstellt wurden.

    > [!IMPORTANT]
    > Wenn Sie Ihren Mandanten in Cloud Connector Edition integrieren, wird die Verwendung des Standarddomänen Suffixes. onmicrosoft.com als SIP-Domäne für Ihre Organisation nicht unterstützt. > Sie SIP nicht verwenden können. \<Domänenname\> als Name Ihrer Cloud Connector-Edge-Zugriffs-Proxyschnittstelle, da dieser DNS-Eintrag von Office 365 verwendet wird.

- Ein Zertifikat für den externen Edgeserver, das von einer öffentlichen Zertifizierungsstelle (Certification Authority, ca) erhalten wurde.

- Firewallregeln, um den Datenverkehr über die erforderlichen Ports zuzulassen, wurden abgeschlossen.

- Eine Internet Verbindung für den Hostcomputer und die VMs. Cloud Connector lädt einige Software aus dem Internet herunter. Daher müssen Sie Gateway-und DNS-Server Informationen bereitstellen, damit der Cloud Connector-Hostcomputer und die VMs eine Verbindung mit dem Internet herstellen und die erforderliche Software herunterladen können.

- Ein auf dem Hostcomputer installiertes Remote-PowerShell-Modul für Mandanten.

- Die Office 365 Skype for Business Administratoranmeldeinformationen zum Ausführen von Remote-PowerShell.

    > [!IMPORTANT]
    > Für das Administratorkonto darf keine mehrstufige Authentifizierung aktiviert sein.

> [!NOTE]
> Die Cloud Connector-Bereitstellung wird nur auf der virtualisierten Microsoft Hyper-V-Plattform unterstützt. Andere Plattformen wie VMware und Amazon Webdienste werden nicht unterstützt.

> [!NOTE]
> Die minimale Hardware Anleitung zum Ausführen von Cloud Connector basiert auf der grundlegenden Hardwarekapazität (Kerne, MHz, Gigabytes usw.) mit einem Puffer für immaterielle Leistungseinbußen, die in der Architektur eines beliebigen Computers vergraben sind. Microsoft hat Tests für den schwersten Fall auf kommerziell verfügbare Hardware durchgeführt, die die Mindestanweisungen erfüllen. Die Medienqualität und die Systemleistung werden überprüft. Offizielle Cloud Connector Appliance-Partner von Microsoft verfügen über spezielle Cloud Connector-Hardwareimplementierungen, bei denen Sie unabhängig getestete Leistung aufweisen und die Eignung ihrer Hardware zur Erfüllung von Last-und Qualitätsanforderungen bereitstellen.

> [!NOTE]
> Von AudioCodes und Sonus erstellte Geräte haben geänderten Code und werden auf Windows Server Standard Edition von Servern ausgeführt. Diese Geräte werden unterstützt.

## <a name="information-you-need-to-gather-before-deployment"></a>Informationen, die Sie vor der Bereitstellung erfassen müssen
<a name="BKMK_PlanDeployment"> </a>

Bevor Sie mit der Bereitstellung beginnen, müssen Sie die Größe der Bereitstellung, die SIP-Domänen, die gewartet werden, und die Konfigurationsinformationen für jeden PSTN-Standort bestimmen, den Sie bereitstellen möchten. Zunächst müssen Sie Folgendes tun:

- Ermitteln Sie anhand der in Ihrem Unternehmen verwendeten SIP-URIs alle SIP-Domänen, die von dieser Bereitstellung bedient werden.

- Ermitteln Sie die Anzahl der PSTN-Standorte, die Sie bereitstellen müssen.

- Stellen Sie sicher, dass Sie über die erforderliche Hardware zur Unterstützung der vier VMS verfügen, die Sie für jede Cloud Connector-Edition installieren.

Für jeden PSTN-Standort, den Sie bereitstellen möchten, müssen Sie Folgendes tun:

- Erstellen Sie Namen für alle Komponenten in jeder Cloud Connector-Appliance (siehe [bestimmen der Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definieren Sie Portbereiche (siehe [Ports und Protokolle](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).

- Erstellen externer DNS-Einträge für die Edge-Komponente (siehe [Voraussetzungen für die Bereitstellung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Bestimmen Sie die Zertifikatanforderungen für die Edge-Komponente (siehe [Zertifikatanforderungen](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Ports und Protokolle
<a name="BKMB_Ports"> </a>

Beachten Sie beim Definieren von Medien Portbereichen Folgendes:

- Clients verwenden immer Portbereich 50000 bis 50019 für den Mediendatenverkehr – dieser Bereich ist in Skype for Business Online vordefiniert und kann nicht geändert werden.

- Die vermittlungskomponente verwendet standardmäßig den Portbereich 49 152 bis 57 500 für den Mediendatenverkehr. Die Verbindung wird jedoch über die interne Firewall hergestellt, und Sie können aus Sicherheitsgründen diesen Portbereich in Ihrer Topologie einschränken. Sie benötigen bis zu vier Ports pro Anruf. Wenn Sie die Anzahl der Ports zwischen der vermittlungskomponente und dem PSTN-Gateway begrenzen möchten, müssen Sie auch den entsprechenden Portbereich auf dem Gateway konfigurieren.

- Sie müssen Cloud Connector in einem Umkreisnetzwerk bereitstellen. Dies bedeutet, dass Sie über zwei Firewalls verfügen:

  - Die erste Firewall ist extern zwischen dem Internet und Ihrem Umkreisnetzwerk.

  - Die zweite Firewall ist intern zwischen dem Umkreisnetzwerk und Ihrem internen Netzwerk.

    Ihre Clients können sich im Internet oder im internen Netzwerk befinden:

  - Clients im Internet verbinden sich über die externe Firewall über die Edge-Komponente mit Ihrem Festnetz.

  - Clients im internen Netzwerk stellen über die interne Firewall eine Verbindung mit der vermittlungskomponente im Umkreisnetzwerk her, die den Datenverkehr mit dem SBC oder dem PSTN-Gateway verbinden wird.

    Dies bedeutet, dass Sie Ports in beiden Firewalls öffnen müssen.

In den folgenden Tabellen werden die Ports und Portbereiche für die externen und internen Firewalls beschrieben.

In dieser Tabelle sind die Ports und Portbereiche für die Aktivierung der Kommunikation zwischen Clients im internen Netzwerk und der vermittlungskomponente aufgeführt:

**Interne Firewall**



|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Cloud Connector-vermittlungskomponente  <br/> |SBC/PSTN-Gateway  <br/> |Any  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN-Gateway  <br/> |Cloud Connector-vermittlungskomponente  <br/> |Any  <br/> |TCP-5068/TLS 5067  <br/> |
|Cloud Connector-vermittlungskomponente  <br/> |SBC/PSTN-Gateway  <br/> |UDP 49 152-57 500  <br/> |Alle\*\*\*  <br/> |
|SBC/PSTN-Gateway  <br/> |Cloud Connector-vermittlungskomponente  <br/> |Alle\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Cloud Connector-vermittlungskomponente  <br/> |Interne Clients  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50000-50019  <br/> Optional  <br/> |
|Cloud Connector-vermittlungskomponente  <br/> |Interne Clients  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50000-50019  <br/> |
|Interne Clients  <br/> |Cloud Connector-vermittlungskomponente  <br/> |TCP 50000-50019  <br/> |TCP 49 152-57 500\*  <br/> |
|Interne Clients  <br/> |Cloud Connector-vermittlungskomponente  <br/> |UDP 50000-50019  <br/> |UDP 49 152-57 500\*  <br/> |

\*Dies ist der standardmäßige Portbereich in der vermittlungskomponente. Für einen optimalen Anruffluss sind vier Ports pro Anruf erforderlich.

\*\*Dieser Port muss auf dem SBC/PSTN-Gateway konfiguriert werden; 5060 ist ein Beispiel. Sie können andere Ports auf Ihrem SBC/PSTN-Gateway konfigurieren.

\*\*\*Beachten Sie, dass Sie auch den Portbereich Ihres SBC/Gateways begrenzen können, wenn dies vom SBC/Gateway-Hersteller zugelassen wird.

Aus Sicherheitsgründen können Sie den Portbereich für die vermittlungskomponente mithilfe des Cmdlets " [csmediationserver begrenzen](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) " einschränken.

Mit dem folgenden Befehl wird beispielsweise die Anzahl der Ports, die von der vermittlungskomponente für den Mediendatenverkehr verwendet werden, auf 50 000-51 000 für Audio (in und Out) eingeschränkt. Die vermittlungskomponente kann 250 gleichzeitige Anrufe mit dieser Konfiguration verarbeiten. Beachten Sie, dass Sie diesen Bereich möglicherweise auch auf dem SBC/PSTN-Gateway einschränken möchten:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Um den Namen der vermittlungskomponente abzurufen und die Standardanschlüsse anzuzeigen, können Sie das Cmdlet [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) wie folgt verwenden:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

In der folgenden Tabelle sind Ports und Portbereiche für die Aktivierung der Kommunikation zwischen der Cloud Connector-Edge-Komponente und der externen Firewall aufgeführt. Diese Tabelle enthält eine minimale Empfehlung.

In diesem Fall fließt der gesamte Mediendatenverkehr über den Online-edgecode wie folgt: Benutzer Endpunkt--\>Online Edge--\>Cloud Connector Edge:

**Externe Firewall – minimale Konfiguration**



|**Quell-IP**|**Ziel-IP**|**Quell Port**|**Ziel-Port**|
|:-----|:-----|:-----|:-----|
|Any  <br/> |Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |Any  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |Any  <br/> |TCP 80  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |Any  <br/> |UDP 53  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |Any  <br/> |TCP 53  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Any  <br/> |Externe Schnittstelle für Cloud Connector-Edge  <br/> |TCP 50000-59.999  <br/> |TCP 443  <br/> |
|Any  <br/> |Externe Schnittstelle für Cloud Connector-Edge  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |TCP 50000-59.999  <br/> |TCP 443  <br/> |

In der folgenden Tabelle sind Ports und Portbereiche für die Aktivierung der Kommunikation zwischen der Cloud Connector-Edge-Komponente und der externen Firewall aufgeführt. Diese Tabelle zeigt die empfohlene Lösung.

In diesem Fall kann der gesamte Mediendatenverkehr für den Endpunkt im Internet direkt an die Cloud Connector-Edge-Komponente fließen. Der Medienpfad ist der Endpunkt des Endpunkts des Benutzers:\> Cloud Connector Edge.

> [!NOTE]
> Diese Lösung funktioniert nicht, wenn sich der Endpunkt des Benutzers hinter einer symmetrischen NAT befindet.

**Externe Firewall – Empfohlene Konfiguration**


|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Any  <br/> |Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |Any  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |Any  <br/> |TCP 80  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |Any  <br/> |UDP 53  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |Any  <br/> |TCP 53  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |TCP 50000-59.999  <br/> |Any  <br/> |
|Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |UDP 3478; UDP 50000-59.999  <br/> |Any  <br/> |
|Any  <br/> |Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |TCP 443; TCP 50000-59.999  <br/> |
|Any  <br/> |Externe Schnittstelle für Cloud Connector-Edge  <br/> |Any  <br/> |UDP 3478; UDP 50.000-59.999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Host Internet Connectivity-Anforderungen
<a name="BKMB_Ports"> </a>

Der Hostcomputer muss in der Lage sein, externe Ressourcen zu erreichen, um Cloud Connector erfolgreich zu installieren, zu aktualisieren und zu verwalten. In der folgenden Tabelle sind die Ziele und Ports aufgeführt, die zwischen dem Hostcomputer und externen Ressourcen benötigt werden.

|Direction  <br/> |Quell-IP  <br/> |Ziel-IP  <br/> |Quellport  <br/> |Zielport  <br/> |Protokoll  <br/> |Zweck  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ausgehend  <br/> |Cloud Connector-Host-IPS  <br/> |Beliebiger Wert  <br/> |Beliebiger Wert  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Ausgehend  <br/> |Cloud Connector-Host-IPS  <br/> |Beliebiger Wert  <br/> |Beliebiger Wert  <br/> |80, 443  <br/> |TCP  <br/> |Zertifikatsperrliste (Certificate Revocation List, CRL)  <br/> |
|Ausgehend  <br/> |Cloud connectorer-Host-IPS  <br/> |Beliebiger Wert  <br/> |Beliebiger Wert  <br/> |80, 443  <br/> |TCP  <br/> |Cloud Connector-Update  <br/> Skype for Business Online  <br/> Administrator-PowerShell  <br/> Windows Update  <br/> |

Wenn restriktivere Regeln erforderlich sind, lesen Sie die folgenden URL-Listen:

- [URLs für Zertifikatsperrlisten](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) in [Office 365-URLs und IP-Adressbereichen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [Konfigurieren einer Firewall für Software Updates](https://technet.microsoft.com/library/bb693717.aspx)

- Skype for Business Online Administrator PowerShell: \*. online.lync.com

    Wenn Sie einen Proxy Ausschluss für dieses Ziel benötigen, müssen Sie ihn der WinHTTP-Umgehungsliste hinzufügen.

- Cloud Connector-Update: [Download Center](https://aka.ms/CloudConnectorInstaller), [https://go.microsoft.com](https://go.microsoft.com)und[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>DNS-Namensauflösung für die Edge-Komponente
<a name="BKMB_Ports"> </a>

Die Edge-Komponente muss die externen Namen von Office 365 Diensten und die internen Namen anderer Cloud Connector-Komponenten auflösen.

Jede Edge-Komponente ist ein mehrfach vernetzter Computer mit externen und internen Schnittstellen. Cloud Connector stellt DNS-Server auf der Domänen Controller Komponente innerhalb des Umkreisnetzwerks bereit. Sie können Edgeserver auf den DNS-Server innerhalb des Perimeters für alle Namensauflösungen hinweisen, aber Sie müssen den Cloud Connector-DNS-Server aktivieren, um externe Namen aufzulösen, indem Sie eine DNS-Zone mit mindestens einem DNS-a-Eintrag für externe Abfragen festlegen, die den Namen referieren. Lookups auf andere öffentliche DNS-Server.

Wenn Sie in der INI-Datei den FQDN-Namen für Gateways aus demselben Domänen Raum wie Ihre SIP-Domäne festlegen, wird die autorisierende Zone für diese SIP-Domäne auf dem DNS-Server innerhalb des Perimeters erstellt. Wenn Edgeserver auf diesen DNS-Server verwiesen wird, um Namen aufzulösen, löst Edge das _sipfederationtls nie auf. \<yourdomain\> -DNS-Eintrag, der für den Anruffluss erforderlich ist. In diesem Fall empfiehlt Microsoft, dass Sie einen DNS-Server auf der externen Edge-Schnittstelle zum Auflösen von Internet Namen suchen bereitstellen, und jede Edge-Komponente muss eine Hostdatei zum Auflösen anderer Cloud Connector-Komponentennamen in IP-Adressen verwenden.

> [!NOTE]
> Aus Sicherheitsgründen wird empfohlen, dass Sie den Cloud Connector-DNS-Server nicht auf interne Server in der Produktionsdomäne für die Namensauflösung richten.

### <a name="determine-deployment-parameters"></a>Bestimmen der Bereitstellungsparameter
<a name="BKMK_SiteParams"> </a>

Zunächst müssen Sie die folgenden allgemeinen Bereitstellungsparameter definieren:


|**Element**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|SIP-Domänen  <br/> |SIP-URI wird von Unternehmensbenutzern verwendet. Stellen Sie alle SIP-Domänen bereit, die von dieser Bereitstellung bedient werden. Sie können mehr als eine SIP-Domäne haben.  <br/> ||
|Anzahl der PSTN-Standorte  <br/> |Die Anzahl der PSTN-Standorte, die Sie bereitstellen werden.  <br/> ||

Für jeden PSTN-Standort, den Sie bereitstellen möchten, müssen Sie die folgenden Informationen sammeln, bevor Sie mit der Bereitstellung beginnen. Sie müssen diese Informationen bereitstellen, wenn Sie die Datei "cloudconnector. ini aktualisieren.

Beachten Sie beim Konfigurieren von Gateway-Informationen Folgendes:

- Wenn Sie nur ein Gateway haben, entfernen Sie den Abschnitt in der INI-Datei für das zweite Gateway. Wenn mehr als zwei Gateways vorhanden sind, führen Sie das vorhandene Format aus, um neue hinzuzufügen.

- Stellen Sie sicher, dass die IP-Adresse und der Port des Gateways (s) korrekt sind.

- Um die PSTN-Gatewayebene zu unterstützen, halten Sie das sekundäre Gateway oder fügen Sie zusätzliche Gateways hinzu.

Optional Um die ausgehenden Anrufnummern einzuschränken, aktualisieren Sie den LocalRoute-Wert.



|**Website Parameter**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|Domänenname der virtuellen Maschine  <br/> |Domänenname für die internen Komponenten von Cloud Connector. Diese Domäne muss sich von der Produktionsdomäne unterscheiden. Der Name muss für alle Cloud Connector-Appliances gleich sein.  <br/> Name in der INI-Datei: "VirtualMachineDomain"  <br/> |. local-Domäne wird bevorzugt.  <br/> |
|Name des Cloud Connector-Domänencontrollers  <br/> |Name des Domänencontrollers.  <br/> Name in der INI-Datei: "Servername"  <br/> |Darf mindestens 15 Zeichen lang sein. Geben Sie nur NetBIOS-Namen ein.  <br/> |
|Cloud Connector-Domänencontroller-IP/Subnetzmaske  <br/> |IP-Adresse des Domänencontrollers.  <br/> Name in der INI-Datei: "IP"  <br/> ||
|FQDNs des O365-Online Diensts  <br/> |In den meisten Fällen muss es sich um die Standardeinstellung für die weltweite O365-Instanz handeln.  <br/> Name in der INI-Datei: "OnlineSipFederationFqdn"  <br/> ||
|Sitename  <br/> |Skype for Business Websitename; Beispiel: Seattle.  <br/> Name in der INI-Datei: "Sitename"  <br/> Für Version 1.4.1 und höher muss der Standortname für jeden Standort unterschiedlich sein, und der Name muss mit dem in Office 365 definierten PSTN-Standort übereinstimmen. Beachten Sie, dass PSTN-Standorte automatisch beim Registrieren der ersten Appliance an einem Standort erstellt werden.  <br/> ||
|Hardware Type  <br/> Version 1.4.1 und höher  <br/> |Typ der Hardware. Der Standardwert ist "Normal". Sie können auch auf "Minimum" festlegen.  <br/> ||
|Country Code  <br/> |Landesvorwahl für das wählen.  <br/> Name in der INI-Datei: "CountryCode"  <br/> ||
|Stadt  <br/> |Stadt (optional).  <br/> Name in der INI-Datei: "City"  <br/> ||
|Status  <br/> |Status (optional).  <br/> Name in der INI-Datei: "Status"  <br/> ||
|Basis-VM-IP-Adresse  <br/> |Die IP-Adresse der temporären Basis-VM, die zum Erstellen der VHDX für alle virtuellen Computer in Cloud Connector verwendet wird. Diese IP-Adresse muss sich im selben Subnetz des Umkreis Unternehmensnetzwerks befinden, das im nächsten Schritt definiert ist, und erfordert Internet Zugriff. Stellen Sie sicher, dass Sie das Standardgateway für Unternehmen und den DNS definieren, der mit dem Internet geroutet werden kann.  <br/> Name in der INI-Datei: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 und höher  <br/> |Die Adresse von Windows Server Update Services (WSUS) – einem Intranetserver, auf dem Updates von Microsoft Update gehostet werden.  <br/> Sie können leer lassen, wenn WSUS nicht benötigt wird.  <br/> ||
|Subnetzmaske für internes Netzwerk  <br/> |Cloud Connector konfiguriert ein IP-Netzwerk für die interne Kommunikation zwischen Cloud Connector-Komponenten. Edge muss außerdem mit einem anderen Subnetz verbunden sein, das Internet Verbindungen zulässt.  <br/> Name in der INI-Datei: "CorpnetIPPrefixLength" unter "Parameter für einen Pool von VM-Netzwerk"  <br/> ||
|Subnetzmaske für externes Netzwerk  <br/> |Für das externe Netzwerk der Edge-Komponente.  <br/> Name in der INI-Datei: "InternetIPPrefix" unter "Parameter für einen Pool von VM-Netzwerk"  <br/> ||
|Switch-Name für internes Netzwerk  <br/> |Name für Switch, der für das interne Cloud Connector-Netzwerk verwendet wird.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in der INI-Datei: "CorpnetSwitchName" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Switch-Name für externes Netzwerk  <br/> |Name für Switch, der für das externe Cloud Connector-Netzwerk verwendet wird.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in der INI-Datei: "InternetSwitchName" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Standard Gateway für internes Netzwerk  <br/> |Dieses Gateway muss Zugriff auf das Internet bieten (Internet erfordert auch das Festlegen des DNS-Servers) und wird für interne Schnittstellen von Cloud Connector-Komponenten konfiguriert.  <br/> Name in der INI-Datei: "CorpnetDefaultGateway" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Standard Gateway für externe Schnittstelle der Edge-Komponente  <br/> |Wird auf der externen Schnittstelle der Edge-Komponente konfiguriert.  <br/> Name in der INI-Datei: "InternetDefaultGateway" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|DNS-Server für internes Netzwerk  <br/> |Wird auf der internen Schnittstelle der temporären VM konfiguriert. Es muss eine Namensauflösung für Internet Namen bereitgestellt werden. Ohne einen DNS-Server bereitzustellen, schlägt die Internet Verbindung fehl, und die Bereitstellung wird nicht abgeschlossen.  <br/> Name in der INI-Datei: "CorpnetDNSIPAddress" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|DNS-Server für externe Schnittstelle der Edge-Komponente  <br/> |Wird auf der externen Schnittstelle von Edge konfiguriert.  <br/> Name in der INI-Datei: "InternetDNSIPAddress" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Verwaltungs Switch-Name  <br/> |Der Verwaltungs Switch ist ein temporärer Switch, der automatisch erstellt wird und für die Konfiguration von Cloud Connector während der Bereitstellung verwendet wird. Die Verbindung wird nach der Bereitstellung automatisch getrennt. Es muss sich um ein anderes Subnetz als alle anderen Netzwerke handeln, die in Cloud Connector verwendet werden.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in der INI-Datei: "ManagementSwitchName" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Verwaltungs-Subnetz-Adresse/Subnetzmaske  <br/> |Das Verwaltungs-Subnetz ist ein temporäres Subnetz, das automatisch erstellt wird und für die Konfiguration von Cloud Connector während der Bereitstellung verwendet wird. Sie wird nach der Bereitstellung automatisch entfernt. Es muss sich um ein anderes Subnetz als alle anderen Netzwerke handeln, die in Cloud Connector verwendet werden.  <br/> Namen in der INI-Datei: "ManagementIPPrefix" und "ManagementIPPrefixLength" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Zentraler Verwaltungsspeicher-Computer (CMS)  <br/> |Ein einzelner FQDN, der für zentraler Verwaltungsspeicher (CMS) verwendet wird. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in der INI-Datei: "Servername" unter "Parameters for Primary Central Management Service  <br/> |Darf mindestens 15 Zeichen lang sein. Geben Sie nur NetBIOS-Namen ein.  <br/> (CMS Pool Name = Server Name)  <br/> |
|IP-Adresse des CMS-Computers  <br/> |IP-Adresse für den CMS-Server (intern im Umkreisnetzwerk).  <br/> Name in der INI-Datei: "IP" unter "Parameters for Primary Central Management Service  <br/> ||
|Dateifreigabe Name  <br/> |Dateifreigabe Name, der auf dem CMS-Server für Skype for Business Replikationsdaten erstellt werden soll (beispielsweise CmsFileStore).  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in der INI-Datei: "CmsFileStore" unter "Parameters for Primary Central Management Service  <br/> ||
|Name des Vermittlungs Komponenten Pools  <br/> |Poolname der vermittlungskomponente. Geben Sie nur NetBIOS-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in der INI-Datei: "Poolname" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> |Darf mindestens 15 Zeichen lang sein. Geben Sie nur NetBIOS-Namen ein.  <br/> |
|Name der vermittlungskomponente  <br/> |Komponenten Name der vermittlungskomponente 1. Geben Sie nur NetBIOS-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in der INI-Datei: "Servername" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> |Darf mindestens 15 Zeichen lang sein. Geben Sie nur NetBIOS-Namen ein.  <br/> |
|IP-Adresse des Vermittlungs Komponenten Computers  <br/> |Interne Corpnet-IP für die vermittlungskomponente (intern im Umkreisnetzwerk).  <br/> Name in der INI-Datei: "IP" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> ||
|Edgepool interner Name  <br/> |Der Name des Pools der Edge-Komponente. Geben Sie nur NetBIOS-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in der INI-Datei: "InternalPoolName" unter "Parameter for a Pool of Edge Servers"  <br/> |Darf mindestens 15 Zeichen lang sein. Geben Sie nur NetBIOS-Namen ein.  <br/> |
|Edgeserver interner Name  <br/> |Komponenten Name der Edge-Komponente. Geben Sie nur NetBIOS-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in der INI-Datei: "InternalServerName" unter "Parameter for a Pool of Edge Servers"  <br/> |Darf mindestens 15 Zeichen lang sein. Geben Sie nur NetBIOS-Namen ein.  <br/> |
|Interne IP-Adresse des Edge-Servers  <br/> |Interne Umkreisnetzwerk-IP der Edge-Komponente zur Kommunikation mit anderen Komponenten von Cloud Connector.  <br/> Name in der INI-Datei: "InternalServerIPs" unter "Parameter for a Pool of Edge Servers"  <br/> ||
|Externer Name des Access-Pools  <br/> |Name der Zugriffs Kante; Beispiel: AP. Dieser Name muss mit dem für das SSL-Zertifikat bereitgestellten Namen übereinstimmen. Geben Sie nur NetBIOS-Namen ein. Der SIP-Domänenname wird verwendet, um den FQDN zu generieren. Für alle Edge-Komponenten im Pool wird ein externer Pool-Name verwendet. Pro PSTN-Standort ist ein Edge-Zugriffs Pool erforderlich.  <br/> Name in der INI-Datei: "ExternalSIPPoolName" unter "Parameter for a Pool of Edge Servers"  <br/> |Darf mindestens 15 Zeichen lang sein. Geben Sie nur NetBIOS-Namen ein.  <br/> "SIP" ist reserviert und kann daher nicht als Name verwendet werden.  <br/> Der generierte FQDN-Name muss mit dem für das SSL-Zertifikat bereitgestellten Namen übereinstimmen.  <br/> |
|Externe IP-Zugriffs Kante  <br/> |Externe IP-Adresse der Edge-Komponente-entweder öffentliche IP-Adresse, wenn keine NAT verfügbar ist, oder übersetzte IP (geben Sie bei der Zuordnung beide Adressen an).  <br/> Name in der INI-Datei: "ExternalSIPIPs" unter "Parameter for a Pool of Edge Servers"  <br/> ||
|Name des Medien Relays  <br/> |Name der Audiovideo-Medien Relay-Kante; Beispielsweise wird Mr. Für alle Edge-Komponenten in einem Pool wird ein externer Pool-Name verwendet. Pro PSTN-Standort ist ein Edge-Medien Relay-Pool erforderlich.  <br/> Name in der INI-Datei: "ExternalMRFQDNPoolName" unter "Parameter for a Pool of Edge Servers"  <br/> |Darf mindestens 15 Zeichen lang sein. Geben Sie nur NetBIOS-Namen ein.  <br/> |
|Externe IP-Adresse des Medien Relay-Edges  <br/> |Derzeit wird nur eine IP-Adresse unterstützt, sodass dies dieselbe IP-Adresse wie der Zugriffs Rand ist, entweder öffentliche oder zugeordnete IP (geben Sie beide Adressen an, falls diese zugeordnet sind). Kann dieselbe Adresse wie die externe IP-Adresse der Edge-Komponente der Zugriffs Kante sein. Hinweis Wenn Edge hinter NAT liegt, müssen Sie auch den Wert für den Next-Parameter angeben.  <br/> Name in der INI-Datei: "" externalmrips "" unter "Parameter for a Pool of Edge Servers"  <br/> ||
|Externe IP-Adresse des Medien Relay-Edges (Wenn Edge hinter NAT liegt)  <br/> |Wenn Ihr Edge hinter NAT liegt, müssen Sie auch die öffentliche Adresse des NAT-Geräts angeben.  <br/> Name in der INI-Datei: "ExternalMRPublicIPs" unter "Parameter for a Pool of Edge Servers"  <br/> ||
|Marke und Modell für VoIP-Gateway 1  <br/> |Geben Sie die Marke und das Modell des SBC/Voice-Gateways an. Beachten Sie, dass Sie ein Gerät oder einen SIP-Trunk von der Liste der getesteten Geräte unter [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)verbinden können.  <br/> ||
|Marke und Modell von VoIP-Gateway 2 (Kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |Geben Sie die Marke und das Modell für das VoIP-Gateway an. Beachten Sie, dass Sie ein Gerät aus der Liste der getesteten Geräte [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)unter verbinden können.  <br/> ||
|Name des VoIP-Gateways 1  <br/> |Wird verwendet, um den Computer-FQDN mit der AD-Domäne zu generieren. Erforderlich, wenn TLS zwischen der vermittlungskomponente und dem VoIP-Gateway verwendet wird. Wenn Sie nicht die Verwendung von FQDN planen, beispielsweise ist TLS nicht erforderlich, oder Voice Gateway unterstützt keine Verbindung über FQDN (nur IP) – geben Sie bitte an.  <br/> ||
|Name des VoIP-Gateways 2 (Kopieren Sie diese Zeile, wenn Sie mehr als zwei Gateways haben)  <br/> |Wird verwendet, um den Computer-FQDN mit der AD-Domäne zu generieren. Erforderlich, wenn TLS zwischen der vermittlungskomponente und dem VoIP-Gateway verwendet wird. Wenn Sie nicht die Verwendung von FQDN planen, beispielsweise ist TLS nicht erforderlich, oder Voice Gateway unterstützt keine Verbindung über FQDN (nur IP) – geben Sie bitte an.  <br/> ||
|IP-Adresse des VoIP-Gateways 1  <br/> |IP-Adresse des VoIP-Gateways.  <br/> ||
|IP-Adresse des VoIP-Gateways 2 (Kopieren Sie diese Zeile, wenn Sie mehr als 2 Gateways haben)  <br/> |IP-Adresse des VoIP-Gateways.  <br/> ||
|Voice Gateway 1 Port # (Kopieren Sie diese Zeile, wenn Sie mehr als 2 Gateways haben)  <br/> |Port, auf dem der SIP-Trunk des Voice-Gateways lauscht, beispielsweise 5060.  <br/> ||
|VoIP-Gateway 2-Port #  <br/> |Port, auf dem der SIP-Trunk des Voice-Gateways lauscht, beispielsweise 5060.  <br/> ||
|VoIP-Gateway-1-Protokoll für SIP-Datenverkehr  <br/> |TCP oder TLS.  <br/> ||
|Voice Gateway 2-Protokoll für SIP-Datenverkehr (Kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |TCP oder TLS.  <br/> ||
|Externer Medienportbereich für Datenverkehr an und von der Edge-Komponente  <br/> |TCP/UDP-Portbereich für den Mediendatenverkehr an und von der externen Edge-Schnittstelle. Muss immer von 50 000 beginnen. Weitere Informationen erhalten Sie unter "Ports and Protocols".  <br/> |50000-59 999  <br/> |
|Medienportbereich für die Kommunikation mit der vermittlungskomponente über die interne Firewall  <br/> |UDP-Portbereich, den die vermittlungskomponente zur Kommunikation mit Clients und Gateways verwendet (Empfehlung 4 Ports pro Anruf).  <br/> ||
|Medienportbereich für die Kommunikation mit/von Skype for Business Client über die interne Firewall  <br/> |Zu Planungszwecken kann nicht geändert werden. Ports müssen in der internen Firewall geöffnet werden, um zwischen Skype for Business Clients innerhalb des internen Netzwerks und mit der vermittlungskomponente zu kommunizieren.  <br/> |50 000-50 019  <br/> |
|Öffentliches Zertifikat Kennwort  <br/> |Muss im Skript angegeben werden.  <br/> ||
|Administrator Kennwort für den sicheren Modus  <br/> Nur Version 1.4.2  <br/> |Administratorkennwort für den sicheren Modus für die interne CC-Domäne.  <br/> ||
|Cloud Connector-Domänen Administrator Kennwort  <br/> Nur Version 1.4.2  <br/> |Kennwort für den Cloud Connector-Domänen Administrator (unterscheidet sich von der Produktionsdomäne). Benutzername ist Administrator. Sie können den Benutzernamen nicht ändern.  <br/> ||
|Administrator Kennwort für virtuelle Computer  <br/> Nur Version 1.4.2  <br/> |Wird zum Konfigurieren des Verwaltungsnetzwerks während der Bereitstellung verwendet.  <br/> Benutzername ist Administrator. Sie können den Benutzernamen nicht ändern.  <br/> ||
|CABackupFile  <br/> Version 2,0 und höher  <br/> |Dient zum Speichern des Zertifizierungsstellendiensts vom Active Directory Server in einer Datei, wenn mehrere Appliances an einem Cloud Connector-Standort bereitgestellt werden. Stellen Sie sicher, dass Sie für alle Appliances innerhalb eines Cloud Connector-Standorts dasselbe Kennwort verwenden, um die ca-Sicherungsdatei erfolgreich in die neue hinzugefügte Appliance zu importieren.  <br/> ||
|"Cceservice"  <br/> Version 2,0 und höher  <br/> |Wird für den Cloud Connector-Verwaltungsdienst verwendet. benötigt Zugriff auf das Cloud Connector-Websiteverzeichnis. Stellen Sie sicher, dass Sie für alle Appliances innerhalb eines Cloud Connector-Standorts dasselbe Kennwort verwenden.  <br/> ||
|Office 365 mandantenadministrator  <br/> | Das Konto wird von Cloud Connector verwendet, um Mandanten Einstellungen für Cloud Connector zu aktualisieren und zu verwalten: <br/>  Version 2,0 und höher: Anmeldeinformationen für ein dediziertes Office 365 Konto mit Skype for Business Administrator Rechten. <br/>  Frühere Versionen von 2,0: Anmeldeinformationen für ein dediziertes Office 365 Konto mit globalen Mandanten Administrator Rechten. <br/> ||
|Aktivieren der Refer-Unterstützung  <br/> |Dadurch wird festgelegt, ob die SIP-Refer-Unterstützung für die trunk Konfiguration für Ihre IP/Nebenstellenanlage aktiviert oder deaktiviert ist. Der Standardwert lautet "True". Wenn Ihr IP/PBX-Gateway den Refer-Support unterstützt, lassen Sie dies bitte als "true". Wenn dies nicht der Fall ist, muss dieser Wert in false geändert werden. Wenn Sie nicht sicher sind, ob Ihr Gateway Refer unterstützt, finden Sie weitere Informationen unter [qualifizierte IP-PBX-Anlagen und Gateways](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Version 2,0 und höher  <br/> |Wenn ausgehende Anrufe nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, werden Sie mit dem Standardwert "true" an das nächste verfügbare Gateway weitergeleitet. Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.  <br/> In einer Organisation mit langsamen Netzwerken und Gateway-Antworten oder wenn der Vorgang zum Einrichten von Anrufen mehr als 10 Sekunden dauert, kann dies potenziell dazu führen, dass Anrufe unnötig verworfen werden.  <br/> Beim Platzieren von Anrufen in einigen Ländern, beispielsweise in den VAE oder in Afghanistan, kann das Aufrufen der Erstellungsprozess mehr als 10 Sekunden dauern. Wenn ähnliche Probleme auftreten, müssen Sie den Wert in false ändern. Vergessen Sie nicht, die entsprechende Einstellung auf dem verbundenen SBC oder Gateway zu ändern.  <br/> Der Wert kann true oder false sein. Der Standardwert lautet "True".  <br/> ||
|ForwardCallHistory  <br/> Version 2,0 und höher  <br/> | Dieser Parameter wird verwendet, um SIP-Kopfzeilen einzuschalten, die verwendet werden, um den ursprünglichen Anrufer bei gleichzeitigen Klingeln, Anrufweiterleitungen und Anruf Übertragungs Szenarien zu melden. Wenn Sie den Parameter auf true festlegen, werden zwei SIP-Header aktiviert: <br/>  Historie-Info <br/>  Weitergeleitet <br/>  Der History-Info-Header wird für die erneute Ausrichtung auf SIP-Anforderungen und "Bereitstellen eines Standardmechanismus zum Erfassen der Anforderungs Verlaufsinformationen zum Aktivieren einer Vielzahl von Diensten für Netzwerke und Endbenutzer" ([RFC 4244-section 1,1](http://www.ietf.org/rfc/rfc4244.txt)) verwendet. Für die Cloud Connector trunk-Schnittstellen wird dies in gleich-und Anruf Weiterleitungs Szenarien verwendet.  <br/>  Der Wert kann true oder false sein. Der Standardwert ist False. <br/> ||
|Vorwärts Pai  <br/> Version 2,0 und höher  <br/> |Pai ist eine private Durchwahl zu SIP, die es SIP-Servern ermöglicht, die Identität authentifizierter Benutzer zu bestätigen. Für den SIP-Trunk Anbieter kann Pai für Rechnung-zu-Zwecke verwendet werden, falls keine Verlaufsinformationen und keine verwiesenen Kopfzeilen vorhanden sind. Wenn die Weiterleitung P-Asserted-Identity in der Konfiguration aktiviert ist, leitet der Vermittlungsserver Pai-Header &amp; mit SIP Tel URI von Cloud Connector an den SIP-Trunk weiter. Die Vermittlungsserver leitet Pai-Header mit E. 164 &amp; -Nummern des Tel URI weiter, die nur auf dem SIP-Trunk an Cloud Connector empfangen werden. Die Vermittlungsserver leitet auch alle Datenschutz Kopfzeilen, die in beide Richtungen empfangen werden. Wenn die vom Vermittlungsserver gesendete SIP-Anforderung eine Datenschutz Kopfzeile des Formulars-"Privacy: ID" in Verbindung mit dem Pai-Header enthält, sollte die asserted Identity außerhalb der Netzwerk Vertrauensstellungs Domäne privat aufbewahrt werden.  <br/> Der Wert kann true oder false sein. Der Standardwert ist False.  <br/> ||

### <a name="certificate-requirements"></a>Anforderungen für Zertifikate
<a name="BKMK_Certs"> </a>

Für jede Edge-Komponente ist ein Zertifikat von einer öffentlichen Zertifizierungsstelle erforderlich. Zertifikate müssen über einen exportierbaren privaten Schlüssel verfügen, der zwischen den Edge-Komponenten kopiert werden muss. Um die Zertifikatanforderungen zu erfüllen, müssen Sie sich zwischen den folgenden Optionen entscheiden und den Antragstellernamen (SN) und den alternativen Antragstellernamen (San) für das Zertifikat angeben.

 **Wenn Sie über eine einzelne SIP-Domäne verfügen:**

- **Option 1.** Der Antragstellername muss den Namen des Pools enthalten, den Sie den Edge-Komponenten zugewiesen haben. Beachten Sie, dass der Antragstellername nicht SIP.sipdomain.com sein kann, da dieser Name für die Online Skype for Business Edge-Komponente reserviert ist. Das San muss SIP.sipdomain.com und den Namen des Zugriffs Edgepool enthalten:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Option 2.** Wenn Sie ein einzelnes Platzhalterzertifikat auf allen bereitgestellten Edgepool Servern verwenden möchten, können Sie anstelle des Edgepool namens im Zertifikat \*einen Platzhalter-San-Eintrag von. sipdomain.com verwenden. Der Antragstellername kann der Zugriff Edgepool Name eines beliebigen Edge-Pools sein, den Sie bereitgestellt haben:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Sie dürfen keinen externen DNS-Eintrag für SIP erstellen. \<sipdomain "\>. com, da dieser Name zur Office 365-Bereitstellung gehört.

> [!NOTE]
> Wenn Sie ein einzelnes Zertifikat für alle in Ihrer Organisation bereitgestellten Edge-Pools verwenden möchten und kein Platzhalterzertifikat wie in Option 2 definiert verwenden können, müssen Sie den FQDN für alle bereitgestellten Edge-Pools im San-Namen im Zertifikat einschließen.

 **Wenn Sie über mehrere SIP-Domänen verfügen:**

Sie müssen SIP.sipdomain.com für jede SIP-Domäne und den Namen der Access-Edge-Pools pro Domäne hinzufügen (es kann sich um einen physischen Pool mit unterschiedlichen Namen handeln). Unten sehen Sie ein Beispiel für SN-und San-Einträge in einem Szenario mit mehreren SIP-Domänen:

- **Option 1.** Der Antragstellername muss den Namen des Pools enthalten, den Sie für Edge-Komponenten zugewiesen haben. Beachten Sie, dass der Antragstellername nicht SIP.sipdomain.com sein kann, da dieser Name für die Online Skype for Business Edge-Komponente reserviert ist. Das San muss SIP.sipdomain.com und den Namen des Zugriffs Edgepool enthalten:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Option 2.</strong> Wenn Sie ein einzelnes Platzhalterzertifikat auf allen bereitgestellten Edgepool Servern verwenden möchten, können Sie anstelle des Edgepool namens im Zertifikat \*einen Platzhalter-San-Eintrag von. sipdomain.com verwenden. Der Antragstellername kann der Zugriff Edgepool Name eines beliebigen Edge-Pools sein, den Sie bereitgestellt haben:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Sie dürfen keinen externen DNS-Eintrag für SIP erstellen. \<sipdomain "\>. com, da dieser Name zur Office 365-Bereitstellung gehört.

Zum Zwecke der Bereitstellung können Sie die folgende Tabelle verwenden:

|**Option**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|Welche Option wird für Ihre Bereitstellung verwendet?  <br/> |Option 1 oder 2  <br/> ||
|SN  <br/> |Bereitstellen des SN für Ihr Zertifikat  <br/> ||
|San  <br/> |Bereitstellen des San für Ihr Zertifikat  <br/> ||

Wenn Sie TLS zwischen dem Gateway und dem Vermittlungsserver verwenden, müssen Sie das Stammzertifikat oder die vollständige Zertifikatkette für das Zertifikat abrufen, das dem Gateway zugewiesen ist.

## <a name="dial-plan-considerations"></a>Überlegungen zu Wähleinstellungen
<a name="BKMK_DailPlan"> </a>

Cloud Connector erfordert die Verwendung eines Online Wähl Plans. Weitere Informationen zum Konfigurieren eines Online Wähl Plans finden Sie unter [Was sind Wählpläne?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Überlegungen zur hohen Verfügbarkeit
<a name="BKMK_HA"> </a>

Wenn Sie Cloud Connector Edition für hohe Verfügbarkeit bereitstellen, stellen Sie mindestens zwei Appliances bereit, die als Sicherung für einander fungieren. Jede Appliance besteht aus vier Komponenten: Edge, Mediation, zentraler Verwaltungsspeicher (CMS) und Domänencontroller.

Wenn eine Komponente innerhalb einer Appliance ausfällt, kann Cloud Connector Edition in der Regel weiterhin Anrufe verarbeiten, Sie müssen jedoch Folgendes berücksichtigen:

- **Überlegungen zu Vermittlungs-, CMS-und Domänencontroller Komponenten**

    Es wird davon ausgegangen, dass die CMS-oder Domänencontroller Komponente in einer Appliance ausfällt. Die Appliance kann weiterhin eingehende und ausgehende Anrufe verarbeiten, aber wenn Sie eine vermittlungskomponente neu starten, wenn der Domänencontroller oder die CMS-Komponente nicht erreichbar ist, funktioniert die Vermittlung nicht. Gleiches gilt für den Neustart der CMS-Komponente, wenn der Domänencontroller nicht aktiv ist.

    **Empfehlung:** Überprüfen Sie vor dem Neustart von Komponenten die Verfügbarkeit der anderen Komponenten in der Appliance.

- **Überlegungen zur Edge-Komponente**

    Wenn die Edge-Komponente in einer Appliance nicht verfügbar ist, unterscheidet sich das Verhalten für eingehende und ausgehende Anrufe wie folgt:

  - **Ausgehende Anrufe**– ein Anruf von Ihrem Benutzer im Internet an ein PSTN-Netzwerk.

    Mit dem Anruf Verteilungsmechanismus in der Cloud wird ermittelt, dass eine Edge-Komponente nicht aktiv ist, und alle Anrufe an eine andere Appliance weitergeleitet, sodass der ausgehende Anruf erfolgreich ausgeführt werden kann.

  - Eingehender **Anruf**– ein Anruf aus dem PSTN-Netzwerk an einen Benutzer, der sich entweder in einem lokalen Netzwerk oder im Internet befindet.

     Wenn die Edge-Komponente der Appliance, die den Anruf empfangen hat, nicht funktioniert, sind eingehende Anrufe an diese Appliance nicht erfolgreich, da die vermittlungskomponente den Anruf nicht an die Edge-Komponente in der anderen Appliance weiterleiten kann.

    **Empfehlung:** Ein Überwachungssystem vorhanden ist. Nachdem Sie eine Fehlfunktion der Edge-Komponente identifiziert haben, fahren Sie alle Komponenten in der Appliance herunter, in der die Edge-Komponente nicht verfügbar ist.

## <a name="cloud-connector-media-flow"></a>Cloud Connector-Medienfluss
<a name="BKMK_MediaFlow"> </a>

Die folgenden Diagramme erläutern den Fluss eines ausgehenden und eingehenden Anrufs über Cloud Connector Edition. Dies sind nützliche Informationen, um zu verstehen, wie die Konnektivität hergestellt wird.

Im ersten Diagramm platziert ein interner Benutzer einen ausgehenden Anruf wie folgt:

1. Dave, ein Benutzer, der Online verwaltet wird, sich jetzt aber im internen Netzwerk befindet, platziert einen Anruf an einen externen PSTN-Benutzer.

2. SIP-Datenverkehrs Routen zu Skype for Business Online.

3. Skype for Business Online führt eine umgekehrte Nummernsuche für die Nummer aus. Die rückwärts Nummernsuche schlägt fehl, da diese Nummer keinem Personen in der Skype for Business Organisation gehört.

4. Der Anruf wird an die Edge-Komponente weitergeleitet (SIP-und Medienfluss über Online Edge zuerst; Medien werden über die interne Firewall zur vermittlungskomponente weiter geschaltet).

5. Wenn die Route vorhanden ist, leitet die Edge-Komponente den Datenverkehr an die vermittlungskomponente im Umkreisnetzwerk weiter.

6. Die vermittlungskomponente sendet den Datenverkehr an das PSTN-Gateway.

![Ausgehenden Medienfluss für Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Im nächsten Diagramm erhält ein interner Benutzer einen eingehenden Anruf wie folgt:

1. Das PSTN-Gateway empfängt einen Anruf für Benutzer Dave, der Online verwaltet wird, sich jetzt aber im internen Netzwerk befindet.

2. Der SIP-Datenverkehr wird an die vermittlungskomponente weitergeleitet.

3. Die vermittlungskomponente sendet SIP-Datenverkehr an die Edge-Komponente, und dann geht es zu Skype for Business Online.

4. Skype for Business Online führt eine umgekehrte Nummernsuche für die Nummer aus und stellt fest, dass es sich um den Benutzer Dave handelt.

5. SIP-Signalisierung geht an alle Daves Points of Presence.

6. Der Mediendatenverkehr wird zwischen dem Gateway und der vermittlungskomponente sowie zwischen der vermittlungskomponente und dem Endpunkt hergestellt.

![Eingehenden Medienfluss für Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Überwachung und Problembehandlung
<a name="BKMK_Monitor"> </a>

Der Mechanismus zur Überwachung und Problembehandlung wird bei jeder Cloud Connector-Appliance automatisch installiert. Der Mechanismus erkennt die folgenden Ereignisse:

- Mindestens ein virtueller Computer einer Cloud Connector-Appliance ist nicht mit einem internen oder virtuellen Switch des Internets verbunden.

- Mindestens ein virtueller Computer einer Cloud Connector-Appliance befindet sich im Status gespeichert oder beendet.

- Dienste, die nicht gestartet werden.

  Wenn eines der folgenden Ereignisse erkannt wird, wird die gesamte Cloud Connector-Appliance entleert und als offline gekennzeichnet, um zu verhindern, dass ein Fehler bei einer Appliance auftritt. Die automatische Wiederherstellungsfunktion von Cloud Connector stellt anschließend Dienste wieder her und kennzeichnet die Appliance als Online. Wenn die automatische Wiederherstellung aus irgendeinem Grund fehlschlägt, finden Sie weitere Informationen unter [Troubleshoot your Cloud Connector Deployment](troubleshoot-your-cloud-connector-deployment.md).

  - Auf dem virtuellen Computer zentraler Verwaltungsspeicher:

     - Skype for Business Master Replicator-Agent

     - Skype for Business Replikat Replikationsdienst-Agent

  - Auf dem virtuellen Computer Vermittlungsserver:

     - Skype for Business Replikat Replikationsdienst-Agent

     - Skype for Business Server Vermittlung

  - Auf dem virtuellen Computer Edgeserver

     - Skype for Business Replikat Replikationsdienst-Agent

     -  Skype for Business Server Zugriffs Kante

     - Skype for Business Server Audio/Video-Edge

     - Skype for Business Server Audio/Video-Authentifizierung

     - Skype for Business Server-Webkonferenz-Edge

- Eingehende Regel der Windows-Firewall für "CS RTCSRV" auf dem Edgeserver, "CS RTCMEDSRV" im Vermittlungsserver ist deaktiviert.

Cloud Connector 2,1 und höher unterstützt Cloud Connector für die Überwachung mithilfe von Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md) .

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_MoreInfo"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:

- [Microsoft-Telefonie-Lösungen](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Planen der medienumgehung in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Bereitstellen der medienumgehung in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)


