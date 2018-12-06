---
title: 'Lync Server 2013: Bereitstellen von Enterprise-VoIP'
TOCTitle: Bereitstellen von Enterprise-VoIP
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412876(v=OCS.15)
ms:contentKeyID: 49295160
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von Enterprise-VoIP in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Lync Server 2013, Enterprise-VoIP ist Bestandteil der Lync Server 2013-Infrastruktur.

Zum Bereitstellen der Enterprise-VoIP müssen Sie Folgendes ausführen:

1.  Die Themen im Abschnitt [Planen von Enterprise-VoIP in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) in der Planungsdokumentation lesen.

2.  Die Planung von Features und Komponenten abschließen, um diese Arbeitslast bereitzustellen.

3.  Das Planungstool ausführen, um eine Topologie zu entwerfen, die Ihre Bereitstellungsentscheidungen berücksichtigt.

4.  Den Topologieentwurf gemäß den Anweisungen unter [Definieren und Konfigurieren der Topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in der Bereitstellungdokumentation im Topologie-Generator öffnen.
    

    > [!NOTE]
    > Die Installation des Topologie-Generators ist Bestandteil des Bereitstellungsprozesses des internen Pools gehört. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">Installieren von Lync Server 2013-Verwaltungstools</A> in der Bereitstellungsdokumentation.



Darüber hinaus müssen Sie bereits Lync Server Enterprise Edition an zentralen Standorten und Zweigstellenstandorten bereitgestellt haben, die der Referenztopologie entsprechen, die Sie bereitstellen möchten. Sie können Enterprise-VoIP-Komponenten erst bereitstellen, nachdem Sie Dateien für mindestens einen internen Pool definiert, veröffentlicht und installiert wurden, und Sie müssen mit dem Topologie-Generator einen internen Pool definieren und veröffentlichen.

Referenztopologien mit Beispielen, wo Enterprise-VoIP-Serverrollen bereitgestellt werden können, und ihre Beziehung zueinander und zu anderen Lync Server 2013-Serverrollen finden Sie unter [Referenztopologien in Lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation.

Zum Anzeigen einer Referenztopologie, die eine beispielhafte Anrufsteuerungsbereitstellung, einschließlich Netzwerkregionen, Netzwerkstandorten und Subnetzen veranschaulicht und erläutert, finden Sie unter [Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.


> [!IMPORTANT]
> Wenn Sie Enterprise-VoIP an einem zentralen Standort bereitstellen möchten, lesen Sie die weiteren Themen in diesem Abschnitt. Wenn Sie Enterprise-VoIP an einem Zweigstellenstandort einrichten möchten, springen Sie zu <A href="lync-server-2013-deploying-branch-sites.md">Bereitstellen von Zweigstellen in Lync Server 2013</A> in der Bereitstellungsdokumentation.



Dieser Abschnitt enthält Verfahren für Bereitstellungen, in denen ein Vermittlungsserver wie empfohlen auf jedem Front-End-Server oder Standard Edition-Server gemeinsam ausgeführt wird, und auch für Bereitstellungen mit einem eigenständigen Vermittlungsserverpool.

Sie können die folgenden Inhalte überspringen, wenn Sie mit dem Topologie-Generator eine Topologie definiert und veröffentlicht haben, in der ein Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server ausgeführt wird, da der Bereitstellungs-Assistent automatisch die Dateien für den Vermittlungsserver installiert hat, als Sie Dateien für Ihren Front-End-Serverpool oder Standard Edition-Server installiert haben:

  - [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md)

Wenn Sie mit dem Topologie-Generator einen Vermittlungsserver in einem eigenständigen Pool definiert und veröffentlicht haben, gelten die folgenden Inhalte für Sie:

  - Vergewissern Sie sich, dass Ihre Topologie die Software- und Umgebungsanforderungen erfüllt, die unter [Voraussetzungen für Enterprise-VoIP für Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md) beschrieben sind.

## In diesem Abschnitt

  - [Voraussetzungen für Enterprise-VoIP für Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - [Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - [Konfigurieren von Wählplänen in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - [Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - [Exportieren und Importieren einer VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - [Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Bereitstellen lokaler Exchange Unified Messaging-Dienste zur Unterstützung von Lync Server 2013-Voicemail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - [Bereitstellen von Voicemail für Benutzer von Lync Server 2013 für gehostete Exchange Unified Messaging-Dienste](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - [Konfigurieren der lokalen Lync Server 2013-Integration in Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - [Bereitstellen von erweiterten Enterprise-VoIP-Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Informationen zu Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Erstellen oder Ändern einer Netzwerkregion in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Konfigurieren der Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Konfigurieren von E9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Konfigurieren der Medienumgehung in Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - [Aktivieren von Benutzern für Enterprise-VoIP in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

## Siehe auch

#### Weitere Ressourcen

[Bereitstellen von Zweigstellen in Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Konfigurieren von Einwahlkonferenzen in Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Konfigurieren des Parkens von Anrufen in Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Konfigurieren von Ansagen für nicht zugewiesene Nummern in Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Bereitstellen des Monitoring Servers](lync-server-2013-deploying-monitoring.md)

