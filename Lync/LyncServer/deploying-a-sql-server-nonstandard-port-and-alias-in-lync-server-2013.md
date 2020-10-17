---
title: Bereitstellen eines SQL Server nicht standardmäßigen Ports und Alias in lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8721cc82651710ab5fc8158eeb6f297f80847c33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502912"
---
# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Bereitstellen eines SQL Server nicht standardmäßigen Ports und Alias in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-09-16_

Microsoft lync Server 2013 unterstützt die Verwendung eines nicht standardmäßigen Ports und Alias in SQL Server. Durch die Verwendung eines SQL Server nicht standardmäßigen Ports und eines Alias wird die Sicherheit erhöht und eine flexiblere Umgebung für die lync-Bereitstellung erstellt. Diese Schritte sind nur ein einzelner Schritt bei der ordnungsgemäßen Sicherung ihrer lync Server 2013 Umgebung. Es sollten zusätzliche Schritte unternommen werden, um die Angriffsfläche einer lync Server 2013 Implementierung zu reduzieren.

Im folgenden Artikel werden die erforderlichen Schritte zum Einrichten eines SQL Server nicht standardmäßigen Ports und Alias in lync Server 2013 beschrieben.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Bereitstellen eines SQL Server nicht Standard mäßigen Ports und Alias in lync Server 2013

Lync Server 2013 Topologie-Generator unterstützt die Verwendung eines SQL Server Alias als vollqualifizierter Domänen Name (Fully Qualified Domain Name, FQDN) anstelle des tatsächlichen SQL Server FQDN beim Konfigurieren von lync Server 2013. Dadurch kann der tatsächliche SQL Server FQDN vor böswilligen Angreifern ausgeblendet werden. Darüber hinaus wird durch die Verwendung eines nicht standardmäßigen Ports der tatsächliche Port von einem Angreifer verdeckt, der versucht, die Datenbank am Standard Port 1433 anzugreifen, wie in der folgenden Abbildung dargestellt.

![Ein Hacker kennt die angegriffene Portnummer nicht.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Ein Hacker kennt die angegriffene Portnummer nicht.")

Um bei der Bestimmung des Ports, der für die Kommunikation mit SQL Server verwendet wird, erfolgreich zu sein, müsste der Angreifer alle Ports überprüfen, um die Portinformationen zu erhalten. lync Server 2013 Eine Portüberprüfung durch einen Angreifer erhöht die Wahrscheinlichkeit, dass die Sicherheit die Anweisung erkennen und beenden kann. Zusätzlich zum Hinzufügen erhöhter Sicherheit mit einem nicht standardmäßigen Port können Sie auch einen SQL Server-Alias verwenden, um Flexibilität für die Bereitstellung bereitzustellen. Dies ist hilfreich, um Konfigurationsänderungen in Situationen zu reduzieren, in denen eine SQL Server Namensänderung erforderlich ist.

<div>


> [!NOTE]  
> SQL Server bietet zwei Fehlertoleranz Methoden (Failover-Clusterunterstützung und-Spiegelung). Beide SQL Server-Fehlertoleranz Methoden werden mit einem SQL Server nicht standardmäßigen Port und Alias mit lync Server 2013 unterstützt. Wenn sich das vom Pool verwendete SQL Server-Back-End in einer gespiegelten Konfiguration befindet, sollte der SQL-Browserdienst auf den SQL Server-Back-End-Servern für Front-End-Server ausgeführt werden, um eine Verbindung mit der gespiegelten Datenbank herzustellen, wenn die Datenbanken auf den gespiegelten SQL Server gescheitert sind.



</div>

Beim Konfigurieren SQL Serverer Datenbankkonnektivität innerhalb des Topologie-Generators oder bei Verwendung des Install-CsDatabase-Cmdlets ist es nicht möglich, explizit eine SQL Server nicht standardmäßige Portnummer zu definieren und diese einer SQL-Instanz zuzuordnen. Zum Festlegen eines nicht standardmäßigen Ports müssen Sie SQL Server-und Windows Server-Dienstprogramme verwenden.

Um einen SQL Server nicht standardmäßigen Port und Alias für die Verwendung mit lync Server 2013 einzurichten, müssen Sie drei primäre Schritte ausführen. Die folgenden Schritte sind erforderlich:

  - Vergewissern Sie sich, dass lync Server 2013 die neuesten Updates angewendet haben.

  - Richten Sie den SQL Server nicht Standard mäßigen Port und Alias ein.

  - Konfigurieren Sie lync Server 2013 mit dem SQL Server-Alias mithilfe des Topologie-Generators.

  - Veröffentlichen Sie die Topologie, und überprüfen Sie die Datenbank.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Vergewissern Sie sich, dass lync Server 2013 die neuesten Updates angewendet haben.

Es ist wichtig, lync Server 2013 auf dem neuesten Stand zu halten. Informationen zum Überprüfen der neuesten Aktualisierungen und Informationen zum Anwenden dieser Updates finden Sie unter [Updates für lync Server 2013](https://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Einrichten des SQL Server nicht Standard mäßigen Ports und Alias

Die SQL Server nicht standardmäßigen Port und Alias müssen auf der Datenbankinstanz eingerichtet werden, bevor Sie von lync Server 2013 Topologie-Generator referenziert werden kann. Um einen SQL Server nicht standardmäßigen Port und Alias einzurichten, müssen Sie drei primäre Schritte ausführen. Diese Schritte lauten wie folgt:

  - Ändern Sie die Standardwerte für TCP/IP-Protokolle.

  - Erstellen und konfigurieren Sie einen SQL Server-Alias.

  - Erstellen Sie einen CNAME-Ressourceneintrag (Domain Name System (DNS) Canonical Name).

**Ändern der Standardwerte für TCP/IP-Protokolle**

1.  Wählen Sie **Start**aus, und wählen Sie **SQL Server Konfigurations-Manager**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Das SQL Server Management Studio-Symbol](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Das SQL Server Management Studio-Symbol")

2.  Wählen Sie im Navigationsbereich aus, um die **SQL Server Instanz**zu erweitern, wählen Sie aus, um **SQL Server Netzwerkkonfiguration**zu erweitern, und wählen Sie **Protokolle für aus \<instance name\> **, wie in der folgenden Abbildung dargestellt.
    
    ![Navigieren zu TCP/IP-Eigenschaften](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigieren zu TCP/IP-Eigenschaften")

3.  Klicken Sie im rechten Bereich mit der rechten Maustaste auf **TCP/IP**, und wählen Sie **Eigenschaften**aus. Das Dialogfeld TCP/IP-Eigenschaften wird angezeigt.

4.  Klicken Sie auf die Registerkarte **IP-Adressen** . Auf der Registerkarte IP-Adressen werden alle aktiven IP-Adressen auf dem Server angezeigt. Diese befinden sich im Format IP1, IP2, bis IPAll, wie in der folgenden Abbildung dargestellt.
    
    ![Öffnen Sie die TCP/IP-Eigenschaften.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Öffnen Sie die TCP/IP-Eigenschaften.")

5.  Deaktivieren Sie das Feld **dynamische TCP-Ports** für alle IP-Adressen. Wenn das Feld ein Nullzeichen enthält, bedeutet dies, dass SQL Server dynamische Ports überwacht. Stellen Sie sicher, dass diese Felder deaktiviert sind und keine NULL enthalten.

6.  Stellen Sie für die IP-Adresse, mit der lync Server eine Verbindung mit der Datenbank herstellen wird, sicher, dass **Enabled** auf **Ja**festgelegt ist, wie in der folgenden Abbildung dargestellt.
    
    ![Legen Sie für die richtige IP-Adresse aktiviert als Ja fest.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Legen Sie für die richtige IP-Adresse aktiviert als Ja fest.")

7.  Geben Sie im Abschnitt **IPAll** im unteren Bereich des Dialogfelds den gewünschten Port in das Feld **TCP-Port** ein, wie in der folgenden Abbildung dargestellt. In diesem Beispiel verwenden wir Port 50062, aber Sie können einen beliebigen Port zwischen 49152 und 65535 verwenden. Dabei handelt es sich um die Ports, die dynamischer und privater Nutzung zugewiesen sind, und dadurch wird sichergestellt, dass Sie nicht mit anderen Ports in der lync Server 2013-Bereitstellung in Konflikt stehen.
    
    ![Port im Abschnitt IPAll festlegen.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Port im Abschnitt IPAll festlegen.")

8.  Wählen Sie **OK** aus, um das Dialogfeld TCP/IP-Eigenschaften zu schließen.

9.  Starten Sie die SQL Server-Instanz neu, indem Sie im linken Bereich von SQL Server Configuration Manager **SQL Server Dienste** auswählen. Klicken Sie dann im rechten Bereich mit der rechten Maustaste auf ** \<instance name\> SQL Server** , und wählen Sie **neu starten**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Setzen Sie beispielsweise den SQL Server Dienst zurück.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Setzen Sie beispielsweise den SQL Server Dienst zurück.")

<div>


> [!IMPORTANT]  
> Stellen Sie sicher, dass Sie die Firewalleinstellungen so aktualisieren, dass Sie dem neuen SQL Server-Port entsprechen.



</div>

**Erstellen und Konfigurieren eines SQL Server Alias**

1.  Wählen Sie **Start**aus, und wählen Sie **SQL Server Konfigurations-Manager**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Das SQL Server Management Studio-Symbol](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Das SQL Server Management Studio-Symbol")

2.  Wählen Sie im linken Bereich **SQL Server Instanz**erweitern aus, und wählen Sie aus, um die **SQL Native Client- \<version\> Konfiguration**zu erweitern, und wählen Sie dann **Aliase**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Aliase in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliase in SQL Server Configuration Manager.")

3.  Klicken Sie mit der rechten Maustaste auf **Aliase**, und wählen Sie **Neuer Alias**aus.

4.  Geben Sie den **Alias Namen**, die **Port Nummer**, das **Protokoll**und den **Server**ein, wie in der folgenden Abbildung dargestellt.
    
    ![Erstellen eines neuen Alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Erstellen eines neuen Alias")
    
    <div>
    

    > [!CAUTION]  
    > Stellen Sie sicher, dass Sie denselben nicht standardmäßigen Port eingeben, den Sie im vorherigen Schritt verwendet haben, da dies der Port ist, auf dem SQL Server überwacht wird. Wenn ein konfigurierter Alias eine Verbindung mit dem falschen SQL Server FQDN oder einer Instanz herstellt, deaktivieren Sie das zugehörige Netzwerkprotokoll, und aktivieren Sie es dann erneut. Dadurch werden alle zwischengespeicherten Verbindungsinformationen gelöscht, und der Client kann eine ordnungsgemäße Verbindung herstellen.

    
    </div>

**Erstellen eines DNS-CNAME-Ressourceneintrags**

1.  Melden Sie sich beim Computer an, der DNS verwaltet.

2.  Wählen Sie **Start**aus, und wählen Sie **Server-Manager**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Öffnen des Server-Managers](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Öffnen des Server-Managers")

3.  Wählen Sie die Dropdownliste **Tools** aus, und wählen Sie **DNS**aus, wie in der folgenden Abbildung dargestellt.
    
    ![Öffnen von DNS im Server-Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Öffnen von DNS im Server-Manager.")

4.  Erweitern Sie im linken Bereich den Knoten Servername, erweitern Sie den Knoten Forward-Nachschlage Zonen, und wählen Sie die entsprechende Domäne aus.

5.  Klicken Sie mit der rechten Maustaste auf die Domäne, und wählen Sie **New Alias (CNAME)...** aus, wie in der folgenden Abbildung dargestellt.
    
    ![Auswählen der Option zum Erstellen eines neuen Alias-CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Auswählen der Option zum Erstellen eines neuen Alias-CNAME")

6.  Geben Sie den **Alias Namen** und den **FQDN für SQL Server**ein, wie in der folgenden Abbildung dargestellt.
    
    ![Füllen Sie das Dialogfeld Neuer Alias-CNAME aus.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Füllen Sie das Dialogfeld Neuer Alias-CNAME aus.")

7.  Wählen Sie **OK** aus, um den CNAME zu speichern und im DNS-Manager anzuzeigen.

</div>

<div>

## <a name="validate-database-connectivity"></a>Überprüfen der Datenbankkonnektivität

Es gibt viele verschiedene Möglichkeiten, um sicherzustellen, dass es funktioniert. Sie möchten sicherstellen, dass die SQL Server Datenbank den angegebenen Port mithilfe des Alias überwacht. Eine Schnellüberprüfung kann mit den Befehlen **netstat** und **Telnet** abgeschlossen werden.

<div>


> [!NOTE]  
> Der Telnet-Client ist ein Feature, das mit Windows Server ausgeliefert wird, aber installiert werden muss. Ein Windows Server-Feature kann installiert werden, indem Sie Server-Manager öffnen und im Menü verwalten die Option Rollen und Features hinzufügen auswählen.



</div>

**Verwenden von netstat und Telnet zum Überprüfen der Datenbankkonnektivität**

1.  Wählen Sie **Start**, und geben Sie **cmd** ein, um eine Eingabeaufforderung zu öffnen.

2.  Geben Sie **netstat-a-f ein**, und bestätigen Sie, dass SQL Server mit dem korrekten Port läuft, wie in der folgenden Abbildung dargestellt.
    
    ![Verwenden von netstat zum Überprüfen des Ports.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Verwenden von netstat zum Überprüfen des Ports.")

3.  Geben **Sie \<alias name\> \<port \#\> Telnet** ein, um die Verbindung mit der SQL Server Instanz zu bestätigen. Wenn die Verbindung erfolgreich hergestellt wurde, stellt Telnet eine Verbindung her, und es sollte kein Fehler angezeigt werden. Dies zeigt, dass die SQL Server Instanz den korrekten Port mit dem korrekten Alias überwacht. Wenn beim Herstellen einer Verbindung mit der SQL Server Datenbank ein Problem auftritt, zeigt Telnet einen Fehler an, bei dem die Verbindung nicht hergestellt werden kann. Nachdem Sie nun die Datenbankkonnektivität auf dem Datenbankserver überprüft haben, können Sie dasselbe von lync Server (über das Netzwerk) durchführen und sicherstellen, dass keine Firewalls den Zugriff auf dem Weg blockieren.

</div>

<div>

## <a name="conclusion"></a>Schlussbemerkung

Nachdem der SQL Server-Alias konfiguriert wurde, können Sie ihn verwenden, um eine lync Server 2013 Topologie im Topologie-Generator-Tool zu erstellen. Weitere Informationen zu Topologien finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Microsoft lync Server 2013](microsoft-lync-server-2013.md)  
 [Planen der Sicherheit in lync Server 2013](lync-server-2013-planning-for-security.md)  
[Definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

