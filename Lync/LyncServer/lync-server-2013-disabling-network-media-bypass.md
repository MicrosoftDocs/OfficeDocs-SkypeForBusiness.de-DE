---
title: 'Lync Server 2013: Deaktivieren der Netzwerkmedien Umgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaad239f320f498378498f9b3e373592d487c0c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Deaktivieren der Netzwerkmedien Umgehung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-15_

Die Einstellungen für die medienumgehung gelten global für eine Microsoft lync Server 2013-Bereitstellung. Die Medienumgehung ermöglicht bei Anrufen die Umgehung des Vermittlungsservers. Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) im Abschnitt Planning. Sie können die medienumgehung aus dem lync Server-Systemsteuerung deaktivieren. Ausführliche Informationen zum Aktivieren und Konfigurieren der medialen Umgehung finden Sie unter [Aktivieren der Netzwerkmedien Umgehung in lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>So deaktivieren Sie die Medienumgehung

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**. Es ist immer nur eine Konfiguration vorhanden, und diese trägt stets den Namen "Global".

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Deaktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.

7.  Klicken Sie auf **Commit**, um Ihre Änderungen zu speichern.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Aktivieren der Netzwerkmedien Umgehung in lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

