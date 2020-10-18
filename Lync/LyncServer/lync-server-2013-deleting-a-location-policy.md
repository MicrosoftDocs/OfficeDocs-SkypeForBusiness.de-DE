---
title: 'Lync Server 2013: Löschen einer ortungsrichtlinie'
description: 'Lync Server 2013: Löschen einer ortungsrichtlinie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88935c00a60de377c9812a4d119708fd610338ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575841"
---
# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Löschen einer ortungsrichtlinie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-10_

In lync Server 2013 können Sie die Standortrichtlinie verwenden, um Einstellungen anzuwenden, die sich auf Erweiterte 9-1-1-Funktionen (E9-1-1) und auf Standorteinstellungen für Benutzer oder Kontakte beziehen. Die ortungsrichtlinie legt fest, ob ein Benutzer für E9-1-1 aktiviert ist und was das Verhalten eines Notrufs ist. Beispielsweise können Sie die ortungsrichtlinie verwenden, um zu definieren, welche Zahl einen Notruf darstellt (beispielsweise 911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.

Sie können Standortrichtlinien in lync Server 2013 Systemsteuerung in der Gruppe " **Netzwerkkonfiguration** " konfigurieren. In lync Server-Systemsteuerung können Sie Standortrichtlinien anzeigen, erstellen, ändern oder löschen. Gehen Sie wie folgt vor, um eine Ortungsrichtlinie zu löschen. Ausführliche Informationen zum Erstellen oder Ändern von ortungsrichtlinien finden Sie unter [erstellen oder Ändern einer ortungsrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-delete-a-location-policy"></a>So löschen Sie eine Ortungsrichtlinie

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die gelöscht werden soll.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehrere Ortungsrichtlinien in einem Arbeitsschritt löschen. Drücken Sie hierzu die STRG-TASTE, und wählen Sie bei gedrückter STRG-TASTE mehrere Richtlinien aus. Wenn Sie alle Richtlinien auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Die globale Ortungsrichtlinie kann nicht gelöscht werden. Beim Versuch, die globale Richtlinie zu löschen, wird eine Warnmeldung angezeigt, und die Richtlinie wird auf die Standardwerte zurückgesetzt.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern einer ortungsrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Anzeigen von Informationen zu Standortrichtlinien in lync Server 2013](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

