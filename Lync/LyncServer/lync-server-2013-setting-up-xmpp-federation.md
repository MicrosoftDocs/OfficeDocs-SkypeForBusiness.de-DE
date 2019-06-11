---
title: 'Lync Server 2013: Einrichten eines XMPP-Partnerverbunds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cda79f7b80d6f1bbdf2163ecf987f4a05949bfc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Einrichten eines XMPP-Partnerverbunds in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-12-03_

Wenn Sie den XMPP-Proxy auf dem Edgeserver bereitstellen möchten, müssen Sie den Edgeserver für die XMPP-Föderation konfigurieren. Führen Sie dazu die folgenden Schritte aus.

<div>

## <a name="setting-up-xmpp-federation"></a>Einrichten von XMPP Federation

1.  Melden Sie sich bei dem Computer an, auf dem der lync Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.

2.  Öffnen Sie auf dem Front-End-Server den lync Server-Bereitstellungs-Assistenten. Klicken Sie auf lync Server System installieren oder aktualisieren und dann auf lync Server-Komponenten einrichten oder entfernen. Klicken Sie erneut auf ausführen.

3.  Klicken Sie bei der Installation von lync Server-Komponenten auf Weiter. Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.

4.  Öffnen Sie auf dem Edgeserver den lync Server-Bereitstellungs-Assistenten. Klicken Sie auf lync Server System installieren oder aktualisieren und dann auf lync Server-Komponenten einrichten oder entfernen. Klicken Sie erneut auf ausführen.

5.  Klicken Sie bei der Installation von lync Server-Komponenten auf Weiter. Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.

6.  Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten auf erneut ausführen.
    
    <div class=" ">
    

    > [!TIP]  
    > Wenn Sie den Edgeserver zum ersten Mal bereitstellen, wird Run anstelle von Run erneut angezeigt.

    
    </div>

7.  Klicken Sie auf der Seite Verfügbare Zertifikataufgaben auf Neue Zertifikatsanforderung erstellen.

8.  Klicken Sie auf der Seite Zertifikatanforderung auf externes Zertifikat.

9.  Aktivieren Sie auf der Seite verzögerte oder sofortige Anforderung das Kontrollkästchen Anforderung jetzt vorbereiten, aber später senden.

10. Geben Sie auf der Seite Zertifikatanforderungsdatei den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: CERT,\_"Edge. cer").

11. Aktivieren Sie auf der Seite Alternative Zertifikatvorlage angeben für das Kontrollkästchen Alternative Zertifikatvorlage für die ausgewählte Zertifizierungsstelle verwenden, um eine andere Vorlage als die standardmäßige Webservervorlage zu verwenden.

12. Führen Sie auf der Seite  Namens- und Sicherheitseinstellungen  die folgenden Aufgaben aus:
    
    1.  Geben Sie unter Anzeigename einen Anzeigenamen für das Zertifikat ein.
    
    2.  Geben Sie in Bit length die Bit-Länge an (in der Regel der Standardwert von 2048).
    
    3.  Überprüfen, ob das Kontrollkästchen "Zertifikat privater Schlüssel als exportierbar kennzeichnen" aktiviert ist

13. Geben Sie auf der Seite Organisationsinformationen den Namen für die Organisation und die Organisationseinheit ein (beispielsweise eine Abteilung oder Abteilung).

14. Geben Sie auf der Seite geographische Informationen die Standortinformationen an.

15. Auf der Seite Betreffname/Subject Alternative Names werden die Informationen angezeigt, die automatisch vom Assistenten ausgefüllt werden sollen. Wenn zusätzliche Alternative Namen für Subjekte benötigt werden, geben Sie diese in den nächsten beiden Schritten an.

16. Aktivieren Sie in der SIP-Domäneneinstellung auf der Seite Subject Alternate Names (SANs) das Kontrollkästchen Domäne, um einen SIP hinzuzufügen. \<sipdomain\> -Eintrag in der Liste Subject Alternative Names.

17. Geben Sie auf der Seite Configure additional Subject Alternative Names die zusätzlichen alternativen Subjektnamen an, die erforderlich sind.
    
    <div class=" ">
    

    > [!TIP]  
    > Wenn der XMPP-Proxy installiert ist, wird standardmäßig der Domänenname (wie contoso.com) in den San-Einträgen ausgefüllt. Wenn Sie weitere Einträge benötigen, fügen Sie Sie in diesem Schritt hinzu.

    
    </div>

18. Überprüfen Sie auf der Seite Anforderungszusammenfassung die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

19. Nachdem die Befehle ausgeführt wurden, können Sie das Protokoll anzeigen oder auf Weiter klicken, um fortzufahren.

20. Auf der Seite Zertifikatanforderungsdatei können Sie die generierte CSR-Datei (Certificate Signing Request) anzeigen, indem Sie auf Fertig stellen klicken oder den Zertifikat-Assistenten verlassen.

21. Kopieren Sie die Anforderungsdatei, und senden Sie Sie an Ihre öffentliche Zertifizierungsstelle.

22. Nachdem Sie das öffentliche Zertifikat empfangen, importiert und zugewiesen haben, müssen Sie die Edgeserver-Dienste beenden und neu starten. Hierzu geben Sie in der lync Server-Verwaltungskonsole Folgendes ein:
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

23. Zum Konfigurieren von DNS für die XMPP-Föderation fügen Sie den folgenden SRV-Eintrag zu\_externem DNS hinzu: XMPP-Server. \_TCP. \<Domänenname\> der SRV-Eintrag wird in den Access-Edge-FQDN des Edge-Servers mit einem Portwert von 5269 aufgelöst. Darüber hinaus konfigurieren Sie einen "A"-Hosteintrag (beispielsweise xmpp.contoso.com), der auf die IP-Adresse des Access Edge-Servers verweist.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Wenn Sie über Edge-Pools an mehreren Standorten verfügen, empfehlen wir, dass Sie mehrere SRV-Einträge für die XMPP-Föderation hinzufügen. Fügen Sie einen SRV-Eintrag für jeden Edge-Pool in Ihrer Organisation hinzu, und geben Sie jedem dieser SRV-Einträge eine andere Priorität. Wenn alle Edge-Pools ausgeführt werden, werden alle XMPP-Anforderungen vom Edge-Pool mit der ersten Priorität verarbeitet, doch wenn dieser Edge-Pool ausfällt, müssen Sie keinen neuen SRV-Eintrag hinzufügen, um die Funktion der XMPP-Föderation wiederherzustellen.

    
    </div>

24. Konfigurieren Sie eine neue Richtlinie für den externen Zugriff, um alle Benutzer zu aktivieren, indem Sie die lync Server-Verwaltungsshell auf dem Front-End öffnen und Folgendes eingeben:
    
       ```
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Aktivieren Sie den XMPP-Zugriff für externe Benutzer, indem Sie Folgendes eingeben:
    
       ```
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. Öffnen Sie auf dem Edgeserver, auf dem der XMPP-Proxy bereitgestellt wird, eine Eingabeaufforderung oder eine Windows PowerShell-™ Befehlszeilenschnittstelle, und geben Sie Folgendes ein:
    
       ```
        Netstat -ano | findstr 5269
       ```
    
       ```
        Netstat -ano | findstr 23456
       ```
    
    Der Befehl **netstat – ano** ist ein Netzwerkstatistik Befehl, die Parameter **– Ano-** Anforderung, dass netstat alle Verbindungen und Abhör Anschlüsse anzeigt, Adresse und Ports werden in einer numerischen Form angezeigt, und die besitzende Prozess-ID ist zugeordnet bei jeder Verbindung. Das Zeichen **|** definiert eine Pipe für den nächsten Befehl, die **findstr**oder die Suchzeichenfolge. Die Zahl 5269 und 23456, die als Parameter an findstr übergeben wird, weist findstr an, die Ausgabe von netstat für die Zeichenfolgen 5269 und 23456 zu durchsuchen. Wenn XMPP ordnungsgemäß konfiguriert ist, sollte das Ergebnis der Befehle zum Überwachen und Herstellen von Verbindungen führen, die sowohl auf dem externen (Port 5269) als auch auf den internen (Port 23456)-Schnittstellen des Edge-Servers erfolgen.
    
    Wenn die Befehle keine festgelegten oder abhörenden Ports auf 5269 und 23456 zurückgeben, überprüfen Sie Folgendes:

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Problembehandlung bei der XMPP-Föderation

1.  Gehen Sie wie folgt vor, um festzustellen, ob der XMPP-Proxy ausgeführt wird:

2.  Melden Sie sich beim Edgeserver, auf dem der XMPP-Proxy Dienst ausgeführt wird, als Mitglied der lokalen Administratorgruppe an.

3.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Verwaltung**, klicken Sie auf **Dienste** .

4.  Suchen Sie in Dienste nach lync Server XMPP übersetzen des Gateway-Proxys. Der Dienst sollte den Status " **gestartet** " aufweisen. Wenn Sie nicht gestartet wurde, klicken Sie auf der Symbolleiste auf das Symbol **Start** . Das Symbol wird als grüner, nach rechts zeigender Pfeil angezeigt.

5.  Überprüfen Sie, ob der Dienst in **Started**geändert wurde. Wenn Sie erfolgreich gestartet wurde, schließen Sie **Dienste** , und fahren Sie fort.
    
    Wenn der Dienst nicht erfolgreich gestartet wurde, öffnen Sie in den Verwaltungs Tools die Ereignisanzeige, und verweisen Sie auf die Fehler und Warnungen im **lync Server** -Abschnitt unter **Anwendungen und Dienstprotokolle**.

6.  Nachdem der **lync Server XMPP** -Konvertierungs-Gatewayserver ausgeführt wurde, überprüfen Sie die zuvor verwendeten netstat-Befehle erneut. Wenn Sie keine festgelegten oder anhörenden Sitzungen sehen, überprüfen und sicherstellen, dass die **XMPP-Föderations Route** im Topologie-Generator richtig konfiguriert ist

7.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

8.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

9.  Wählen Sie im Topologie-Generator die Website für die XMPP-Föderations Route und überprüfen aus, um zu bestätigen, dass die **Standort Verbund-Routenzuordnung** für den **XMPP-Verbund** Ihren Edge-Server oder Edge-Pool als ausgewählte XMPP-Verbund Routenzuordnung anzeigt.
    
    Wenn die Arbeitsplanzuordnung falsch ist oder nicht eingerichtet ist, klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**. Aktivieren Sie das Kontrollkästchen XMPP Federation, und wählen Sie dann den richtigen Edgeserver oder Edge-Pool aus.

10. Veröffentlichen Sie die Topologie. Ausführliche Informationen finden Sie unter [Veröffentlichen Ihrer Topologie in lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Obwohl dies nicht erforderlich ist und in der Regel nicht erforderlich ist, müssen Sie möglicherweise die Edgeserver neu starten.

    
    </div>

11. Überprüfen Sie mithilfe des zuvor verwendeten netstat-Prozesses, ob der Edgeserver jetzt zuhört oder Sitzungen auf Port 5269 und Port 23456 eingerichtet hat.

12. Wenn die erwarteten Sitzungen immer noch nicht angezeigt werden, überprüfen Sie die Ereignisanzeige auf mögliche Ursachen für das Kommunikationsproblem.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

