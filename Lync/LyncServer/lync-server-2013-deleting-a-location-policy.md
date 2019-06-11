---
title: 'Lync Server 2013: Löschen einer Standortrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4766d2b05cef89ab29b9c303c5ba1ec456843669
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Löschen einer Standortrichtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

In lync Server 2013 können Sie mithilfe der ortungsrichtlinie Einstellungen anwenden, die sich auf die erweiterte 9-1-1 (E9-1-1)-Funktionalität und auf die Standorteinstellungen für Benutzer oder Kontakte beziehen. Die ortungsrichtlinie bestimmt, ob ein Benutzer für E9-1-1 aktiviert ist, und wenn ja, was das Verhalten eines Notrufs ist. So können Sie beispielsweise mithilfe der ortungsrichtlinie definieren, welche Nummer ein Notruf ist (beispielsweise 911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.

Sie können Standortrichtlinien über die Gruppe **Netzwerkkonfiguration** in der lync Server 2013-Systemsteuerung konfigurieren. In der lync Server-Systemsteuerung können Sie Positions Richtlinien anzeigen, erstellen, ändern oder löschen. Gehen Sie wie folgt vor, um eine Standortrichtlinie zu löschen. Details zum Erstellen oder Ändern von Standortrichtlinien finden Sie unter [erstellen oder Ändern einer Standortrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-delete-a-location-policy"></a>So löschen Sie eine Standortrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **ortungsrichtlinie**.

4.  Wählen Sie auf der Seite **Standortrichtlinie** die zu löschende Standortrichtlinie aus.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehr als eine Standortrichtlinie gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Richtlinien aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Richtlinien auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können die globale Standortrichtlinie nicht löschen. Wenn Sie versuchen, die globale Richtlinie zu löschen, wird eine Warnmeldung angezeigt, und die Richtlinie wird auf die Standardwerte zurückgesetzt.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern einer Standortrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Anzeigen von Standortrichtlinien Informationen in lync Server 2013](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

