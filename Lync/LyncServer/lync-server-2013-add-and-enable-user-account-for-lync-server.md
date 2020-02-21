---
title: 'Lync Server 2013: Hinzufügen und Aktivieren des Benutzerkontos für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24fe3004f588f50edbcb9428d8bece7a4b20a28a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a>Hinzufügen und Aktivieren des Benutzerkontos für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-02_

Nachdem Sie ein Benutzerkonto in Active Directory Benutzer und Computer aktiviert haben, können Sie lync Server-Systemsteuerung verwenden, um neue lync Server 2013 Benutzerkonten zu erstellen und zu aktivieren, indem Sie einen Active Directory Benutzer zu lync Server hinzufügen.

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a>So fügen Sie einen neuen lync Server Benutzer hinzu und aktivieren ihn

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Klicken Sie auf **Benutzer aktivieren**.

5.  Klicken Sie im Dialogfeld **neue lync Server Benutzer** auf **Hinzufügen**.

6.  Geben Sie im Feld **Benutzer suchen** den vollständigen oder ersten Teil des Namens, des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der e-Mail-Adresse, des Benutzerprinzipalnamens (User Principal Name, UPN) oder der Telefonnummer des gewünschten Active Directory Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

7.  Wählen Sie in der Tabelle das Konto aus, das Sie lync Server hinzufügen möchten, und klicken Sie dann auf **OK**.

8.  Weisen Sie den Benutzer einem Pool zu, geben Sie weitere Details an, und weisen Sie die Richtlinien dem gewünschten Benutzer zu, und klicken Sie dann auf **aktivieren**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Entfernen eines Benutzerkontos aus lync Server 2013](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[Aktivieren und Deaktivieren von Benutzern für lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

