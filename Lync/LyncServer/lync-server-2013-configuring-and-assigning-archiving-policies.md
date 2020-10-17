---
title: 'Lync Server 2013: Konfigurieren und Zuweisen von Archivierungsrichtlinien'
description: 'Lync Server 2013: Konfigurieren und Zuweisen von Archivierungsrichtlinien.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebe08715433e04e56758c7fb09b331065fbd6f44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570911"
---
# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

In lync Server 2013 verwenden Sie Richtlinien, um die Archivierung für die interne Kommunikation und die externe Kommunikation für Benutzer zu aktivieren und zu deaktivieren, die in lync Server 2013 verwaltet werden. Dies umfasst die folgenden Archivierungsrichtlinien:

  - Eine globale Richtlinie, die bei der Bereitstellung von lync Server 2013 standardmäßig erstellt wird.

  - Optionale Richtlinien auf Standort- und Benutzerebene, die Sie erstellen und verwenden können, um festzulegen, wie die Archivierung für bestimmte Standorte oder Benutzer umgesetzt wird.

Sie richten die Archivierungsrichtlinien zunächst bei der Bereitstellung der Archivierung ein, können diese aber nach der Bereitstellung ändern, hinzufügen und löschen. In lync Server 2013 Systemsteuerung können Sie auf der Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** Richtlinien auf globaler Ebene, auf Standortebene und auf Benutzerebene verwalten.

<div>


> [!NOTE]  
> Zur Steuerung der Archivierungsimplementierung müssen Sie Optionen in den Archivierungskonfigurationen auswählen, beispielsweise um festzulegen, ob Sofortnachrichten oder Konferenzinhalte archiviert werden, wie der kritische Modus verwendet wird, sowie Löschoptionen. Standardmäßig sind in der globalen Archivierungskonfiguration oder in Standortarchivierungs- oder Poolarchivierungskonfigurationen keine Optionen aktiviert. Sie sollten alle geeigneten Optionen in den Archivierungskonfigurationen festlegen, bevor Sie die Archivierung für die interne oder externe Kommunikation in den Archivierungsrichtlinien aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration options in lync Server 2013 für Ihre Organisation, Standorte und Pools</A> in der Betriebsdokumentation.<BR>Wenn Sie Ihren lync Server Speicher in Exchange 2013 Speicher integrieren, haben die Exchange-Benutzerrichtlinien Vorrang vor den lync Server 2013 Archivierungsrichtlinien, jedoch nur für die Benutzer, die in Exchange 2013 verwaltet werden, deren Postfächer In-Place Aufbewahrungsverfahren abgelegt wurden.



</div>

Ausführliche Informationen zur Implementierung von Richtlinien, einschließlich der Hierarchie der Richtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Ausführliche Informationen zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Managing the Archiving of Internal and External Communications in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in der Betriebsdokumentation.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren der globalen Richtlinie für die Archivierung in lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Einrichten von Standortrichtlinien für die Archivierung in lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Einrichten von Archivierungsrichtlinien für Benutzer in lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

