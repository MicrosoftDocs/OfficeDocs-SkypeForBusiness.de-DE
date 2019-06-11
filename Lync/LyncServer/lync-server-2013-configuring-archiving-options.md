---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98356b53940c6189abac5a4b554769093f84dd2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Konfigurieren von Archivierungsoptionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

In der lync Server 2013-Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um anzugeben, wie die Archivierung durchgeführt wird. Dies umfasst die folgenden Archivierungs Konfigurationen:

  - Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.

  - Optionale Konfigurationen auf Websiteebene und auf Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Pools implementiert werden soll.

Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen. In der lync Server 2013-Systemsteuerung können Sie auf **** der Seite Archivierungs-und Überwachungsgruppe auf der Seite Archivierungs **-und Überwachungs** Einstellungen Konfigurationen auf globaler Ebene, Websiteebene und Poolebene verwalten. Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [wie funktioniert die Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellung Dokumentation oder Betriebsdokumentation. Details zum Verwalten von Konfigurationen nach der Bereitstellung finden Sie unter [Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Websites und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Um die Archivierung verwenden zu können, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll. Standardmäßig ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert. Bevor Sie die Archivierung in einer beliebigen Richtlinie aktivieren, sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben. Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie die Microsoft Exchange-Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für beide aktiviert werden soll. Standardmäßig ist die Archivierung für die Archivierung von Daten bei der Verwendung von lync Server 2013-Archivierungsdatenbanken nicht für die interne oder externe Kommunikation aktiviert. Bevor Sie die Archivierung in einer beliebigen Richtlinie aktivieren, sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben. Details zum Aktivieren der Archivierung zur Verwendung mit lync Server 2013-Archivierungsdatenbanken finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von Archivierungsoptionen auf globaler Ebene in lync Server 2013](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Konfigurieren von Archivierungsoptionen für eine Website in lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Konfigurieren von Archivierungsoptionen für einen Pool in lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

