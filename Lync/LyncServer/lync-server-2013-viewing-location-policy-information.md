---
title: 'Lync Server 2013: Anzeigen von Informationen zu Standortrichtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b5c4b512acc3541b933f583ad69e3f730dc14f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523512"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Anzeigen von Informationen zu Standortrichtlinien in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

In lync Server 2013 können Sie die Standortrichtlinie verwenden, um Einstellungen anzuwenden, die sich auf Erweiterte 9-1-1-Funktionen (E9-1-1) und auf Standorteinstellungen für Benutzer oder Kontakte beziehen. Die ortungsrichtlinie legt fest, ob ein Benutzer für E9-1-1 aktiviert ist und was das Verhalten eines Notrufs ist. Beispielsweise können Sie die ortungsrichtlinie verwenden, um zu definieren, welche Zahl einen Notruf darstellt (beispielsweise 911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.

Sie können Standortrichtlinien in lync Server 2013 Systemsteuerung in der Gruppe " **Netzwerkkonfiguration** " konfigurieren. In lync Server-Systemsteuerung können Sie Standortrichtlinien anzeigen, erstellen, ändern oder löschen. Verwenden Sie das folgende Verfahren, um Informationen zu Ortungsrichtlinien anzuzeigen. Ausführliche Informationen zum Erstellen oder Ändern von ortungsrichtlinien finden Sie unter [erstellen oder Ändern einer ortungsrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-view-information-about-a-location-policy"></a>So zeigen Sie Informationen zu einer Ortungsrichtlinie an

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
    
    <div>
    

    > [!NOTE]  
    > Sie können jeweils nur Informationen zu einer Ortungsrichtlinie anzeigen.

    
    </div>

Standardmäßig ist eine einzige Richtlinie (Global) vorhanden, die nicht gelöscht oder umbenannt werden kann. Sie können die globale Richtlinie jedoch ändern. Sofern keine Standortrichtlinien oder Richtlinien auf Benutzerbasis erstellt werden, wird diese Richtlinie auf sämtliche Benutzer und Kontakte angewendet. Richtlinien auf Benutzerbasis müssen auf bestimmte Benutzer angewendet werden.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern einer ortungsrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Erstellen von ortungsrichtlinien in lync Server 2013](lync-server-2013-create-location-policies.md)  
[Erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  


[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Gruppe-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

