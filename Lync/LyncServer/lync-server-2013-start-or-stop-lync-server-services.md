---
title: 'Lync Server 2013: Starten oder Beenden von lync Server Diensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc8e398a79c8541db4a2362e5419ed98fdf7f53e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>Starten oder Beenden von lync Server 2013 Diensten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

Sie können lync Server-Systemsteuerung verwenden, um alle lync Server 2013-Dienste zu starten oder zu beenden, die auf einem bestimmten Computer laufen, oder um einen bestimmten Dienst zu starten oder zu beenden.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>So starten oder beenden Sie alle Lync Server-Dienste auf einem Computer

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben. Sie können bestimmen, ob Ihnen die CsServerAdministrator-oder die CsAdministrator-RBAC-Rolle zugewiesen wurde, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, und ermitteln Sie so den Computer, auf dem die Dienste ausgeführt werden, die Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf **Alle Dienste starten** bzw. auf **Alle Dienste beenden**.

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>So starten oder beenden Sie einen bestimmten Dienst

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.

5.  Klicken Sie auf **Eigenschaften**.

6.  Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.

7.  Klicken Sie auf **Aktion**.

8.  Klicken Sie auf **Dienst starten** bzw. auf **Dienst beenden**.

9.  Klicken Sie auf **Schließen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verhindern von Sitzungen für Dienste in lync Server 2013](lync-server-2013-prevent-sessions-for-services.md)  


[Verwalten der lync Server 2013 Topologie](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

