---
title: 'Lync Server 2013: Aktivieren der Netzwerkmedien Umgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a269f22eabc294af45697ab1bd2c0eabe4b5aad6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Aktivieren der Netzwerkmedien Umgehung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Die Einstellungen für die medienumgehung gelten global für eine Microsoft lync Server 2013-Bereitstellung. Die Medienumgehung ermöglicht bei Anrufen die Umgehung des Vermittlungsservers. Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) im Abschnitt Planning.

Sie können die medienumgehung im lync Server-Systemsteuerung aktivieren und konfigurieren.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>So aktivieren und konfigurieren Sie die Medienumgehung

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**. Es ist immer nur eine Konfiguration vorhanden, und diese trägt stets den Namen "Global".

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** auf das Kontrollkästchen **Medienumgehung aktivieren**.

7.  Wählen Sie eine der folgenden Optionen aus:
    
      - **Immer umgehen**   wählen Sie diese Option aus, um die medienumgehung für alle Anrufe zu versuchen. Diese Option ist nicht verfügbar, wenn die Anrufsteuerung aktiviert ist. Ist die Anrufsteuerung nicht aktiviert, wählen Sie diese Option in den folgenden Situationen:
        
          - Es besteht keine Notwendigkeit zur Bandbreitensteuerung.
        
          - Es ist keine fein abgestimmte Konfiguration erforderlich, mit der die Anforderung einer Medienumgehung erkannt wird.
        
          - Zwischen Gateways und Clients ist vollständige Konnektivität gegeben.
    
      - **Verwenden von Websites und Regions Konfiguration**   wenn die Anrufsteuerung aktiviert ist, ist diese Option standardmäßig aktiviert und kann nicht geändert werden. Ist diese Option ausgewählt, wird anhand der Standorte und Regionen in der Netzwerkkonfiguration ermittelt, ob eine Medienumgehung möglich ist. Wenn Sie diese Option auswählen, können Sie eine Umgehung für Standorte aktivieren, die nicht zugeordnet sind. Aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren** nur dann, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die mit einer bestimmten Region verknüpft sind, und Sie außerdem über einige Zweigstellen mit Bandbreiteneinschränkungen verfügen, die mit derselben Region verknüpft sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die mit den Zweigstandorten verknüpften Subnetze angeben, statt sämtliche, mit allen Standorten verknüpfte Subnetze angeben zu müssen. Es wird empfohlen, das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte** nicht zu aktivieren, wenn die Anrufsteuerung aktiviert ist.

8.  Klicken Sie auf **Commit**, um Ihre Änderungen zu speichern.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Deaktivieren der Netzwerkmedien Umgehung in lync Server 2013](lync-server-2013-disabling-network-media-bypass.md)  


[Optionen für die globale medienumgehung in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

