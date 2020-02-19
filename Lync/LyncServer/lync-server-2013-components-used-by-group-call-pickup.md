---
title: 'Lync Server 2013: von der gruppenanrufannahme verwendete Komponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05f41b7420f15c2815ababa0f85d8aca43898dd2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Von der gruppenanrufannahme in lync Server 2013 verwendete Komponenten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Die gruppenanrufannahme wird automatisch bereitgestellt, wenn Sie Enterprise-VoIP und die Anwendung zum Parken von Anrufen bereitstellen. Sie aktivieren die gruppenanrufannahme durch Konfigurieren der Orbit-Tabelle für das Parken von Anrufen mit getrennten Nummernbereichen, die als Nummern für die Anrufannahme Gruppe festgelegt sind, und dann durch Zuweisen von Benutzern zu Anrufannahme Gruppen und Aktivieren der Benutzer für die gruppenanrufannahme. Die folgenden lync Server Komponenten unterstützen die gruppenanrufannahme:

  - **Anwendungsdienst**   Anwendungsdienst bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen wie der Anwendung zum Parken von anrufen. Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server installiert.

  - **Anwendung zum Parken von Anrufen**   das Anwendung zum Parken von anrufen ist eine der Unified Communications-Anwendungen, die von Anwendungsdienst gehostet werden. Die gruppenanrufannahme basiert auf dem Anwendung zum Parken von anrufen.

  - **Lync Server-Verwaltungsshell**   Sie lync Server-Verwaltungsshell zum Verwalten von Gruppenanruf-pickupgruppen verwenden.

  - **SEFAUtil Resource Kit-Tool**   Sie verwenden das sekundäre Erweiterungsfeature Activation Utility (SEFAUtil), um Benutzer einer Anrufannahme Gruppe zuzuweisen und die Anrufannahme für Benutzer zu aktivieren oder zu deaktivieren.

</div>

<span> </span>

</div>

</div>

</div>

