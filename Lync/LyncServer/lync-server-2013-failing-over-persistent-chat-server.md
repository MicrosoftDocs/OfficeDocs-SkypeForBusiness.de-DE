---
title: 'Lync Server 2013: Ausführen eines Failovers für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 021b34cafd91397cc36da1dbc22f91b8665aea96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Ausführen eines Failovers für den Server für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Das Failover für beständigen Chat Server ist hauptsächlich ein manueller Prozess.

Das Failover-Verfahren basiert auf der Annahme, dass das sekundäre Rechenzentrum in Betrieb ist, aber die Server Dienste für beständigen Chat, bei denen sich die primäre Datenbank für beständigen Chat befindet, sind vollständig nicht verfügbar, einschließlich der folgenden:

  - Die primäre Datenbank des beständigen Chat Servers und die Spiegeldatenbank des beständigen Chat Servers sind nicht mehr vorhanden.

  - Der lync Server-Front-End-Server ist ausgefallen.

Das Verfahren basiert auf zwei grundlegenden Schritten:

  - Wiederherstellen der primären persistent Chat-Datenbank (MGC)

  - Einrichten der Spiegelung für die neue Primärdatenbank

Die beständige Chat-Kompatibilitätsdatenbank (mgccomp) ist nicht fehlerhaft. Die Inhalte dieser Datenbank sind flüchtig und werden gelöscht, wenn der Konformitätsadapter die Daten verarbeitet. Es liegt in ihrer Verantwortung als Administrator des beständigen Chats, die Adapter Ausgabe ordnungsgemäß zu verwalten, um Datenverluste zu vermeiden.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>So führen Sie einen Failover für beständigen Chat Server durch

1.  Entfernen Sie den Protokollversand aus der Datenbank des beständigen Chat Server-Sicherungs Protokolls.
    
    1.  Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Datenbankinstanz her, in der sich die Datenbank des beständigen Chat Server-Backup MGC befindet.
    
    2.  Öffnen Sie ein Abfragefenster zur Masterdatenbank.
    
    3.  Verwenden Sie den folgenden Befehl, um den Protokollversand zu verwerfen:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Kopieren Sie alle nicht kopierten Sicherungsdateien von der Sicherungsfreigabe in den Kopierzielordner des Sicherungsservers.

3.  Wenden Sie alle nicht angewendeten Sicherungen des Transaktionsprotokolls nacheinander auf die sekundäre Datenbank an. Ausführliche Informationen finden Sie unter "Vorgehensweise: Anwenden einer Transaktionsprotokollsicherung (Transact-SQL http://go.microsoft.com/fwlink/p/?linkid=247428)" unter.

4.  Stellen Sie die mgc-Sicherungsdatenbank online bereit. Führen Sie im Abfragefenster, das in Schritt 1b oben geöffnet wird, folgende Aufgaben aus:
    
    1.  Beenden Sie alle Verbindungen mit der mgc-Datenbank, falls vorhanden:
        
        1.  **exec SP\_who2** , um Verbindungen zur MGC-Datenbank zu identifizieren.
        
        2.  **Kill \<SPID\> ** , um diese Verbindungen zu beenden.
    
    2.  Stellen Sie die Datenbank online bereit:
        
        1.  **restore database mgc with recovery**.

5.  Verwenden Sie in der lync Server-Verwaltungsshell den Befehl **Satz-CsPersistentChatState-Identity "Service: ATL-CS-001.litwareinc.com" – PoolState FailedOver** , um ein Failover zur MGC-Sicherungsdatenbank durchführen zu können. Achten Sie darauf, den vollqualifizierten Domänennamen Ihres Pools für beständigen Chat durch „atl-cs-001.litwareinc.com“ zu ersetzen.
    
    Die mgc-Sicherungsdatenbank dient jetzt als Primärdatenbank.

6.  Verwenden Sie in der lync Server-Verwaltungsshell das Cmdlet " **install-CsMirrorDatabase** ", um eine Hochverfügbarkeits-Spiegelung für die Sicherungsdatenbank einzurichten, die jetzt als primäre Datenbank fungiert. Verwenden Sie die Sicherungsdatenbankinstanz als Primärdatenbank und die Instanz der Sicherungsspiegeldatenbank als Spiegelinstanz. Dies ist nicht dieselbe Spiegelung, die anfänglich beim Setup für die Primärdatenbank eingerichtet wurde. Ausführliche Informationen finden Sie im Abschnitt "Verwenden von lync Server-Verwaltungsshell-Cmdlets" unter [Bereitstellen der SQL-Spiegelung für den Back-End-Server mit einer höheren Verfügbarkeit in lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Setzen Sie die aktiven Server für den beständigen Chat Server. Verwenden Sie in der lync Server-Befehlsshell das Cmdlet " **Satz-CsPersistentChatActiveServer** ", um die Liste der aktiven Server einzurichten.
    
    <div>
    

    > [!IMPORTANT]  
    > Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt.

    
    </div>
    
    An diesem Punkt wird das Failover von der primären Datenbank des beständigen Chat Servers zur Datenbank des beständigen Chat Servers erfolgreich abgeschlossen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

