---
title: Verhindern von Sitzungen für Dienste
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf8fb96fef5a01f9b25ca954dd27d1bdfd1f7055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Sie können die Systemsteuerung von Microsoft lync Server 2010 verwenden, um neue Sitzungen für alle lync Server 2010-Dienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten lync Server 2010-Dienst zu verhindern.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>So verhindern Sie, dass neue Sitzungen für alle lync Server-Dienste auf einem Computer

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten, und klicken Sie darauf.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf **neue Sitzungen für alle Dienste verhindern**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>So verhindern Sie neue Sitzungen für einen bestimmten Dienst

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten, und klicken Sie darauf.

5.  Klicken Sie auf **Eigenschaften**.

6.  Sortieren Sie die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.

7.  Klicken Sie auf **Aktion**.

8.  Klicken Sie auf **neue Sitzungen für Dienst verhindern**.

9.  Klicken Sie auf **Schließen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

