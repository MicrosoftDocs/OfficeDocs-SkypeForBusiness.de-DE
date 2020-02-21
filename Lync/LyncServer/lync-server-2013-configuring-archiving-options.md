---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd70d2742e54da801f80b07f1a00b97e0d91a990
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Konfigurieren von Archivierungsoptionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-10_

In lync Server 2013 Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um anzugeben, wie die Archivierung implementiert wird. Dies schließt die folgenden Archivierungskonfigurationen ein:

  - Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie lync Server 2013 bereitstellen.

  - Optionale Konfigurationen auf Standort- und Poolebene, die Sie zum Angeben der Implementierungsart für spezielle Standorte oder Pools erstellen und verwenden können.

Sie legen Archivierungskonfigurationen anfangs fest, wenn Sie Archivierungen bereitstellen, Sie können jedoch nach der Bereitstellung Konfigurationen ändern, hinzufügen und löschen. In lync Server 2013 Systemsteuerung können Sie die Seite **Archivierungskonfiguration** der Gruppe **Archivierung und Überwachung** verwenden, um Konfigurationen auf globaler Ebene, auf Standortebene und auf Poolebene zu verwalten. Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Ausführliche Informationen zum Verwalten von Konfigurationen nach der Bereitstellung finden Sie unter [Managing Archiving Configuration options in lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Für die Verwendung der Archivierung müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für die interne Kommunikation, für externe Kommunikationen oder für Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll. Standardmäßig ist die Archivierung weder für die interne noch für die externe Kommunikation aktiviert. Bevor Sie die Archivierung in Richtlinien aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional für spezielle Standorte und Pools angeben, wie in diesem Abschnitt beschrieben. Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie Microsoft Exchange Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für beides aktiviert werden soll. Standardmäßig ist die Archivierung für die interne oder externe Kommunikation für die Archivierung von Daten nicht aktiviert, wenn lync Server 2013 Archivierungsdatenbanken verwendet werden. Vor dem Aktivieren der Archivierung in sämtlichen Richtlinien sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellungen und optional für bestimmte Standorte und Pools angeben, wie dies in diesem Abschnitt beschrieben ist. Ausführliche Informationen zum Aktivieren der Archivierung für die Verwendung mit lync Server 2013-Archivierungsdatenbanken finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.



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

