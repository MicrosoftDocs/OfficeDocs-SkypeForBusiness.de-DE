---
title: 'Lync Server 2013: Konfigurieren und Zuweisen von Archivierungsrichtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8b3b4f1f9465684d7c9139b8cd548caacf91c41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

In lync Server 2013 verwenden Sie Richtlinien, um die Archivierung für die interne Kommunikation und die externe Kommunikation für Benutzer zu aktivieren und zu deaktivieren, die in lync Server 2013 gehostet werden. Dies umfasst die folgenden Archivierungsrichtlinien:

  - Eine globale Richtlinie, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.

  - Optionale Richtlinien auf Websiteebene und auf Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Benutzer implementiert wird.

Sie haben zunächst Archivierungsrichtlinien eingerichtet, wenn Sie die Archivierung bereitstellen, Sie können aber nach der Bereitstellung Richtlinien ändern, hinzufügen und löschen. In der lync Server 2013-Systemsteuerung können Sie die Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** verwenden, um Richtlinien auf globaler Ebene, auf Websiteebene und auf Benutzerebene zu verwalten.

<div>


> [!NOTE]  
> Um die Implementierung der Archivierung zu steuern, müssen Sie Optionen in Archivierungs Konfigurationen angeben, beispielsweise ob Sie Chatnachrichten oder Konferenzen archivieren, die Verwendung des kritischen Modus und Bereinigungsoptionen verwenden möchten. Standardmäßig sind keine Optionen in der globalen Archivierungskonfiguration oder einer Standort-oder Pool Archivierungskonfiguration aktiviert. Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung für die interne oder externe Kommunikation in den Archivierungsrichtlinien aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Websites und Pools</A> in der Betriebsdokumentation.<BR>Wenn Sie Ihren lync-Server Speicher in Exchange 2013-Speicher integrieren, haben die Exchange-Benutzerrichtlinien Vorrang vor den Archivierungsrichtlinien für lync Server 2013, aber nur für die Benutzer, die sich in Exchange 2013 befinden und deren Postfächer in der Warteschleife platziert wurden.



</div>

Einzelheiten zur Implementierung von Richtlinien, einschließlich der Hierarchie der Richtlinien, finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation. Ausführliche Informationen zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in der Betriebsdokumentation.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren der globalen Richtlinie für die Archivierung in lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Einrichten von Website Richtlinien für die Archivierung in lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Einrichten von Archivierungsrichtlinien für Benutzer in lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

