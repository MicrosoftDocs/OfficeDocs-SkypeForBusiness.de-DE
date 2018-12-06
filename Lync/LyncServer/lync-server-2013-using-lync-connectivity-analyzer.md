---
title: Verwenden der Lync-Verbindungsanalyse
TOCTitle: Verwenden der Lync-Verbindungsanalyse
ms:assetid: 954953fb-0c7a-4fd5-8acd-68ecb59b20af
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ907302(v=OCS.15)
ms:contentKeyID: 52056388
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden der Lync-Verbindungsanalyse

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Mithilfe der Microsoft Lync-Verbindungsanalyse können Lync-Administratoren festlegen, ob die Bereitstellung und Konfiguration ihrer Office 365- oder lokalen Lync Server-Umgebung den Anforderungen für die Unterstützung von Verbindungen von Windows Store-App für Lync- und Lync-Apps auf mobilen Geräten erfüllt.

Die Lync-Verbindungsanalyse versucht, eine Verbindung mit Ihrer lokalen Lync Server-Umgebung oder Skype for Business Onlineherzustellen, indem dieselben Dienste und Protokolle verwendet werden, die auch von Windows Store-App für Lync und Lync Mobile-Apps verwendet werden. Sie können die Verbindungstests über Ihr internes Netzwerk oder über ein externes Netzwerk durchführen, das mit Lync Server oder Skype for Business Online verbunden ist. Die Lync-Verbindungsanalyse bietet einen Bericht mit ausführlichen Informationen zu jedem Verbindungsschritt, anhand dessen Sie Ihre Konfiguration überprüfen und Verbindungsprobleme beheben können.

Mit der Lync-Verbindungsanalyse werden folgende Lync Server-Komponenten getestet:

  - AutoErmittlungsdienst

  - Authentifizierungsbrokerdienst (Reach)

  - Mobilitätsdienst (MCX)

  - Mobilitätsdienst (UCWA)

  - WebTicket-Dienst

Mit der Lync-Verbindungsanalyse wird die Konfiguration folgender weiterer Komponenten gestestet:

  - Veröffentlichung von DNS-Einträgen für AutoErmittlungs-URLs

  - Zertifikate

  - Proxyserver

Sie können die Lync-Verbindungsanalyse aus dem Microsoft Download Center unter <http://go.microsoft.com/fwlink/?linkid=277056> herunterladen.

## So analysieren Sie Ihre Verbindung

1.  Geben Sie die Anmeldeinformationen für ein gültiges Lync-Konto ein (entweder für ein lokales Lync-Konto oder für ein Office 365Lync-Konto), das vom Tool zum Testen der Verbindung verwendet wird:
    
      - Wählen Sie unter **Lync-KontotypOffice 365** oder **Lokal** aus.
    
      - Geben Sie in **SIP-URI** die SIP-Anmeldeadresse für die Lync-Verbindung im Format <strong>benutzer@domäne.com</strong> ein.
    
      - Geben Sie in **Kennwort** das Kennwort für dieses Konto ein.
    
      - Geben Sie in **Benutzername (optional)** ggf. einen Benutzernamen ein. Der Benutzername wird auch als "Benutzerprinzipalname" (User Principal Name, UPN) bezeichnet. Wenn der Benutzername dem SIP-URI entspricht, müssen Sie keinen Benutznamen eingeben. Unterscheidet er sich jedoch, geben Sie den Benutzernamen im Format <strong>benutzer@domäne.com</strong> oder **domäne\\benutzer** ein.
    
      - Wählen Sie unter **Netzwerkzugriff** die Option **Innerhalb meiner Organisation**, wenn Sie die Lync-Verbindungsanalyse auf einem mit Ihrem internen Netzwerk verbundenen Computer ausführen. Wählen Sie andernfalls **Extern (Internet)**. Die Lync-Verbindungsanalyse führt immer interne und externe Tests durch, aber mit der Angabe, ob Sie sich innerhalb oder außerhalb Ihres Netzwerks befinden, kann das Tool ermitteln, ob bestimmte Fehler zu erwarten sind.
    
      - Wählen Sie unter **Client** aus, ob Verbindungstests für die **Lync Windows Store-App**, die **Lync Mobile 2010-App** oder die **Lync Mobile 2013-App** durchgeführt werden sollen.
    
      - Wählen Sie unter **Serverermittlung** den Typ des durchzuführenden Tests aus:
        
          - Wenn das Tool den Lync-Server automatisch ermitteln soll, wählen Sie **Automatisch** aus.
        
          - Wenn das Tool den AutoErmittlungs-Test umgehen soll, oder wenn Ihnen der Name des Servers bekannt ist, mit dem eine Verbindung hergestellt werden soll, wählen Sie **Manuell zu verwendende Adresse** aus, und geben Sie den vollqualifizierten Domänennamen (FQDN) des Lync-Servers an – z. B. **lync.company.com**.

2.  (Optional) Aktivieren Sie das Kontrollkästchen unter **Protokolldatei**, wenn Sie eine Protokolldatei unter dem angegebenen Pfad erstellen möchten. Wenn die Protokollierung aktiviert ist, klicken Sie auf **Löschen**, um die Protokolldatei zu löschen, klicken Sie auf **Öffnen**, um die Protokolldatei zu öffnen und anzuzeigen, klicken Sie auf **E-Mail**, um eine E-Mail-Nachricht zu öffnen, um die Ergebnisse an Ihr Supportteam zu senden (Sie müssen die Protokolldatei vom angegebenen Pfad manuell anhängen).

3.  Klicken Sie auf **Start**.

Die folgende Abbildung zeigt Beispielergebnisse der Lync-Verbindungsanalyse.

**Lync-Verbindungsanalyse**

![Screenshot der Lync-Verbindungsanalyse](images/JJ907302.a7cc0abe-fac2-4691-a7d8-9ffef59cdee5(OCS.15).png "Screenshot der Lync-Verbindungsanalyse")

## Mit der Lync-Verbindungsanalyse getestete Komponenten

Die Lync-Verbindungsanalyse versucht, den Lync-Server zu ermitteln und eine Verbindung herzustellen, indem dieselben Schritte wie für die Windows Store-App für Lync und Lync Mobile-Apps verwendet werden. Die Tests werden gemäß der Beschreibung in diesem Abschnitt durchgeführt.

Bei der Auswahl von **Automatische Ermittlung** führt die Lync-Verbindungsanalyse folgende Aktionen durch:

  - Abfrage des DNS (Domain Name Service) nach AutoErmittlungs-URLs.

  - Ermittlungsversuch durch Verwendung des gesicherten internen Kanals. Beispiel: **HTTPS://lyncdiscoverinternal.company.com/**.

  - Ermittlungsversuch durch Verwendung des ungesicherten internen Kanals. Beispiel: **HTTP://lyncdiscoverinternal.company.com/**.

  - Ermittlungsversuch durch Verwendung des gesicherten externen Kanals. Beispiel: **HTTPS://lyncdiscover.company.com**.

  - Ermittlungsversuch durch Verwendung des ungesicherten externen Kanals. Beispiel: **HTTP://lyncdiscover.company.com**.

Bei der Auswahl von **Folgende Serverermittlungsadresse verwenden**führt die Lync-Verbindungsanalyse folgende Aktionen durch:

  - Abfrage des DNS nach dem FQDN des Servers.

  - Ermittlungsversuch durch Verwendung des gesicherten Kanals. Beispiel: **HTTPS://serverFQDN/**.

  - Ermittlungsversuch durch Verwendung des ungesicherten Kanals. Beispiel: **HTTP://serverFQDN/**.

Wenn unter **Voraussetzungen testen für** die Option **Lync-Windows Store-App** ausgewählt ist, führt die Lync-Verbindungsanalyse folgende Aktionen durch:

  - Überprüft die Verfügbarkeit des WebTicket-Diensts und testet die Authentifizierung der Lync-Kontoanmeldeinformationen.

  - Überprüft, ob der Authentifizierungsbrokerdienst (Reach) verfügbar ist.

Wenn die **Lync Mobile 2010-App** unter **Client** ausgewählt ist, führt die Lync-Verbindungsanalyse die folgenden Aktionen durch:

  - Überprüft die Verfügbarkeit des WebTicket-Diensts und testet die Authentifizierung der Lync-Kontoanmeldeinformationen.

  - Überprüft, ob der Mobilitätsdienst (MCX) verfügbar ist.

Wenn die **Lync Mobile 2013-App** unter **Client** ausgewählt ist, führt die Lync-Verbindungsanalyse die folgenden Aktionen durch:

  - Überprüft die Verfügbarkeit des WebTicket-Diensts und testet die Authentifizierung der Lync-Kontoanmeldeinformationen.

  - Überprüft, ob der Mobilitätsdienst (UCWA) verfügbar ist.

Während der Durchführung dieser Tests überprüft die Lync-Verbindungsanalyse die Zertifikate, die auf Lync Server, Hardwaregeräten zum Lastenausgleich, Proxyservern und dem Computer installiert sind, auf dem die Tests ausgeführt werden.

## Weitere Ressourcen

Microsoft bietet auch die Microsoft Remote-Verbindungsanalyse, ein webbasiertes Verbindungstesttool, das unter <https://testconnectivity.microsoft.com/> verfügbar ist. Die Lync-Verbindungsanalyse und die Remote-Verbindungsanalyse unterscheiden sich wie folgt:

  - Mit der Remote-Verbindungsanalyse kann die Verbindung neben Microsoft Lync auch für Microsoft Exchange und Outlook gestestet werden.

  - Mit der Remote-Verbindungsanalyse wir die SIP-Anmeldung durchgeführt, während mit derLync-Verbindungsanalyse nur die Kontoanmeldeinformationen überprüft werden, die Anmeldung aber nicht erfolgt.

  - Mit der Remote-Verbindungsanalyse werden nur Verbindungen von außerhalb des Netzwerks Ihrer Organisation gestestet, da sie auf einem öffentlichen Webserver ausgeführt wird.

  - Mit der Remote-Verbindungsanalyse wird nicht die Verfügbarkeit der Authentifizierungsbroker- (Reach), Mobilitäts- (MCX) und WebTicket-Dienste überprüft.

  - Mit der Lync-Verbindungsanalyse wird der AutoErmittlungsdienst getestet.

  - Mit der Remote-Verbindungsanalyse kann eine Verbindung mit einer beliebigen Version von Lync Server hergestellt werden, während mit der Lync-Verbindungsanalyse nur eine erfolgreiche Verbindung mit Lync Server 2010 mit den kumulativen Updates für Lync Server 2010: Februar 2012 (Mindestvoraussetzung) oder der aktuellen Version von Lync Server hergestellt werden kann.

In der folgenden Dokumentation werden die Voraussetzungen und Verfahren für die Bereitstellung und Konfiguration von Lync Server zur Unterstützung von Windows Store-App für Lync und Lync Mobile-Clients beschrieben:

  - [Bereitstellen von Clients und Geräten in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)

  - [Planen der Mobilität in Lync Server 2013](lync-server-2013-planning-for-mobility.md)

  - [Bereitstellen von Mobilität in Lync Server 2013](lync-server-2013-deploying-mobility.md)

