---
title: 'Lync Server 2013: Erforderliche Software für Enterprise-VoIP'
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
ms.openlocfilehash: cb85a8da9fe0d009f46ef23b919aeb9fd006fab4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Erforderliche Software für Enterprise-VoIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Überprüfen Sie, ob die Infrastruktur, in der Sie Enterprise-VoIP bereitstellen möchten, die folgenden Softwarevoraussetzungen erfüllt:

  - Lync Server 2013 Standard Edition oder Enterprise Edition ist in Ihrem Netzwerk installiert und betriebsbereit.

  - Alle Edgeserver werden in Ihrem Umkreisnetzwerk bereitgestellt und in Betrieb genommen, einschließlich Edgeserver mit Access Edge-Dienst, a/V-Edgedienst, Webkonferenz-Edgedienst und einem Reverse-Proxy.

  - Entweder Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 oder Microsoft Exchange Server 2013 ist für die Integration von Exchange Unified Messaging mit lync Server erforderlich und bietet umfangreiche Benachrichtigungen und Anrufprotokoll Informationen für die Lync-Endpunkte

  - Mindestens ein Benutzer wurde für lync Server erstellt und aktiviert.

  - Lync-Clients und-Geräte wurden erfolgreich bereitgestellt.

  - Der Topologie-Generator ist auf einem Server in Ihrem Netzwerk installiert.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Nächste Schritte: Überprüfen der Voraussetzungen für Sicherheit und Konfiguration

Nachdem Sie die Softwarevoraussetzungen für Enterprise-VoIP überprüft haben, können Sie die Dokumentation verwenden, um die Bereitstellung von Enterprise-VoIP weiter vorzubereiten:

1.  Überprüfen Sie die Sicherheits-, Benutzer-und Hardware Vergünstigungen, wie unter [Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)beschrieben.

2.  Installieren Sie den Vermittlungsserver, wie unter [Installieren der Dateien für den Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)beschrieben, aber *nur* , wenn Sie einen eigenständigen Vermittlungsserver oder-Pool bereitstellen möchten, da Vermittlungsserver als Teil des Front-End-Pools oder des Standard Edition-Server Bereitstellungsprozesses installiert werden, wenn Sie zusammengestellt sind.

3.  Konfigurieren Sie trunk-Verbindungen, um PSTN-Konnektivität für Benutzer bereitzustellen, wie unter [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)beschrieben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

