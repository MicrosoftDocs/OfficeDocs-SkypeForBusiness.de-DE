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
ms.openlocfilehash: 6c4191ed20497b4136b4e836da112054bef5a446
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Entwerfen des SIP-Trunks für E9-1-1 in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Lync Server verwendet SIP-Trunks, um einen Notruf mit dem E9-1 -1-Dienstanbieter zu verbinden. Sie können Notfalldienst-SIP-Trunks für E9-1-1 an einem zentralen Standort, an mehreren zentralen Standorten oder an jedem Zweigstellenstandort einrichten. Wenn jedoch die WAN-Verbindung zwischen dem Standort des Anrufers und dem Standort, der den SIP-Trunk Dienst hostet, nicht verfügbar ist, benötigt ein Anruf, der von einem Benutzer am getrennten Standort getätigt wird, einen speziellen Telefonverwendungseintrag in der VoIP-Richtlinie des Benutzers, der den Anruf an den ECRC über das lokale PSTN-Gateway (Public Switched Telephone Network). Das gleiche gilt, wenn die Anrufsteuerung gleichzeitige Anruf Grenzwerte wirksam macht.

<div>


> [!NOTE]  
> Es gibt zwei Möglichkeiten, einen SIP-Trunk in einer lync Server Umgebung zu implementieren: 
> <UL>
> <LI>
> <P>Verwenden Sie mehrfach vernetzte Vermittlungsserver, die ihre nach außen gerichteten öffentlich weitergeleiteten Schnittstellen verwenden, um mit dem SIP-Trunk Anbieter zu kommunizieren.</P>
> <LI>
> <P>Verwenden Sie einen lokalen Session Border Controller (SBC), um einen sicheren Abgrenzungs Pfad zwischen den Vermittlungsservern und den Diensten des SIP-Trunk Anbieters bereitzustellen.</P></LI></UL>Wenn Sie die letztere Methode auswählen, müssen Sie sicherstellen, dass die von Ihnen ausgewählte SBC-Marke und das Modell zertifiziert wurden und unterstützt die Übergabe von Anwesenheitsinformationen im Daten Format Location-Objekt (PIDF-Lo) als Teil der SIP-INVITE-Daten. Andernfalls werden die Anrufe bei dem Notrufdienst Anbieter eintreffen, der von den Standortinformationen entfernt wurde. Ausführliche Informationen zu zertifizierten SBCS finden Sie unter "qualifizierte Infrastruktur für Microsoft lync <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>" unter.<BR>Mit E9-1-1-Dienstanbietern erhalten Sie Zugriff auf ein SBCS-Paar für Redundanz. Sie müssen mehrere Entscheidungen hinsichtlich der Vermittlungsserver Topologie und der Anruf Weiterleitungskonfiguration treffen. Werden Sie beide SBCS als gleichwertige Peers behandeln und das Round-Robin-Routing für Anrufe zwischen Ihnen verwenden, oder werden Sie einen SBC als primären und den anderen als sekundären angeben?



</div>

Ausführliche Informationen zum Bereitstellen eines SIP-Trunks in lync Server finden Sie unter [wie kann ich SIP-Trunking in lync Server 2013 implementieren?](lync-server-2013-how-do-i-implement-sip-trunking.md). Die folgenden Fragen helfen Ihnen bei der Entscheidung, wie die SIP-Trunks für E9-1-1 bereitgestellt werden.

  - **Sollten Sie den SIP-Trunk über eine dedizierte geleaste oder eine gemeinsam genutzte Internetverbindung bereitstellen?**  
    Es ist wichtig, dass Notrufe immer eine Verbindung herstellen. Eine dedizierte Leitung bietet eine Verbindung, die nicht von anderen Datenverkehr im Netzwerk getrennt wird, und bietet Ihnen die Möglichkeit zur Implementierung von Quality of Service (QoS). Denken Sie daran, dass die IPSec-Verschlüsselung erforderlich ist, wenn Sie über das öffentliche Internet eine Verbindung mit Dienstanbietern für die Notfalldienste herstellen und die Vertraulichkeit von Notrufen sicherstellen müssen.

<!-- end list -->

  - **Ist Ihre E9-1-1-Bereitstellung für die Notfalltoleranz ausgelegt?**  
    Da es sich hierbei um eine Notfalllösung handelt, ist die Ausfallsicherheit wichtig. Stellen Sie Ihre primären und sekundären Vermittlungsserver und SIP-Trunks an Notfall toleranten Speicherorten bereit. Es empfiehlt sich, die primäre Vermittlungsserver bereitzustellen, die den von ihr unterstützten Benutzern am nächsten ist, und Failover-Anrufe über das sekundäre Vermittlungsserver (an einem anderen geografischen Standort) weiterleiten.

<!-- end list -->

  - **Sollten Sie einen separaten SIP-Trunk für jede Zweigstelle bereitstellen?**  
    Lync Server bietet verschiedene Strategien für die Handhabung von VoIP-Ausfallsicherheit in Zweigstellen, darunter: belastbare Datennetzwerke, Bereitstellungeines SIP-Trunks in jeder Filiale oder Pushen von Anrufen beim lokalen Gateway während Ausfällen. Ausführliche Informationen finden Sie unter [Branch Site SIP Trunking in lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **Ist die Anrufsteuerung (Call Admission Control, CAC) aktiviert?**  
    In lync Server werden Notrufe nicht anders als bei normalen anrufen behandelt. Aus diesem Grund kann sich die Bandbreitenverwaltung oder die Anrufsteuerung (Call Admission Control, CAC) negativ auf eine E9-1-1-Konfiguration auswirken. Notfallanrufe werden blockiert oder an das lokale PSTN-Gateway weitergeleitet, wenn eine Anrufsteuerung aktiviert ist und die konfigurierte Grenze für einen Link überschritten wird, an dem Notrufe weitergeleitet werden. Wie weiter oben in diesem Thema erwähnt, werden solche Anrufe keine Standortdaten haben und müssen manuell an die ECRC weitergeleitet werden.

</div>

<span> </span>

</div>

</div>

</div>

