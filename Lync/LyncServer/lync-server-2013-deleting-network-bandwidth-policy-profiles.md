---
title: 'Lync Server 2013: Löschen von Richtlinienprofilen für Netzwerkbandbreiten'
description: 'Lync Server 2013: Löschen von Richtlinienprofilen für Netzwerkbandbreite.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f460d9620158d1857dae41e0033f6d36078868
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552661"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Löschen von Richtlinienprofilen für Netzwerkbandbreite in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren. In Microsoft lync Server 2013 können nur Audio-und Video Modalitäten Bandbreiteneinschränkungen zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen. Sie können das lync Server-Systemsteuerung verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Mit den folgenden Verfahren können Sie Richtlinienprofile für Netzwerkbandbreiten löschen. Ausführliche Informationen zum Erstellen oder Ändern eines Richtlinienprofils für die Netzwerkbandbreite finden Sie unter [erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>So löschen Sie ein Richtlinienprofil für die Bandbreite

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das Richtlinienprofil der Bandbreite, das Sie löschen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können auch mehrere Profile auf einmal löschen. Drücken Sie dazu die STRG-TASTE, und halten Sie sie gedrückt, während Sie mit der Maus auf die einzelnen Profile klicken. Wenn Sie alle Profile auswählen möchten, klicken Sie einfach im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.

    
    </div>

5.  Abschließend klicken Sie im Menü **Bearbeiten** auf **Löschen**.
    
    <div>
    

    > [!WARNING]  
    > Richtlinienprofile für Bandbreiten, die mit einem Netzwerkstandort verknüpft sind, können nicht ohne Weiteres gelöscht werden. In diesem Fall müssen Sie zuerst die Verknüpfung mit dem Netzwerkstandort aufheben, bevor Sie das Profil löschen können. Ausführliche Informationen zum Ändern des Netzwerkstandorts finden Sie unter <A href="lync-server-2013-creating-or-modifying-network-sites.md">erstellen oder Ändern von Netzwerkstandorten in lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Anzeigen von Richtlinienprofil Informationen für Netzwerkbandbreite in lync Server 2013](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Konfigurieren der Anrufsteuerung in lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

