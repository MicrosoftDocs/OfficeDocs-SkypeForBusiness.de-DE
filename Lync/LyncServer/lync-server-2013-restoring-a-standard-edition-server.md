---
title: 'Lync Server 2013: Wiederherstellen eines Standard Edition-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 101cf0cb2fc4073e2b79aa008187465f84d2d439
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Wiederherstellen eines Standard Edition-Servers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Wenn ein Standard Edition-Server, auf dem der zentrale Verwaltungsspeicher nicht gehostet wird, fehlschlägt, führen Sie die Verfahren in diesem Abschnitt aus. Wenn der zentrale Verwaltungsspeicher fehlschlägt, lesen Sie [Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)wird.

<div>


> [!TIP]  
> Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>So stellen Sie einen Standard Edition-Server wieder her

1.  Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.
    
    <div>
    

    > [!NOTE]  
    > Befolgen Sie die Server Bereitstellungsverfahren Ihrer Organisation, um diesen Schritt ausführen zu können.

    
    </div>

2.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe und der lokalen Gruppe Administratoren ist, bei dem Server an, den Sie wiederherstellen möchten.

3.  Stellen Sie den Dateispeicher wieder her, indem Sie den entsprechenden Dateispeicher aus $Backup in den Dateispeicher Speicherort auf dem Server kopieren und den Ordner freigeben.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Pfad und Dateinamen für den wiederhergestellten Dateispeicher sollten exakt mit dem gesicherten Dateispeicher identisch sein, damit die Komponenten, die die Dateien verwenden, darauf zugreifen können.

    
    </div>

4.  Ausführen des Topologie-Generators:
    
    1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.
    
    2.  Klicken Sie auf **Topologie aus vorhandener Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.
    
    3.  Wählen Sie die Topologie aus, und klicken Sie dann auf **Speichern**. Klicken Sie auf **Ja** , um die Auswahl zu bestätigen.

5.  Navigieren Sie zum lync Server-Installationsordner oder-Medium, und starten Sie dann den lync Server- \\Bereitstellungs-Assistenten unter Setup\\amd64\\Setup. exe. Verwenden Sie den lync Server-Bereitstellungs-Assistenten, um folgende Aktionen auszuführen:
    
    1.  Führen Sie **Schritt 1: Installieren des lokalen Konfigurationsspeichers** aus, um die lokalen Konfigurationsdateien zu installieren.
    
    2.  Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten** aus, um die lync Server-Serverrollen zu installieren.
    
    3.  Führen Sie **Schritt 3 aus: anfordern, installieren oder Zuweisen von Zertifikaten** zum Zuweisen der Zertifikate.
    
    4.  Führen Sie **Schritt 4: Dienste starten** aus, um Dienste auf dem Server zu starten.
    
    Details zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation für die Serverrolle, die Sie wiederherstellen.

6.  Wiederherstellen von Benutzerdaten durch Ausführen der folgenden Schritte:
    
    1.  Kopieren Sie ExportedUserData. zip aus\\ $Backup in ein lokales Verzeichnis.
    
    2.  Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden. Geben Sie dazu Folgendes ein:
        
            Stop-CsWindowsService
    
    3.  Geben Sie zum Wiederherstellen der Benutzerdaten in der Befehlszeile Folgendes ein:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Beispiel:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Starten Sie lync Services neu, indem Sie Folgendes eingeben:
        
            Start-CsWindowsService

7.  Wenn Sie die Reaktionsgruppe auf diesem Standard Edition-Server bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Einstellungen für die Reaktionsgruppe in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

8.  Wenn Sie den beständigen Chat auf diesem Standard Edition-Server bereitgestellt haben, stellen Sie die persistent Chat-Datenbank (MGC. mdf) wieder her.
    
    Wenn Sie die Datenbank für persistente Chats mithilfe der SQL Server-Sicherung gesichert haben, verwenden Sie die SQL Server-Wiederherstellungsverfahren, um Sie wiederherzustellen.
    
    Wenn Sie das Cmdlet Export-CsPersistentChatData verwendet haben, um es zu sichern, können Sie es mithilfe der Import-CsPersistentChatData wiederherstellen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

