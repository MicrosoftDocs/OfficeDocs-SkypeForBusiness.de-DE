---
title: 'Lync Server 2013: Erstellen oder Ändern von Bandbreitenrichtlinien Profilen'
description: 'Lync Server 2013: Erstellen oder Ändern von Bandbreitenrichtlinien Profilen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8450cf8f4da53bf4a7e096fd7618b7fc6d055b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562971"
---
# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-15_

Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren. In Microsoft lync Server 2013 können nur Audio-und Video Modalitäten Bandbreiteneinschränkungen zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen. Sie können das lync Server-Systemsteuerung verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Jedes Bandbreitenrichtlinienprofil kann mindestens einem Netzwerkstandort zugeordnet werden. Erstellen oder ändern Sie mithilfe der folgenden Verfahren ein Bandbreitenrichtlinienprofil. Informationen zum Löschen eines bandbreitenrichtlinienprofils finden Sie unter [Löschen von Richtlinienprofilen für die Netzwerkbandbreite in lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>So erstellen Sie ein neues Bandbreitenrichtlinienprofil

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf **Neu**.

5.  Geben Sie im Abschnitt **Neues Bandbreitenrichtlinienprofil** im Feld **Name** einen Namen ein. Dieser Name muss eindeutig sein.

6.  Geben Sie im Feld **Audiolimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für alle Audioverbindungen in KBit/s fest.

7.  Geben Sie im Feld **Audiositzungslimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für eine einzelne Audioverbindung in KBit/s fest. Dieser Wert muss auf mindestens 40 festgelegt werden.

8.  Geben Sie im Feld **Videolimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für alle Videoverbindungen in KBit/s fest.

9.  Geben Sie im Feld **Videositzungslimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für eine einzelne Videoverbindung in KBit/s fest. Dieser Wert muss auf mindestens 100 festgelegt werden.

10. (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Bandbreitenrichtlinienprofil ein, die nicht durch den Namen allein vermittelt werden können.

11. Klicken Sie auf **Commit**.
    
    <div>
    

    > [!NOTE]  
    > Beim Erstellen eines neuen Bandbreitenrichtlinienprofils werden die Bandbreiteneinschränkungen nicht automatisch erzwungen. Sie müssen das Richtlinienprofil zunächst einem Standort zuordnen. Ausführliche Informationen zum Zuordnen eines Richtlinienprofils zu einer Website finden Sie unter <A href="lync-server-2013-creating-or-modifying-network-sites.md">erstellen oder Ändern von Netzwerkstandorten in lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>So ändern Sie ein Bandbreitenrichtlinienprofil

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das Bandbreitenrichtlinienprofil, das geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie auf der Seite **Bandbreitenrichtlinienprofil bearbeiten** die gewünschten Felder (ausführliche Informationen finden Sie im Abschnitt "So erstellen Sie ein neues Bandbreitenrichtlinienprofil" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit**.
    
    <div>
    

    > [!NOTE]  
    > Beim Ändern des Bandbreitenrichtlinienprofils werden die Bandbreiteneinschränkungen aller Netzwerkstandorte, die diesem Bandbreitenrichtlinienprofil zugeordnet sind, umgehend aktualisiert.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen von Richtlinienprofilen für Netzwerkbandbreite in lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Konfigurieren der Anrufsteuerung in lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Gruppe-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

