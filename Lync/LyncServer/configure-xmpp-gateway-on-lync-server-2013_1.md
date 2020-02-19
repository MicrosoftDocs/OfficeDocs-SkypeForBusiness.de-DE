---
title: Konfigurieren des XMPP-Gateways auf lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e1b9134b1dd1c22fed888d409dd9ea21c9877ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Konfigurieren des XMPP-Gateways auf lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Beim Konfigurieren von Richtlinien für die Unterstützung von XMPP-Verbundpartnern (extensible Messaging and Presence Protocol) gelten die Richtlinien für Benutzer von XMPP-Partnerverbunddomänen, aber nicht für Benutzer von SIP (Session Initiation Protocol)-Chatdienstanbietern (z. B. Windows Live) oder von SIP-Partnerverbunddomänen. Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Partnerverbunddomäne, der Ihre Benutzer Kontakte hinzufügen und mit der sie kommunizieren sollen können. Sobald die Richtlinien vorhanden sind, umfassen zusätzliche Aufgaben das Konfigurieren der XMPP-Gateway-Zertifikate, die Bereitstellung des lync Server 2013 XMPP-Gateways und das schließliche Aktualisieren der DNS-Einträge für das XMPP-Gateway.

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Konfigurieren von XMPP-Gatewayzertifikaten auf dem Lync Server 2013-Edgeserver

1.  Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen**.
    
    <div class=" ">
    

    > [!TIP]  
    > Wenn Sie den Edgeserver zum ersten Mal bereitstellen, wird anstelle von "Erneut ausführen" die Option "Ausführen" angezeigt.

    
    </div>

2.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatanforderung erstellen**.

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **Externes Edgezertifikat**.

4.  Aktivieren Sie auf der Seite **Verzögerte oder sofortige Anforderung** das Kontrollkästchen **Anforderung jetzt vorbereiten, jedoch später senden**.

5.  Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: Zertifikat "\_Edge. cer").

6.  Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden**, um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.

7.  Führen Sie auf der Seite **Namens- und Sicherheitseinstellungen** die folgenden Aufgaben aus:
    
    1.  Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein.
    
    2.  Geben Sie unter **Bitlänge** die Bitlänge ein (normalerweise wird der Standardwert 2048 verwendet).
    
    3.  Stellen Sie sicher, dass das Kontrollkästchen **Privaten Schlüssel des Zertifikats als exportierbar markieren** aktiviert ist.

8.  Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).

9.  Geben Sie auf der Seite **Geografische Informationen** die Standortinformationen ein.

10. Auf der Seite **Antragstellername/Alternative Antragstellernamen** werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden. Wenn zusätzliche alternative Antragstellernamen erforderlich sind, werden diese in den nächsten zwei Schritten angegeben.

11. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen (SANs)** das Kontrollkästchen Domäne, um ein SIP hinzuzufügen. \<sipdomain "\> -Eintrag zur Liste der alternativen Antragstellernamen.

12. Geben Sie auf der Seite **Zusätzliche alternative Antragstellernamen konfigurieren** zusätzliche alternative Antragstellernamen an, die benötigt werden.
    
    <div class=" ">
    

    > [!TIP]  
    > Bei der Installation des XMPP-Proxys wird in den Einträgen für den alternativen Antragstellernamen standardmäßig der Domänenname (z. B. contoso.com) gefüllt. Wenn Sie weitere Einträge benötigen, fügen Sie diese in diesem Schritt ein.

    
    </div>

13. Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

14. Nachdem die Ausführung der Befehle abgeschlossen ist, können Sie die Option **Protokoll anzeigen ** verwenden oder auf **Weiter** klicken, um fortzufahren.

15. Auf der Seite **Zertifikatsanforderungsdatei** können Sie die erstellte Datei für Signieranforderung für das Zertifikat anzeigen, indem Sie auf "Anzeigen" klicken, oder Sie können den Zertifikat-Assistenten beenden, indem Sie auf **Fertig stellen** klicken.

16. Kopieren Sie die Anforderungsdatei, und übermitteln Sie diese an Ihre öffentliche Zertifizierungsstelle.

17. Nachdem das öffentliche Zertifikat empfangen, importiert und zugewiesen wurde, müssen Sie die Edgeserverdienste beenden und neu starten. Geben Sie in der Lync Server-Verwaltungskonsole dazu Folgendes ein:
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Konfigurieren eines neuen Lync Server 2013-XMPP-Gateways

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund- und
externer Zugriff** und dann auf **XMPP-Verbundpartner**.

3.  Klicken Sie auf **Neu**, um eine neue Konfiguration zu erstellen.

4.  Definieren Sie die folgenden Einstellungen:

5.  **Primäre Domäne**     (erforderlich). Die primäre Domäne ist die Basisdomäne des XMPP-Partners. Sie können beispielsweise **fabrikam.com** als Domänennamen für den XMPP-Partner eingeben. Dies ist ein erforderlicher Eintrag.

6.  **Description**   die Beschreibung ist für Notizen oder andere identifizierende Informationen für diese bestimmte Konfiguration. Dieser Eintrag ist optional.

7.  **Zusätzliche**   Domänen zusätzliche Domänen sind Domänen, die Bestandteil der Domäne Ihres XMPP-Partners sind, die als Teil der zulässigen XMPP-Kommunikation einbezogen werden sollte. Wenn die primäre Domäne z. B. **fabrikam.com** lautet, führen Sie alle anderen Domänen von "fabrikam.com" auf, mit denen Sie per XMPP kommunizieren möchten.

8.  **Partnertyp**   der **Partnertyp** ist eine erforderliche Einstellung. Wählen Sie eine der folgenden Optionen aus, um zu beschreiben und vorzugeben, welche Kontakte hinzugefügt werden können. Die Optionen lauten:
    
      - **Verbund** Ein **Verbund** Partnertyp stellt eine hohe Vertrauensebene zwischen der lync Server-Bereitstellung und dem XMPP-Partner dar.Dieser Partnertyp wird für Verbunde mit XMPP-Servern in demselben Unternehmen oder bei Verwendung einer festen Geschäftsbeziehung empfohlen.Für XMPP-Kontakte bestehen unter "Verbund" folgende Möglichkeiten:
        
        1.  Hinzufügen von Lync-Kontakten und Anzeigen der Anwesenheit ohne Schnellautorisierung durch den Lync-Benutzer
        
        2.  Senden von Chatnachrichten an Lync-Kontakte (unabhängig davon, ob der Lync-Benutzer diese seiner Kontaktliste hinzugefügt hat)
        
        3.  Anzeigen der Statusinformationen von Lync-Benutzern
    
      - **Public** verifyed ein **öffentlich überprüfter** Partner ist ein öffentlicher XMPP-Anbieter, der als vertrauenswürdig eingestuft wird, um die Identität seiner Benutzer zu überprüfen.XMPP-Kontakte in Netzwerken vom Typ "Überprüft öffentlich" können Lync-Kontakte hinzufügen, ihre Anwesenheit anzeigen und ihnen Chatnachrichten ohne Schnellautorisierung durch die Lync-Benutzer senden.XMPP-Kontakte in Netzwerken vom Typ "Überprüft öffentlich" können jedoch keine Statusinformationen von Lync-Benutzern anzeigen.Diese Einstellung ist nicht zu empfehlen.
    
      - **Nicht überprüft öffentlich**   Ein Partner vom Typ **Nicht überprüft öffentlich** ist ein öffentlicher XMPP-Anbieter, der nicht über die Vertrauenswürdigkeit zum Überprüfen der Identität seiner Benutzer verfügt. XMPP-Benutzer in Netzwerken vom Typ "Nicht überprüft öffentlich" können mit Lync-Benutzern nur kommunizieren, wenn der Lync-Benutzer sie per Hinzufügung zur Kontaktliste ausdrücklich dazu autorisiert hat. XMPP-Benutzer in Netzwerken vom Typ "Nicht überprüft öffentlich" können keine Statusinformationen von Lync-Benutzern anzeigen. Diese Einstellung ist für Verbunde mit öffentlichen XMPP-Anbietern wie Google Talk zu empfehlen.

9.  **Verbindungstyp:** Dient zum Definieren der verschiedenen Regeln und Rückrufeinstellungen.
    
      - **TLS-Aushandlung**   definiert die TLS-Aushandlungs Regeln. Ein XMPP-Dienst kann TLS erfordern, kann TLS optional machen, oder Sie definieren, dass TLS nicht unterstützt wird. Bei Auswahl von optional wird die Anforderung für eine obligatorische Aushandlungs Entscheidung für den XMPP-Dienst erfüllt. Anzeigen aller möglichen Einstellungen und Details für SASL-, TLS-und Rückruf-Aushandlung – einschließlich nicht gültiger und bekannter Fehler Konfigurationen – Informationen finden Sie unter [Aushandlungs Einstellungen für XMPP-Verbundpartner in lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)
        
           - **Erforderlich**   der XMPP-Dienst erfordert TLS-Aushandlung.
        
           - **Optional**   der XMPP-Dienst gibt an, dass TLS für die Verhandlung obligatorisch ist.
        
           - **Nicht unterstützt**   der XMPP-Dienst unterstützt keine TLS-Daten.
    
      - **Die SASL-Aushandlung**   definiert die SASL-Aushandlungs Regeln. Ein XMPP-Dienst kann SASL erfordern, kann SASL optional machen, oder Sie definieren, dass SASL nicht unterstützt wird. Wenn Sie die Option optional auswählen, bleibt die Anforderung bis zum Partner-XMPP-Dienst für eine obligatorische-zu-Aushandlungs Entscheidung.
        
           - **Erforderlich**   der XMPP-Dienst erfordert SASL-Aushandlung.
        
           - **Optional**   der XMPP-Dienst gibt an, dass SASL für die Aushandlung erforderlich ist.
        
           - **Nicht unterstützt**   der XMPP-Dienst unterstützt SASL nicht.
    
      - **Unterstützung für Server-Rückruf Verhandlung** Der Rückruf-Aushandlungsprozess des Support Servers verwendet das DNS (Domain Name System) und einen autorisierenden Server, um zu überprüfen, ob die Anforderung von einem gültigen XMPP-Partner stammt. Hierzu erstellt der Ausgangsserver eine Meldung eines bestimmten Typs mit einem generierten Rückrufschlüssel und schlägt den empfangenden Server im DNS nach. Der Ausgangsserver sendet den Schlüssel in einem XML-Datenstrom an den resultierenden DNS-Lookup, wahrscheinlich an den empfangenden Server. Wenn der Schlüssel über den XML-Datenstrom empfangen wird, antwortet der empfangende Server dem Ausgangsserver nicht, sondern sendet den Schlüssel aber an einen bekannten autoritativen Server. Der autoritative Server überprüft die Gültigkeit des Schlüssels. Wenn der Schlüssel nicht gültig ist, antwortet der empfangende Server dem Ausgangsserver nicht. Wenn der Schlüssel gültig ist, informiert der empfangende Server den Ausgangsserver, dass die Identität und der Schlüssel gültig sind und dass die Unterhaltung beginnen kann.
        
        Für die **Rückrufaushandlung** gibt es zwei gültige Statusangaben:
        
           - **True**   der XMPP-Server ist für die Verwendung der Rückruf-Aushandlung konfiguriert, wenn eine Anforderung von einem ursprünglichen Server empfangen werden soll.
        
           - **False**   der XMPP-Server ist nicht für die Verwendung der Rückruf-Aushandlung konfiguriert, und wenn eine Anforderung von einem ursprünglichen Server empfangen werden soll, wird Sie ignoriert.

10. Klicken Sie auf **Commit ausführen**, um die Änderungen an der Standort- oder Benutzerrichtlinie zu speichern.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Aktualisieren der DNS-Einträge für das Lync Server 2013-XMPP-Gateway

1.  Um DNS für den XMPP-Verbund zu konfigurieren, fügen Sie den folgenden SRV-Eintrag zu\_Ihrem externen DNS hinzu: XMPP-Server. \_TCP. \<Domänenname\> der SRV-Eintrag wird in den Zugriffs-Edge-FQDN des Edgeserver mit dem Portwert 5269 aufgelöst.

</div>

</div>

<span> </span>

</div>

</div>

</div>

