---
title: 'Lync Server 2013: Voraussetzungen und Rollen für die Ankündigungs Konfiguration'
description: 'Lync Server 2013: Voraussetzungen und Rollen für die Ankündigungs Konfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e6e7009adc6826c255e28ddda925b0e9be5fd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561891"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Voraussetzungen und Rollen für die Ankündigungs Konfiguration in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-25_

Announcement ist eine Enterprise-VoIP-anrufverwaltungsfunktion. In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie die Ankündigung und die Rollenzuweisungen konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.

In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zur Ankündigung gelesen haben (siehe [Planung der anrufverwaltungsfunktionen in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Konfigurationsvoraussetzungen für Ansagen

Die Ankündigungsanwendung erfordert die folgenden Komponenten:

  - Anwendungsdienst

  - Reaktionsgruppenanwendung

  - Dateispeicher für Audiodateien

All diese Komponenten werden bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Rollen für die Konfiguration von Ansagen

Sie können Ansagen mithilfe der folgenden Verwaltungstools konfigurieren:

  - Lync Server-Systemsteuerung

  - Lync Server-Verwaltungsshell

Für das Konfigurieren von Ankündigungsanwendung ist eine der folgenden Administratorrollen erforderlich:

  - **CsVoiceAdministrator**     Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien einschließlich Ankündigungseinstellungen erstellen, konfigurieren und verwalten.

  - **CsServerAdministrator**     Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen und alle Ankündigungseinstellungen konfigurieren.

  - **CsAdministrator**     Diese Administratorrolle kann alle administrativen Aufgaben ausführen und alle Einstellungen ändern.

  - **CsViewOnlyAdministrator**     Diese Administratorrolle kann die Bereitstellung anzeigen, um den Bereitstellungsstatus zu überwachen.

<div>


> [!NOTE]  
> Ausführliche Informationen zu Administrator Benutzerrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</A> in der Planungsdokumentation.



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

