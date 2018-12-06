---
title: Konfigurieren eines XMPP-Gateways in Lync Server 2013
TOCTitle: Konfigurieren eines XMPP-Gateways in Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49890931
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines XMPP-Gateways in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-28_

Die letzten Schritte zum Migrieren des XMPP-Gateways bestehen aus dem Konfigurieren von Zertifikaten für den Lync Server 2013-Edgeserver, dem Bereitstellen des Lync Server 2013-XMPP-Gateways und dem Aktualisieren der DNS-Einträge für das XMPP-Gateway. Diese Schritte sollten parallel ausgeführt werden, um die Ausfallzeit des XMPP-Gateways zu minimieren. Alle Benutzer müssen in die Microsoft Lync Server 2013-Bereitstellung verschoben werden, bevor Sie diese Schritte ausführen.


> [!IMPORTANT]
> Der XMPP-Partnerverbund wird nicht für Benutzer unterstützt, die auf Survivable Branch Appliances gehostet werden. Dies gilt sowohl für die Anzeige von Anwesenheitsinformationen als auch das Austauschen von Chatnachrichten.



## Konfigurieren von XMPP-Gatewayzertifikaten auf dem Lync Server 2013-Edgeserver

1.  Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen** .
    

    > [!TIP]
    > Wenn Sie den Edgeserver zum ersten Mal bereitstellen, wird Ausführen anstelle von Erneut ausführen angezeigt.



2.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen** .

3.  Klicken Sie auf der Seite **Zertifikatsanforderung** auf **Externes Edgezertifikat** .

4.  Aktivieren Sie auf der Seite **Verzögerte oder sofortige Anforderungen** das Kontrollkästchen **Anforderung jetzt vorbereiten, jedoch später senden** .

5.  Geben Sie auf der Seite **Zertifikatsanforderungsdatei** den vollständigen Pfad und Namen der Datei ein, in der die Anforderung gespeichert werden soll (Beispiel: c:\\cert\_exernal\_edge.cer ).

6.  Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden** , um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.

7.  Führen Sie auf der Seite **Namens- und Sicherheitseinstellungen** die folgenden Aufgaben aus:
    
    1.  Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein.
    
    2.  Geben Sie im Feld **Bitlänge** die Bitlänge ein (typischerweise wird der Standardwert 2048 verwendet).
    
    3.  Stellen Sie sicher, dass das Kontrollkästchen **Privaten Schlüssel des Zertifikats als exportierbar markieren** aktiviert ist.

8.  Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).

9.  Geben Sie auf der Seite **Geografische Informationen** die Standortinformationen ein.

10. Auf der Seite **Antragstellernamen/Alternative Antragstellernamen** werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden. Wenn zusätzliche alternative Antragstellernamen erforderlich sind, werden diese in den nächsten zwei Schritten angegeben.

11. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen** das Kontrollkästchen der Domäne, um der Liste der alternativen Antragstellernamen einen Eintrag sip.\<SIP-Domäne\> hinzuzufügen.

12. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzliche alternative Antragstellernamen an, die benötigt werden.
    

    > [!TIP]
    > Falls der XMPP-Proxy installiert ist, wird standardmäßig der Domänenname (z.&nbsp;B. contoso.com ) in den SAN-Einträgen aufgefüllt. Für den Fall, dass Sie weitere Einträge benötigen, fügen Sie sie in diesem Schritt hinzu.



13. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

14. Nachdem die Befehle ausgeführt wurden, können Sie auf **Protokoll anzeigen** klicken, oder auf Weiter , um fortzufahren.

15. Auf der Seite **Zertifikatsanforderungsdatei** können Sie die generierte Datei für die Zertifikatsignieranforderung (Certificate Signing Request, CSR) durch Klicken auf **Anzeigen** anzeigen. Durch Klicken auf **Fertig stellen** können Sie den Zertifikat-Assistenten beenden.

16. Kopieren Sie die Anforderungsdatei, und senden Sie sie an die öffentliche Zertifizierungsstelle.

17. Nachdem Sie das öffentliche Zertifikate empfangen, importiert und zugewiesen haben, müssen Sie die Edgeserverdienste beenden und neu starten. Dazu geben Sie in der Lync Server-Verwaltungskonsole Folgendes ein:
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

## Konfigurieren eines neuen Lync Server 2013-XMPP-Gateways

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** , und klicken Sie dann auf **XMPP-Verbundpartner** .

3.  Klicken Sie auf **Neu** , um eine neue Konfiguration zu erstellen.

4.  Definieren Sie die folgenden Einstellungen:

5.  **Primäre Domäne**     (Erforderlich). Die primäre Domäne ist die Basisdomäne des XMPP-Verbundpartners. Beispielsweise würden Sie **fabrikam.com** für den Domänennamen des XMPP-Verbundpartners eingeben. Dieser Eintrag ist erforderlich.

6.  **Beschreibung**    Die Beschreibung dient für Notizen oder sonstige Identifikationsinformationen für diese spezielle Konfiguration. Dieser Eintrag ist optional.

7.  **Weitere Domänen**    Weitere Domänen sind jene Domänen, die Bestandteil der Domäne Ihres XMPP-Verbundpartners sind und für die XMPP-Kommunikation zulässig sein sollten. Wenn z. B. die primäre Domäne **fabrikam.com** lautet, würden Sie alle untergeordneten Domänen von fabrikam.com auflisten, mit denen Sie per XMPP kommunizieren werden.

8.  **Verbundpartnertyp**    Der **Verbundpartnertyp** ist eine erforderliche Einstellung. Sie müssen eine der folgenden Optionen auswählen, um die Kontakte, die hinzugefügt werden können, zu beschreiben und zu erzwingen. Die folgenden Optionen stehen zur Auswahl:
    
      - **Verbund**    Der Partnertyp **Verbund** stellt eine hohe Vertrauensebene zwischen der Lync Server-Bereitstellung und dem XMPP-Verbundpartner dar. Dieser Partnertyp wird für den Partnerverbund mit XMPP-Servern innerhalb desselben Unternehmens oder für Partner mit einer bestehenden Geschäftsbeziehung empfohlen. XMPP-Kontakte in Verbundpartnern können folgende Aufgaben ausführen:
        
        1.  Hinzufügen von Lync-Kontakten und Anzeigen deren Anwesenheit ohne ausdrückliche Zustimmung des Lync-Benutzers.
        
        2.  Senden von Chatnachrichten an Lync-Kontakte unabhängig davon, ob der Lync-Benutzer diese in ihrer Kontaktliste hinzugefügt hat.
        
        3.  Anzeigen der Statushinweise eines Lync-Benutzers.
    
      - **Überprüft öffentlich**    Ein Partner vom Typ **Überprüft öffentlich** ist ein öffentlicher XMPP-Anbieter, dem die Überprüfung der Identität seiner Benutzer anvertraut wird. XMPP-Kontakte in überprüften öffentlichen Netzwerken können Lync-Kontakte hinzufügen und deren Anwesenheit anzeigen sowie Chatnachrichten an sie senden, und zwar ohne ausdrückliche Zustimmung der Lync-Benutzer. XMPP-Kontakte in überprüften öffentlichen Netzwerken sehen die Statushinweise eines Lync-Benutzers nie. Diese Einstellung wird nicht empfohlen.
    
      - **Nicht überprüft öffentlich**    Ein Partner vom Typ **Nicht überprüft öffentlich** ist ein öffentlicher XMPP-Anbieter, dem die Überprüfung der Identität seiner Benutzer nicht anvertraut wird. XMPP-Benutzer in nicht überprüften öffentlichen Netzwerken können nur mit Lync-Benutzern kommunizieren, wenn der Lync-Benutzer dem ausdrücklich zugestimmt hat, indem er sie der Kontaktliste hinzufügt. XMPP-Benutzer in nicht überprüften öffentlichen Netzwerken sehen die Statushinweise von Lync-Benutzern nie. Diese Einstellung wird für jeden Partnerverbund mit öffentlichen XMPP-Anbietern wie z. B. Google Talk empfohlen.

9.  **Verbindungstyp:** Definiert die verschiedenen Regeln und Rückrufeinstellungen.
    
      - **TLS-Aushandlung**    Definiert die Regeln für die TLS-Aushandlung. Für einen XMPP-Dienst kann TLS als erforderlich, optional oder nicht unterstützt festgelegt werden. Durch die Auswahl von Optional liegt die Entscheidung für die obligatorische Aushandlung beim XMPP-Dienst. Informationen zu allen Einstellungen und Details zu SASL, TLS und zur Rückrufaushandlung - einschließlich ungültiger und fehlerhafter Konfigurationen - finden Sie unter [Aushandlungseinstellungen für XMPP-Verbundpartner in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - **Erforderlich**    Der XMPP-Dienst erfordert die TLS-Aushandlung.
        
          - **Optional**    Für den XMPP-Dienst muss TLS ausgehandelt werden.
        
          - **Nicht unterstützt**    Der XMPP-Dienst unterstützt TLS nicht.
    
      - **SASL-Aushandlung**    Definiert die Regeln für die SASL-Aushandlung. Für einen XMPP-Dienst kann SASL als erforderlich, optional oder nicht unterstützt festgelegt werden. Durch die Auswahl von Optional liegt die Entscheidung für die obligatorische Aushandlung beim XMPP-Dienst des Partners.
        
          - **Erforderlich**    Der XMPP-Dienst erfordert die SASL-Aushandlung.
        
          - **Optional**    Für den XMPP-Dienst muss SASL ausgehandelt werden.
        
          - **Nicht unterstützt**    Der XMPP-Dienst unterstützt SASL nicht.
    
      - **Konferenzaushandlung für ausgehende Verbindungen unterstützen** Für den Prozess Konferenzaushandlung für ausgehende Verbindungen unterstützen verwenden Sie DNS (Domain Name System) und einen autoritativen Server, um zu überprüfen, ob eine Anforderung von einem gültigen XMPP-Partner stammt. Dazu erstellt der Ausgangsserver eine Nachricht eines bestimmten Typs mit einem generierten Rückrufschlüssel und sucht in DNS nach dem empfangenden Server. Der Ausgangsserver sendet den Schlüssel in einem XML-Stream an die resultierende DNS-Suche, vermutlich den empfangenden Server. Nachdem der Schlüssel über den XML-Stream empfangen wurde, antwortet der empfangende Server dem Ausgangsserver nicht, sondern sendet den Schlüssel an einen bekannten autoritativen Server. Der autoritative Server überprüft, ob der Schlüssel gültig bzw. nicht gültig ist. Wenn er nicht gültig ist, antwortet der empfangende Server dem Ausgangsserver nicht. Wenn der Schüssel gültig ist, informiert der empfangende Server den Ausgangsserver, dass die Identität und der Schlüssel gültig sind, sodass die Unterhaltung beginnen kann.
        
        Für **Rückrufaushandlung** gibt es die folgenden beiden gültigen Status:
        
          - **Wahr**    Für den XMPP-Server ist konfiguriert, dass die Rückrufaushandlung verwendet wird, falls eine Anforderung von einem Ausgangsserver empfangen wird.
        
          - **Falsch**    Für den XMPP-Server ist nicht konfiguriert, dass die Rückrufaushandlung verwendet wird, und falls eine Anforderung von einem Ausgangsserver empfangen wird, wird sie ignoriert.

10. Klicken Sie auf **Commit ausführen** , um Ihre Änderungen am Standort oder an der Benutzerrichtlinie zu speichern.

## Aktualisieren von DNS-Einträgen für ein Lync Server 2013-XMPP-Gateway

1.  Wenn Sie für DNS den XMPP-Partnerverbund konfigurieren möchten, fügen Sie Ihrem externen DNS den SRV-Eintrag \_xmpp-server.\_tcp.\<Domänenname\> hinzu. Der SRV-Eintrag wird in den Zugriffsedge-FQDN des Edgeservers aufgelöst, und zwar mit dem Portwert 5269.

