---
title: 'Lync Server 2013: Konfigurationsvoraussetzungen und -rollen für Ansagen'
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
ms.openlocfilehash: 42cbc1429d4e27ee172dc1dacf6b86fa6ac243d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Konfigurationsvoraussetzungen und -rollen für Ansagen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Ankündigung ist eine Enterprise-VoIP-anrufverwaltungsfunktion. In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie die Ankündigung und die Rollenzuweisungen konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.

In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zu Ankündigungen gelesen haben (siehe [Planen von Anruf Verwaltungsfeatures in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Voraussetzungen für die Ankündigungs Konfiguration

Für die Ankündigungs Anwendung sind die folgenden Komponenten erforderlich:

  - Anwendungsdienst

  - Reaktionsgruppenanwendung

  - Dateispeicher zum Speichern von Audiodateien

Alle diese Komponenten werden standardmäßig installiert, wenn Sie Enterprise-VoIP bereitstellen.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Ankündigungs Konfigurations Rollen

Sie können die folgenden Verwaltungstools verwenden, um Ankündigungen zu konfigurieren:

  - Lync Server-Systemsteuerung

  - Lync Server-Verwaltungsshell

Zum Konfigurieren der Ankündigungs Anwendung ist eine der folgenden Administratorrollen erforderlich:

  - **CsVoiceAdministrator**   diese Administratorrolle kann alle sprachbezogenen Einstellungen und Richtlinien, einschließlich Ankündigungseinstellungen, erstellen, konfigurieren und verwalten.

  - **CsServerAdministrator**   diese Administratorrolle kann Server und Dienste verwalten, überwachen und behandeln sowie alle Ankündigungseinstellungen konfigurieren.

  - **CsAdministrator**   diese Administratorrolle kann alle administrativen Aufgaben ausführen und alle Einstellungen ändern.

  - **CsViewOnlyAdministrator**   diese Administratorrolle kann die Bereitstellung anzeigen, um den Bereitstellungsstatus zu überwachen.

<div>


> [!NOTE]  
> Ausführliche Informationen zu administrativen Benutzerrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planen der Anruf Verwaltungsfeatures in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

