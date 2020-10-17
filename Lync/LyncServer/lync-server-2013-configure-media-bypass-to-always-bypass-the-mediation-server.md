---
title: 'Lync Server 2013: Konfigurieren Sie die medienumgehung so, dass die Vermittlungsserver immer umgangen wird.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23b77f246398ab47002ddef38e804419ffa4f5bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507612"
---
# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Konfigurieren der medienumgehung in lync Server 2013, um die Vermittlungsserver immer zu umgehen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-25_

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie die Medienumgehung für Trunkverbindungen mit einem Peer (PSTN-Gateway, IP-Nebenstellenanlage oder Session Border Controller [SBC] des Anbieters von Internettelefoniediensten [Internet Telephony Service Provider, ITSP]) bereits für einen bestimmten Standort oder Dienst konfiguriert haben, für den die Medienverarbeitung durch den Vermittlungsserver umgangen werden soll.<BR>Sie können keine dauerhafte Umgehung der Mediendatenverarbeitung durch den Vermittlungsserver konfigurieren, wenn Sie gleichzeitig die Anrufsteuerung (Call Admission Control, CAC) aktivieren. Diese Einstellungen sind nicht kompatibel und sind daher gegenseitig ausschließende Einstellungen in der Benutzeroberfläche von lync Server-Systemsteuerung.



</div>

Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zum Vermittlungsserver zugeordnet sind, müssen Sie auch die globalen Einstellungen für die Medienumgehung konfigurieren. Wenn Sie die Schritte in diesem Thema zum Konfigurieren globaler Einstellungen für die medienumgehung verwenden, wird davon ausgegangen, dass Sie über eine gute Verbindung zwischen lync-Endpunkten und allen Peers verfügen, für die Sie die medienumgehung für die trunkverbindung konfiguriert haben.

Wenn Sie keine gute Verbindung zwischen lync Server Endpunkten und allen Peers mit dem Vermittlungsserver haben, dessen zugehörige trunk Verbindungen für die medienumgehung aktiviert wurden, müssen Sie die Einstellungen für die globale medienumgehung konfigurieren, um Standort-und Regionsinformationen bei Verwendung der medienumgehung zu verwenden. Auf diese Weise kann die Umgehung der Mediendatenverarbeitung durch den Vermittlungsserver besser gesteuert werden. Verwenden Sie dazu die Schritte unter [configure Media Bypass Global Settings in lync Server 2013, um Standort-und Regionsinformationen zu verwenden](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) und [ein Subnetz einem Netzwerkstandort in lync Server 2013 zuzuordnen](lync-server-2013-associate-a-subnet-with-a-network-site.md) .

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Doppelklicken Sie in der Liste auf die Konfiguration **Global**.

4.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.

5.  Klicken Sie auf **Immer umgehen**.

6.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der medienumgehung in lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Optionen für die globale medienumgehung in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Medienumgehung und Vermittlungsserver in lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  


[Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

