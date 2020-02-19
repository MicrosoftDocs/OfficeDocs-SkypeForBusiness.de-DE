---
title: 'Lync Server 2013: Hinzufügen von Archivierungsdatenbanken zur lync Server 2013-Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bed8e9fa8b15bd4e9e7fb1f72b102ed223edd9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Hinzufügen von Archivierungsdatenbanken zur lync Server 2013 Topologie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-10_

Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können. Die Informationen in diesem Thema erläutern, wie Sie mithilfe des Topologie-Generators der vorhandenen Topologie Archivierung hinzufügen.

<div>


> [!NOTE]  
> Wenn Sie Microsoft Exchange Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange 2013 Servern für alle Benutzer in Ihrer Bereitstellung verwenden möchten, geben Sie die <STRONG>Archivierungs SQL Server Store</STRONG> oder <STRONG>Use SQL Server Speicher Spiegelungs</STRONG> Informationen nicht an.



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>So fügen Sie Ihrer Topologie Archivierungsdatenbankunterstützung hinzu

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 läuft oder auf dem die lync Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit gleichwertigen Benutzerrechten).
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die erforderlich ist, um der Topologie einen Server hinzuzufügen. Sie müssen ein Konto verwenden, das Mitglied der Gruppe " <STRONG>Domänen-Admins</STRONG> " und der Gruppe " <STRONG>RTCUniversalServerAdmins</STRONG> " ist und das über die Berechtigung "Vollzugriff" (lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den lync Server 2013 Dateispeicher verwenden (damit der Topologie-Generator die erforderliche DACL (Discretionary Access Control List) konfigurieren kann. oder ein Konto mit gleichwertigen Rechten.

    
    </div>

2.  Starten Sie den Topologie-Generator.

3.  Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem die Archivierung bereitgestellt werden soll, und klicken Sie dann auf den Namen des entsprechenden Front-End-Pools.

4.  Klicken Sie im Menü **Aktion** auf **Eigenschaften bearbeiten**.

5.  Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.

6.  Führen Sie einen Bildlauf nach unten zu **Archivierung** durch.

7.  Aktivieren Sie das Kontrollkästchen **Archivierung**.

8.  Führen Sie unter **Archivierung SQL Server Speicher** einen der folgenden Schritte aus:
    
      - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten. Wenn alle Ihre Benutzer in Microsoft Exchange Server 2013 oder höher verwaltet werden, können Sie lync Communications für alle Ihre Benutzer in Exchange archivieren. In diesem Fall müssen Sie SQL Server Archivierungsspeicher nicht konfigurieren.
    
      - Um einen neuen SQL Server Speicher anzugeben, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** folgende Schritte aus:
        
          - Geben Sie in **SQL Server FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
        
          - Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
        
          - Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in einer Spiegelungs** Beziehung, und geben Sie dann unter **Spiegel Portnummer**die Portnummer an.

9.  Wenn Sie SQL Server Speicherspiegelung verwenden möchten, wählen Sie **SQL Server Speicherspiegelung aktivieren**aus, und gehen Sie dann wie folgt vor:
    
      - Wenn Sie einen vorhandenen SQL Server Speicher für die Spiegelung verwenden möchten, klicken Sie im Dropdown-Listenfeld **Archivierung SQL Server Speicher Spiegel** auf den Namen des SQL Server Speichers, den Sie für die Spiegelung verwenden möchten.
    
      - Wenn Sie einen neuen SQL Server Speicher für die Spiegelung angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** einen der folgenden Schritte aus:
        
        1.  Geben Sie in **SQL Server FQDN**den FQDN des SQL Server an, für den Sie den neuen SQL Server Speicher erstellen möchten.
        
        2.  Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
        
        3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in einer Spiegelungs** Beziehung, und geben Sie dann unter **Spiegel Portnummer**die Portnummer an.
    
      - Wenn Sie SQL Server Spiegelung aktivieren und einen SQL Server-Spiegelungs Zeugen (eine dritte, separate SQL Server Instanz, die die Integrität des primären SQL Server Servers und der Spiegelungs Instanzen erkennen kann) einschließen möchten, aktivieren Sie das Kontrollkästchen **verwenden Sie SQL Server Spiegelungs Zeugen zum Aktivieren des automatischen Failovers** , und führen Sie dann eine der folgenden Aktionen aus:
        
        1.  Geben Sie in **SQL Server FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungs Zeugen erstellen möchten.
        
        2.  Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
        
        3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in einer Spiegelungs** Beziehung, und geben Sie dann unter **Spiegel Portnummer**die Portnummer an.

10. Klicken Sie zum Speichern der Konfiguration auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

