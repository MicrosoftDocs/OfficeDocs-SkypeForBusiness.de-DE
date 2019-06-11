---
title: 'Lync Server 2013: Bereitstellen von Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Bereitstellen von Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Lync Server 2013, Enterprise-VoIP ist Teil der lync Server 2013-Infrastruktur.

Zur Bereitstellung von Enterprise-VoIP müssen Sie Folgendes ausführen:

<div id="sectionSection0" class="section">

1.  Lesen Sie den Abschnitt [Planning for Enterprise Voice in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) der Planungsdokumentation.

2.  Abschließen von Plänen für Features und Komponenten, die mit dieser Arbeitsauslastung bereitgestellt werden sollen.

3.  Führen Sie das Planungs Tool aus, um eine Topologie zu entwerfen, die ihre Bereitstellungsentscheidungen widerspiegelt.

4.  Öffnen Sie den Topologie-Entwurf im Topologie-Generator, wie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in der Bereitstellungsdokumentation beschrieben.
    
    <div>
    

    > [!NOTE]  
    > Die Installation des Topologie-Generators ist Teil des Bereitstellungsprozesses für den internen Pool. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">Installieren von lync Server 2013-Verwaltungstools</A> in der Bereitstellungsdokumentation.

    
    </div>

Darüber hinaus müssen Sie lync Server, Enterprise Edition, auf zentralen Websites und Zweigstellen bereitgestellt haben, die der von Ihnen bereitzustellenden Referenztopologie entsprechen. Sie können Enterprise-VoIP-Komponenten erst bereitstellen, nachdem Sie Dateien für mindestens einen internen Pool definiert, veröffentlicht und installiert haben, und Sie müssen den Topologie-Generator verwenden, um einen internen Pool zu definieren und zu veröffentlichen.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Informationen zum Anzeigen von Referenz Topologien mit Beispielen für die Bereitstellung von Enterprise-VoIP-Serverrollen (und deren Beziehung zu einem anderen und anderen lync Server 2013-Serverrollen) finden Sie unter [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation.

Informationen zum Anzeigen einer Referenztopologie, die eine Beispielbereitstellung für die Anrufsteuerung, einschließlich netzwerkregionen, Netzwerk Websites und Subnetzen, veranschaulicht und erläutert, finden Sie unter [Beispiel: Erfassen Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) im Planungsdokumentation.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Wenn Sie Enterprise-VoIP an einem zentralen Standort bereitstellen möchten, lesen Sie die Themen in diesem Abschnitt weiter. Wenn Sie Enterprise-VoIP an einer Zweigstelle bereitstellen möchten, wechseln Sie zum bereit <A href="lync-server-2013-deploying-branch-sites.md">Stellen von Zweigstellen in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

Dieser Abschnitt enthält Verfahren für Bereitstellungen, in denen ein Vermittlungsserver wie empfohlen auf jedem Front-End-Server oder Standard Edition-Server gemeinsam ausgeführt wird und auch für Bereitstellungen mit einem eigenständigen Vermittlungsserverpool.

Sie können den folgenden Inhalt überspringen, wenn Sie mithilfe des Topologie-Generators eine Topologie definiert und veröffentlicht haben, die einen Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server Kollokatoren, weil die Dateien von dem Bereitstellungs-Assistenten bereits automatisch installiert wurden Vermittlungsserver, wenn Sie Dateien für Ihren Front-End-Serverpool oder Standard Edition-Server installiert haben:

  - [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md)

Wenn Sie den Topologie-Generator zum Definieren und Veröffentlichen eines Vermittlungsservers in einem eigenständigen Pool verwendet haben, können Sie den folgenden Inhalt verwenden:

  - Überprüfen Sie, ob Ihre Topologie die erforderlichen Software-und Umgebungsvoraussetzungen erfüllt, wie in [Enterprise-VoIP-Voraussetzungen für lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)beschrieben.

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - <span></span>  
    [Voraussetzungen für Enterprise-VoIP für Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Konfigurieren von Wählplänen in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Exportieren und Importieren einer VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Bereitstellen lokaler Exchange Unified Messaging-Dienste zur Unterstützung von Lync Server 2013-Voicemail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Bereitstellen von Voicemail für Benutzer von Lync Server 2013 für gehostete Exchange Unified Messaging-Dienste](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Konfigurieren der lokalen lync Server 2013-Integration in Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Informationen zu Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Konfigurieren der Anrufsteuerung in lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Konfigurieren von E9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Konfigurieren der Medienumgehung in Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Zweigstellen in Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Konfigurieren von Einwahlkonferenzen in Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Konfigurieren des Parkens von Anrufen in Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Konfigurieren von Ansagen für nicht zugewiesene Nummern in Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

