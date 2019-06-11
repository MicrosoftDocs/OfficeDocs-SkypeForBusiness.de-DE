---
title: Bereitstellen eines nicht standardmäßigen SQL Server-Ports und -Alias in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35365cbd43aa3bea9afe5cdd036bd3834fae5037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Bereitstellen eines nicht standardmäßigen SQL Server-Ports und -Alias in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-09-16_

Microsoft lync Server 2013 unterstützt die Verwendung eines nicht standardmäßigen Ports und Alias in SQL Server. Mit einem nicht standardmäßigen SQL Server-Port und einem Alias wird die Sicherheit erhöht und eine flexiblere Umgebung für die lync-Bereitstellung erstellt. Diese Schritte stellen nur einen einzigen Schritt bei der ordnungsgemäßen Sicherung ihrer lync Server 2013-Umgebung dar. Es sollten zusätzliche Schritte unternommen werden, um die Angriffsfläche einer lync Server 2013-Implementierung zu verringern.

Im folgenden Artikel werden die Schritte beschrieben, die erforderlich sind, um einen nicht standardmäßigen SQL Server-Port und-Alias in lync Server 2013 einzurichten.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Bereitstellen eines nicht Standard mäßigen SQL Server-Ports und-Alias in lync Server 2013

Der lync Server 2013-Topologie-Generator unterstützt die Verwendung eines SQL Server-Alias als vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) anstelle des eigentlichen SQL Server-FQDN beim Konfigurieren von lync Server 2013. Dadurch kann der tatsächliche SQL Server-FQDN vor böswilligen Angreifern verborgen werden. Darüber hinaus verdeckt die Verwendung eines nicht standardmäßigen Ports den tatsächlichen Port von einem beliebigen Angreifer, der versucht, die Datenbank auf dem Standard Port 1433 anzugreifen, wie in der folgenden Abbildung gezeigt.

![Ein Hacker weiß nicht, welche Portnummer angreifen soll.] (images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Ein Hacker weiß nicht, welche Portnummer angreifen soll.")

Um den Port zu ermitteln, der von lync Server 2013 für die Kommunikation mit SQL Server verwendet wird, muss der Angreifer alle Ports durchsuchen, um die Portinformationen zu erhalten. Eine Portüberprüfung durch einen Angreifer erhöht die Wahrscheinlichkeit, dass die Sicherheit die Anweisung erkennen und beenden kann. Zusätzlich zum Hinzufügen höherer Sicherheit mit einem nicht standardmäßigen Port können Sie auch einen SQL Server-Alias verwenden, um Flexibilität für die Bereitstellung zu bieten. Dies ist hilfreich, um Konfigurationsänderungen in Situationen zu verringern, in denen eine Änderung des SQL Server-namens erforderlich ist.

<div>


> [!NOTE]  
> SQL Server bietet zwei Fehlertoleranz Methoden (Failover-Clustering und Spiegelung). Beide SQL Server-Fehlertoleranz Methoden werden mit einem nicht standardmäßigen SQL Server-Port und-Alias mit lync Server 2013 unterstützt. Wenn sich das vom Pool verwendete SQL Server-Back-End in einer gespiegelten Konfiguration befindet, sollte der SQL-Browserdienst auf den SQL Server-Back-End-Servern für Front-End-Server ausgeführt werden, um eine Verbindung mit der gespiegelten Datenbank herzustellen, wenn die Datenbanken für den gespiegelten SQL-Fehler beendet werden. Server.



</div>

Wenn Sie die SQL Server-Datenbankverbindung im Topologie-Generator konfigurieren oder wenn Sie das Cmdlet "installieren-CsDatabase" verwenden, ist es nicht möglich, eine nicht standardmäßige SQL Server-Portnummer explizit zu definieren und Sie einer SQL-Instanz zuzuordnen. Wenn Sie einen nicht standardmäßigen Port einrichten möchten, müssen Sie die SQL Server-und Windows Server-Dienstprogramme verwenden.

Um einen nicht standardmäßigen SQL Server-Port und-Alias für die Verwendung mit lync Server 2013 einzurichten, müssen Sie drei primäre Schritte ausführen. Diese Schritte sind wie folgt:

  - Vergewissern Sie sich, dass lync Server 2013 die neuesten Updates installiert hat.

  - Richten Sie den SQL Server-Port und-Alias nicht Standard mäßig ein.

  - Konfigurieren Sie lync Server 2013 mit dem SQL Server-Alias mithilfe des Topologie-Generators.

  - Veröffentlichen Sie die Topologie, und überprüfen Sie die Datenbank.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Überprüfen, ob lync Server 2013 die neuesten Updates angewendet hat

Es ist wichtig, lync Server 2013 auf dem neuesten Stand zu halten. Informationen zum Überprüfen der neuesten Updates und Informationen zur Anwendung finden Sie unter [Updates für lync Server 2013](http://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Einrichten des nicht Standard mäßigen SQL Server-Ports und-Alias

Der SQL Server-Port und der nicht standardmäßige Alias müssen für die Datenbankinstanz eingerichtet werden, bevor Sie vom lync Server 2013-Topologie-Generator referenziert werden können. Um einen nicht standardmäßigen SQL Server-Port und-Alias einzurichten, müssen Sie drei primäre Schritte ausführen. Diese Schritte sind wie folgt:

  - Ändern Sie die Standardwerte für TCP/IP-Protokoll.

  - Erstellen und konfigurieren Sie einen SQL Server-Alias.

  - Erstellen Sie einen CNAME-Ressourceneintrag (Domain Name System).

**Ändern der Standardwerte für TCP/IP-Protokolle**

1.  Wählen Sie **Start**aus, und wählen Sie **SQL Server-Konfigurations-Manager**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Das SQL Server Management Studio-Symbol] (images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Das SQL Server Management Studio-Symbol")

2.  Wählen Sie im Navigationsbereich aus, um die **SQL Server-Instanz**zu erweitern, wählen Sie die Option **SQL Server-Netzwerkkonfiguration**erweitern aus, und wählen Sie **Protokolle \<für\>Instanzname**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Navigieren zu TCP/IP-Eigenschaften] (images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigieren zu TCP/IP-Eigenschaften")

3.  Klicken Sie im rechten Bereich mit der rechten Maustaste auf **TCP/IP**, und wählen Sie **Eigenschaften**aus. Das Dialogfeld TCP/IP-Eigenschaften wird angezeigt.

4.  Wählen Sie die Registerkarte **IP-Adressen** aus. Auf der Registerkarte IP-Adressen werden alle aktiven IP-Adressen auf dem Server angezeigt. Diese befinden sich im Format IP1, IP2, bis zu IPAll, wie in der folgenden Abbildung dargestellt.
    
    ![Öffnen Sie die TCP/IP-Eigenschaften.] (images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Öffnen Sie die TCP/IP-Eigenschaften.")

5.  Deaktivieren Sie das Feld **TCP Dynamic Ports** für alle IP-Adressen. Wenn das Feld ein Nullzeichen enthält, bedeutet dies, dass SQL Server dynamische Ports überwacht. Stellen Sie sicher, dass diese Felder deaktiviert sind und keine 0 (null) enthalten.

6.  Stellen Sie für die IP-Adresse, die von lync Server für die Verbindung mit der Datenbank verwendet wird, sicher, dass **Enabled** auf **Ja**festgesetzt ist, wie in der folgenden Abbildung gezeigt.
    
    ![Aktivieren Sie für die richtige IP-Adresse die Option "Ja".] (images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Aktivieren Sie für die richtige IP-Adresse die Option \"Ja\".")

7.  Geben Sie im Abschnitt **IPAll** am unteren Rand des Dialogfelds den gewünschten Port im Feld **TCP-Port** ein, wie in der folgenden Abbildung dargestellt. In diesem Beispiel verwenden wir Port 50062, Sie können jedoch einen beliebigen Port zwischen 49152 und 65535 verwenden. Hierbei handelt es sich um die Ports, die der dynamischen und privaten Verwendung zugewiesen sind, und dadurch wird sichergestellt, dass Sie keinen Konflikt mit anderen in der lync Server 2013-Bereitstellung verwendeten Anschlüssen verursachen.
    
    ![Port im IPAll-Abschnitt einstellen.] (images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Port im IPAll-Abschnitt einstellen.")

8.  Wählen Sie **OK** aus, um das Dialogfeld TCP/IP-Eigenschaften zu beenden.

9.  Starten Sie die SQL Server-Instanz neu, indem Sie im linken Bereich des SQL Server-Konfigurations-Managers **SQL Server-Dienste** auswählen. Klicken Sie dann im rechten Bereich mit der rechten Maustaste auf **SQL Server \<-\> Instanzname** , und wählen Sie dann **neu starten**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Setzen Sie den SQL Server-Dienst zum Beispiel zurück.] (images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Setzen Sie den SQL Server-Dienst zum Beispiel zurück.")

<div>


> [!IMPORTANT]  
> Stellen Sie sicher, dass Sie Ihre Firewalleinstellungen so aktualisieren, dass Sie den neuen SQL Server-Port aufnehmen.



</div>

**Erstellen und Konfigurieren eines SQL Server-Alias**

1.  Wählen Sie **Start**aus, und wählen Sie **SQL Server-Konfigurations-Manager**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Das SQL Server Management Studio-Symbol] (images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Das SQL Server Management Studio-Symbol")

2.  Wählen Sie im linken Bereich die Option zum Erweitern der **SQL Server-Instanz**aus, wählen Sie aus, um die **Versions \<\> Konfiguration von SQL Native Client**zu erweitern, und wählen Sie dann **Aliase**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Aliase im SQL Server-Konfigurations-Manager.] (images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliase im SQL Server-Konfigurations-Manager.")

3.  Klicken Sie mit **** der rechten Maustaste auf Aliase, und wählen Sie **Neuer Alias**aus.

4.  Geben Sie den **Alias Namen**, die **Port Nummer**, das **Protokoll**und den **Server**ein, wie in der folgenden Abbildung dargestellt.
    
    ![Erstellen eines neuen Alias] (images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Erstellen eines neuen Alias")
    
    <div>
    

    > [!CAUTION]  
    > Stellen Sie sicher, dass Sie den gleichen nicht standardmäßigen Port eingeben, den Sie im vorherigen Schritt verwendet haben, da dies der Port ist, der von SQL Server überwacht wird. Wenn ein konfigurierter Alias eine Verbindung mit dem falschen SQL Server-FQDN oder-Beispiel herstellt, deaktivieren Sie das zugeordnete Netzwerkprotokoll, und aktivieren Sie es dann erneut. Dadurch werden alle zwischengespeicherten Verbindungsinformationen gelöscht, und der Client kann eine ordnungsgemäße Verbindung herstellen.

    
    </div>

**Erstellen eines DNS-CNAME-Ressourceneintrags**

1.  Registrieren Sie sich beim Computer, der DNS verwaltet.

2.  Wählen Sie **Start**aus, und wählen Sie **Server-Manager**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Öffnen des Server-Managers] (images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Öffnen des Server-Managers")

3.  Wählen Sie die Dropdownliste **Tools** aus, und wählen Sie **DNS**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Öffnen von DNS im Server-Manager] (images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Öffnen von DNS im Server-Manager")

4.  Erweitern Sie im linken Bereich den Knoten Servername, erweitern Sie den Knoten Forward Lookup Zones, und wählen Sie die entsprechende Domäne aus.

5.  Klicken Sie mit der rechten Maustaste auf die Domäne, und wählen Sie **Neuer Alias (CNAME)...** aus, wie in der folgenden Abbildung dargestellt.
    
    ![Auswählen der Option zum Erstellen eines neuen Alias] -CNAMES (images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Auswählen der Option zum Erstellen eines neuen Alias") -CNAMES

6.  Geben Sie den **Alias Namen** und den **FQDN für SQL Server**ein, wie in der folgenden Abbildung dargestellt.
    
    ![Ausfüllen des neuen Alias-CNAME-Dialogfelds] (images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Ausfüllen des neuen Alias-CNAME-Dialogfelds")

7.  Wählen Sie **OK** aus, um den CNAME zu speichern und im DNS-Manager anzuzeigen.

</div>

<div>

## <a name="validate-database-connectivity"></a>Überprüfen der Datenbankkonnektivität

Es gibt viele verschiedene Möglichkeiten, um sicherzustellen, dass es funktioniert. Sie möchten sicherstellen, dass die SQL Server-Datenbank den angegebenen Port mithilfe des Alias abhört. Eine Schnellüberprüfung kann mithilfe der Befehle **netstat** und **Telnet** ausgeführt werden.

<div>


> [!NOTE]  
> Der Telnet-Client ist ein Feature, das im Lieferumfang von Windows Server enthalten ist, aber installiert werden muss. Sie können ein Windows Server-Feature installieren, indem Sie Server-Manager öffnen und im Menü verwalten die Option Rollen und Features hinzufügen auswählen.



</div>

**Verwenden von netstat und Telnet zur Überprüfung der Datenbankkonnektivität**

1.  Wählen Sie **Start**aus, und geben Sie **cmd** ein, um eine Eingabeaufforderung zu öffnen.

2.  Geben Sie **netstat-a-f ein**, und vergewissern Sie sich, dass SQL Server mit dem richtigen Port ausgeführt wird, wie in der folgenden Abbildung dargestellt.
    
    ![Verwenden Sie netstat, um den Port zu überprüfen.] (images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Verwenden Sie netstat, um den Port zu überprüfen.")

3.  Geben Sie den ** \<Telnet\> \<- \# Aliasnamen Port** ein, um die Verbindung mit der SQL Server-Instanz zu bestätigen. Wenn die Verbindung erfolgreich hergestellt wurde, stellt Telnet eine Verbindung her, und Sie sollten keinen Fehler sehen. Dies zeigt, dass die SQL Server-Instanz den richtigen Port mit dem richtigen Alias abhört. Wenn beim Herstellen einer Verbindung mit der SQL Server-Datenbank ein Problem auftritt, zeigt Telnet einen Fehler an, dass die Verbindung nicht hergestellt werden kann. Nachdem Sie nun die Datenbankkonnektivität auf dem Datenbankserver überprüft haben, können Sie das gleiche von lync Server (über das Netzwerk) durchführen und sicherstellen, dass keine Firewalls den Zugriff auf dem Weg blockieren.

</div>

<div>

## <a name="conclusion"></a>Fazit

Nachdem der SQL Server-Alias konfiguriert wurde, können Sie ihn zum Erstellen einer lync Server 2013-Topologie im Tool Topologie-Generator verwenden. Weitere Informationen zu Topologien finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Microsoft lync Server 2013](microsoft-lync-server-2013.md) 
-[Planung für Sicherheit in lync Server 2013](lync-server-2013-planning-for-security.md)  
[Definieren und Konfigurieren der Topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

