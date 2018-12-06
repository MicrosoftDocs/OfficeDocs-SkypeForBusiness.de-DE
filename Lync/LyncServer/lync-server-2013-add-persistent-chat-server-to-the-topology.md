---
title: 'Lync Server 2013: Hinzufügen eines Server für beständigen Chat zu einer Topologie'
TOCTitle: Hinzufügen eines Server für beständigen Chat zu einer Topologie
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205049(v=OCS.15)
ms:contentKeyID: 49294599
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen eines Server für beständigen Chat zu einer Topologie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Sie müssen in Lync Server 2013 die Unterstützung für den Server für beständigen Chat in Ihre Topologie integrieren, um Ihre Bereitstellung für die Unterstützung des Server für beständigen Chat konfigurieren zu können. In diesem Thema wird beschrieben, wie Sie den Topologie-Generator verwenden, um Ihrer vorhandenen Topologie die Unterstützung für den Server für beständigen Chat hinzuzufügen.

## So fügen Sie den Server für beständigen Chat einer Topologie hinzu

Führen Sie die folgenden Schritte aus, um einen einzelnen Serverpool für beständigen Chat ohne Konfiguration für eine Notfallwiederherstellung zu installieren. Informationen zur Konfiguration eines gestreckten Serverpool für beständigen Chat für hohe Verfügbarkeit und die Notfallwiederherstellung finden Sie unter [Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in der Bereitstellungsdokumentation.

Wenn Sie mehrere Serverpools für beständigen Chat bereitstellen möchten, wiederholen Sie diesen Prozess für jeden Pool.

1.  Melden Sie sich bei einem Computer, der Lync Server 2013 ausführt oder auf dem die Lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit entsprechenden Benutzerrechten).
    

    > [!NOTE]
    > Eine Topologie kann über ein Konto definiert werden, das Mitglied der lokalen Benutzergruppe ist. Um jedoch eine Topologie zu veröffentlichen (was zur Installation eines Lync Server 2013-Servers erforderlich ist), müssen Sie ein Konto verwenden, das Mitglied der Gruppe <STRONG>Domänen-Admins</STRONG> und der Gruppe <STRONG>RTCUniversalServerAdmins</STRONG> ist sowie über Vollzugriff (Lesen, Schreiben und Ändern) für den Dateispeicher verfügt, den Sie für den Dateispeicher für den Server für beständigen Chat verwenden möchten (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann). Alternativ dazu können Sie ein Konto mit gleichwertigen Rechten verwenden.



2.  Starten Sie den Topologie-Generator.

3.  Erweitern Sie in der Konsolenstruktur den Knoten **Beständiger Chat-Pools** , und wählen Sie einen Serverpool für beständigen Chat, oder klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **Neuer Beständiger Chat-Pool** . Sie müssen den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools definieren und festlegen, ob der Pool in der Bereitstellung einen einzelnen oder mehrere Server enthalten soll.
    
    Wählen Sie **Pool mit mehreren Computern** oder **Pool mit einem Computer** aus. Wählen Sie die erste Option, wenn Sie mehr als einen Server für beständigen Chat- Front-End-Server in Ihren Serverpool für beständigen Chat aufnehmen möchten. Wählen Sie diese Option jetzt oder zu einem späteren Zeitpunkt, da Sie einem Pool mit einem Computer später keine zusätzlichen Server hinzufügen können. Wenn Sie sich für einen Pool mit mehreren Computern entscheiden, geben Sie die Namen der einzelnen Server für beständigen Chat- Front-End-Server an, die im Pool enthalten sind.
    

    > [!IMPORTANT]
    > Wenn die Server für beständigen Chat-Rolle auf einem Lync Server 2013Standard Edition-Server installiert wird, muss der FQDN mit dem FQDN des Standard Edition-Servers übereinstimmen.



4.  Definieren Sie einen einfachen **Anzeigenamen** für den Serverpool für beständigen Chat. Der Anzeigename kann von benutzerdefinierten Clients verwendet werden, vor allem im Falle von mehreren Serverpools für beständigen Chat, um zwischen Chatrooms zu unterscheiden.

5.  Definieren Sie den von Server für beständigen Chat für die Kommunikation mit den Lync ServerFront-End-Server verwendeten Port. Der Standardport lautet 5041.

6.  Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, aktivieren Sie das Kontrollkästchen **Kompatibilität aktivieren** . In diesem Fall wird der Kompatibilitätsdienst für den Server für beständigen Chat auf demselben Computer installiert, wie der Front-End-Server für den Server für beständigen Chat. Sie werden aufgefordert, später einen SQL ServerBack-End-Server für die Kompatibilität mit dem Server für beständigen Chat auszuwählen.

7.  Weisen Sie die Standortaffinität für den Serverpool für beständigen Chat zu. Aktivieren Sie das Kontrollkästchen **Diesen Pool standardmäßig für den Standort \<Standortname\> verwenden** oder **Diesen Pool standardmäßig für alle Standorte verwenden** , um diesen Serverpool für beständigen Chat als Standardpool für den aktuellen Standort oder alle Standorte festzulegen. Wird der Lync 2013-Client zum Erstellen und Verwalten von Chatrooms verwendet, wird der dem Benutzerstandort zugeordnete Standardpool vom Chatroomerstellungs- und Verwaltungserlebnis verwendet, um die Erstellung und Verwaltung von Chatrooms an diesen Pool weiterzuleiten. Dies ist nur möglich, wenn Sie mehrere Serverpools für beständigen Chat bereitgestellt haben und die Funktionen zum Erstellen und Verwalten von Chatrooms von Server für beständigen Chat nutzen möchten.
    

    > [!IMPORTANT]
    > Sie können die Funktionen zum Erstellen und Verwalten von Chatrooms mit dem Software Development Kit (SDK) für den Server für beständigen Chat anpassen.<BR>Informationen zum Konfigurieren von SQL Server-Backup-Datenbanken für eine Notfallwiederherstellung finden Sie unter <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013</A> in der Bereitstellungsdokumentation.



8.  Definieren Sie den **SQL-Speicher für das Server für beständigen Chat-Back-End (wo der Inhalt des Chatrooms gespeichert ist)** wie folgt:
    
      - Wenn Sie eine vorhandene SQL Server-Datenbank verwenden möchten, klicken Sie in der Dropdownliste auf den Namen der gewünschten SQL Server-Datenbank.
    
      - Wenn Sie stattdessen eine neue SQL Server-Datenbank angeben möchten, klicken Sie auf **Neu** , und führen Sie unter **Neuen SQL-Speicher definieren** die folgenden Schritte aus:
    
    <!-- end list -->
    
      - Geben Sie in **SQL Server-FQDN** den FQDN des SQL Servers an, auf dem Sie die neue SQL Server-Datenbank erstellen möchten.
    
      - Wählen Sie entweder **Standardinstanz** , um die Standardinstanz zu verwenden, oder wählen Sie **Benannte Instanz** aus, um eine andere Instanz anzugeben, die Sie verwenden möchten.

9.  Definieren Sie die SQL Server-Kompatibilitätsdatenbank, wenn Sie die Kompatibilität aktiviert haben.
    

    > [!IMPORTANT]
    > Einzelheiten zum Konfigurieren von SQL Server-Spiegeln für die hohe Verfügbarkeit von Datenbanken für den Server für beständigen Chat und die Kompatibilitätsdatenbank für den Server für beständigen Chat finden Sie unter <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013</A> in der Bereitstellungsdokumentation.



10. Definieren Sie den Dateispeicher. Ein Dateispeicher ist ein Ordner, in dem eine Kopie einer beliebigen Datei gespeichert wird, die in das Dateirepository hochgeladen wurde (z. B. Dateianhänge, die in einem Chatroom veröffentlicht wurden). Für eine Server für beständigen Chat-Topologie mit mehreren Servern muss ein UNC-Pfad (Universal Naming Convention) angegeben werden. Für eine Server für beständigen Chat-Topologie mit nur einem Server ist ein lokaler Dateipfad ausreichend.
    
    Führen Sie die folgenden Schritte aus, um einen vorhandenen Dateispeicher zu verwenden:
    
      - Geben Sie in **Dateiserver-FQDN** den FQDN des Dateispeichers an, auf dem Sie den neuen Dateispeicher erstellen möchten.
    
      - Geben Sie in **Dateifreigabe** den Dateispeicher an, den Sie verwenden möchten.
    

    > [!IMPORTANT]
    > Sie können den Dateispeicher im Topologie-Generator definieren, bevor Sie den Dateispeicher erstellen, aber Sie müssen den Dateispeicher am angegebenen Speicherort erstellen, bevor Sie die Topologie veröffentlichen.



11. Wählen Sie den Front-End-Server-Pool, der als nächster Hop für diesen Serverpool für beständigen Chat verwendet werden soll. Hierbei handelt es sich um den Front-End-Server-Pool, der Anfragen vom Server für beständigen Chat an diesen Pool weiterleiten kann.

12. Klicken Sie auf **Fertig stellen** , um die Konfiguration zu speichern. Der Serverpool für beständigen Chat wird im Topologie-Generator zusammen mit Ihren Pool-Einstellungen angezeigt.
    
    Informationen zum Veröffentlichen Ihrer aktualisierten Topologie, der Sie den Server für beständigen Chat hinzugefügt haben, finden Sie unter [Veröffentlichen der aktualisierten Topologie in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in der Bereitstellungsdokumentation.
    

    > [!NOTE]
    > Bei geöffnetem Topologie-Generator können Sie mit Schritt 3 unter <A href="lync-server-2013-publish-the-updated-topology.md">Veröffentlichen der aktualisierten Topologie in Lync Server 2013</A> fortfahren, um mit der Veröffentlichung Ihrer aktualisierten Topologie zu beginnen.


