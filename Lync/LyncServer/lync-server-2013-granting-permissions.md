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
ms.openlocfilehash: ccfdf804fc9052ac69b383d0f8cd3321222e79a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Gewähren von Berechtigungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Für Setup können Sie der universellen RTCUniversalServerAdmins-Gruppe für eine bestimmte Active Directory-Organisationseinheit Berechtigungen erteilen, sodass Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser OU lync Server 2013 in der angegebenen Domäne installieren können. Wenn Sie Berechtigungen für eine OU erteilen, werden die folgenden Berechtigungen gewährt:

  - Lesen

  - Schreiben

  - ReadSPN

  - WriteSPN

Für die Verwaltung können Sie den angegebenen OUs Berechtigungen hinzufügen, sodass Mitglieder der universellen RTC-Gruppen, die von der Gesamtstrukturvorbereitung erstellt wurden, auf die OUs zugreifen können, ohne dass Sie Mitglieder der Gruppe der Domänenadministratoren sein müssen. Die der angegebenen Organisationseinheit hinzugefügten Berechtigungen sind dieselben Berechtigungen, die das Cmdlet **enable-CsAdDomain** den OU-Containern Computer und Benutzer hinzufügt.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Gewähren von Setupberechtigungen in Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Gewähren von Berechtigungen für die Organisationseinheit in Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

