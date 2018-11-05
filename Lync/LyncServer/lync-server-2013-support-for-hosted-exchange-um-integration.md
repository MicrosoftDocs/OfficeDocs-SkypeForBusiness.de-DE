---
title: 'Lync Server 2013: Unterstützung für die Integration gehosteter Exchange UM-Dienste'
TOCTitle: Unterstützung für die Integration gehosteter Exchange UM-Dienste
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398821(v=OCS.15)
ms:contentKeyID: 49295367
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die Lync Server 2013 ExUM-Routinganwendung bietet Unterstützung für die Integration mit Exchange Unified Messaging (UM) in einer lokalen Umgebung, wobei sowohl Lync Server 2013 als auch Exchange UM lokal innerhalb des Unternehmens installiert werden, oder Exchange UM durch einen Dienstanbieter gehostet wird, wie im nachfolgenden Diagramm dargestellt.

![Lokale Lync Server-Exchange UM-Bereitstellung](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale Lync Server-Exchange UM-Bereitstellung")

Die folgenden Modi werden unterstützt:

  - **Lokaler Modus**   Sowohl Lync Server 2013 als auch Exchange UM werden auf lokalen Servern innerhalb des Unternehmens bereitgestellt.

  - **Standortübergreifender Modus**    Lync Server 2013 wird auf lokalen Servern innerhalb des Unternehmens bereitgestellt, und Exchange UM wird in der Umgebung eines Onlinedienstanbieters gehostet, beispielsweise in einem Microsoft Exchange Online-Rechenzentrum.

  - **Gemischter Modus**   Ihre Lync Server 2013-Bereitstellung umfasst einige Benutzerpostfächer auf lokalen Servern mit Microsoft Exchange Server sowie Postfächer, die in einem gehosteten Exchange-Rechenzentrum verwaltet werden.
    

    > [!NOTE]
    > Der gemischte Modus kann als Übergangslösung bei der Evaluierung und schrittweisen Migration von Benutzern auf gehostete Exchange UM-Dienste oder als dauerhafte Lösung eingesetzt werden, wenn Sie einige Exchange UM-Dienste nach der Migration weiterhin lokal verwalten möchten.



Zur Integration von Lync Server 2013 mit gehosteten Exchange UM-Diensten müssen Sie einen *freigegebenen SIP-Adressraum* konfigurieren (auch als *getrennte Domäne* bezeichnet). In dieser Konfiguration steht derselbe SIP-Domänenadressraum sowohl für Lync Server 2013 als auch für den Drittanbieter für gehostete Exchange UM-Dienste zur Verfügung. Ausführliche Informationen finden Sie unter [Architektur für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in der Planungsdokumentation.

