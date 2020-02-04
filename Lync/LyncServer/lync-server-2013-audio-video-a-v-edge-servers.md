---
title: 'Lync Server 2013: Audio/Video (A/V)-Edgeserver'
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
ms.openlocfilehash: c99cc3522c13ece937c6e2a0ba06f995431e08d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Audio/Video-Edgeserver (A/V) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Der a/V-Edgedienst bietet internen Benutzern (Benutzern, die bei Ihrem Unternehmensnetzwerk angemeldet sind) die Möglichkeit, Audio und Video für externe Benutzer freizugeben (Benutzer, die nicht bei Ihrem Organisationsnetzwerk angemeldet sind). Neben Audio und Video bietet der A/V-Edgedienst auch Unterstützung für die Desktopfreigabe und Dateiübertragung.

Der a/v-Edgedienst wird hauptsächlich mithilfe der a/v-Edge-Konfiguration verwaltet. Mithilfe dieser Einstellungen können Sie die maximale Bandbreite verwalten, die pro Port und pro Benutzer zugewiesen werden soll, und angeben, wie lange ein Authentifizierungstoken verwendet werden kann, bevor dieses Token erneuert werden muss. A/v-Edge-Konfigurationseinstellungen können auf Websites oder auf einzelne a/v-Edgeserver angewendet werden. Verwenden Sie die folgende Anleitung, um zu ermitteln, welche Sammlung von Einstellungen Vorrang hat:

  - Im Dienstbereich konfigurierte Einstellungen (also auf einem einzelnen Server) haben Vorrang vor allem.

  - Die für den Website Bereich konfigurierten Einstellungen haben Vorrang vor den im globalen Bereich konfigurierten Einstellungen. Dienstbereichs Einstellungen ersetzen jedoch auch die Einstellungen für den Website Bereich.

  - Einstellungen im globalen Bereich werden nur verwendet, wenn auf dem einzelnen Server keine Diensteinstellungen konfiguriert sind und keine Websiteeinstellungen für die Website vorhanden sind, auf der sich der Server befindet.

Der A/V-Edgedienst kann nur mithilfe der lync Server PowerShell und der CsAVEdgeConfiguration-Cmdlets verwaltet werden.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zurückgeben von A/V-Edgeserver-Konfigurationsinformationen in lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Erstellen oder Ändern einer Sammlung von a/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Löschen einer vorhandenen Sammlung von A/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

