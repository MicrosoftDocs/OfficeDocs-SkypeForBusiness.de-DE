---
title: 'Lync Server 2013: Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff09dc330c7194ebe3657220c20a6138dc2f9a4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Nach dem Aktualisieren der Topologie im Topologie-Generator müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie die Archivierung konfigurieren und verwenden können. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.

<div>

## <a name="to-publish-your-updated-topology"></a>So veröffentlichen Sie Ihre aktualisierte Topologie

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 läuft oder auf dem die lync Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit gleichwertigen Benutzerrechten).
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die erforderlich ist, um der Topologie einen Server hinzuzufügen. Sie müssen ein Konto verwenden, das Mitglied der Gruppe " <STRONG>Domänen-Admins</STRONG> " und der Gruppe " <STRONG>RTCUniversalServerAdmins</STRONG> " ist und das über die Berechtigung "Vollzugriff" (lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den lync Server 2013 Dateispeicher verwenden (damit der Topologie-Generator die erforderliche DACL (Discretionary Access Control List) konfigurieren kann. oder ein Konto mit gleichwertigen Rechten.

    
    </div>

2.  Öffnen Sie die Topologie, die Sie im vorherigen Abschnitt mithilfe des Topologie-Generators erstellt haben.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.

4.  Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

5.  Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann. Ausführliche Informationen zu den erforderlichen Administratorrechten und-Berechtigungen finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Mithilfe des Topologie-Generators können nur Datenbanken auf dedizierten SQL Server Servern installiert werden. Datenbanken auf SQL Server Servern, die mit anderen Server Komponenten zusammenhängen, müssen installiert werden, indem das lokale Setup auf diesem Computer ausgeführt wird.

    
    </div>

6.  Überprüfen Sie auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, ob die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-support-for-archiving.md">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

