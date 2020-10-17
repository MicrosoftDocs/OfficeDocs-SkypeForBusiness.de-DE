---
title: Konfigurieren der globalen Einstellungen für die medienumgehung zur Verwendung von Standort-und Regionsinformationen
description: Konfigurieren der globalen Einstellungen für die medienumgehung zur Verwendung von Standort-und Regionsinformationen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a65dcec966030262d6d0fb5530b94f2411003c7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559801"
---
# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Konfigurieren der globalen Einstellungen für die medienumgehung in lync Server 2013 zur Verwendung von Standort-und Regionsinformationen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

<div>


> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie die Medienumgehung bereits für Trunkverbindungen zwischen dem Vermittlungsserver und einem Peer (PSTN)-Gateway, einer IP-Nebenstellenanlage oder dem Session Border Controller (SBC) eines Anbieters von Internettelefoniediensten (ITSP) für einen bestimmten Standort oder Dienst konfiguriert haben, für den die Medienverarbeitung durch den Vermittlungsserver umgangen werden soll.<BR>In diesem Thema wird auch davon ausgegangen, dass Sie alle zentralen Standorte und Zweigstellen im Topologie-Generator so definiert haben, dass Sie mit der netzwerkregion, dem Netzwerkstandort und der Subnetz Konfiguration übereinstimmen, die Sie gemäß den Schritten unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern einer netzwerkregion in lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</A>und einem <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Netzwerkstandort in lync Server 2013 zuordnen</A>. Falls die Konfigurationen nicht übereinstimmen, ist die Medienumgehung nicht erfolgreich.



</div>

Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie auch die globalen Einstellungen konfigurieren. Wenn Sie die globalen Einstellungen für die Medienumgehung anhand der hier beschriebenen Schritte durchführen, wird vorausgesetzt, dass eine der folgenden Bedingungen für Ihre Konfiguration zutrifft:

  - Sie verfügen *nicht* über eine gute Konnektivität zwischen lync Server Endpunkten und allen Peers, für die Sie die medienumgehung für die trunkverbindung konfiguriert haben.

  - Die Anrufsteuerung (Call Admission Control, CAC) zur Bandbreitenverwaltung ist aktiviert.
    
    <div>
    

    > [!NOTE]
    > Ausführliche Informationen zu den Überlegungen zur Anrufsteuerung und zur medienumgehung finden Sie im Abschnitt "Anrufsteuerung für PSTN-Verbindungen" unter <A href="lync-server-2013-media-bypass-and-mediation-server.md">medienumgehung und Vermittlungsserver in lync Server 2013</A> in der Planungsdokumentation.

    
    </div>

Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten.

Oder führen Sie diese Schritte aus, wenn die Informationen zu Standorten und Regionen für Entscheidungen zur Medienumgehung herangezogen werden sollen, Sie jedoch nicht die Anrufsteuerung aktivieren möchten. In diesem Fall müssen Links zur Bandbreiteneinschränkung weiterhin über Netzwerk-standortübergreifende Richtlinien dargestellt werden, wie unter [Create Network Standort-Richtlinien in lync Server 2013](lync-server-2013-create-network-intersite-policies.md)beschrieben. Die tatsächlichen Bandbreiteneinschränkungen sind hierbei weniger wichtig, da die Anrufsteuerung nicht aktiviert wurde. Stattdessen werden diese Verbindungen zur Partitionierung von Subnetzen verwendet, um Verbindungen mit Bandbreitenbeschränkungen anzugeben, die für die Medienumgehung eingesetzt werden können. Beachten Sie, dass dies auch gilt, wenn sowohl die Anrufsteuerung als auch die Medienumgehung aktiviert wurden.

Damit die Umgehung ordnungsgemäß funktioniert, muss außerdem Konsistenz zwischen einem Standort gemäß Definition im Topologie-Generator und wie er definiert ist, wenn Sie netzwerkregionen und Netzwerkstandorte konfigurieren. Wenn Sie beispielsweise einen Zweigstellenstandort haben, den Sie im Topologie-Generator als nur ein PSTN-Gateway festgelegt haben, muss dieser Zweigstellenstandort mit einer Enterprise-VoIP-Richtlinie konfiguriert werden, mit deren Hilfe Zweigstellenbenutzer ihre PSTN-Anrufe über das PSTN-Gateway am Zweigstellenstandort weiterleiten können.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Doppelklicken Sie in der Tabelle auf die Konfiguration **Global**.

4.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.

5.  Klicken Sie auf **Konfiguration von Standorten und Regionen verwenden**.

6.  Falls erforderlich, aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren**.
    
    <div>
    

    > [!NOTE]
    > Aktivieren Sie dieses Kontrollkästchen nur dann, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die einer bestimmten Region zugeordnet sind, und Sie außerdem über einige Zweigstellen mit Bandbreiteneinschränkungen verfügen, die derselben Region zugeordnet sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die den Zweigstandorten zugeordneten Subnetze angeben, statt sämtliche, allen Standorten zugeordnete Subnetze angeben zu müssen. Es wird empfohlen, dieses Kontrollkästchen nicht zu aktivieren, wenn die Anrufsteuerung aktiviert wurde.

    
    </div>

7.  Klicken Sie auf **Commit**.

Fügen Sie dann dem Netzwerkstandort Subnetze hinzu, wie in [Zuordnen von Subnetzen mit Netzwerkstandorten für die medienumgehung in lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)beschrieben. (Die tatsächlichen Verfahren zum Zuordnen von Subnetzen zu Netzwerkstandorten werden in [Zuordnen eines Subnetzes mit einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)beschrieben.) Nachdem Sie alle Subnetze mit Netzwerkstandorten verknüpft haben, ist die Bereitstellung der medienumgehung abgeschlossen.

<div>


> [!IMPORTANT]
> Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern einer netzwerkregion in lync Server 2013</A> und <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuordnen von Subnetzen zu Netzwerkstandorten für die medienumgehung in lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

