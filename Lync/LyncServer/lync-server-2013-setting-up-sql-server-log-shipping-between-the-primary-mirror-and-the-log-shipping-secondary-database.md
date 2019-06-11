---
title: 'Lync Server 2013: Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank des Protokollversands'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a>Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank des Protokollversands in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Führen Sie die folgenden Schritte aus, damit der Protokollversand fortgesetzt wird, wenn die primäre Datenbank für beständige Chats auf die Spiegeldatenbank übertragen wird.

1.  Manuelles Failover der primären persistent-Chat-Datenbank auf die Spiegelung. Dies erfolgt mithilfe der lync Server-Verwaltungsshell und des **Invoke-CsDatabaseFailover-** Cmdlets. Ausführliche Informationen finden Sie unter "Verwenden von Cmdlets für die lync Server-Verwaltungsshell" unter [Bereitstellen der SQL-Spiegelung für den Back-End-Server mit einer höheren Verfügbarkeit in lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

2.  Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der primären persistent Chat Server-Spiegelungs Instanz her.

3.  Stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.

4.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.

5.  Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.

6.  Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.

7.  Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.

8.  Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zu der Freigabe ein, die Sie für den Transaktionsprotokoll-Sicherungsordner erstellt haben.

9.  Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben.

    
    </div>

10. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.

11. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.
    
    <div>
    

    > [!IMPORTANT]  
    > Verwenden Sie die gleichen Einstellungen, die Sie auch für die primäre Datenbank verwendet haben.

    
    </div>

12. Wählen Sie unter **Komprimierung** den Eintrag **Standardservereinstellung verwenden** aus und klicken Sie auf **OK**.

13. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.

14. Klicken Sie auf **Verbinden** und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.

15. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.

16. Wählen Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Nein, die sekundäre Datenbank ist initialisiert** aus.

17. Geben Sie auf der Registerkarte **Dateien kopieren** unter **Zielordner für kopierte Dateien** den Pfad des Ordners ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen, und klicken Sie auf **OK**. Dieser Ordner befindet sich in der Regel auf dem sekundären Server.

18. Öffnen Sie die Dropdownliste **Skript für Konfiguration erstellen** und wählen Sie **Skript für Konfiguration in Fenster 'Neue Abfrage' schreiben** aus.

19. Klicken Sie im neuen Abfragefenster unter **Datenbankeigenschaften** auf **OK**, um mit der Konfiguration zu beginnen.

20. Wählen Sie die erste Hälfte der Abfrage aus, und führen Sie Sie aus (siehe Schritt 18) bis zur \* \* \* \* \* \* Zeile:--Ende: Skript, das \* \* \* \* \* \*bei primär ausgeführt werden soll:.
    
    <div>
    

    > [!IMPORTANT]  
    > Das manuelle Ausführen dieses Skripts ist erforderlich, da SQL Server Management Studio mehrere primäre Datenbanken in einer SQL Server-Protokollversandkonfiguration nicht unterstützt.

    
    </div>

21. Wählen Sie **Abbrechen** aus, um das Konfigurationsfenster für den Protokolldateiversand zu schließen und ein funktionierendes Setup zu erstellen, das den Protokolldateiversand für die primäre und für die gespiegelte Datenbank (bei einem Failover) ordnungsgemäß implementiert. 

22. Manuelles Zurücksetzen der primären beständigen Chat Datenbank auf das primäre. Dies erfolgt mithilfe der lync Server-Verwaltungsshell und des Cmdlets **Invoke-CsDatabaseFailover** . Ausführliche Informationen finden Sie unter "Verwenden von Cmdlets für die lync Server-Verwaltungsshell" unter [Bereitstellen der SQL-Spiegelung für den Back-End-Server mit einer höheren Verfügbarkeit in lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

