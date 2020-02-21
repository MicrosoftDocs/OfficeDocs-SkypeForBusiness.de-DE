---
title: 'Lync Server 2013: Wiederherstellen einer Standard Edition-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77c49b7d1b02fc2d1cb41efd3fd68213fa8a0dfb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Wiederherstellen eines Standard Edition-Servers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Wenn ein Standard Edition-Server, auf dem der zentrale Verwaltungsspeicher nicht gehostet wird, fehlerhaft ist, führen Sie die Verfahren in diesem Abschnitt aus. Wenn der zentrale Verwaltungsspeicher fehlschlägt, finden Sie weitere Informationen unter [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).

<div>


> [!TIP]  
> Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht. Am besten erstellen Sie die Abbildkopie, nachdem Sie das Betriebssystem und SQL Server installiert und die Zertifikate wiederhergestellt oder erneut registriert haben.



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>So stellen Sie einen Standard Edition-Server wieder her

1.  Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her oder registrieren Sie Sie erneut.
    
    <div>
    

    > [!NOTE]  
    > Gehen Sie nach den in Ihrer Organisation gültigen Verfahren für die Serverbereitstellung vor, um diesen Schritt durchzuführen.

    
    </div>

2.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins und der lokalen Administratoren ist, bei dem Server an, den Sie wiederherstellen möchten.

3.  Stellen Sie die Dateispeicher wieder her, indem Sie den entsprechenden Dateispeicher von $Backup an den Dateispeicher Speicherort auf dem Server kopieren und den Ordner freigeben.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Pfad und der Dateiname für das wiederhergestellte Dateispeicher sollten genau mit dem gesicherten Dateispeicher identisch sein, damit Komponenten, die die Dateien verwenden, darauf zugreifen können.

    
    </div>

4.  Ausführen des Topologie-Generators:
    
    1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.
    
    2.  Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.
    
    3.  Wählen Sie die Topologie aus, und klicken Sie auf **Speichern**. Klicken Sie auf **Ja**, um die Auswahl zu bestätigen.

5.  Navigieren Sie zum Installationsordner für lync Server oder Medien, und starten Sie dann den lync Server-Bereitstellungs\\-\\Assistenten unter \\Setup amd64 Setup. exe. Verwenden Sie den lync Server-Bereitstellungs-Assistenten, um folgende Aktionen auszuführen:
    
    1.  Führen Sie **Schritt 1: Lokalen Konfigurationsspeicher installieren** aus, um die lokalen Konfigurationsdateien zu installieren.
    
    2.  Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server Komponenten** aus, um die lync Server-Server Rollen zu installieren.
    
    3.  Führen Sie **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** aus, um die Zertifikate zuzuweisen.
    
    4.  Führen Sie **Schritt 4: Dienste starten** aus, um die Dienste auf dem Server zu starten.
    
    Ausführliche Informationen über die Ausführung des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation zu der Serverrolle, die Sie wiederherstellen.

6.  Stellen Sie Benutzerdaten wieder her, indem Sie folgende Schritte ausführen:
    
    1.  Kopieren Sie ExportedUserData. zip aus\\ $Backup in ein lokales Verzeichnis.
    
    2.  Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden. Geben Sie dazu Folgendes ein:
        
            Stop-CsWindowsService
    
    3.  Geben Sie in die Befehlszeile Folgendes ein, um die Benutzerdaten wiederherzustellen:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Beispiel:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Starten Sie lync Services neu, indem Sie Folgendes eingeben:
        
            Start-CsWindowsService

7.  Wenn Sie die Reaktionsgruppe in diesem Standard Edition-Server bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Reaktionsgruppeneinstellungen in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

8.  Wenn Sie den beständigen Chat in diesem Standard Edition-Server bereitgestellt haben, stellen Sie die Datenbank für beständigen Chat (MGC. mdf) wieder her.
    
    Wenn Sie SQL Server Sicherung zum Sichern der Datenbank für beständigen Chat verwendet haben, verwenden Sie SQL Server Wiederherstellungsverfahren, um Sie wiederherzustellen.
    
    Wenn Sie das Cmdlet Export-CsPersistentChatData verwendet haben, verwenden Sie das Import-CsPersistentChatData, um es wiederherzustellen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

