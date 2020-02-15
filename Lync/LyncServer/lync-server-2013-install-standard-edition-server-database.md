---
title: 'Lync Server 2013: Installieren Standard Edition-Server Datenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52853073fec62a3386936fe093b83e902d576069
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Installieren Standard Edition-Server Datenbank für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Das Einrichten eines Standard Edition-Server als einziger Server in Ihrer Infrastruktur, der von den Heimbenutzern unterschiedlich ist, unterscheidet sich von anderen Server Installationen dadurch, dass eine Auswahl im **Bereitstellungs-Assistenten** speziell für das Einrichten des ursprünglichen Servers vorliegt.

<div>

## <a name="to-install-a-standard-edition-server"></a>So installieren Sie einen Standard Edition-Server

1.  Melden Sie sich an dem Server an, auf dem Standard Edition-Server als lokaler Administrator oder als Domänen Äquivalent installiert werden soll.

2.  Wenn Sie Active Directory-Domänendienste nicht vorbereitet haben, führen Sie zunächst diese Verfahren aus. Ausführliche Informationen finden Sie unter [vorbereiten Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **erste Standard Edition-Server vorbereiten**.

4.  Klicken Sie auf der Seite **Einzelnen Standard Edition-Server vorbereiten** auf **Weiter**.

5.  Auf der Seite **Befehle werden ausgeführt** wird der SQL Server 2012 Express als zentraler Verwaltungsspeicher installiert. Die erforderlichen Firewallregeln werden erstellt. Klicken Sie auf **Fertig stellen**, wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist.
    
    <div>
    

    > [!NOTE]  
    > Die Erstinstallation kann einige Zeit in Anspruch nehmen, und auf dem Zusammenfassungsbildschirm zur Befehlsausgabe werden keine Aktualisierungen angezeigt. Dies ist auf die Installation des SQL Server Express zurückzuführen. Sie können den Fortschritt der Datenbankinstallation im Task-Manager überwachen.

    
    </div>

6.  Klicken Sie auf der Seite lync Server-Bereitstellungs-Assistenten auf **Topologie-Generator installieren** , wenn Sie die Verwaltungstools nicht zuvor installiert haben. Ausführliche Informationen finden Sie unter [install lync Server 2013 Administration Tools](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Vergewissern Sie sich, dass neben "Vorbereiten von Active Directory", "Vorbereiten des ersten Standard Edition-Servers" und "Installieren des Topologie-Generators" grüne Häkchen angezeigt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

