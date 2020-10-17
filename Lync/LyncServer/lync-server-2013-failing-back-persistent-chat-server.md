---
title: 'Lync Server 2013: Fehler beim zurückhalten des Servers für beständigen Chat'
description: 'Lync Server 2013: Fehler beim zurückhalten des Servers für beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa36562b3892c0e22960677ffcba4b862e708c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567731"
---
# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Fehler beim wieder beständigen Chat Server in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

In diesem Verfahren werden die erforderlichen Schritte zum Wiederherstellen nach einem Server Ausfall für beständigen Chat und zum erneuten Einrichten von Vorgängen aus dem primären Rechenzentrum beschrieben.

Während des Server Ausfalls eines beständigen Chats leidet das primäre Rechenzentrum unter einem vollständigen Ausfall, und die primäre und die Spiegeldatenbank werden nicht mehr verfügbar sein. Für das primäre Rechenzentrum erfolgt ein Failover auf den Sicherungsserver.

Wenn das primäre Rechenzentrum wieder verfügbar ist und die Server wiederhergestellt sind, wird anhand der folgenden Verfahrensweise der normale Betrieb wieder aufgenommen. Bei dem Verfahren wird davon ausgegangen, dass das primäre Rechenzentrum aus dem Gesamtausfall wiederhergestellt wurde und dass die MGC-Datenbank und die mgccomp-Datenbank mithilfe des Topologie-Generators neu erstellt und neu installiert wurden.

Bei diesem Verfahren wird auch davon ausgegangen, dass während des Failovers kein neuer Spiegel-und Sicherungsserver bereitgestellt wurde und dass der einzige bereitgestellte Server der Sicherungsserver und der zugehörige Spiegelserver ist, wie in [Failover über den Server für beständigen Chat in lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md)definiert.

Mit den folgenden Schritten soll die Konfiguration so wiederhergestellt werden, wie sie vor dem Ausfall, der zu dem Failover vom primären Server auf den Sicherungsserver geführt hat, vorlag.

<div>

## <a name="to-fail-back-persistent-chat-server"></a>So führen Sie einen Fehler zurück für persistent Chat Server

1.  Löschen Sie alle Server aus der Liste der aktiven Server für beständigen Chat Server, indem Sie das `Set-CsPersistentChatActiveServer` Cmdlet aus dem lync Server-Verwaltungsshell verwenden. Dadurch wird verhindert, dass alle Server für beständigen Chat während des Failback eine Verbindung mit der MGC-Datenbank und der mgccomp-Datenbank herstellen.
    
    <div>
    

    > [!IMPORTANT]  
    > Der SQL Server-Agent auf dem sekundären persistent Chat Server-Back-End-Server sollte unter einem privilegierten Konto betrieben werden. Dieses Konto muss insbesondere über die folgenden Berechtigungen verfügen: 
    > <UL>
    > <LI>
    > <P>Lesezugriff auf die Netzwerkfreigabe, in der Sicherungen abgelegt werden sollen</P>
    > <LI>
    > <P>Schreibzugriff auf das lokale Verzeichnis, in das die Sicherungen kopiert werden sollen</P></LI></UL>

    
    </div>

2.  Deaktivieren Sie die Spiegelung für die mgc-Sicherungsdatenbank:
    
    1.  Stellen Sie mit SQL Server Management Studio eine Verbindung mit der MGC-Sicherungsinstanz her.
    
    2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, und klicken Sie dann auf **Spiegeln**.
    
    3.  Klicken Sie auf **Spiegelung entfernen**.
    
    4.  Klicken Sie auf **OK**.
    
    5.  Führen Sie die gleichen Schritte mit der mgccomp-Datenbank durch.

3.  Sichern Sie die mgc-Datenbank, damit Sie in der neuen primären Datenbank wiederhergestellt werden kann:
    
    1.  Stellen Sie mit SQL Server Management Studio eine Verbindung mit der MGC-Sicherungsinstanz her.
    
    2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, und klicken Sie dann auf **Sichern**. Das Dialogfeld **Datenbank sichern** wird angezeigt.
    
    3.  Wählen Sie in **Sicherungstyp** die Option **Vollständig** aus.
    
    4.  Klicken Sie bei **Sicherungskomponente** auf **Datenbank**.
    
    5.  Akzeptieren Sie den Standardnamen für den Sicherungssatz, der in **Name** vorgeschlagen wird, oder geben Sie eine anderen Namen ein.
    
    6.  *\<Optional\>* Geben Sie unter **Beschreibung**eine Beschreibung des Sicherungssatzes ein.
    
    7.  Entfernen Sie den standardmäßigen Sicherungsspeicherort aus der Zielliste.
    
    8.  Fügen Sie der Liste eine Datei mit dem Pfad zu dem Freigabespeicherort ein, den Sie für Protokollversand eingerichtet haben. Dieser Pfad ist für die primäre und die Sicherungsdatenbank verfügbar.
    
    9.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen und mit dem Sicherungsvorgang zu beginnen.

4.  Stellen Sie die primäre Datenbank unter Verwendung der im vorherigen Schritt erstellten Sicherungsdatenbank wieder her.
    
    1.  Stellen Sie mit SQL Server Management Studio eine Verbindung mit der primären MGC-Instanz her.
    
    2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, zeigen Sie auf **Wiederherstellen**, und klicken Sie dann auf **Datenbank**. Das Dialogfeld **Datenbank wiederherstellen** wird angezeigt.
    
    3.  Wählen Sie **Von Medium** aus.
    
    4.  Klicken Sie auf die Schaltfläche zum Durchsuchen. Das Dialogfeld **Sicherung angeben** wird geöffnet. Wählen Sie in **Sicherungsmedium** die Option **Datei** aus. Klicken Sie auf **Hinzufügen**, wählen Sie die Sicherungsdatei aus, die Sie in Schritt 3 erstellt haben, und klicken Sie dann auf **OK**.
    
    5.  Wählen Sie in **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die Sicherung aus.
    
    6.  Klicken Sie auf **Optionen** im Bereich **Seite auswählen**.
    
    7.  Aktivieren Sie in **Wiederherstellungsoptionen** die Option **Vorhandene Datenbank überschreiben**.
    
    8.  Aktivieren Sie in **Wiederherstellungsstatus** die Option **Datenbank betriebsbereit belassen**.
    
    9.  Klicken Sie auf **OK**, um mit dem Wiederherstellungsvorgang zu beginnen.

5.  Konfigurieren Sie SQL Server Protokollversand für die primäre Datenbank. Führen Sie die Verfahren unter [Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) aus, um den Protokollversand für die primäre MGC-Datenbank einzurichten.

6.  Legen Sie den Server für beständigen Chat als aktive Server fest. Verwenden Sie im lync Server-Verwaltungsshell das Cmdlet " **CsPersistentChatActiveServer** ", um die Liste der aktiven Server festzulegen.
    
    <div>
    

    > [!IMPORTANT]  
    > Alle aktiven Server müssen sich in demselben Datencenter wie die neue Primärdatenbank befinden oder in einem Datencenter, das über eine Datenbankverbindung mit geringer Wartezeit und hoher Bandbreite verfügt.

    
    </div>

Wenn Sie den normalen Zustand des Pools wiederherstellen, führen Sie den folgenden Windows PowerShell Befehl aus:

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Weitere Informationen finden Sie im Hilfethema für das Cmdlet " [cspersistentchatstate"](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

