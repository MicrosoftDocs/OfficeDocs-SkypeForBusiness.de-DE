---
title: 'Lync Server 2013: Ausführen eines Failbacks für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Ausführen eines Failbacks für den Server für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

In diesem Verfahren werden die erforderlichen Schritte zum Wiederherstellen nach einem Server Fehler des beständigen Chats und zum Wiederherstellen von Vorgängen aus dem primären Rechenzentrum erläutert.

Beim Server Ausfall des beständigen Chats leidet das primäre Rechenzentrum unter einem vollständigen Ausfall, und die primäre und die Spiegeldatenbank werden nicht mehr zur Verfügung gestellt. Für das primäre Rechenzentrum erfolgt ein Failover auf den Sicherungsserver.

Wenn das primäre Rechenzentrum wieder verfügbar ist und die Server wiederhergestellt sind, wird anhand der folgenden Verfahrensweise der normale Betrieb wieder aufgenommen. Bei diesem Verfahren wird davon ausgegangen, dass das primäre Rechenzentrum vom Totalausfall wiederhergestellt wurde und dass die MGC-Datenbank und die mgccomp-Datenbank mithilfe des Topologie-Generators neu erstellt und neu installiert wurden.

Bei dem Verfahren wird auch davon ausgegangen, dass während des Failovers keine neuen Spiegelungs-und Sicherungsserver bereitgestellt wurden und dass der einzige bereitgestellte Server der Sicherungsserver und sein Spiegelserver ist, wie unter [fehlerhafte Chat Server in lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md)definiert.

Mit den folgenden Schritten soll die Konfiguration so wiederhergestellt werden, wie sie vor dem Ausfall vorlag, der zu dem Failover vom primären Server auf den Sicherungsserver geführt hat.

<div>

## <a name="to-fail-back-persistent-chat-server"></a>So führen Sie einen Ausfall des beständigen Chat Servers aus

1.  Löschen Sie alle Server aus der Active Server-Liste des beständigen `Set-CsPersistentChatActiveServer` Chat Servers mithilfe des Cmdlets aus der lync Server-Verwaltungsshell. Dadurch wird verhindert, dass alle beständigen Chat Server während des Failback eine Verbindung mit der MGC-Datenbank und der mgccomp-Datenbank herstellen.
    
    <div>
    

    > [!IMPORTANT]  
    > Der SQL Server-Agent auf dem Back-End-Server des sekundären beständigen Chat Servers sollte unter einem privilegierten Konto ausgeführt werden. Dieses Konto muss insbesondere über die folgenden Berechtigungen verfügen: 
    > <UL>
    > <LI>
    > <P>Lesezugriff auf die Netzwerkfreigabe, in der Sicherungen abgelegt werden sollen</P>
    > <LI>
    > <P>Schreibzugriff auf das lokale Verzeichnis, in das die Sicherungen kopiert werden sollen</P></LI></UL>

    
    </div>

2.  Deaktivieren Sie die Spiegelung für die mgc-Sicherungsdatenbank:
    
    1.  Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Sicherungs MGC-Instanz her.
    
    2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Spiegeln**.
    
    3.  Klicken Sie auf **Spiegelung entfernen**.
    
    4.  Klicken Sie anschließend auf **OK**.
    
    5.  Führen Sie die gleichen Schritte mit der mgccomp-Datenbank durch.

3.  Sichern Sie die mgc-Datenbank, damit sie in der neuen primären Datenbank wiederhergestellt werden kann:
    
    1.  Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Sicherungs MGC-Instanz her.
    
    2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Sichern**. Das Dialogfeld **Datenbank sichern** wird angezeigt.
    
    3.  Wählen Sie unter **Sicherungstyp** die Option **Vollständig** aus.
    
    4.  Klicken Sie unter **Sicherungskomponente** auf **Datenbank**.
    
    5.  Akzeptieren Sie den Standardnamen für den Sicherungssatz, der in **Name** vorgeschlagen wird, oder geben Sie einen anderen Namen ein.
    
    6.  * \<Optional\> * Geben Sie im Feld **Beschreibung**eine Beschreibung für den Sicherungssatz ein.
    
    7.  Entfernen Sie den standardmäßigen Sicherungsspeicherort aus der Zielliste.
    
    8.  Fügen Sie der Liste eine Datei mit dem Pfad zu dem Freigabespeicherort ein, den Sie für Protokollversand eingerichtet haben. Dieser Pfad ist für die primäre und die Sicherungsdatenbank verfügbar.
    
    9.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen und mit dem Sicherungsvorgang zu beginnen.

4.  Stellen Sie die primäre Datenbank unter Verwendung der im vorherigen Schritt erstellten Sicherungsdatenbank wieder her.
    
    1.  Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der primären MGC-Instanz her.
    
    2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, zeigen Sie auf **Wiederherstellen** und klicken Sie dann auf **Datenbank**. Das Dialogfeld **Datenbank wiederherstellen** wird angezeigt.
    
    3.  Wählen Sie **Von Medium** aus.
    
    4.  Klicken Sie auf die Schaltfläche zum Durchsuchen. Das Dialogfeld **Sicherung angeben** wird geöffnet. Wählen Sie in **Sicherungsmedium** die Option **Datei** aus. Klicken Sie auf **Hinzufügen**, wählen Sie die Sicherungsdatei aus, die Sie in Schritt 3 erstellt haben, und klicken Sie dann auf **OK**.
    
    5.  Wählen Sie in **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die Sicherung aus.
    
    6.  Klicken Sie im Bereich **Seite auswählen** auf **Optionen**.
    
    7.  Aktivieren Sie unter **Wiederherstellungsoptionen** die Option **Vorhandene Datenbank überschreiben**.
    
    8.  Aktivieren Sie in **Wiederherstellungsstatus** die Option **Datenbank betriebsbereit belassen**.
    
    9.  Klicken Sie auf **OK**, um mit dem Wiederherstellungsvorgang zu beginnen.

5.  Konfigurieren Sie den SQL Server-Protokollversand für die primäre Datenbank. Führen Sie die Verfahren unter Konfigurieren des beständigen [Chat Servers für die Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) aus, um den Protokollversand für die primäre MGC-Datenbank festzulegen.

6.  Setzen Sie die aktiven Server für den beständigen Chat Server. Verwenden Sie in der lync Server-Verwaltungsshell das Cmdlet " **Satz-CsPersistentChatActiveServer** ", um die Liste der aktiven Server einzurichten.
    
    <div>
    

    > [!IMPORTANT]  
    > Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt.

    
    </div>

Das Wiederherstellen des Pools in seinem normalen Zustand führt den folgenden Windows PowerShell-Befehl aus:

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

