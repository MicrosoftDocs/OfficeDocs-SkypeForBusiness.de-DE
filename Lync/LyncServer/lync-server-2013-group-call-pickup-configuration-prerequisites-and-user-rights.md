---
title: Konfigurationsvoraussetzungen und Benutzerrechte für Gruppenanruf Pickups
description: Konfigurationsvoraussetzungen für die gruppenanrufannahme und Benutzerrechte.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554451"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Konfigurieren von Voraussetzungen und Benutzerrechten für Gruppenanruf Pickups in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Bei der gruppenanrufannahme handelt es sich um eine anrufverwaltungsfunktion, die bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert wird. In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie die gruppenanrufannahme und die Benutzerrechte konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.

In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zur gruppenanrufannahme gelesen haben (Weitere Informationen finden Sie unter [Planning for Group Call Pickup in lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Konfigurationsvoraussetzungen für Gruppenanruf Pickups

Für die Gruppenanruf Abholung sind die folgenden Komponenten erforderlich:

  - Anwendungsdienst

  - Anwendung zum Parken von Anrufen

Diese Komponenten werden automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Gruppenanruf-Pickup-Konfiguration Benutzerrechte

Verwenden Sie die folgenden Verwaltungstools zum Konfigurieren der gruppenanrufannahme:

  - Lync Server-Verwaltungsshell

  - SEFAUtil Resource Kit-Tool

Verwenden Sie lync Server-Verwaltungsshell zum Erstellen und Verwalten von Anrufgruppen in der Orbit-Tabelle für das Parken von anrufen. Verwenden Sie das SEFAUtil Resource Kit-Tool, um eine Anrufannahme Gruppe zuzuweisen und die gruppenanrufannahme für Benutzer zu aktivieren oder um die gruppenanrufannahme für Benutzer zu deaktivieren.

Für die Konfiguration der gruppenanrufannahme sind je nach Aufgabe die folgenden Administratorrollen erforderlich:

  - **CsVoiceAdministrator:** Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.

  - **CsUserAdministrator:** Diese Administratorrolle kann die gruppenanrufannahme für Benutzer aktivieren. Diese Administratorrolle hat außerdem schreibgeschützten Zugriff auf alle VoIP-Konfigurationen.

  - **CsServerAdministrator:** Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen.

  - **CsAdministrator:** Diese Administratorrolle kann alle Aufgaben von CsVoiceAdministrator, CsServerAdministrator und CsUserAdministrator ausführen.

<div>


> [!NOTE]
> Ausführliche Informationen zu Administratorrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</A> in der Planungsdokumentation.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planen von Funktionen für die Anrufverwaltung in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

