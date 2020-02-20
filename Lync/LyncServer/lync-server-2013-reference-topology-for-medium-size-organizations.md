---
title: Lync Server 2013 Referenztopologie für mittelständische Unternehmen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c35c0053ac775ae804b6d92cb84c0ef3d77b4208
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Referenztopologie für lync Server 2013 in mittelständischen Organisationen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Die Referenztopologie mit hoher Verfügbarkeit und einem einzelnen Rechenzentrum ist auf kleine bis mittelständische Organisationen mit einem zentralen Standort zugeschnitten. Die exakte Topologie im folgenden Diagramm richtet sich an eine Organisation mit 20.000-Benutzern.

**Referenztopologie für mittelständische Unternehmen**

![Referenztopologie für ein einzelnes Datencenter Diagramm](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Referenztopologie für ein einzelnes Datencenter Diagramm")

  - **Mehr Benutzer aufnehmen, indem Sie weitere Front-End-Server hinzufügen.**    Die exakte Topologie in diesem Diagramm verfügt über drei Front-End-Server, die Unterstützung für 20.000-Benutzer bieten. Wenn Sie über einen einzelnen zentralen Standort und mehr Benutzer verfügen, können Sie dem Pool einfach weitere Front-End-Server hinzufügen. Die maximale Anzahl von Benutzern pro Pool beträgt 80.000, mit zwölf Front-End-Servern.
    
    Die Topologie mit einem einzelnen Standort kann jedoch noch mehr Benutzer unterstützen, wenn dem Standort ein weiterer Front-End-Pool hinzugefügt wird.

  - **Notfallwiederherstellung konnte hinzugefügt werden.**    Für diese Organisation ist die hohe Verfügbarkeit Ihrer lync Server Dienste ein erforderliches Feature, die Notfallwiederherstellung jedoch nicht. Der Pool der bereitgestellten Front-End-Server bietet hohe Verfügbarkeit.
    
    Wenn Sie die Möglichkeit zur Notfallwiederherstellung hinzufügen wollten, könnten Sie in der Lage sein, ein weiteres Rechenzentrum einzurichten und ein weiteres Front-End-Pool hinzuzufügen und es mit dem Front-End-Pool in Ihrem aktuellen Datencenter zu koppeln. Wenn sich dann ein Notfall auf den primären Pool ausgewirkt hat, können die Administratoren einen Failover der Benutzer zum Sicherungspool durchführen.

  - **Back-End-Server werden gespiegelt**   , um eine höhere Verfügbarkeit für grundlegende Benutzerfunktionen bereitzustellen, hat die Organisation ein gespiegeltes paar von Back-End-Servern für jede Front-End-Pool bereitgestellt. Dies ist eine neue Topologie-Option für lync Server 2013 und ist optional. Stattdessen können Sie einen einzelnen Back-End-Server bereitstellen.

  - **Monitoring Server Datenbankoptionen.**    Diese Organisation hat die Überwachung bereitgestellt, um die Qualität von Enterprise-VoIP-Anrufen und A/V-Konferenzen sicherzustellen. Die Überwachung wird auf jeder Front-End-Server bereitgestellt, und die Überwachungsdatenbank ist mit den Back-End-Servern verbunden. Wir unterstützen auch Topologien, in denen sich die Überwachungsdatenbank auf einem separaten Server befindet.

  - **Edgeserver hohe Verfügbarkeit**    in dieser Beispielorganisation mit 20.000-Benutzern, genügt nur eine Edgeserver für die Leistung. Es gibt jedoch einen Pool von zwei Edgeserver bereitgestellt, um hohe Verfügbarkeit bereitzustellen.

  - **Bereitstellungsoptionen für Zweigstellenstandorte.**    Die Organisation in dieser Topologie hat Enterprise-VoIP als VoIP-Lösung bereitgestellt. Zweigstelle 1 verfügt nicht über eine ausfallsichere WAN-Verbindung (Wide Area Network) mit dem zentralen Standort, sodass ein Survivable Branch Appliance bereitgestellt wurde, um viele lync Server Funktionen beizubehalten, falls die WAN-Verbindung zum zentralen Standort ausfällt. Zweigstellenstandort 2 verfügt über eine ausfallsichere WAN-Verbindung, daher wird nur ein PSTN-Gateway benötigt. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird an Zweigstellenstandort 2 kein Vermittlungsserver benötigt. Ausführliche Informationen zur Entscheidung, was an einem Zweigstellenstandort bereitgestellt werden soll, finden Sie unter [Planning for Branch-Site Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in der Planungsdokumentation.

  - **DNS-Lastenausgleich.**    Der Front-End-Pool andEdge-Server Pool mit DNS-Lastenausgleich für SIP-Datenverkehr bereitgestellt. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die Edgeserver erforderlich, und Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools werden erheblich vereinfacht, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

  - **Exchange UM-Bereitstellung.** Diese Referenztopologie umfasst einen Exchange Unified Messaging (um) Server, der Exchange Server und nicht lync Server ausführt.
    
    Ausführliche Informationen zu Exchange um finden Sie unter [Planning for Exchange Unified Messagingintegration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messagingintegration in lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planungsdokumentation.

  - **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Mit Office Web Apps Server können Powerpoint-Folien in Webkonferenzen präsentiert werden. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Edgeserver werden empfohlen.**    Obwohl die Bereitstellung einer Edgeserver nicht erforderlich ist, wird Sie für eine beliebige Größe der Bereitstellung empfohlen. Sie können Ihre lync Server Investition maximieren, indem Sie eine Edgeserver bereitstellen, um die Dienste für Benutzer bereitzustellen, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden. Hierdurch bieten sich folgende Vorteile:
    
      - Die eigenen Benutzer Ihrer Organisation können lync Server Funktionalität verwenden, wenn Sie von zu Hause aus arbeiten oder unterwegs sind.
    
      - Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.
    
      - Wenn Sie über einen Partner, einen Anbieter oder eine Kundenorganisation verfügen, die auch lync Server verwendet, können Sie eine *Verbundbeziehung* mit dieser Organisation bilden. Ihre lync Server-Bereitstellung würde dann Benutzer aus dieser Verbundorganisation erkennen, was zu einer besseren Zusammenarbeit führt.
    
      - Ihre Benutzer können Sofortnachrichten mit Benutzern von öffentlichen Instant Messaging-Diensten austauschen, einschließlich einer oder aller der folgenden: Windows Live, AOL,\!Yahoo und Google Talk. Für öffentliche Chat Verbindungen mit diesen Diensten ist möglicherweise eine separate Lizenz erforderlich.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
        > <LI>
        > <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
        > <LI>
        > <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>

        
        </div>

  - **Directors konnten hinzugefügt werden.**    Wenn diese Organisation die Sicherheit vor Denial-of-Service-Angriffen verbessern wollte, könnte Sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in lync Server, die keine Benutzerkonten aufweist, oder Anwesenheits-oder Konferenzdienste bereitstellen. Er dient als interner nächster Hop-Server, an den ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet. Der Director authentifiziert eingehende Anforderungen vorab und leitet Sie an den privaten Pool oder Server des Benutzers weiter. Die Vorabauthenitifizierung in Director ermöglicht das Aussortieren von Anfragen, die von Benutzerkonten stammen, die in der Bereitstellung nicht bekannt sind. Ein Director unterstützt das Isolieren von Front-End-Servern vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen (DOS). Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externem Datenverkehr überflutet wird, endet der Datenverkehr beim Director.

  - **System Center Operations Manager wird empfohlen.**   Es wird empfohlen, die Integrität ihrer lync Server-Bereitstellung zu überwachen, um die Verfügbarkeit von Diensten für Endbenutzer sicherzustellen. Sie können lync mit dem System Center Operations Manager Management Pack für lync überwachen, das als kostenloser Download von Microsoft zur Verfügung steht. Mit dem Lync Management Pack erhalten Sie proaktiv Echtzeitwarnungen, sobald Probleme auftreten, können synthetische Transaktionen ausführen, um die Lync-Funktionalität von Ende zu Ende zu testen, Berichte zur Dienstverfügbarkeit erhalten usw. Dies hilft Ihnen bei der proaktiven Behandlung von Problemen mit Ihrer Bereitstellung, bevor diese für Endbenutzer spürbar werden.

</div>

<span> </span>

</div>

</div>

</div>

