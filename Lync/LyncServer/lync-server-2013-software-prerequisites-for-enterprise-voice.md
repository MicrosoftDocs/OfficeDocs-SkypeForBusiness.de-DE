---
title: 'Lync Server 2013: Software Voraussetzungen für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4b0b2e2708abbf3b92223474ec0804c1d11ac8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Software Voraussetzungen für Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Stellen Sie sicher, dass die zur Bereitstellung von Enterprise-VoIP vorgesehene Infrastruktur die folgenden Softwareanforderungen erfüllt:

  - Lync Server 2013 Standard Edition oder Enterprise Edition ist in Ihrem Netzwerk installiert und betriebsbereit.

  - Alle Edgeserver werden in Ihrem Umkreisnetzwerk bereitgestellt und in Betrieb genommen, einschließlich Edgeserver mit Zugriffs-Edgedienst, A/V-Edgedienst, Webkonferenz-Edgedienst und einem Reverseproxy.

  - Für die Integration von Exchange Unified Messaging mit lync Server ist entweder Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 oder Microsoft Exchange Server 2013 erforderlich, und Sie erhalten umfangreiche Benachrichtigungen und Anrufprotokoll Informationen für Lync-Endpunkte.

  - Mindestens ein Benutzer wurde für lync Server erstellt und aktiviert.

  - Lync-Clients und-Geräte wurden erfolgreich bereitgestellt.

  - Der Topologie-Generator wird auf einem Server in Ihrem Netzwerk installiert.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Nächste Schritte: Überprüfen der Anforderungen an Sicherheit und Konfiguration

Nachdem Sie sich vergewissert haben, dass die Softwareanforderungen für Enterprise-VoIP erfüllt wurden, können Sie anhand der folgenden Dokumentation die Bereitstellung von Enterprise-VoIP weiter vorbereiten:

1.  Überprüfen Sie die Sicherheit, Benutzerkonfiguration und Hardware Vergünstigungen, wie unter [Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)beschrieben.

2.  Installieren Sie die Vermittlungsserver, wie in [Installieren der Dateien für Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)beschrieben, jedoch *nur* , wenn Sie eine eigenständige Vermittlungsserver oder einen Pool bereitstellen möchten, da Vermittlungsserver im Rahmen des Front-End-Pool-oder Standard Edition-Server Bereitstellungsprozesses installiert werden.

3.  Konfigurieren Sie trunk Verbindungen für die Bereitstellung der PSTN-Konnektivität für Benutzer, wie unter [Configuring Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)beschrieben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

