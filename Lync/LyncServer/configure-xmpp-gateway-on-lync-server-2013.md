---
title: Konfigurieren des XMPP-Gateways auf lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60896937432df17bb743a0feafc187cbf7d9df61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Konfigurieren des XMPP-Gateways auf lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-28_

Die letzten Schritte zur Migration Ihres XMPP-Gateways sind das Konfigurieren von Zertifikaten für die lync Server 2013 Edgeserver, Bereitstellen des lync Server 2013 XMPP-Gateways und Aktualisieren der DNS-Einträge für das XMPP-Gateway. Diese Schritte sollten parallel ausgeführt werden, um die Ausfallzeit Ihres XMPP-Gateways zu minimieren. Alle Benutzer müssen zu Ihrer Microsoft lync Server 2013-Bereitstellung verschoben werden, bevor Sie diese Schritte ausführen.

<div class=" ">


> [!IMPORTANT]  
> Der XMPP-Verbund wird für Benutzer, die in Survivable Branch Appliances verwaltet werden, nicht unterstützt. Dies gilt sowohl für das Anzeigen von Anwesenheitsinformationen als auch für den Austausch von Chatnachrichten.



</div>

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

14. Nachdem die Befehle ausgeführt wurden, können Sie auf **Protokoll anzeigen** oder auf Weiter klicken, um den Vorgang fortzusetzen.

15. Auf der Seite **Zertifikatsanforderungsdatei** können Sie die Signieranforderung für das Zertifikat (CSR-Datei) anzeigen, indem Sie auf **Anzeigen** klicken. Oder beenden Sie den Zertifikat-Assistenten, indem Sie auf **Fertig stellen** klicken.

16. Kopieren Sie die Datei mit der Signieranforderung für das Zertifikat, und übermitteln Sie sie an Ihre öffentliche Zertifizierungsstelle.

17. Nachdem das öffentliche Zertifikat empfangen, importiert und zugewiesen wurde, müssen Sie die Edgeserverdienste beenden und neu starten. Geben Sie in der Lync Server-Verwaltungskonsole dazu Folgendes ein:
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

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
    
      - **Partnerverbund**   ein **Verbund** Partnertyp stellt eine hohe Vertrauensebene zwischen der lync Server-Bereitstellung und dem XMPP-Partner dar.Dieser Partnertyp wird für Verbunde mit XMPP-Servern in demselben Unternehmen oder bei Verwendung einer festen Geschäftsbeziehung empfohlen.Für XMPP-Kontakte bestehen unter "Verbund" folgende Möglichkeiten:
        
        1.  Hinzufügen von Lync-Kontakten und Anzeigen der Anwesenheit ohne Schnellautorisierung durch den Lync-Benutzer
        
        2.  Senden von Chatnachrichten an Lync-Kontakte (unabhängig davon, ob der Lync-Benutzer diese seiner Kontaktliste hinzugefügt hat)
        
        3.  Anzeigen der Statusinformationen von Lync-Benutzern
    
      - **Public**   verifyed ein **öffentlich überprüfter** Partner ist ein öffentlicher XMPP-Anbieter, der als vertrauenswürdig eingestuft wird, um die Identität seiner Benutzer zu überprüfen.XMPP-Kontakte in Netzwerken vom Typ "Überprüft öffentlich" können Lync-Kontakte hinzufügen, ihre Anwesenheit anzeigen und ihnen Chatnachrichten ohne Schnellautorisierung durch die Lync-Benutzer senden.XMPP-Kontakte in Netzwerken vom Typ "Überprüft öffentlich" können jedoch keine Statusinformationen von Lync-Benutzern anzeigen.Diese Einstellung ist nicht zu empfehlen.
    
      - **Public unverifyed**   ein **öffentlicher nicht überprüfter** Partner ist ein öffentlicher XMPP-Anbieter, der nicht vertrauenswürdig ist, um die Identität seiner Benutzer zu überprüfen.XMPP-Benutzer in Netzwerken vom Typ "Nicht überprüft öffentlich" können mit Lync-Benutzern nur kommunizieren, wenn der Lync-Benutzer sie per Hinzufügung zur Kontaktliste ausdrücklich dazu autorisiert hat.XMPP-Benutzer in Netzwerken vom Typ "Nicht überprüft öffentlich" können keine Statusinformationen von Lync-Benutzern anzeigen.Diese Einstellung ist für Verbunde mit öffentlichen XMPP-Anbietern wie Google Talk zu empfehlen.

9.  **Verbindungstyp:** Dient zum Definieren der verschiedenen Regeln und Rückrufeinstellungen.
    
      - **TLS-Aushandlung**   definiert die TLS-Aushandlungs Regeln. Ein XMPP-Dienst kann TLS erfordern, kann TLS optional machen, oder Sie definieren, dass TLS nicht unterstützt wird. Bei Auswahl von optional wird die Anforderung für eine obligatorische Aushandlungs Entscheidung für den XMPP-Dienst erfüllt. Um alle möglichen Einstellungen und Details für SASL, TLS und Rückruf-Aushandlung – einschließlich nicht gültiger und bekannter Fehler Konfigurationen – anzuzeigen, finden Sie weitere Informationen unter [Aushandlungs Einstellungen für XMPP-Verbundpartner in lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Erforderlich**   der XMPP-Dienst erfordert TLS-Aushandlung.
        
          - <span></span>  
            **Optional**   der XMPP-Dienst gibt an, dass TLS für die Verhandlung obligatorisch ist.
        
          - <span></span>  
            **Nicht unterstützt**   der XMPP-Dienst unterstützt keine TLS-Daten.
    
      - **Die SASL-Aushandlung**   definiert die SASL-Aushandlungs Regeln. Ein XMPP-Dienst kann SASL erfordern, kann SASL optional machen, oder Sie definieren, dass SASL nicht unterstützt wird. Wenn Sie die Option optional auswählen, bleibt die Anforderung bis zum Partner-XMPP-Dienst für eine obligatorische-zu-Aushandlungs Entscheidung.
        
          - <span></span>  
            **Erforderlich**   der XMPP-Dienst erfordert SASL-Aushandlung.
        
          - <span></span>  
            **Optional**   der XMPP-Dienst gibt an, dass SASL für die Aushandlung erforderlich ist.
        
          - <span></span>  
            **Nicht unterstützt**   der XMPP-Dienst unterstützt SASL nicht.
    
      - **Unterstützung für Server-Rückruf Verhandlung** Der Rückruf-Aushandlungsprozess des Support Servers verwendet das DNS (Domain Name System) und einen autorisierenden Server, um zu überprüfen, ob die Anforderung von einem gültigen XMPP-Partner stammt. Hierzu erstellt der Ausgangsserver eine Meldung eines bestimmten Typs mit einem generierten Rückrufschlüssel und schlägt den empfangenden Server im DNS nach. Der Ausgangsserver sendet den Schlüssel in einem XML-Datenstrom an den resultierenden DNS-Lookup, wahrscheinlich an den empfangenden Server. Wenn der Schlüssel über den XML-Datenstrom empfangen wird, antwortet der empfangende Server dem Ausgangsserver nicht, sondern sendet den Schlüssel aber an einen bekannten autoritativen Server. Der autoritative Server überprüft die Gültigkeit des Schlüssels. Wenn der Schlüssel nicht gültig ist, antwortet der empfangende Server dem Ausgangsserver nicht. Wenn der Schlüssel gültig ist, informiert der empfangende Server den Ausgangsserver, dass die Identität und der Schlüssel gültig sind und dass die Unterhaltung beginnen kann.
        
        Für die **Rückrufaushandlung** gibt es zwei gültige Statusangaben:
        
          - <span></span>  
            **True**   der XMPP-Server ist für die Verwendung der Rückruf-Aushandlung konfiguriert, wenn eine Anforderung von einem ursprünglichen Server empfangen werden soll.
        
          - <span></span>  
            **False**   der XMPP-Server ist nicht für die Verwendung der Rückruf-Aushandlung konfiguriert, und wenn eine Anforderung von einem ursprünglichen Server empfangen werden soll, wird Sie ignoriert.

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

