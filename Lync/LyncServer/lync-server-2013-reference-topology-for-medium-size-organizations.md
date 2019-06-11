---
title: 'Lync Server 2013: Referenztopologie für mittelständische Organisationen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41a003bd87e4dc8b85e78946a5ce870f3f6dd045
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Referenztopologie für Lync Server 2013 für mittelständische Organisationen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Die Referenztopologie mit hoher Verfügbarkeit und einem einzelnen Rechenzentrum ist auf kleine bis mittelständische Organisationen mit einem zentralen Standort zugeschnitten. Die im folgenden Diagramm gezeigte exakte Topologie ist auf 20.000 Benutzer ausgelegt.

**Referenztopologie für mittelständige Organisationen**

![Referenztopologie für ein einzelnes Datencenter-Diagramm] (images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Referenztopologie für ein einzelnes Datencenter-Diagramm")

  - **Mehr Benutzer aufnehmen, indem Sie weitere Front-End-Server hinzufügen.**    Die exakte Topologie in diesem Diagramm verfügt über drei Front-End-Server, die Unterstützung für 20.000-Benutzer bereitstellen. Wenn Sie über einen einzelnen zentralen Standort und mehr Benutzer verfügen, können Sie dem Pool einfach weitere Front-End-Server hinzufügen. Die maximale Anzahl von Benutzern pro Pool beträgt 80.000 mit zwölf Front-End-Servern.
    
    Die Topologie mit einem einzelnen Standort kann jedoch noch mehr Benutzer unterstützen, wenn dem Standort ein weiterer Front-End-Pool hinzugefügt wird.

  - **Disaster Recovery könnte hinzugefügt werden.**    Für diese Organisation ist eine höhere Verfügbarkeit für Ihre lync Server-Dienste ein notwendiges Feature, aber Disaster Recovery ist nicht erforderlich. Der von Ihnen bereitgestellte Pool der Front-End-Server bietet eine große Verfügbarkeit.
    
    Wenn die Fähigkeit zur Notfallwiederherstellung hinzugefügt werden soll, könnte die Organisation ein weiteres Rechenzentrum einrichten und dort einen weiteren Front-End-Pool hinzufügen, der dann mit dem Front-End-Pool im aktuellen Rechenzentrum kombiniert wird. Dadurch könnten die Administratoren bei einem Notfall, der den primären Pool betrifft, einen Failover der Benutzer auf den Sicherungspool durchführen.

  - **Back-End-Server werden gespiegelt**   , um eine höhere Verfügbarkeit für grundlegende Benutzer Features bereitzustellen, hat die Organisation ein gespiegeltes paar von Back-End-Servern für jeden Front-End-Pool bereitgestellt. Hierbei handelt es sich um eine neue Topologie-Option für lync Server 2013, die optional ist. Stattdessen können Sie einen einzelnen Back-End-Server bereitstellen.

  - **Überwachungs Server-Datenbankoptionen**    Diese Organisation hat die Überwachung bereitgestellt, um die Qualität von Enterprise-Sprachanrufen und A/V-Konferenzen zu gewährleisten. Die Überwachung wird auf jedem Front-End-Server bereitgestellt und die Überwachungsdatenbank wird mit den Back-End-Servern verbunden. Außerdem werden Topologien unterstützt, in denen sich die Überwachungsdatenbank auf einem separaten Server befindet.

  - Spitzen **Server-Verfügbarkeit**    In dieser Beispielorganisation mit 20.000-Benutzern reicht nur ein Edgeserver für die Leistung aus. Es gibt jedoch einen Pool von zwei Edgeserver, die bereitgestellt werden, um eine höhere Verfügbarkeit bereitzustellen.

  - **Bereitstellungsoptionen für Verzweigungs Websites**    Die Organisation in dieser Topologie hat Enterprise-VoIP als Sprachlösung bereitgestellt. Branch Site 1 verfügt nicht über eine stabile WAN-Verbindung (Wide Area Network) mit dem zentralen Standort, sodass eine überlebensfähige Branch-Appliance bereitgestellt wird, um viele lync Server-Features zu verwalten, falls die WAN-Verbindung zur zentralen Website ausfällt. Zweigstelle 2 verfügt über eine ausfallsichere WAN-Verbindung, daher wird nur ein PSTN-Gateway benötigt. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird in Zweigstelle 2 kein Vermittlungsserver benötigt. Ausführliche Informationen zur Entscheidung, was auf einer Zweigstelle bereitgestellt werden soll, finden Sie unter [Planen der sprach Sicherheit in der Zweigstelle in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in der Planungsdokumentation.

  - **DNS-Lastenausgleich**    Im Front-End-Pool-andEdge-Server Pool ist der DNS-Lastenausgleich für den SIP-Datenverkehr bereitgestellt. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die Edgeserver erforderlich und Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools werden erheblich vereinfacht, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Details zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

  - **Exchange UM-Bereitstellung.** Diese Referenztopologie umfasst einen Exchange Unified Messaging (um)-Server, auf dem Microsoft Exchange Server ausgeführt wird, nicht lync Server.
    
    Ausführliche Informationen zu Exchange um finden Sie unter [Planen der Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) und [gehostete Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planning-Dokumentation.

  - **Office Web Apps Server.** Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Der Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen. Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Edgeserver werden empfohlen.**    Obwohl die Bereitstellungeines Edgeserver nicht erforderlich ist, empfehlen wir ihn für eine beliebige Größe der Bereitstellung. Sie können Ihre lync Server-Investition maximieren, indem Sie einen Edgeserver bereitstellen, um die Dienste für Benutzer bereitzustellen, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden. Dies bietet folgende Vorteile:
    
      - Die eigenen Benutzer Ihrer Organisation können die lync-Server Funktionalität verwenden, wenn Sie von zu Hause aus arbeiten oder unterwegs sind.
    
      - Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.
    
      - Wenn Sie über einen Partner, einen Kreditor oder eine Kundenorganisation verfügen, die ebenfalls lync Server verwendet, können Sie eine *Verbundbeziehung* mit dieser Organisation bilden. Ihre lync Server-Bereitstellung erkennt dann Benutzer aus dieser Verbundorganisation, was zu einer besseren Zusammenarbeit führt.
    
      - Ihre Benutzer können Sofortnachrichten mit Benutzern von öffentlichen Chat Diensten austauschen, einschließlich einer oder aller der folgenden: Windows Live, AOL, Yahoo\!und Google Talk. Für die Konnektivität öffentlicher Chats mit diesen Diensten ist möglicherweise eine separate Lizenz erforderlich.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum beendet hat. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
        > <LI>
        > <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</P>
        > <LI>
        > <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</P></LI></UL>

        
        </div>

  - **Directors können hinzugefügt werden.**    Wenn diese Organisation dazu beitragen soll, die Sicherheit vor Denial-of-Service-Angriffen zu erhöhen, kann Sie auch einen Pool von Directors bereitstellen. Bei einem Director handelt es sich um eine separate, optionale Serverrolle in lync Server, auf der keine Benutzerkonten zu Hause sind, oder Anwesenheits-oder Konferenzdienste bereitstellen. Sie fungiert als interner Server für den nächsten Hop, auf dem ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet. Der Director authentifiziert eingehende Anforderungen vorab und leitet Sie an den privaten Pool oder Server des Benutzers weiter. Die Vorabauthentifizierung durch den Director ermöglicht das Verwerfen von Anfragen von Benutzerkonten, die der Bereitstellung nicht bekannt sind. Ein Director hilft, Front-End-Server vor böswilligem Datenverkehr zu isolieren, wie DOS-Attacken (Denial-of-Service). Wenn das Netzwerk bei einem solchen Angriff mit einem ungültigen externen Datenverkehr überflutet wird, endet der Datenverkehr beim Director.

  - **System Center Operations Manager wird empfohlen.**   Wir empfehlen, dass Sie den Status Ihrer lync Server-Bereitstellung überwachen, um die Dienstverfügbarkeit für Endbenutzer zu gewährleisten. Sie können lync mit dem System Center Operations Manager-Management Pack für lync überwachen, das als kostenloser Download von Microsoft zur Verfügung steht. Mit dem lync-Management Pack können Sie proaktiv Echtzeitbenachrichtigungen erhalten, wenn Probleme auftreten, synthetische Transaktionen ausführen, um die End-to-End-lync-Funktionalität zu testen, Berichte für die Dienstverfügbarkeit abzurufen usw. This helps you to proactively respond to issues with your deployment before end-users experience them.

</div>

<span> </span>

</div>

</div>

</div>

