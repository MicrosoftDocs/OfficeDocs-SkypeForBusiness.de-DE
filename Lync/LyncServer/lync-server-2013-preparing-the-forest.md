---
title: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec335e95264c4588b81ea5cae8473e540e9af5a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>Vorbereiten der Gesamtstruktur auf lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Bei der Gesamtstrukturvorbereitung werden Active Directory globale Einstellungen und Objekte und Active Directory universelle Gruppen für die Verwendung durch lync Server 2013 erstellt, und es werden geeignete Zugriffsberechtigungen für die Active Directory-Objekte erteilt. Eine Beschreibung der universellen Gruppen und der globalen Einstellungen und Objekte, die von der Gesamtstrukturvorbereitung erstellt werden, finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommen](lync-server-2013-changes-made-by-forest-preparation.md)wurden.

Bei der Gesamtstrukturvorbereitung werden auch Objekte erstellt, die Eigenschaftensätze und Anzeigebezeichner enthalten, die von lync Server 2013 verwendet werden, und diese im Konfigurationscontainer speichern.

<div>


> [!IMPORTANT]  
> Stellen Sie sicher, dass Änderungen der Schemavorbereitung auf alle Domänencontroller repliziert wurden, bevor Sie das Verfahren zur Gesamtstrukturvorbereitung durchführen. Wenn die Replikation noch nicht abgeschlossen wurde, tritt ein Fehler auf.



</div>

Wenn Sie eine neue lync Server-Bereitstellung durchführen, müssen Sie globale Einstellungen im Konfigurationscontainer speichern. Wenn Sie ein Upgrade von einer früheren Version durchführen und globale Einstellungen weiterhin im Systemcontainer speichern, können Sie weiterhin den Systemcontainer verwenden.

Zum Durchführen dieses Verfahrens müssen Sie ein Mitglied der Gruppe "Organisations-Admins" oder "Domänen-Admins" für die Stammdomäne der Gesamtstruktur sein.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Laufende Gesamtstrukturvorbereitung für lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

