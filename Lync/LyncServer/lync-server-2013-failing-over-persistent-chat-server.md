---
title: 'Lync Server 2013: Fehler beim Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91c4d5092fc12ac374b57872b7cda2d6f88d9e33
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Failover des Servers für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

Das Failover für den Server für beständigen Chat dient hauptsächlich als manueller Prozess.

Das Failover-Verfahren basiert auf der Annahme, dass das sekundäre Rechenzentrum betriebsbereit ist, aber die Server Dienste für beständigen Chat, auf denen sich die primäre Datenbank für beständigen Chat befindet, sind vollständig nicht verfügbar, einschließlich der folgenden:

  - Die primäre Datenbank für beständigen Chat Server und die Spiegeldatenbank für beständigen Chat Server sind nicht verfügbar.

  - Lync Server Front-End-Server ist nicht aktiv.

Das Verfahren basiert auf zwei grundlegenden Schritten:

  - Wiederherstellen der primären Datenbank für beständigen Chat (MGC).

  - Einrichten der Spiegelung für die neue Primärdatenbank

Bei der beständigen Chat-Kompatibilitätsdatenbank (mgccomp) ist kein Failover ausgeführt. Die Inhalte dieser Datenbank sind flüchtig und werden gelöscht, wenn der Konformitätsadapter die Daten verarbeitet. Es liegt in ihrer Verantwortung als Administrator für beständigen Chat, die Adapter Ausgabe ordnungsgemäß zu verwalten, um Datenverluste zu vermeiden.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>So führen Sie einen Failover des Servers für beständigen Chat durch

1.  Entfernen Sie den Protokollversand aus der Datenbank für den Sicherungsprotokoll Versand des beständigen Chat Servers.
    
    1.  Stellen Sie mit SQL Server Management Studio eine Verbindung mit der Datenbankinstanz her, in der sich die Datenbank der persistent Chat Server-Sicherung MGC befindet.
    
    2.  Öffnen Sie ein Abfragefenster zur Masterdatenbank.
    
    3.  Verwenden Sie den folgenden Befehl, um den Protokollversand zu verwerfen:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Kopieren Sie alle nicht kopierten Sicherungsdateien von der Sicherungsfreigabe in den Kopierzielordner des Sicherungsservers.

3.  Wenden Sie alle nicht angewendeten Sicherungen des Transaktionsprotokolls nacheinander auf die sekundäre Datenbank an. Ausführliche Informationen finden Sie unter "Vorgehensweise: Anwenden einer Transaktionsprotokollsicherung (Transact-SQL https://go.microsoft.com/fwlink/p/?linkid=247428)" unter.

4.  Stellen Sie die mgc-Sicherungsdatenbank online bereit. Führen Sie im Abfragefenster, das in Schritt 1b oben geöffnet wird, folgende Aufgaben aus:
    
    1.  Beenden Sie alle Verbindungen mit der mgc-Datenbank, falls vorhanden:
        
        1.  **exec SP\_who2** , um Verbindungen zur MGC-Datenbank zu identifizieren.
        
        2.  **Kill \<SPID\> ** , um diese Verbindungen zu beenden.
    
    2.  Stellen Sie die Datenbank online bereit:
        
        1.  **Wiederherstellen der Daten Bank MGC mit Wiederherstellung**.

5.  Verwenden Sie in lync Server-Verwaltungsshell den Befehl **festlegen-cspersistentchatstate "-Identity" Service: ATL-CS-001.litwareinc.com "– PoolState FailedOver** , um ein Failover zur MGC-Sicherungsdatenbank durchführen zu können. Stellen Sie sicher, dass Sie den vollqualifizierten Domänennamen des Pools für beständigen Chat für ATL-CS-001.litwareinc.com ersetzen.
    
    Die mgc-Sicherungsdatenbank dient jetzt als Primärdatenbank.

6.  Verwenden Sie in lync Server-Verwaltungsshell das Cmdlet **install-CsMirrorDatabase** , um eine hoch Verfügbarkeits Spiegelung für die Sicherungsdatenbank einzurichten, die nun als primäre Datenbank dient. Verwenden Sie die Sicherungsdatenbankinstanz als Primärdatenbank und die Instanz der Sicherungsspiegeldatenbank als Spiegelinstanz. Dies ist nicht dieselbe Spiegelung, die anfänglich beim Setup für die Primärdatenbank eingerichtet wurde. Ausführliche Informationen finden Sie im Abschnitt "Verwenden von lync Server-Verwaltungsshell-Cmdlets" unter [Bereitstellen von SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Legen Sie den Server für beständigen Chat als aktive Server fest. Verwenden Sie in der lync Server-Befehlsshell das Cmdlet " **CsPersistentChatActiveServer** ", um die Liste der aktiven Server festzulegen.
    
    <div>
    

    > [!IMPORTANT]  
    > Alle aktiven Server müssen sich in demselben Datencenter wie die neue Primärdatenbank befinden oder in einem Datencenter, das über eine Datenbankverbindung mit geringer Wartezeit und hoher Bandbreite verfügt.

    
    </div>
    
    Zu diesem Zeitpunkt wird das Failover der primären Datenbank für beständigen Chat Server in die Datenbank für den persistent Chat Server erfolgreich abgeschlossen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

