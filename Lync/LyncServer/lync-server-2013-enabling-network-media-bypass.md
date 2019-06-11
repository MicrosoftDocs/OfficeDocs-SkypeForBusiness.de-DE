---
title: 'Lync Server 2013: Aktivieren der Netzwerkmedien Umgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff18c69d6d257a520d2413bff266c97879d4963e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Aktivieren der Netzwerkmedien Umgehung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Medienumgehungseinstellungen gelten global für eine Microsoft lync Server 2013-Bereitstellung. Die medienumgehung ermöglicht Anrufe, den Vermittlungs Server zu umgehen. Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) im Abschnitt Planung.

Sie können die medienumgehung in der lync Server-Systemsteuerung aktivieren und konfigurieren.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>So aktivieren und konfigurieren Sie die medienumgehung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration. Es gibt immer nur eine Konfiguration, und Sie wird immer als "Global" bezeichnet.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Klicken Sie auf der Seite **globale Einstellungen bearbeiten** auf das Kontrollkästchen **medienumgehung aktivieren** .

7.  Wählen Sie eine der folgenden Optionen aus:
    
      - **Immer umgehen**   wählen Sie diese Option aus, um bei allen Anrufen medienumgehung zu versuchen. Diese Option steht nicht zur Verfügung, wenn die Anrufsteuerung (Call Admission Control, CAC) aktiviert ist. Wenn CAC nicht aktiviert ist, wählen Sie diese Option in den folgenden Fällen aus:
        
          - Die Bandbreitensteuerung ist nicht erforderlich.
        
          - Es besteht keine Notwendigkeit für eine fein abgestimmte Konfiguration, um festzustellen, wann eine Umgehung erfolgen soll.
        
          - Es besteht eine vollständige Konnektivität zwischen Gateways und Clients.
    
      - **Verwenden von Websites und der Regions Konfiguration**   wenn CAC aktiviert ist, ist diese Option standardmäßig aktiviert und kann nicht geändert werden. Wenn diese Option ausgewählt ist, werden Netzwerk Konfigurations Websites und-Regionen verwendet, um zu ermitteln, wann eine medienumgehung möglich ist. Wenn Sie diese Option auswählen, können Sie die Umgehung für Websites aktivieren, die nicht zugeordnet sind. Aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Websites aktivieren** nur, wenn Sie über eine oder mehrere große Websites verfügen, die dem gleichen Bereich zugeordnet sind, die keine Bandbreiteneinschränkungen aufweisen (beispielsweise eine große zentrale Website), und auch einige Verzweigungs Websites zugeordnet sind, die dem dieselbe Region mit Bandbreiteneinschränkungen. Wenn Sie die Umgehung für nicht zugeordnete Websites aktivieren, wird die Konfiguration optimiert, da Sie nur die Subnetze angeben, die den Zweigstellen zugeordnet sind, anstatt alle Subnetze anzugeben, die allen Websites zugeordnet sind. Wir empfehlen, dass Sie das Kontrollkästchen **Bypass für nicht zugeordnete Websites aktivieren** nicht aktivieren, wenn CAC aktiviert ist.

8.  Klicken Sie auf **Commit** , um Ihre Änderungen zu speichern.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Deaktivieren der Netzwerkmedien Umgehung in lync Server 2013](lync-server-2013-disabling-network-media-bypass.md)  


[Globale Medien Umgehungs Optionen in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

