---
title: 'Lync Server 2013: Beispiel für eine XMPP-Konfiguration – XMPP-Partnerverbund mit Google Talk'
TOCTitle: Beispiel für eine XMPP-Konfiguration – XMPP-Partnerverbund mit Google Talk
ms:assetid: 360a2f7b-015b-4e93-ac67-0f609c21f1a2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204807(v=OCS.15)
ms:contentKeyID: 49293654
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Eine Beispielkonfiguration für die Bereitstellung des XMPP-Proxys definiert einen Partnerverbund mit Google Talk.

## Beispiel für eine XMPP-Konfiguration – XMPP-Partnerverbund mit Google Talk

1.  Öffnen Sie auf dem Front-End-Server den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** und klicken Sie dann auf **Lync Server-Komponenten einrichten oder entfernen** . Klicken Sie auf **Erneut ausführen** .

2.  Klicken Sie unter **Lync Server-Komponenten einrichten** auf **Weiter** . Im Bild mit der Zusammenfassung wird angezeigt, welche Aktionen ausgeführt werden. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.

3.  Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** , und klicken Sie dann auf **Lync Server-Komponenten einrichten oder entfernen** . Klicken Sie auf **Erneut ausführen** .

4.  Fügen Sie Google Talk als einen zugelassenen XMPP-Partner hinzu. Google Talk unterstützt derzeit unverschlüsselte TCP-Verbindungen für den Server-zu-Server-XMPP-Partnerverbund und unterstützt nur den Serverrückruf zum Überprüfen der Identität (siehe <http://xmpp.org/extensions/xep-0220.html>).
    
        New-CsXmppAllowedPartner Google Mail.com -TlsNegotiation NotSupported -SaslNegotiation NotSupported -EnableKeepAlive $false -SupportDialbackNegotiation $true

5.  Geben Sie zum Aktivieren des Edge-Partnerverbunds Folgendes ein:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $true

6.  Klicken Sie unter **Lync Server-Komponenten einrichten** auf **Weiter** . Im Bild mit der Zusammenfassung wird angezeigt, welche Aktionen ausgeführt werden. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.

7.  Klicken Sie auf dem Edgeserver im Lync Server-Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen** .
    

    > [!TIP]
    > Wenn Sie den Edgeserver zum ersten Mal bereitstellen, wird Ausführen anstelle von Erneut ausführen angezeigt.



8.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen** .

9.  Klicken Sie auf der Seite **Zertifikatsanforderung** auf **Externes Edgezertifikat** .

10. Aktivieren Sie auf der Seite **Verzögerte oder sofortige Anforderungen** das Kontrollkästchen **Anforderung jetzt vorbereiten, jedoch später senden** .

11. Geben Sie auf der Seite **Zertifikatsanforderungsdatei** den vollständigen Pfad und Namen der Datei ein, in der die Anforderung gespeichert werden soll (Beispiel: c:\\cert\_exernal\_edge.cer ).

12. Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden** , um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.

13. Führen Sie auf der Seite **Namens- und Sicherheitseinstellungen** die folgenden Aufgaben aus:
    
    1.  Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein.
    
    2.  Geben Sie im Feld **Bitlänge** die Bitlänge ein (typischerweise wird der Standardwert **2048** verwendet).
    
    3.  Stellen Sie sicher, dass das Kontrollkästchen **Privaten Schlüssel des Zertifikats als "Exportierbar" markieren** aktiviert ist.

14. Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).

15. Geben Sie auf der Seite **Geografische Informationen** die Standortinformationen ein.

16. Auf der Seite **Antragstellername/Alternative Antragstellernamen** werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden. Wenn zusätzliche alternative Antragstellernamen erforderlich sind, werden diese in den nächsten zwei Schritten angegeben.

17. Wählen Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen** das Kontrollkästchen der Domäne, um einen Eintrag "sip. *\<SIP-Domäne\>* " zur Liste der alternativen Antragstellernamen hinzuzufügen.

18. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzliche alternative Antragstellernamen an, die benötigt werden.
    

    > [!TIP]
    > Falls der XMPP-Proxy installiert ist, wird standardmäßig der Domänenname (z.&nbsp;B. contoso.com ) in den SAN-Einträgen aufgefüllt. Für den Fall, dass Sie weitere Einträge benötigen, fügen Sie sie in diesem Schritt hinzu.



19. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

20. Nachdem die Befehle ausgeführt wurden, können Sie auf **Protokoll anzeigen** oder auf **Weiter** klicken, um den Vorgang fortzusetzen.

21. Auf der Seite **Zertifikatsanforderungsdatei** können Sie die generierte Datei für die Zertifikatsignieranforderung (Certificate Signing Request, CSR) durch Klicken auf **Anzeigen** anzeigen. Durch Klicken auf **Fertig stellen** können Sie den Zertifikat-Assistenten beenden.

22. Kopieren Sie die Anforderungsdatei, und senden Sie sie an die öffentliche Zertifizierungsstelle.

23. Nachdem Sie das öffentliche Zertifikat erhalten, importiert und zugewiesen haben, müssen Sie die Edgeserverdienste stoppen und neu starten. Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.. Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein:
    ```
        Stop-CsWindowsService
    ```
    ```
        Start-CsWindowsService
    ```

24. Um DNS für den XMPP-Partnerverbund zu konfigurieren, fügen Sie den folgenden SRV-Eintrag zum externen DNS hinzu:\_xmpp-server.\_tcp. *\<Domänenname\>* Der SRV-Eintrag wird in den Zugriffs-Edge-FQDN des Edgeservers mit einem Portwert von 5269 aufgelöst.

25. Konfigurieren Sie eine neue externe Zugriffsrichtlinie, um alle Benutzer zu aktivieren, indem Sie die Lync Server-Verwaltungsshell auf einem Front-End-Server öffnen und Folgendes eingeben:
    
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAccess $true -EnablePublicCloudAccess $true
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic

