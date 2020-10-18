---
title: 'Lync Server 2013: Sichern und schützen von Datenbanken'
description: 'Lync Server 2013: Härten und schützen von Datenbanken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1ed8f54384e8ecac3b1e4ce6a4253a10bcc2c6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577431"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Härten und schützen der Datenbanken von lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-12-05_

Microsoft lync Server 2013 hängt auch von SQL Server Datenbanken zum Speichern von Benutzerinformationen, Konferenzstatus, Archivierungsdaten und Anruf Detail Datensätzen (CDRs) ab. Sie können die Verfügbarkeit von lync Server 2013 Daten in lync Server Back-End-Datenbanken maximieren, indem Sie die Anwendungsdaten auf eine Weise partitionieren, die die Fehlertoleranz verbessert und die Problembehandlung vereinfacht. Um diese Ziele zu erreichen, partitionieren Sie die Anwendungsdaten nach folgendem:

  - **Verwenden von bewährten Methoden**     für die Server Partitionierung Trennen Sie Ihre Betriebssystem-, Anwendungs-und Programmdateien von ihren Datendateien.

  - **Speichern von Transaktionsprotokolldateien und Datenbankdateien**     Speichern Sie diese Dateien separat, um die Fehlertoleranz zu erhöhen und die Wiederherstellung zu optimieren, und speichern Sie Sie auf einem verschlüsselten Datenträger oder Volume.

  - **Verwenden von Server Clustering**     Gruppieren Sie die Back-End-Server, um lync Server 2013 Systemverfügbarkeit zu optimieren.

  - **Sicherstellen, dass alle Datensicherungen verschlüsselt und ordnungsgemäß verarbeitet werden**     Verloren gegangene, verworfene oder verlegte Sicherungsmedien können eine erhebliche Bedrohung für die Datensicherheit für lync Server 2013 Bereitstellungen darstellen.

Auf einem beliebigen lync Server 2013 Server mit Ausnahme von Standard Edition-Server kann auf die SQL Server Express Instanz (RTCLOCAL-Instanz) nicht remote zugegriffen werden, und es werden keine lokalen Firewall-Ausnahmen erstellt, außer SQL Server Express auf einem Standard Edition-Server. Auf einem Standard Edition-Server sind sowohl die Back-End-Datenbank als auch der zentrale Verwaltungsspeicher (CMS) so eingerichtet, dass Sie Remote verfügbar sind. Um SQL Server Datenbanken zu verhärten, können Sie folgende Aktionen ausführen:

  - Passen Sie die SQL Server Express Firewall auf Standard Edition-Servern an, wodurch der Umfang von Servern eingeschränkt wird, die Remote auf die Datenbank zugreifen können. Standardmäßig kann eine beliebige IP-Adresse Remote auf die Datenbank zugreifen.

  - Verwenden Sie SQL Server Konfigurations-Manager, um die Protokolle, IP-Adressen und Ports für SQL Server Remotezugriff anzugeben:
    
      - Lync Server 2013 verwendet das TCP/IP-Protokoll. Er unterstützt IP Version 4 (IPv4), jedoch nicht IP Version 6 (IPv6).
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 können in einem Netzwerk mit aktiviertem dualen IP-Stack funktionieren.

        
        </div>
    
      - Lync Server 2013 unterstützt mehrere IP-Adressen (Multi-Homed-Netzwerk-Adresskarten). Sie können angeben, dass SQL Server nur bestimmte IP-Adressen (einzelne Adressen oder Subnetze) abhören und nur bestimmte Protokolle verwenden.
    
      - Lync Server 2013 unterstützt statische und dynamische SQL Server Ports.

  - Führen Sie SQL Server auf einem statischen (nicht-standardmäßigen) Port aus, und führen Sie SQL Server Browser nicht aus (damit der Abhör Port dem Client nicht gemeldet werden kann). Dies erfordert eine benutzerdefinierte Konfiguration für jeden SQL Server Client, einschließlich Front-End-Server, Monitoring Server, Archivierungsserver und Verwaltungskonsolen (ausführen lync Server-Verwaltungsshell, lync Server-Systemsteuerung oder Topologie-Generator) und alle anderen Server, auf denen lync Server Datenbanken ausführen).

<div>


> [!NOTE]  
> Der Zugriff auf Datenbanken muss auf vertrauenswürdige Datenbankadministratoren limitiert sein. Ein böswilliger Datenbankadministrator kann Daten in die Datenbanken einfügen oder ändern, um Rechte über die lync Server 2013 Server zu erwerben oder vertrauliche Informationen von den Diensten abzurufen, selbst wenn dem Datenbankadministrator kein direkter Zugriff oder keine Steuerung der lync Server 2013 Server gewährt wurde.



</div>

Ausführliche Informationen zu benutzerdefinierten Konfigurationen und zum Härten SQL Server Datenbanken finden Sie im NextHop-Blog Artikel "Verwenden von lync Server 2010 mit einer benutzerdefinierten SQL Server Netzwerkkonfiguration" unter [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) .

<div>


> [!NOTE]  
> Sie können auch Betriebssysteme und Anwendungsserver verhärten, und Sie können mithilfe von Gruppenrichtlinien Sicherheitssperren in ihrer lync Server-Bereitstellung implementieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Härten und schützen von Servern und Anwendungen für lync Server 2013</A>.



</div>

</div>

<span> </span>

</div>

</div>

</div>

