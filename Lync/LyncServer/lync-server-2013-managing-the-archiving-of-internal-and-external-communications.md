---
title: Verwalten der Archivierung interner und externer Kommunikation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a9e3c0a0708075eecc28282021f98724325ff6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

In lync Server 2013 verwenden Sie Archivierungsrichtlinien, um die Archivierung für die interne Kommunikation und die externe Kommunikation zu aktivieren und zu deaktivieren, wenn Sie die Microsoft Exchange-Integration nicht verwenden oder wenn Sie über Benutzer verfügen, die nicht in Exchange 2013 mit ihren Postfächern gespeichert sind In-situ-Speicher. Dies umfasst die folgenden Archivierungsrichtlinien:

  - Eine globale Richtlinie, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.

  - Optionale Richtlinien auf Websiteebene und auf Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Benutzer implementiert wird.

Sie haben zunächst Archivierungsrichtlinien eingerichtet, wenn Sie die Archivierung bereitstellen, Sie können aber nach der Bereitstellung Richtlinien ändern, hinzufügen und löschen. In der lync Server 2013-Systemsteuerung können Sie die Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** verwenden, um Richtlinien auf globaler Ebene, auf Websiteebene und auf Benutzerebene zu verwalten. Wenn Sie Ihren lync-Server Speicher in Exchange 2013-Speicher integrieren, haben die Exchange-Benutzerrichtlinien Vorrang vor den Archivierungsrichtlinien für lync Server 2013.

Einzelheiten zur Implementierung von Richtlinien, einschließlich der Hierarchie der Richtlinien, finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]
> Um die Implementierung der Archivierung zu steuern, müssen Sie Optionen in Archivierungs Konfigurationen angeben, beispielsweise ob Sie Chatnachrichten oder Konferenzen archivieren, die Verwendung des kritischen Modus und Bereinigungsoptionen verwenden möchten. Standardmäßig sind keine Optionen in der globalen Archivierungskonfiguration oder einer Standort-oder Pool Archivierungskonfiguration aktiviert. Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung für die interne oder externe Kommunikation in den Archivierungsrichtlinien aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Websites und Pools</A> in der Betriebsdokumentation.<BR>Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange 2013 befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen einer Archivierungsrichtlinie in lync Server 2013 zum Aktivieren oder Deaktivieren der Archivierung interner oder externer Kommunikation für bestimmte Websites oder Benutzer](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [Ändern einer Archivierungsrichtlinie in lync Server 2013, um die Archivierung interner oder externer Kommunikation für Ihre Organisation, ihre Websites oder Ihre Benutzer zu aktivieren oder zu deaktivieren](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [Anwenden einer Archivierungsrichtlinie auf Benutzer in lync Server 2013](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Löschen einer Archivierungsrichtlinie in lync Server 2013](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

