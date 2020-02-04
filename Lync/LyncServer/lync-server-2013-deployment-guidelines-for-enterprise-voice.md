---
title: 'Lync Server 2013: Richtlinien für die Enterprise-VoIP-Bereitstellung'
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
ms.openlocfilehash: 221c09fc5dadda267baad35f4784c22cc4f3c9c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Richtlinien für die Enterprise-VoIP-Bereitstellung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

In diesem Thema werden die Voraussetzungen und anderen Richtlinien beschrieben, die bei der Bereitstellung von lync Server 2013 und der Enterprise-VoIP-Arbeitsauslastung zu beachten sind.

<div>

## <a name="deployment-prerequisites"></a>Voraussetzungen für die Bereitstellung

Für eine optimale Benutzerfreundlichkeit bei der Bereitstellung von Enterprise-VoIP stellen Sie sicher, dass Ihre IT-Infrastruktur, Ihr Netzwerk und ihre Systeme die folgenden Voraussetzungen erfüllen:

  - Lync Server 2013 Standard Edition oder Enterprise Edition ist in Ihrem Netzwerk installiert und betriebsbereit.

  - Alle Edgeserver werden in Ihrem Umkreisnetzwerk bereitgestellt und in Betrieb genommen, einschließlich Edgeserver mit Access Edge Service, a/V Edge Service, Web Conferencing Edge Service und einem Reverse Proxy.

  - Mindestens ein Benutzer wurde für lync Server erstellt und aktiviert.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) oder neuestes Service Pack oder Microsoft Exchange Server 2010 ist installiert. Eine dieser Funktionen ist für die Integration von Exchange Unified Messaging (um) in lync Server und für die Bereitstellung umfassender Benachrichtigungen und Anrufprotokoll Informationen für Clientendpunkte erforderlich.

  - Für jeden Benutzer, der für Enterprise-VoIP aktiviert werden soll, wurde eine eindeutige primäre Telefonnummer festgelegt, normalisiert und in das **Attribut msRTCSIP-** Attribut kopiert.
    
    <div>
    

    > [!NOTE]  
    > Lync Server unterstützt E. 164-Nummern und nicht Direkteinwahl Nummern (DID). Nicht-did-Zahlen können im Format <STRONG> &lt;E. 164&gt;; Ext =&lt;Extension&gt; </STRONG> oder als Zeichenfolge von Ziffern dargestellt werden, mit der Voraussetzung, dass die private Erweiterung im gesamten Unternehmen eindeutig ist. Beispielsweise kann eine private Zahl von 1001 als <STRONG>+ 1425550100; ext = 1001</STRONG>oder als <STRONG>1001</STRONG>dargestellt werden. Wenn Sie als <STRONG>1001</STRONG>dargestellt wird, wird davon ausgegangen, dass diese private Nummer im gesamten Unternehmen eindeutig ist.

    
    </div>

  - Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglieder der RTCUniversalServerAdmins-Gruppe sein.

  - Office Communicator 2007 wird mindestens erfolgreich bereitgestellt. Um Features zu verwenden, die in dieser Version neu sind, wird lync 2013 bereitgestellt.

  - Die Managed Key-Infrastruktur (MkII) wird mithilfe einer Microsoft-oder einer Drittanbieter-Infrastruktur (Certification Authority, ca) bereitgestellt und konfiguriert.

  - Jeder Computer, auf dem Sie den Vermittlungs Server installieren, muss wie folgt lauten:
    
      - Einen Mitgliedsserver einer Domäne und für die Active Directory-Domänendienste vorbereitet. Informationen zur Vorbereitung der Active Directory-Domänendienste finden Sie unter [Vorbereiten der Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.
    
      - Führen Sie eines der folgenden Betriebssysteme aus:
        
          - <span></span>  
            Die 64-Bit-Version des Windows Server 2008-Standard Betriebssystems
        
          - <span></span>  
            Die 64-Bit-Version des Windows Server 2008 Enterprise-Betriebssystems

  - Wenn die Verbindung mit dem PSTN (Public Switched Telephone Network) oder der PBX (Private Branch Exchange) über eine Time Division Multiplexing (TDM)-Verbindung erfolgt, stehen mindestens ein PSTN-Gateway für die Bereitstellung zur Verfügung. (Wenn die Verbindung über einen SIP-Stamm erfolgt, ist kein PSTN-Gateway erforderlich.)

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Strom-, Netzwerk-oder Telefondienst Ausfälle

Wenn es zu einem Ausfall, zu einer Unterbrechung oder zu einer anderen Verschlechterung der Strom-, Netzwerk-oder Telefondienste an Ihrem Standort kommt, funktionieren die sprach-, Chat-, Anwesenheits-und anderen Funktionen von lync Server und jedes mit lync Server verbundene Gerät möglicherweise nicht ordnungsgemäß.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>Enterprise-VoIP hängt von der Server Verfügbarkeit und der Funktionsfähigkeit des sprach Clients und der Hardware ab

Die Sprachkommunikation mit lync Server hängt von der Verfügbarkeit der Server Software und der ordnungsgemäßen Funktion der VoIP-Clients oder der Hardware-Telefongeräte ab, die mit der Server Software verbunden sind.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Alternative Möglichkeiten für den Zugriff auf Notfalldienste

Für die Speicherorte, an denen Sie einen VoIP-Client installieren (beispielsweise einen PC mit lync-Client oder ein lync Phone Edition-Gerät), empfehlen wir, dass Sie eine Sicherungsoption für Benutzer zum Aufrufen von Notfalldiensten (beispielsweise 911 oder 999) im Fall eines Stromausfalls verwalten. , Netzwerk Verbindungs Verschlechterung, Ausfall des Telefondiensts oder anderes Problem, das den Betrieb von lync Server-, lync-oder lync Phone Edition-Geräten hemmen kann. Solche Alternativen können auch ein Telefon sein, das an eine standardmäßige öffentlich geschaltete Telefonnetz Leitung oder ein Mobiltelefon angeschlossen ist.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Notrufe und mehrzeilige Telefonanlagen

Die Verwendung eines mehrzeiligen Telefonsystems (MLTS) unterliegt möglicherweise den US-bundesstaatlichen oder bundesstaatlichen Gesetzen oder den Gesetzen anderer Länder/Regionen, in denen die MLTS die Telefonnummer, die Durchwahl und/oder den physischen Standort eines Anrufers für die entsprechenden Notfalldienste zur Verfügung stellen muss, wenn ein Anrufer in die Notfalldienste gestellt wird (beispielsweise bei der Wahl einer 999 911 Notruf In dieser Version kann lync Server so konfiguriert werden, dass der physikalische Standort eines Anrufers einem Notrufdienst Anbieter bereitgestellt wird, wie unter [Planen von Notfalldiensten (E9-1-1) in lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)beschrieben. Die Einhaltung der MLTS-Gesetze obliegt der alleinigen Verantwortung des Käufers von lync Server-, lync-Client-und lync Phone Edition-Geräten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

