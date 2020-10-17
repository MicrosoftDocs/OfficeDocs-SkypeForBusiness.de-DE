---
title: 'Lync Server 2013: Ändern von Archivierungsdatenbank Optionen'
description: 'Lync Server 2013: Ändern von Archivierungsdatenbank Optionen.'
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
ms.openlocfilehash: 7a3751be63e17688ad9258b9773a1a5397b67952
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543581"
---
# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Ändern von Archivierungsdatenbank Optionen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Wenn Sie die Archivierung mithilfe SQL Server Speichers für Archivierungsspeicher für alle Ihre Benutzer bereitstellen, können Sie die folgenden Änderungen an der Datenbankspeicherung vornehmen:

  - Verwenden Sie für die Archivierungs Speicherung eine andere SQL Server Datenbank. Dies umfasst die primäre Archivierungsdatenbank und alle Datenbanken, die Sie für die SQL Server Spiegelung verwenden.

  - Wechseln Sie zu Microsoft Exchange Integration, um Archivierungsdaten und-Dateien auf Exchange 2013 Servern zu speichern. Wenn alle Benutzer auf Ihren Exchange 2013 Servern verwaltet werden und Sie Microsoft Exchange Speicher für alle Benutzer in Ihrer Bereitstellung verwenden möchten, sollten Sie die SQL Server Store-Datenbanken aus Ihrer Topologie entfernen.

Um eine dieser Änderungen vornehmen zu können, müssen Sie den Topologie-Generator ausführen, die Änderungen vornehmen und die Topologie dann erneut veröffentlichen. Sie können den Topologie-Generator verwenden, um dies zu tun. Geben Sie keine **Archivierungs SQL Server speichern** oder **Aktivieren Sie SQL Server Speicher Spiegelungs** Informationen, es sei denn, Sie verfügen über lync-Benutzer, die nicht auf Exchange 2013 Servern verwaltet werden.

<div>

## <a name="to-change-your-archiving-database-option"></a>So ändern Sie die Archivierungsdatenbankoption

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 läuft oder auf dem die lync Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit gleichwertigen Benutzerrechten).
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die zum Hinzufügen einer Komponente zur Topologie erforderlich ist. Sie müssen ein Konto verwenden, das Mitglied der Gruppe "Domänen- <STRONG>Admins</STRONG> " und der <STRONG>RTCUniversalServerAdmins</STRONG> -Gruppe ist und das über die Berechtigung "Vollzugriff" (lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den lync Server 2013 Dateispeicher verwenden (damit der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control Lists) oder ein Konto mit gleichwertigen Rechten konfigurieren kann

    
    </div>

2.  Starten Sie den Topologie-Generator.

3.  Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem Sie die Archivierung bereitgestellt haben, und klicken Sie dann auf den Namen des Front-End-Pools, in dem Sie die Datenbankoptionen ändern möchten.

4.  Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.

5.  Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.

6.  Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.

7.  Führen Sie im Dialogfeld **Archivierung** die folgenden Schritte aus:
    
      - Wenn Sie zu einem anderen SQL Server-Speicher wechseln möchten, gehen Sie unter **SQL Server-Speicher für Archivierung** im Dropdown-Listenfeld wie folgt vor:
        
          - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
        
          - Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu** und gehen dann im Dialogfeld **Neuen SQL Server-Speicher definieren** wie folgt vor:
            
              - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
            
              - Um einen neuen SQL Server Speicher anzugeben, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** folgende Schritte aus:
                
                  - Geben Sie in **SQL Server FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
                
                  - Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
                
                  - Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in einer Spiegelungs** Beziehung, und geben Sie dann unter **Spiegel Portnummer**die Portnummer an.
    
      - Wenn Sie einen SQL Server-Speicher zur Spiegelung hinzufügen oder für die SQL Server-Speicherspiegelung zu einem anderen vorhandenen SQL Server-Speicher wechseln möchten, wählen Sie **SQL Server-Speicherspiegelung aktivieren** aus, und gehen Sie dann wie folgt vor:
        
          - Wenn Sie einen vorhandenen SQL Server Speicher für die Spiegelung verwenden möchten, klicken Sie im Dropdown-Listenfeld **Archivierung SQL Server Speicher Spiegel** auf den Namen des SQL Server Speichers, den Sie für die Spiegelung verwenden möchten.
        
          - Wenn Sie einen neuen SQL Server Speicher für die Spiegelung angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** einen der folgenden Schritte aus:
            
            1.  Geben Sie in **SQL Server FQDN**den FQDN des SQL Server an, für den Sie den neuen SQL Server Speicher erstellen möchten.
            
            2.  Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
            
            3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in einer Spiegelungs** Beziehung, und geben Sie dann unter **Spiegel Portnummer**die Portnummer an.
        
          - Wenn Sie SQL Server Spiegelung aktivieren und einen SQL Server-Spiegelungs Zeugen (eine dritte separate SQL Server Instanz, die die Integrität des primären SQL Server Servers und der Spiegelungs Instanzen erkennen kann) hinzufügen oder ändern möchten, aktivieren Sie das Kontrollkästchen **verwenden Sie SQL Server Spiegelungs Zeugen zum Aktivieren des automatischen Failovers** , und führen Sie eine der folgenden Aktionen aus:
            
            1.  Geben Sie in **SQL Server FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungs Zeugen erstellen möchten.
            
            2.  Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
            
            3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in einer Spiegelungs** Beziehung, und geben Sie dann unter **Spiegel Portnummer**die Portnummer an.
    
      - Wenn Sie zur Microsoft Exchange Integration wechseln möchten, um Archivierungsdaten und-Dateien auf Exchange 2013 Servern zu speichern (wenn alle Benutzer in Ihrer Bereitstellung auf Ihren Exchange 2013 Servern verwaltet werden), löschen Sie alle Informationen für Archivierungsdatenbanken.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie lync-Benutzer haben, die nicht auf Exchange 2013 Servern verwaltet werden, löschen Sie nicht die SQL Server Informationsspeicher.

    
    </div>

8.  Klicken Sie zum Speichern der Konfiguration auf **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Die im Topologie-Generator vorgenommenen Änderungen werden erst wirksam, wenn Sie die neue Topologie veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

