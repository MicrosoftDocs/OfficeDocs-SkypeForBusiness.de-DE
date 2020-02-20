---
title: 'Lync Server 2013: Gewähren von Berechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc725122005793790344544575fa4456d742c88d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Erteilen von Berechtigungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-15_

Für das Setup können Sie der universellen Gruppe RTCUniversalServerAdmins Berechtigungen für eine bestimmte Active Directory Organisationseinheit (Organizational Unit, OU) erteilen, sodass Mitglieder der Gruppe RTCUniversalServerAdmins in dieser Organisationseinheit lync Server 2013 in der angegebenen Domäne installieren können. Wenn Sie Berechtigungen für eine Organisationseinheit erteilen, werden die folgenden Berechtigungen erteilt:

  - Lesen

  - Schreiben

  - ReadSPN

  - WriteSPN

Zur Verwaltung können Sie bestimmten Organisationseinheiten Berechtigungen gewähren, sodass Mitglieder der während der Gesamtstrukturvorbereitung erstellten universellen RTC-Gruppen auf die Organisationseinheit zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein. Bei den Berechtigungen, die Sie zur angegebenen Organisationseinheit hinzufügen, handelt es sich um die gleichen Berechtigungen, die das Cmdlet **Enable-CsAdDomain** den OU-Containern für Computer und Benutzer hinzufügt.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erteilen von Setup Berechtigungen in lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Erteilen von Berechtigungen für Organisationseinheiten in lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

