---
title: 'Lync Server 2013: Anzeigen von Positions Richtlinieninformationen'
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
ms.openlocfilehash: 0f68ad38ffbc8bb1b4abdfbf8119add7d9f965e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Anzeigen von Standortrichtlinien Informationen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In lync Server 2013 können Sie mithilfe der ortungsrichtlinie Einstellungen anwenden, die sich auf die erweiterte 9-1-1 (E9-1-1)-Funktionalität und auf die Standorteinstellungen für Benutzer oder Kontakte beziehen. Die ortungsrichtlinie bestimmt, ob ein Benutzer für E9-1-1 aktiviert ist, und wenn ja, was das Verhalten eines Notrufs ist. So können Sie beispielsweise mithilfe der ortungsrichtlinie definieren, welche Nummer ein Notruf ist (beispielsweise 911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.

Sie können Standortrichtlinien über die Gruppe **Netzwerkkonfiguration** in der lync Server 2013-Systemsteuerung konfigurieren. In der lync Server-Systemsteuerung können Sie Positions Richtlinien anzeigen, erstellen, ändern oder löschen. Gehen Sie wie folgt vor, um Informationen zu Standortrichtlinien anzuzeigen. Details zum Erstellen oder Ändern von Standortrichtlinien finden Sie unter [erstellen oder Ändern einer Standortrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-view-information-about-a-location-policy"></a>So zeigen Sie Informationen zu einer Standortrichtlinie an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **ortungsrichtlinie**.

4.  Wählen Sie auf der Seite **Standortrichtlinie** die zu ändernde Standortrichtlinie aus.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
    
    <div>
    

    > [!NOTE]  
    > Sie können nur Informationen zu einer Standortrichtlinie gleichzeitig anzeigen.

    
    </div>

Eine einzelne Richtlinie namens "Global" ist standardmäßig vorhanden und kann nicht gelöscht oder umbenannt werden. Sie können jedoch die globale Richtlinie ändern. Diese Richtlinie gilt für alle Benutzer und Kontakte, es sei denn, Sie erstellen Website Richtlinien oder Richtlinien für einzelne Benutzer. Richtlinien für einzelne Benutzer müssen auf bestimmte Benutzer angewendet werden.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern einer Standortrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Erstellen von Standortrichtlinien in lync Server 2013](lync-server-2013-create-location-policies.md)  
[Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  


[Neu – CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Satz-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

