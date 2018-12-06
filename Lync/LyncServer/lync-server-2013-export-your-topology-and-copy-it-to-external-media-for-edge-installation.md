---
title: 'Lync Server 2013: Exportieren der Topologie und Kopieren auf externe Medien zur Edgeinstallation'
TOCTitle: Exportieren der Topologie und Kopieren auf externe Medien zur Edgeinstallation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398983(v=OCS.15)
ms:contentKeyID: 49295640
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportieren der Lync Server 2013-Topologie und Kopieren auf externe Medien zur Edgeinstallation

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Nachdem Sie Ihre Topologie veröffentlicht haben, benötigt der Lync Server-Bereitstellungs-Assistent Zugriff auf die Dateien im zentralen Verwaltungsspeicher, um den Bereitstellungsprozess auf dem Server zu starten. Im internen Netzwerk sind die Daten direkt auf den Servern verfügbar, jedoch haben Edgeserver, die sich nicht in der internen Domäne befinden, keinen Zugriff auf die Daten. Um die Daten der Topologiekonfiguration für eine Edgeserverbereitstellung verfügbar zu machen, müssen Sie die Topologiedaten in eine Datei exportieren und diese auf einen externen Datenträger kopieren (dies kann z. B. ein USB-Laufwerk oder eine Netzwerkfreigabe sein, das bzw. die auf dem Edgeserver verfügbar ist), bevor Sie den Lync Server-Bereitstellungs-Assistenten auf dem Edgeserver ausführen. Verwenden Sie das folgende Verfahren, um die Daten der Topologiekonfiguration für den bereitzustellenden Edgeserver verfügbar zu machen.


> [!NOTE]
> Nachdem Sie Lync Server 2013 auf einem Edgeserver installiert haben, können Sie den Edgeserver unter Verwendung der Verwaltungstools im internen Netzwerk verwalten. So wird die Konfiguration automatisch auf jeden bereitgestellten Edgeserver repliziert. Die einzigen Aufgaben, die auf dem Edgeserver ausgeführt werden müssen, sind das Zuweisen und Installieren von Zertifikaten sowie das Beenden und Starten von Diensten.



## So stellen Sie Ihre Topologiedaten mithilfe der Lync Server-Verwaltungsshell auf einem Edgeserver zur Verfügung

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie in der Lync Server-Verwaltungsshell das folgende Cmdlet aus:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Kopieren Sie die exportierte Datei auf einen externen Datenträger (z. B. auf ein USB-Laufwerk oder eine Netzwerkfreigabe, das bzw. die während der Bereitstellung für den Edgeserver verfügbar ist).

