---
title: 'Lync Server 2013: Einrichten eines XMPP-Partnerverbunds'
TOCTitle: Einrichten eines XMPP-Partnerverbunds
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204939(v=OCS.15)
ms:contentKeyID: 49294160
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten eines XMPP-Partnerverbunds in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-12-03_

Zum Bereitstellen des XMPP-Proxys auf dem Edgeserver müssen Sie den Edgeserver für XMPP-Verbund konfigurieren. Führen Sie dazu die folgenden Schritte aus:

## Einrichten eines XMPP-Partnerverbunds

1.  Melden Sie sich auf dem Computer, auf dem der Lync Server-Bereitstellungs-Assistent installiert ist, als Mitglied der Gruppen "Domänen-Admins" und "RTCUniversalServerAdmins" an.

2.  Öffnen Sie auf dem Front-End-Server den Assistenten für die Lync Server-Bereitstellung. Klicken Sie auf "Lync Server-System installieren oder aktualisieren", und klicken Sie dann auf "Lync Server-Komponenten einrichten oder entfernen". Klicken Sie auf "Erneut ausführen".

3.  Klicken Sie unter **Lync Server-Komponenten einrichten** auf **Weiter** . Auf dem Zusammenfassungsbild werden die ausgeführten Aktionen angezeigt. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.

4.  Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** , und klicken Sie dann auf **Lync Server-Komponenten einrichten oder entfernen** . Klicken Sie auf **Erneut ausführen** .

5.  Klicken Sie unter **Lync Server-Komponenten einrichten** auf **Weiter** . Auf dem Zusammenfassungsbild werden die ausgeführten Aktionen angezeigt. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.

6.  Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben Schritt 3: Zertifikate anfordern, installieren oder zuweisen auf Erneut ausführen.
    

    > [!TIP]
    > Wenn Sie den Edgeserver zum ersten Mal bereitstellen, wird Ausführen anstelle von Erneut ausführen angezeigt.



7.  Klicken Sie auf der Seite Verfügbare Zertifikataufgaben auf Neue Zertifikatsanforderung erstellen.

8.  Klicken Sie auf der Seite Zertifikatsanforderung auf Externes Edgezertifikat.

9.  Aktivieren Sie auf der Seite Verzögerte oder sofortige Anforderungen das Kontrollkästchen Anforderung jetzt vorbereiten, jedoch später senden.

10. Geben Sie auf der Seite Zertifikatsanforderungsdatei den vollständigen Pfad und Namen der Datei ein, in der die Anforderung gespeichert werden soll (Beispiel: c:\\cert\_exernal\_edge.cer).

11. Aktivieren Sie auf der Seite Alternative Zertifikatvorlage angeben das Kontrollkästchen Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden, um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.

12. Führen Sie auf der Seite Namens- und Sicherheitseinstellungen die folgenden Aufgaben aus:
    
    1.  Geben Sie im Feld "Anzeigename" einen Anzeigenamen für das Zertifikat ein.
    
    2.  Geben Sie im Feld "Bitlänge" die Bitlänge ein (für gewöhnlich wird der Standardwert 2048 verwendet).
    
    3.  Stellen Sie sicher, dass das Kontrollkästchen "Privaten Schlüssel des Zertifikats als 'Exportierbar' markieren" aktiviert ist.

13. Geben Sie auf der Seite "Organisationsinformationen" den Namen für die Organisation und Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).

14. Geben Sie auf der Seite "Geografische Informationen" die Angaben zum Standort ein.

15. Auf der Seite "Antragstellername/Alternative Antragstellernamen" werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden. Wenn zusätzliche alternative Antragstellernamen erforderlich sind, werden Sie diese in den nächsten zwei Schritten angegeben.

16. Aktivieren Sie auf der Seite SIP-Domäneneinstellung für alternative Antragstellernamen das Kontrollkästchen der Domäne, um der Liste der alternativen Antragstellernamen einen Eintrag sip.\<SIP-Domäne\> hinzuzufügen.

17. Geben Sie auf der Seite "Zusätzliche alternative Antragstellernamen konfigurieren" alle erforderlichen zusätzlichen alternativen Antragstellernamen an.
    

    > [!TIP]
    > Falls der XMPP-Proxy installiert ist, wird standardmäßig der Domänenname (z.&nbsp;B. contoso.com ) in den SAN-Einträgen aufgefüllt. Für den Fall, dass Sie weitere Einträge benötigen, fügen Sie sie in diesem Schritt hinzu.



18. Überprüfen Sie auf der Seite Zusammenfassung über Zertifikatsanforderungen die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

19. Nachdem die Befehle ausgeführt wurden, können Sie auf Protokoll anzeigen klicken, oder auf Weiter, um fortzufahren.

20. Auf der Seite Zertifikatsanforderungsdatei können Sie die generierte Datei für die Zertifikatsignieranforderung (Certificate Signing Request, CSR) durch Klicken auf Anzeigen anzeigen. Durch Klicken auf Fertig stellen können Sie den Zertifikat-Assistenten beenden.

21. Kopieren Sie die Anforderungsdatei, und senden Sie sie an die öffentliche Zertifizierungsstelle.

22. Nachdem Sie das öffentliche Zertifikate empfangen, importiert und zugewiesen haben, müssen Sie die Edgeserverdienste beenden und neu starten. Dazu geben Sie in der Lync Server-Verwaltungskonsole Folgendes ein:
    
        Stop-CsWindowsService

       &nbsp;
    
        Start-CsWindowsService

23. Zum Konfigurieren von DNS für XMPP-Verbund fügen Sie dem externen DNS den folgenden SRV-Eintrag hinzu:\_xmpp-server.\_tcp.\<Domänenname\>. Der SRV-Eintrag wird in den Zugriffsedge-FQDN des Edgeservers mit einem Portwert von 5269 aufgelöst. Zusätzlich können Sie einen 'A'-Host-Eintrag konfigurieren (z. B. "xmpp.contoso.com"), der auf die IP-Adresse des Zugriffsedge-Servers zeigt.
    

    > [!IMPORTANT]
    > Wenn bei Ihnen Edgepools an mehreren Standorten vorhanden sind, sollten Sie auch mehrere SRV-Einträge für XMPP-Verbund hinzufügen. Fügen Sie für jeden in Ihrer Organisation vorhandenen Edgepool einen SRV-Eintrag hinzu, und legen Sie dabei für jeden SRV-Eintrag eine andere Priorität fest. Wenn alle Edgepools ausgeführt werden, werden alle XMPP-Anforderungen von dem Edgepool mit der ersten Priorität bearbeitet. Sollte dieser Edgepool jedoch ausfallen, brauchen Sie keinen neuen SRV-Eintrag hinzuzufügen, um wieder einen XMPP-Verbund zu erhalten.



24. Konfigurieren Sie eine neue Richtlinie, die allen Benutzern den externen Zugriff ermöglicht. Öffnen Sie dazu auf dem Front-End die Lync Server-Verwaltungsshell, und geben Sie Folgendes ein:
    
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true

       &nbsp;
    
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true

       &nbsp;
    
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
    
    So ermöglichen Sie XMPP-Zugriff für externe Benutzer:
    
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true

       &nbsp;
    
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true

25. Öffnen Sie auf dem Edgeserver, auf dem der XMPP-Proxy bereitgestellt ist, eine Eingabeaufforderung oder eine Windows PowerShell™-Befehlszeilenschnittstelle, und geben Sie Folgendes ein:
    
        Netstat -ano | findstr 5269

       &nbsp;
    
        Netstat -ano | findstr 23456
    
    Der Befehl **netstat \\endash ano** ist ein Netzwerkstatistikbefehl. Der Parameter **\\endash ano** gibt an, dass Netstat alle Verbindungen und Überwachungsports anzeigen soll, wobei Adresse und Port in numerischer Form aufgeführt sein sollen und zu jeder Verbindung die ID des besitzenden Prozesses angegeben sein soll. Das Zeichen **|** ist ein Pipe-Zeichen, das eine Weiterleitung zum nächsten Befehl \\endash **findstr** (d. h. "Zeichenfolge suchen") \\endash festlegt. Die Zahlen 5269 und 23456, die als Parameter an findstr übergeben werden, weisen findstr an, in der Ausgabe des Netstat-Befehls nach den Zeichenfolgen "5269" und "23456" zu suchen. Wenn XMPP korrekt konfiguriert ist, sollten diese Befehle bewirken, dass alle hergestellten Verbindungen sowohl in der externen (Port 5269) als auch der internen (Port 23456) Schnittstelle des Edgeservers überwacht werden.
    
    Wenn die Befehle keine hergestellten Verbindungen oder Überwachungsports auf 5269 und 23456 zurückgeben, müssen Sie Folgendes überprüfen:

## Behandlung von Problemen bei XMPP-Verbund

1.  Gehen Sie wie folgt vor, um festzustellen, ob der XMPP-Proxy ausgeführt wird:

2.  Melden Sie sich bei dem Edgeserver, auf dem der XMPP-Proxydienst ausgeführt wird, als Mitglied der lokalen Administratorengruppe an.

3.  Klicken Sie nacheinander auf **Start** , **Alle Programme** , **Verwaltung** und **Dienste** .

4.  Suchen Sie in "Dienste" den Lync Server-XMPP-Translating-Gatewayproxy. Der Dienst sollte **Gestartet** sein. Wenn nicht, klicken Sie auf der Symbolleiste auf das Symbol **Starten** . Das Symbol wird als ein grüner Rechtspfeil angezeigt.

5.  Überzeugen Sie sich, dass der Dienst **Gestartet** ist. Wenn alles ordnungsgemäß ist, schließen Sie **Dienste** , und setzen Sie den Vorgang fort.
    
    Wenn der Dienst nicht ordnungsgemäß gestartet ist, öffnen Sie in "Verwaltung" die "Ereignisanzeige", und überprüfen Sie die Fehlermeldungen und Warnungen im Bereich **Lync Server** unter **Anwendungs- und Dienstprotokolle** .

6.  Sobald der Dienst **Lync Server-XMPP-Translating-Gateway** ausgeführt wird, können Sie die oben verwendeten Netstat-Befehle erneut überprüfen. Wenn keine hergestellten oder Überwachungssitzungen angezeigt werden, überprüfen Sie, ob die **XMPP-Verbundroute** im Topologie-Generator ordnungsgemäß konfiguriert ist.

7.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

8.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

9.  Wählen Sie im Topologie-Generator den Standort für die XMPP-Verbundroute aus, und überprüfen Sie, ob in der **Zuweisung der Partnerverbundroute des Standorts** bei **XMPP-Verbund** Ihr Edgeserver oder Edgepool als Zuweisung für die XMPP-Verbundroute ausgewählt ist.
    
    Wenn die Routenzuweisung fehlerhaft oder nicht festgelegt ist, klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten** . Aktivieren Sie das Kontrollkästchen "XMPP-Verbund", und wählen Sie dann den korrekten Edgeserver oder Edgepool aus.

10. Veröffentlichen Sie die Topologie. Einzelheiten dazu finden Sie unter [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-your-topology.md).
    

    > [!TIP]
    > Obgleich für gewöhnlich nicht erforderlich, sollten Sie die Edgeserver neu starten.



11. Überprüfen Sie mit der oben gezeigten Netstat-Methode, ob der Edgeserver jetzt Port 5269 und Port 23456 überwacht oder Sitzungen dafür aufgebaut hat.

12. Sollten weiterhin keine der erwarteten Sitzungen angezeigt werden, überprüfen Sie die "Ereignisanzeige" auf mögliche Ursachen für das Kommunikationsproblem.

## Siehe auch

#### Aufgaben

[Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Weitere Ressourcen

[Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

