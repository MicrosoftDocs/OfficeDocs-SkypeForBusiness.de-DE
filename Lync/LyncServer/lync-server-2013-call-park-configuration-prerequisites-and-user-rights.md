---
title: 'Lync Server 2013: Voraussetzungen und Benutzerrechte für die Konfiguration des Anruf Parks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e39fd811a39a1221ec522c7ca3874d0de4f340b4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Voraussetzungen und Benutzerrechte für die Konfiguration des Anruf Parks in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-10_

Das Parken von anrufen ist ein Anruf Verwaltungsfeature, das standardmäßig bei der Bereitstellung von Enterprise-VoIP installiert wird. In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie das Parken von Anrufen und die Benutzerrechte konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.

<div>


> [!IMPORTANT]  
> Benutzerdefinierte Musikdateien für die Anwendung zum Parken von Anrufen werden im Rahmen des lync Server 2013 Notfall Wiederherstellungsvorgangs nicht gesichert, und die Dateien gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden. Bewahren Sie immer eine separate Sicherungskopie der angepassten Musikdateien auf, die Sie für das Parken von Anrufen hochgeladen haben.



</div>

In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation im Zusammenhang mit dem Parken von Anrufen gelesen haben (siehe [Planning for Call Management Features in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Voraussetzungen für die Konfiguration des Anruf Parks

Das Parken von Anrufen erfordert die folgenden Komponenten:

  - Anwendungsdienst

  - Anwendung zum Parken von Anrufen

Diese Komponenten werden automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.

Wenn Sie möchten, dass Anrufer Wartemusik hören, solange der Anruf geparkt ist, wird zusätzlich eine Datei für die Wartemusik benötigt. Eine standardmäßige Musikdatei wird automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen. Sie können die Standarddatei durch eine eigene Wartemusikdatei ersetzen. Der Anruf Park verwendet Dateispeicher, um die Audiodatei zu speichern.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Konfigurieren von Benutzerrechten für das Parken von Anrufen

Sie können die folgenden Verwaltungstools verwenden, um das Parken von Anrufen zu konfigurieren:

  - Lync Server-Systemsteuerung

  - Lync Server-Verwaltungsshell

Sie verwenden diese Tools zum Einrichten der Orbit-Tabelle für das Parken von Anrufen und zum Konfigurieren anderer Einstellungen, die von der Funktion zum Parken von Anrufen verwendet werden.

Für die Konfiguration des Parkens von Anrufen sind je nach Aufgabe die folgenden Administratorrollen erforderlich:

  - **CsVoiceAdministrator:** Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.

  - **CsUserAdministrator:** Diese Administratorrolle kann das Parken von Anrufen in der VoIP-Richtlinie aktivieren. Diese Administratorrolle hat außerdem schreibgeschützten Zugriff auf alle VoIP-Konfigurationen.

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

