---
title: 'Lync Server 2013: Features für Ausfallsicherheit für Zweigstellenstandorte'
description: 'Lync Server 2013: Features für Ausfallsicherheit für Zweigstellenstandorte.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552201"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-10_

Wenn Sie Ausfallsicherheit für Zweigstellenstandorte bereitstellen, sollten die folgenden VoIP-Funktionen weiterhin verfügbar sein, wenn die WAN-Leitung zwischen einem Zweigstellenstandort und einem zentralen Standort ausfällt oder der zentrale Standort nicht verfügbar ist.

<div>


  - Eingehende und ausgehende PSTN-Anrufe (Public Switched Telephone Network)

  - Enterprise-Anrufe zwischen Benutzern, die sich entweder am selben oder an zwei verschiedenen Standorten befinden

  - Grundlegende Anrufbehandlung, einschließlich Halten, Wiederaufnahme und Übergabe

  - Instant Messaging mit zwei Teilnehmern

  - Anrufweiterleitung, gleichzeitiges Klingeln von Endgeräten, Anrufdelegierung und Teamanrufdienste – jedoch nur, wenn beide Teilnehmer für die Anrufdelegierung (z. B. ein Manager und der Administrator des Managers) oder alle Teammitglieder am selben Standort konfiguriert sind.

  - Kommunikationsdatensätze (KDS)

  - PSTN-Einwahlkonferenzen mit automatischer Konferenzzentrale

  - Voicemailfunktionen, sofern Sie Einstellungen für die Voicemailumleitung konfigurieren. (Ausführliche Informationen finden Sie unter Anforderungen an die [Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)

  - Benutzerauthentifizierung und -autorisierung

Die folgenden Funktionen stehen nur zur Verfügung, wenn es sich bei ihrer ausfallsicherheitslösung um eine umfassende lync Server-Bereitstellung am Zweigstellenstandort handelt:

  - IM-, Web- und A/V-Konferenzen

  - Anwesenheits- und DND-basiertes Routing (Telefon soll bei eingehenden Anrufen an Ihre Durchwahlnummern mit dem Status "Nicht stören" nicht klingen)

  - Aktualisieren der Einstellungen für die Anrufweiterleitung

  - Reaktionsgruppenanwendung und Anwendung zum Parken von Anrufen

  - Die Einrichtung neuer Telefone und Clients, jedoch nur, wenn Active Directory-Domänendienste am Zweigstellenstandort vorhanden ist.

  - 9-1-1 (erweitert) (E9-1-1)
    
    Wenn E9-1-1 bereitgestellt wird und der SIP-Trunk am zentralen Standort nicht zur Verfügung steht, weil die WAN-Verbindung nicht verfügbar ist, leitet der Survivable Branch Appliance E9-1 -1-Anrufe an das lokale Zweigstellen Gateway weiter. Zum Aktivieren dieser Funktion muss die Weiterleitung von Anrufen an das lokale Gateway bei einem WAN-Ausfall in den VoIP-Richtlinien der Zweigstellenbenutzer festgelegt werden.

<div>


> [!NOTE]  
> SBA (Survivable Branch Office) wird für XMPP nicht unterstützt. Benutzer, die in einer SBA-Konfiguration verwaltet werden, können IMS nicht senden oder Anwesenheitsinformationen mit XMPP-Kontakten sehen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

