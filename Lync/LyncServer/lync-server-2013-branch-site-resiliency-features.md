---
title: 'Lync Server 2013: Ausfallsicherheitsfunktionen für Zweigstellenstandorte'
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
ms.openlocfilehash: a490de36322914235346cbc141784aab2c24f2ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Ausfallsicherheitsfunktionen für Zweigstellenstandorte in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-10_

Wenn Sie eine Ausfallsicherheit für Zweigstellen angeben, wenn die WAN-Verbindung einer Zweigstelle zu einem zentralen Standort fehlschlägt oder wenn der zentrale Standort nicht erreichbar ist, sollten die folgenden Sprachfeatures weiterhin zur Verfügung stehen:

<div>


  - Eingehende und ausgehende PSTN-Anrufe (Public Switched Telephone Network)

  - Enterprise-Anrufe zwischen Benutzern am gleichen Standort und zwischen zwei unterschiedlichen Websites

  - Einfache Anrufbehandlung, einschließlich Anruf halten, abrufen und übertragen

  - Instant Messaging mit zwei Teilnehmern

  - Anrufweiterleitung, gleichzeitiges Klingeln von Endpunkten, Anrufdelegierung und Team Anrufdienste, aber nur, wenn der delegator und Stellvertreter (beispielsweise ein Manager und der Administrator des Managers) oder alle Teammitglieder am gleichen Standort konfiguriert sind

  - Anruf Detaildatensätze (CDRs)

  - PSTN-Einwahlkonferenzen mit automatischer Konferenz Automatik

  - Voicemail-Funktionen, wenn Sie die Einstellungen für die Umleitung von Voicemail konfigurieren. (Ausführliche Informationen finden Sie unter Anforderungen an die [Stabilität der Zweigstelle für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)

  - Benutzerauthentifizierung und Autorisierung

Die folgenden Features stehen nur zur Verfügung, wenn Ihre Resilienz-Lösung eine vollständige lync Server-Bereitstellung auf der Zweigstelle ist:

  - Chat-, Web-und A/V-Konferenzen

  - Anwesenheits-und (nicht stören)-basiertes Routing (wenn Anrufe an Erweiterungen, die mit "nicht aktiviert" sind, verhindert werden)

  - Aktualisieren der Einstellungen für die Anrufweiterleitung

  - Anwendung für Reaktionsgruppen und Anruf parken

  - Bereitstellungneuer Telefone und Clients, jedoch nur, wenn die Active Directory-Domänendienste auf der Zweigstelle vorhanden sind.

  - Enhanced 9-1-1 (E9-1-1)
    
    Wenn E9-1-1 bereitgestellt wird und der SIP-Stamm am zentralen Standort nicht zur Verfügung steht, weil die WAN-Verbindung nicht verfügbar ist, leitet die Survivable Branch-Appliance E9-1-1-Anrufe an das lokale Verzweigung-Gateway weiter. Um dieses Feature zu aktivieren, sollten die VoIP-Richtlinien für die Zweigstellenbenutzer im Fall eines WAN-Fehlers Anrufe an das lokale Gateway weiterleiten.

<div>


> [!NOTE]  
> SBA (Survivor Branch Office) wird für XMPP nicht unterstützt. Benutzer, die in einer SBA-Konfiguration verwaltet werden, können keine IMS senden oder Anwesenheitsinformationen mit XMPP-Kontakten anzeigen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

