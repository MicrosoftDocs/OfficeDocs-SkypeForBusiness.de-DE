---
title: 'Lync Server 2013: Bereitstellungsrichtlinien für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 688cf48c7f716047f0d7412c34ce84006a5a9348
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Bereitstellungsrichtlinien für Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

In diesem Thema werden die Voraussetzungen und anderen Richtlinien beschrieben, die Sie bei der Bereitstellung von lync Server 2013 und der Enterprise-VoIP-Arbeitsauslastung berücksichtigen sollten.

<div>

## <a name="deployment-prerequisites"></a>Voraussetzungen für die Bereitstellung

Für eine optimale Benutzerfreundlichkeit bei der Bereitstellung von Enterprise-VoIP stellen Sie sicher, dass Ihre IT-Infrastruktur, Ihr Netzwerk und ihre Systeme die folgenden Voraussetzungen erfüllen:

  - Lync Server 2013 Standard Edition oder Enterprise Edition ist in Ihrem Netzwerk installiert und betriebsbereit.

  - Alle Edgeserver werden in Ihrem Umkreisnetzwerk bereitgestellt und in Betrieb genommen, einschließlich Edgeserver mit Zugriffs-Edgedienst, A/V-Edgedienst, Webkonferenz-Edgedienst und einem Reverse-Proxy.

  - Mindestens ein Benutzer wurde für lync Server erstellt und aktiviert.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) oder neuestes Service Pack oder Microsoft Exchange Server 2010 installiert ist. Eine davon ist für die Integration von Exchange Unified Messaging (um) mit lync Server erforderlich, um umfangreiche Benachrichtigungen und Anrufprotokoll Informationen für Clientendpunkte bereitzustellen.

  - Für jeden Benutzer, der für Enterprise-VoIP aktiviert werden soll, wurde eine eindeutige primäre Telefonnummer festgelegt, normalisiert und in das Attribut **msRTCSIP-Linie** kopiert.
    
    <div>
    

    > [!NOTE]  
    > Lync Server unterstützt E. 164-Nummern und DID-Nummern (nicht direktes Inward Dialing). Nicht-DID-Nummern können im Format <STRONG> &lt;E. 164&gt;; Ext =&lt;Extension&gt; </STRONG> oder als Ziffernfolge dargestellt werden, mit der Voraussetzung, dass die private Durchwahl im gesamten Unternehmen eindeutig ist. Beispielsweise kann eine private Zahl von 1001 als <STRONG>+ 1425550100; ext = 1001</STRONG>oder als <STRONG>1001</STRONG>dargestellt werden. Wenn er als <STRONG>1001</STRONG>dargestellt wird, besteht die Erwartung, dass diese private Nummer im gesamten Unternehmen eindeutig ist.

    
    </div>

  - Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglieder der Gruppe RTCUniversalServerAdmins sein.

  - Office Communicator 2007 wird mindestens erfolgreich bereitgestellt. Für die Verwendung neuer Features in dieser Version wird lync 2013 bereitgestellt.

  - Es wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter eine Managed Key-Infrastruktur (MKI) bereitgestellt und konfiguriert.

  - Für jeden Computer, auf dem Sie einen Vermittlungsserver installieren, gilt Folgendes:
    
      - Ein Mitgliedsserver einer Domäne, der für Active Directory-Domänendienste vorbereitet wurde. Informationen Active Directory-Domänendienste Vorbereitungsverfahren finden Sie unter [vorbereiten Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.
    
      - Es muss eines der folgenden Betriebssysteme ausgeführt werden:
        
          - <span></span>  
            Die 64-Bit-Version von Windows Server 2008 Standard
        
          - <span></span>  
            Die 64-Bit-Version von Windows Server 2008 Enterprise

  - Wenn die Verbindung zum Telefonfestnetz (Public Switched Telephone Network, PSTN) oder zu einer Nebenstellenanlage (Private Branch Exchange, PBX) per TDM-Verbindung (Time Division Multiplexing) erfolgt, stehen für die Bereitstellung ein oder mehrere PSTN-Gateways zur Verfügung. (Falls die Verbindung über einen SIP-Trunk hergestellt wird, ist kein PSTN-Gateway erforderlich.)

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Stromausfall, Ausfall des Netzwerks oder des Telefondiensts

Wenn ein Ausfall, eine Unterbrechung oder andere Beeinträchtigungen der Stromversorgung, des Netzwerks oder der Telefondienste an Ihrem Standort auftreten, funktionieren die sprach-, Chat-, Anwesenheits-und andere Features von lync Server sowie alle mit lync Server verbundenen Geräte möglicherweise nicht ordnungsgemäß.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>Abhängigkeit von Enterprise-VoIP von der Verfügbarkeit des Servers sowie der Funktionsfähigkeit des VoIP-Client und der Hardware

Die Sprachkommunikation mit lync Server hängt von der Verfügbarkeit der Server Software und der ordnungsgemäßen Funktion der VoIP-Clients oder der Hardware Telefongeräte ab, die eine Verbindung mit der Server Software herstellen.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Alternativer Zugriff auf Notrufdienste

Für die Standorte, an denen Sie einen VoIP-Client installieren (beispielsweise einen PC, auf dem lync-Client oder ein lync Phone Edition-Gerät ausgeführt wird), wird empfohlen, dass Sie eine Sicherungsoption für Benutzer zum Aufrufen von Notrufdiensten (beispielsweise 911 oder 999) für den Fall eines Stromausfalls beibehalten. , Beeinträchtigung der Netzwerkkonnektivität, Ausfall eines Telefondiensts oder ein anderes Problem, das den Betrieb von lync Server-, lync-oder lync Phone Edition-Geräten hemmen kann. Zu diesen alternativen Optionen kann ein Telefon gehören, das mit einer standardmäßigen Telefonnetz Leitung oder einem Mobiltelefon verbunden ist.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Notruf und Telefonsysteme mit mehreren Leitungen

Die Verwendung von Mehrleitungstelefonsystemen (MLTS) unterliegt eventuell gesetzlichen Bestimmungen, die bei einem Notruf die Angabe der Rufnummer, der Durchwahl und/oder des physischen Standorts des Anrufers erfordern. In dieser Version können lync Server so konfiguriert werden, dass der physische Standort eines Anrufers für einen Anbieter von Notrufdiensten bereitgestellt wird, wie in [Planning for Emergency Services (E9-1-1) in lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)beschrieben. Die Einhaltung von MLTS-Gesetzen liegt in der alleinigen Verantwortung des Käufers von lync Server-, lync-Client-und lync Phone Edition-Geräten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

