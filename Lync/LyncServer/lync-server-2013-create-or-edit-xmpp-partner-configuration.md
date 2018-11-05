---
title: 'Lync Server 2013: Erstellen oder Bearbeiten einer XMPP-Verbundpartnerkonfiguration'
TOCTitle: Erstellen oder Bearbeiten einer XMPP-Verbundpartnerkonfiguration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ552447(v=OCS.15)
ms:contentKeyID: 49293655
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Bearbeiten einer XMPP-Verbundpartnerkonfiguration in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Von Microsoft Lync Server 2013 wird ein XMPP-Proxy (Extensible Messaging and Presence-Protokoll) auf dem Edgeserver und ein XMPP-Gateway auf dem Front-End-Server oder im Front-End-Pool integriert. Um Verbindungen von anderen XMPP-Bereitstellungen aus zu ermöglichen, müssen Sie XMPP über die Lync Server-Systemsteuerung konfigurieren. Die Einstellungen werden auf XMPP-Domänenbasis konfiguriert. Führen Sie zum Erstellen eines neuen Partnerverbunds die folgenden Schritte aus:

## So erstellen Sie einen neuen Verbundpartner oder bearbeiten eine vorhandene Konfiguration

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund- und externer Zugriff** und dann auf **XMPP-Verbundpartner**.

4.  Klicken Sie zum Erstellen einer neuen Konfiguration auf **Neu**.

5.  Wenn Sie eine vorhandene Konfiguration bearbeiten möchten, wählen Sie die Konfiguration aus, und klicken Sie auf **Bearbeiten**.

6.  Um Konfigurationen für **XMPP-Verbundpartner** zu erstellen oder zu bearbeiten, definieren Sie die folgenden Einstellungen:

7.  **Primäre Domäne** (Erforderlich). Die primäre Domäne ist die Basisdomäne des XMPP-Verbundpartners. Beispielsweise würden Sie **fabrikam.com** für den Domänennamen des XMPP-Verbundpartners eingeben. Dieser Eintrag ist erforderlich.

8.  **Beschreibung**. Die Beschreibung ist für Notizen oder sonstige Identifikationsinformationen für diese spezielle Konfiguration vorgesehen. Dieser Eintrag ist optional.

9.  **Weitere Domänen**. Weitere Domänen sind Domänen, die zur Domäne Ihres XMPP-Verbundpartners gehören und als Teil der zulässigen XMPP-Kommunikation einbezogen werden sollen. Wenn die primäre Domäne z. B. **fabrikam.com** ist, dann würden Sie alle anderen Domänen unter fabrikam.com auflisten, mit den Sie über XMPP kommunizieren. Sie können z. B. **corp.fabrikam.com** und **it.fabrikam.com** für die XMPP-Unternehmensdomäne und die XMPP-IT-Domäne unter der XMPP-Hauptdomäne fabrikam.com eingeben.

10. **Partnertyp**. Der **Partnertyp** ist eine erforderliche Einstellung. Im dazugehörigen Dropdownmenü stehen drei Einträge zur Auswahl. Wählen Sie einen der folgenden Partnertypen aus, um zu beschreiben und zu erzwingen, welche Kontakte hinzugefügt werden können. Folgende Optionen stehen zur Verfügung:
    
      - **Verbund**. Der Partnertyp **Verbund** ist eine vertrauenswürdige Verbindung zwischen einer Lync Server- oder einer Office Communications Server 2007 R2-Partnerbereitstellung.
    
      - **Überprüft öffentlich**. Als **Überprüft öffentlich** gelten Partner, wenn Kontakte, die Teil einer Bereitstellung sind, vom Anbieter überprüft werden und der Kontaktliste Ihres Benutzer hinzugefügt werden können. Vom Lync-Benutzer können Einladungen gesendet werden oder der Lync-Benutzer kann Einladungen vom Partnerkontakt akzeptieren.
    
      - **Nicht überprüft öffentlich**. Eine Beziehung vom Typ **Nicht überprüft öffentlich** bedeutet, dass zwischen den beiden Bereitstellungen kein etablierter und überprüfbarer Status besteht. Ein Lync-Benutzer muss den nicht überprüften Kontakt einladen, damit dieser Kontakt der Kontaktliste des Lync-Benutzers hinzugefügt werden kann. So ist z. B. Google GTalk im Hinblick auf Lync Server kein öffentlich überprüfter XMPP-Dienst. Ein GTalk-Benutzer kann den Lync-Benutzer nicht als Kontakt hinzufügen, sofern der Lync-Benutzer nicht eine explizite Einladung sendet.

11. Anmerkungen zur Datenstromaushandlung und den Sicherheitsmethoden TLS (Transport Layer Security) und SASL (Software Authentication and Security Layer):
    
    Die **XMPP Standards Foundation** (XSF) und die **Internet Engineering Task Force** (IETF) definieren einen Satz von Regeln und Standards zum Verwenden und Verwalten von TLS-Clientzertifikaten, TLS-Serverzertifikaten und des SASL-Mechanismus. Das Verwenden von TLS und SASL ist zum Schützen des XMPP-Datenstroms erforderlich. Aus dem Dokument der XMPP Standards Foundation geht hervor, dass **XEP-0178** einen empfohlenen Protokollablauf für die Verwendung des SASL EXTERNAL-Mechanismus mit PKIX-Zertifikaten angibt, insbesondere wenn ein XMPP-Dienst TLS zur Aushandlung erfordert. PKIX bezieht sich gemäß der XSF-Dokumentation auf eine Public Key-Infrastruktur (kurz PKI).
    
    Im XSF-Dokument zu XEP-0178 finden Sie weitere Informationen zu den XMPP-Anforderungen. Ausführliche Informationen finden Sie im Dokument "XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates" unter <http://xmpp.org/extensions/xep-0178.html>.
    
    Lesen Sie auch den Abschnitt 5.0 "STARTTLS Negotiation" im IETF-Dokument "Extensible Messaging and Presence Protocol (XMPP): Core" unter <http://tools.ietf.org/html/rfc6120>.
    
      - **TLS-Aushandlung**. Definiert die Regeln für die TLS-Aushandlung. Für einen XMPP-Dienst kann TLS als erforderlich, optional oder nicht unterstützt festgelegt werden. Durch die Auswahl von "Optional" liegt die Entscheidung für die obligatorische Aushandlung beim XMPP-Dienst. Informationen zu allen Einstellungen sowie Details zu SASL, TLS und zur Rückrufaushandlung – einschließlich ungültiger und fehlerhafter Konfigurationen – finden Sie unter [Aushandlungseinstellungen für XMPP-Verbundpartner in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - **Erforderlich**. Für den XMPP-Dienst ist die TLS-Aushandlung erforderlich.
        
          - **Optional**. Für den XMPP-Dienst muss TLS ausgehandelt werden.
        
          - **Nicht unterstützt**. Der XMPP-Dienst unterstützt TLS nicht.
    
      - **SASL-Aushandlung**. Definiert die Regeln für die SASL-Aushandlung. Für einen XMPP-Dienst kann SASL als erforderlich, optional oder nicht unterstützt festgelegt werden. Durch die Auswahl von "Optional" liegt die Entscheidung für die obligatorische Aushandlung beim XMPP-Dienst des Partners.
        

        > [!WARNING]
        > SASL erfordert TLS. Um SASL verwenden zu können, muss TLS entweder erforderlich oder optional sein. TLS muss in jeder Konfiguration unterstützt werden, die SASL entweder als erforderlich oder optional definiert. Wenn Sie auf <STRONG>Commit ausführen</STRONG> klicken, um Ihre Änderungen zu speichern, und TLS nicht als erforderlich oder optional festgelegt haben, wird eine Warnung angezeigt. Diese besagt, dass SASL eine TLS-Unterstützung erfordert, und Ihre Änderungen werden nicht gespeichert. Legen Sie TLS auf <STRONG>Erforderlich</STRONG> oder <STRONG>Optional</STRONG> fest, um den Fehler zu beheben. Wenn die Verwendung von SASL optional und die Unterstützung der TLS-Aushandlung nicht möglich ist, müssen Sie die SASL-Aushandlung auf <STRONG>Nicht unterstützt</STRONG> festlegen. Überprüfen Sie für den XMPP-Dienst, wie die Aushandlungsdatenströme für TLS und SASL genau aussehen müssen, um eine Dienstunterbrechung zu verhindern.

        
          - **Erforderlich**. Für den XMPP-Dienst ist die SASL-Aushandlung erforderlich.
        
          - **Optional**. Für den XMPP-Dienst muss SASL ausgehandelt werden.
        
          - **Nicht unterstützt**. Der XMPP-Dienst unterstützt SASL nicht.
    
      - **Rückrufaushandlung**. Die Rückrufaushandlung ist im Dokument **XEP-220: Server Dialback** unter <http://xmpp.org/extensions/xep-0220.html> von der XSF definiert. Der Serverrückrufprozess verwendet das Domain Name System (DNS) und einen autoritativen Server, um zu überprüfen, ob die Anforderung von einem gültigen XMPP-Verbundpartner stammt. Hierzu erstellt der Ausgangsserver eine Meldung eines bestimmten Typs mit einem generierten Rückrufschlüssel und schlägt den empfangenden Server im DNS nach. Der Ausgangsserver sendet den Schlüssel in einem XML-Datenstrom an den resultierenden DNS-Lookup, wahrscheinlich an den empfangenden Server. Wenn der Schlüssel über den XML-Datenstrom empfangen wird, antwortet der empfangende Server dem Ausgangsserver nicht, sondern sendet den Schlüssel an einen bekannten autoritativen Server. Der autoritative Server überprüft die Gültigkeit des Schlüssels. Wenn der Schlüssel nicht gültig ist, antwortet der empfangende Server dem Ausgangsserver nicht. Wenn der Schlüssel gültig ist, informiert der empfangende Server den Ausgangsserver, dass die Identität und der Schlüssel gültig sind und dass die Unterhaltung beginnen kann.
        
        Für **Rückrufaushandlung** gibt es die folgenden beiden gültigen Status:
        
          - **True**. Der XMPP-Server ist für die Verwendung der Rückrufaushandlung konfiguriert, wenn eine Anforderung von einem Ausgangsserver eingeht.
        
          - **False**. Der XMPP-Server ist nicht für die Verwendung der Rückrufaushandlung konfiguriert. Wenn eine Anforderung von einem Ausgangsserver eingeht, wird sie ignoriert.

