---
title: Bereitstellen eines nicht standardmäßigen SQL Server-Ports und -Alias in Lync Server 2013
TOCTitle: Bereitstellen eines nicht standardmäßigen SQL Server-Ports und -Alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634525
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen eines nicht standardmäßigen SQL Server-Ports und -Alias in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Microsoft Lync Server 2013 unterstützt die Verwendung eines nicht standardmäßigen Ports und eines Alias in SQL Server. Die Verwendung eines nicht standardmäßigen SQL Server-Ports und eines Alias verbessert die Sicherheit und schafft eine flexiblere Umgebung für die Lync-Bereitstellung. Diese Maßnahmen bilden nur einen Schritt in der ordnungsgemäßen Sicherung Ihrer Lync Server 2013-Umgebung. Es sollten zusätzliche Schritte erfolgen, um die Angriffsoberfläche einer Lync Server 2013-Implementierung zu verringern.

Der folgende Artikel beschreibt die erforderlichen Schritte für die Einrichtung eines nicht standardmäßigen SQL Server-Ports und -Alias in Lync Server 2013.

## Bereitstellen eines nicht standardmäßigen SQL Server-Ports und -Alias in Lync Server 2013

Lync Server 2013Topologie-Generator unterstützt bei der Konfiguration von Lync Server 2013 die Verwendung eines SQL Server-Alias als Fully Qualified Domain Name (FQDN) anstelle des tatsächlichen SQL Server-FQDN. So kann der tatsächliche SQL Server-FQDN vor bösartigen Angreifern verborgen werden. Zudem verbirgt die Verwendung eines nicht standardmäßigen Ports den tatsächlichen Port vor möglichen Angreifern, die versuchen, die Datenbank über den Standardport 1433 anzugreifen, wie in der folgenden Abbildung gezeigt.

![Ein Hacker weiß nicht, welche Portnummer er angreifen muss.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Ein Hacker weiß nicht, welche Portnummer er angreifen muss.")

Um den Port, über den Lync Server 2013 mit SQL Server kommuniziert, erfolgreich zu bestimmen, müsste der Angreifer alle Ports scannen und die Portinformationen abrufen. Ein Portscan durch einen Angreifer erhöht die Wahrscheinlichkeit, dass die Sicherheit die Anweisung entdeckt und unterbindet. Neben der verbesserten Sicherheit durch einen nicht standardmäßigen Port können Sie zudem einen SQL Server-Alias verwenden, der eine flexible Bereitstellung ermöglicht. Dies ist besonders hilfreich, um Konfigurationsänderungen in Situationen zu verringern, in denen der SQL Server-Name geändert werden muss.


> [!NOTE]
> SQL Server bietet zwei Fehlertoleranzmethoden (Failoverclustering und Spiegelung). Beide Fehlertoleranzmethoden von SQL Server werden über einen nicht standardmäßigen SQL Server-Port und -Alias in Lync Server 2013 unterstützt.



Beim Konfigurieren einer SQL Server-Datenbankverbindung über den Topologie-Generator oder bei Verwendung des Install-CsDatabase-Cmdlet ist es nicht möglich, explizit eine nicht standardmäßige SQL Server-Portnummer anzugeben und einer SQL-Instanz zuzuweisen. Sie müssen SQL Server- und Windows Server-Dienstprogramme verwenden, um einen nicht standardmäßigen Port festzulegen.

Um einen nicht standardmäßigen SQL Server-Port und -Alias zur Verwendung mit Lync Server 2013 einzurichten, sind drei grundlegende Schritte erforderlich. Diese lauten:

  - Sicherstellen, dass die aktuellen Updates für Lync Server 2013 angewendet wurden

  - Einrichten des nicht standardmäßigen SQL Server-Ports und -Alias

  - Konfigurieren von Lync Server 2013 mit dem SQL Server-Alias über den Topologie-Generator

  - Veröffentlichen der Topologie und Überprüfen der Datenbank

## Sicherstellen, dass die aktuellen Updates für Lync Server 2013 angewendet wurden

Lync Server 2013 muss unbedingt auf dem neuesten Stand bleiben. Wie Sie nach aktuellen Updates suchen und diese anwenden erfahren Sie unter [Updates für Lync Server 2013](http://support.microsoft.com/kb/2809243).

## Einrichten des nicht standardmäßigen SQL Server-Ports und -Alias

Der nicht standardmäßige SQL Server-Port und -Alias müssen in der Datenbankinstanz einrichtet werden, bevor sie vom Lync Server 2013Topologie-Generator referenziert werden kann. Um einen nicht standardmäßigen SQL Server-Port und -Alias einzurichten, sind drei grundlegende Schritte erforderlich. Diese lauten:

  - Ändern der standardmäßigen TCP/IP-Protokollwerte

  - Erstellen und Konfigurieren eines SQL Server-Alias

  - Erstellen eines Domain Name System (DNS) Canonical Name (CNAME) Resource Record

**Ändern der standardmäßigen TCP/IP-Protokollwerte**

1.  Wählen Sie **Start** und dann **SQL Server Configuration Manager**, wie in der folgenden Abbildung gezeigt.
    
    ![Das SQL Server Management Studio-Symbol](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Das SQL Server Management Studio-Symbol")

2.  Erweitern Sie im Navigationsbereich die **SQL Server-Instanz** und dann **SQL Server-Netzwerkkonfiguration**. Wählen Sie anschließend **Protokolle für \<Instanzname\>**, wie in der nachfolgenden Abbildung gezeigt.
    
    ![Navigieren Sie zu den TCP/IP-Eigenschaften.](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigieren Sie zu den TCP/IP-Eigenschaften.")

3.  Klicken Sie im rechten Fensterbereich auf **TCP/IP** und wählen Sie **Eigenschaften**. Das Dialogfeld „TCP/IP-Eigenschaften“ wird geöffnet.

4.  Öffnen Sie die Registerkarte **IP-Adressen**. Die Registerkarte „IP-Adressen“ führt alle aktiven IP-Adressen auf dem Server auf. Sie liegen im Format IP1, IP2 bis zu IPAll vor, wie in der folgenden Abbildung gezeigt.
    
    ![Öffnen Sie die TCP/IP-Eigenschaften.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Öffnen Sie die TCP/IP-Eigenschaften.")

5.  Deaktivieren Sie das Feld **Dynamische TCP-Ports** für alle IP-Adressen. Wenn das Feld eine Null enthält, bedeutet dies, dass SQL Server auf dynamischen Ports empfangsbereit ist. Stellen Sie sicher, dass diese Felder leer sind und keine Null enthalten.

6.  Stellen Sie für die IP-Adresse, die Lync Server zur Verbindung mit der Datenbank verwendet, sicher, dass **Aktiviert** auf **Ja** eingestellt ist, wie in der folgenden Abbildung gezeigt.
    
    ![Aktivieren Sie die richtige IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Aktivieren Sie die richtige IP.")

7.  Geben Sie im Abschnitt **IPAll** unten im Dialogfeld den gewünschten Port in das Feld **TCP-Port** ein, wie in der folgenden Abbildung gezeigt. In diesem Beispiel verwenden wir 50062. Sie können aber jeden beliebigen Port zwischen 49152 und 65535 verwenden. Diese Ports werden der dynamischen und privaten Nutzung zugewiesen, sodass sichergestellt wird, dass sie keine Konflikte mit anderen in der Lync Server 2013-Bereitstellung verwendeten Ports verursachen.
    
    ![Legen Sie den Port im Abschnitt „IPAll“ fest.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Legen Sie den Port im Abschnitt „IPAll“ fest.")

8.  Wählen Sie **OK**, um das Dialogfeld „TCP/IP-Eigenschaften“ zu schließen.

9.  Starten Sie die SQL Server-Instanz neu, indem Sie im linken Fensterbereich des SQL Server Configuration Manager **SQL Server-Dienste** auswählen. Klicken Sie dann im rechten Fensterbereich mit der rechten Maustaste auf **SQL Server \<Instanzname\>** und wählen Sie **Neu starten**, wie in der folgenden Abbildung gezeigt.
    
    ![Setzen Sie den SQL Server-Dienst für die Instanz zurück.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Setzen Sie den SQL Server-Dienst für die Instanz zurück.")


> [!IMPORTANT]
> Stellen Sie sicher, dass Sie Ihre Firewall-Einstellungen an den neuen SQL Server-Port anpassen.



**Erstellen und Konfigurieren eines SQL Server-Alias**

1.  Wählen Sie **Start** und dann **SQL Server Configuration Manager**, wie in der folgenden Abbildung gezeigt.
    
    ![Das SQL Server Management Studio-Symbol](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Das SQL Server Management Studio-Symbol")

2.  Erweitern Sie im linken Fensterbereich **SQL Server-Instanz** und dann **SQL Native Client \<Version\>-Konfiguration**. Wählen Sie anschließend **Aliase**, wie in der folgenden Abbildung gezeigt.
    
    ![Aliase im SQL Server-Konfigurations-Manager](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliase im SQL Server-Konfigurations-Manager")

3.  Klicken Sie mit der rechten Maustaste auf **Aliase** und wählen Sie **Neuer Alias…**.

4.  Geben Sie den **Aliasnamen**, die **Portnummer**, das **Protokoll** und den **Server** wie in der folgenden Abbildung gezeigt ein.
    
    ![Erstellen eines neuen Aliases](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Erstellen eines neuen Aliases")
    
    > [!CAUTION]  
	> Achten Sie darauf, den gleichen nicht standardmäßigen Port einzugeben, den Sie im vorherigen Schritt verwendet haben, da dies der Port ist, auf dem SQL Server empfangsbereit ist. Wenn ein konfigurierter Alias sich mit dem falschen SQL Server-FQDN oder der falschen Instanz verbindet, deaktivieren Sie das zugehörige Netzwerkprotokoll und aktivieren Sie es dann erneut. Dadurch werden die zwischengespeicherten Verbindungsinformationen gelöscht und der Client kann sich korrekt verbinden.


**Erstellen eines DNS CNAME Resource Record**

1.  Melden Sie sie bei dem Computer an, der den DNS verwaltet.

2.  Wählen Sie **Start** und dann **Server Manager**, wie in der folgenden Abbildung gezeigt.
    
    ![Öffnen des Server-Managers](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Öffnen des Server-Managers")

3.  Wählen Sie das Dropdown-Menü **Extras** und dann **DNS**, wie in der folgenden Abbildung gezeigt.
    
    ![Öffnen von DNS vom Server-Manager](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Öffnen von DNS vom Server-Manager")

4.  Erweitern Sie im linken Fensterbereich den Knoten des Servernamens und dann den Knoten der Forward-Lookupzonen. Wählen Sie die entsprechende Domain aus.

5.  Klicken Sie mit der rechten Maustaste auf die Domain und wählen Sie **Neuer Alias (CNAME)…**, wie in der folgenden Abbildung gezeigt.
    
    ![Auswählen der Option zum Erstellen eines neuen Alias-CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Auswählen der Option zum Erstellen eines neuen Alias-CNAME")

6.  Geben Sie den **Aliasnamen** und den **FQDN für SQL Server** wie in der folgenden Abbildung gezeigt ein.
    
    ![Ausfüllen des Dialogfelds für den neuen Alias-CNAME](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Ausfüllen des Dialogfelds für den neuen Alias-CNAME")

7.  Wählen Sie **OK**, um den CNAME zu speichern und in DNS Manager anzuzeigen.

## Prüfen der Datenbankverbindung

Es gibt verschiedene Methoden sicherzustellen, dass Ihre Konfiguration funktioniert. Stellen Sie sicher, dass die SQL Server-Datenbank am angegebenen Port über den Alias empfangsbereit ist. Verwenden Sie zur schnellen Prüfung die Befehle **netstat** und **telnet**.


> [!NOTE]
> Der Telnet-Client ist ein in Windows Server enthaltenes Feature, muss jedoch installiert werden. Um ein Windows Server-Feature zu installieren, öffnen Sie den Server Manager und wählen Sie im Menü „Verwalten“ die Option „Rollen und Features hinzufügen“.



**Verwenden von netstat und telnet zur Überprüfung der Datenbankverbindung**

1.  Wählen Sie **Start** und geben Sie **cmd** in eine geöffnete Befehlszeile ein.

2.  Geben Sie **netstat -a -f** und stellen Sie sicher, dass SQL Server mit dem richtigen Port ausgeführt wird, wie in der folgenden Abbildung gezeigt.
    
    ![Verwenden von Netstat zum Überprüfen des Ports](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Verwenden von Netstat zum Überprüfen des Ports")

3.  Geben Sie **telnet \<Aliasname\> \<Portnummer\>** ein, um die Verbindung zur SQL Server-Instanz zu bestätigen. Wenn die Verbindung erfolgreich ist, stellt telnet eine Verbindung her und es werden keine Fehler angezeigt. Dies bedeutet, dass die SQL Server-Instanz auf dem richtigen Port mit dem richtigen Alias empfangsbereit ist. Wenn ein Problem bei der Verbindung zur SQL Server-Datenbank auftritt, zeigt telnet einen Fehler an, dass die Verbindung nicht hergestellt werden kann. Nachdem Sie die Datenbankverbindung auf dem Datenbankserver geprüft haben, führen Sie die gleichen Schritte vom Lync-Server (über das Netzwerk) durch und stellen Sie sicher, dass der Zugriff unterwegs nicht durch Firewalls blockiert wird.

## Fazit

Sobald der SQL Server-Alias konfiguriert wurde, können Sie ihn verwenden, um eine Lync Server 2013-Topologie im Topologie-Generator-Tool zu erstellen. Weitere Informationen zu Topologien finden Sie unter [Definieren und Konfigurieren der Topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

## Siehe auch

#### Konzepte

[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  

#### Weitere Ressourcen

[Planen für mehr Sicherheit in Lync Server 2013](lync-server-2013-planning-for-security.md)  
[Definieren und Konfigurieren der Topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)

