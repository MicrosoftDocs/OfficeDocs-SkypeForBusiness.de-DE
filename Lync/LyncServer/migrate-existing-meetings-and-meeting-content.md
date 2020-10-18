---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
description: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94dd35063a121a057a218c27fdb36e42a155b77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579311"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrieren vorhandener Besprechungen und Besprechungsinhalte

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Wenn ein Benutzerkonto von lync Server 2010 auf einen lync Server 2013 Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:

  - **Vom Benutzer bereits geplante Besprechungen**: Dies beinhaltet das Verschieben von Konferenzverzeichnissen und Konferenzdaten.

  - **Die persönliche Identifikationsnummer (PIN) des Benutzers**: Die aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.

Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben:

  - **Besprechungsinhalte**: Um den während einer Besprechung freigegebenen Inhalt zu verschieben, z. B. PowerPoint- oder Whiteboard-Inhalt, Anlagen oder Umfragedaten, verwenden Sie den **-MoveConferenceData**-Parameter als Teil des **Move-CsUser**-Cmdlets.

</div>

<span> </span>

</div>

</div>

</div>

