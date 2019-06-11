---
title: 'Lync Server 2013: Installieren der Standard Edition-Serverdatenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Installieren der Standard Edition-Serverdatenbank für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Wenn Sie einen Standard Edition-Server als einzigen Server in Ihrer Infrastruktur einrichten, der sich von anderen Server Installationen unterscheidet, gibt es im Bereitstellungs- **Assistenten** eine Auswahl, die speziell für das Einrichten des ursprünglichen Servers vorgesehen ist.

<div>

## <a name="to-install-a-standard-edition-server"></a>So installieren Sie einen Standard Edition-Server

1.  Melden Sie sich bei dem Server an, auf dem Sie den Standard Edition-Server als lokalen Administrator oder als Domänen Entsprechung installieren möchten.

2.  Wenn Sie die Active Directory-Domänendienste nicht vorbereitet haben, führen Sie zuerst diese Verfahren aus. Ausführliche Informationen finden Sie unter [Vorbereiten von Active Directory-Domänendiensten für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **First Standard Edition-Server vorbereiten**.

4.  Klicken Sie auf der Seite **Single Standard Edition-Server vorbereiten** auf **weiter**.

5.  Auf der Seite **Ausführungsbefehle** wird SQL Server 2012 Express als zentraler Verwaltungsspeicher installiert. Es werden erforderliche Firewallregeln erstellt. Wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Die anfängliche Installation kann einige Zeit in Anspruch nehmen, ohne dass die Anzeige des Befehlsausgabe Zusammenfassungsbildschirms sichtbar wird. Dies ist auf die Installation von SQL Server Express zurückzuführen. Wenn Sie die Installation der Datenbank überwachen müssen, verwenden Sie den Task-Manager, um das Setup zu überwachen.

    
    </div>

6.  Klicken Sie auf der Seite mit dem lync Server-Bereitstellungs-Assistenten auf **Topologie-Generator installieren** , wenn Sie die Verwaltungstools zuvor noch nicht installiert haben. Ausführliche Informationen finden Sie unter [Installieren von lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Vergewissern Sie sich, dass neben "Active Directory vorbereiten", "Vorbereiten des ersten Standard Edition-Servers" und "Installieren des Topologie-Generators" grüne Häkchen vorhanden sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

