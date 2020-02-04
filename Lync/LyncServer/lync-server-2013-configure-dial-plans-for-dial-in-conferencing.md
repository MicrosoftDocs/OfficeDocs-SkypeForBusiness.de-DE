---
title: 'Lync Server 2013: Konfigurieren von Wählplänen für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 544c431257dea20db729e80dd1d9acc565da8201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Bei der Bereitstellung von Einwahlkonferenzen müssen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl erstellen oder ändern. Stellen Sie sicher, dass mindestens eine Normalisierungsregel in den einzelnen Wähleinstellungen Telefonerweiterungen in vollständige Telefonnummern im E. 164-Format umwandelt. Benutzer von Einwahlkonferenzen nehmen an Konferenzen als authentifizierte Unternehmensbenutzer teil, indem sie ihre PIN und die Telefonnummer eingeben. Sie benötigen eine Normalisierungsregel zum Konvertieren von Durchwahlen in vollständige Rufnummern, damit Benutzer bei Eingabe einer Durchwahl authentifiziert werden können.

Gehen Sie wie folgt vor, um Wählpläne für Einwahlkonferenzen einzurichten:

  - Unabhängig davon, ob Sie Enterprise-VoIP bereitstellen oder nicht, fügen Sie zu den Wähleinstellungen eine Region für Einwahlkonferenzen hinzu und stellen Sie sicher, dass Ihre Einwahlnummern einwandfrei von einer Normalisierungsregel umgewandelt werden. Ausführliche Anweisungen finden Sie unter [Ändern von Wähleinstellungen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Wenn Sie Enterprise-VoIP nicht bereitstellen, erstellen Sie Wählpläne für Ihre Einwahlnummern. Fügen Sie auf jeden Fall eine Region für Einwahlkonferenzen hinzu. Ausführliche Anweisungen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Wenn Sie Enterprise-VoIP bereitgestellt haben, ändern Sie Enterprise-sprach Wählpläne nach Bedarf, um Regionen einzubeziehen und geeignete Normalisierungsregeln für Einwahl Zugriffsnummern zu verwenden. Ausführliche Anweisungen finden Sie unter [Ändern von Wähleinstellungen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md). Sie können auch dedizierte Wählpläne erstellen, die nur für Einwahl Zugriffsnummern verwendet werden. Ausführliche Anweisungen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Details zu Planungsregionen finden Sie unter [Anforderungen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Anzeigen von Wähl Planinformationen in lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Definieren von Normalisierungsregeln in Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

