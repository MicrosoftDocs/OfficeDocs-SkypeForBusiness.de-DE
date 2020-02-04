---
title: 'Lync Server 2013: Deaktivieren eines Benutzers für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f89b40a7398f35efab418fac7be92536ec17270
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Deaktivieren eines Benutzers für Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Gehen Sie wie folgt vor, um Enterprise-VoIP für ein Benutzerkonto zu deaktivieren, das für lync Server 2013 aktiviert ist.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7.  Klicken Sie auf der Seite **lync Server-Benutzer bearbeiten** unter **Telefonie**auf eine beliebige Option mit Ausnahme von **Enterprise-VoIP**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen Benutzer daran hindern möchten, Audio-oder Videoanrufe mit lync zu führen, klicken Sie unter <STRONG>Telefonie</STRONG>auf <STRONG>Audio/Video deaktiviert</STRONG>.

    
    </div>

8.  Klicken Sie auf **Commit ausführen**.

Der Benutzer kann nun die Enterprise-VoIP-Funktion nicht verwenden.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Verwalten von Enterprise-VoIP für Benutzer in lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Verwaltungsshell für Lync Server 2013](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

