---
title: 'Lync Server 2013: Audio/Video-Edgeserver (a/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fce9f00d84465928d942220b1ca2275e59a3817
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Audio/Video-Edgeserver (A/V) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Zusätzlich zu Audio und Video bietet der A/V-Edgedienst beispielsweise Unterstützung für die Desktopfreigabe und die Dateiübertragung.

Der A/V-Edgeserverdienst wird primär durch die Verwendung der A/V-Edge-Konfiguration verwaltet. Mit diesen Einstellungen können Sie die maximale zuzuweisende Bandbreite pro Port und Benutzer verwalten und den Zeitraum definieren, in dem das Authentifizierungstoken verwendet werden kann, bevor es erneuert werden muss. A/V-Edge-Konfigurationseinstellungen können auf Standorte oder einzelne A/V-Edgeserver angewendet werden. Verwenden Sie beim Bestimmen der zu bevorzugenden Einstellungsauflistung die folgende Anleitung:

  - Auf Dienstebene konfigurierte Einstellungen (d. h. auf einem einzelnen Server) haben die höchste Priorität.

  - Auf Standortebene zugewiesene Einstellungen haben Vorrang vor den global zugewiesenen Einstellungen. Auf Dienstebene vorgenommene Einstellungen ersetzen jedoch ebenfalls auf Standortebene vorgenommene Einstellungen.

  - Einstellungen auf globaler Ebene werden nur verwendet, wenn auf dem einzelnen Server keine auf Dienstebene vorgenommenen Einstellungen konfiguriert wurden und wenn keine auf Standortebene vorgenommenen Einstellungen für den Standort, wo sich der Server befindet, vorliegen.

Die A/V-Edgedienst kann nur mit lync Server PowerShell und den CsAVEdgeConfiguration-Cmdlets verwaltet werden.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zurückgeben von A/V-Edgeserver Konfigurationsinformationen in lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Erstellen oder Ändern einer Sammlung von a/V-Edgeserver Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

