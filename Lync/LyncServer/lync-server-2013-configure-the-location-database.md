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
ms.openlocfilehash: b2b15f0c679e9380a1f1a624f00f6c19384878fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Configure the location database in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Sie müssen zunächst die Standortdatenbank konfigurieren, um Clients für die automatische Ermittlung ihres Standorts innerhalb eines Netzwerks zu aktivieren. Wenn Sie eine Standortdatenbank nicht konfigurieren und der Standort, der in der Standortrichtlinie **erforderlich** ist, auf **Ja** oder **Disclaimer**eingestellt ist, wird der Benutzer aufgefordert, einen Standort manuell einzugeben.

Um die Standortdatenbank zu konfigurieren, führen Sie die folgenden Aufgaben aus:

1.  Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf. Wenn Sie ein Elin-Gateway (Notfall Standort-Identifikationsnummer) verwenden, müssen Sie Elin in das \<Feld\> "CompanyName" einbeziehen.

2.  Überprüfen Sie die Adressen anhand der MSAG-Daten (Master Street Address Guide), die vom Dienstanbieter für E9-1-1 verwaltet werden.

3.  Veröffentlichen Sie die aktualisierte Datenbank.

<div>


> [!NOTE]  
> Alternativ können Sie eine sekundäre Standort Quelldatenbank definieren, die für die Position der Standortdatenbank verwendet werden kann. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Konfigurieren eines sekundären Standort Informationsdiensts in lync Server 2013</A>.



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

