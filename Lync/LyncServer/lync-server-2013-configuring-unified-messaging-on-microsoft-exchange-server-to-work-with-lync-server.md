---
title: 'Lync Server 2013: Konfigurieren von Unified Messaging für Exchange Server für die Verwendung von lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cbb859a3cd9f49791eb7b959a59c00c38db6336
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41995970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Konfigurieren von Unified Messaging für Exchange Server zum Arbeiten mit lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Wenn Sie Exchange Unified Messaging (um) verwenden möchten, um Mailboxansage, Outlook Voice Access oder automatische Telefonzentralendienste für Enterprise-VoIP-Benutzer bereitzustellen, lesen Sie <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planen der Integration von Exchange Unified Messaging in lync Server 2013</A> in der Planungsdokumentation, und befolgen Sie dann die Anweisungen in diesem Abschnitt.



</div>

Um Exchange Unified Messaging (um) für die Zusammenarbeit mit Enterprise-VoIP zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen:

  - Konfigurieren von Zertifikaten auf dem Server mit Exchange Unified Messaging (um) Diensten
    
    <div>
    

    > [!NOTE]  
    > Fügen Sie alle Client Zugriffs-und Postfachserver allen um-SIP-URI-Wählplänen hinzu. Wenn dies nicht der Fall ist, funktioniert das Routing für ausgehende Anrufe nicht wie erwartet.

    
    </div>

  - Erstellen Sie bei Bedarf einen oder mehrere um-SIP-URI-Wählpläne zusammen mit den Telefonnummern für den Teilnehmerzugriff, und erstellen Sie dann entsprechende lync Server Wählpläne.

  - Verwenden Sie das **Skript "exchucutil. ps1-** Skript für Folgendes:
    
      - Erstellen von UM-IP-Gateways
    
      - Erstellen von UM-Sammelanschlüssen
    
      - Erteilen Sie lync Server 2013 Berechtigung zum Lesen von um-Active Directory-Domänendienste Objekten.

  - Erstellen Sie ein um-Objekt der automatischen Telefonzentrale.

  - Erstellen eines Teilnehmerzugriffs Objekts.

  - Erstellen Sie einen SIP-URI für jeden Benutzer, und verknüpfen Sie Benutzer mit einem um-SIP-URI-Wählplan.

<div>

## <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Bevor Sie beginnen, wird in der Dokumentation in diesem Abschnitt davon ausgegangen, dass Sie die folgenden Exchange 2013 Rollen bereitgestellt haben: Client Zugriff und Postfach. In Microsoft Exchange Server 2013 wird Exchange um als Dienst auf diesen Servern ausgeführt.

Ausführliche Informationen zum Bereitstellen von Exchange 2013 finden Sie in der Exchange 2013 TechNet-Bibliothek unter[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

Beachten Sie auch Folgendes:

  - Wenn Exchange um in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server Integrationsschritte für jede um-Gesamtstruktur ausgeführt werden. Darüber hinaus muss jede um-Gesamtstruktur so konfiguriert werden, dass Sie der Gesamtstruktur vertraut, in der lync Server 2013 bereitgestellt wird, und die Gesamtstruktur, in der lync Server 2013 bereitgestellt wird, muss so konfiguriert sein, dass jeder um-Gesamtstruktur vertraut wird.

  - Integrationsschritte werden sowohl für die Exchange Server Rollen, in denen Unified Messaging-Dienste ausgeführt werden, als auch auf dem Server ausgeführt, auf dem lync Server 2013 ausgeführt wird. Sie sollten die Exchange Server Unified Messaging-Integrationsschritte durchführen, bevor Sie die lync Server 2013 Integrationsschritte durchführen.
    
    <div>
    

    > [!NOTE]  
    > Informationen dazu, welche Integrationsschritte auf welchen Servern und mit welchen Administratorrollen ausgeführt werden, finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment Process for Integration on-premises Unified Messaging and lync Server 2013</A>.

    
    </div>

Die folgenden Tools müssen auf jedem Server mit Exchange um verfügbar sein:

  - Exchange-Verwaltungsshell

  - Das Skript **exchucutil.ps1**, mit dem die folgenden Aufgaben ausgeführt werden:
    
      - Erstellt ein um-IP-Gateway für jeden lync Server 2013.
    
      - Erstellen eines Sammelanschlusses für jedes Gateway. Die Pilot-ID jedes Sammelanschlusses gibt die um-SIP-URI-Wähleinstellungen an, die von der Front-End-Pool oder Standard Edition-Server verwendet werden, die dem Gateway zugeordnet ist.
    
      - Erteilt lync Server 2013 Berechtigung zum Lesen von Exchange um-Objekten in Active Directory-Domänendienste.

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging läuft](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Konfigurieren von Unified Messaging für Microsoft Exchange für lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

