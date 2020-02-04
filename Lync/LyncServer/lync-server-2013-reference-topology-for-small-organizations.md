---
title: Lync Server 2013-Referenztopologie für kleine Organisationen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Referenztopologie für lync Server 2013 in kleinen Organisationen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine robuste, hoch verfügbare Lösung bereitstellen können, indem Sie nur drei Server mit lync Server bereitstellen.

**Referenztopologie für kleine Organisationen**

![Referenztopologie mit drei Servern (Diagramm)](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Referenztopologie mit drei Servern (Diagramm)")

  - **Paar von Standard Edition-Servern**     , die diese Organisation bereitgestellt hat, hat 4.000-Benutzer an Ihrem zentralen Standort. Die Organisation hat zwei Standard Edition-Server bereitgestellt und kombiniert, um eine höhere Verfügbarkeit und Disaster Recovery zu ermöglichen. Jeder Server verfügt über 2.000-Benutzer, aber Informationen zu allen Benutzern werden zwischen den beiden Servern synchronisiert. Wenn einer ausfällt, kann ein Administrator für diese Benutzer einen Failover durchführen, um von dem anderen Server bedient zu werden, mit einem mindestunterbrechungs Intervall für die Benutzer. Weitere Informationen zu Funktionen für die Hochverfügbarkeits-und Disaster Recovery in lync Server 2013 finden Sie unter [Planen von Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Die Bereitstellung von Edge-Servern wird empfohlen.**    Obwohl die Bereitstellungeines Edgeserver für interne Chats, Anwesenheitsfunktionen und Konferenzen nicht erforderlich ist, empfehlen wir dies auch für kleine Bereitstellungen. Sie können Ihre lync Server-Investition maximieren, indem Sie einen Edgeserver bereitstellen, um die Dienste für Benutzer bereitzustellen, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden. Dies bietet folgende Vorteile:
    
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

  - **Überlebensfähigkeit der Verzweigungs Website.**    In dieser Organisation wird ein Pilotprogramm des Enterprise-VoIP-Features von lync Server ausgeführt. Einige Benutzer verwenden lync Server als einzige Sprachlösung. Einige dieser sprach Pilotbenutzer befinden sich auf der Zweigstelle. Die Verzweigungs Website verfügt nicht über einen zuverlässigen WAN-Link (Wide Area Network) mit dem zentralen Standort, daher wird eine Survivable Branch-Appliance dort bereitgestellt. Dank der Survivable Branch-Anwendung können die Benutzer in der Zweigstelle bei Ausfall der WAN-Verbindung weiterhin Anrufe tätigen und entgegennehmen (sowohl innerhalb der Organisation als auch über das Festnetz), die Voicemailfunktion nutzen und per Chat kommunizieren. Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist.

  - **Exchange UM-Bereitstellung.** Diese Referenztopologie umfasst einen Exchange Unified Messaging (um)-Server, auf dem Microsoft Exchange Server ausgeführt wird, nicht lync Server.
    
    Ausführliche Informationen zu Exchange um finden Sie unter [Planen der Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) und [gehostete Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planning-Dokumentation.

  - **Office Web Apps Server.** Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Mit Office Web Apps Server können PowerPoint-Folien in Webkonferenzen präsentiert werden. Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

