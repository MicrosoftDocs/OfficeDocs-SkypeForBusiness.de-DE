---
title: 'Lync Server 2013: Konfigurieren der Standortdatenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9495bc0c52e8e9af4af0daa3d29304d5b25d4b7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520262"
---
# <a name="configure-the-location-database-in-lync-server-2013"></a>Konfigurieren der Standortdatenbank in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-17_

Sie müssen zunächst die Standortdatenbank konfigurieren, um Clients für die automatische Ermittlung ihres Standorts innerhalb eines Netzwerks zu aktivieren. Wenn Sie keine Standortdatenbank konfigurieren und **Standort erforderlich** in der Ortungsrichtlinie auf **Ja** oder **Haftungsausschluss** festgelegt ist, wird der Benutzer zur manuellen Eingabe eines Standorts aufgefordert.

Zur Konfiguration der Standortdatenbank führen Sie die folgenden Aufgaben aus:

1.  Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf. Wenn Sie ein Elin-Gateway (Emergency Location Identification Number) verwenden, müssen Sie das Elin in das \<CompanyName\> Feld einbeziehen.

2.  Überprüfen Sie die Adressen anhand der MSAG-Daten (Master Street Address Guide), die vom Dienstanbieter für E9-1-1 verwaltet werden.

3.  Veröffentlichen Sie die aktualisierte Datenbank.

<div>


> [!NOTE]  
> Alternativ können Sie eine sekundäre Standortdatenbank definieren, die anstelle der Standortdatenbank verwendet wird. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Konfigurieren einer sekundären Standortinformationsdienst in lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Auffüllen der Standortdatenbank in lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [Überprüfen von Adressen in lync Server 2013](lync-server-2013-validate-addresses.md)

  - [Veröffentlichen der Standortdatenbank aus lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

