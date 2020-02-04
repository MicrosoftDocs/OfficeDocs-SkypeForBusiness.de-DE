---
title: Konfigurationsvoraussetzungen und -berechtigungen für Einwahlkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6610272c39583b70c1ab20d8271551796f65372
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Konfigurationsvoraussetzungen und -berechtigungen für Einwahlkonferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-20_

Einwahlkonferenzen ist eine optionale Komponente der lync Server 2013-Konferenz Arbeitsauslastung. Die Komponenten, die Sie installieren müssen, bevor Sie Einwahlkonferenzen konfigurieren können, werden bereitgestellt, wenn Sie die Topologie mithilfe des Topologie-Generators entwerfen und dann Ihren Front-End-Pool oder Standard Edition-Server einrichten. In diesem Thema wird beschrieben, welche Voraussetzungen erfüllt sein müssen, bevor Sie Einwahlkonferenzen konfigurieren können.

In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsabschnitte im Zusammenhang mit der Konferenz Arbeitsauslastung und insbesondere Einwahlkonferenzen gelesen haben.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Voraussetzungen für die Konfiguration von Einwahlkonferenzen

Für Einwahlkonferenzen sind die folgenden lync Server 2013-Komponenten erforderlich:

  - Unified Communications-Anwendungsdienst (auch nur *Anwendungsdienst* genannt)

  - Konferenzzentrale

  - Konferenzankündigungsanwendung

  - Webseite mit Einstellungen für Einwahlkonferenzen

  - Mindestens ein lync Server 2013-Vermittlungsserver und mindestens ein PSTN-Gateway

Diese Komponenten werden bereitgestellt, wenn Sie den Topologie-Generator verwenden, um Ihre Topologie zu definieren und zu veröffentlichen und dann einen Front-End-Pool oder einen Standard Edition-Server bereitzustellen. Wenn Sie Enterprise-VoIP bereitstellen, sollten Sie es bereitstellen, bevor Sie Einwahlkonferenzen konfigurieren. Wenn Sie Enterprise-VoIP nicht bereitstellen, können Sie einen Vermittlungs Server und ein PSTN-Gateway (Public Switched Telephone Network) bereitstellen, wenn Sie den Front-End-Pool oder den Standard Edition-Server bereitstellen.

<div>


> [!NOTE]
> Wenn Sie ein Upgrade von Office Communications Server 2007 R2 auf lync Server 2013 durchführen, stellen Sie Einwahlkonferenzen in jedem Pool bereit, den Sie zum Hosten von lync Server 2013-Konferenzen verwenden möchten. Details zum Migrieren von Einwahlkonferenzen finden Sie unter <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration von Office Communications Server 2007 R2 zu lync Server 2013</A>.



</div>

In diesem Abschnitt wird davon ausgegangen, dass Sie die folgenden Schritte ausgeführt haben:

  - Sie haben die neuesten Updates für Ihre Office Communications Server 2007 R2-Umgebung angewendet, wenn Sie zu lync Server 2013 migrieren.

  - Mithilfe des Topologie-Generators können Sie Ihre Topologie entwerfen und konfigurieren. Wenn Sie die Konferenz Arbeitsauslastung angeben, haben Sie die Option Einwahlkonferenzen ausgewählt. Details zum Definieren Ihrer Topologie finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in der Bereitstellungsdokumentation.

  - Haben Sie Ihre Topologie veröffentlicht, und richten Sie den Front-End-Pool oder den Standard Edition-Server ein. Details zum Veröffentlichen der Topologie und zur Installation von lync Server 2013 finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.
    
    <div>
    

    > [!NOTE]
    > Wenn Sie Ihre veröffentlichte Topologie installieren, wird die Seite Einwahlkonferenzeinstellungen auf dem Front-End-Server oder Standard Edition-Server als Teil von Webdiensten installiert.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Wenn Sie den Pfad für den Dateispeicher in Topology Builder nach der Bereitstellung von lync Server 2013 ändern, müssen Sie die Anwendungen für Konferenzzentrale und Konferenz Ankündigungen neu starten, um den neuen Pfad zu verwenden.

    
    </div>

  - Enterprise-VoIP bereitgestellt. Wenn Sie Enterprise-VoIP nicht bereitstellen, haben Sie entweder einen Vermittlungsserver auf dem Enterprise Edition-Front-End-Server oder auf dem Standard Edition-Server zusammengestellt, oder Sie haben einen eigenständigen Vermittlungsserver bereitgestellt, und Sie haben ein PSTN-Gateway bereitgestellt. Details zur Bereitstellung von Enterprise-VoIP finden Sie unter [Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation. Details zum Installieren eines eigenständigen Vermittlungsservers und eines PSTN-Gateways finden Sie unter [Bereitstellen von Vermittlungsservern und Definieren von Peers in lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in der Bereitstellungsdokumentation.

Das folgende Flussdiagramm zeigt die Schritte, die Sie ausführen müssen, bevor Sie Einwahlkonferenzen und die Schritte konfigurieren können, die Sie zum Konfigurieren von Einwahlkonferenzen durchführen.

**Bereitstellen von Einwahlkonferenzen**

![Bereitstellungs Flussdiagramm für Einwahlkonferenzen](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Bereitstellungs Flussdiagramm für Einwahlkonferenzen")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Berechtigungen für Einwahlkonferenzen

Zum Konfigurieren von Einwahlkonferenzen müssen Sie die folgenden Verwaltungstools verwenden:

  - Systemsteuerung für Lync Server 2013

  - Lync Server-Verwaltungsshell

Sie verwenden diese Verwaltungstools, um Einstellungen für Einwahlkonferenzen und die Wählpläne, Richtlinien und andere Einstellungen zu konfigurieren, die für Einwahlkonferenzen erforderlich sind.

Für die Konfiguration von Einwahlkonferenzen sind je nach Aufgabe eine der folgenden Administratorrollen erforderlich:

  - **CsVoiceAdministrator**   diese Administratorrolle kann sprachbezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.

  - **CsUserAdministrator**   diese Administratorrolle kann Benutzer für lync Server aktivieren und deaktivieren und Benutzern vorhandene Richtlinien wie Konferenzrichtlinien und PIN-Richtlinien zuweisen.

  - **CsAdministrator**   diese Administratorrolle kann alle Aufgaben von CsVoiceAdministrator und CsUserAdministrator ausführen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

