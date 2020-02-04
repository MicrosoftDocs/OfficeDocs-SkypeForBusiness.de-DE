---
title: 'Lync Server 2013: Ändern der Optionen für die Archivierungsdatenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198e2abff6118197167f0f017ace22fc2ad76381
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Ändern der Optionen für die Archivierungsdatenbank in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wenn Sie die Archivierung mithilfe des SQL Server-Speichers zum Archivieren von Speicher für Ihre Benutzer bereitstellen, können Sie die folgenden Datenbankspeicher Änderungen vornehmen:

  - Verwenden Sie eine andere SQL Server-Datenbank zum Archivieren von Speicher. Dazu gehören die primäre Archivierungsdatenbank und jede Datenbank, die Sie für die SQL Server-Spiegelung verwenden.

  - Wechseln Sie zur Microsoft Exchange-Integration, um Archivierungsdaten und-Dateien auf Exchange 2013-Servern zu speichern. Wenn alle Ihre Benutzer auf Ihren Exchange 2013-Servern verwaltet werden und Sie den Microsoft Exchange-Speicher für alle Benutzer in Ihrer Bereitstellung verwenden möchten, sollten Sie die SQL Server-Speicher Datenbanken aus Ihrer Topologie entfernen.

Wenn Sie eine dieser Änderungen vornehmen möchten, müssen Sie den Topologie-Generator ausführen, die Änderungen vornehmen und die Topologie dann erneut veröffentlichen. Sie können den Topologie-Generator verwenden, um dies zu tun. Geben Sie keinen **Archivierungs-SQL Server-Speicher** an, oder aktivieren Sie die **Spiegelungsinformationen des SQL Server-Speichers** , es sei denn, Sie verfügen über lync-Benutzer, die nicht auf Exchange 2013-Servern verwaltet werden

<div>

## <a name="to-change-your-archiving-database-option"></a>So ändern Sie die Option für die Archivierungsdatenbank

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 ausgeführt wird oder auf dem die lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe "Benutzer" (oder einem Konto mit entsprechenden Benutzerrechten) ist.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das ein Mitglied der lokalen Benutzergruppe ist, aber eine Topologie veröffentlichen, die zum Hinzufügen einer Komponente zur Topologie erforderlich ist. Sie müssen ein Konto verwenden, das ein Mitglied der Gruppe " <STRONG>Domänen-Admins</STRONG> " und der Gruppe " <STRONG>RTCUniversalServerAdmins</STRONG> " ist und über Vollzugriffsberechtigungen (also lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den lync Server 2013-Dateispeicher verwenden (Dies bedeutet, dass der Topologie-Generator die erforderlichen freigegebenen Zugriffssteuerungslisten konfigurieren kann ( DACLs) oder ein Konto mit entsprechenden Rechten.

    
    </div>

2.  Starten Sie den Topologie-Generator.

3.  Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem Sie die Archivierung bereitgestellt haben und klicken Sie dann auf den Namen des Front-End-Pools, in dem Sie die Datenbankoptionen ändern möchten.

4.  Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.

5.  Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.

6.  Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.

7.  Führen Sie im Dialogfeld **Archivierung** die folgenden Schritte aus:
    
      - Wenn Sie zu einem anderen SQL Server-Speicher wechseln möchten, gehen Sie unter **SQL Server-Speicher für Archivierung** im Dropdown-Listenfeld wie folgt vor:
        
          - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
        
          - Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu** und gehen dann im Dialogfeld **Neuen SQL Server-Speicher definieren** wie folgt vor:
            
              - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
            
              - Wenn Sie einen neuen SQL Server-Speicher angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** die folgenden Aktionen aus:
                
                  - Geben Sie im **SQL Server-FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
                
                  - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
                
                  - Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in der Spiegelungs** Beziehung, und geben Sie dann in **Spiegelungs-Portnummer**die Portnummer an.
    
      - Wenn Sie einen SQL Server-Speicher zur Spiegelung hinzufügen oder für die SQL Server-Speicherspiegelung zu einem anderen vorhandenen SQL Server-Speicher wechseln möchten, wählen Sie **SQL Server-Speicherspiegelung aktivieren** aus und gehen Sie dann wie folgt vor:
        
          - Wenn Sie einen vorhandenen SQL Server-Speicher für die Spiegelung verwenden möchten, klicken Sie im Dropdown-Listenfeld **SQL Server Store Mirror-Archivierung** auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten.
        
          - Wenn Sie einen neuen SQL Server-Speicher für die Spiegelung angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** eine der folgenden Aktionen aus:
            
            1.  Geben Sie im **SQL Server-FQDN**den FQDN des SQL Server an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
            
            2.  Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
            
            3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in der Spiegelungs** Beziehung, und geben Sie dann in **Spiegelungs-Portnummer**die Portnummer an.
        
          - Wenn Sie die SQL Server-Spiegelung aktivieren und einen SQL Server-Spiegelungs Zeugen (eine dritte, separate SQL Server-Instanz, die den Zustand des primären SQL Server-Servers und der Spiegelungs Instanzen erkennen kann) hinzufügen oder ändern möchten, aktivieren Sie das Kontrollkästchen **SQL Server-Spiegelungs Zeuge zum Aktivieren des automatischen Failovers verwenden** , und führen Sie dann eine der folgenden Aktionen aus:
            
            1.  Geben Sie im **SQL Server-FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungs Zeugen erstellen möchten.
            
            2.  Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
            
            3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in der Spiegelungs** Beziehung, und geben Sie dann in **Spiegelungs-Portnummer**die Portnummer an.
    
      - Wenn Sie zur Microsoft Exchange-Integration wechseln möchten, um Archivierungsdaten und-Dateien auf Exchange 2013-Servern zu speichern (wenn alle Benutzer in Ihrer Bereitstellung auf Ihren Exchange 2013-Servern verwaltet werden), löschen Sie alle Informationen für die Archivierung von Datenbanken.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie lync-Benutzer haben, die nicht auf Exchange 2013-Servern gehostet werden, löschen Sie die SQL Server-Informationsspeicherinformationen nicht.

    
    </div>

8.  Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Änderungen, die Sie im Topologie-Generator vornehmen, werden erst wirksam, nachdem Sie die neue Topologie veröffentlicht haben. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

