---
title: 'Lync Server 2013: Verwalten von Ansagen während der Notfallwiederherstellung'
TOCTitle: Verwalten von Ansagen während der Notfallwiederherstellung
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49890929
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Ansagen während der Notfallwiederherstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Lync Server 2013 unterstützt Ansagen für Anrufe an nicht zugewiesene Nummern bei einem Ausfall. Die Wiederherstellung der Ansagefunktionalität bei einem Ausfall ist optional. Wenn Sie sich dafür entscheiden, Ansagen bei einem Ausfall wiederherzustellen, müssen Sie die Ansagekonfiguration im Sicherungspool erneut erstellen. In diesem Abschnitt wird die Vorgehensweise beschrieben, falls Sie Ansagen bei einer Notfallwiederherstellung wiederherstellen möchten.

Dieser Abschnitt gilt für nicht zugewiesene Nummernbereiche, die die Ansageanwendung verwenden. Für nicht zugewiesene Nummernbereiche, die die automatische Telefonzentrale von Exchange Unified Messaging (UM) verwenden, ist dieser Abschnitt nicht zutreffend.

## Vor einem Ausfall

Unabhängig davon, ob Sie Ansagen bei einem Ausfall verwenden möchten, sollten Sie separate Backups von allen angepassten Audiodateien erstellen, die Sie für die Ansageanwendung konfiguriert haben. Angepasste Ansagen werden nicht im Rahmen des Notfallwiederherstellungsprozesses von Lync Server gesichert. Wenn Sie keine separaten Backups der Dateien erstellen und die auf den Server oder in den Pool hochgeladenen Dateien beschädigt, infiziert oder gelöscht werden, sind die Dateien verloren.

Falls Sie nicht über Sicherungskopien von angepassten Audiodateien verfügen und die ursprünglichen Audiodateien nicht mehr verfügbar sind, finden Sie die Audiodateien, die Sie für eine Ansageanwendung konfiguriert haben, im Dateispeicher für den Server oder Pool, auf bzw. in den Sie die Dateien ursprünglich importiert haben. Sie können alle Audiodateien, die Sie für die Ansageanwendung konfiguriert haben, im Dateispeicher kopieren.

**So kopieren Sie Audiodateien aus dem Dateispeicher**

1.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Beispiel:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Dabei steht X-ApplicationServer-X für die Dienst-ID des Anwendungsservers des Pools (z. B. 1-ApplicationServer-1 ).


## Bei einem Ausfall

Wenn Sie die Ansageanwendung bei einem Ausfall verwenden möchten, müssen Sie die Ansagekonfiguration im Sicherungspool erneut erstellen, indem Sie die in diesem Abschnitt beschriebenen Schritte ausführen.


> [!NOTE]
> Es wird empfohlen, diese Schritte nach dem Failover auf den Sicherungspool auszuführen. Sobald Sie nämlich Schritt&nbsp;2 ausführen, wird der Sicherungspool zum Besitzer der nicht zugewiesenen Nummernbereiche.




> [!NOTE]
> Für Nummernbereiche, die eine Exchange UM-Rufnummer der automatischen Telefonzentrale verwenden, sind diese Schritte nicht erforderlich.



**So stellen Sie die Ansagekonfiguration im Sicherungspool wieder her**

1.  Führen Sie die folgenden Aktionen aus, um die Ansagen, die Sie im primären Pool erstellt haben, im Sicherungspool erneut zu erstellen:
    
    1.  Importieren Sie alle im primären Pool verwendeten Audiodateien im Sicherungspool, indem Sie das **Import-CsAnnouncementFile**-Cmdlet verwenden und den Sicherungspool für den Parent -Parameter angeben.
    
    2.  Erstellen Sie alle Ansagen erneut, indem Sie das **New-CsAnnouncement**-Cmdlet verwenden und den Sicherungspool für den Parent -Parameter angeben.
    

    > [!NOTE]
    > Ausführliche Informationen zum Erstellen von Ansagen im Sicherungspool mithilfe dieser Parameter finden Sie unter <A href="lync-server-2013-create-an-announcement.md">Erstellen einer Ansage in Lync Server 2013</A>.



2.  Nachdem Sie alle Ansagen im Sicherungspool erneut erstellt haben, leiten Sie alle nicht zugewiesenen Nummernbereiche, die Ansagen im primären Pool verwenden, an die erneut erstellten Ansagen im Sicherungspool um.
    
    Für jeden nicht zugewiesenen Nummernbereich, der eine Ansage im primären Pool verwendet, führen Sie folgenden Befehl aus:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

## Nach einem Ausfall

Wenn der primäre Pool nicht mehr verfügbar ist, müssen Sie die nicht zugewiesenen Nummernbereiche, die Sie für den Ausfall geändert haben, wieder an den primären Pool umleiten.


> [!NOTE]
> Für Nummernbereiche, die eine Exchange UM-Rufnummer der automatischen Telefonzentrale verwenden, sind diese Schritte nicht erforderlich.



**So stellen Sie Ankündigungen im primären Pool wieder her**

1.  Wenn Sie den primären Pool während der Wiederherstellung erneut erstellen mussten, müssen Sie die Ansagen im primären Pool erneut erstellen. Dazu importieren Sie die Audiodateien und erstellen Ankündigungen, so wie das beim Sicherungspool der Fall war, außer dass Sie den primären Pool für den Parent -Parameter angeben. Weitere Informationen hierzu finden Sie unter "Bei einem Ausfall" weiter oben in diesem Thema.

2.  Für jeden nicht zugewiesenen Nummernbereich, den Sie für den Ausfall geändert haben, führen Sie folgenden Befehl aus:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Entfernen Sie optional die Ansagen, die Sie im Sicherungspool erneut erstellt haben. Rufen Sie eine Liste der Ansagen für die Sicherungspool- Ansageanwendung ab. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Beispiel:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    Suchen Sie in der zurückgegebenen Liste die Ansagen, die Sie entfernen möchten, und kopieren Sie die GUIDs. Führen Sie für jede Ansage, die Sie entfernen möchten, Folgendes aus:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Beispiel:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


