---
title: 'Lync Server 2013: Entwerfen des SIP-Trunks für E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0ca42092b33632dbc7aed84808499b13ab0843c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Entwerfen des SIP-Trunks für E9-1-1 in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Lync Server verwendet SIP-Trunks, um einen Notruf mit dem E9-1-1-Dienstanbieter zu verbinden. Sie können Notrufdienst-SIP-Trunks für E9-1-1 an einem zentralen Standort, an mehreren zentralen Standorten oder an jeder Zweigstelle einrichten. Wenn jedoch die WAN-Verbindung zwischen dem Standort des Anrufers und dem Standort, an dem der Notfalldienst-SIP-Trunk gehostet wird, nicht verfügbar ist, ist für einen Anruf von einem Benutzer am nicht verbundenen Standort ein spezieller Telefonverwendungseintrag in der VoIP-Richtlinie des Benutzers erforderlich, der den Anruf über das lokale PSTN-Gateway an das ECRC weiterleitet. Das gleiche trifft zu, wenn in der Anrufsteuerung Begrenzungen für gleichzeitige Anrufe aktiviert sind.

<div>


> [!NOTE]  
> Es gibt zwei Möglichkeiten, einen SIP-Trunk in einer lync Server-Umgebung zu implementieren: 
> <UL>
> <LI>
> <P>Verwenden Sie mehrfach vernetzte Vermittlungsserver, die ihre nach außen gerichteten, öffentlich weitergeleiteten Schnittstellen verwenden, um mit dem SIP-Trunk-Anbieter zu kommunizieren.</P>
> <LI>
> <P>Verwenden Sie einen lokalen Session Border Controller (SBC), um einen sicheren abgrenzungspunkt zwischen den Vermittlungsservern und den Diensten des SIP Trunk-Anbieters bereitzustellen.</P></LI></UL>Wenn Sie sich für die zweite Methode entscheiden, stellen Sie sicher, dass die Marke/das Modell des von Ihnen ausgewählten SBC die Weitergabe von PIDF-LO (Presence Information Data Format Location Object)-Standortdaten als Teil der SIP INVITE unterstützt. Andernfalls gehen die Anrufe ohne Standortinformationen beim Anbieter für die Notrufunterstützung ein. Ausführliche Informationen zu zertifizierten SBCS finden Sie unter "für Microsoft lync qualifizierte Infrastruktur <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>".<BR>Über E9-1-1-Dienstanbieter erhalten Sie Zugriff auf ein SBC-Paar, um Redundanz zu gewährleisten. Sie müssen mehrere Entscheidungen bezüglich der Mediations Server Topologie und der Konfiguration des Anruf Routings treffen. Möchten Sie beide SBCs als gleichwertig behandeln und Roundrobinrouting für Anrufe zwischen ihnen verwenden oder werden Sie einen SBC als primären und den anderen als sekundären SBC festlegen?



</div>

Details zum Bereitstellen eines SIP-Trunks in lync Server finden Sie unter [wie kann ich SIP-Trunking in lync Server 2013 implementieren?](lync-server-2013-how-do-i-implement-sip-trunking.md). Zur einfacheren Bereitstellung der SIP-Trunks für E9-1-1 sollten Sie zunächst die folgenden Fragen beantworten.

  - **Soll der SIP-Trunk über eine dedizierte geleaste oder eine gemeinsam genutzte Internetverbindung bereitgestellt werden?**  
    Es ist wichtig, dass jederzeit Notrufe getätigt werden können. Eine dedizierte Leitung bietet eine Verbindung, die nicht durch anderen Datenverkehr im Netzwerk belegt ist, und ermöglicht gleichzeitig die Implementierung von QoS. Denken Sie daran, dass eine IPSec-Verschlüsselung erforderlich ist, wenn Sie beim Herstellen einer Verbindung mit Anbietern für die Notrufunterstützung über das öffentliche Internet die Vertraulichkeit von Notrufen gewährleisten müssen.

<!-- end list -->

  - **Ist Ihre E9-1-1-Bereitstellung für die Notfalltoleranz konzipiert?**  
    Da es sich um eine Lösung für Notrufe handelt, ist die Ausfallsicherheit von grundlegender Bedeutung. Stellen Sie Ihre primären und sekundären Vermittlungsserver und SIP-Stämme in Disaster-toleranten Speicherorten bereit. Es empfiehlt sich, den primären Vermittlungsserver den Benutzern, die er unterstützt, am nächsten zu stellen und Failover-Anrufe über den sekundären Vermittlungsserver (an einem anderen geografischen Standort) weiterzuleiten.

<!-- end list -->

  - **Sollten Sie einen separaten SIP-Trunk für jeden Zweigstellenstandort bereitstellen?**  
    Lync Server bietet verschiedene Strategien für die Behandlung von VoIP-Flexibilität in Zweigniederlassungen, einschließlich: mit belastbaren Datennetzwerken, Bereitstellen eines SIP-Trunks an jeder Verzweigung oder durch Drücken von Anrufen an das lokale Gateway während Ausfällen. Ausführliche Informationen finden Sie unter [SIP-Trunking in der Zweigstelle in lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **Ist die Anrufsteuerung aktiviert?**  
    Lync Server behandelt keine Notrufe anders als normale Anrufe. Aus diesem Grund kann sich die Bandbreitenverwaltung oder Anrufsteuerung negativ auf die E9-1-1-Konfiguration auswirken. Notrufe werden möglicherweise blockiert oder zum lokalen PSTN-Gateway geroutet, wenn die Anrufsteuerung aktiviert ist und der konfigurierte Grenzwert für die Verbindung überschritten wird, über die Notrufe geroutet werden. Wie bereits in diesem Thema besprochen verfügen solche Anrufe über keine Standortdaten und müssen manuell an das ECRC weitergeleitet werden.

</div>

<span> </span>

</div>

</div>

</div>

