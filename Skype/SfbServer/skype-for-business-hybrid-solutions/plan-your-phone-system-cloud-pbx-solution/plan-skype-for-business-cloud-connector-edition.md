---
title: Planen für die Skype for Business Cloud Connector-Edition
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
description: Hier erhalten Sie Informationen zu Skype for Business Cloud Connector Edition, einem als Paket zusammengesetzten Satz von virtuellen Maschinen (VMs), die eine lokale PSTN-Anbindung mit dem Telefonsystem in Office 365 (Cloud-PBX) implementieren.
ms.openlocfilehash: 20ea88b230fe0fd9a590c489cb6f0017a2c27209
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814463"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planen für die Skype for Business Cloud Connector-Edition

Hier erhalten Sie Informationen zu Skype for Business Cloud Connector Edition, einem als Paket zusammengesetzten Satz von virtuellen Maschinen (VMs), die eine lokale PSTN-Anbindung mit dem Telefonsystem in Office 365 (Cloud-PBX) implementieren.

Cloud Connector Edition ist möglicherweise die richtige Lösung für Ihre Organisation, wenn Sie noch nicht über eine vorhandene lync Server-oder Skype for Business Server-Bereitstellung verfügen. Wenn Sie immer noch untersuchen, welches Telefon System in Office 365-Lösung für Ihr Unternehmen richtig ist, lesen Sie [Microsoft-Telefonie-Lösungen](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

Dieses Dokument beschreibt die Anforderungen und unterstützten Topologien von Cloud Connector Edition und hilft Ihnen bei der Planung Ihrer Cloud Connector Edition-Bereitstellung. Lesen Sie dieses Thema, bevor Sie Ihre Cloud Connector-Umgebung konfigurieren. Wenn Sie bereit sind, Cloud Connector Edition bereitzustellen und zu konfigurieren, lesen Sie [Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

Cloud Connector Edition 2,1 ist jetzt verfügbar. Wenn Sie noch nicht auf Version 2.1 aktualisiert haben, lesen Sie [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Sie finden die Installationsdatei unter [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).

> [!NOTE]
> Microsoft unterstützt die vorherige Version von Cloud Connector Edition für 60 Tage nach der Veröffentlichung einer neuen Version. Microsoft unterstützt Version 2.0.1 nach der Veröffentlichung von Version 2.1 60 Tage lang, damit Sie Zeit zum Aktualisieren haben. Alle Versionen vor Version 2.0.1 werden nicht mehr unterstützt.

Bei Cloud Connector Edition handelt es sich um ein Hybrid Angebot, das aus einer Reihe von virtuellen Maschinen (Virtual Machines) besteht, die lokale PSTN-Konnektivität mit dem Telefon System in Office 365 implementieren. Durch die Bereitstellung einer minimalen Skype for Business Server-Topologie in einer virtualisierten Umgebung können Benutzer in Ihrer Organisation, die in der Cloud gehostet werden, PBX-Dienste aus der Microsoft-Cloud empfangen, aber die PSTN-Konnektivität wird über die vorhandene lokale Sprachausgabe bereitgestellt. Infrastruktur.

![Topologiediagramm, in dem das Cloud PBX-Gateway und die Herstellung der Verbindung von Cloud PBX mit einer lokalen Bereitstellung von Skype for Business dargestellt wird.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Da Sie mit Cloud Connector die Möglichkeit haben, die Dienste des Telefonsystems in Office 365 in eine vorhandene Telefonieumgebung (z. B. PBX, analoge Geräte und Callcenter) zu integrieren, können Sie eine phasenweise Migration von der vorhandenen Telefonielösung zum Telefonsystem in Office 365 implementieren.

Nehmen wir zum Beispiel an, Ihre Firma hat ein anspruchsvolles Callcenter mit bestimmten Funktionen, die das Telefonsystem in Office 365 nicht bietet. Sie können für die Callcenterbenutzer weiter die vorhandene Lösung verwenden, während Sie die anderen Benutzer nach Office 365 übertragen.

Cloud Connector ermöglicht die Weiterleitung zwischen den lokal verwalteten Benutzern und den online verwalteten Benutzern, und Sie können wahlweise Ihren eigenen PSTN-Anbieter mit dem Telefonsystem in Office 365 verwenden.

Bei der Planung Ihrer Cloud Connector Edition-Bereitstellung sollten Sie Folgendes bedenken:

- Wenn Sie Cloud Connector verwenden möchten, um Cloud-VoIP-Lösungen zu nutzen, müssen Sie sich für einen Office 365-Mandanten registrieren, der das Telefon System in Office 365 umfasst. Wenn Sie noch keinen Office 365-Mandanten haben, können Sie hier erfahren, wie Sie sich hier anmelden: [Office 365 for Business](https://products.office.com/en-us/business/office). Beachten Sie, dass Sie sich für einen Plan registrieren müssen, der Skype for Business Online umfasst.

- Um Cloud Connector-Appliances mit dem Skype for Business Online-Dienst zu registrieren und verschiedene Cmdlets auszuführen, erfordert Cloud Connector 2,0 und höher ein dediziertes Office 365-Konto mit den Administrator Rechten für den Mandanten von Skype for Business. Cloud Connector-Versionen vor 2.0 erfordern ein dediziertes Office 365-Konto mit den Rechten eines globalen Mandantenadministrators.

- Für Cloud Connector ist keine vollständige lokale Skype for Business Server-Bereitstellung erforderlich.

    Derzeit kann Cloud Connector nicht mit lync-oder Skype for Business-lokalen Servern koexistieren. Wenn Sie vorhandene lync-oder Skype for Business-Benutzer in Office 365 verschieben und die lokale Telefonie weiterhin für Ihre Benutzer bereitstellen möchten, sollten Sie das Telefon System in Office 365 mit einer lokalen Konnektivität über eine vorhandene Skype for Business Server-Bereitstellung in Verbindung bringen. Weitere Informationen finden Sie unter [Planen Ihres Telefonsystems in Office 365 (Cloud PBX)-Lösung](plan-your-phone-system-cloud-pbx-solution.md) und [Planen des Telefonsystems in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Wenn Sie über eine vorherige Skype for Business-oder lync Server-Bereitstellung verfügen und das Schema erweitert haben, müssen Sie das Schema für die Cloud Connector-Bereitstellung nicht bereinigen, solange Sie alle Skype for Business-oder lync Server-Komponenten aus Ihrer Umgebung entfernt haben.

- Ihre Benutzer werden online verwaltet.

- Wenn Ihre Organisation Verzeichnissynchronisierung (DirSync) konfiguriert hat, müssen alle Konten von Benutzern, die für Hybridtelefonie geplant sind, zuerst in Ihrer lokalen Bereitstellung erstellt und dann mit der Cloud synchronisiert werden.

- Falls erforderlich, können Sie Ihren aktuellen PSTN-Betreiber behalten.

- Wenn Sie Einwahlkonferenzen für Benutzer bereitstellen möchten, die auf Cloud Connector gehostet werden, können Sie die Lizenz für PSTN-Konferenzen erwerben oder im Rahmen des Audiokonferenz-Angebots von Microsoft zahlen.

- Die Lizenz für die Audiokonferenz (oder das Angebot "im Voraus bezahlen") ist auch für Anruf Eskalationen erforderlich. Wenn ein Skype for Business-Benutzer einen Anruf von einem externen PSTN-Benutzer erhält und einen weiteren Teilnehmer zu diesem Anruf hinzufügen möchte (den Anruf an eine Konferenz weiterleiten), wird die Eskalation über den Microsoft-Audiokonferenzdienst durchgeführt.

- Cloud Connector 2.0 und höher unterstützt jetzt Medienumgehung. Die medienumgehung ermöglicht es einem Client, Medien direkt an das öffentlich geschaltete Telefon Netzwerk (PSTN) nächster Hop zu senden – einen Gateway-oder Session Border Controller (SBC) – und die Cloud Connector Edition-Komponente aus dem Medienpfad zu entfernen. Weitere Informationen finden Sie unter [Planen der medienumgehung in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2.1 und höher unterstützt das Überwachen von Cloud Connector mithilfe von Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md).

- Cloud Connector ist in allen Ländern verfügbar, in denen Office 365 Enterprise E5 verfügbar ist.

Dieses Thema enthält die folgenden Abschnitte:

- [Cloud Connector Edition – Komponenten](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Cloud Connector Edition – Topologien](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Anforderungen für die Bereitstellung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informationen, die Sie vor der Bereitstellung sammeln müssen](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Hinweise zum Wählplan](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Überlegungen zur hohen Verfügbarkeit](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Cloud Connector-Mediendatenverkehr](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Überwachung und Problembehandlung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Weitere Informationen](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Cloud Connector Edition – Komponenten
<a name="BKMK_Components"> </a>

Mit Cloud Connector Edition stellen Sie eine Reihe von gepackten VMS bereit, die eine minimale Skype for Business Server-Topologie enthalten – bestehend aus einer Edge-Komponente, einer Mediations Komponente und einer Rolle des zentralen Verwaltungsspeichers (CMS). Sie können auch einen Domänencontroller installieren, der für die interne Funktion von Cloud Connector erforderlich ist. Diese Dienste sind für hybride mit Ihrem Office 365-Mandanten konfiguriert, der Skype for Business Online-Dienste umfasst.

![Cloud Connector Edition – Komponenten](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Cloud Connector-Komponenten bieten die folgenden Funktionen:

- **Edge-Komponente** – die Kommunikation zwischen der lokalen Topologie und den Onlinediensten durchläuft die Edge-Komponente, die die folgenden Komponenten umfasst:

  - **Access Edge** – bietet SIP-Routing zwischen der lokalen Bereitstellung und Skype for Business Online.

  - **Medien Relay** – ermöglicht das Routing von Medien zwischen der Mediations Komponente und anderen Medien Endpunkten.

  - **Media Relay Authentication/MRAS** -generiert Tokens für den Zugriff auf Medien Relais.

- **Ausgehendes Routing** – ermöglicht den Lastenausgleich des VoIP-Datenverkehrs zwischen Gateways oder SBCS, die mit einer Cloud Connector-Appliance verbunden sind. Anrufe werden gleichmäßig zwischen allen Gateways oder SBCS aufgeteilt, die mit der Cloud Connector-Appliance verbunden sind.

    Bietet Routing zu Gateways basierend auf Richtlinien. Es werden nur globale Richtlinien unterstützt, die auf (ausgehenden) PSTN-Zielnummern basieren.

- **Rolle des zentralen Verwaltungsspeichers (CMS)** – umfasst den Konfigurationsspeicher für die Topologie-Komponenten, einschließlich der CMS-Dateiübertragung.

- **Replikat des zentralen Verwaltungsspeichers (CMS)** – synchronisiert Konfigurationsinformationen vom globalen CMS DB auf dem CMS-Rollen Server.

- **Domänencontroller** – Cloud Connector für Active Directory-Domänendienste zum Speichern aller globalen Einstellungen und Gruppen, die für die Bereitstellung von Cloud Connector-Komponenten erforderlich sind. Für jede Cloud Connector-Appliance wird eine Gesamtstruktur erstellt. Der Domänencontroller darf keine Verbindungen mit dem Active Directory Production aufweisen. Zu den Active Directory-Diensten gehören:

  - Active Directory-Domänendienste

  - Active Directory-Zertifikatdienste zum Erstellen interner Zertifikate

- **Mediation-Komponente** – implementiert das SIP-und Media Gateway-Zuordnungs Protokoll zwischen Skype for Business und PSTN-Gateways. Enthält ein CMS-Replikat, das die Konfiguration aus der globalen CMS-Datenbank synchronisiert.

## <a name="cloud-connector-edition-topologies"></a>Cloud Connector Edition – Topologien
<a name="BKMK_Topologies"> </a>

Im Rahmen dieser Erläuterungen ist von PSTN-Standorten die Rede. Eine PSTN-Website ist eine Kombination aus Cloud Connector-Appliances, die am gleichen Standort bereitgestellt werden, und mit gemeinsamen PSTN-Gateways, die mit Ihnen verbunden sind. PSTN-Standorte bieten Ihnen folgende Möglichkeiten:

- Verbindungen zu den Gateways herstellen, die Ihren Benutzern am nächsten sind

- Ermöglichen Sie Skalierbarkeit, indem Sie mehrere Cloud Connector-Appliances innerhalb einer oder mehrerer PSTN-Standorte bereitstellen.

- Ermöglichen Sie eine höhere Verfügbarkeit, indem Sie mehrere Cloud Connector-Appliances auf einer einzigen PSTN-Website bereitstellen.

In diesem Thema werden PSTN-Standorte vorgestellt. Weitere Informationen zum Planen Ihrer PSTN-Standorte finden Sie unter [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Sie können die folgenden Cloud Connector-Topologien bereitstellen:

- Eine einzelne Cloud Connector Edition-Appliance pro PSTN-Website. Diese Topologie wird nur für Evaluierungszwecke empfohlen, da sie keine hohe Verfügbarkeit bietet.

- Mehrere Cloud Connector Edition-Appliances pro PSTN-Website, um eine höhere Verfügbarkeit zu gewährleisten.

- Mehrere PSTN-Standorte mit mehreren Cloud Connector Edition-Appliances, um Skalierbarkeit mit höherer Verfügbarkeit bereitzustellen. Sie können bis zu 200 Standorte bereitstellen.

Beim Planen Ihrer Topologie sollten Sie Folgendes beachten:

- Mit Cloud Connector 2,0 und höher kann eine PSTN-Website bis zu 16 Cloud Connector-Appliances enthalten. Vorherige Versionen unterstützen bis zu vier Appliances pro Standort.

- Es gibt zwei Arten von Hardwarekonfigurationen, die mit Cloud Connector getestet wurden:

  - Die größere Version ist in der Lage, große Mengen von Anrufen gleichzeitig zu verarbeiten. Sie wird in jeder Art von Produktionsumgebung unterstützt.

  - Die kleinere Version ist dafür gedacht, auf Hardware mit geringerer Leistungsfähigkeit ausgeführt zu werden. Sie kann für Prüfzwecke oder für Standorte mit geringerem Anrufaufkommen verwendet werden. Aber auch wenn Sie eine kleinere Version von Cloud Connector einsetzen, müssen Sie dennoch die Hardwareanforderungen der Produktionsklasse berücksichtigen (zum Beispiel doppelte Stromversorgung).

- Wenn Sie über Cloud Connector Version 2,0 oder höher verfügen und die maximale Konfiguration von 16 Appliances (mit größerer Hardware) bereitstellen, kann Ihre PSTN-Website bis zu 8.000 gleichzeitige Anrufe verarbeiten. Wenn Sie die kleinere Version bereitstellen, werden maximal 800 gleichzeitige Anrufe unterstützt.

    Außerdem müssen Sie einen Teil der Appliances für hohe Verfügbarkeit verwenden. Die Mindestkonfiguration sieht eine für hohe Verfügbarkeit reservierte Appliance vor.

  - Wenn Sie in Version 2 eine 15 +1-Konfiguration bereitstellen, kann Ihre PSTN-Website bis zu 7.500 gleichzeitige Anrufe verarbeiten.

  - Wenn Sie eine frühere Version verwenden und die maximale 3+1-Konfiguration (mit leistungsstärkerer Hardware) bereitstellen, kann Ihr PSTN-Standort bis zu 1.500 Anrufe gleichzeitig verarbeiten. Wenn Sie die kleinere Version bereitstellen, werden maximal 150 Anrufe unterstützt.

-  Falls Sie noch mehr Anrufe pro PSTN-Standort verarbeiten möchten, können Sie die Zahl der Anrufe heraufsetzen, indem Sie an einem Ort zusätzliche PSTN-Standorte bereitstellen.

> [!NOTE]
> Sofern nicht anders angegeben, wird in den folgenden Diagrammen und Beispielen die Verwendung der größeren Version von Cloud Connector vorausgesetzt.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Einzelne Cloud Connector-Appliance an einem einzelnen PSTN-Standort

Das folgende Diagramm zeigt eine einzelne Cloud Connector Edition-Appliance innerhalb einer einzelnen PSTN-Website. Beachten Sie, dass Cloud Connector aus vier VMS besteht, die auf einem physikalischen Hostcomputer, der sich aus Sicherheitsgründen befindet, in einem Umkreisnetzwerk installiert sind.

![Ein Cloud Connector mit einem Festnetzstandort](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Mehrere Cloud Connector-Appliances an einem einzelnen PSTN-Standort

 Aus Gründen der Skalierbarkeit und der höchst Verfügbarkeit können Sie festlegen, dass mehrere Cloud Connector-Editionen auf einer einzelnen PSTN-Website vorhanden sind, wie im folgenden Diagramm dargestellt. Beachten Sie dabei Folgendes:

- Die Anrufe werden auf die verschiedenen Cloud Connector-Instanzen in einem Pool verteilt, wobei die Verteilung nach dem Zufallsprinzip erfolgt.

- Bei Ihrer Kapazitätsplanung müssen Sie berücksichtigen, dass die Last auch dann noch bewältigt werden muss, wenn eine oder mehrere Cloud Connector-Instanzen offline sind. Mit der folgenden Berechnung können Sie ermitteln, wie viele Anrufe verarbeitet werden können:

  - **n+1 Boxen**. Für die größere Version von Cloud Connector unterstützen n + 1-Felder\*500 n gleichzeitige Anrufe mit einer Verfügbarkeit von 99,8%.

    Für die kleinere Version von Cloud Connector unterstützen n + 1-Felder\*50 n gleichzeitige Anrufe mit einer Verfügbarkeit von 99,8%.

  - **n+2 Boxen**. Für die größere Version von Cloud Connector unterstützen n + 2-Felder\*500 n gleichzeitige Anrufe mit einer Verfügbarkeit von 99,9%.

    Für die kleinere Version von Cloud Connector unterstützen n + 2-Felder\*50 n gleichzeitige Anrufe mit einer Verfügbarkeit von 99,9%.

![Zwei Cloud Connectors im Rahmen eines Festnetzstandorts](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Mehrere PSTN-Standorte mit einer oder mehreren Cloud Connector-Instanzen pro Standort

Alternativ können Sie sich für mehrere PSTN-Standorte mit einer oder mehreren Cloud Connector Edition-Instanzen pro Standort entscheiden. Falls Ihr PSTN-Standort den Grenzwert für gleichzeitige Anrufe erreicht, können Sie einen weiteren PSTN-Standort hinzufügen, um alle Anrufe zu verarbeiten.

Die Verwendung mehrerer PSTN-Standorte bietet Ihnen außerdem die Möglichkeit, Verbindungen zu den Gateways herzustellen, die Ihren Nutzern am nächsten sind. Nehmen wir einmal an, Sie haben PSTN-Gateways in Seattle und in Amsterdam. Sie können also zwei PSTN-Gateways – eins in Seattle und eins in Amsterdam – bereitstellen und Nutzer dem PSTN-Standort zuweisen, der ihnen näher ist. Dadurch werden Nutzer aus Seattle dann an den PSTN-Standort und die Gateways in Seattle und Nutzer aus Amsterdam an den PSTN-Standort und die Gateways in Amsterdam weitergeleitet:

![Cloud Connector Edition im Rahmen von zwei Festnetzstandorten](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Anforderungen für die Bereitstellung
<a name="BKMK_Requirements"> </a>

Bevor Sie Cloud Connector Edition bereitstellen, stellen Sie sicher, dass Sie für Ihre Umgebung die folgenden Aktionen ausführen:

- **Für den Hostcomputer –** VMS für Cloud-Connectors müssen auf dedizierter Hardware bereitgestellt werden, auf der Windows Server 2012 R2 Datacenter Edition (Englisch) ausgeführt wird und die Hyper-V-Rolle aktiviert ist.

    Für Version 2.0 und höher muss die Netzwerkkarte des Hostcomputers, die an den Unternehmensnetzwerk-Switch für Skype for Business gebunden ist, mit einer IP-Adresse im gleichen Subnetz wie die Cloud Connector-Computer im Unternehmensnetzwerk konfiguriert sein. 

- Für Versionen 2,1 und höher muss die Host-Appliance .NET Framework 4.6.1 oder höher installiert haben.

- **Für die virtuellen Computer –** Ein Windows Server 2012 R2 ISO (Englisch)-Bild (. ISO). Die ISO wird für die virtuellen Computer, auf denen Skype for Business Cloud Connector Edition ausgeführt wird, in virtuelle Festplatten konvertiert.

- Die erforderliche Hardware zur Unterstützung der Installation der 4 VMs für jede Cloud Connector-Edition in Ihrer Bereitstellung. Die folgenden Konfigurationen werden empfohlen:

  - 64-Bit-Dualprozessor, sechs Kern (12 echte Kerne), 2,50 Gigahertz (GHz) oder höher

  - 64 GB EEC-RAM 

  - Vier Festplatten mit 600 GB (oder mehr),10.000 U/min, 128 MB Cache, 6 GB/s SAS in RAID-5-Konfiguration

  - Drei 1-GB/s-RJ45-Netzwerkadapter mit hohem Durchsatz

- Wenn Sie festlegen, dass die kleinere Version von Cloud Connector Edition bereitgestellt werden soll, die bis zu 50 gleichzeitige Anrufe unterstützt, benötigen Sie die folgende Hardware:

  - Intel i7 4790 QuadCore mit Grafikeinheit Intel 4600 Graphics (High-End-Grafik ist nicht erforderlich)

  - 32 GB DDR3-1600, Non-ECC

  - 2: 1 TB 7.200 U/min SATA III (6 GBit/s) in RAID 0

  - 2: 1 GBit/s Ethernet (RJ45)

- Wenn auf dem Hostcomputer ein Proxyserver zum Surfen im Internet erforderlich ist, sollten Sie die folgenden Konfigurationsänderungen vornehmen:

  - Um den Proxy zu umgehen, geben Sie die WinHTTP-Proxyeinstellungen an, die mit Ihrem Proxy Server festgelegt sind, und eine Umgehungsliste, einschließlich des "192.168.213. \*"Netzwerk, das von ihren Cloud Connector-Verwaltungsdiensten und Skype for Business-Corpnet-Subnetz verwendet wird, wie in ihrer CloudConnector. ini-Datei definiert. Andernfalls führt die Verwaltungs Konnektivität zu einem Fehler und verhindert die Bereitstellung und automatische Wiederherstellung des Cloud Connectors. Es folgt ein Beispiel für einen WinHTTP-Konfigurationsbefehl: netsh WinHTTP-Proxy "10.10.10.175:8080" Bypass-List\*= ". local; 1. \*; 172,20. \*; 192.168.218. \*"\<lokal\>".

  - Geben Sie Proxyeinstellungen pro Computer und nicht pro Benutzer an. Andernfalls schlägt der Download von Cloud Connector fehl. Sie können Proxyeinstellungen wie folgt mit einer Registrierungsänderung oder mit einer Gruppenrichtlinieneinstellung pro Computer angeben:

  - **Registrierung:** HKEY_LOCAL_MACHINE \software\policies\microsoft\windows\currentversion\internet-Einstellungen] ProxySettingsPerUser DWORD: 00000000

  - **Gruppenrichtlinien:** Computer\>administrative Vorlagen\>Windows-\> Komponenten Internet Explorer: Proxy Einstellungen pro Computer vornehmen (und nicht pro Benutzer)

- Qualifizierte PBX/qualifizierter Trunk oder qualifizierter SBC/qualifiziertes Gateway (Empfohlen werden mindestens zwei Gateways.)

    Cloud Connector unterstützt die gleichen Session Border Controller (SBCs), die für Skype for Business zertifiziert sind. Weitere Informationen finden Sie unter [Telefonie-Infrastruktur für Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Ein lokales Server Administratorkonto mit Berechtigungen zum Installieren und Konfigurieren von Hyper-V auf den Hostservern. Das Konto muss über Administratorberechtigungen auf dem lokalen Server verfügen, auf dem Hyper-V installiert und konfiguriert ist.

- Im Zuge der Bereitstellung werden Sie aufgefordert, ein Domänenadministratorkonto mit Berechtigungen zum Erstellen und Veröffentlichen der Topologie in der Cloud Connector-Domäne anzulegen. 

- Die externen DNS-Einträge, die in der im Installationspaket enthaltenen Datei „CloudConnector.ini“ definiert sind:

  - Externer DNS-Eintrag für den Access Edge-Dienst der Edge-Komponente; Beispiel: AP.\<Domain-Name\>. Sie benötigen einen Eintrag pro PSTN-Standort. Dieser Eintrag muss IP-Adressen für alle Edges des jeweiligen Standorts enthalten.

- Ein Office 365-Mandant, in dem alle erforderlichen DNS-und SRV-Einträge erstellt wurden.

    > [!IMPORTANT]
    > Wenn Sie Ihren Mandanten in Cloud Connector Edition integrieren, wird die Verwendung des Standarddomänen Suffixes. onmicrosoft.com als SIP-Domäne für Ihre Organisation nicht unterstützt. > Sie SIP nicht verwenden können. \<Domänenname\> als Name der Edge Access-Proxyschnittstelle des Cloud Connectors, da dieser DNS-Eintrag von Office 365 verwendet wird.

- Ein von einer öffentlichen Zertifizierungsstelle (CA) erhaltenes Zertifikat für den externen Edgeserver.

- Firewallregeln, um den Datenverkehr über die erforderlichen Ports zuzulassen, wurden fertiggestellt.

- Eine Internet Verbindung für den Hostcomputer und die VMs. Cloud Connector lädt einige Software aus dem Internet herunter. Daher müssen Sie Gateway-und DNS-Server Informationen bereitstellen, damit der Cloud Connector-Hostcomputer und VMS eine Verbindung mit dem Internet herstellen und die erforderliche Software herunterladen können.

- Ein Remote-PowerShell-Modul für einen Mandanten ist auf der Hostmaschine installiert.

- Die Anmeldeinformationen des Office 365 Skype for Business-Administrators zum Ausführen von Remote-PowerShell  

    > [!IMPORTANT]
    > Für das Administratorkonto darf die mehrstufige Authentifizierung NICHT aktiviert sein.

> [!NOTE]
> Die Bereitstellung von Cloud Connector wird nur auf der virtualisierten Microsoft Hyper-V-Plattform unterstützt. Andere Plattformen (zum Beispiel VMware und Amazon Web Services) werden nicht unterstützt.

> [!NOTE]
> Der minimale Hardware-Leitfaden für die Ausführung von Cloud Connector basiert auf der grundlegenden Hardwarekapazität (Cores, MHz, Gigabyte usw.) mit einigen Puffern zur Unterbringung von immateriellen Performance-Beeinträchtigungen, die in der Architektur eines beliebigen Computers vergraben sind. Microsoft hat den Worst-Case-Auslastungstest auf kommerziell verfügbarer Hardware ausgeführt, wobei die Mindestvorgaben erfüllt sind. Medienqualität und Systemleistung werden überprüft. Offizielle Cloud Connector Appliance-Partner von Microsoft verfügen über spezifische Cloud Connector-Hardwareimplementierungen, auf denen Sie die Leistung unabhängig getestet haben, und Sie stehen für die Eignung ihrer Hardware, um die Auslastungs-und Qualitätsanforderungen zu erfüllen.

> [!NOTE]
> Von AudioCodes und Sonus hergestellte Geräte enthalten geänderten Code und können mit Servern unter Windows Server Standard Edition betrieben werden. Diese Geräte werden unterstützt.

## <a name="information-you-need-to-gather-before-deployment"></a>Informationen, die Sie vor der Bereitstellung sammeln müssen
<a name="BKMK_PlanDeployment"> </a>

Bevor Sie mit der Bereitstellung beginnen, müssen Sie die Größe Ihrer Bereitstellung, die betreffenden SIP-Domänen sowie die Konfigurationsinformationen für jeden PSTN-Standort, den Sie bereitstellen möchten, bestimmen. Zunächst nehmen Sie folgenden Schritt vor:

- Identifizieren Sie alle SIP-Domänen, die von dieser Bereitstellung abhängig von den in Ihrem Unternehmen verwendeten SIP-URIs bedient werden.

- Ermitteln Sie die Anzahl der PSTN-Standorte, die Sie bereitstellen müssen.

- Stellen Sie sicher, dass Sie über die erforderliche Hardware verfügen, um die vier VMS zu unterstützen, die Sie für jede Cloud Connector-Edition installieren werden.

Für jede PSTN-Website, die Sie bereitstellen möchten, müssen Sie Folgendes ausführen:

- Erstellen Sie Namen für alle Komponenten in jeder Cloud Connector-Appliance (siehe [Ermitteln von Bereitstellungs Parametern](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definieren Sie Portbereiche (siehe auch [Ports und Protokolle](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)). 

- Erstellen Sie externe DNS-Einträge für die Edgekomponente (siehe [Anforderungen für die Bereitstellung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Bestimmen Sie die Zertifikatanforderungen für die Edgekomponente (siehe auch [Zertifikatanforderungen](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Ports und Protokolle
<a name="BKMB_Ports"> </a>

Beim Definieren von Medienportbereichen sollten Sie Folgendes berücksichtigen:

- Clients verwenden immer Portbereich 50000 bis 50019 für Mediendatenverkehr – dieser Bereich ist in Skype for Business Online vordefiniert und kann nicht geändert werden.

- Die Vermittlungskomponente verwendet für den Mediendatenverkehr standardmäßig einen Portbereich von 49152 bis 57500. Die Verbindung wird jedoch über eine interne Firewall hergestellt, und aus Sicherheitsgründen können Sie diesen Portbereich in Ihrer Topologie einschränken. Pro Anruf benötigen Sie bis zu vier Ports. Falls Sie die Anzahl der Ports zwischen der Vermittlungskomponente und dem PSTN-Gateway begrenzen möchten, müssen Sie den entsprechenden Portbereich auf dem Gateway ebenfalls konfigurieren.

- Sie müssen den Cloud Connector in einem Umkreisnetzwerk bereitstellen. Auf diese Weise sind Sie durch zwei Firewalls geschützt:

  - Bei der ersten Firewall handelt es sich um eine externe Firewall zwischen dem Internet und Ihrem Umkreisnetzwerk.

  - Die zweite Firewall ist intern zwischen dem Umkreisnetzwerk und dem internen Netzwerk.

    Ihre Clients können sich im Internet oder im internen Netzwerk befinden: 

  - Bei Internetclients erfolgt die Verbindung zu Ihrem PSTN über die externe Firewall mithilfe der Edgekomponente.

  - Clients im internen Netzwerk stellen über die interne Firewall eine Verbindung mit der Mediations Komponente im Umkreisnetzwerk her, wodurch der Datenverkehr mit dem SBC-oder PSTN-Gateway verbunden wird.

    Das bedeutet, dass Sie in beiden Firewalls Ports öffnen müssen. 

In den folgenden Tabellen werden Ports und Portbereiche im Hinblick auf die externen und internen Firewalls beschrieben.

Diese Tabelle stellt die Ports und Portbereiche dar, mit denen die Kommunikation zwischen Clients im internen Netzwerk und der Vermittlungskomponente hergestellt werden kann:

**Interne Firewall**



|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Cloud Connector-Mediations Komponente  <br/> |SBC/PSTN-Gateway  <br/> |Beliebig  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN-Gateway  <br/> |Cloud Connector-Mediations Komponente  <br/> |Beliebig  <br/> |TCP 5068/TLS 5067  <br/> |
|Cloud Connector-Mediations Komponente  <br/> |SBC/PSTN-Gateway  <br/> |UDP 49 152-57 500  <br/> |Alle\*\*\*  <br/> |
|SBC/PSTN-Gateway  <br/> |Cloud Connector-Mediations Komponente  <br/> |Alle\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Cloud Connector-Mediations Komponente  <br/> |Interne Clients  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50.000-50.019  <br/> (Optional)  <br/> |
|Cloud Connector-Mediations Komponente  <br/> |Interne Clients  <br/> |UDP 49 152-57 500\*  <br/> |TCP 50000–50019  <br/> |
|Interne Clients  <br/> |Cloud Connector-Mediations Komponente  <br/> |TCP 50.000-50.019  <br/> |TCP 49 152-57 500\*  <br/> |
|Interne Clients  <br/> |Cloud Connector-Mediations Komponente  <br/> |TCP 50000–50019  <br/> |UDP 49 152-57 500\*  <br/> |

\*Dies ist der Standardportbereich für die Mediation-Komponente. Um einen optimalen Anruffluss zu gewährleisten, sind vier Ports pro Anruf notwendig.

\*\*Dieser Port muss auf dem SBC/PSTN-Gateway konfiguriert sein. 5060 ist ein Beispiel. An Ihrem SBC/PSTN-Gateway können Sie auch andere Ports konfigurieren.

\*\*\*Beachten Sie, dass Sie den Portbereich Ihres SBC/Gateways auch begrenzen können, wenn dies vom SBC/Gateway-Hersteller zugelassen wird.

Aus Sicherheitsgründen können Sie den Portbereich für die Mediations Komponente mithilfe des Cmdlets " [CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) " einschränken.

Mit dem folgenden Befehl können Sie beispielsweise die Anzahl der Ports einschränken, die von der Mediations Komponente für den Mediendatenverkehr auf 50 000-51 000 für Audio (ein-und ausgehend) verwendet werden. Mit dieser Konfiguration kann die Vermittlungskomponente 250 Anrufe gleichzeitig verarbeiten. Beachten Sie, dass es ratsam sein kann, diesen Bereich auch am SBC/PSTN-Gateway zu begrenzen:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Wenn Sie den Namen der Mediations Komponente abrufen und Standardanschlüsse sehen möchten, können Sie das Cmdlet [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) wie folgt verwenden:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

In der folgenden Tabelle werden Ports und Portbereiche für die Kommunikation zwischen der Edge-Komponente des Cloud-Connectors und der externen Firewall angezeigt. Bei den Angaben handelt es sich um Mindestempfehlungen.

In diesem Fall wird der gesamte Mediendatenverkehr über den Online-Edge wie folgt durchlaufen: Endpunkt des Benutzers –\>Online-Edge –\>Cloud Connector Edge:

**Externe Firewall – Mindestkonfiguration**



|**Quell-IP**|**Ziel-IP**|**Quell-Port**|**Ziel-Port**|
|:-----|:-----|:-----|:-----|
|Beliebig  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig   <br/> |Beliebig  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig   <br/> |Beliebig  <br/> |TCP 80  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig   <br/> |Beliebig  <br/> |UDP 53  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig   <br/> |Beliebig  <br/> |TCP 53  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Beliebig  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
|Beliebig  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |

In der nächsten Tabelle werden Ports und Portbereiche zum Aktivieren der Kommunikation zwischen der Edge-Komponente des Cloud-Connectors und der externen Firewall angezeigt. Diese Tabelle zeigt die empfohlene Lösung.

In diesem Fall kann der gesamte Mediendatenverkehr für den Endpunkt im Internet direkt an die Edge-Komponente des Cloud-Connectors fließen. Der Medienpfad ist der Endpunkt des Endpunkts\> des Benutzers.

> [!NOTE]
> Diese Lösung kann nicht verwendet werden, falls sich der Benutzerendpunkt hinter einer symmetrischen NAT befindet.

**Externe Firewall – empfohlene Konfiguration**


|**Quell-IP**|**Ziel-IP**|**Quellport**|**Ziel-Port**|
|:-----|:-----|:-----|:-----|
|Beliebig  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig   <br/> |Beliebig  <br/> |TCP (MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig   <br/> |Beliebig  <br/> |TCP 80  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig   <br/> |Beliebig  <br/> |UDP 53  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig   <br/> |Beliebig  <br/> |TCP 53  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig  <br/> |TCP 50.000-59.999  <br/> |Beliebig  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig  <br/> |UDP 3478; UDP 50000–59999  <br/> |Beliebig   <br/> |
|Beliebig  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig  <br/> |TCP 443; TCP 50000–59999  <br/> |
|Beliebig  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |Beliebig  <br/> |UDP 3478; UDP 50000–59999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Anforderungen für die Internetkonnektivität des Hosts
<a name="BKMB_Ports"> </a>

Der Hostcomputer muss in der Lage sein, externe Ressourcen zu erreichen, um Cloud Connector erfolgreich zu installieren, zu aktualisieren und zu verwalten. Die folgende Tabelle zeigt die erforderlichen Ziele und Ports zwischen dem Hostcomputer und externen Ressourcen.

|Richtung  <br/> |Quell-IP  <br/> |Ziel-IP  <br/> |Quellport  <br/> |Zielport  <br/> |Protokoll  <br/> |Verwendungszweck  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ausgehend  <br/> |Cloud Connector Host IPS  <br/> |Beliebig  <br/> |Beliebig  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Ausgehend  <br/> |Cloud Connector Host IPS  <br/> |Beliebig  <br/> |Beliebig  <br/> |80, 443  <br/> |TCP  <br/> |Zertifikatssperrliste (CRL)  <br/> |
|Ausgehend  <br/> |Cloud connectorer-Host IPS  <br/> |Beliebig  <br/> |Beliebig  <br/> |80, 443  <br/> |TCP  <br/> |Cloud Connector-Update  <br/> Administrator-PowerShell  <br/> Administrator-PowerShell  <br/> Wenn restriktivere Regeln erforderlich sind, finden Sie unter den folgenden URLs zum Thema Whitelists weitere Informationen:  <br/> |

Wenn restriktivere Regeln erforderlich sind, finden Sie unter den folgenden URLs zum Thema Whitelists weitere Informationen:

- [URLs der Zertifikatsperrliste](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) in [Office 365-URLs und IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [Konfigurieren einer Firewall für Software Updates](https://technet.microsoft.com/en-us/library/bb693717.aspx)

- Skype for Business Online-Administrator- \*PowerShell:. online.lync.com

    Wenn Sie einen Proxyausschluss für dieses Ziel benötigen, müssen Sie ihn der WinHTTP-Umgehungsliste hinzufügen.

- Cloud Connector-Update: [Download Center](https://aka.ms/CloudConnectorInstaller), [https://go.microsoft.com](https://go.microsoft.com)und[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>DNS-Namensauflösung für die Edgekomponente
<a name="BKMB_Ports"> </a>

Die Edge-Komponente muss die externen Namen von Office 365-Diensten und die internen Namen anderer Cloud Connector-Komponenten auflösen.

Jede Edge-Komponente ist ein mehrfach vernetzter Computer mit externen und internen Schnittstellen. Cloud Connector stellt DNS-Server auf der Domänen Controller Komponente im Umkreisnetzwerk bereit. Sie können den Edgeserver im Umkreis für alle Namensauflösungen auf den DNS-Server verweisen, aber Sie müssen den Cloud Connector-DNS-Server aktivieren, um externe Namen zu beheben, indem Sie eine DNS-Zone mit einem oder mehreren DNS-a-Einträgen für externe Abfragen einrichten, die auf den Namen verweisen. Suchen nach anderen öffentlichen DNS-Servern.

Wenn Sie in der INI-Datei den Namen des FQDN für Gateways aus dem gleichen Domänen Raum wie Ihre SIP-Domäne festlegen, wird die autorisierende Zone für diese SIP-Domäne auf dem DNS-Server innerhalb des Perimeters erstellt. Wenn Edgeserver auf diesen DNS-Server verweist, um Namen aufzulösen, löst Edge den _sipfederationtls nie auf. \<yourdomain\> -DNS-Eintrag, der für den Anruffluss erforderlich ist. In diesem Fall empfiehlt Microsoft, dass Sie einen DNS-Server auf der Edge-externen Schnittstelle bereitstellen, um Internet Namen-Lookups zu beheben, und jede Edge-Komponente muss eine Hostdatei verwenden, um andere Komponentennamen für Cloud Connectors in IP-Adressen aufzulösen.

> [!NOTE]
> Aus Sicherheitsgründen empfehlen wir, dass Sie den Cloud Connector-DNS-Server nicht auf interne Server in der Produktionsdomäne für die Namensauflösung verweisen.

### <a name="determine-deployment-parameters"></a>Bereitstellungsparameter festlegen
<a name="BKMK_SiteParams"> </a>

Zunächst müssen Sie folgende allgemeine Bereitstellungsparameter festlegen:


|**Element**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|SIP-Domänen  <br/> |SIP-URI wird von Unternehmensbenutzern verwendet. Geben Sie alle SIP-Domänen an, die von dieser Bereitstellung bedient werden sollen. Sie können mehrere SIP-Domänen eintragen.  <br/> ||
|Anzahl der PSTN-Standorte  <br/> |Anzahl der PSTN-Standorte, die Sie bereitstellen möchten.  <br/> ||

Für jeden PSTN-Standort, den Sie bereitstellen möchten, müssen Sie die folgenden Informationen sammeln, bevor Sie mit der Bereitstellung beginnen. Sie müssen diese Informationen beim Aktualisieren der CloudConnector.ini-Datei bereitstellen.

Beachten Sie beim Konfigurieren der Gateway-Informationen Folgendes:

- Wenn Sie nur ein Gateway haben, entfernen Sie den Abschnitt für das zweite Gateway in der .ini-Datei. Wenn Sie mehr als zwei Gateways haben, orientieren Sie sich am vorhandenen Format, um neue Gateways hinzuzufügen.

- Stellen Sie sicher, dass die IP-Adresse und der Port des bzw. der Gateways korrekt sind. 

- Behalten Sie das sekundäre Gateway oder fügen Sie zusätzliche Gateways hinzu, um die hohe Verfügbarkeit auf der PSTN-Gateway-Ebene zu gewährleisten.

(Optional) Zum Einschränken der ausgehenden Rufnummern aktualisieren Sie den LocalRoute-Wert.



|**Standortparameter**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|Virtuelle Maschine – Domänenname  <br/> |Domänenname für die internen Komponenten von Cloud Connector. Diese Domäne muss sich von der Produktionsdomäne unterscheiden. Der Name muss für sämtliche Cloud Connector-Appliances verwendet werden.  <br/> Name in INI-Datei: "VirtualMachineDomain"  <br/> |Eine .local-Domäne wird bevorzugt.   <br/> |
|Name des Domänencontrollers des Cloud Connectors  <br/> |Name des Domänencontrollers   <br/> Name in der INI-Datei: "Servername"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Cloud Connector-Domänencontroller-IP/Subnetzmaske  <br/> |IP-Adresse des Domänencontrollers   <br/> Name in der INI-Datei: "IP"  <br/> ||
|O365-Onlinedienst-FQDNs  <br/> |Muss in den meisten Fällen die Standardeinstellung für die weltweite Office 365-Instanz sein.  <br/> Name in INI-Datei: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Skype for Business-Websitename; Beispiel: Seattle.  <br/> Name in der INI-Datei: "Sitename"  <br/> Für Version 1.4.1 und höher muss der Standortname für jeden Standort eindeutig sein und mit dem in Office 365 definierten PSTN-Standort (sofern vorhanden) übereinstimmen. Beachten Sie, dass bei der Registrierung der ersten Appliance an einem Standort automatisch PSTN-Standorte erstellt werden.  <br/> ||
|HardwareType  <br/> Version 1.4.1 und höher  <br/> |Hardwaretyp. Der Standardwert ist „Normal“. Sie können diesen Wert aber auch auf „Minimum“ festlegen.  <br/> ||
|Landesvorwahl  <br/> |Telefonvorwahl des Landes  <br/> Name in INI-Datei: "CountryCode"  <br/> ||
|Ort  <br/> |Ort (optional)  <br/> Name in INI-Datei: "Ort"  <br/> ||
|Bundesland/Kanton  <br/> |Bundesland (optional)  <br/> Name in INI-Datei: "Zustand"  <br/> ||
|Basis-VM-IP-Adresse  <br/> |Die IP-Adresse der temporären Basis-VM, die zum Erstellen des VHDX für alle virtuellen Computer des Cloud Connectors verwendet wird. Diese IP muss sich in dem Umkreissubnetz des Unternehmensnetzwerks befinden, das im nächsten Schritt definiert wird, und benötigt Internetzugriff. Achten Sie darauf, das Standardgateway des Unternehmens und den ins Internet routbaren DNS-Server zu definieren.  <br/> Name in INI-Datei: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 und höher  <br/> |Die Adresse des Windows Server Update Services (WSUS) – ein Intranetserver zum Hosten von Updates von Microsoft Update.  <br/> Sie müssen keine Angabe machen, wenn WSUS nicht benötigt wird.   <br/> ||
|Subnetzmaske für internes Netzwerk  <br/> |Cloud Connector konfiguriert ein IP-Netzwerk für die interne Kommunikation zwischen Cloud Connector-Komponenten. Der Edge muss außerdem mit einem anderen Subnetz verbunden sein, das Internetkonnektivität zulässt.  <br/> Name in der INI-Datei: "CorpnetIPPrefixLength" unter "Parameter für einen Pool von VM-Netzwerk"  <br/> ||
|Subnetzmaske für externes Netzwerk   <br/> |Für das externe Netzwerk der Edgekomponente.  <br/> Name in der INI-Datei: "InternetIPPrefix" unter "Parameter für einen Pool von VM-Netzwerk"  <br/> ||
|Switch-Name für internes Netzwerk  <br/> |Name für Switch, der für das interne Cloud Connector-Netzwerk verwendet wird.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in INI-Datei: "CorpnetSwitchName" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Switch-Name für externes Netzwerk  <br/> |Name für Switch, der für das externe Cloud Connector-Netzwerk verwendet wird.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in INI-Datei: "InternetSwitchName" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Standardgateway für internes Netzwerk  <br/> |Dieses Gateway muss Zugriff auf das Internet bieten (das Internet erfordert auch das Festlegen des DNS-Servers) und wird auf internen Schnittstellen von Cloud Connector-Komponenten konfiguriert.  <br/> Name in INI-Datei: "CorpnetDefaultGateway" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Standardgateway für die externe Schnittstelle der Edgekomponente  <br/> |Wird auf der externen Schnittstelle der Edgekomponente konfiguriert.  <br/> Name in INI-Datei: "InternetDefaultGateway" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|DNS-Server für internes Netzwerk  <br/> |Wird an der internen Schnittstelle der temporären VM konfiguriert. Muss Namensauflösung für Namen im Internet bereitstellen. Ohne Bereitstellung eines DNS-Servers schlägt die Internetverbindung fehl, und die Bereitstellung wird nicht abgeschlossen.  <br/> Name in INI-Datei: "CorpnetDNSIPAddress" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|DNS-Server für externe Schnittstelle der Edgekomponente  <br/> |Wird auf der externen Schnittstelle des Edges konfiguriert.  <br/> Name in INI-Datei: "InternetDNSIPAddress" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Management-Switch-Name  <br/> |Verwaltungs Schalter ist ein temporärer Schalter, der automatisch erstellt wird und für die Konfiguration des Cloud Connectors während der Bereitstellung verwendet wird. Nach der Bereitstellung wird er automatisch getrennt. Es muss sich um ein anderes Subnetz von allen anderen Netzwerken handeln, die in Cloud Connector verwendet werden.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in INI-Datei: "ManagementSwitchName" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Managementsubnetzadresse/-subnetzmaske  <br/> |Das Verwaltungs Subnetz ist ein temporäres Subnetz, das automatisch erstellt wird und für die Konfiguration des Cloud Connectors während der Bereitstellung verwendet wird. Nach der Bereitstellung wird es automatisch entfernt. Es muss sich um ein anderes Subnetz von allen anderen Netzwerken handeln, die in Cloud Connector verwendet werden.  <br/> Namen in der INI-Datei: "ManagementIPPrefix" und "ManagementIPPrefixLength" unter "Parameter für einen Pool von VM-Netzwerk  <br/> ||
|Central Management Store (CMS)-Computer  <br/> |Ein einzelner FQDN wird für den zentralen Verwaltungsspeicher (CMS) verwendet. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in INI-Datei: "Servername" unter "Parameter für primären zentralen Verwaltungsdienst  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> (CMS-Poolname = Servername)  <br/> |
|CMS-Maschine – IP-Adresse  <br/> |IP-Adresse für den CMS-Server (intern im Umkreisnetzwerk).  <br/> Name in INI-Datei: "IP" unter "Parameter für primären zentralen Verwaltungsdienst  <br/> ||
|Name Dateifreigabe   <br/> |Dateifreigabe Name, der auf dem CMS-Server für Skype for Business-Replikationsdaten erstellt werden soll (beispielsweise CmsFileStore).  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in INI-Datei: "CmsFileStore" unter "Parameter für primären zentralen Verwaltungsdienst  <br/> ||
|Name des Mediation-Komponenten Pools  <br/> |Poolname der Mediations Komponente Tragen Sie nur den NetBIOS-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in der INI-Datei: "Poolname" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Name der Mediations Komponente  <br/> |Komponenten Name der Mediations Komponente 1 Tragen Sie nur den NetBIOS-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in der INI-Datei: "Servername" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|IP-Adresse der Mediations Komponenten Maschine  <br/> |Interne Corpnet-IP für Mediation-Komponente (intern im Umkreisnetzwerk).  <br/> Name in der INI-Datei: "IP" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> ||
|Interner Name des Edgepools  <br/> |Name des Pools der Edge-Komponente. Tragen Sie nur den NetBIOS-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in der INI-Datei: "InternalPoolName" unter "Parameter für einen Pool von Edge-Servern"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Interner Name des Edgeservers  <br/> |Komponentenname der Edgekomponente. Geben Sie nur den NetBIOS-Namen ein; zum Erstellen des FQDN wird die AD-Domäne verwendet.   <br/> Name in der INI-Datei: "InternalServerName" unter "Parameter für einen Pool von Edge-Servern"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Interne IP des Edgeservers   <br/> |Die IP-Adresse des internen Umkreisnetzwerks der Edge-Komponente für die Kommunikation mit anderen Komponenten des Cloud Connectors.  <br/> Name in der INI-Datei: "InternalServerIPs" unter "Parameter für einen Pool von Edge-Servern"  <br/> ||
|Externer Name des Zugriffspools  <br/> |Name des Zugriffs-Edgediensts, z. B. AP. Dieser Name muss mit dem für das SSL-Zertifikat vorgesehenen Namen übereinstimmen. Geben Sie nur den NetBIOS-Namen ein. Zum Erstellen des FQDN wird der Name der SIP-Domäne verwendet. Ein externer Pool-Name wird für alle Edge-Komponenten im Pool verwendet. Pro PSTN-Website ist ein Edge-Zugriffs Pool erforderlich.  <br/> Name in der INI-Datei: "ExternalSIPPoolName" unter "Parameter für einen Pool von Edge-Servern"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> "SIP" ist reserviert und kann daher nicht als Name verwendet werden.  <br/> Der generierte FQDN-Name muss mit dem für das SSL-Zertifikat bereitgestellten Namen übereinstimmen.   <br/> |
|Externe IP des Zugriffs Rands  <br/> |Externe IP-Adresse der Edge-Komponente – entweder Public IP, wenn kein NAT verfügbar ist, oder übersetzte IP (bitte beide Adressen angeben, falls zugeordnet).  <br/> Name in der INI-Datei: "ExternalSIPIPs" unter "Parameter für einen Pool von Edge-Servern"  <br/> ||
|Mediarelay-Name  <br/> |Name des Audio/Video-Mediarelay-Edges, z. B. MR. Ein externer Poolname wird für alle Edgekomponenten in dem Pool verwendet. Pro PSTN-Website ist ein Edge Media Relay-Pool erforderlich.  <br/> Name in der INI-Datei: "ExternalMRFQDNPoolName" unter "Parameter für einen Pool von Edge-Servern"  <br/> |Höchstens 15 Zeichen. Tragen Sie nur den NetBIOS-Namen ein.  <br/> |
|Externe IP-Adresse des Medien Relais-Edge  <br/> |Derzeit wird nur eine IP-Adresse unterstützt, daher ist dies die gleiche IP-Adresse wie Access Edge, entweder öffentliche oder zugeordnete IP (Bitte geben Sie beide Adressen an, wenn Sie zugeordnet sind). Kann dieselbe Adresse wie die externe IP-Adresse der Edge-Komponente von Access-Edge sein. Hinweis Wenn Edge hinter NAT liegt, müssen Sie auch den Wert für den nächsten Parameter angeben.  <br/> Name in der INI-Datei: "ExternalMRIPs" unter "Parameter für einen Pool von Edge-Servern"  <br/> ||
|Externe IP-Adresse des Media Relay-Edge (Wenn Edge hinter NAT steht)  <br/> |Wenn sich der Edge hinter der NAT befindet, müssen Sie auch die öffentliche Adresse des NAT-Geräts angeben.  <br/> Name in der INI-Datei: "ExternalMRPublicIPs" unter "Parameter für einen Pool von Edge-Servern"  <br/> ||
|VoIP-Gateway 1 erstellen und modellieren  <br/> |Geben Sie die Marke und das Modell des SBC/Voice-Gateways an. Beachten Sie, dass Sie ein Gerät oder einen SIP-Trunk aus der Liste der getesteten Geräte unter [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)verbinden können.  <br/> ||
|VoIP-Gateway 2 erstellen und modellieren (Kopieren Sie diese Zeile, wenn Sie über mehr als zwei Gateways verfügen)  <br/> |Geben Sie die Marke und das Modell des VoIP-Gateways an. Beachten Sie, dass Sie ein Gerät aus der Liste der getesteten Geräte [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)unter verbinden können.  <br/> ||
|Name des VoIP-Gateways 1  <br/> |Wird zusammen mit der AD-Domäne verwendet, um den FQDN des Computers zu erstellen. Erforderlich, falls eine TLS-Verbindung zwischen der Vermittlungskomponente und dem VoIP-Gateway hergestellt werden soll. Wenn Sie nicht beabsichtigen, den FQDN zu verwenden, beispielsweise ist TLS nicht erforderlich, oder Voice Gateway unterstützt keine Verbindung mithilfe von FQDN (nur IP) – geben Sie bitte an.  <br/> ||
|Name des Voice Gateway 2 (Kopieren Sie diese Zeile, wenn Sie über mehr als zwei Gateways verfügen)  <br/> |Wird zusammen mit der AD-Domäne verwendet, um den FQDN des Computers zu erstellen. Erforderlich, falls eine TLS-Verbindung zwischen Vermittlungskomponente und VoIP-Gateway hergestellt werden soll. Wenn Sie nicht beabsichtigen, den FQDN zu verwenden, beispielsweise ist TLS nicht erforderlich, oder Voice Gateway unterstützt keine Verbindung mithilfe von FQDN (nur IP) – geben Sie bitte an.  <br/> ||
|VoIP-Gateway 1-IP-Adresse  <br/> |IP-Adresse des VoIP-Gateways  <br/> ||
|IP-Adresse des VoIP-Gateways 2 (Kopieren Sie diese Zeile, wenn Sie über mehr als zwei Gateways verfügen)  <br/> |IP-Adresse des VoIP-Gateways  <br/> ||
|Voice Gateway 1 Port # (Kopieren Sie diese Zeile, wenn Sie über mehr als zwei Gateways verfügen)  <br/> |Nummer des Ports, den der VoIP-Gateway-SIP-Trunk überwacht, z. B. 5060  <br/> ||
|VoIP-Gateway 2-Port #  <br/> |Nummer des Ports, den der VoIP-Gateway-SIP-Trunk überwacht, z. B. 5060  <br/> ||
|Voice Gateway 1-Protokoll für SIP-Datenverkehr  <br/> |TCP oder TLS  <br/> ||
|Voice Gateway 2-Protokoll für SIP-Datenverkehr (Kopieren Sie diese Zeile, wenn Sie über mehr als zwei Gateways verfügen)  <br/> |TCP oder TLS  <br/> ||
|Externer Medienportbereich für Datenverkehr von der bzw. zur Edgekomponente  <br/> |TCP/UDP-Portbereich für Mediendatenverkehr an und von der externen Schnittstelle von Edge. Muss immer von 50 000 beginnen. Weitere Informationen finden Sie unter "Ports and Protocols".  <br/> |50000 - 59 999  <br/> |
|Medienportbereich, der über die interne Firewall an/von der Mediations Komponente kommuniziert  <br/> |UDP-Portbereich, der von der Mediations Komponente für die Kommunikation mit Clients und Gateways verwendet wird (Empfehlung 4 Ports pro Anruf).  <br/> ||
|Medienportbereich für die Kommunikation mit/über den Skype for Business-Client über eine interne Firewall  <br/> |Beachten Sie bei der Planung, dass dies nicht geändert werden kann. Ports müssen in der internen Firewall geöffnet werden, um zwischen Skype for Business-Clients innerhalb des internen Netzwerks und der Mediations Komponente zu kommunizieren.  <br/> |50000–50019  <br/> |
|Kennwort für das öffentliche Zertifikat  <br/> |Muss im Skript angegeben sein  <br/> ||
|Administratorkennwort für den sicheren Modus  <br/> Nur Version 1.4.2  <br/> |Administratorkennwort für den sicheren Modus und die CC-Domäne  <br/> ||
|Cloud Connector-Domänen Administrator Kennwort  <br/> Nur Version 1.4.2  <br/> |Kennwort für den Cloud Connector-Domänen Administrator (anders als ihre Produktionsdomäne). Der Benutzername lautet „Administrator“. Sie können den Benutzernamen nicht ändern.  <br/> ||
|Administratorkennwort virtuelle Maschinen  <br/> Nur Version 1.4.2  <br/> |Wird im Zuge der Bereitstellung verwendet, um das Verwaltungsnetzwerk zu konfigurieren.  <br/> Der Benutzername lautet „Administrator“. Sie können den Benutzernamen nicht ändern.   <br/> ||
|CABackupFile  <br/> Version 2.0 und höher  <br/> |Wird verwendet, um den Zertifizierungsstellendienst vom Active Directory-Server in einer Datei zu speichern, wenn mehrere Appliances auf einer Cloud Connector-Website bereitgestellt werden. Achten Sie darauf, für alle Appliances an einem Cloud Connector-Standort das gleiche Kennwort zu verwenden, damit die CA-Sicherungsdatei auf neu hinzugefügten Appliances erfolgreich importiert werden kann.  <br/> ||
|Nur Version 2.0  <br/> Version 2.0 und höher   <br/> |Wird für den Cloud Connector-Verwaltungsdienst verwendet und benötigt Zugriff auf das Cloud Connector-Standortverzeichnis. Achten Sie darauf, für alle Appliances an einem Cloud Connector-Standort das gleiche Kennwort zu verwenden.   <br/> ||
|Office 365-Mandantenadministrator  <br/> | Das Konto wird von Cloud Connector verwendet, um Mandanteneinstellungen für Cloud Connector zu aktualisieren und zu verwalten: <br/>  Version 2,0 und höher: Anmeldeinformationen für ein dediziertes Office 365-Konto mit den Skype for Business-Administrator Rechten. <br/>  Versionen vor 2.0: Anmeldeinformationen für ein dediziertes Office 365-Konto mit den Rechten eines globalen Mandantenadministrators <br/> ||
|Aktivieren von REFER-Unterstützung  <br/> |Dadurch wird festgelegt, ob „SIP REFER-Unterstützung“ in der Trunk-Konfiguration zu Ihrer IP/PBX aktiviert oder deaktiviert ist. Der Standardwert ist „TRUE“ (WAHR). Sofern Ihr IP/PBX-Gateway „REFER-Unterstützung“ unterstützt, belassen Sie die Einstellung auf „WAHR“. Wenn nicht, muss dieser Wert in „FALSE“ (FALSCH) geändert werden. Wenn Sie nicht sicher sind, ob Ihr Gateway Refer unterstützt, lesen Sie [qualifizierte IP-PBX-Anlagen und Gateways](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Version 2.0 und höher  <br/> |Mit dem Standardwert "true", wenn ausgehende Anrufe nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, werden Sie an das nächste verfügbare Gateway weitergeleitet; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.  <br/> Wenn in einer Organisation langsame Netzwerke und Gatewayreaktionen vorliegen oder der Aufbau von Anrufen mehr als zehn Sekunden in Anspruch nimmt, kann dies dazu führen, dass Anrufe unnötig getrennt werden.  <br/> Wenn Anrufe in bestimmte Länder/Regionen wie zum Beispiel in die Vereinigten Arabischen Emirate oder nach Afghanistan getätigt werden, kann der Anrufaufbau länger als zehn Sekunden dauern. Wenn vergleichbare Probleme auftreten, müssen Sie den Wert in „False“ ändern. Denken Sie daran, die entsprechende Einstellung auf dem verbundenen SBC oder Gateway zu ändern.  <br/> Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „True“.  <br/> ||
|ForwardCallHistory  <br/> Version 2.0 und höher  <br/> | Dieser Parameter wird verwendet, um SIP-Header zu aktivieren, mit deren Hilfe der anfängliche Anrufer in Szenarien mit gleichzeitigem Klingeln, Anrufweiterleitung und Anrufdurchstellung gemeldet wird. Wenn Sie den Parameter auf „True“ festlegen, werden zwei SIP-Header aktiviert:<br/>  Referred-By <br/>  Referred-By <br/>  Der Header "History-Info" wird für das erneute Ausrichten von SIP-Anforderungen und "bereitstellen (s) eines Standardmechanismus zum Erfassen der Informationen zum Anforderungsverlauf verwendet, um eine Vielzahl von Diensten für Netzwerke und Endbenutzer zu ermöglichen" ([RFC 4244-Abschnitt 1,1](http://www.ietf.org/rfc/rfc4244.txt)). Für die Cloud Connector-Trunkschnittstellen wird diese in Szenarien mit gleichzeitigem Klingeln und Anrufweiterleitung verwendet.  <br/>  Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „False“.<br/> ||
|PAI weiterleiten  <br/> Version 2.0 und höher  <br/> |PAI ist eine private Erweiterung von SIP, mit der SIP-Server die Identität von authentifizierten Benutzern bestätigen können. Der SIP-Trunkanbieter kann PAI zu Abrechnungszwecken verwenden, falls keine „History-Info“- und „Referred-By“-Header vorhanden sind. Wenn Forward P-Asserted-Identity in der Konfiguration aktiviert ist, leitet der Vermittlungs Server Pai-Header mit &amp; SIP Tel URI vom Cloud-Connector auf den SIP-Stamm weiter. Der Vermittlungs Server leitet Pai-Header mit den E &amp; . 164-Nummern von Tel URI weiter, die nur über den SIP-Trunk an Cloud Connector empfangen werden. Außerdem leitet der Vermittlungsserver alle empfangenen „Privacy“-Header unabhängig von der Richtung weiter. Wenn die vom Vermittlungs Server gesendete SIP-Anforderung einen Datenschutz Header des Formulars "Datenschutz: ID" in Verbindung mit dem Pai-Header enthält, sollte die Assertions Identität außerhalb der Netzwerk Vertrauensstellungs Domäne privat aufbewahrt werden.  <br/> Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „False“.  <br/> ||

### <a name="certificate-requirements"></a>Zertifikatanforderungen
<a name="BKMK_Certs"> </a>

Für jede Edgekomponente wird ein Zertifikat von einer öffentlichen Zertifizierungsstelle benötigt. Die Zertifikate müssen mit einem exportierbaren privaten Schlüssel versehen sein, der zwischen Edgekomponenten kopiert wird. Um die Zertifikatanforderungen zu erfüllen, müssen Sie sich für eine der folgenden Optionen entscheiden und den Antragstellernamen (Subject Name, SN) sowie den alternativen Antragstellernamen (Subject Alternative Name, SAN) für das Zertifikat angeben.

 **Wenn Sie über eine einzige SIP-Domäne verfügen:**

- **Option 1.** Der Antragstellername muss den Poolnamen enthalten, den Sie den Edgekomponenten zugewiesen haben. Beachten Sie, dass der Name des Antragstellers nicht SIP.sipdomain.com werden kann, da dieser Name für die Online-Komponente Skype for Business Edge reserviert ist. Der alternative Antragstellername muss „sip.sipdomain.com“ enthalten sowie den Namen des Zugriffs-Edgepools:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Option 2.** Wenn Sie ein einzelnes Platzhalterzertifikat auf allen Edge-Pool Servern verwenden möchten, die Sie bereitstellen, können Sie einen Platzhalter- \*San-Eintrag von sipdomain.com anstelle des Namens des Edge-Pools im Zertifikat verwenden. Der Antragstellername kann der Zugriffs-Edgepoolname eines der bereitgestellten Edgepools sein:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Sie dürfen keinen externen DNS-Eintrag für SIP erstellen. \<sipdomain\>. com, da dieser Name zur Office 365-Bereitstellung gehört.

> [!NOTE]
> Wenn Sie ein einzelnes Zertifikat für alle in Ihrer Organisation bereitgestellten Edgepools verwenden möchten und kein Zertifikat mit Platzhaltern wie in Option 2 definiert nutzen können, dann müssen Sie den FQDN für alle bereitgestellten Edgepools im Namen für den alternativen Antragstellernamen in das Zertifikat einschließen. 

 **Wenn Sie über mehrere SIP-Domänen verfügen:**

Sie müssen für jede SIP-Domäne „sip.sipdomain.com“ sowie den Namen der Zugriffs-Edgepools für jede Domäne hinzufügen (dies kann ein einzelner physischer Pool mit unterschiedlichen Namen sein). Hier ist ein Beispiel für SN- und SAN-Einträge in einem Szenario mit mehreren SIP-Domänen:

- **Option 1.** Der Name des Antragstellers muss den Namen des Pools enthalten, den Sie für Edge-Komponenten zugewiesen haben. Beachten Sie, dass der Name des Antragstellers nicht SIP.sipdomain.com werden kann, da dieser Name für die Online-Komponente Skype for Business Edge reserviert ist. Der alternative Antragstellername muss „sip.sipdomain.com“ enthalten sowie den Namen des Zugriffs-Edgepools:

  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Option 2.</strong> Wenn Sie ein einzelnes Platzhalterzertifikat auf allen Edge-Pool Servern verwenden möchten, die Sie bereitstellen, können Sie einen Platzhalter- \*San-Eintrag von sipdomain.com anstelle des Namens des Edge-Pools im Zertifikat verwenden. Der Antragstellername kann der Zugriffs-Edgepoolname eines der bereitgestellten Edgepools sein:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Sie dürfen keinen externen DNS-Eintrag für SIP erstellen. \<sipdomain\>. com, da dieser Name zur Office 365-Bereitstellung gehört.

Für die Bereitstellung können Sie folgende Tabelle verwenden:

|**Option**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|Welche Option möchten Sie für Ihre Bereitstellung verwenden?  <br/> |Option 1 oder 2  <br/> ||
|SN  <br/> |Geben Sie den SN für Ihr Zertifikat an.  <br/> ||
|SAN  <br/> |Geben Sie den SAN für Ihr Zertifikat an.  <br/> ||

Wenn Sie zwischen dem Gateway und dem Vermittlungsserver TLS verwenden, müssen Sie sich das Stammzertifikat oder die vollständige Zertifikatkette für das Zertifikat besorgen, das dem Gateway zugewiesen ist.

## <a name="dial-plan-considerations"></a>Hinweise zum Wählplan
<a name="BKMK_DailPlan"> </a>

Sie müssen für Cloud Connector einen Onlinewählplan verwenden. Weitere Informationen zum Konfigurieren von Online-Wählplänen finden Sie unter [Was sind Wählpläne?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Überlegungen zur hohen Verfügbarkeit
<a name="BKMK_HA"> </a>

Wenn Sie Cloud Connector Edition für eine höhere Verfügbarkeit bereitstellen, stellen Sie mindestens zwei Appliances bereit, die sich gegenseitig als Backups fungieren. Jede Appliance besteht aus vier Komponenten: Edge, Mediation, Central Management Store (CMS) und Domänencontroller.

Wenn eine Komponente innerhalb einer Appliance ausfällt, kann Cloud Connector Edition weiterhin Anrufe verarbeiten, Sie müssen jedoch Folgendes berücksichtigen:

- **Überlegungen zu Vermittlungs-, CMS- und Domänencontrollerkomponente**

    Angenommen, die CMS-oder Domänencontroller Komponente in einer Appliance sinkt. Die Appliance kann weiterhin eingehende und ausgehende Anrufe verarbeiten, doch wenn Sie eine Mediations Komponente neu starten, wenn der Domänencontroller oder die CMS-Komponente nicht erreichbar ist, funktioniert die Mediation nicht. Das gleiche gilt für den Neustart der CMS-Komponente, wenn der Domänencontroller ausgefallen ist.

    **Empfehlung:** Überprüfen Sie vor dem Neustart der Komponenten die Verfügbarkeit der anderen Komponenten in der Appliance.

- **Überlegungen zur Edgekomponente**

    Wenn die Edgekomponente einer Appliance nicht verfügbar ist, unterscheidet sich das Verhalten für eingehende und ausgehende Anrufe wie folgt:

  - Ausgehender **Anruf**– ein Anruf von Ihrem Benutzer im Internet zu einem PSTN-Netzwerk.

    Der Mechanismus zur Anrufverteilung in der Cloud stellt fest, dass eine Edgekomponente ausgefallen ist, und leitet alle Anrufe an eine andere Appliance weiter. Der ausgehende Anruf ist also erfolgreich.

  - Eingehender **Anruf**– ein Anruf vom PSTN-Netzwerk an einen Benutzer, der sich entweder in einem lokalen Netzwerk oder im Internet befindet.

     Wenn die Edgekomponente der Appliance, die den Anruf angenommen hat, nicht funktioniert, sind eingehende Anrufe an diese Appliance nicht erfolgreich, weil die Vermittlungskomponente den Anruf nicht an die Edgekomponente der anderen Appliance umleiten kann.

    **Empfehlung:** Ein Überwachungssystem eingerichtet haben. Nachdem Sie eine Fehlfunktion der Edge-Komponente festgestellt haben, fahren Sie alle Komponenten in der Appliance herunter, wobei die Edge-Komponente nicht verfügbar ist.

## <a name="cloud-connector-media-flow"></a>Cloud Connector-Mediendatenverkehr
<a name="BKMK_MediaFlow"> </a>

Die folgenden Diagramme erläutern den Fluss eines ausgehenden und eingehenden Anrufs über die Cloud Connector Edition. Die Diagramme veranschaulichen, wie eine Verbindung hergestellt wird.

Im ersten Diagramm tätigt ein interner Nutzer einen Anruf und geht dabei wie folgt vor:

1. Dave – ein Benutzer, der online verwaltet wird, sich jetzt aber im internen Netzwerk befindet – ruft einen externen Festnetzbenutzer an.

2. SIP-Traffic-Routen zu Skype for Business Online.

3. Skype for Business Online führt eine Reverse-Number-Suche der Nummer durch. Die Suche nach umgekehrter Zahl schlägt fehl, da diese Nummer keiner beliebigen Person in der Skype for Business-Organisation gehört.

4. Der Anruf wird an die Edgekomponente weitergeleitet (zunächst SIP und Mediendatenverkehr über Online Edge; die Mediendaten gelangen dann über die interne Firewall zur Vermittlungskomponente).

5. Sofern diese Route vorhanden ist, überträgt die Edgekomponente die Daten an die Vermittlungskomponente im Umkreisnetzwerk.

6. Die Vermittlungskomponente leitet den Datenverkehr schließlich an das PSTN-Gateway weiter.

![Ausgehender Mediendatenfluss für Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Im nächsten Diagramm erhält ein interner Benutzer einen Anruf:

1. Das PSTN-Gateway empfängt einen Anruf für Benutzer Dave, der online verwaltet wird, sich jetzt aber im internen Netzwerk befindet.

2. Der SIP-Datenverkehr wird an die Vermittlungskomponente weitergeleitet.

3. Die Mediations Komponente sendet SIP-Datenverkehr an die Edge-Komponente und geht dann zu Skype for Business Online.

4. Skype for Business Online führt eine Reverse-Number-Suche der Nummer durch und stellt fest, dass es sich um einen Benutzer Dave handelt.

5. Die SIP-Signale werden an alle Geräte von Dave gesendet.

6. Der Mediendatenverkehr zwischen Gateway und Vermittlungskomponente sowie zwischen Vermittlungskomponente und Endpunkt wird hergestellt.

![Eingehender Mediendatenfluss für Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Überwachung und Problembehandlung
<a name="BKMK_Monitor"> </a>

Der Mechanismus für Überwachung und Problembehandlung wird mit jeder Cloud Connector-Appliance automatisch installiert. Der Mechanismus erkennt die folgenden Ereignisse:

- Eine oder mehrere virtuelle Maschinen einer Cloud Connector-Appliance sind nicht mit einem internen Switch oder einem virtuellen Internetswitch verbunden.

- Eine oder mehrere virtuelle Maschinen einer Cloud Connector-Appliance wurden gespeichert oder beendet.

- Dienste werden nicht ausgeführt.

  Wenn eines der folgenden Ereignisse erkannt wird, wird die gesamte Cloud Connector-Appliance entladen und als offline gekennzeichnet, um zu verhindern, dass Anrufe an eine nicht funktionierende Appliance durchgeführt werden. Cloud Connector-Features für die automatische Wiederherstellung werden anschließend Dienste wiederherstellen und die Appliance als Online kennzeichnen. Wenn die automatische Wiederherstellung aus irgendeinem Grund fehlschlägt, lesen Sie [Behandeln von Problemen mit der Cloud Connector-Bereitstellung](troubleshoot-your-cloud-connector-deployment.md).

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

Cloud Connector 2.1 und höher unterstützt das Überwachen von Cloud Connector mithilfe von Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md).

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_MoreInfo"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:

- [Microsoft-Telefonielösungen](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Planen der Medienumgehung in der Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Bereitstellen der medienumgehung in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)


