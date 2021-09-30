---
title: Planen der Skype for Business Cloud Connector Edition
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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Hier finden Sie Informationen zu Skype for Business Cloud Connector Edition, einer Reihe von verpackten virtuellen Computern (VMs), die lokale PSTN-Konnektivität mit Telefonsystem (Cloud PBX) implementieren.
ms.openlocfilehash: f27fdd41978cd686a7019876dedbfe63a29af9e9
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014149"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planen der Skype for Business Cloud Connector Edition

> [!Important]
> Cloud Connector Edition wird zusammen mit Skype for Business Online am 31. Juli 2021 eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

Hier finden Sie Informationen zu Skype for Business Cloud Connector Edition, einer Reihe von verpackten virtuellen Computern (VMs), die lokale PSTN-Konnektivität mit Telefonsystem (Cloud PBX) implementieren.

Cloud Connector Edition ist möglicherweise die richtige Lösung für Ihre Organisation, wenn Sie noch nicht über eine vorhandene Lync Server- oder Skype for Business Server-Bereitstellung verfügen. Wenn Sie noch untersuchen, welche Telefonsystem Lösung für Ihr Unternehmen geeignet ist, lesen Sie [die Microsoft-Telefonielösungen.](/microsoftteams/cloud-voice-landing-page)

Dieses Dokument beschreibt die Anforderungen der Cloud Connector Edition und unterstützte Topologien und hilft Ihnen bei der Planung Ihrer Cloud Connector Edition-Bereitstellung. Lesen Sie diesen Artikel unbedingt, bevor Sie Ihre Cloud Connector-Umgebung konfigurieren. Wenn Sie bereit sind, Cloud Connector Edition bereitzustellen und zu konfigurieren, lesen [Sie "Konfigurieren und Verwalten Skype for Business Cloud Connector Edition."](configure-skype-for-business-cloud-connector-edition.md)

Cloud Connector Edition 2.1 ist jetzt verfügbar. Wenn Sie noch nicht auf 2.1 aktualisiert haben, lesen Sie [das Upgrade auf eine neue Version von Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md) Die Installationsdatei finden Sie unter [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .

> [!NOTE]
> Microsoft unterstützt die vorherige Version von Cloud Connector Edition 60 Tage nach der Veröffentlichung einer neuen Version. Microsoft unterstützt Version 2.0.1 für 60 Tage nach der Veröffentlichung von 2.1, damit Sie Zeit zum Upgrade haben. Alle Versionen vor Version 2.0.1 werden nicht mehr unterstützt.

Cloud Connector Edition ist ein Hybridangebot, das aus einer Reihe von verpackten virtuellen Computern (VMs) besteht, die lokale PSTN-Konnektivität mit Telefonsystem implementieren. Durch die Bereitstellung einer minimalen Skype for Business Server Topologie in einer virtualisierten Umgebung können Benutzer in Ihrer Organisation, die in der Cloud verwaltet werden, PBX-Dienste aus der Microsoft-Cloud empfangen, die PSTN-Konnektivität wird jedoch über die vorhandene lokale VoIP-Infrastruktur bereitgestellt.

![Topologiediagramm, das das Cloud PBX-Gateway zeigt, das Cloud PBX mit einer lokalen Bereitstellung von Skype for Business verbindet.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Da Sie mit Cloud Connector Telefonsystem Dienste in Ihre vorhandene Telefonieumgebung integrieren können , z. B. Nebenstellenanlagen, analoge Geräte und Callcenter, können Sie eine phasenweise Migration von Ihrer vorhandenen Telefonielösung zu Telefonsystem implementieren.

Angenommen, Ihr Unternehmen verfügt über ein komplexes CallCenter mit bestimmten Funktionen, die Telefonsystem nicht bereitstellt. Sie können festlegen, dass call center-Benutzer die vorhandene Lösung beibehalten, aber andere Benutzer zu Telefonsystem verschieben.

Cloud Connector bietet Routing zwischen den lokal und online verwalteten Benutzern, und Sie können ihren eigenen PSTN-Anbieter mit Telefonsystem verwenden.

Berücksichtigen Sie bei der Planung Ihrer Cloud Connector Edition-Bereitstellung Folgendes:

- Um Cloud Connector zur Nutzung von Cloud Voice-Lösungen zu verwenden, müssen Sie sich für eine Microsoft 365 oder Office 365 Organisation registrieren, die Telefonsystem umfasst. Wenn Sie noch keine Microsoft 365 oder Office 365 Organisation haben, erfahren Sie, wie Sie sich hier registrieren: [Microsoft 365 for Business](https://products.office.com/business/office). Beachten Sie, dass Sie sich für einen Plan registrieren müssen, der Skype for Business Online umfasst.

- Um Cloud Connector-Appliances beim Skype for Business Onlinedienst zu registrieren und verschiedene Cmdlets auszuführen, erfordert Cloud Connector 2.0 und höher ein dediziertes Microsoft 365- oder Office 365-Konto mit den Skype for Business Mandantenadministratorrechten. Cloud Connector-Versionen vor Version 2.0 erfordern ein dediziertes Microsoft 365- oder Office 365-Konto mit globalen Mandantenadministratorrechten.

- Cloud Connector erfordert keine vollständige lokale Skype for Business Server Bereitstellung.

    Derzeit kann Cloud Connector nicht mit Lync oder Skype for Business lokalen Servern koexistieren. Wenn Sie vorhandene Lync- oder Skype for Business-Benutzer in Microsoft 365 verschieben und Ihren Benutzern weiterhin lokale Telefonie bereitstellen möchten, sollten Sie Telefonsystem mit lokaler Konnektivität mithilfe einer vorhandenen Skype for Business Server-Bereitstellung in Betracht ziehen. Weitere Informationen finden Sie unter [Plan your Telefonsystem (Cloud PBX) solution](/microsoftteams/cloud-voice-landing-page) and Plan Telefonsystem with [on-premises PSTN connectivity in Skype for Business Server.](plan-phone-system-with-on-premises-pstn-connectivity.md)

- Wenn Sie eine vorherige Skype for Business oder Lync Server-Bereitstellung hatten und das Schema erweitert haben, müssen Sie das Schema für die Cloud Connector-Bereitstellung nicht bereinigen, solange Sie alle Skype for Business oder Lync Server-Komponenten aus Ihrer Umgebung entfernt haben.

- Ihre Benutzer werden online verwaltet.

- Wenn Ihre Organisation die Verzeichnissynchronisierung (DirSync) konfiguriert hat, müssen alle Konten von Benutzern, die für Hybrid-VoIP geplant sind, zuerst in Ihrer lokalen Bereitstellung erstellt und dann mit der Cloud synchronisiert werden.

- Sie können Ihren aktuellen PSTN-Netzbetreiber bei Bedarf behalten.

- Wenn Sie Einwahlkonferenzen für Benutzer bereitstellen möchten, die auf Cloud Connector gehostet werden, können Sie eine PSTN-Konferenzlizenz erwerben oder bezahlen, wenn Sie ein Audiokonferenzangebot von Microsoft erhalten.

- Für Anrufeskalationen ist auch die Lizenz für Audiokonferenzen erforderlich (oder wird während des Angebots bezahlt). Wenn ein Skype for Business Benutzer einen Anruf von einem externen PSTN-Benutzer empfängt und diesem Anruf einen weiteren Teilnehmer hinzufügen möchte (den Anruf an eine Konferenz eskalieren), wird die Eskalation über den Microsoft-Audiokonferenzdienst ausgeführt.

- Cloud Connector 2.0 und höher unterstützt jetzt die Medienumgehung. Die Medienumgehung ermöglicht es einem Client, Medien direkt an den nächsten Hop (PsTN) zu senden – ein Gateway oder Session Border Controller (SBC) – und die Cloud Connector Edition-Komponente aus dem Medienpfad zu entfernen. Weitere Informationen finden Sie unter [Planen der Medienumgehung in Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)

- Cloud Connector 2.1 und höher unterstützt die Überwachung von Cloud Connector mithilfe von Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Überwachen von Cloud Connector mit Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- Cloud Connector ist in allen Ländern verfügbar, in denen Office 365 Enterprise E5 verfügbar ist.

Dieser Artikel enthält die folgenden Abschnitte:

- [Cloud Connector Edition-Komponenten](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Cloud Connector Edition-Topologien](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Anforderungen für die Bereitstellung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informationen, die Sie vor der Bereitstellung sammeln müssen](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Überlegungen zum Wählplan](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Überlegungen zur hohen Verfügbarkeit](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Cloud Connector-Medienfluss](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Überwachung und Problembehandlung](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Weitere Informationen](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Cloud Connector Edition-Komponenten
<a name="BKMK_Components"> </a>

Mit Cloud Connector Edition stellen Sie eine Reihe von verpackten VMs bereit, die eine minimale Skype for Business Server Topologie enthalten, die aus einer Edgekomponente, einer Vermittlungskomponente und einer zentralen Verwaltungsrolle Store (CMS) besteht. Außerdem installieren Sie einen Domänencontroller, der für die interne Funktion von Cloud Connector erforderlich ist. Diese Dienste sind für die Hybridbereitstellung mit Ihrer Microsoft 365 oder Office 365 Organisation konfiguriert, die Skype for Business Onlinedienste umfasst.

![Cloud Connector Edition-Komponenten.](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Cloud Connector-Komponenten bieten die folgenden Funktionen:

- **Edgekomponente** – Die Kommunikation zwischen der lokalen Topologie und den Onlinediensten erfolgt über die Edgekomponente, die die folgenden Komponenten umfasst:

  - **Zugriffs-Edge** : Stellt SIP-Routing zwischen der lokalen Bereitstellung und Skype for Business Online bereit.

  - **MediaRelay** : Stellt das Routing von Medien zwischen der Vermittlungskomponente und anderen Medienendpunkten bereit.

  - **MediaRelay-Authentifizierung/MRAS** : Generiert Token für den Zugriff auf Das Medienrelay.

- **Ausgehendes Routing** – Bietet einen Lastenausgleich des VoIP-Datenverkehrs zwischen Gateways oder SBCs, die mit einer Cloud Connector-Appliance verbunden sind. Anrufe werden gleichmäßig zwischen allen Gateways oder SBCs aufgeteilt, die mit der Cloud Connector-Appliance verbunden sind.

    Stellt Das Routing an Gateways basierend auf Richtlinien bereit. Es werden nur globale Richtlinien unterstützt, die auf zielbasierten (ausgehenden) PSTN-Nummern basieren.

- **Rolle "Zentrale Verwaltung Store ( CMS)** – Umfasst den Konfigurationsspeicher für die Topologiekomponenten, einschließlich der CMS-Dateiübertragung.

- **Cms-Replikat (Central Management Store):** Synchronisiert Konfigurationsinformationen aus der globalen CMS-DATENBANK auf dem CMS-Rollenserver.

- **Domänencontroller** – Cloud Connector Active Directory Domain Services zum Speichern aller globalen Einstellungen und Gruppen, die zum Bereitstellen von Cloud Connector-Komponenten erforderlich sind. Für jede Cloud Connector-Appliance wird eine Gesamtstruktur erstellt. Der Domänencontroller darf keine Verbindungen mit dem Produktions-Active Directory haben. Active Directory-Dienste umfassen:

  - Active Directory Domain Services

  - Active Directory-Zertifikatdienste zum Ausstellen interner Zertifikate

- **Vermittlungskomponente** – Implementiert das SIP- und Mediengatewayzuordnungsprotokoll zwischen Skype for Business und PSTN-Gateways. Enthält ein CMS-Replikat, das die Konfiguration aus der globalen CMS-Datenbank synchronisiert.

## <a name="cloud-connector-edition-topologies"></a>Cloud Connector Edition-Topologien
<a name="BKMK_Topologies"> </a>

Im Zusammenhang mit dieser Erläuterung beziehen wir uns auf PSTN-Standorte. Ein PSTN-Standort ist eine Kombination aus Cloud Connector-Appliances, die am gleichen Standort bereitgestellt werden und mit allgemeinen PSTN-Gateways verbunden sind. PSTN-Standorte ermöglichen Folgendes:

- Stellen Sie Verbindungen zu Gateways bereit, die Ihren Benutzern am nächsten sind.

- Ermöglichen Sie Skalierbarkeit, indem Sie mehrere Cloud Connector-Appliances an einem oder mehreren PSTN-Standorten bereitstellen.

- Hohe Verfügbarkeit durch Bereitstellung mehrerer Cloud Connector-Appliances an einem einzelnen PSTN-Standort zulassen.

In diesem Thema werden PSTN-Standorte vorgestellt. Weitere Informationen zur Planung Ihrer PSTN-Standorte finden Sie unter [Plan for Cloud Connector Edition PSTN sites.](plan-for-cloud-connector-edition-pstn-sites.md)

Sie können die folgenden Cloud Connector-Topologien bereitstellen:

- Eine einzelne Cloud Connector Edition-Appliance pro PSTN-Standort. Diese Topologie wird nur zu Evaluierungszwecken empfohlen, da sie keine hohe Verfügbarkeit bietet.

- Mehrere Cloud Connector Edition-Appliances pro PSTN-Standort für hohe Verfügbarkeit.

- Mehrere PSTN-Standorte mit mehreren Cloud Connector Edition-Appliances zur Bereitstellung von Skalierbarkeit mit hoher Verfügbarkeit. Sie können bis zu 200 Standorte bereitstellen.

Berücksichtigen Sie bei der Planung Ihrer Topologie Folgendes:

- Mit Cloud Connector 2.0 und höher kann ein PSTN-Standort bis zu 16 Cloud Connector-Appliances aufweisen. In früheren Versionen werden bis zu vier Appliances pro Standort unterstützt.

- Es gibt zwei Arten von Hardwarekonfigurationen, die mit Cloud Connector getestet wurden:

  - Die größere Version kann große Mengen gleichzeitiger Anrufe verarbeiten und wird in allen Arten von Produktionsumgebungen unterstützt.

  - Die kleinere Version ist für die Ausführung auf Niedriger-End-Hardware vorgesehen und kann für Evaluierungszwecke oder für Standorte mit geringem Anrufvolumen verwendet werden. Wenn Sie eine kleinere Version von Cloud Connector bereitstellen, müssen Sie dennoch die Hardwareanforderungen der Produktionsklasse berücksichtigen (z. B. duale Stromversorgung).

- Wenn Sie über Cloud Connector Version 2.0 oder höher verfügen und die maximale Konfiguration von 16 Appliances (mit größerer Hardware) bereitstellen, kann Ihr PSTN-Standort bis zu 8.000 gleichzeitige Anrufe verarbeiten. Wenn Sie die kleinere Version bereitstellen, beträgt der unterstützte Grenzwert 800.

    Außerdem müssen Sie einige Appliances für hohe Verfügbarkeit verwenden. Die minimale Empfehlung ist, dass eine Appliance für hohe Verfügbarkeit reserviert werden soll.

  - Wenn Sie mit Version 2 eine 15+1-Konfiguration bereitstellen, kann Ihr PSTN-Standort bis zu 7.500 anrufe gleichzeitig verarbeiten.

  - Wenn Sie über eine frühere Version verfügen und die maximale Konfiguration von 3 + 1 (mit größerer Hardware) bereitstellen, kann Ihr PSTN-Standort bis zu 1500 gleichzeitige Anrufe verarbeiten. Wenn Sie die kleinere Version bereitstellen, beträgt der unterstützte Grenzwert 150.

-  Wenn Sie mehr Anrufe pro PSTN-Standort benötigen, können Sie eine Skalierung durchführen, indem Sie zusätzliche PSTN-Standorte am selben Standort bereitstellen.

> [!NOTE]
> Sofern nicht anders angegeben, wird in den folgenden Diagrammen und Beispielen davon ausgegangen, dass die größere Version von Cloud Connector verwendet wird.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Einzelne Cloud Connector-Appliance an einem einzelnen PSTN-Standort

Das folgende Diagramm zeigt eine einzelne Cloud Connector Edition-Appliance an einem einzelnen PSTN-Standort. Beachten Sie, dass Cloud Connector aus vier VMs besteht, die auf einem physischen Hostcomputer installiert sind, der sich aus Sicherheitsgründen in einem Umkreisnetzwerk befindet.

![Ein Cloud Connector mit einem PSTN-Standort.](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Mehrere Cloud Connector-Appliances an einem einzelnen PSTN-Standort

 Aus Gründen der Skalierbarkeit und hohen Verfügbarkeit können Sie mehrere Cloud Connector Editionen an einem einzelnen PSTN-Standort verwenden, wie im folgenden Diagramm dargestellt. Dabei ist Folgendes zu berücksichtigen:

- Anrufe werden in zufälliger Reihenfolge zwischen Cloud Connectors in einem Pool verteilt.

- Für die Kapazitätsplanung müssen Sie die Möglichkeit in Betracht ziehen, die Last zu verarbeiten, wenn ein oder mehrere Cloud Connectors offline gehen, basierend auf den folgenden Berechnungen:

  - **N+1 Felder.** Für die größere Version von Cloud Connector unterstützen N+1-Felder 500 \* N gleichzeitige Anrufe mit einer Verfügbarkeit von 99,8 %.

    Für die kleinere Version von Cloud Connector unterstützen N+1-Felder 50 \* N gleichzeitige Anrufe mit einer Verfügbarkeit von 99,8 %.

  - **N+2 Felder.** Für die größere Version von Cloud Connector unterstützen N+2-Felder 500 \* N gleichzeitige Anrufe mit einer Verfügbarkeit von 99,9 %.

    Für die kleinere Version von Cloud Connector unterstützen N+2-Felder 50 \* N gleichzeitige Anrufe mit einer Verfügbarkeit von 99,9 %.

![Zwei Cloud Connectors an einem PSTN-Standort.](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Mehrere PSTN-Standorte mit einem oder mehreren Cloud Connectors pro Standort

Sie können auch mehrere PSTN-Standorte mit einer oder mehreren Cloud Connector Editionen an jedem Standort verwenden. Wenn Ihr PSTN-Standort die Grenze für gleichzeitige Anrufe erreicht, können Sie einen weiteren PSTN-Standort hinzufügen, um die Last zu verarbeiten.

Mit mehreren PSTN-Standorten können Sie auch Verbindungen mit Gateways bereitstellen, die Ihren Benutzern am nächsten sind. Angenommen, Sie verfügen über PSTN-Gateways in Seattle und Amsterdam. Sie können zwei PSTN-Standorte bereitstellen – einen in Seattle, einen in Amsterdam – und Benutzern die Verwendung des PSTN-Standorts zuweisen, der ihnen am nächsten ist. Benutzer aus Seattle werden an den PSTN-Standort und die Gateways von Seattle weitergeleitet, während Benutzer in Amsterdam an den PSTN-Standort und die Gateways in Amsterdam weitergeleitet werden:

![Cloud Connector Edition innerhalb von 2 PSTN-Standorten.](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Anforderungen für die Bereitstellung
<a name="BKMK_Requirements"> </a>

Bevor Sie Cloud Connector Edition bereitstellen, stellen Sie sicher, dass Sie für Ihre Umgebung über Folgendes verfügen:

- **Für den Hostcomputer –** Cloud Connector-VMs müssen auf dedizierter Hardware bereitgestellt werden, die Windows Server 2012 R2 Datacenter Edition (Englisch) ausgeführt wird, wobei die Hyper-V-Rolle aktiviert ist.

    Für Version 2.0 und höher muss die Netzwerkkarte des Hostcomputers, die an den Skype for Business Corpnet-Switch gebunden ist, über eine IP-Adresse verfügen, die im selben Subnetz wie die Cloud Connector-Unternehmensnetzwerkcomputer konfiguriert ist.

- Für Die Versionen 2.1 und höher muss in der Host-Appliance .NET Framework 4.6.1 oder höher installiert sein.

- **Für die virtuellen Computer –** A Windows Server 2012 R2 ISO (English) image (.iso). Die ISO wird für die virtuellen Computer, die Skype for Business Cloud Connector Edition ausgeführt werden, in VHDs konvertiert.

- Die erforderliche Hardware zur Unterstützung der Installation der vier virtuellen Computer für jede Cloud Connector Edition in Ihrer Bereitstellung. Die folgenden Konfigurationen werden empfohlen:

  - 64-Bit-Dualprozessor, sechs Kerne (12 echte Kerne), 2,50 gHz oder höher

  - 64 Gigabyte (GB) ECC-RAM

  - Vier Festplatten mit 600 GB (oder höher) 10.000 U/min 128M Cache SAS 6 GBit/s, konfiguriert in einer RAID 5-Konfiguration

  - Drei 1 GBit/s RJ45-Netzwerkadapter mit hohem Durchsatz

- Wenn Sie die kleinere Version von Cloud Connector Edition bereitstellen möchten, die bis zu 50 gleichzeitige Anrufe unterstützt, benötigen Sie die folgende Hardware:

  - Intel i7 4790 Quad Core mit Intel 4600 Graphics (keine High-End-Grafiken erforderlich)

  - 32 GB BETRIEBSSYSTEM3-1600 nicht ECC

  - 2: 1 TB 7200RPM SATA III (6 GBit/s) in RAID 0

  - 2: 1 GBit/s Ethernet (RJ45)

- Wenn ein Proxyserver auf dem Hostcomputer zum Durchsuchen des Internets erforderlich ist, müssen Sie die folgenden Konfigurationsänderungen vornehmen:

  - Um den Proxy zu umgehen, geben Sie winHTTP-Proxyeinstellungen an, die mit Ihrem Proxyserver festgelegt wurden, sowie eine Umgehungsliste einschließlich "192.168.213". \* Netzwerk, das von Ihren Cloud Connector Managements-Diensten und Skype for Business Corpnet-Subnetz gemäß definition in Ihrer CloudConnector.ini-Datei verwendet wird. Andernfalls schlägt die Verwaltungskonnektivität fehl und verhindert die Bereitstellung und automatische Wiederherstellung von Cloud Connector. Es folgt ein Beispiel für einen Winhttp-Konfigurationsbefehl: netsh winhttp set proxy "10.10.10.175:8080" bypass-list=" \* .local;1. \* 172.20. \* ;192.168.218. \* ' \<local\> ".

  - Geben Sie Proxyeinstellungen pro Computer und nicht pro Benutzer an. Andernfalls schlagen Cloud Connector-Downloads fehl. Sie können Proxyeinstellungen pro Computer mit einer Registrierungsänderung oder mit der Gruppenrichtlinieneinstellung wie folgt angeben:

  - **Registry:** HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings] ProxySettingsPerUser dword: 00000000

  - **Gruppenrichtlinie:** Administrative Vorlagen für Computer \> Windows Komponenten von Internet \> \> Explorer: Proxyeinstellungen pro Computer (statt pro Benutzer)

- Qualifizierte Nebenstellenanlage/Trunk oder qualifizierter SBC/Gateway (es werden mindestens zwei Gateways empfohlen).

    Cloud Connector unterstützt die gleichen Session Border Controller (SBCs), die für Skype for Business zertifiziert sind. Weitere Informationen finden Sie unter [Telefonieinfrastruktur für Skype for Business.](../../../SfbPartnerCertification/certification/infra-gateways.md)

- Ein lokales Serveradministratorkonto mit Berechtigungen zum Installieren und Konfigurieren von Hyper-V auf den Hostservern. Das Konto muss über Administratorberechtigungen auf dem lokalen Server verfügen, auf dem Hyper-V installiert und konfiguriert ist.

- Während der Bereitstellung werden Sie aufgefordert, ein Domänenadministratorkonto mit Berechtigungen zum Erstellen und Veröffentlichen der Topologie in der Cloud Connector-Domäne zu erstellen.

- Die externen DNS-Einträge, die in der CloudConnector.ini-Datei definiert sind, die im Installationspaket enthalten ist:

  - Externer DNS-Eintrag für den Zugriffs-Edgedienst der Edgekomponente; Beispiel: ap. \<Domain Name\> . Sie benötigen einen Datensatz pro PSTN-Standort. Dieser Datensatz muss IP-Adressen aller Edges für diesen Standort enthalten.

- Eine Microsoft 365 oder Office 365 Organisation, in der alle erforderlichen DNS- und SRV-Einträge erstellt wurden.

    > [!IMPORTANT]
    > Wenn Sie Ihren Mandanten in Cloud Connector Edition integrieren, wird die Verwendung des Standarddomänensuffixs .onmicrosoft.com als SIP-Domäne für Ihre Organisation nicht unterstützt. > Sip kann nicht verwendet werden.\<Domain Name\> als Name der Cloud Connector Edge Access-Proxyschnittstelle, da dieser DNS-Eintrag von Microsoft 365 und Office 365 verwendet wird.

- Ein Zertifikat für den externen Edgeserver, der von einer öffentlichen Zertifizierungsstelle (Ca) abgerufen wurde.

- Firewallregeln zum Zulassen von Datenverkehr über die erforderlichen Ports wurden abgeschlossen.

- Eine Internetverbindung für den Hostcomputer und die virtuellen Computer. Cloud Connector lädt Software aus dem Internet herunter. Daher müssen Sie Gateway- und DNS-Serverinformationen bereitstellen, damit der Cloud Connector-Hostcomputer und VMs eine Verbindung mit dem Internet herstellen und die erforderliche Software herunterladen können.

- Ein auf dem Hostcomputer installiertes Mandanten-Remote-PowerShell-Modul.

- Die Skype for Business Administratoranmeldeinformationen zum Ausführen von Remote-PowerShell.

    > [!IMPORTANT]
    > Für das Administratorkonto DARF die mehrstufige Authentifizierung NICHT aktiviert sein.

> [!NOTE]
> Die Cloud Connector-Bereitstellung wird nur auf der Microsoft Hyper-V virtualisierten Plattform unterstützt. Andere Plattformen wie VMware und Amazon Web Services werden nicht unterstützt.

> [!NOTE]
> Die Mindesthardwareanleitung für die Ausführung von Cloud Connector basiert auf der grundlegenden Hardwarekapazität (Kerne, MHz, Gigabyte usw.) mit einem Puffer, um leistungsbeeinträchtigungen zu beheben, die in der Architektur eines beliebigen Computers auftreten. Microsoft hat Auslastungstests für den schlechtesten Fall auf kommerziell verfügbarer Hardware ausgeführt, um die Mindestanforderungen zu erfüllen. Medienqualität und Systemleistung werden überprüft. Offizielle Cloud Connector-Appliance-Partner von Microsoft verfügen über spezifische Cloud Connector-Hardwareimplementierungen, auf denen sie die Leistung unabhängig getestet haben und sich an der Eignung ihrer Hardware zur Erfüllung von Last- und Qualitätsanforderungen halten.

> [!NOTE]
> Von AudioCodes und Sonus produzierte Geräte haben Code geändert und werden auf Windows ServerStandard Edition von Servern ausgeführt. Diese Geräte werden unterstützt.

## <a name="information-you-need-to-gather-before-deployment"></a>Informationen, die Sie vor der Bereitstellung sammeln müssen
<a name="BKMK_PlanDeployment"> </a>

Bevor Sie mit der Bereitstellung beginnen, müssen Sie die Größe Ihrer Bereitstellung, die sip-Domänen, die gewartet werden, und die Konfigurationsinformationen für jeden PSTN-Standort ermitteln, den Sie bereitstellen möchten. Zunächst führen Sie Folgendes aus:

- Identifizieren Sie alle SIP-Domänen, die von dieser Bereitstellung basierend auf den in Ihrem Unternehmen verwendeten SIP-URIs bedient werden.

- Ermitteln Sie die Anzahl der PSTN-Standorte, die Sie bereitstellen müssen.

- Stellen Sie sicher, dass Sie über die erforderliche Hardware verfügen, um die vier VMs zu unterstützen, die Sie für jede Cloud Connector Edition installieren werden.

Für jeden PSTN-Standort, den Sie bereitstellen möchten, müssen Sie:

- Erstellen Sie Namen für alle Komponenten in jeder Cloud Connector-Appliance (siehe [Bereitstellungsparameter ermitteln).](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)

- Definieren von Portbereichen (siehe [Ports und Protokolle).](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)

- Erstellen externer DNS-Einträge für die Edgekomponente (siehe [Anforderungen für die Bereitstellung).](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- Ermitteln Sie Die Zertifikatanforderungen für die Edgekomponente (siehe [Zertifikatanforderungen).](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)

### <a name="ports-and-protocols"></a>Ports und Protokolle
<a name="BKMB_Ports"> </a>

Beachten Sie beim Definieren von Medienportbereichen Folgendes:

- Clients verwenden immer den Portbereich 50000 bis 50019 für Mediendatenverkehr . Dieser Bereich ist in Skype for Business Online vordefiniert und kann nicht geändert werden.

- Die Vermittlungskomponente verwendet standardmäßig den Portbereich 49 152 bis 57 500 für Mediendatenverkehr. Die Verbindung wird jedoch über eine interne Firewall hergestellt, und aus Sicherheitsgründen können Sie diesen Portbereich in Ihrer Topologie einschränken. Sie benötigen bis zu vier Ports pro Anruf. Wenn Sie die Anzahl der Ports zwischen der Vermittlungskomponente und dem PSTN-Gateway einschränken möchten, müssen Sie auch den entsprechenden Portbereich auf dem Gateway konfigurieren.

- Sie müssen Cloud Connector in einem Umkreisnetzwerk bereitstellen. Dies bedeutet, dass Sie über zwei Firewalls verfügen:

  - Die erste Firewall ist extern zwischen dem Internet und Ihrem Umkreisnetzwerk.

  - Die zweite Firewall ist intern zwischen dem Umkreisnetzwerk und Ihrem internen Netzwerk.

    Ihre Clients können sich im Internet oder im internen Netzwerk befinden:

  - Clients im Internet stellen über die externe Firewall über die Edgekomponente eine Verbindung mit Ihrem PSTN her.

  - Clients im internen Netzwerk stellen über die interne Firewall eine Verbindung mit der Vermittlungskomponente im Umkreisnetzwerk her, die den Datenverkehr mit dem SBC- oder PSTN-Gateway verbindet.

    Dies bedeutet, dass Sie Ports in beiden Firewalls öffnen müssen.

In den folgenden Tabellen werden die Ports und Portbereiche für die externen und internen Firewalls beschrieben.

In dieser Tabelle sind die Ports und Portbereiche aufgeführt, um die Kommunikation zwischen Clients im internen Netzwerk und der Vermittlungskomponente zu ermöglichen:

**Interne Firewall**



|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Cloud Connector-Vermittlungskomponente  <br/> |SBC/PSTN-Gateway  <br/> |Beliebig  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN-Gateway  <br/> |Cloud Connector-Vermittlungskomponente  <br/> |Beliebig  <br/> |TCP 5068/ TLS 5067  <br/> |
|Cloud Connector-Vermittlungskomponente  <br/> |SBC/PSTN-Gateway  <br/> |UDP 49 152 - 57 500  <br/> |Jegliche\*\*\*  <br/> |
|SBC/PSTN-Gateway  <br/> |Cloud Connector-Vermittlungskomponente  <br/> |Jegliche\*\*\*  <br/> |UDP 49 152 - 57 500  <br/> |
|Cloud Connector-Vermittlungskomponente  <br/> |Interne Clients  <br/> |TCP 49 152 - 57 500\*  <br/> |TCP 50.000-50.019  <br/> (Optional)  <br/> |
|Cloud Connector-Vermittlungskomponente  <br/> |Interne Clients  <br/> |UDP 49 152 - 57 500\*  <br/> |UDP 50.000-50.019  <br/> |
|Interne Clients  <br/> |Cloud Connector-Vermittlungskomponente  <br/> |TCP 50.000-50.019  <br/> |TCP 49 152 - 57 500\*  <br/> |
|Interne Clients  <br/> |Cloud Connector-Vermittlungskomponente  <br/> |UDP 50.000-50.019  <br/> |UDP 49 152 -57 500\*  <br/> |

\* Dies ist der Standardportbereich der Vermittlungskomponente. Für einen optimalen Anruffluss sind vier Ports pro Anruf erforderlich.

\*\* Dieser Port muss auf dem SBC/PSTN-Gateway konfiguriert werden. 5060 ist ein Beispiel. Sie können andere Ports auf Ihrem SBC/PSTN-Gateway konfigurieren.

\*\*\* Beachten Sie, dass Sie auch den Portbereich auf Ihrem SBC/Gateway einschränken können, wenn dies vom SBC/Gateway-Hersteller zulässig ist.

Aus Sicherheitsgründen können Sie den Portbereich für die Vermittlungskomponente mithilfe des Cmdlets ["Set-CsMediationServer"](/powershell/module/skype/set-csmediationserver?) einschränken.

Der folgende Befehl beschränkt beispielsweise die Anzahl der Ports, die die Vermittlungskomponente für Mediendatenverkehr verwendet, auf 50 000 bis 51 000 für Audio (ein und aus). Die Vermittlungskomponente kann 250 gleichzeitige Anrufe mit dieser Konfiguration verarbeiten. Beachten Sie, dass Sie diesen Bereich auch auf dem SBC/PSTN-Gateway einschränken möchten:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Um den Namen der Vermittlungskomponente abzurufen und die Standardports anzuzeigen, können Sie das Cmdlet ["Get-CsService"](/powershell/module/skype/get-csservice?) wie folgt verwenden:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

In der folgenden Tabelle sind Ports und Portbereiche aufgeführt, um die Kommunikation zwischen der Cloud Connector Edge-Komponente und der externen Firewall zu ermöglichen. Diese Tabelle enthält eine Mindestempfehlung.

In diesem Fall fließt der gesamte Mediendatenverkehr ins Internet über den Online-Edge wie folgt: Benutzerendpunkt - Online Edge \> - \> Cloud Connector Edge:

**Externe Firewall – Mindestkonfiguration**



|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Beliebig  <br/> |Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |TCP(MTLS) 5061  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP(MTLS) 5061  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP 80  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |Beliebig  <br/> |UDP 53  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP 53  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Beliebig  <br/> |Externe Cloud Connector Edge-Schnittstelle  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
|Beliebig  <br/> |Externe Cloud Connector Edge-Schnittstelle  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |

In der nächsten Tabelle sind Ports und Portbereiche aufgeführt, um die Kommunikation zwischen der Cloud Connector Edge-Komponente und der externen Firewall zu ermöglichen. Diese Tabelle zeigt die empfohlene Lösung.

In diesem Fall kann der gesamte Mediendatenverkehr für den Endpunkt im Internet direkt an die Cloud Connector Edge-Komponente fließen. Der Medienpfad ist der Endpunkt des Benutzers – \> Cloud Connector Edge.

> [!NOTE]
> Diese Lösung funktioniert nicht, wenn sich der Endpunkt des Benutzers hinter einer symmetrischen NAT befindet.

**Externe Firewall – empfohlene Konfiguration**


|**Quell-IP**|**Ziel-IP**|**Quellport**|**Zielport**|
|:-----|:-----|:-----|:-----|
|Beliebig  <br/> |Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |TCP(MTLS) 5061  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP(MTLS) 5061  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP 80  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |Beliebig  <br/> |UDP 53  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |Beliebig  <br/> |TCP 53  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |TCP 50.000-59.999  <br/> |Beliebig  <br/> |
|Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |UDP 3478; UDP 50.000-59.999  <br/> |Beliebig  <br/> |
|Beliebig  <br/> |Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |TCP 443; TCP 50.000-59.999  <br/> |
|Beliebig  <br/> |Externe Cloud Connector Edge-Schnittstelle  <br/> |Beliebig  <br/> |UDP 3478; UDP 50.000 - 59.999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Anforderungen an die Internetverbindung von Hosts
<a name="BKMB_Ports"> </a>

Der Hostcomputer muss in der Lage sein, externe Ressourcen zu erreichen, um Cloud Connector erfolgreich zu installieren, zu aktualisieren und zu verwalten. In der folgenden Tabelle sind die Ziele und Ports aufgeführt, die zwischen dem Hostcomputer und externen Ressourcen erforderlich sind.

|Richtung  <br/> |Quell-IP  <br/> |Ziel-IP  <br/> |Quellport  <br/> |Zielport  <br/> |Protokoll  <br/> |Zweck  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ausgehend  <br/> |Cloud Connector-Host-IPs  <br/> |Beliebiger Wert  <br/> |Beliebiger Wert  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Ausgehend  <br/> |Cloud Connector-Host-IPs  <br/> |Beliebiger Wert  <br/> |Beliebiger Wert  <br/> |80, 443  <br/> |TCP  <br/> |Zertifikatsperrliste (Certificate Revocation List, CRL)  <br/> |
|Ausgehend  <br/> |Cloud Connector-Host-IPs  <br/> |Beliebiger Wert  <br/> |Beliebiger Wert  <br/> |80, 443  <br/> |TCP  <br/> |Cloud Connector-Update  <br/> Skype for Business Online  <br/> Administrator-PowerShell  <br/> Windows Update  <br/> |

Wenn restriktivere Regeln erforderlich sind, lesen Sie die folgenden Allowlist-URLs:

- [URLs der Zertifikatsperrliste](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) in [Office 365 URLs und IP-Adressbereichen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [Verwalten zusätzlicher Windows Updateeinstellungen](/windows/deployment/update/waas-wu-settings)

- Skype for Business PowerShell für Onlineadministratoren: \* .online.lync.com

    Wenn Sie einen Proxyausschluss für dieses Ziel benötigen, müssen Sie ihn der WinHTTP-Umgehungsliste hinzufügen.

- Cloud Connector Update: [Download Center](https://aka.ms/CloudConnectorInstaller) [https://go.microsoft.com](https://go.microsoft.com) und [https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>DNS-Namensauflösung für die Edgekomponente
<a name="BKMB_Ports"> </a>

Die Edgekomponente muss die externen Namen von Microsoft 365 oder Office 365 Diensten und die internen Namen anderer Cloud Connector-Komponenten auflösen.

Bei jeder Edgekomponente handelt es sich um einen Computer mit mehreren Verwalteten Computern mit externen und internen Schnittstellen. Cloud Connector stellt DNS-Server auf der Domänencontrollerkomponente innerhalb des Umkreisnetzwerks bereit. Sie können den Edgeserver für alle Namensauflösungen auf den DNS-Server innerhalb des Umkreiss verweisen, aber Sie müssen den Cloud Connector-DNS-Server aktivieren, um externe Namen aufzulösen, indem Sie eine DNS-Zone festlegen, die einen oder mehrere DNS A-Einträge für externe Abfragen enthält, die namensuche auf andere öffentliche DNS-Server verweisen.

Wenn Sie in der .ini Datei den FQDN-Namen für Gateways aus demselben Domänenbereich wie Ihre SIP-Domäne festlegen, wird die autorisierende Zone für diese SIP-Domäne im DNS-Server innerhalb des Umkreisbereichs erstellt. Wenn der Edgeserver auf diesen DNS-Server verweist, um Namen aufzulösen, löst Edge die _sipfederationtls nie auf.\<yourdomain\> DNS-Eintrag, der für den Anruffluss erforderlich ist. In diesem Fall empfiehlt Microsoft, dass Sie einen DNS-Server auf der externen Edgeschnittstelle bereitstellen, um Internetnamenssuchvorgänge aufzulösen, und jede Edgekomponente muss eine HOST-Datei verwenden, um andere Cloud Connector-Komponentennamen in IP-Adressen aufzulösen.

> [!NOTE]
> Aus Sicherheitsgründen wird empfohlen, den Cloud Connector-DNS-Server nicht zur Namensauflösung auf interne Server in der Produktionsdomäne zu verweisen.

### <a name="determine-deployment-parameters"></a>Ermitteln von Bereitstellungsparametern
<a name="BKMK_SiteParams"> </a>

Zunächst müssen Sie die folgenden allgemeinen Bereitstellungsparameter definieren:


|**Item**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|SIP-Domänen  <br/> |SIP-URIs, die von Unternehmensbenutzern verwendet werden. Stellen Sie alle SIP-Domänen bereit, die von dieser Bereitstellung bedient werden. Sie können über mehrere SIP-Domänen verfügen.  <br/> ||
|Anzahl der PSTN-Standorte  <br/> |Die Anzahl der PSTN-Standorte, die Sie bereitstellen werden.  <br/> ||

Für jeden PSTN-Standort, den Sie bereitstellen möchten, müssen Sie die folgenden Informationen sammeln, bevor Sie mit der Bereitstellung beginnen. Sie müssen diese Informationen angeben, wenn Sie die CloudConnector.ini-Datei aktualisieren.

Beachten Sie beim Konfigurieren von Gatewayinformationen Folgendes:

- Wenn Sie nur über ein Gateway verfügen, entfernen Sie den Abschnitt in der .ini-Datei für das zweite Gateway. Wenn mehr als zwei Gateways vorhanden sind, folgen Sie dem vorhandenen Format, um neue Gateways hinzuzufügen.

- Stellen Sie sicher, dass die IP-Adresse und der Port der Gateways korrekt sind.

- Um HA auf PSTN-Gatewayebene zu unterstützen, behalten Sie das sekundäre Gateway bei, oder fügen Sie zusätzliche Gateways hinzu.

(Optional) Um die ausgehenden Anrufnummern einzuschränken, aktualisieren Sie den LocalRoute-Wert.



|**Websiteparameter**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|Domänenname des virtuellen Computers  <br/> |Domänenname für die internen Komponenten von Cloud Connector. Diese Domäne muss sich von der Produktionsdomäne unterscheiden. Der Name muss in allen Cloud Connector-Appliances identisch sein.  <br/> Name in .ini Datei: "VirtualMachineDomain"  <br/> |.local domain is preferred.  <br/> |
|Name des Cloud Connector-Domänencontrollers  <br/> |Name des Domänencontrollers.  <br/> Name in .ini Datei: "ServerName"  <br/> |Darf maximal 15 Zeichen lang sein. Geben Sie nur den Netbios-Namen ein.  <br/> |
|Ip-/Subnetzmaske des Cloud Connector-Domänencontrollers  <br/> |IP-Adresse des Domänencontrollers.  <br/> Name in .ini Datei: "IP"  <br/> ||
|FQDNs für Microsoft 365 oder Office 365 Onlinedienst  <br/> |Muss in den meisten Fällen der Standardwert für die weltweite Microsoft 365 oder Office 365 Instanz sein.  <br/> Name in .ini Datei: "OnlineSipFederationFqdn"  <br/> ||
|Sitename  <br/> |Skype for Business Websitename; Beispiel: Seattle.  <br/> Name in .ini Datei: "SiteName"  <br/> Für Version 1.4.1 und höher muss der Standortname für jeden Standort unterschiedlich sein, und der Name muss mit dem PSTN-Standort übereinstimmen( falls vorhanden), der in Microsoft 365 oder Office 365 definiert ist. Beachten Sie, dass PSTN-Standorte automatisch erstellt werden, wenn Sie die erste Appliance an einem Standort registrieren.  <br/> ||
|HardwareType  <br/> Version 1.4.1 und höher  <br/> |Typ der Hardware. Der Standardwert ist "Normal". Sie können auch auf Minimum festlegen.  <br/> ||
|Country Code  <br/> |Landesvorwahl für die Wählfunktion.  <br/> Name in .ini Datei: "CountryCode"  <br/> ||
|Stadt  <br/> |Ort (optional).  <br/> Name in .ini Datei: "Ort"  <br/> ||
|Status  <br/> |Status (optional).  <br/> Name in .ini Datei: "State"  <br/> ||
|BASIS-VM-IP-Adresse  <br/> |Die IP-Adresse der temporären Basis-VM, die zum Erstellen der VHDX für alle virtuellen Cloud Connector-Computer verwendet wird. Diese IP muss sich im gleichen Umkreis-Unternehmensnetzwerk-Subnetz befinden, das im nächsten Schritt definiert ist, und erfordert Internetzugriff. Achten Sie darauf, das Standardgateway des Unternehmens und das DNS zu definieren, das in das Internet umleitbar ist.  <br/> Name in .ini Datei: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 und höher  <br/> |Die Adresse des Windows Server Update Services (WSUS) – ein Intranetserver zum Hosten von Updates von Microsoft Update.  <br/> Sie können keinen Wert angeben, wenn WSUS nicht benötigt wird.  <br/> ||
|Subnetzmaske für internes Netzwerk  <br/> |Cloud Connector konfiguriert ein IP-Netzwerk für die interne Kommunikation zwischen Cloud Connector-Komponenten. Edge muss auch mit einem anderen Subnetz verbunden sein, das eine Internetverbindung ermöglicht.  <br/> Name in .ini Datei: "CorpnetIPPrefixLength" unter "Parameters for a pool of VM network"  <br/> ||
|Subnetzmaske für externes Netzwerk  <br/> |Für das externe Netzwerk der Edgekomponente.  <br/> Name in .ini Datei: "InternetIPPrefix" unter "Parameters for a pool of VM network"  <br/> ||
|Switchname für internes Netzwerk  <br/> |Name für den Switch, der für das interne Cloud Connector-Netzwerk verwendet wird.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in .ini Datei: "CorpnetSwitchName" unter "Parameters for a pool of VM network"  <br/> ||
|Switchname für externes Netzwerk  <br/> |Name für den Switch, der für das externe Cloud Connector-Netzwerk verwendet wird.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in .ini Datei: "InternetSwitchName" unter "Parameters for a pool of VM network" (Parameter für einen Pool des VM-Netzwerks)  <br/> ||
|Standardgateway für internes Netzwerk  <br/> |Dieses Gateway muss Zugriff auf das Internet bieten (internet erfordert auch das Festlegen des DNS-Servers) und wird auf internen Schnittstellen von Cloud Connector-Komponenten konfiguriert.  <br/> Name in .ini Datei: "CorpnetDefaultGateway" unter "Parameters for a pool of VM network" (Parameter für einen Pool des VM-Netzwerks)  <br/> ||
|Standardgateway für externe Schnittstelle der Edgekomponente  <br/> |Wird auf der externen Schnittstelle der Edgekomponente konfiguriert.  <br/> Name in .ini Datei: "InternetDefaultGateway" unter "Parameters for a pool of VM network"  <br/> ||
|DNS-Server für internes Netzwerk  <br/> |Wird auf der internen Schnittstelle des temporären virtuellen Computers konfiguriert. Muss die Namensauflösung für Internetnamen bereitstellen. Ohne Angabe eines DNS-Servers schlägt die Internetverbindung fehl, und die Bereitstellung wird nicht abgeschlossen.  <br/> Name in .ini Datei: "CorpnetDNSIPAddress" unter "Parameters for a pool of VM network"  <br/> ||
|DNS-Server für externe Schnittstelle der Edgekomponente  <br/> |Wird auf der externen Schnittstelle von Edge konfiguriert.  <br/> Name in .ini Datei: "InternetDNSIPAddress" unter "Parameters for a pool of VM network"  <br/> ||
|Name des Verwaltungsschalters  <br/> |Der Verwaltungsschalter ist ein temporärer Switch, der automatisch erstellt wird und während der Bereitstellung für die Konfiguration von Cloud Connector verwendet wird. Nach der Bereitstellung wird die Verbindung automatisch getrennt. Es muss ein anderes Subnetz als alle anderen Netzwerke sein, die in Cloud Connector verwendet werden.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in .ini Datei: "ManagementSwitchName" unter "Parameters for a pool of VM network"  <br/> ||
|Verwaltungssubnetzadresse/Subnetzmaske  <br/> |Das Verwaltungssubnetz ist ein temporäres Subnetz, das automatisch erstellt wird und während der Bereitstellung für die Konfiguration von Cloud Connector verwendet wird. Sie wird nach der Bereitstellung automatisch entfernt. Es muss ein anderes Subnetz als alle anderen Netzwerke sein, die in Cloud Connector verwendet werden.  <br/> Namen in .ini Datei: "ManagementIPPrefix" und "ManagementIPPrefixLength" unter "Parameters for a pool of VM network"  <br/> ||
|Central Management Store (CMS)-Computer  <br/> |Single FQDN used for Central Management Store (CMS). Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "ServerName" unter "Parameters for Primary Central Management Service"  <br/> |Darf maximal 15 Zeichen lang sein. Geben Sie nur den Netbios-Namen ein.  <br/> (CMS-Poolname = Servername)  <br/> |
|CMS-Computer-IP-Adresse  <br/> |IP-Adresse für CMS-Server (intern im Umkreisnetzwerk).  <br/> Name in der INI-Datei: "IP" unter "Parameters for Primary Central Management Service" (Parameter für den primären zentralen Verwaltungsdienst)  <br/> ||
|Dateifreigabename  <br/> |Dateifreigabename, der auf dem CMS-Server für Skype for Business Replikationsdaten (z. B. CmsFileStore) erstellt werden soll.  <br/> In den meisten Fällen kann der vorgeschlagene Standardwert verwendet werden.  <br/> Name in .ini Datei: "CmsFileStore" unter "Parameters for Primary Central Management Service"  <br/> ||
|Name des Vermittlungskomponentenpools  <br/> |Poolname der Vermittlungskomponente. Geben Sie nur den Netbios-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "PoolName" unter "Parameters for a pool of Mediation Servers" (Parameter für einen Pool von Vermittlungsservern)  <br/> |Darf maximal 15 Zeichen lang sein. Geben Sie nur den Netbios-Namen ein.  <br/> |
|Name der Vermittlungskomponente  <br/> |Komponentenname der Vermittlungskomponente 1. Geben Sie nur den Netbios-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "ServerName" unter "Parameters for a pool of Mediation Servers" (Parameter für einen Pool von Vermittlungsservern)  <br/> |Darf maximal 15 Zeichen lang sein. Geben Sie nur den Netbios-Namen ein.  <br/> |
|Vermittlungskomponente Computer-IP-Adresse  <br/> |Interne Corpnet-IP für Vermittlungskomponente (intern im Umkreisnetzwerk).  <br/> Name in .ini Datei: "IP" unter "Parameter für einen Pool von Vermittlungsservern"  <br/> ||
|Interner Name des Edgepools  <br/> |Poolname der Edgekomponente. Geben Sie nur den Netbios-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "InternalPoolName" unter "Parameters for a pool of Edge Servers" (Parameter für einen Pool von Edgeservern)  <br/> |Darf maximal 15 Zeichen lang sein. Geben Sie nur den Netbios-Namen ein.  <br/> |
|Interner Name des Edgeservers  <br/> |Komponentenname der Edgekomponente. Geben Sie nur den Netbios-Namen ein. Der AD-Domänenname wird verwendet, um den FQDN zu generieren.  <br/> Name in .ini Datei: "InternalServerName" unter "Parameters for a pool of Edge Servers" (Parameter für einen Pool von Edgeservern)  <br/> |Darf maximal 15 Zeichen lang sein. Geben Sie nur den Netbios-Namen ein.  <br/> |
|Interne IP-Adresse des Edgeservers  <br/> |Interne Umkreisnetzwerk-IP der Edgekomponente für die Kommunikation mit anderen Komponenten von Cloud Connector.  <br/> Name in .ini Datei: "InternalServerIPs" unter "Parameters for a pool of Edge Servers" (Parameter für einen Pool von Edgeservern)  <br/> ||
|Externer Name des Zugriffspools  <br/> |Name des Zugriffs-Edges; z. B. AP. Dieser Name muss mit dem Für das SSL-Zertifikat angegebenen Namen übereinstimmen. Geben Sie nur den Netbios-Namen ein. Der NAME DER SIP-Domäne wird verwendet, um den FQDN zu generieren. Ein externer Poolname wird für alle Edgekomponenten im Pool verwendet. Pro PSTN-Standort ist ein Edgezugriffspool erforderlich.  <br/> Name in .ini Datei: "ExternalSIPPoolName" unter "Parameters for a pool of Edge Servers" (Parameter für einen Pool von Edgeservern)  <br/> |Darf maximal 15 Zeichen lang sein. Geben Sie nur den Netbios-Namen ein.  <br/> "sip" ist reserviert und kann daher nicht als Name verwendet werden.  <br/> Der generierte FQDN-Name muss mit dem Für das SSL-Zertifikat angegebenen Namen übereinstimmen.  <br/> |
|Externe IP des Zugriffs-Edges  <br/> |Externe IP der Edgekomponente – entweder öffentliche IP, wenn keine NAT verfügbar ist, oder übersetzte IP (geben Sie beide Adressen an, wenn diese zugeordnet sind).  <br/> Name in .ini Datei: "ExternalSIPIPs" unter "Parameters for a pool of Edge Servers" (Parameter für einen Pool von Edgeservern)  <br/> ||
|Name des Medienrelays  <br/> |Name des Audio-Video-Medienrelay-Edges; z. B. MR. Ein externer Poolname wird für alle Edgekomponenten in einem Pool verwendet. Pro PSTN-Standort ist ein Edge-Mediarelay-Pool erforderlich.  <br/> Name in .ini Datei: "ExternalMRFQDNPoolName" unter "Parameters for a pool of Edge Servers" (Parameter für einen Pool von Edgeservern)  <br/> |Darf maximal 15 Zeichen lang sein. Geben Sie nur den Netbios-Namen ein.  <br/> |
|Externe IP des MediaRelay-Edges  <br/> |Derzeit wird nur eine IP unterstützt, daher ist dies die gleiche IP wie der Zugriffs-Edge, entweder öffentliche oder zugeordnete IP (geben Sie beide Adressen an, wenn diese zugeordnet sind). Kann die gleiche Adresse wie die externe IP der Edgekomponente des Zugriffs sein. Wenn Edge hinter NAT liegt, müssen Sie auch den Wert für den nächsten Parameter angeben.  <br/> Name in .ini Datei: "ExternalMRIPs" unter "Parameters for a pool of Edge Servers" (Parameter für einen Pool von Edgeservern)  <br/> ||
|Externe IP des MediaRelay-Edges (wenn sich Edge hinter NAT befindet)  <br/> |Wenn sich Ihr Edge hinter NAT befindet, müssen Sie auch die öffentliche Adresse des NAT-Geräts angeben.  <br/> Name in .ini Datei: "ExternalMRPublicIPs" unter "Parameters for a pool of Edge Servers" (Parameter für einen Pool von Edgeservern)  <br/> ||
|VoIP-Gateway 1 – Erstellen und Modell  <br/> |Geben Sie das Make-and-Model des SBC/Voice-Gateways an. Beachten Sie, dass Sie ein Gerät oder einen SIP-Trunk aus der Liste der getesteten Geräte unter verbinden [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) können.  <br/> ||
|Erstellen und Modell für VoIP-Gateway 2 (kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |Geben Sie die Vorlage und das Modell des VoIP-Gateways an. Beachten Sie, dass Sie ein Gerät aus der Liste der getesteten Geräte unter verbinden [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) können.  <br/> ||
|Name des VoIP-Gateways 1  <br/> |Wird verwendet, um den Computer-FQDN mit AD-Domäne zu generieren. Erforderlich, wenn TLS zwischen der Vermittlungskomponente und dem VoIP-Gateway verwendet wird. Wenn Sie nicht beabsichtigen, FQDN zu verwenden – z. B. ist TLS nicht erforderlich oder das VoIP-Gateway unterstützt keine Verbindung mit FQDN (nur IP) – geben Sie an.  <br/> ||
|Name des VoIP-Gateways 2 (kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |Wird verwendet, um den Computer-FQDN mit AD-Domäne zu generieren. Erforderlich, wenn TLS zwischen Vermittlungskomponente und VoIP-Gateway verwendet wird. Wenn Sie nicht beabsichtigen, FQDN zu verwenden – z. B. ist TLS nicht erforderlich oder das VoIP-Gateway unterstützt keine Verbindung mit FQDN (nur IP) – geben Sie an.  <br/> ||
|IP-Adresse des VoIP-Gateways 1  <br/> |IP-Adresse des VoIP-Gateways.  <br/> ||
|Ip-Adresse des VoIP-Gateways 2 (kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |IP-Adresse des VoIP-Gateways.  <br/> ||
|Voice Gateway 1 Port # (kopieren Sie diese Zeile, wenn Sie mehr als 2 Gateways haben)  <br/> |Port, auf den der VoIP-Gateway-SIP-Trunk lauscht, z. B. 5060.  <br/> ||
|VoIP-Gateway 2-Port #  <br/> |Port, auf den der VoIP-Gateway-SIP-Trunk lauscht, z. B. 5060.  <br/> ||
|VoIP-Gateway 1-Protokoll für SIP-Datenverkehr  <br/> |TCP oder TLS.  <br/> ||
|VoIP-Gateway 2-Protokoll für SIP-Datenverkehr (kopieren Sie diese Zeile, wenn Sie über mehr als 2 Gateways verfügen)  <br/> |TCP oder TLS.  <br/> ||
|Externer Medienportbereich für Datenverkehr zu und von edgekomponente  <br/> |TCP/UDP-Portbereich für Mediendatenverkehr zur und von der externen Schnittstelle des Edges. Muss immer bei 50 000 beginnen. Weitere Informationen finden Sie unter "Ports und Protokolle".  <br/> |50000 - 59 999  <br/> |
|Medienportbereich für die Kommunikation mit/von der Vermittlungskomponente über die interne Firewall  <br/> |UDP-Portbereich, den die Vermittlungskomponente für die Kommunikation mit Clients und Gateways verwendet (Empfehlung: 4 Ports pro Anruf).  <br/> ||
|Medienportbereich für die Kommunikation mit/von Skype for Business Client über eine interne Firewall  <br/> |Aus Planungsgründen kann dies nicht geändert werden. Ports müssen in der internen Firewall geöffnet werden, um zwischen Skype for Business Clients innerhalb des internen Netzwerks und mit der Vermittlungskomponente zu kommunizieren.  <br/> |50 000- 50 019  <br/> |
|Öffentliches Zertifikatkennwort  <br/> |Muss im Skript angegeben werden.  <br/> ||
|Tresor Modusadministratorkennwort  <br/> Nur Version 1.4.2  <br/> |Tresor-Modus-Administratorkennwort für die interne CC-Domäne.  <br/> ||
|Cloud Connector-Domänenadministratorkennwort  <br/> Nur Version 1.4.2  <br/> |Kennwort für Cloud Connector Domain Administrator (anders als Ihre Produktionsdomäne). Der Benutzername ist Administrator. Sie können den Benutzernamen nicht ändern.  <br/> ||
|Administratorkennwort für virtuelle Computer  <br/> Nur Version 1.4.2  <br/> |Wird verwendet, um das Verwaltungsnetzwerk während der Bereitstellung zu konfigurieren.  <br/> Der Benutzername ist Administrator. Sie können den Benutzernamen nicht ändern.  <br/> ||
|CABackupFile  <br/> Version 2.0 und höher  <br/> |Wird zum Speichern des Zertifizierungsstellendiensts vom Active Directory-Server in einer Datei verwendet, wenn mehrere Appliances an einem Cloud Connector-Standort bereitgestellt werden. Achten Sie darauf, das gleiche Kennwort für alle Appliances innerhalb eines Cloud Connector-Standorts zu verwenden, um die Ca-Sicherungsdatei erfolgreich in die neu hinzugefügte Appliance zu importieren.  <br/> ||
|CCEService  <br/> Version 2.0 und höher  <br/> |Wird für den Cloud Connector-Verwaltungsdienst verwendet. benötigt Zugriff auf das Cloud Connector-Standortverzeichnis. Achten Sie darauf, dasselbe Kennwort für alle Appliances an einem Cloud Connector-Standort zu verwenden.  <br/> ||
|Microsoft 365 oder Office 365 Mandantenadministrator  <br/> | Das Konto wird von Cloud Connector zum Aktualisieren und Verwalten von Mandanteneinstellungen für Cloud Connector verwendet: <br/>  Version 2.0 und höher: Anmeldeinformationen für ein dediziertes Microsoft 365- oder Office 365 konto mit Skype for Business Administratorrechten. <br/>  Versionen vor Version 2.0: Anmeldeinformationen für ein dediziertes Microsoft 365- oder Office 365 konto mit globalen Mandantenadministratorrechten. <br/> ||
|Aktivieren der REFER-Unterstützung  <br/> |Dadurch wird definiert, ob die SIP REFER-Unterstützung für die Trunkkonfiguration für Ihre IP/Nebenstellenanlage aktiviert oder deaktiviert ist. Der Standardwert lautet "True". Wenn Ihr IP/PBX-Gateway DIE REFER-Unterstützung unterstützt, lassen Sie dies auf "True" festgelegt. Wenn dies nicht der Typ ist, muss dieser Wert in "False" geändert werden. Wenn Sie nicht sicher sind, ob Ihr Gateway REFER unterstützt, lesen Sie ["Qualifizierte IP-PBXs und Gateways".](../../../SfbPartnerCertification/certification/infra-gateways.md)   <br/> ||
|EnableFastFailoverTimer  <br/> Version 2.0 und höher  <br/> |Mit dem Standardwert "True", wenn ausgehende Anrufe nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, werden sie an das nächste verfügbare Gateway weitergeleitet. Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch abgebrochen.  <br/> In einer Organisation mit langsamen Netzwerken und Gatewayantworten oder wenn das Einrichten von Anrufen mehr als 10 Sekunden dauert, kann dies potenziell dazu führen, dass Anrufe unnötigerweise abgebrochen werden.  <br/> Beim Tätigen von Anrufen in einige Länder, z. B. die Vereinigten Arabischen Emirate oder Die Vereinigten Arabischen Emirate, kann der Anrufaufbau mehr als 10 Sekunden dauern. Sie müssen den Wert in "False" ändern, wenn ähnliche Probleme auftreten. Vergessen Sie nicht, die entsprechende Einstellung auf dem verbundenen SBC oder Gateway zu ändern.  <br/> Der Wert kann True oder False sein. Der Standardwert lautet "True".  <br/> ||
|ForwardCallHistory  <br/> Version 2.0 und höher  <br/> | Dieser Parameter wird verwendet, um SIP-Header zu aktivieren, die verwendet werden, um den ursprünglichen Anrufer in Szenarien mit gleichzeitigen Anrufen, Anrufweiterleitung und Anrufübertragung zu melden. Wenn Sie den Parameter auf "True" festlegen, werden zwei SIP-Header aktiviert: <br/>  History-Info <br/>  Referred-By <br/>  Der History-Info-Header wird zum Neutargetieren von SIP-Anforderungen verwendet und stellt einen Standardmechanismus zum Erfassen der Anforderungsverlaufsinformationen bereit, um eine Vielzahl von Diensten für Netzwerke und Endbenutzer zu ermöglichen. ([RFC 4244 – Abschnitt 1.1](http://www.ietf.org/rfc/rfc4244.txt)). Für die Cloud Connector-Trunkschnittstellen wird dies in Szenarien mit gleichzeitigen Anrufen und Anrufweiterleitung verwendet.  <br/>  Der Wert kann True oder False sein. Der Standardwert ist False. <br/> ||
|Weiterleiten von PAI  <br/> Version 2.0 und höher  <br/> |PAI ist eine private Erweiterung für SIP, mit der SIP-Server die Identität authentifizierter Benutzer bestätigen können. Für den SIP-Trunkanbieter kann PAI für Abrechnungszwecke verwendet werden, wenn History-Info und Referred-By Header nicht vorhanden sind. Wenn "P-Asserted-Identity weiterleiten" in der Konfiguration aktiviert ist, leitet der Vermittlungsserver PAI-Header mit SIP &amp; Tel-URIs vom Cloud Connector an den SIP-Trunk weiter. Der Vermittlungsserver leitet PAI-Header mit den &amp; E.164-Nummern des TEL-URIs, die NUR im SIP-Trunk empfangen wurden, an Cloud Connector weiter. Der Vermittlungsserver leitet auch alle In beide Richtungen empfangenen Datenschutzheader weiter. Wenn die vom Vermittlungsserver gesendete SIP-Anforderung einen Datenschutzheader des Formulars " Privacy: id" in Verbindung mit dem PAI-Header enthält, sollte die bestätigte Identität außerhalb der Netzwerkvertrauensdomäne privat bleiben.  <br/> Der Wert kann True oder False sein. Der Standardwert ist False.  <br/> ||

### <a name="certificate-requirements"></a>Anforderungen für Zertifikate
<a name="BKMK_Certs"> </a>

Jede Edgekomponente erfordert ein Zertifikat von einer öffentlichen Zertifizierungsstelle. Zertifikate müssen über einen exportierbaren privaten Schlüssel verfügen, um zwischen Edgekomponenten zu kopieren. Um die Zertifikatanforderungen zu erfüllen, müssen Sie sich zwischen den folgenden Optionen entscheiden und den Antragstellernamen (Subject Name, SN) und den alternativen Antragstellernamen (Subject Alternative Name, SAN) für das Zertifikat angeben.

 **Wenn Sie über eine einzelne SIP-Domäne verfügen:**

- **Option 1.** Der Antragstellername muss den Poolnamen enthalten, den Sie den Edgekomponenten zugewiesen haben. Beachten Sie, dass der Antragstellername nicht sip.sipdomain.com werden kann, da dieser Name für die Online-Skype for Business Edgekomponente reserviert ist. Der SAN muss sip.sipdomain.com und den Namen des Zugriffs-Edgepools enthalten:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Option 2.** Wenn Sie ein einzelnes Platzhalterzertifikat auf allen Edgepoolservern verwenden möchten, die Sie bereitstellen, können Sie anstelle des Edgepoolnamens im Zertifikat den Platzhalter-SAN-Eintrag \* ".sipdomain.com" verwenden. Der Antragstellername kann der Name des Zugriffs-Edgepools eines der Edgepools sein, die Sie bereitgestellt haben:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Sie dürfen keinen externen DNS-Eintrag für sip \<sipdomain\> erstellen. com, da dieser Name zur Microsoft 365- oder Office 365-Bereitstellung gehört.

> [!NOTE]
> Wenn Sie ein einzelnes Zertifikat für alle in Ihrer Organisation bereitgestellten Edgepools verwenden möchten und kein Platzhalterzertifikat wie in Option 2 definiert verwenden können, müssen Sie den FQDN für alle bereitgestellten Edgepools in den SAN-Namen im Zertifikat einschließen.

 **Wenn Sie über mehrere SIP-Domänen verfügen:**

Sie müssen sip.sipdomain.com für jede SIP-Domäne und den Namen der Zugriffs-Edgepools pro Domäne hinzufügen (es kann sich um einen physischen Pool mit unterschiedlichen Namen handeln). Nachfolgend finden Sie ein Beispiel für SN- und SAN-Einträge in einem Szenario mit mehreren Sip-Domänen:

- **Option 1.** Der Antragstellername muss den Poolnamen enthalten, den Sie für Edgekomponenten zugewiesen haben. Beachten Sie, dass der Antragstellername nicht sip.sipdomain.com werden kann, da dieser Name für die Online-Skype for Business Edgekomponente reserviert ist. Der SAN muss sip.sipdomain.com und den Namen des Zugriffs-Edgepools enthalten:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Option 2.</strong> Wenn Sie ein einzelnes Platzhalterzertifikat auf allen Edgepoolservern verwenden möchten, die Sie bereitstellen, können Sie anstelle des Edgepoolnamens im Zertifikat einen Platzhalter-SAN-Eintrag von \* .sipdomain.com verwenden. Der Antragstellername kann der Name des Zugriffs-Edgepools eines der Edgepools sein, die Sie bereitgestellt haben:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Sie dürfen keinen externen DNS-Eintrag für sip \<sipdomain\> erstellen. com, da dieser Name zur Microsoft 365- oder Office 365-Bereitstellung gehört.

Für die Bereitstellung können Sie die folgende Tabelle verwenden:

|**Option**|**Beschreibung**|**Hinweise**|
|:-----|:-----|:-----|
|Welche Option verwenden Sie für Ihre Bereitstellung?  <br/> |Option 1 oder 2  <br/> ||
|SN  <br/> |Bereitstellen des SN für Ihr Zertifikat  <br/> ||
|SAN  <br/> |Stellt den SAN für Ihr Zertifikat bereit.  <br/> ||

Wenn Sie TLS zwischen dem Gateway und dem Vermittlungsserver verwenden, müssen Sie das Stammzertifikat oder die vollständige Zertifikatkette für das dem Gateway zugewiesene Zertifikat abrufen.

## <a name="dial-plan-considerations"></a>Überlegungen zum Wählplan
<a name="BKMK_DailPlan"> </a>

Cloud Connector erfordert die Verwendung eines Onlinewählplans. Weitere Informationen zum Konfigurieren eines Onlinewählplans finden Sie unter [Was sind Wählpläne?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Überlegungen zur hohen Verfügbarkeit
<a name="BKMK_HA"> </a>

Wenn Sie Cloud Connector Edition für hohe Verfügbarkeit bereitstellen, stellen Sie mindestens zwei Appliances bereit, die als Sicherung füreinander dienen. Jede Appliance besteht aus vier Komponenten: Edge, Vermittlung, zentrale Verwaltung Store (CMS) und Domänencontroller.

Im Allgemeinen kann Cloud Connector Edition weiterhin Anrufe verarbeiten, wenn eine Komponente innerhalb einer Appliance ausfällt, aber Sie müssen Folgendes berücksichtigen:

- **Überlegungen zu Vermittlungs-, CMS- und Domänencontrollerkomponenten**

    Gehen Sie davon aus, dass die CMS- oder Domänencontrollerkomponente in einer Appliance ausfällt. Die Appliance kann weiterhin eingehende und ausgehende Anrufe verarbeiten. Wenn Sie jedoch eine Vermittlungskomponente neu starten, wenn der Domänencontroller oder die CMS-Komponente nicht erreichbar ist, funktioniert die Vermittlung nicht. Das gleiche gilt für den Neustart der CMS-Komponente, wenn der Domänencontroller ausgefallen ist.

    **Empfehlung:** Überprüfen Sie vor dem Neustart der Komponenten die Verfügbarkeit der anderen Komponenten in der Appliance.

- **Überlegungen zu Edgekomponenten**

    Wenn die Edgekomponente in einer Appliance nicht verfügbar ist, unterscheidet sich das Verhalten für eingehende und ausgehende Anrufe wie folgt:

  - **Ausgehender Anruf**– ein Anruf von Ihrem Benutzer im Internet an ein PSTN-Netzwerk.

    Der Anrufverteilungsmechanismus in der Cloud identifiziert, dass eine Edgekomponente ausgefallen ist, und leitet alle Anrufe an eine andere Appliance weiter, sodass der ausgehende Anruf erfolgreich ist.

  - **Eingehender Anruf**– ein Anruf aus dem PSTN-Netzwerk an einen Benutzer, der sich entweder in einem lokalen Netzwerk oder im Internet befindet.

     Wenn die Edgekomponente der Appliance, die den Anruf empfangen hat, nicht funktioniert, sind die eingehenden Anrufe an diese Appliance nicht erfolgreich, da die Vermittlungskomponente den Anruf nicht an die Edgekomponente in der anderen Appliance umleiten kann.

    **Empfehlung:** Verfügen über ein Überwachungssystem. Nachdem Sie eine Fehlfunktion der Edgekomponente erkannt haben, fahren Sie alle Komponenten in der Appliance herunter, in denen die Edgekomponente nicht verfügbar ist.

## <a name="cloud-connector-media-flow"></a>Cloud Connector-Medienfluss
<a name="BKMK_MediaFlow"> </a>

Die folgenden Diagramme beschreiben den Fluss eines ausgehenden und eingehenden Anrufs über Cloud Connector Edition. Dies sind nützliche Informationen, um zu verstehen, wie Konnektivität hergestellt wird.

Im ersten Diagramm führt ein interner Benutzer einen ausgehenden Anruf wie folgt aus:

1. Dave, ein Onlinebenutzer, der sich jetzt im internen Netzwerk befindet, ruft einen externen PSTN-Benutzer an.

2. SIP-Datenverkehr wird an Skype for Business Online geroutet.

3. Skype for Business Online führt eine umgekehrte Nummernsuche der Zahl aus. Die Umgekehrte Nummernsuche schlägt fehl, da diese Nummer keiner person in der Skype for Business Organisation gehört.

4. Der Anruf wird an die Edgekomponente weitergeleitet (ZUERST SIP- und Medienfluss über Online Edge; Medien werden über die interne Firewall zur Vermittlungskomponente weitergeleitet).

5. Wenn die Route vorhanden ist, leitet die Edgekomponente den Datenverkehr an die Vermittlungskomponente im Umkreisnetzwerk weiter.

6. Die Vermittlungskomponente sendet den Datenverkehr an das PSTN-Gateway.

![Ausgehender Medienfluss für Cloud Connector.](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Im nächsten Diagramm empfängt ein interner Benutzer einen eingehenden Anruf wie folgt:

1. Das PSTN-Gateway empfängt einen Anruf für Benutzer Dave, der online verwaltet wird, sich aber jetzt im internen Netzwerk befindet.

2. SIP-Datenverkehr wird an die Vermittlungskomponente weitergeleitet.

3. Die Vermittlungskomponente sendet SIP-Datenverkehr an die Edgekomponente und wechselt dann zu Skype for Business Online.

4. Skype for Business Online führt eine umgekehrte Nummernsuche der Zahl durch und findet, dass dies der Benutzer Dave ist.

5. Die SIP-Signalisierung erfolgt an alle Anwesenheitspunkte von Dave.

6. Der Mediendatenverkehr wird zwischen dem Gateway und der Vermittlungskomponente sowie zwischen der Vermittlungskomponente und dem Endpunkt hergestellt.

![Eingehende Medien Flow für Cloud Connector.](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Überwachung und Problembehandlung
<a name="BKMK_Monitor"> </a>

Der Überwachungs- und Problembehandlungsmechanismus wird automatisch mit jeder Cloud Connector-Appliance installiert. Der Mechanismus erkennt die folgenden Ereignisse:

- Ein oder mehrere virtuelle Computer einer Cloud Connector-Appliance sind nicht mit einem internen oder internetbasierten virtuellen Switch verbunden.

- Ein oder mehrere virtuelle Computer einer Cloud Connector-Appliance befinden sich im Status "Gespeichert" oder "Beendet".

- Dienste, die nicht ausgeführt werden.

  Wenn eines der folgenden Ereignisse erkannt wird, wird die gesamte Cloud Connector-Appliance geleert und als offline markiert, um den Versuch zu verhindern, Anrufe an eine fehlerhafte Appliance einzurichten. Die automatischen Wiederherstellungsfunktionen von Cloud Connector stellen anschließend Dienste wieder her und markieren die Appliance als online. Wenn die automatische Wiederherstellung aus irgendeinem Grund fehlschlägt, lesen Sie [Die Problembehandlung für Ihre Cloud Connector-Bereitstellung.](troubleshoot-your-cloud-connector-deployment.md)

  - Auf dem virtuellen Computer für die zentrale Verwaltung Store:

     - Skype for Business Master Replicator Agent

     - Skype for Business Replikatreplikationsdienst-Agent

  - Auf dem virtuellen Computer des Vermittlungsservers:

     - Skype for Business Replikatreplikationsdienst-Agent

     - Skype for Business Server Mediation

  - Auf dem virtuellen Edgeservercomputer

     - Skype for Business Replikatreplikationsdienst-Agent

     -  Skype for Business Server Zugriffs-Edge

     - Skype for Business Server Audio-/Video-Edge

     - Skype for Business Server Audio-/Videoauthentifizierung

     - Skype for Business Server Webkonferenz-Edge

- Eingehende Regel von Windows Firewall für "CS RTCSRV" auf Edge, "CS RTCMEDSRV" auf dem Vermittlungsserver ist deaktiviert.

Cloud Connector 2.1 und höher unterstützt die Überwachung von Cloud Connector mithilfe von Operations Management Suite (OMS). Weitere Informationen finden Sie unter [Überwachen von Cloud Connector mit Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_MoreInfo"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:

- [Microsoft-Telefonielösungen](/microsoftteams/cloud-voice-landing-page)

- [Konfigurieren und Verwalten von Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Planen der Medienumgehung in der Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Bereitstellen der Medienumgehung in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
