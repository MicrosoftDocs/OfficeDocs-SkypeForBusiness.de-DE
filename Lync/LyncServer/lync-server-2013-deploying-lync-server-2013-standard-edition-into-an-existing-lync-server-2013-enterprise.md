---
title: 'Lync Server 2013: Bereitstellen von Lync Server 2013 Standard Edition in einer vorhandenen Lync Server 2013 Enterprise-Bereitstellung'
TOCTitle: Bereitstellen von Lync Server 2013 Standard Edition in einer vorhandenen Lync Server 2013 Enterprise-Bereitstellung
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398112(v=OCS.15)
ms:contentKeyID: 49293055
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von Lync Server 2013 Standard Edition in einer vorhandenen Lync Server 2013 Enterprise-Bereitstellung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Die Bereitstellung eines Standard Edition-Servers in einer vorhandenen Enterprise Edition-Bereitstellung ähnelt der Bereitstellung zusätzlicher Serverrollen. Ein Standard Edition-Server kann an einem anderen Standort bereitgestellt werden, um die Benutzer an diesem Standort nicht über eine WAN (Wide Area Network)-Verbindung im Front-End-Pool, sondern stattdessen auf dem Standard Edition-Server zu verwalten. Die Verfahren zum Installieren des neuen Standorts und der Server an diesem Standort werden bereits in anderen Abschnitten der Dokumentation [Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md) beschrieben.

**So definieren Sie einen neuen Standort**

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **Lync Server 2013** und klicken Sie dann auf **Neuer zentraler Standort**.

3.  Geben Sie auf der Seite **Standort identifizieren** einen Namen für den Standort und optional eine Beschreibung ein.

4.  Führen Sie die erforderlichen Schritte zum Definieren der weiteren Komponenten der Standorttopologie aus. Ausführliche Informationen finden Sie unter [Definieren und Konfigurieren der Topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Veröffentlichen Sie die aktualisierte Topologie. Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Installieren Sie einen Standard Edition-Server und richten Sie ihn ein.
    
    > [!CAUTION]  
	> Wenn Sie über eine Bereitstellung mit nur einem Standard Edition-Server verfügen, haben Sie die Einrichtung mit dem Lync Server-Bereitstellungs-Assistenten unter Verwendung des Links <strong>Vorbereiten des ersten Standard Edition-Servers</strong> durchgeführt, um die anfänglichen Datenbankdateien auf dem neuen Standard Edition-Server zu installieren. Führen Sie dieses Verfahren <strong>nicht aus</strong>, wenn Sie einen Standard Edition-Server in einer vorhandenen Lync Server 2013-Bereitstellung installieren.

