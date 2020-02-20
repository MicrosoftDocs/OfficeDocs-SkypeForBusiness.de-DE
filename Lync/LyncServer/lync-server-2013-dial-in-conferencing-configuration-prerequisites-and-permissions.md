---
title: Voraussetzungen und Berechtigungen für die Konfiguration von Einwahlkonferenzen
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
ms.openlocfilehash: 40bceea093ff5ffc99f941b27cfc13f2b4eff589
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Voraussetzungen und Berechtigungen für die Einwahlkonferenz Konfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-20_

Einwahlkonferenzen sind eine optionale Komponente der Arbeitsauslastung von lync Server 2013 Konferenzen. Die Komponenten, die Sie installieren müssen, bevor Sie Einwahlkonferenzen konfigurieren können, werden bereitgestellt, wenn Sie den Topologie-Generator verwenden, um Ihre Topologie zu entwerfen und dann Ihre Front-End-Pool oder Standard Edition-Server einzurichten. In diesem Thema wird beschrieben, welche Aufgaben vor der Konfiguration von Einwahlkonferenzen ausgeführt werden müssen.

Es wird davon ausgegangen, dass Sie die Planungsdokumentation im Zusammenhang mit Konferenzen und insbesondere mit Einwahlkonferenzen gelesen haben.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Voraussetzungen für die Konfiguration von Einwahlkonferenzen

Für Einwahlkonferenzen sind die folgenden lync Server 2013 Komponenten erforderlich:

  - Unified Communications-Anwendungsdienst (auch nur *Anwendungsdienst* genannt)

  - Konferenzzentrale

  - Konferenzankündigungsanwendung

  - Webseite mit Einstellungen für Einwahlkonferenzen

  - Mindestens ein lync Server 2013 Vermittlungsserver und mindestens ein PSTN-Gateway

Sie stellen diese Komponenten bereit, wenn Sie den Topologie-Generator verwenden, um die Topologie zu definieren und zu veröffentlichen und anschließend eine Front-End-Pool oder ein Standard Edition-Server bereitzustellen. Wenn Sie Enterprise-VoIP bereitstellen, sollten Sie es vor dem Konfigurieren von Einwahlkonferenzen bereitstellen. Wenn Sie Enterprise-VoIP nicht bereitstellen, können Sie eine Vermittlungsserver und ein PSTN-Gateway (Public Switched Telephone Network) bereitstellen, wenn Sie Ihre Front-End-Pool oder Standard Edition-Server bereitstellen.

<div>


> [!NOTE]
> Wenn Sie ein Upgrade von Office Communications Server 2007 R2 auf lync Server 2013 durchführen, stellen Sie Einwahlkonferenzen in jedem Pool bereit, den Sie zum Hosten von lync Server 2013 Konferenzen verwenden möchten. Ausführliche Informationen zum Migrieren von Einwahlkonferenzen finden Sie unter <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to lync Server 2013</A>.



</div>

Dieser Abschnitt setzt voraus, dass Sie die folgenden Schritte ausgeführt haben:

  - Die neuesten Updates wurden auf Ihre Office Communications Server 2007 R2 Umgebung angewendet, wenn Sie zu lync Server 2013 migrieren.

  - Verwenden Sie den Topologie-Generator, um Ihre Topologie zu entwerfen und zu konfigurieren. Bei der Angabe der Arbeitsauslastung für Konferenzen haben Sie die Option Einwahlkonferenzen ausgewählt. Ausführliche Informationen zum Definieren Ihrer Topologie finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in der Bereitstellungsdokumentation.

  - Die Topologie veröffentlicht sowie den Front-End-Pool oder Standard Edition-Server eingerichtet haben. Ausführliche Informationen zum Veröffentlichen der Topologie und zum Installieren von lync Server 2013 finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.
    
    <div>
    

    > [!NOTE]
    > Bei der Installation Ihrer veröffentlichten Topologie wird die Webseite mit Einstellungen für Einwahlkonferenzen als Teil der Webdienste auf dem Front-End-Server oder Standard Edition-Server installiert.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Wenn Sie den Pfad für den Dateispeicher im Topologie-Generator ändern, nachdem Sie lync Server 2013 bereitgestellt haben, müssen Sie die Konferenzzentrale und die Konferenz Ankündigungs Anwendungen neu starten, um den neuen Pfad zu verwenden.

    
    </div>

  - Bereitstellung von Enterprise-VoIP Wenn Sie Enterprise-VoIP nicht bereitstellen, haben Sie entweder eine Vermittlungsserver im Enterprise Edition-Front-End-Server oder im Standard Edition-Server oder ein eigenständiges Vermittlungsserver bereitgestellt und ein PSTN-Gateway bereitgestellt. Ausführliche Informationen zur Bereitstellung von Enterprise-VoIP finden Sie unter [Deploying Enterprise Voice in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation. Ausführliche Informationen zum Installieren eines eigenständigen Vermittlungsserver und eines PSTN-Gateways finden Sie unter [Deploying Mediation Servers and Definition Peers in lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in der Bereitstellungsdokumentation.

Das folgende Flussdiagramm zeigt die Schritte, die erfolgen müssen, bevor Sie Einwahlkonferenzen konfigurieren können, und die Schritte, die Sie zum Konfigurieren von Einwahlkonferenzen ausführen müssen.

**Bereitstellen von Einwahlkonferenzen**

![Flussdiagramm zur Bereitstellung von Einwahlkonferenzen](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Flussdiagramm zur Bereitstellung von Einwahlkonferenzen")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Berechtigungen für Einwahlkonferenzen

Zum Konfigurieren von Einwahlkonferenzen müssen Sie die folgenden Verwaltungsprogramme verwenden:

  - Lync Server 2013-Systemsteuerung

  - Lync Server-Verwaltungsshell

Mithilfe dieser Verwaltungsprogramme konfigurieren Sie die Einwahlkonferenzeinstellungen, Wähleinstellungen, Richtlinien und anderen Einstellungen, die für Einwahlkonferenzen erforderlich sind.

Für das Konfigurieren von Einwahlkonferenzen ist, je nach Aufgabe, eine der folgenden Administratorrollen erforderlich:

  - **CsVoiceAdministrator**   diese Administratorrolle kann VoIP-bezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.

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

