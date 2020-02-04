---
title: 'Lync Server 2013: Hinzufügen eines Server für beständigen Chat zu einer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53f8c65f561a0f2c7b1937d60344c0177d221ba8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Hinzufügen eines Server für beständigen Chat zu einer Topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Sie müssen lync Server 2013 und die Unterstützung für beständigen Chat Server in Ihre Topologie einbeziehen, bevor Sie Ihre Bereitstellung für die Unterstützung des beständigen Chat Servers konfigurieren können. Die Informationen in diesem Thema beschreiben, wie Sie mithilfe des Topologie-Generators Ihrer vorhandenen Topologie Unterstützung für beständigen Chat Server hinzufügen.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>So fügen Sie einen beständigen Chat Server zu einer Topologie hinzu

Führen Sie die folgenden Schritte aus, um einen einzelnen beständigen Chat Server Pool ohne Disaster Recovery-Konfiguration zu installieren. Informationen zum Konfigurieren eines gestreckten beständigen Chat-Server Pools für Hochverfügbarkeits-und Disaster Recovery finden Sie unter [Konfigurieren des beständigen Chat Servers für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in der Bereitstellungsdokumentation.

Zum Bereitstellen mehrerer beständiger Chat Server-Pools wiederholen Sie diesen Vorgang für jeden Pool.

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 ausgeführt wird oder auf dem die lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe "Benutzer" (oder einem Konto mit entsprechenden Benutzerrechten) ist.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die erforderlich ist, um einen lync Server 2013-Server zu installieren. Sie müssen ein Konto verwenden, das ein Mitglied der Gruppe " <STRONG>Domänen-Admins</STRONG> " und der Gruppe " <STRONG>RTCUniversalServerAdmins</STRONG> " ist und über Vollzugriffsberechtigungen (also lesen, schreiben und ändern) für den Dateispeicher verfügt, den Sie für den Dateispeicher des beständigen Chat Servers verwenden werden (d.-a., damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann) oder ein Konto mit entsprechenden Rechten.

    
    </div>

2.  Starten Sie den Topologie-Generator.

3.  Navigieren Sie in der Konsolenstruktur zum Knoten **beständiger Chat Pools** , und erweitern Sie ihn, um einen Server Pool für beständigen Chat auszuwählen, oder klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **neuer beständiger Chat Pool**aus. Sie müssen den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools definieren und angeben, ob es sich bei dem Pool um eine Einzelserver Pool-oder um die Bereitstellung mehrerer Server Pools handelt.
    
    Wählen Sie **Pool mit mehreren Computern** oder **Pool mit einem Computer** aus. Wählen Sie die erste Option aus, wenn Sie beabsichtigen, mehr als einen beständigen Chat Server-Front-End-Server in Ihrem beständigen Chat-Serverpool zu haben. Wählen Sie diese Option jetzt oder zu einem späteren Zeitpunkt, da Sie einem Pool mit einem Computer später keine zusätzlichen Server hinzufügen können. Wenn Sie einen Pool mit mehreren Computern auswählen, geben Sie die Namen der einzelnen beständigen Chat Server-Front-End-Server ein, aus denen sich der Pool zusammensetzt.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn die Serverrolle "beständiger Chat" auf einem lync Server&nbsp;2013 Standard Edition-Server installiert wird, muss der FQDN dem FQDN des Standard Edition-Servers entsprechen.

    
    </div>

4.  Definieren Sie einen einfachen **Anzeige Namen** für den Server Pool des beständigen Chats. Der Anzeigename kann von benutzerdefinierten Clients verwendet werden, insbesondere dann, wenn mehrere beständige Chat Server Pools vorhanden sind, um Räume zu unterscheiden.

5.  Definieren Sie den Port, der vom beständigen Chat Server für die Kommunikation mit lync Server-Front-End-Servern verwendet wird. Der Standardport lautet 5041.

6.  Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, aktivieren Sie das Kontrollkästchen **Kompatibilität aktivieren**. Falls ausgewählt, wird der beständige Chat Server-Kompatibilitätsdienst auf demselben Computer wie der Front-End-Server des beständigen Chats installiert. Sie werden aufgefordert, einen SQL Server-Back-End-Server für die beständige Chat Server-Kompatibilität zu einem späteren Zeitpunkt auszuwählen.

7.  Zuweisen einer Website Affinität für den Server Pool für beständigen Chat Aktivieren Sie das Kontrollkästchen **diesen Pool als Standard \<für\> Website Sitename verwenden** , oder **verwenden Sie diesen Pool als Standard für alle Websites** , um diesen Server Pool für beständigen Chat als Standardpool für die aktuelle Website oder alle Websites festzulegen. Wenn der lync 2013-Client zum Erstellen und Verwalten von Räumen verwendet wird, wird der Standardpool, der der Website des Benutzers zugeordnet ist, von der raumerstellung und-Verwaltung verwendet, um Raum Erstellungs-und Verwaltungsvorgänge an diesen Pool weiterleiten zu können. Dies gilt nur, wenn Sie mehrere beständige Chat Server Pools bereitgestellt haben und die Funktionen zur raumerstellung und-Verwaltung des beständigen Chat Servers verwenden möchten.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können die Funktionen zur raumerstellung und-Verwaltung mithilfe des beständigen Chat-Servers Software Development Kit (SDK) anpassen.<BR>Ausführliche Informationen zum Konfigurieren von SQL Server-Sicherungsdatenbanken für die Disaster Recovery finden Sie unter <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Konfigurieren des beständigen Chat Servers für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

8.  Definieren Sie den **SQL Store für den beständigen Chat Server-Back-End (wobei Chatroom-Inhalte gespeichert werden)** , indem Sie eine der folgenden Aktionen ausführen:
    
      - Wenn Sie eine vorhandene SQL Server-Datenbank verwenden möchten, klicken Sie in der Dropdownliste auf den Namen der SQL Server-Datenbank, die Sie verwenden möchten.
    
      - Wenn Sie eine neue SQL Server-Datenbank angeben möchten, klicken Sie auf **neu**, und führen Sie im **neuen SQL Store definieren**die folgenden Aktionen aus:
    
    <!-- end list -->
    
      - Geben Sie im **SQL Server-FQDN**den FQDN des SQL Server an, auf dem Sie die neue SQL Server-Datenbank erstellen möchten.
    
      - Wählen Sie entweder **Standardinstanz** aus, um die Standardinstanz zu verwenden, oder wählen Sie **Benannte Instanz** aus, um eine andere Instanz anzugeben, die Sie verwenden möchten.

9.  Definieren Sie die SQL Server-Kompatibilitätsdatenbank, wenn Sie die Kompatibilität aktiviert haben.
    
    <div>
    

    > [!IMPORTANT]  
    > Weitere Informationen zum Konfigurieren von SQL Server-Spiegelungen für die Hochverfügbarkeits-Datenbank für die persistente Chat Server-Datenbank und die Datenbank für beständigen Chat Server finden Sie unter <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Konfigurieren des beständigen Chat Servers für die Hochverfügbarkeits-und Disaster Recovery in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

10. Definieren Sie den Dateispeicher. Bei einem Dateispeicher handelt es sich um einen Ordner, in dem eine Kopie einer Datei, die in das Datei-Repository hochgeladen wurde, gespeichert wird (beispielsweise das Speichern von Dateianlagen, die in einem Chatroom gepostet wurden). Bei einer persistenten Chat Server Topologie mit mehreren Servern muss es sich um einen UNC-Pfad (Universal Naming Convention) handeln. und bei einer Server Topologie mit einem Server für beständigen Chat kann es sich um einen lokalen Dateipfad handeln.
    
    Führen Sie die folgenden Schritte aus, um einen vorhandenen Dateispeicher zu verwenden:
    
      - Geben Sie im **FQDN des Dateiservers**den FQDN des Dateispeichers an, für den Sie den neuen Dateispeicher erstellen möchten.
    
      - Geben Sie in **Dateifreigabe** den Dateispeicher an, den Sie verwenden möchten.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können den Dateispeicher in Topology Builder definieren, bevor Sie den Dateispeicher erstellen, aber Sie müssen den Dateispeicher am definierten Speicherort erstellen, den Sie definieren, bevor Sie die Topologie veröffentlichen.

    
    </div>

11. Wählen Sie den Front-End-Serverpool aus, der als nächster Hop für diesen beständigen Chat Serverpool verwendet werden soll. Dies ist der Front-End-Serverpool, der beständige Chat Server Anforderungen an diesen Pool weiterleiten kann.

12. Klicken Sie auf **Fertig stellen**, um die Konfiguration zu speichern. Der Server Pool für beständigen Chat wird im Topologie-Generator mit ihren spezifischen Pooleinstellungen angezeigt.
    
    Wenn Sie jetzt Ihre aktualisierte Topologie veröffentlichen möchten, auf der Sie den persistenten Chat Server haben, lesen Sie [Veröffentlichen der aktualisierten Topologie in lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in der Bereitstellungsdokumentation.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Topologie-Generator bereits geöffnet ist, können Sie mit Schritt 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Veröffentlichen der aktualisierten Topologie in lync Server 2013</A> fortfahren, um mit der Veröffentlichung ihrer aktualisierten Topologie zu beginnen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

