---
title: 'Lync Server 2013: Anforderungen und Benutzerrechte für die Konfiguration zum Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a2f322ffec1d2ffa7aa238b76686391fc76ed7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Anforderungen und Benutzerrechte für die Konfiguration zum Parken von Anrufen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-10_

Anruf Parken ist eine anrufverwaltungsfunktion, die standardmäßig bei der Bereitstellung von Enterprise-VoIP installiert wird. In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie den Anruf Park und die Benutzerrechte konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.

<div>


> [!IMPORTANT]  
> Angepasste Musik-in-situ-Dateien für die Anwendung "Parken" werden nicht im Rahmen des lync Server 2013-Wiederherstellungsprozesses gesichert, und die Dateien gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht wurden. Bewahren Sie stets eine separate Sicherungskopie der für geparkte Anrufe hochgeladenen angepassten Musikdateien auf.



</div>

In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zum Parken von Anrufen gelesen haben (siehe [Planen von Anruf Verwaltungsfeatures in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Voraussetzungen für die Konfiguration des Anruf Parks

Für den Parken von Anrufen sind die folgenden Komponenten erforderlich:

  - Anwendungsdienst

  - Anwendung zum Parken von Anrufen

Diese Komponenten werden automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.

Wenn Sie möchten, dass Anrufer Musik hören, während der Anruf abgestellt wird, ist auch eine Musik-auf-halten-Datei erforderlich. Wenn Sie Enterprise-VoIP bereitstellen, wird automatisch eine standardmäßige Music-on-halten-Datei installiert. Sie können die Standarddatei durch ihre eigene Musik-in-halten-Datei ersetzen. Call Park verwendet den Dateispeicher, um die Audiodatei zu speichern.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Konfigurations Benutzerrechte des Anruf Parks

Sie können die folgenden Verwaltungstools zum Konfigurieren des Anruf Parks verwenden:

  - Lync Server-Systemsteuerung

  - Lync Server-Verwaltungsshell

Sie verwenden diese Tools, um die Umlaufbahn Tabelle des Anruf Parks einzurichten und andere Einstellungen zu konfigurieren, die von Call Park verwendet werden.

Die Konfiguration des Anruf Parks erfordert je nach Aufgabe eine der folgenden Administratorrollen:

  - **CsVoiceAdministrator:** Diese Administratorrolle kann alle sprachbezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.

  - **CsUserAdministrator:** Mit dieser Administratorrolle kann der Anruf Park in der VoIP-Richtlinie aktiviert werden. Diese Administratorrolle verfügt auch über die schreibgeschützte Ansicht Zugriff auf alle Sprachkonfigurationen.

  - **CsServerAdministrator:** Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen.

  - **CsAdministrator:** Diese Administratorrolle kann alle Aufgaben von CsVoiceAdministrator, CsServerAdministrator und CsUserAdministrator ausführen.

<div>


> [!NOTE]  
> Details zu Administratorrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation.



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

