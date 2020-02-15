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
ms.openlocfilehash: e28dd2ddb0633a45d19f1a7bb7638d86e042658b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Konfigurieren von Wählplänen für Einwahlkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-25_

Bei der Bereitstellung von Einwahlkonferenzen müssen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl erstellen oder ändern. Stellen Sie sicher, dass in jedem Satz mit Wähleinstellungen mindestens eine Normalisierungsregel die Telefondurchwahlen in vollständige Rufnummern im E.164-Format konvertiert. Benutzer von Einwahlkonferenzen nehmen an Konferenzen als authentifizierte Unternehmensbenutzer teil, indem sie ihre PIN und die Telefonnummer eingeben. Sie benötigen eine Normalisierungsregel zum Konvertieren von Durchwahlen in vollständige Rufnummern, damit Benutzer bei Eingabe einer Durchwahl authentifiziert werden können.

Gehen Sie folgendermaßen vor, um Wähleinstellungen für Einwahlkonferenzen einzurichten:

  - Unabhängig davon, ob Sie Enterprise-VoIP bereitstellen oder nicht, ändern Sie den globalen Wählplan so, dass eine Einwahlkonferenz Region hinzugefügt wird, und stellen Sie sicher, dass die Zugriffsnummern für die Einwahl in Normalisierungsregeln korrekt konvertiert werden. Ausführliche Anweisungen finden Sie unter [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Wenn Sie Enterprise-VoIP nicht bereitgestellt haben, erstellen Sie Wählpläne für Ihre Zugriffsnummern für Einwahlkonferenzen. Stellen Sie sicher, dass Sie eine Region für Einwahlkonferenzen angeben. Ausführliche Anweisungen finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Wenn Sie Enterprise-VoIP bereitgestellt haben, ändern Sie Enterprise-VoIP-Wählpläne nach Bedarf, um Regionen einzubeziehen und geeignete Normalisierungsregeln für Einwahlnummern zu verwenden. Ausführliche Anweisungen finden Sie unter [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md). Sie können auch dedizierte Wähleinstellungen erstellen, die nur für Zugriffsnummern für die Einwahl eingesetzt werden. Ausführliche Anweisungen finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Ausführliche Informationen zu Planungsregionen finden Sie unter [Einwahlkonferenz Anforderungen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Anzeigen von Informationen zu Wählplänen in lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Erstellen von Wähleinstellungen in lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Ändern von Wähleinstellungen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

