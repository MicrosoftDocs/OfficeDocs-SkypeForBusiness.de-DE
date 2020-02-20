---
title: 'Lync Server 2013: Einrichten des XMPP-Verbunds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec4b696fd482ec9b37d952aaa955a47fbde4747
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Einrichten des XMPP-Verbunds in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-03_

Um den XMPP-Proxy im Edgeserver bereitzustellen, müssen Sie die Edgeserver für XMPP-Verbund konfigurieren. Hierzu führen Sie die folgenden Schritte aus.

<div>

## <a name="setting-up-xmpp-federation"></a>Einrichten des XMPP-Verbunds

1.  Melden Sie sich an dem Computer an, auf dem der lync Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.

2.  Öffnen Sie auf dem Front-End-Server den Assistenten für die lync Server-Bereitstellung. Klicken Sie auf "Lync Server-System installieren oder aktualisieren", und klicken Sie anschließend auf "Lync Server-Komponenten einrichten oder entfernen". Klicken Sie auf "Erneut ausführen".

3.  Klicken Sie unter "Lync Server-Komponenten einrichten" auf "Weiter". Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Nachdem Sie die Bereitstellung durchgeführt haben, klicken Sie auf "Protokoll anzeigen", um verfügbare Protokolldateien anzuzeigen. Klicken Sie auf "Fertig stellen", um die Bereitstellung abzuschließen.

4.  Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf "Lync Server-System installieren oder aktualisieren", und klicken Sie anschließend auf "Lync Server-Komponenten einrichten oder entfernen". Klicken Sie auf "Erneut ausführen".

5.  Klicken Sie unter "Lync Server-Komponenten einrichten" auf "Weiter". Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Nachdem Sie die Bereitstellung durchgeführt haben, klicken Sie auf "Protokoll anzeigen", um verfügbare Protokolldateien anzuzeigen. Klicken Sie auf "Fertig stellen", um die Bereitstellung abzuschließen.

6.  Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben Schritt 3: Zertifikate anfordern, installieren oder zuweisen auf Erneut ausführen.
    
    <div class=" ">
    

    > [!TIP]  
    > Wenn Sie den Edgerserver zum ersten Mal bereitstellen, sehen Sie die Schaltfläche Ausführen anstatt Erneut ausführen.

    
    </div>

7.  Klicken Sie auf der Seite Verfügbare Zertifikataufgaben auf Neue Zertifikatanforderung erstellen.

8.  Klicken Sie auf der Seite Zertifikatanforderung auf Externes Edgezertifikat.

9.  Aktivieren Sie auf der Seite Verzögerte oder sofortige Anforderung das Kontrollkästchen Anforderung jetzt vorbereiten, jedoch später senden.

10. Geben Sie auf der Seite Zertifikatanforderungsdatei den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: Zertifikat "\_Edge. cer").

11. Aktivieren Sie auf der Seite Alternative Zertifikatvorlage angeben das Kontrollkästchen Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden, um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.

12. Führen Sie auf der Seite Namens- und Sicherheitseinstellungen die folgenden Aufgaben aus:
    
    1.  Geben Sie im Feld Anzeigename einen Anzeigenamen für das Zertifikat ein.
    
    2.  Geben Sie im Feld Bitlänge die Bitlänge ein (typischerweise wird der Standardwert 2048 verwendet).
    
    3.  Stellen Sie sicher, dass das Kontrollkästchen Privaten Schlüssel des Zertifikats als "Exportierbar" markieren aktiviert ist.

13. Geben Sie auf der Seite Organisationsinformationen den Namen für die Organisation und Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).

14. Geben Sie auf der Seite Geografische Informationen die Standortinformationen ein.

15. Auf der Seite Antragstellername/Alternative Antragstellernamen werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden. Wenn zusätzliche alternative Antragstellernamen erforderlich sind, werden diese in den nächsten zwei Schritten angegeben.

16. Aktivieren Sie auf der Seite SIP-Domäneneinstellung für alternative Antragstellernamen (SANs) das Kontrollkästchen Domäne, um ein SIP hinzuzufügen. \<sipdomain "\> -Eintrag zur Liste der alternativen Antragstellernamen.

17. Geben Sie auf der Seite zusätzliche Alternative Antragstellernamen konfigurieren zusätzliche Alternative Antragstellernamen an, die erforderlich sind.
    
    <div class=" ">
    

    > [!TIP]  
    > Bei der Installation des XMPP-Proxys wird in den Einträgen für den alternativen Antragstellernamen standardmäßig der Domänenname (z. B. contoso.com) gefüllt. Wenn Sie weitere Einträge benötigen, fügen Sie diese in diesem Schritt ein.

    
    </div>

18. Überprüfen Sie auf der Seite Anforderungszusammenfassung die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

19. Nachdem die Befehle ausgeführt wurden, können Sie auf Protokoll anzeigen oder auf Weiter klicken, um den Vorgang fortzusetzen.

20. Auf der Seite Zertifikatsanforderungsdatei können Sie die Signieranforderung für das Zertifikat (CSR-Datei) anzeigen, indem Sie auf Anzeigen klicken. Oder beenden Sie den Zertifikat-Assistenten, indem Sie auf Fertig stellen klicken.

21. Kopieren Sie die Anforderungsdatei, und übermitteln Sie diese an Ihre öffentliche Zertifizierungsstelle.

22. Nachdem das öffentliche Zertifikat empfangen, importiert und zugewiesen wurde, müssen Sie die Edgeserverdienste beenden und neu starten. Geben Sie in der Lync Server-Verwaltungskonsole dazu Folgendes ein:
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. Um DNS für den XMPP-Verbund zu konfigurieren, fügen Sie den folgenden SRV-Eintrag\_zu externem DNS hinzu: XMPP-Server. \_TCP. \<Domänenname\> der SRV-Eintrag wird in den Zugriffs-Edge-FQDN des Edgeserver mit dem Portwert 5269 aufgelöst. Darüber hinaus konfigurieren Sie einen "A"-Hosteintrag (beispielsweise xmpp.contoso.com), der auf die IP-Adresse des Access-Edgeserver verweist.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Wenn Sie über Edge-Pools an mehreren Standorten verfügen, wird empfohlen, dass Sie mehrere SRV-Einträge für den XMPP-Partnerverbund hinzufügen. Fügen Sie für jede Edgepool in Ihrer Organisation einen SRV-Eintrag hinzu, und geben Sie jedem dieser SRV-Einträge eine andere Priorität. Wenn alle Edge-Pools ausgeführt werden, werden alle XMPP-Anforderungen von der Edgepool mit der ersten Priorität verarbeitet, aber wenn dieser Edgepool ausfällt, müssen Sie keinen neuen SRV-Eintrag hinzufügen, um die XMPP-Verbund Funktionalität wiederherzustellen.

    
    </div>

24. Konfigurieren Sie eine neue Richtlinie für den externen Zugriff, um alle Benutzer zu aktivieren, indem Sie die lync Server-Verwaltungsshell auf dem Front-End öffnen und Folgendes eingeben:
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Aktivieren Sie XMPP-Zugriff für externe Benutzer, indem Sie Folgendes eingeben:
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. Öffnen Sie auf dem Edgeserver, in dem der XMPP-Proxy bereitgestellt wird, eine Eingabeaufforderung oder eine Windows PowerShell™ Befehlszeilenschnittstelle, und geben Sie Folgendes ein:
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    Der Befehl **netstat – ano** ist ein Befehl "Netzwerkstatistik", die Parameter **– Ano-** Anforderung, dass netstat alle Verbindungen und Abhör-Ports, die Adresse und die Ports anzeigen, in numerischer Form angezeigt werden, und dass der besitzenden Prozess-ID jeder Verbindung zugeordnet ist. Das Zeichen **|** definiert eine Pipe für die nächste Befehls-, **findstr**-oder Find-Zeichenfolge. Die Zahl 5269 und 23456, die an findstr als Parameter übergeben wird, weist findstr an, die Ausgabe von netstat für die Zeichenfolgen 5269 und 23456 zu durchsuchen. Wenn XMPP ordnungsgemäß konfiguriert ist, sollte das Ergebnis der Befehle zum hören und zum Herstellen von Verbindungen führen, sowohl auf der externen (Port 5269) als auch auf den internen Schnittstellen (Port 23456) des Edgeserver.
    
    Wenn die Befehle keine festgelegten oder abhörenden Ports an 5269 und 23456 zurückgeben, überprüfen Sie Folgendes:

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Problembehandlung beim XMPP-Verbund

1.  Gehen Sie folgendermaßen vor, um festzustellen, ob der XMPP-Proxy aktiv ist:

2.  Melden Sie sich bei dem Edgeserver, auf dem der XMPP-Proxy Dienst läuft, als Mitglied der lokalen Administratorgruppe an.

3.  Klicken Sie im **Startmenü**auf **Alle Programme**, dann auf **Verwaltung**und dann auf **Dienste** .

4.  Suchen Sie in Dienste nach lync Server XMPP-Übersetzungs Gateway-Proxy. Der Dienst sollte den Status **gestartet** aufweisen. Wenn er nicht gestartet wurde, klicken Sie in der Symbolleiste auf das Symbol **Start** . Das Symbol wird als grüner, nach rechts zeigender Pfeil angezeigt.

5.  Stellen Sie sicher, dass der Dienst in **gestartet**geändert wurde. Wenn er erfolgreich gestartet wurde, schließen Sie **Dienste** , und fahren Sie fort.
    
    Wenn der Dienst nicht erfolgreich gestartet wurde, öffnen Sie in der Verwaltungs Tools die Ereignisanzeige, und lesen Sie die Fehler und Warnungen im Abschnitt **lync Server** unter **Anwendungs-und Dienstprotokolle**.

6.  Nachdem der **lync Server XMPP-Übersetzungs Gateway** -Dienst aktiv ist, überprüfen Sie die zuvor verwendeten netstat-Befehle erneut. Wenn Sie keine festgelegten oder Überwachungssitzungen sehen, überprüfen und sicherstellen, dass die **XMPP-Verbund Route** ordnungsgemäß im Topologie-Generator konfiguriert ist

7.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

8.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

9.  Wählen Sie im Topologie-Generator den Standort für die XMPP-Verbund Route aus, und überprüfen Sie, um zu bestätigen, dass die **Standort Verbund-Routen Zuweisung** für **XMPP-Verbund** ihre Edgeserver oder Edgepool als ausgewählte XMPP-Verbund Routen Zuweisung anzeigt.
    
    Wenn die Routen Zuweisung falsch oder nicht festgelegt ist, klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie auf **Eigenschaften bearbeiten**. Aktivieren Sie das Kontrollkästchen XMPP Federation, und wählen Sie dann die richtige Edgeserver oder Edgepool aus.

10. Veröffentlichen Sie die Topologie. Ausführliche Informationen finden Sie unter [Veröffentlichen Ihrer Topologie in lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Obwohl dies nicht erforderlich ist und in der Regel nicht erforderlich ist, müssen Sie die Edgeserver möglicherweise neu starten.

    
    </div>

11. Überprüfen Sie mithilfe des zuvor verwendeten netstat-Prozesses, ob der Edgeserver nun Sitzungen auf Port 5269 und Port 23456 überwacht oder eingerichtet hat.

12. Wenn die erwarteten Sitzungen immer noch nicht angezeigt werden, überprüfen Sie die Ereignisanzeige auf mögliche Ursachen für das Kommunikationsproblem.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Verwalten von XMPP-Verbundpartnern in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

