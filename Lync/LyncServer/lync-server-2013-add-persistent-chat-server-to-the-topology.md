---
title: 'Lync Server 2013: Hinzufügen des Servers für beständigen Chat zur Topologie'
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
ms.openlocfilehash: 4656c21d9d28d84259bfaa108c399f36bd2c3d72
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521442"
---
# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Hinzufügen eines Servers für beständigen Chat zur Topologie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

Sie müssen lync Server 2013 Unterstützung für beständigen Chat Server in Ihrer Topologie integrieren, bevor Sie Ihre Bereitstellung für die Unterstützung des Servers für beständigen Chat konfigurieren können. In den Informationen in diesem Thema wird beschrieben, wie Sie mithilfe des Topologie-Generators der vorhandenen Topologie Unterstützung für beständigen Chat hinzufügen.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>So fügen Sie einer Topologie einen Server für beständigen Chat hinzu

Führen Sie die folgenden Schritte aus, um einen einzelnen Server Pool für beständigen Chat ohne Notfall Wiederherstellungskonfiguration zu installieren. Informationen zum Konfigurieren eines ausgedehnten Server Pools für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung finden Sie unter [Configuring persistent Chat Server for High Availability and Disaster Recovery in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in der Bereitstellungsdokumentation.

Um mehrere Server Pools für beständigen Chat bereitzustellen, wiederholen Sie diesen Vorgang für jeden Pool.

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 oder auf dem die lync Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit gleichwertigen Benutzerrechten).
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die für die Installation eines lync Server 2013 Servers erforderlich ist. Sie müssen ein Konto verwenden, das Mitglied der Gruppe " <STRONG>Domänen-Admins</STRONG> " und der Gruppe " <STRONG>RTCUniversalServerAdmins</STRONG> " ist und das über die Berechtigung "Vollzugriff" (Lese-, Schreib-und Änderungsberechtigungen) für den Dateispeicher verfügt, den Sie für den Dateispeicher des beständigen Chat Servers verwenden möchten (Dies bedeutet, dass der Topologie-Generator die erforderlichen DACLs konfigurieren kann) oder ein

    
    </div>

2.  Starten Sie den Topologie-Generator.

3.  Navigieren Sie in der Konsolenstruktur zum Knoten **persistent Chat Pools** , und erweitern Sie ihn, um einen Server Pool für beständigen Chat auszuwählen, oder klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **neuer Pool für beständigen Chat**aus. Sie müssen den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools definieren und festlegen, ob der Pool in der Bereitstellung einen einzelnen oder mehrere Server enthalten soll.
    
    Wählen Sie **Pool mit mehreren Computern** oder **Pool mit einem Computer** aus. Wählen Sie die erste Option aus, wenn Sie mehr als einen Server für beständigen Chat Front-End-Server im Serverpool für beständigen Chat planen. Wählen Sie diese Option jetzt oder zu einem späteren Zeitpunkt, da Sie einem Pool mit einem Computer später keine zusätzlichen Server hinzufügen können. Wenn Sie einen Pool mit mehreren Computern auswählen, geben Sie die Namen der einzelnen beständigen Chat Server-Front-End-Server ein, aus denen sich der Pool zusammensetzt.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn die Server Rolle für beständigen Chat auf einem lync Server 2013 &nbsp; Standard Edition-Server installiert wird, muss der FQDN mit dem FQDN des Standard Edition-Server übereinstimmen.

    
    </div>

4.  Definieren Sie einen einfachen **Anzeigenamen** für den Server Pool für beständigen Chat. Der Anzeigename kann von benutzerdefinierten Clients verwendet werden, insbesondere dann, wenn es mehrere Server Pools für beständigen Chat gibt, um Räume zu unterscheiden.

5.  Definieren Sie den Port, der vom Server für beständigen Chat verwendet wird, um mit lync Server-Front-End-Servern zu kommunizieren. Der Standardport lautet 5041.

6.  Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, aktivieren Sie das Kontrollkästchen **Kompatibilität aktivieren**. Wenn dieser ausgewählt ist, wird der Kompatibilitätsdienst für den Server für beständigen Chat auf dem gleichen Computer wie der Server für beständigen Chat Front-End-Server installiert. Sie werden aufgefordert, einen SQL Server Back-End-Server für die Kompatibilität mit beständigen Chat Servern zu einem späteren Zeitpunkt auszuwählen.

7.  Zuweisen der Standortaffinität für den Server Pool für beständigen Chat. Aktivieren Sie das Kontrollkästchen **diesen Pool als Standard \<SiteName\> für Website verwenden** , oder **verwenden Sie diesen Pool als Standard für alle Websites** , um diesen Server Pool für beständigen Chat als Standardpool für die aktuelle Website oder alle Websites festzulegen. Wenn der lync 2013-Client zum Erstellen und Verwalten von Räumen verwendet wird, wird der Standardpool, der dem Standort des Benutzers zugeordnet ist, von der Raum Erstellungs-und-Verwaltungsumgebung verwendet, damit er Raum Erstellungs-und Verwaltungsvorgänge an diesen Pool weiterleiten kann. Dies gilt nur, wenn Sie mehrere Server Pools für beständigen Chat bereitgestellt haben und die Funktionen zum Erstellen und Verwalten von Räumen für den Server für beständigen Chat verwenden möchten.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können die Raum Erstellungs-und Verwaltungsfunktionen mit dem Server Software Development Kit (SDK) für beständigen Chat anpassen.<BR>Ausführliche Informationen zum Konfigurieren SQL Server Sicherungsdatenbanken für die Notfallwiederherstellung finden Sie unter <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent Chat Server for High Availability and Disaster Recovery in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

8.  Definieren Sie den **SQL-Speicher für den Server für beständigen Chat zurück, auf dem Chatroom-Inhalte gespeichert sind** , indem Sie einen der folgenden Schritte ausführen:
    
      - Um eine vorhandene SQL Server Datenbank zu verwenden, klicken Sie in der Dropdownliste auf den Namen der SQL Server Datenbank, die Sie verwenden möchten.
    
      - Wenn Sie eine neue SQL Server Datenbank angeben möchten, klicken Sie auf **neu**, und führen Sie im **neuen SQL-Speicher definieren**die folgenden Schritte aus:
    
    <!-- end list -->
    
      - Geben Sie in **SQL Server FQDN**den FQDN des SQL Server an, für den Sie die neue SQL Server Datenbank erstellen möchten.
    
      - Wählen Sie entweder **Standardinstanz**, um die Standardinstanz zu verwenden, oder wählen Sie **Benannte Instanz** aus, um eine andere Instanz anzugeben, die Sie verwenden möchten.

9.  Definieren Sie die SQL Server-Kompatibilitätsdatenbank, wenn Sie die Kompatibilität aktiviert haben.
    
    <div>
    

    > [!IMPORTANT]  
    > Ausführliche Informationen zum Konfigurieren von SQL Server spiegeln für hohe Verfügbarkeit für die Datenbank für beständigen Chat Server und die Datenbank für beständigen Chat Server finden Sie unter <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent Chat Server for High Availability and Disaster Recovery in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

10. Definieren Sie den Dateispeicher. Bei einem Dateispeicher handelt es sich um einen Ordner, in dem eine Kopie aller in das Datei-Repository hochgeladenen Dateien gespeichert wird (beispielsweise das Speichern von Dateianlagen, die in einem Chatroom veröffentlicht werden). Wenn es sich um eine Server Topologie mit mehreren Servern für beständigen Chat handelt, muss es sich um einen UNC-Pfad (Universal Naming Convention) handeln. für eine Server Topologie mit einem einzelnen Server kann es sich um einen lokalen Dateipfad handeln.
    
    Führen Sie die folgenden Schritte aus, um einen vorhandenen Dateispeicher zu verwenden:
    
      - Geben Sie in **Dateiserver-FQDN** den FQDN des Dateispeichers an, auf dem Sie den neuen Dateispeicher erstellen möchten.
    
      - Geben Sie in **Dateifreigabe** den Dateispeicher an, den Sie verwenden möchten.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können den Dateispeicher im Topologie-Generator definieren, bevor Sie den Dateispeicher erstellen, aber Sie müssen den Dateispeicher an dem definierten Speicherort erstellen, den Sie vor dem Veröffentlichen der Topologie definieren.

    
    </div>

11. Wählen Sie den Front-End-Server Pool aus, der als nächster Hop für diesen Server Pool für beständigen Chat verwendet werden soll. Dies ist der Front-End-Server Pool, der beständige Chat Server Anforderungen an diesen Pool weiterleiten kann.

12. Klicken Sie auf **Fertig stellen**, um die Konfiguration zu speichern. Der Server Pool für beständigen Chat wird im Topologie-Generator mit ihren speziellen Pooleinstellungen angezeigt.
    
    Informationen zum Veröffentlichen der aktualisierten Topologie, auf der Sie den Server für beständigen Chat haben, finden Sie unter [Veröffentlichen der aktualisierten Topologie in lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in der Bereitstellungsdokumentation.
    
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

