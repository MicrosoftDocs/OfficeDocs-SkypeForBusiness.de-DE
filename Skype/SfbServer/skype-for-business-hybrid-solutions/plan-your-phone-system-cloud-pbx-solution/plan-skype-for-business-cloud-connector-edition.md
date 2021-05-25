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
description: Hier finden Sie Skype for Business Cloud Connector Edition, eine Reihe von verpackten virtuellen Computern (VMs), die lokale PSTN-Verbindungen mit Telefonsystem (Cloud PBX) implementieren.
ms.openlocfilehash: 4d4573b89f743ea8224905687869cb607a85c00d
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628804"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planen von Skype for Business Cloud Connector Edition

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückziehen. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams [Direct Routing verbinden.](/MicrosoftTeams/direct-routing-landing-page)

Hier finden Sie Skype for Business Cloud Connector Edition, eine Reihe von verpackten virtuellen Computern (VMs), die lokale PSTN-Verbindungen mit Telefonsystem (Cloud PBX) implementieren.

Cloud Connector Edition ist möglicherweise die richtige Lösung für Ihre Organisation, wenn Sie noch nicht über einen vorhandenen Lync Server oder eine Skype for Business Server verfügen. Wenn Sie noch untersuchen, Telefonsystem Lösung für Ihr Unternehmen richtig ist, lesen Sie [Microsoft Telephony Solutions](/microsoftteams/cloud-voice-landing-page).

In diesem Dokument werden die Cloud Connector Edition-Anforderungen und unterstützten Topologien beschrieben, und Sie können Ihre Cloud Connector Edition-Bereitstellung planen. Lesen Sie diesen Artikel unbedingt, bevor Sie Ihre Cloud Connector-Umgebung konfigurieren. Wenn Sie bereit sind, Cloud Connector Edition zu bereitstellen und zu konfigurieren, lesen Sie Konfigurieren und [Verwalten Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

Cloud Connector Edition 2.1 ist jetzt verfügbar. Wenn Sie noch kein Upgrade auf 2.1 durchgeführt haben, lesen Sie [Upgrade auf eine neue Version von Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Die Installationsdatei finden Sie unter [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .

> [!NOTE]
> Microsoft unterstützt die vorherige Version von Cloud Connector Edition 60 Tage nach der Veröffentlichung einer neuen Version. Microsoft unterstützt Version 2.0.1 60 Tage nach version 2.1, um Ihnen Zeit zum Upgrade zu geben. Alle Versionen vor 2.0.1 werden nicht mehr unterstützt.

Cloud Connector Edition ist ein Hybridangebot, das aus einer Reihe von verpackten virtuellen Computern (VMs) besteht, die lokale PSTN-Verbindungen mit Telefonsystem. Durch die Bereitstellung einer minimalen Skype for Business Server-Topologie in einer virtualisierten Umgebung können Benutzer in Ihrer Organisation, die in der Cloud gespeichert sind, Nebenstellendienste aus der Microsoft-Cloud empfangen, die PSTN-Konnektivität wird jedoch über die vorhandene lokale Voiceinfrastruktur bereitgestellt.

![Topologiediagramm mit dem Cloud PBX Gateway, das Cloud PBX mit einer lokalen Bereitstellung von Skype for Business.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Da Sie mit Cloud Connector Telefonsystem-Dienste in Ihre vorhandene Telefonieumgebung integrieren können , z. B. Nebenstellenanlagen, analoge Geräte und Call Center, können Sie eine phasenweise Migration von Ihrer vorhandenen Telefonielösung zu Telefonsystem.

Angenommen, Ihr Unternehmen verfügt über ein ausgeklügeltes Call Center mit bestimmten Funktionen, Telefonsystem nicht zur Verfügung stellt. Sie können wählen, dass Call Center-Benutzer die vorhandene Lösung verlassen, andere Benutzer jedoch in die Telefonsystem.

Cloud Connector bietet Routing zwischen den benutzern, die lokal und online heimisch sind, und Sie können ihren eigenen PSTN-Anbieter mit Telefonsystem.

Berücksichtigen Sie beim Planen der Cloud Connector Edition-Bereitstellung Folgendes:

- Um Cloud Connector zu verwenden, um Cloud-Voice-Lösungen zu nutzen, müssen Sie sich für eine Microsoft 365- oder Office 365-Organisation registrieren, die Telefonsystem. Wenn Sie noch nicht über eine Microsoft 365 oder Office 365 verfügen, erfahren Sie, wie Sie sich hier registrieren: [Microsoft 365 business](https://products.office.com/business/office). Beachten Sie, dass Sie sich für einen Plan registrieren müssen, der Skype for Business enthält.

- Um Cloud Connector-Appliances beim Skype for Business Online-Dienst zu registrieren und verschiedene Cmdlets ausführen zu können, erfordert Cloud Connector 2.0 und höher ein dediziertes Microsoft 365- oder Office 365-Konto mit den Skype for Business-Mandantenadministratorrechten. Cloud Connector-Versionen vor 2.0 erfordern ein dediziertes Microsoft 365 oder Office 365 mit mandantenbasierten globalen Administratorrechten.

- Cloud Connector erfordert keine vollständige lokale Skype for Business Server Bereitstellung.

    Derzeit kann Cloud Connector nicht mit Lync- oder Skype for Business lokalen Servern koexistent sein. Wenn Sie vorhandene Lync- oder Skype for Business-Benutzer in Microsoft 365 verschieben und weiterhin lokale Telefonie für Ihre Benutzer bereitstellen möchten, sollten Sie Telefonsystem lokale Konnektivität mithilfe einer vorhandenen Skype for Business Server in Betracht ziehen. Weitere Informationen finden Sie unter [Plan your Telefonsystem (Cloud PBX) solution](/microsoftteams/cloud-voice-landing-page.md) und Plan Telefonsystem with [on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Wenn Sie eine vorherige Skype for Business- oder Lync Server-Bereitstellung hatten und das Schema erweitert haben, müssen Sie das Schema für die Cloud Connector-Bereitstellung nicht bereinigen, solange Sie alle Skype for Business- oder Lync Server-Komponenten aus Ihrer Umgebung entfernt haben.

- Ihre Benutzer werden online homed.

- Wenn Ihre Organisation die Verzeichnissynchronisierung (DirSync) konfiguriert hat, müssen alle Konten von Benutzern, die für Hybridstimmen geplant sind, zuerst in Ihrer lokalen Bereitstellung erstellt und dann mit der Cloud synchronisiert werden.

- Sie können ihren aktuellen PSTN-Netzbetreiber bei Bedarf behalten.

- Wenn Sie Benutzern, die auf Cloud Connector gehostet werden, Einwahlkonferenzen bereitstellen möchten, können Sie eine PstN-Konferenzlizenz erwerben oder bezahlen, während Sie ein Audiokonferenzangebot von Microsoft nutzen.

- Die Lizenz für Audiokonferenzen (oder die Zahlung während des Angebots) ist auch für Anrufeskalation erforderlich. Wenn ein Skype for Business einen Anruf von einem externen PSTN-Benutzer empfängt und einen weiteren Teilnehmer zu diesem Anruf hinzufügen möchte (eskalieren Sie den Anruf zu einer Konferenz), wird die Eskalation über den Microsoft Audio Conferencing Service durchgeführt.

- Cloud Connector 2.0 und höher unterstützt jetzt die Medienumgehung. Mit der Medienumgehung kann ein Client Medien direkt an das Public Switched Telephone Network (PSTN) des nächsten Hops senden – ein Gateway oder einen Session Border Controller (SBC) – und die Cloud Connector Edition-Komponente aus dem Medienpfad entfernen. Weitere Informationen finden Sie unter [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2.1 und höher unterstützt die Überwachung von Cloud Connector mithilfe der Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- Cloud Connector ist in allen Ländern verfügbar, in denen Office 365 Enterprise E5 verfügbar ist.

Dieser Artikel enthält die folgenden Abschnitte:

- [Cloud Connector Edition-Komponenten](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Cloud Connector Edition-Topologien](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Anforderungen für die Bereitstellung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informationen, die Sie vor der Bereitstellung sammeln müssen](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Überlegungen zu Wählplan](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Überlegungen zur hohen Verfügbarkeit](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Cloud Connector-Medienfluss](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Überwachung und Problembehandlung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Weitere Informationen](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Cloud Connector Edition-Komponenten
<a name="BKMK_Components"> </a>

Mit Cloud Connector Edition stellen Sie eine Reihe von verpackten VMs zur Bereitstellung, die eine minimale Skype for Business Server-Topologie enthalten – bestehend aus einer Edgekomponente, einer Vermittlungskomponente und einer CmS-Rolle (Central Management Store). Außerdem installieren Sie einen Domänencontroller, der für die interne Funktionsweise von Cloud Connector erforderlich ist. Diese Dienste sind für die Hybridbereitstellung mit Microsoft 365 oder Office 365 konfiguriert, die Skype for Business Onlinedienste umfasst.

![Cloud Connector Edition-Komponenten](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Cloud Connector-Komponenten bieten die folgenden Funktionen:

- **Edgekomponente** – Die Kommunikation zwischen der lokalen Topologie und den Onlinediensten wird über die Edgekomponente, die die folgenden Komponenten umfasst, verwendet:

  - **Access Edge** – Bietet SIP-Routing zwischen der lokalen Bereitstellung und Skype for Business Online.

  - **Medienrelais** – Ermöglicht das Routing von Medien zwischen der Vermittlungskomponente und anderen Medienendpunkten.

  - **Media Relay Authentication /MRAS** – Generiert Token für den Zugriff auf Medienrelais.

- **Ausgehendes Routing** : Bietet einen Lastenausgleich für den Sprachdatenverkehr zwischen Gateways oder SBCs, die mit einer Cloud Connector-Appliance verbunden sind. Anrufe werden gleichmäßig auf alle Gateways oder SBCs aufgeteilt, die mit der Cloud Connector-Appliance verbunden sind.

    Ermöglicht das Routing zu Gateways basierend auf Richtlinien. Es werden nur globale Richtlinien unterstützt, die auf zielbasierten (ausgehenden) PSTN-Nummern basieren.

- **Zentrale Store (CMS)-Rolle** – Enthält den Konfigurationsspeicher für die Topologiekomponenten, einschließlich CMS File Transfer.

- **CmS Store (Central Management Store)** – Synchronisiert Konfigurationsinformationen aus der globalen CMS DB auf dem CMS-Rollenserver.

- **Domänencontroller** : Cloud Connector Active Directory Domain Services zum Speichern aller globalen Einstellungen und Gruppen, die für die Bereitstellung von Cloud Connector-Komponenten erforderlich sind. Für jede Cloud Connector-Appliance wird eine Gesamtstruktur erstellt. Der Domänencontroller darf keine Verbindungen mit dem Produktions-Active Directory haben. Zu den Active Directory-Diensten gehören:

  - Active Directory Domain Services

  - Active Directory-Zertifikatdienste zum Ausstellen interner Zertifikate

- **Vermittlungskomponente** – Implementiert SIP- und Mediengatewayzuordnungsprotokoll zwischen Skype for Business und PSTN-Gateways. Enthält ein CMS-Replikat, das die Konfiguration aus der globalen CMS-Datenbank synchronisiert.

## <a name="cloud-connector-edition-topologies"></a>Cloud Connector Edition-Topologien
<a name="BKMK_Topologies"> </a>

Im Sinne dieser Diskussion beziehen wir uns auf PSTN-Websites. Ein PSTN-Standort ist eine Kombination aus Cloud Connector-Appliances, die am gleichen Standort bereitgestellt werden und mit gemeinsamen PSTN-Gateways verbunden sind. Mit PSTN-Websites können Sie:

- Stellen Sie Verbindungen zu Gateways zur Verfügung, die Ihren Benutzern am nächsten sind.

- Ermöglichen Sie Skalierbarkeit, indem Sie mehrere Cloud Connector-Appliances an einem oder mehreren PSTN-Standorten bereitstellen.

- Ermöglichen Sie hohe Verfügbarkeit, indem Sie mehrere Cloud Connector-Appliances an einem einzelnen PSTN-Standort bereitstellen.

In diesem Thema werden PSTN-Websites beschrieben. Weitere Informationen zum Planen Ihrer PSTN-Standorte finden Sie unter [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Sie können die folgenden Cloud Connector-Topologien bereitstellen:

- Eine einzelne Cloud Connector Edition-Appliance pro PSTN-Standort. Diese Topologie wird nur zu Auswertungszwecken empfohlen, da sie keine hohe Verfügbarkeit bietet.

- Mehrere Cloud Connector Edition-Appliances pro PSTN-Standort, um hohe Verfügbarkeit zu bieten.

- Mehrere PSTN-Standorte mit mehreren Cloud Connector Edition-Appliances, um Skalierbarkeit bei hoher Verfügbarkeit zu gewährleisten. Sie können bis zu 200 Websites bereitstellen.

Berücksichtigen Sie bei der Planung Ihrer Topologie Folgendes:

- Mit Cloud Connector 2.0 und höher kann ein PSTN-Standort über bis zu 16 Cloud Connector-Appliances verfügen. Frühere Versionen unterstützen bis zu vier Appliances pro Standort.

- Es gibt zwei Arten von Hardwarekonfigurationen, die mit Cloud Connector getestet werden:

  - Die größere Version kann große Mengen gleichzeitiger Anrufe behandeln und wird in allen Arten von Produktionsumgebungen unterstützt.

  - Die kleinere Version ist für die Ausführung auf Hardware am unteren Ende vorgesehen und kann zu Auswertungszwecken oder für Websites mit geringen Anrufvolumina verwendet werden. Wenn Sie eine kleinere Version von Cloud Connector bereitstellen, müssen Sie weiterhin die Hardwareanforderungen der Produktionsklasse berücksichtigen (z. B. duale Stromversorgungen).

- Wenn Sie Cloud Connector Version 2.0 oder höher verwenden und die maximale Konfiguration von 16 Appliances (mit größerer Hardware) bereitstellen, kann Ihr PSTN-Standort bis zu 8.000 gleichzeitige Anrufe verarbeiten. Wenn Sie die kleinere Version bereitstellen, ist der unterstützte Grenzwert 800.

    Sie müssen auch einige Appliances für hohe Verfügbarkeit widmen. Die minimale Empfehlung ist, dass eine Appliance für hohe Verfügbarkeit reserviert werden sollte.

  - Wenn Sie eine 15+1-Konfiguration bereitstellen, kann Ihr PSTN-Standort mit Version 2 bis zu 7.500 gleichzeitige Anrufe verarbeiten.

  - Wenn Sie über eine frühere Version verfügen und die maximal 3 + 1-Konfiguration (mit größerer Hardware) bereitstellen, kann Ihr PSTN-Standort bis zu 1.500 gleichzeitige Anrufe verarbeiten. Wenn Sie die kleinere Version bereitstellen, ist der unterstützte Grenzwert 150.

-  Wenn Sie mehr Anrufe pro PSTN-Standort benötigen, können Sie die Skalierung hochskalieren, indem Sie zusätzliche PSTN-Standorte am gleichen Standort bereitstellen.

> [!NOTE]
> Sofern nicht erwähnt, wird in den folgenden Diagrammen und Beispielen davon ausgegangen, dass die größere Version von Cloud Connector verwendet wird.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Einzelne Cloud Connector-Appliance an einem einzelnen PSTN-Standort

Das folgende Diagramm zeigt eine einzelne Cloud Connector Edition-Appliance an einem einzelnen PSTN-Standort. Beachten Sie, dass Cloud Connector aus vier virtuellen Computer besteht, die aus Sicherheitsgründen auf einem physischen Hostcomputer innerhalb eines Umkreisnetzwerks installiert sind.

![Ein Cloudconnector mit einem PSTN-Standort](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Mehrere Cloud Connector-Appliances an einem einzelnen PSTN-Standort

 Aus Gründen der Skalierbarkeit und hohen Verfügbarkeit können Sie mehrere Cloud Connector Editionen an einem einzelnen PSTN-Standort verwenden, wie im folgenden Diagramm dargestellt. Berücksichtigen Sie dabei Folgendes:

- Anrufe werden in zufälliger Reihenfolge zwischen CloudConnectors in einem Pool verteilt.

- Aus Gründen der Kapazitätsplanung müssen Sie die Möglichkeit in Betracht ziehen, die Last zu verarbeiten, wenn ein oder mehrere CloudConnectors offline gehen, basierend auf den folgenden Berechnungen:

  - **N+1-Felder.** Für die größere Version von Cloud Connector unterstützen N+1-Boxen 500 N gleichzeitige Anrufe mit einer Verfügbarkeit von \* 99,8 %.

    Für die kleinere Version von Cloud Connector unterstützen N+1-Boxen 50 N gleichzeitige Anrufe mit einer Verfügbarkeit von \* 99,8 %.

  - **N+2-Felder.** Für die größere Version von Cloud Connector unterstützen N+2-Boxen 500 N gleichzeitige Anrufe mit einer Verfügbarkeit von \* 99,9 %.

    Für die kleinere Version von Cloud Connector unterstützen N+2-Boxen 50 N gleichzeitige Anrufe mit einer Verfügbarkeit von \* 99,9 %.

![Zwei Cloudconnectors innerhalb eines PSTN-Standorts](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Mehrere PSTN-Standorte mit einem oder mehreren CloudConnectors pro Standort

Sie können auch mehrere PSTN-Standorte mit einer oder mehreren Cloud Connector Editionen an jedem Standort auswählen. Wenn Ihr PSTN-Standort die Grenze für gleichzeitige Anrufe erreicht, können Sie einen weiteren PSTN-Standort hinzufügen, um die Last zu verarbeiten.

Mit mehreren PSTN-Standorten können Sie auch Verbindungen zu Gateways bereitstellen, die Ihren Benutzern am nächsten sind. Angenommen, Sie verfügen über PSTN-Gateways in Seattle und Amsterdam. Sie können zwei PSTN-Standorte bereitstellen – einen in Seattle, einen in Amsterdam – und Benutzern die Verwendung des PSTN-Standorts zuweisen, der ihnen am nächsten ist. Benutzer aus Seattle werden an den PstN-Standort und die Gateways von Seattle geroutet, während Benutzer in Amsterdam an den Amsterdamer PSTN-Standort und die Gateways geroutet werden:

![Cloud Connector Edition innerhalb von 2 PSTN-Standorten](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Anforderungen für die Bereitstellung
<a name="BKMK_Requirements"> </a>

Stellen Sie vor der Bereitstellung von Cloud Connector Edition folgendes für Ihre Umgebung sicher:

- **Für den Hostcomputer –** Cloud Connector-VMs müssen auf dedizierter Hardware bereitgestellt werden, die Windows Server 2012 R2 Datacenter Edition (Englisch) ausgeführt wird und die Hyper-V-Rolle aktiviert ist.

    Für Version 2.0 und höher muss auf der an den Switch Skype for Business Corpnet gebundenen Hostcomputernetzwerkkarte eine IP-Adresse im gleichen Subnetz wie die Cloud Connector-Unternehmensnetzwerkcomputer konfiguriert sein.

- Für Versionen 2.1 und höher muss die Host appliance .NET Framework 4.6.1 oder höher installiert sein.

- **Für die virtuellen Computer –** Ein Windows Server 2012 R2 ISO (Englisch) image (.iso). Die ISO wird in VHDs für die virtuellen Computer konvertiert, die Skype for Business Cloud Connector Edition.

- Die erforderliche Hardware zur Unterstützung der Installation der 4 VMs für jede Cloud Connector Edition in Ihrer Bereitstellung. Die folgenden Konfigurationen werden empfohlen:

  - 64-Bit-Dualprozessor, sechs Kerne (12 echte Kerne), 2,50 Gigahertz (GHz) oder höher

  - 64 GIGABYTE (GB) ECC RAM

  - Vier 600 GB (oder besser) 10K RPM 128M Cache SAS 6 GBit/s-Datenträger, konfiguriert in einer RAID 5-Konfiguration

  - Drei 1 GBit/s RJ45-Netzwerkadapter mit hohem Durchsatz

- Wenn Sie die kleinere Version von Cloud Connector Edition bereitstellen möchten, die bis zu 50 gleichzeitige Anrufe unterstützt, benötigen Sie die folgende Hardware:

  - Intel i7 4790 Quad Core mit Intel 4600 Graphics (keine High-End-Grafiken erforderlich)

  - 32 GB DDR3-1600 non ECC

  - 2: 1 TB 7200RPM SATA III (6 GBit/s) in RAID 0

  - 2: 1 GBit/s Ethernet (RJ45)

- Wenn auf dem Hostcomputer ein Proxyserver zum Durchsuchen des Internets erforderlich ist, müssen Sie die folgenden Konfigurationsänderungen vornehmen:

  - Um den Proxy zu umgehen, geben Sie winHTTP-Proxyeinstellungen an, die mit Ihrem Proxyserver festgelegt sind, und eine Umgehungsliste, einschließlich "192.168.213". \* netzwerk, das von Ihren Cloud Connector Managements-Diensten verwendet wird, und Skype for Business Corpnet-Subnetz, wie in Ihrer CloudConnector.ini definiert. Andernfalls kann die Verwaltungskonnektivität fehlschlagen und die Bereitstellung und automatische Wiederherstellung von Cloud Connector verhindern. Es folgt ein Beispielbefehl für winhttp-Konfiguration: netsh winhttp set proxy "10.10.10.175:8080" bypass-list=" \* .local;1. \* ; 172.20. \* ;192.168.218. \* ' \<local\> ".

  - Geben Sie Proxyeinstellungen pro Computer und nicht pro Benutzer an. Andernfalls wird beim Herunterladen von Cloud Connector ein Fehler angegeben. Sie können Proxyeinstellungen pro Computer mit einer Registrierungsänderung oder mit der Gruppenrichtlinieneinstellung wie folgt angeben:

  - **Registrierung:** HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings] ProxySettingsPerUser dword: 000000000

  - **Gruppenrichtlinie:** Computer \> Administrative Vorlagen Windows Komponenten Internet \> Explorer: Erstellen von Proxyeinstellungen pro Computer \> (anstatt pro Benutzer)

- Qualifizierte Nebenstellenanlage/Trunk oder qualifizierter SBC/Gateway (mindestens zwei Gateways werden empfohlen).

    Cloud Connector unterstützt dieselben Session Border Controller (SBCs), die für die Skype for Business. Weitere Informationen finden Sie unter [Telephony Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md).

- Ein lokales Serveradministratorkonto mit Berechtigungen zum Installieren und Konfigurieren von Hyper-V auf den Hostservern. Das Konto muss über Administratorberechtigungen auf dem lokalen Server verfügen, auf dem Hyper-V installiert und konfiguriert ist.

- Während der Bereitstellung werden Sie aufgefordert, ein Domänenadministratorkonto mit Berechtigungen zum Erstellen und Veröffentlichen der Topologie in der Cloud Connector-Domäne zu erstellen und zu veröffentlichen.

- Die externen DNS-Einträge, die in der im Installationspaket CloudConnector.ini datei definiert sind:

  - Externer #A0 für den #A1 der Edgekomponente; Beispiel: ap. \<Domain Name\> . Sie benötigen einen Datensatz pro PSTN-Standort. Dieser Datensatz muss IP-Adressen aller Edges für diesen Standort enthalten.

- Eine Microsoft 365 oder Office 365, in der alle erforderlichen DNS- und SRV-Einträge erstellt wurden.

    > [!IMPORTANT]
    > Wenn Sie Ihren Mandanten in Cloud Connector Edition integrieren, wird die Verwendung des Standarddomänensuffixs .onmicrosoft.com als SIP-Domäne für Ihre Organisation nicht unterstützt. > Sie können sip nicht verwenden.\<Domain Name\> als Name Ihrer Cloud Connector Edge Access-Proxyschnittstelle, da dieser DNS-Eintrag von Microsoft 365 und Office 365.

- Ein Zertifikat für den externen Edge, das von einer öffentlichen Zertifizierungsstelle (Certificate Authority, CA) erworben wurde.

- Firewallregeln zum Zulassen des Datenverkehrs über die erforderlichen Ports wurden abgeschlossen.

- Eine Internetverbindung für den Hostcomputer und die VMs. Cloud Connector lädt software aus dem Internet herunter. Daher müssen Sie Gateway- und DNS-Serverinformationen bereitstellen, damit der Cloud Connector-Hostcomputer und VMs eine Verbindung mit dem Internet herstellen und die erforderliche Software herunterladen können.

- Ein Auf dem Hostcomputer installiertes Mandanten-Remote-PowerShell-Modul.

- Die Skype for Business Administratoranmeldeinformationen zum Ausführen von Remote PowerShell.

    > [!IMPORTANT]
    > Für das Administratorkonto DARF KEINE mehrstufige Authentifizierung aktiviert sein.

> [!NOTE]
> Die Cloud Connector-Bereitstellung wird nur auf der virtuellen Microsoft Hyper-V unterstützt. Andere Plattformen, z. B. VMware und Amazon Web Services, werden nicht unterstützt.

> [!NOTE]
> Die Mindesthardwareleitlinie zum Ausführen von Cloud Connector basiert auf der grundlegenden Hardwarekapazität (Kerne, MHz, Gigabytes und so weiter) mit etwas Puffer, um immaterielle Leistungsbeeinträchtigungen in der Architektur eines beliebigen Computers zu unterstützen. Microsoft hat Auslastungstests für den schlechtesten Fall auf handelsüblicher Hardware ausgeführt, die die Mindestleitlinie einberaumt. Medienqualität und Systemleistung werden überprüft. Offizielle Cloud Connector-Appliance-Partner von Microsoft verfügen über bestimmte Cloud Connector-Hardwareimplementierungen, für die sie die Leistung unabhängig getestet haben, und sie stehen zur Eignung ihrer Hardware zur Erfüllung der Last- und Qualitätsanforderungen.

> [!NOTE]
> Von AudioCodes und Sonus produzierte Geräte haben geänderten Code und werden auf Windows Server Standard Edition ausgeführt. Diese Geräte werden unterstützt.

## <a name="information-you-need-to-gather-before-deployment"></a>Informationen, die Sie vor der Bereitstellung sammeln müssen
<a name="BKMK_PlanDeployment"> </a>

Bevor Sie mit der Bereitstellung beginnen, müssen Sie die Größe Ihrer Bereitstellung, die zu verwaltende SIP-Domänen und die Konfigurationsinformationen für jeden pstN-Standort bestimmen, den Sie bereitstellen möchten. Zu Beginn werden Sie:

- Identifizieren Sie alle SIP-Domänen, die von dieser Bereitstellung bedient werden, basierend auf den in Ihrem Unternehmen verwendeten SIP-URIs.

- Bestimmen Sie die Anzahl der PSTN-Standorte, die Sie bereitstellen müssen.

- Stellen Sie sicher, dass Sie über die erforderliche Hardware verfügen, um die vier VMs zu unterstützen, die Sie für jede Cloud Connector Edition installieren.

Für jeden pstN-Standort, den Sie bereitstellen möchten, müssen Sie:

- Erstellen Sie Namen für alle Komponenten in jeder Cloud Connector-Appliance (siehe [Bestimmen von Bereitstellungsparametern](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definieren von Portbereichen (siehe [Ports und Protokolle](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).

- Erstellen externer DNS-Einträge für die Edgekomponente (siehe [Anforderungen für die Bereitstellung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Bestimmen Der Zertifikatanforderungen für die Edgekomponente (siehe [Zertifikatanforderungen](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Ports und Protokolle
<a name="BKMB_Ports"> </a>

Beachten Sie beim Definieren von Medienportbereichen Folgendes:

- Clients verwenden für den Mediendatenverkehr immer den Portbereich 50000 bis 50019 – dieser Bereich ist in Skype for Business Online vordefiniert und kann nicht geändert werden.

- Die Vermittlungskomponente verwendet standardmäßig den Portbereich 49 152 bis 57 500 für den Mediendatenverkehr. Die Verbindung wird jedoch über eine interne Firewall hergestellt, und aus Sicherheitsgründen können Sie diesen Portbereich in Ihrer Topologie einschränken. Sie benötigen bis zu vier Ports pro Anruf. Wenn Sie die Anzahl der Ports zwischen der Vermittlungskomponente und dem PSTN-Gateway begrenzen möchten, müssen Sie auch den entsprechenden Portbereich auf dem Gateway konfigurieren.

- Sie müssen Cloud Connector in einem Umkreisnetzwerk bereitstellen. Dies bedeutet, dass Sie über zwei Firewalls verfügen:

  - Die erste Firewall befindet sich extern zwischen dem Internet und Ihrem Umkreisnetzwerk.

  - Die zweite Firewall ist intern zwischen dem Umkreisnetzwerk und Ihrem internen Netzwerk.

    Ihre Clients können sich im Internet oder im internen Netzwerk befinden:

  - Clients im Internet stellen über die externe Firewall über die Edgekomponente eine Verbindung mit Ihrem PSTN fest.

  - Clients im internen Netzwerk verbinden sich über die interne Firewall mit der Vermittlungskomponente im Umkreisnetzwerk, die Datenverkehr mit dem SBC- oder PSTN-Gateway verbindet.

    Dies bedeutet, dass Sie Ports in beiden Firewalls öffnen müssen.

In den folgenden Tabellen werden die Ports und Portbereiche für die externen und internen Firewalls beschrieben.

In dieser Tabelle sind die Ports und Portbereiche zum Aktivieren der Kommunikation zwischen Clients im internen Netzwerk und der Vermittlungskomponente aufgeführt:

**Interne Firewall**



|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Cloud Connector-Vermittlungskomponente  <br/> |SBC/PSTN Gateway  <br/> |Any  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN Gateway  <br/> |Cloud Connector-Vermittlungskomponente  <br/> |Any  <br/> |TCP 5068/ TLS 5067  <br/> |
|Cloud Connector-Vermittlungskomponente  <br/> |SBC/PSTN Gateway  <br/> |UDP 49 152 - 57 500  <br/> |Any\*\*\*  <br/> |
|SBC/PSTN Gateway  <br/> |Cloud Connector-Vermittlungskomponente  <br/> |Any\*\*\*  <br/> |UDP 49 152 - 57 500  <br/> |
|Cloud Connector-Vermittlungskomponente  <br/> |Interne Clients  <br/> |TCP 49 152 - 57 500\*  <br/> |TCP 50.000-50.019  <br/> (Optional)  <br/> |
|Cloud Connector-Vermittlungskomponente  <br/> |Interne Clients  <br/> |UDP 49 152 - 57 500\*  <br/> |UDP 50.000-50.019  <br/> |
|Interne Clients  <br/> |Cloud Connector-Vermittlungskomponente  <br/> |TCP 50.000-50.019  <br/> |TCP 49 152 - 57 500\*  <br/> |
|Interne Clients  <br/> |Cloud Connector-Vermittlungskomponente  <br/> |UDP 50.000-50.019  <br/> |UDP 49 152 -57 500\*  <br/> |

\* Dies ist der Standardportbereich für die Vermittlungskomponente. Für einen optimalen Anruffluss sind vier Ports pro Anruf erforderlich.

\*\* Dieser Port muss auf dem SBC/PSTN-Gateway konfiguriert werden. 5060 ist ein Beispiel. Sie können andere Ports auf Ihrem SBC/PSTN-Gateway konfigurieren.

\*\*\* Beachten Sie, dass Sie auch den Portbereich auf Ihrem SBC/Gateway einschränken können, wenn dies vom SBC/Gateway-Hersteller zulässig ist.

Aus Sicherheitsgründen können Sie den Portbereich für die Vermittlungskomponente mithilfe des [Cmdlets Set-CsMediationServer](/powershell/module/skype/set-csmediationserver?) einschränken.

Der folgende Befehl begrenzt beispielsweise die Anzahl der Ports, die die Vermittlungskomponente für mediendatenverkehr verwendet, auf 50 000 bis 51 000 für Audio (ein- und aus). Die Vermittlungskomponente kann 250 gleichzeitige Anrufe mit dieser Konfiguration verarbeiten. Beachten Sie, dass Sie diesen Bereich möglicherweise auch für das SBC/PSTN-Gateway einschränken möchten:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Zum Abrufen des Namens der Vermittlungskomponente und anzeigen der Standardports können Sie das [Cmdlet Get-CsService](/powershell/module/skype/get-csservice?) wie folgt verwenden:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

In der folgenden Tabelle sind Ports und Portbereiche zum Aktivieren der Kommunikation zwischen der Cloud Connector Edge-Komponente und der externen Firewall aufgeführt. Diese Tabelle enthält eine Mindestempfehlung.

In diesem Fall wird der ganze Mediendatenverkehr in das Internet wie folgt über den Online-Edge fließen: User-End point-- \> Online Edge-- \> Cloud Connector Edge:

**Externe Firewall – Mindestkonfiguration**



|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Any  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |TCP(MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |Any  <br/> |TCP(MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |Any  <br/> |TCP 80  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |Any  <br/> |UDP 53  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |Any  <br/> |TCP 53  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Any  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
|Any  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |

In der nächsten Tabelle sind Ports und Portbereiche zum Aktivieren der Kommunikation zwischen der Cloud Connector Edge-Komponente und der externen Firewall aufgeführt. In dieser Tabelle ist die empfohlene Lösung aufgeführt.

In diesem Fall kann der medienbasierte Datenverkehr für den Endpunkt im Internet direkt zur Cloud Connector Edge-Komponente fließen. Der Medienpfad ist User End Point – \> Cloud Connector Edge.

> [!NOTE]
> Diese Lösung funktioniert nicht, wenn sich der Benutzerendpunkt hinter einer symmetrischen NAT befindet.

**Externe Firewall – empfohlene Konfiguration**


|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Any  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |TCP(MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |Any  <br/> |TCP(MTLS) 5061  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |Any  <br/> |TCP 80  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |Any  <br/> |UDP 53  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |Any  <br/> |TCP 53  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |TCP 50.000-59.999  <br/> |Any  <br/> |
|Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |UDP 3478; UDP 50.000-59.999  <br/> |Any  <br/> |
|Any  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |TCP 443; TCP 50.000-59.999  <br/> |
|Any  <br/> |Externe Schnittstelle für Cloud Connector Edge  <br/> |Any  <br/> |UDP 3478; UDP 50.000 - 59.999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Anforderungen an die Hostinternetverbindung
<a name="BKMB_Ports"> </a>

Der Hostcomputer muss externe Ressourcen erreichen können, um Cloud Connector erfolgreich installieren, aktualisieren und verwalten zu können. In der folgenden Tabelle sind die Ziele und Ports aufgeführt, die zwischen dem Hostcomputer und externen Ressourcen erforderlich sind.

|Direction  <br/> |Quell-IP  <br/> |Ziel-IP  <br/> |Quellport  <br/> |Zielport  <br/> |Protokoll  <br/> |Zweck  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ausgehend  <br/> |Cloud Connector-Host-IPs  <br/> |Beliebiger Wert  <br/> |Beliebiger Wert  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Ausgehend  <br/> |Cloud Connector-Host-IPs  <br/> |Beliebiger Wert  <br/> |Beliebiger Wert  <br/> |80, 443  <br/> |TCP  <br/> |Zertifikatsperrliste (Certificate Revocation List, CRL)  <br/> |
|Ausgehend  <br/> |Cloud Connector-Host-IPs  <br/> |Beliebiger Wert  <br/> |Beliebiger Wert  <br/> |80, 443  <br/> |TCP  <br/> |Cloud Connector-Update  <br/> Skype for Business Online  <br/> Admin PowerShell  <br/> Windows Update  <br/> |

Wenn restriktivere Regeln erforderlich sind, lesen Sie die folgenden URLs für allowlist:

- [URLs der Zertifikatsperrliste](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) in [Office 365 URLs und IP-Adressbereichen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [Konfigurieren einer Firewall für Softwareupdates](https://technet.microsoft.com/library/bb693717.aspx)

- Skype for Business Online Admin PowerShell: \* .online.lync.com

    Wenn Sie einen Proxyausschluss für dieses Ziel benötigen, müssen Sie ihn der WinHTTP-Umgehungsliste hinzufügen.

- Cloud Connector Update: [Download Center](https://aka.ms/CloudConnectorInstaller) [https://go.microsoft.com](https://go.microsoft.com) , und [https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>DNS-Namensauflösung für die Edgekomponente
<a name="BKMB_Ports"> </a>

Die Edgekomponente muss die externen Namen von Microsoft 365 oder Office 365 und die internen Namen anderer Cloud Connector-Komponenten auflösen.

Jede Edgekomponente ist ein multi-homed Computer mit externen und internen Schnittstellen. Cloud Connector stellt DNS-Server in der Domänencontrollerkomponente innerhalb des Umkreisnetzwerks zur Verfügung. Sie können Edgeserver für alle Namensauflösungen auf den DNS-Server im Umkreis verweisen, sie müssen jedoch den Cloud Connector DNS Server zum Auflösen externer Namen aktivieren, indem Sie eine DNS-Zone festlegen, die einen oder mehrere DNS-A-Einträge für externe Abfragen enthält, die Namenssups auf andere öffentliche DNS-Server verweisen.

Wenn Sie in der .ini den FQDN-Namen für Gateways aus demselben Domänenraum wie Ihre SIP-Domäne festlegen, wird die autorisierende Zone für diese SIP-Domäne im DNS-Server innerhalb des Umkreises erstellt. Wenn Edgeserver zum Auflösen von Namen auf diesen DNS-Server verweist, löst Edge die _sipfederationtls.\<yourdomain\> DNS-Eintrag, der für den Anruffluss erforderlich ist. In diesem Fall empfiehlt Microsoft die Bereitstellung eines DNS-Servers auf der externen Edgeschnittstelle zum Auflösen von Internetnamenssups, und jede Edgekomponente muss eine HOST-Datei verwenden, um andere Cloud Connector-Komponentennamen in IP-Adressen zu auflösen.

> [!NOTE]
> Aus Sicherheitsgründen wird empfohlen, den Cloud Connector-DNS-Server zur Namensauflösung nicht auf interne Server in der Produktionsdomäne zu verweisen.

### <a name="determine-deployment-parameters"></a>Bestimmen von Bereitstellungsparametern
<a name="BKMK_SiteParams"> </a>

Zunächst müssen Sie die folgenden allgemeinen Bereitstellungsparameter definieren:


|**Aspekt**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|SIP-Domänen  <br/> |SIP-URI wird von Unternehmensbenutzern verwendet. Stellen Sie alle SIP-Domänen zur Verfügung, die von dieser Bereitstellung bedient werden. Sie können mehrere SIP-Domänen verwenden.  <br/> ||
|Anzahl der PSTN-Standorte  <br/> |Die Anzahl der PSTN-Standorte, die Sie bereitstellen.  <br/> ||

Für jeden pstN-Standort, den Sie bereitstellen möchten, müssen Sie die folgenden Informationen sammeln, bevor Sie mit der Bereitstellung beginnen. Sie müssen diese Informationen bereitstellen, wenn Sie die Datei CloudConnector.ini aktualisieren.

Beachten Sie beim Konfigurieren von Gatewayinformationen Folgendes:

- Wenn Sie nur über ein Gateway verfügen, entfernen Sie den Abschnitt in der .ini für das zweite Gateway. Wenn mehr als zwei Gateways vorhanden sind, folgen Sie dem vorhandenen Format, um neue hinzuzufügen.

- Stellen Sie sicher, dass die IP-Adresse und der Port der Gateways korrekt sind.

- Zur Unterstützung von HA auf PSTN-Gatewayebene behalten Sie das sekundäre Gateway bei, oder fügen Sie zusätzliche Gateways hinzu.

(Optional) Aktualisieren Sie den LocalRoute-Wert, um die ausgehenden Telefonnummern einzuschränken.



|**Websiteparameter**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|Domänenname des virtuellen Computers  <br/> |Domänenname für die internen Komponenten von Cloud Connector. Diese Domäne muss sich von der Produktionsdomäne unterscheiden. Der Name muss für alle Cloud Connector-Appliances identisch sein.  <br/> Name in .ini Datei: "VirtualMachineDomain"  <br/> |.local domain wird bevorzugt.  <br/> |
|Name des Cloud Connector-Domänencontrollers  <br/> |Name des Domänencontrollers.  <br/> Name in .ini Datei: "ServerName"  <br/> |Muss mindestens 15 Zeichen lang sein. Geben Sie nur Netbios-Namen ein.  <br/> |
|Cloud Connector-Domänencontroller-IP/Subnetzmaske  <br/> |DIE IP-Adresse des Domänencontrollers.  <br/> Name in .ini Datei: "IP"  <br/> ||
|Microsoft 365 oder Office 365 FQDNs des Onlinediensts  <br/> |Muss in den meisten Fällen die Standardeinstellung für die Microsoft 365 oder Office 365 sein.  <br/> Name in .ini Datei: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Skype for Business Websitename; z. B. Seattle.  <br/> Name in .ini Datei: "SiteName"  <br/> Für Version 1.4.1 und höher muss der Websitename für jeden Standort unterschiedlich sein, und der Name muss mit dem in Microsoft 365 oder Office 365 definierten PSTN-Standort übereinstimmen. Beachten Sie, dass beim Registrieren der ersten Appliance an einem Standort automatisch PSTN-Standorte erstellt werden.  <br/> ||
|HardwareType  <br/> Version 1.4.1 und höher  <br/> |Hardwaretyp. Der Standardwert ist "Normal". Sie können auch auf Minimum festlegen.  <br/> ||
|Country Code  <br/> |Ländercode für Wählwahl.  <br/> Name in .ini Datei: "CountryCode"  <br/> ||
|Stadt/Ort  <br/> |Ort (Optional).  <br/> Name in .ini Datei: "City"  <br/> ||
|Status  <br/> |Status (Optional).  <br/> Name in .ini Datei: "Status"  <br/> ||
|Basis-VM-IP-Adresse  <br/> |Die IP-Adresse der temporären Basis-VM, die zum Erstellen der VHDX für alle virtuellen Cloud Connector-Computer verwendet wird. Diese IP muss sich im gleichen Umkreisnetzwerksubnetz befinden, das im nächsten Schritt definiert ist und Internetzugriff erfordert. Stellen Sie sicher, dass Sie das Standardgateway des Unternehmens und das DNS definieren, das für das Internet umstrukturierbar ist.  <br/> Name in .ini Datei: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 und höher  <br/> |Die Adresse des Windows Server Update Services (WSUS) – ein Intranetserver zum Hosten von Updates von Microsoft Update.  <br/> Sie können leer lassen, wenn WSUS nicht benötigt wird.  <br/> ||
|Subnetzmaske für internes Netzwerk  <br/> |Cloud Connector konfiguriert ein IP-Netzwerk für die interne Kommunikation zwischen Cloud Connector-Komponenten. Edge muss auch mit einem anderen Subnetz verbunden sein, das eine Internetverbindung zulässt.  <br/> Name in .ini Datei: "CorpnetIPPrefixLength" unter "Parameters for a pool of VM network"  <br/> ||
|Subnetzmaske für externes Netzwerk  <br/> |Für das externe Netzwerk der Edgekomponente.  <br/> Name in .ini datei: "InternetIPPrefix" unter "Parameters for a pool of VM network"  <br/> ||
|Switchname für internes Netzwerk  <br/> |Name für Switch, der für das interne Cloud Connector-Netzwerk verwendet wird.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in .ini datei: "CorpnetSwitchName" unter "Parameters for a pool of VM network  <br/> ||
|Switchname für externes Netzwerk  <br/> |Name für Switch, der für das externe Cloud Connector-Netzwerk verwendet wird.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in .ini datei: "InternetSwitchName" unter "Parameters for a pool of VM network  <br/> ||
|Standardgateway für interne Netzwerke  <br/> |Dieses Gateway muss Zugriff auf das Internet bereitstellen (das Internet erfordert auch das Festlegen des DNS-Servers) und wird auf internen Schnittstellen von Cloud Connector-Komponenten konfiguriert.  <br/> Name in .ini datei: "CorpnetDefaultGateway" unter "Parameters for a pool of VM network  <br/> ||
|Standardgateway für die externe Schnittstelle der Edgekomponente  <br/> |Wird auf der externen Schnittstelle der Edgekomponente konfiguriert.  <br/> Name in .ini datei: "InternetDefaultGateway" unter "Parameters for a pool of VM network  <br/> ||
|DNS-Server für internes Netzwerk  <br/> |Wird auf der internen Schnittstelle der temporären VM konfiguriert. Muss die Namensauflösung für Internetnamen bereitstellen. Ohne Bereitstellung eines DNS-Servers wird die Internetverbindung nicht ausgeführt, und die Bereitstellung wird nicht beendet.  <br/> Name in .ini Datei: "CorpnetDNSIPAddress" unter "Parameters for a pool of VM network"  <br/> ||
|DNS-Server für die externe Schnittstelle der Edgekomponente  <br/> |Wird auf der externen Schnittstelle von Edge konfiguriert.  <br/> Name in .ini Datei: "InternetDNSIPAddress" unter "Parameters for a pool of VM network"  <br/> ||
|Name des Verwaltungsschalters  <br/> |Der Verwaltungsschalter ist ein temporärer Switch, der automatisch erstellt wird und während der Bereitstellung für die Konfiguration von Cloud Connector verwendet wird. Die Verbindung wird nach der Bereitstellung automatisch getrennt. Es muss sich um ein anderes Subnetz als alle anderen in Cloud Connector verwendeten Netzwerke befinden.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in .ini datei: "ManagementSwitchName" unter "Parameters for a pool of VM network  <br/> ||
|Verwaltungssubnetzadresse/Subnetzmaske  <br/> |Das Verwaltungssubnetz ist ein temporäres Subnetz, das automatisch erstellt wird und während der Bereitstellung für die Konfiguration von Cloud Connector verwendet wird. Sie wird nach der Bereitstellung automatisch entfernt. Es muss sich um ein anderes Subnetz als alle anderen in Cloud Connector verwendeten Netzwerke befinden.  <br/> Namen in .ini: "ManagementIPPrefix" und "ManagementIPPrefixLength" unter "Parameter für einen Pool von VM-Netzwerk"  <br/> ||
|Central Management Store (CMS) Machine  <br/> |Einzelner FQDN, der für die zentrale Store (CMS) verwendet wird. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "ServerName" unter "Parameters for Primary Central Management Service  <br/> |Muss mindestens 15 Zeichen lang sein. Geben Sie nur Netbios-Namen ein.  <br/> (CMS-Poolname = Servername)  <br/> |
|CMS Machine-IP-Adresse  <br/> |IP-Adresse für CMS Server (intern im Umkreisnetzwerk).  <br/> Name in der INI-Datei: "IP" unter "Parameters for Primary Central Management Service  <br/> ||
|Dateifreigabename  <br/> |Dateifreigabename, der auf dem CMS-Server für die Skype for Business (z. B. CmsFileStore) erstellt werden soll.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in .ini Datei: "CmsFileStore" unter "Parameters for Primary Central Management Service  <br/> ||
|Poolname der Vermittlungskomponente  <br/> |Poolname der Vermittlungskomponente. Geben Sie nur Netbios-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "PoolName" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> |Muss mindestens 15 Zeichen lang sein. Geben Sie nur Netbios-Namen ein.  <br/> |
|Name der Vermittlungskomponente  <br/> |Komponentenname der Vermittlungskomponente 1. Geben Sie nur Netbios-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "ServerName" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> |Muss mindestens 15 Zeichen lang sein. Geben Sie nur Netbios-Namen ein.  <br/> |
|Vermittlungskomponente Computer-IP-Adresse  <br/> |Interne Corpnet-IP für Vermittlungskomponente (intern im Umkreisnetzwerk).  <br/> Name in .ini Datei: "IP" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> ||
|Interner Name des Edgepools  <br/> |Poolname der Edgekomponente. Geben Sie nur Netbios-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "InternalPoolName" unter "Parameter für einen Pool von Edgeservern"  <br/> |Muss mindestens 15 Zeichen lang sein. Geben Sie nur Netbios-Namen ein.  <br/> |
|Interner Name des Edgeservers  <br/> |Komponentenname der Edgekomponente. Geben Sie nur Netbios-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "InternalServerName" unter "Parameter für einen Pool von Edgeservern"  <br/> |Muss mindestens 15 Zeichen lang sein. Geben Sie nur Netbios-Namen ein.  <br/> |
|Interne IP des Edgeservers  <br/> |Interne Umkreisnetzwerk-IP der Edgekomponente, um mit anderen Komponenten von Cloud Connector zu kommunizieren.  <br/> Name in .ini Datei: "InternalServerIPs" unter "Parameter für einen Pool von Edgeservern"  <br/> ||
|Externer Name des Zugriffspools  <br/> |Name von Access Edge; Beispiel: AP. Dieser Name muss mit dem Für das SSL-Zertifikat angegebenen Namen übereinstimmen. Geben Sie nur Netbios-Namen ein. Der SIP-Domänenname wird verwendet, um den FQDN zu generieren. Ein externer Poolname wird für alle Edgekomponenten im Pool verwendet. Pro PSTN-Standort ist ein Edgezugriffspool erforderlich.  <br/> Name in .ini Datei: "ExternalSIPPoolName" unter "Parameter für einen Pool von Edgeservern"  <br/> |Muss mindestens 15 Zeichen lang sein. Geben Sie nur Netbios-Namen ein.  <br/> "sip" ist reserviert und kann daher nicht als Name verwendet werden.  <br/> Der generierte FQDN-Name muss mit dem Für das SSL-Zertifikat angegebenen Namen übereinstimmen.  <br/> |
|Externe IP von Access Edge  <br/> |Externe IP der Edgekomponente – entweder öffentliche IP, wenn keine NAT verfügbar ist, oder übersetzte IP (geben Sie beide Adressen an, falls zugeordnet).  <br/> Name in .ini Datei: "ExternalSIPIPs" unter "Parameters for a pool of Edge Servers"  <br/> ||
|Name des Medienrelais  <br/> |Name des #A0 für Audiovideomedien; z. B. MR. Ein externer Poolname wird für alle Edgekomponenten in einem Pool verwendet. Pro PSTN-Standort ist ein Edgemedienrelaispool erforderlich.  <br/> Name in .ini Datei: "ExternalMRFQDNPoolName" unter "Parameter für einen Pool von Edgeservern"  <br/> |Muss mindestens 15 Zeichen lang sein. Geben Sie nur Netbios-Namen ein.  <br/> |
|Externe IP des Media Relay Edge  <br/> |Derzeit wird nur eine IP unterstützt, also handelt es sich um dieselbe IP wie Access Edge, entweder öffentliche oder zugeordnete IP (geben Sie beide Adressen an, wenn sie zugeordnet sind). Kann die gleiche Adresse wie die externe IP der Edge-Edgekomponente sein. Hinweis: Wenn Edge hinter NAT liegt, müssen Sie auch den Wert für den nächsten Parameter angeben.  <br/> Name in .ini Datei: "ExternalMRIPs" unter "Parameters for a pool of Edge Servers"  <br/> ||
|Externe IP des Media Relay Edge (wenn Edge sich hinter NAT befindet)  <br/> |Wenn Sich Ihr Edge hinter NAT befindet, müssen Sie auch die öffentliche Adresse des NAT-Geräts angeben.  <br/> Name in .ini Datei: "ExternalMRPublicIPs" unter "Parameters for a pool of Edge Servers"  <br/> ||
|Voice Gateway 1 Make and Model  <br/> |Geben Sie den Make und das Modell des SBC/Voice-Gateways an. Beachten Sie, dass Sie ein Gerät oder einen SIP-Trunk aus der Liste der getesteten Geräte unter verbinden [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) können.  <br/> ||
|Voice Gateway 2 Make and Model (kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |Geben Sie den Make und das Modell des Voicegateways an. Beachten Sie, dass Sie ein Gerät aus der Liste der getesteten Geräte unter verbinden [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) können.  <br/> ||
|Voice Gateway 1 Name  <br/> |Wird verwendet, um den Computer-FQDN mit ad Domain zu generieren. Erforderlich, wenn TLS zwischen der Vermittlungskomponente und dem Voicegateway verwendet wird. Wenn Sie nicht planen, FQDN zu verwenden , z. B. ist TLS nicht erforderlich oder VoiceGateway unterstützt keine Verbindung mit FQDN (nur IP) - angeben.  <br/> ||
|Voice Gateway 2 Name (kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |Wird verwendet, um den Computer-FQDN mit ad Domain zu generieren. Erforderlich, wenn TLS zwischen Vermittlungskomponente und Voicegateway verwendet wird. Wenn Sie nicht planen, FQDN zu verwenden , z. B. ist TLS nicht erforderlich oder VoiceGateway unterstützt keine Verbindung mit FQDN (nur IP) - angeben.  <br/> ||
|Voice Gateway 1-IP-Adresse  <br/> |IP-Adresse des Voicegateways.  <br/> ||
|Voice Gateway 2-IP-Adresse (kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |IP-Adresse des Voicegateways.  <br/> ||
|Voice Gateway 1 Port # (kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |Port, den der Voicegateway-SIP-Trunk abhört, z. B. 5060.  <br/> ||
|Voice Gateway 2-Port #  <br/> |Port, den der Voicegateway-SIP-Trunk abhört, z. B. 5060.  <br/> ||
|Voice Gateway 1 Protocol for SIP Traffic  <br/> |TCP oder TLS.  <br/> ||
|Voice Gateway 2 Protocol for SIP Traffic (kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |TCP oder TLS.  <br/> ||
|Bereich des externen Medienports für Datenverkehr zur und von der Edgekomponente  <br/> |TCP/UDP-Portbereich für Mediendatenverkehr zu und von der externen Edgeschnittstelle. Muss immer bei 50 000 beginnen. Weitere Informationen finden Sie unter "Ports and Protocols".  <br/> |50000 - 59 999  <br/> |
|Medienportbereich für die Kommunikation mit/von der Vermittlungskomponente über die interne Firewall  <br/> |UDP-Portbereich, den die Vermittlungskomponente für die Kommunikation mit Clients und Gateways verwendet (Empfehlung 4 Ports pro Anruf).  <br/> ||
|Medienportbereich zur Kommunikation zwischen und Skype for Business Client über interne Firewall  <br/> |Aus Planungsgründen kann nicht geändert werden. Ports müssen in der internen Firewall geöffnet werden, um zwischen Skype for Business clients innerhalb des internen Netzwerks und mit der Vermittlungskomponente zu kommunizieren.  <br/> |50 000- 50 019  <br/> |
|Kennwort für öffentliches Zertifikat  <br/> |Muss im Skript angegeben werden.  <br/> ||
|Administratorkennwort für den abgesicherten Modus  <br/> Nur Version 1.4.2  <br/> |Administratorkennwort für den abgesicherten Modus für die interne CC-Domäne.  <br/> ||
|Domänenadministratorkennwort für Cloud Connector  <br/> Nur Version 1.4.2  <br/> |Kennwort für Cloud Connector Domain Administrator (anders als Ihre Produktionsdomäne). Benutzername ist Administrator. Sie können den Benutzernamen nicht ändern.  <br/> ||
|Administratorkennwort für virtuelle Computer  <br/> Nur Version 1.4.2  <br/> |Wird verwendet, um das Verwaltungsnetzwerk während der Bereitstellung zu konfigurieren.  <br/> Benutzername ist Administrator. Sie können den Benutzernamen nicht ändern.  <br/> ||
|CABackupFile  <br/> Version 2.0 und höher  <br/> |Wird zum Speichern des Zertifizierungsstellendiensts vom Active Directory-Server in einer Datei verwendet, wenn mehrere Appliances an einem Cloud Connector-Standort bereitgestellt werden. Verwenden Sie für alle Appliances innerhalb eines Cloud Connector-Standorts das gleiche Kennwort, um die Sicherungsdatei der Zertifizierungsstelle erfolgreich in die neue hinzugefügte Appliance zu importieren.  <br/> ||
|CCEService  <br/> Version 2.0 und höher  <br/> |Wird für den Cloud Connector-Verwaltungsdienst verwendet. benötigt Zugriff auf das Cloud Connector-Websiteverzeichnis. Verwenden Sie das gleiche Kennwort für alle Appliances innerhalb eines Cloud Connector-Standorts.  <br/> ||
|Microsoft 365 oder Office 365 Mandantenadministrator  <br/> | Das Konto wird von Cloud Connector zum Aktualisieren und Verwalten von Mandanteneinstellungen für Cloud Connector verwendet: <br/>  Version 2.0 und höher: Anmeldeinformationen für ein dediziertes Microsoft 365 oder Office 365 mit Skype for Business Administratorrechten. <br/>  Versionen vor 2.0: Anmeldeinformationen für ein dediziertes Microsoft 365 oder Office 365 mit globalen Mandantenadministratorrechten. <br/> ||
|Aktivieren der REFER-Unterstützung  <br/> |Dadurch wird definiert, ob die SIP -REFER-Unterstützung für die Trunkkonfiguration für Ihre IP/PBX aktiviert oder deaktiviert ist. Der Standardwert lautet "True". Wenn Ihr IP/PBX-Gateway die UNTERSTÜTZUNG von REFER unterstützt, lassen Sie dies als True. Andern falls nicht, muss dieser Wert in False geändert werden. Wenn Sie nicht sicher sind, ob Ihr Gateway REFER unterstützt, finden Sie weitere Informationen [unter Qualified IP-PBXs and Gateways](../../../SfbPartnerCertification/certification/infra-gateways.md).   <br/> ||
|EnableFastFailoverTimer  <br/> Version 2.0 und höher  <br/> |Wenn ausgehende Anrufe vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, werden sie mit dem Standardwert "True" an das nächste verfügbare Gateway geroutet. Wenn keine zusätzlichen Trunks installiert sind, wird der Anruf automatisch gelöscht.  <br/> In einer Organisation mit langsamen Netzwerken und Gatewayantworten oder wenn das Einrichten von Anrufen mehr als 10 Sekunden dauert, kann dies jedoch dazu führen, dass Anrufe unnötigerweise gelöscht werden.  <br/> Bei Anrufen in einigen Ländern, z. B. in den Vereinigten Arabischen Emiraten oder In-Afghanistan, kann der Anruferstellenprozess mehr als 10 Sekunden dauern. Sie müssen den Wert in False ändern, wenn ähnliche Probleme auftreten. Vergessen Sie nicht, die entsprechende Einstellung auf dem verbundenen SBC oder Gateway zu ändern.  <br/> Der Wert kann True oder False sein. Der Standardwert lautet "True".  <br/> ||
|ForwardCallHistory  <br/> Version 2.0 und höher  <br/> | Dieser Parameter wird verwendet, um SIP-Header zu aktivieren, die zum Melden des anfänglichen Anrufers in Szenarien für gleichzeitiges Klingeln, Weiterleiten von Anrufen und Anrufübertragung verwendet werden. Wenn Sie den Parameter auf True festlegen, werden zwei SIP-Header angezeigt: <br/>  History-Info <br/>  Referred-By <br/>  Der History-Info-Header wird zum Retargeting von SIP-Anforderungen verwendet und "stellt(n) einen Standardmechanismus zum Erfassen der Anforderungsverlaufsinformationen zur Verfügung, um eine Vielzahl von Diensten für Netzwerke und Endbenutzer zu ermöglichen" ([RFC 4244 - Section 1.1](http://www.ietf.org/rfc/rfc4244.txt)). Für die Cloud Connector-Trunkschnittstellen wird dies in Szenarien für die gleichzeitige Anruf- und Anruf weiterleitung verwendet.  <br/>  Der Wert kann True oder False sein. Der Standardwert ist False. <br/> ||
|Weiterleiten von PAI  <br/> Version 2.0 und höher  <br/> |PAI ist eine private Sip-Erweiterung, mit der SIP-Server die Identität authentifizierter Benutzer bestätigen können. Für den SIP-Trunkanbieter kann PAI für Abrechnungszwecke verwendet werden, wenn History-Info und Referred-By nicht vorhanden sind. Wenn Forward P-Asserted-Identity in der Konfiguration aktiviert ist, wird der Vermittlungsserver PAI-Header mit SIP-Tel-URI von Cloud Connector an den &amp; SIP-Trunk weiterleiten. Der Vermittlungsserver gibt PAI-Header mit den E.164-Nummern von Tel URI weiter, die nur im &amp; SIP-Trunk empfangen wurden, an Cloud Connector. Der Vermittlungsserver gibt auch alle empfangenen Datenschutzheader in beide Richtungen weiter. Wenn die vom Vermittlungsserver gesendete SIP-Anforderung einen Datenschutzheader des Formulars - "Privacy: id" in Verbindung mit dem PAI-Header enthält, sollte die bestätigte Identität außerhalb der Netzwerkvertrauensdomäne privat bleiben.  <br/> Der Wert kann True oder False sein. Der Standardwert ist False.  <br/> ||

### <a name="certificate-requirements"></a>Anforderungen für Zertifikate
<a name="BKMK_Certs"> </a>

Jede Edgekomponente erfordert ein Zertifikat von einer öffentlichen Zertifizierungsstelle. Zertifikate müssen über einen exportierbaren privaten Schlüssel verfügen, der zwischen Edgekomponenten kopiert werden kann. Um die Zertifikatanforderungen zu erfüllen, müssen Sie zwischen den folgenden Optionen entscheiden und den Betreffnamen (Subject Name, SN) und den alternativen Subject Name (SAN) für das Zertifikat bereitstellen.

 **Wenn Sie über eine einzelne SIP-Domäne verfügen:**

- **Option 1.** Der Betreffname muss den Poolnamen enthalten, den Sie den Edgekomponenten zugewiesen haben. Beachten Sie, dass der Betreffname nicht sip.sipdomain.com, da dieser Name für die Skype for Business edge-Komponente reserviert ist. Das SAN muss sip.sipdomain.com und den Namen des Zugriffs-Edgepools enthalten:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Option 2.** Wenn Sie ein einzelnes Platzhalterzertifikat auf allen bereitgestellten Edgepoolservern verwenden möchten, können Sie anstelle des Edgepoolnamens im Zertifikat einen Platzhalter-SAN-Eintrag von \* .sipdomain.com verwenden. Der Betreffname kann der Name des Zugriffs-Edgepools aller edgepools sein, die Sie bereitgestellt haben:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Sie dürfen keinen externen DNS-Eintrag für sip \<sipdomain\> erstellen. com, da dieser Name zum Microsoft 365 oder Office 365 gehört.

> [!NOTE]
> Wenn Sie ein einzelnes Zertifikat für alle in Ihrer Organisation bereitgestellten Edgepools verwenden möchten und kein Platzhalterzertifikat wie in Option 2 definiert verwenden können, müssen Sie den FQDN für alle bereitgestellten Edgepools in den SAN-Namen in das Zertifikat eingeben.

 **Wenn Sie über mehrere SIP-Domänen verfügen:**

Sie müssen sip.sipdomain.com für jede SIP-Domäne und den Namen der Zugriffs-Edgepools pro Domäne hinzufügen (es kann sich um einen physischen Pool mit unterschiedlichen Namen geben). Im Folgenden finden Sie ein Beispiel für SN- und SAN-Einträge in einem Szenario mit mehreren Sipdomänen:

- **Option 1.** Der Betreffname muss den Poolnamen enthalten, den Sie Edgekomponenten zugewiesen haben. Beachten Sie, dass der Betreffname nicht sip.sipdomain.com, da dieser Name für die Skype for Business edge-Komponente reserviert ist. Das SAN muss sip.sipdomain.com und den Namen des Zugriffs-Edgepools enthalten:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Option 2.</strong> Wenn Sie ein einzelnes Platzhalterzertifikat auf allen bereitgestellten Edgepoolservern verwenden möchten, können Sie anstelle des Edgepoolnamens im Zertifikat einen Platzhalter-SAN-Eintrag von \* .sipdomain.com verwenden. Der Betreffname kann der Name des Zugriffs-Edgepools aller edgepools sein, die Sie bereitgestellt haben:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Sie dürfen keinen externen DNS-Eintrag für sip \<sipdomain\> erstellen. com, da dieser Name zum Microsoft 365 oder Office 365 gehört.

Für die Bereitstellung können Sie die folgende Tabelle verwenden:

|**Option**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|Welche Option wird für Ihre Bereitstellung verwendet?  <br/> |Option 1 oder 2  <br/> ||
|SN  <br/> |Bereitstellen des SN für Ihr Zertifikat  <br/> ||
|SAN  <br/> |Stellt das SAN für Ihr Zertifikat zur  <br/> ||

Wenn Sie TLS zwischen dem Gateway und dem Vermittlungsserver verwenden, müssen Sie das Stammzertifikat oder die vollständige Zertifikatkette für das dem Gateway zugewiesene Zertifikat abrufen.

## <a name="dial-plan-considerations"></a>Überlegungen zu Wählplan
<a name="BKMK_DailPlan"> </a>

Cloud Connector erfordert die Verwendung eines Onlinewählplans. Weitere Informationen zum Konfigurieren eines Onlinewählplans finden Sie unter [Was sind Wählpläne?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Überlegungen zur hohen Verfügbarkeit
<a name="BKMK_HA"> </a>

Wenn Sie Cloud Connector Edition für hohe Verfügbarkeit bereitstellen, stellen Sie mindestens zwei Appliances zur Verfügung, die als Sicherung füreinander fungieren. Jede Appliance besteht aus vier Komponenten: Edge, Mediation, Central Management Store (CMS) und Domänencontroller.

Im Allgemeinen kann Cloud Connector Edition weiterhin Anrufe verarbeiten, wenn eine Komponente innerhalb einer Appliance aus ist, aber Sie müssen Folgendes berücksichtigen:

- **Überlegungen zu Vermittlungs-, CMS- und Domänencontrollerkomponenten**

    Angenommen, die CMS- oder Domänencontrollerkomponente in einer Appliance geht aus. Die Appliance kann eingehende und ausgehende Anrufe weiterhin verarbeiten. Wenn Sie jedoch eine Vermittlungskomponente neu starten, wenn der Domänencontroller oder die CMS-Komponente nicht erreichbar ist, funktioniert die Vermittlung nicht. Dies gilt auch für den Neustart der CMS-Komponente, wenn der Domänencontroller aus ist.

    **Empfehlung:** Überprüfen Sie vor dem Neustart der Komponenten die Verfügbarkeit der anderen Komponenten in der Appliance.

- **Überlegungen zu Edgekomponenten**

    Wenn die Edgekomponente in einer Appliance nicht verfügbar ist, unterscheidet sich das Verhalten für eingehende und ausgehende Anrufe wie folgt:

  - **Ausgehender Anruf**– ein Anruf von Ihrem Benutzer im Internet an ein PSTN-Netzwerk.

    Der Anrufverteilungsmechanismus in der Cloud identifiziert, dass eine Edgekomponente aus ist und alle Anrufe an eine andere Appliance weiter, sodass der ausgehende Anruf erfolgreich ist.

  - **Eingehender Anruf**– ein Anruf aus dem PSTN-Netzwerk an einen Benutzer, der sich entweder in einem lokalen Netzwerk oder im Internet befindet.

     Wenn die Edgekomponente der Appliance, die den Anruf empfangen hat, nicht funktioniert, sind die eingehenden Anrufe an diese Appliance nicht erfolgreich, da die Vermittlungskomponente den Anruf nicht an die Edgekomponente in der anderen Appliance umleiten kann.

    **Empfehlung:** Verfügen Sie über ein Überwachungssystem. Nachdem Sie eine Fehlfunktion der Edgekomponente identifiziert haben, fahren Sie alle Komponenten in der Appliance herunter, in der die Edgekomponente nicht verfügbar ist.

## <a name="cloud-connector-media-flow"></a>Cloud Connector-Medienfluss
<a name="BKMK_MediaFlow"> </a>

In den folgenden Diagrammen wird der Ablauf eines ausgehenden und eingehenden Anrufs über Cloud Connector Edition dargestellt. Dies sind hilfreiche Informationen, um zu verstehen, wie die Verbindung hergestellt wird.

Im ersten Diagramm platziert ein interner Benutzer einen ausgehenden Anruf wie folgt:

1. Dave, ein Onlinebenutzer, aber jetzt im internen Netzwerk, stellt einen Anruf an einen externen PSTN-Benutzer.

2. SIP-Datenverkehrsrouten zu Skype for Business Online.

3. Skype for Business Online führt eine Reverse Number Lookup der Zahl aus. Die Reverse Number Lookup schlägt fehl, da diese Nummer niemandem in der Organisation Skype for Business gehört.

4. Der Anruf wird an die Edgekomponente (SIP und Medienfluss über Online Edge zuerst; Medien werden über die interne Firewall zur Vermittlungskomponente wechseln).

5. Wenn die Route vorhanden ist, leitet die Edgekomponente den Datenverkehr an die Vermittlungskomponente im Umkreisnetzwerk weiter.

6. Die Vermittlungskomponente sendet den Datenverkehr an das PSTN-Gateway.

![Ausgehender Medienfluss für Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Im nächsten Diagramm empfängt ein interner Benutzer einen eingehenden Anruf wie folgt:

1. Das PSTN-Gateway empfängt einen Anruf für den Benutzer Dave, der online, aber jetzt im internen Netzwerk gespeichert ist.

2. DER SIP-Datenverkehr wird an die Vermittlungskomponente geroutet.

3. Die Vermittlungskomponente sendet SIP-Datenverkehr an die Edgekomponente und dann zu Skype for Business Online.

4. Skype for Business Online führt eine Reverse Number-Suche der Nummer durch und stellt fest, dass es sich um den Benutzer Dave handelt.

5. Die SIP-Signalisierung geht an alle Anwesenheitspunkte von Dave.

6. Mediendatenverkehr wird zwischen dem Gateway und der Vermittlungskomponente und zwischen der Vermittlungskomponente und dem Endpunkt eingerichtet.

![Eingehende Medien Flow für Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Überwachung und Problembehandlung
<a name="BKMK_Monitor"> </a>

Der Überwachungs- und Problembehandlungsmechanismus wird automatisch mit jeder Cloud Connector-Appliance installiert. Der Mechanismus erkennt die folgenden Ereignisse:

- Mindestens ein virtueller Computer einer Cloud Connector-Appliance ist nicht mit einem internen oder virtuellen Internetschalter verbunden.

- Mindestens ein virtueller Computer einer Cloud Connector-Appliance wird gespeichert oder beendet.

- Dienste, die nicht ausgeführt werden.

  Wenn eines der folgenden Ereignisse erkannt wird, wird die gesamte Cloud Connector-Appliance entleert und als offline markiert, um den Versuch zu verhindern, Anrufe an eine fehlerhafte Appliance zu erstellen. Die automatischen Wiederherstellungsfeatures von Cloud Connector stellen dienste anschließend wiederher und markieren die Appliance als online. Wenn die automatische Wiederherstellung aus einem bestimmten Grund fehlschlägt, finden Sie weitere Informationen unter [Troubleshoot your Cloud Connector deployment](troubleshoot-your-cloud-connector-deployment.md).

  - Auf der zentralen Store virtuellen Computer:

     - Skype for Business Master Replicator Agent

     - Skype for Business Replikatreplikate-Agent

  - Auf dem virtuellen Vermittlungsservercomputer:

     - Skype for Business Replikatreplikate-Agent

     - Skype for Business Server Vermittlung

  - Auf dem virtuellen Edgeservercomputer

     - Skype for Business Replikatreplikate-Agent

     -  Skype for Business Server Access Edge

     - Skype for Business Server Audio/Video Edge

     - Skype for Business Server Audio-/Videoauthentifizierung

     - Skype for Business Server Edge für Webkonferenzen

- Eingehende Regel der Windows "CS RTCSRV" auf Edge, "CS RTCMEDSRV" auf dem Vermittlungsserver ist deaktiviert.

Cloud Connector 2.1 und höher unterstützt die Überwachung von Cloud Connector mithilfe der Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_MoreInfo"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:

- [Microsoft-Telefonielösungen](/microsoftteams/cloud-voice-landing-page)

- [Konfigurieren und Verwalten Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Planen der Medienumgehung in der Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Bereitstellen der Medienumgehung in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
