---
title: Verhindern von Sitzungen für Dienste
description: Verhindern von Sitzungen für Dienste
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563691"
---
# <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Sie können Microsoft lync Server 2010 Systemsteuerung verwenden, um neue Sitzungen für alle lync Server 2010-Dienste zu verhindern, die auf einem bestimmten Computer auszuführen sind, oder um neue Sitzungen für einen bestimmten lync Server 2010 Dienst zu verhindern.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>So verhindern Sie neue Sitzungen für alle Lync Server-Dienste auf einem Computer

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder durchsuchen Sie auf der Seite **Status** die Liste, um den Computer zu ermitteln, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten. Klicken Sie anschließend auf den Computer.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf **Neue Sitzungen für alle Dienste verhindern**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>So verhindern Sie neue Sitzungen für einen bestimmten Dienst

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.

5.  Klicken Sie auf **Eigenschaften**.

6.  Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.

7.  Klicken Sie auf **Aktion**.

8.  Klicken Sie auf **Neue Sitzungen für Dienst verhindern**.

9.  Klicken Sie auf **Schließen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

