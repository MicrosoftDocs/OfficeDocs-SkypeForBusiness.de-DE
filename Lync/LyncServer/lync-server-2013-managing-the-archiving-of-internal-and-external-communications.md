---
title: Verwalten der Archivierung von interner und externer Kommunikation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14df9a4472d920e5b583e4d2abe2deeb3fba0c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525032"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Verwalten der Archivierung von interner und externer Kommunikation in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

In lync Server 2013 verwenden Sie Archivierungsrichtlinien, um die Archivierung für die interne Kommunikation und die externe Kommunikation zu aktivieren und zu deaktivieren, wenn Sie Microsoft Exchange Integration nicht verwenden oder wenn Sie über Benutzer verfügen, die nicht in Exchange 2013 mit ihren Postfächern in In-Place Aufbewahrung abgelegt werden. Dies umfasst die folgenden Archivierungsrichtlinien:

  - Eine globale Richtlinie, die bei der Bereitstellung von lync Server 2013 standardmäßig erstellt wird.

  - Optionale Richtlinien auf Standort- und Benutzerebene, die Sie erstellen und verwenden können, um festzulegen, wie die Archivierung für bestimmte Standorte oder Benutzer umgesetzt wird.

Sie richten die Archivierungsrichtlinien zunächst bei der Bereitstellung der Archivierung ein, können diese aber nach der Bereitstellung ändern, hinzufügen und löschen. In lync Server 2013 Systemsteuerung können Sie auf der Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** Richtlinien auf globaler Ebene, auf Standortebene und auf Benutzerebene verwalten. Wenn Sie Ihren lync Server Speicher in Exchange 2013 Speicher integrieren, haben die Exchange-Benutzerrichtlinien Vorrang vor den lync Server 2013 Archivierungsrichtlinien.

Ausführliche Informationen zur Implementierung von Richtlinien, einschließlich der Hierarchie der Richtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]
> Zur Steuerung der Archivierungsimplementierung müssen Sie Optionen in den Archivierungskonfigurationen auswählen, beispielsweise um festzulegen, ob Sofortnachrichten oder Konferenzinhalte archiviert werden, wie der kritische Modus verwendet wird, sowie Löschoptionen. Standardmäßig sind in der globalen Archivierungskonfiguration oder in Standortarchivierungs- oder Poolarchivierungskonfigurationen keine Optionen aktiviert. Sie sollten alle geeigneten Optionen in den Archivierungskonfigurationen festlegen, bevor Sie die Archivierung für die interne oder externe Kommunikation in den Archivierungsrichtlinien aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration options in lync Server 2013 für Ihre Organisation, Standorte und Pools</A> in der Betriebsdokumentation.<BR>Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und lassen ihre Postfächer In-Place halten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen einer Archivierungsrichtlinie in lync Server 2013 zum Aktivieren oder Deaktivieren der Archivierung interner oder externer Kommunikation für bestimmte Websites oder Benutzer](lync-server-2013-create-archiving-policy-sites-users.md)

  - [Ändern einer Archivierungsrichtlinie in lync Server 2013 zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für Ihre Organisation, Websites oder Benutzer](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [Anwenden einer Archivierungsrichtlinie auf Benutzer in lync Server 2013](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server Integration](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Löschen einer Archivierungsrichtlinie in lync Server 2013](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

