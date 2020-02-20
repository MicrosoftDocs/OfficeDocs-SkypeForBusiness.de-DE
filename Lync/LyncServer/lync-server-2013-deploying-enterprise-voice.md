---
title: 'Lync Server 2013: Bereitstellen von Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b56065b0e3b7e7ef25c81f20140e8869dbe5376
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Bereitstellen von Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Lync Server 2013 ist Enterprise-VoIP Teil der lync Server 2013-Infrastruktur.

Zum Bereitstellen der Enterprise-VoIP müssen Sie Folgendes ausführen:

<div id="sectionSection0" class="section">

1.  Lesen Sie den Abschnitt [Planung für Enterprise-VoIP in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) der Planungsdokumentation.

2.  Die Planung von Features und Komponenten abschließen, um diese Arbeitslast bereitzustellen.

3.  Führen Sie das Planungs Tool aus, um eine Topologie zu entwerfen, die ihre Bereitstellungsentscheidungen widerspiegelt.

4.  Öffnen Sie den Topologie-Entwurf im Topologie-Generator, wie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in der Bereitstellungsdokumentation beschrieben.
    
    <div>
    

    > [!NOTE]  
    > Die Installation des Topologie-Generators ist Teil des Bereitstellungsprozesses für den internen Pool. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">install lync Server 2013 Administration Tools</A> in der Bereitstellungsdokumentation.

    
    </div>

Darüber hinaus müssen Sie bereits lync Server Enterprise Edition an zentralen Standorten und Zweigstellenstandorten bereitgestellt haben, die der Referenztopologie entsprechen, die Sie bereitstellen möchten. Sie können Enterprise-VoIP-Komponenten erst bereitstellen, nachdem Sie Dateien für mindestens einen internen Pool definiert, veröffentlicht und installiert haben, und Sie müssen den Topologie-Generator verwenden, um einen internen Pool zu definieren und zu veröffentlichen.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Informationen zum Anzeigen von Referenz Topologien mit Beispielen dafür, wo Enterprise-VoIP-Serverrollen bereitgestellt werden können (und ihre Beziehung zu einem anderen und anderen lync Server 2013-Serverrollen), finden Sie unter [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation.

Informationen zum Anzeigen einer Referenztopologie, die eine Beispielbereitstellung für die Anrufsteuerung, einschließlich netzwerkregionen, Netzwerkstandorten und Subnetzen, veranschaulicht und erläutert, finden Sie unter [example: Gathering your Requirements for Call Admission Control in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Lesen Sie die Themen in diesem Abschnitt weiter, um Enterprise-VoIP an einem zentralen Standort bereitzustellen. Um Enterprise-VoIP an einem Zweigstellenstandort bereitzustellen, fahren Sie mit dem <A href="lync-server-2013-deploying-branch-sites.md">Bereitstellen von Zweigstellenstandorten in lync Server 2013</A> in der Bereitstellungsdokumentation fort.



</div>

Dieser Abschnitt enthält Verfahren für Bereitstellungen, in denen ein Vermittlungsserver wie empfohlen auf jedem Front-End-Server oder Standard Edition-Server gemeinsam ausgeführt wird, und auch für Bereitstellungen mit einem eigenständigen Vermittlungsserverpool.

Sie können den folgenden Inhalt überspringen, wenn Sie den Topologie-Generator verwendet haben, um eine Topologie zu definieren und zu veröffentlichen, die eine Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server Kollokatoren, da die Dateien für den Bereitstellungs-Assistenten bereits automatisch installiert wurden. Vermittlungsserver, wenn Sie Dateien für Ihren Front-End-Server Pool oder Standard Edition-Server installiert haben:

  - [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)

Wenn Sie den Topologie-Generator zum Definieren und Veröffentlichen eines Vermittlungsserver in einem eigenständigen Pool verwendet haben, können Sie den folgenden Inhalt verwenden:

  - Stellen Sie sicher, dass Ihre Topologie die erforderlichen Software-und Umgebungsvoraussetzungen erfüllt, wie unter [Enterprise-VoIP-Voraussetzungen für lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)beschrieben.

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - <span></span>  
    [Voraussetzungen für Enterprise-VoIP für lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Bereitstellen von Vermittlungsservern und Definieren von Peers in lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Exportieren und Importieren der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Testen des VoIP-Routings in lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Bereitstellen von lokaler Exchange um zur Bereitstellung von lync Server 2013-Voicemail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Bereitstellen von Voicemail für lync Server 2013-Benutzer in gehosteten Exchange um](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Konfigurieren der lokalen lync Server 2013 Integration in Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Informationen zu netzwerkregionen, Standorten und Subnetzen in lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Erstellen oder Ändern einer netzwerkregion in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Konfigurieren der Anrufsteuerung in lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Konfigurieren von Enhanced 9-1-1 in lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Konfigurieren der medienumgehung in lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Zweigstellenstandorten in lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Konfigurieren von Einwahlkonferenzen in lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Konfigurieren des Parkens von Anrufen in lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Konfigurieren von Ankündigungen für nicht zugewiesene Nummern in lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

