---
title: Konfigurieren des XMPP-Gateways auf lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5874495bb7a398ab8b5b5cde6376faaa6c193a85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Konfigurieren des XMPP-Gateways auf lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Wenn Sie Richtlinien für die Unterstützung von Verbundpartnern des Extensible Messaging and Presence Protocol (XMPP) konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, nicht aber für Benutzer von SIP-Chat Diensten (im). (beispielsweise Windows Live) oder SIP-Verbunddomänen. Sie konfigurieren einen XMPP-Verbund Partner für jede XMPP-Verbunddomäne, die es Ihren Benutzern ermöglichen soll, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren. Sobald die Richtlinien vorhanden sind, umfassen zusätzliche Aufgaben die Konfiguration der XMPP-Gateway-Zertifikate, die Bereitstellung des lync Server 2013-XMPP-Gateways und schließlich das Aktualisieren der DNS-Einträge für das XMPP-Gateway.

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Konfigurieren von XMPP-Gateway-Zertifikaten auf dem lync Server 2013-Edgeserver

1.  Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.
    
    <div class=" ">
    

    > [!TIP]  
    > Wenn Sie den Edgeserver zum ersten Mal bereitstellen, wird Run anstelle von Run erneut angezeigt.

    
    </div>

2.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen**.

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **externes Zertifikat**.

4.  Aktivieren Sie auf der Seite **verzögerte oder sofortige Anforderung** das Kontrollkästchen **Anforderung jetzt vorbereiten, aber später senden** .

5.  Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: CERT,\_"Edge. cer").

6.  Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** für das Kontrollkästchen **Alternative Zertifikatvorlage für die ausgewählte Zertifizierungsstelle verwenden** , um eine andere Vorlage als die standardmäßige Webservervorlage zu verwenden.

7.  Gehen Sie auf der Seite **Name und Sicherheitseinstellungen** wie folgt vor:
    
    1.  Geben Sie unter Anzeige **Name**einen Anzeigenamen für das Zertifikat ein.
    
    2.  Geben Sie in **Bit length**die Bittiefe (in der Regel den Standardwert von 2048) an.
    
    3.  Überprüfen Sie, ob das Kontrollkästchen **Zertifikat privater Schlüssel als exportierbar kennzeichnen** aktiviert ist.

8.  Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit ein (beispielsweise eine Abteilung oder Abteilung).

9.  Geben Sie auf der Seite **geographische Informationen** die Standortinformationen an.

10. Auf der Seite **Betreffname/Subject Alternative** Names werden die Informationen angezeigt, die automatisch vom Assistenten ausgefüllt werden sollen. Wenn zusätzliche Alternative Namen für Subjekte benötigt werden, geben Sie diese in den nächsten beiden Schritten an.

11. Aktivieren Sie in der **SIP-Domäneneinstellung auf der Seite Subject Alternate Names (SANs)** das Kontrollkästchen Domäne, um einen SIP hinzuzufügen. \<sipdomain\> -Eintrag in der Liste Subject Alternative Names.

12. Geben Sie auf der Seite **configure additional Subject Alternative Names** alle zusätzlichen alternativen Subjektnamen an, die erforderlich sind.
    
    <div class=" ">
    

    > [!TIP]  
    > Wenn der XMPP-Proxy installiert ist, wird standardmäßig der Domänenname (wie contoso.com) in den San-Einträgen ausgefüllt. Wenn Sie weitere Einträge benötigen, fügen Sie Sie in diesem Schritt hinzu.

    
    </div>

13. Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

14. Nachdem die Befehle ausgeführt wurden, können Sie das **Protokoll anzeigen**oder auf **weiter** klicken, um fortzufahren.

15. Auf der Seite **Zertifikatanforderungsdatei** können Sie die generierte CSR-Datei (Certificate Signing Request) anzeigen, indem Sie auf **Fertig stellen**klicken oder den Zertifikat-Assistenten verlassen.

16. Kopieren Sie die Anforderungsdatei, und senden Sie Sie an Ihre öffentliche Zertifizierungsstelle.

17. Nachdem Sie das öffentliche Zertifikat empfangen, importiert und zugewiesen haben, müssen Sie die Edgeserver-Dienste beenden und neu starten. Hierzu geben Sie in der lync Server-Verwaltungskonsole Folgendes ein:
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Konfigurieren eines neuen lync Server 2013 XMPP-Gateways

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff** , und klicken Sie dann auf **XMPP Federated Partners**.

3.  Wenn Sie eine neue Konfiguration erstellen möchten, klicken Sie auf **neu**.

4.  Definieren Sie die folgenden Einstellungen:

5.  **Primäre Domäne**     (erforderlich). Die primäre Domäne ist die Basisdomäne des XMPP-Partners. Geben Sie beispielsweise **Fabrikam.com** für den Namen der XMPP-Partnerdomäne ein. Dies ist ein erforderlicher Eintrag.

6.  **Beschreibung**   die Beschreibung gilt für Notizen oder andere identifizierende Informationen für diese bestimmte Konfiguration. Dieser Eintrag ist optional.

7.  **Zusätzliche**   Domänen zusätzliche Domänen sind Domänen, die Teil der Domäne Ihres XMPP-Partners sind und als Teil der zulässigen XMPP-Kommunikation enthalten sein sollten. Wenn es sich bei der primären Domäne beispielsweise um **Fabrikam.com**handelt, werden alle anderen Domänen aufgelistet, die unter fabrikam.com sind, mit denen Sie über XMPP kommunizieren.

8.  **Partnertyp**   der **Partnertyp** ist eine erforderliche Einstellung. Sie müssen eine der folgenden Optionen auswählen, um zu beschreiben und zu erzwingen, welche Kontakte hinzugefügt werden können. Sie können Folgendes auswählen:
    
      - **Federated** Ein **Federated** -Partner-Typ stellt eine hohe Vertrauensebene zwischen der lync Server-Bereitstellung und dem XMPP-Partner dar.Dieser Partnertyp wird für die Föderation mit XMPP-Servern innerhalb desselben Unternehmens oder mit einer festgelegten Geschäftsbeziehung empfohlen.XMPP-Kontakte in Verbundpartnern können:
        
        1.  Fügen Sie lync-Kontakte hinzu, und zeigen Sie deren Anwesenheit ohne ausdrückliche Autorisierung des lync-Benutzers an.
        
        2.  Senden Sie Sofortnachrichten an lync-Kontakte, unabhängig davon, ob der lync-Benutzer Sie in seine Kontaktliste aufgenommen hat.
        
        3.  Anzeigen der Status Notizen eines lync-Benutzers
    
      - **Öffentlich überprüft** ein **öffentlicher überprüfte** Partner ist ein öffentlicher XMPP-Anbieter, der als vertrauenswürdig eingestuft wird, um die Identität seiner Benutzer zu überprüfen.XMPP-Kontakte in öffentlich überprüfte Netzwerke können lync-Kontakte hinzufügen und deren Anwesenheit anzeigen und Ihnen Sofortnachrichten senden, ohne die ausdrückliche Autorisierung der lync-Benutzer zu haben.Bei XMPP-Kontakten in öffentlich überprüften Netzwerken werden die Status Notizen der lync-Benutzer nie angezeigt.Diese Einstellung wird nicht empfohlen.
    
      - **Öffentliche nicht bestätigt** Ein **öffentlicher** , nicht überprüfter Partner ist ein öffentlicher XMPP-Anbieter, der nicht als vertrauenswürdig eingestuft wird, um die Identität seiner Benutzer zu überprüfen.XMPP-Benutzer in öffentlichen nicht überprüften Netzwerken können nicht mit lync-Benutzern kommunizieren, es sei denn, der lync-Benutzer hat Sie ausdrücklich autorisiert, indem Sie Sie der Kontaktliste hinzugefügt.Für XMPP-Benutzer in öffentlichen nicht überprüften Netzwerken werden die Status Notizen von lync-Benutzern nie angezeigt.Diese Einstellung wird für alle Föderationen mit öffentlichen XMPP-Anbietern wie Google Talk empfohlen.

9.  **Verbindungstyp:** Definiert die verschiedenen Regeln und Dialback-Einstellungen.
    
      - **TLS**   -Aushandlung definiert die TLS-Aushandlungs Regeln. Ein XMPP-Dienst kann TLS erfordern, kann TLS optional machen, oder Sie definieren, dass TLS nicht unterstützt wird. Wenn Sie optional auswählen, bleibt die Anforderung dem XMPP-Dienst für eine obligatorische Aushandlungs Entscheidung überlassen. So zeigen Sie alle möglichen Einstellungen und Details für SASL-, TLS-und Dialback-Aushandlung an – einschließlich Ungültiger und bekannter Fehler Konfigurationen – finden Sie unter Aushandlungs [Einstellungen für XMPP-Verbundpartner in lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)
        
           - **Erforderlich**   der XMPP-Dienst erfordert TLS-Aushandlung.
        
           - **Optional**   : der XMPP-Dienst gibt an, dass TLS obligatorisch-zu-Negotiate ist.
        
           - **Nicht unterstützt**   der XMPP-Dienst unterstützt keine TLS-Funktion.
    
      - **SASL**   -Aushandlung definiert die SASL-Aushandlungs Regeln. Ein XMPP-Dienst kann SASL erfordern, kann SASL optional machen, oder Sie definieren, dass SASL nicht unterstützt wird. Wenn Sie optional auswählen, bleibt die Anforderung dem Partner XMPP-Dienst für eine obligatorische-zu-Aushandlungs Entscheidung überlassen.
        
           - **Erforderlich**   der XMPP-Dienst erfordert SASL-Aushandlung.
        
           - **Optional**   zeigt der XMPP-Dienst an, dass SASL obligatorisch-zu-Negotiate ist.
        
           - **Nicht unterstützt**   der XMPP-Dienst unterstützt keine SASL-Funktion.
    
      - **Support Server-Dialback** -Aushandlung Der Dialback-Aushandlungsprozess für Support Server verwendet das Domain Name System (DNS) und einen autorisierenden Server, um zu überprüfen, ob die Anforderung von einem gültigen XMPP-Partner kam. Zu diesem Zweck erstellt der ursprüngliche Server eine Nachricht eines bestimmten Typs mit einem generierten Dialback-Schlüssel und schlägt den empfangenden Server in DNS nach. Der ursprüngliche Server sendet den Schlüssel in einem XML-Datenstrom an den resultierenden DNS-Lookup, vermutlich den empfangenden Server. Nach Erhalt des Schlüssels über den XML-Datenstrom antwortet der empfangende Server nicht auf den ursprünglichen Server, sondern sendet den Schlüssel an einen bekannten autorisierenden Server. Der autorisierende Server überprüft, ob der Schlüssel entweder gültig oder ungültig ist. Wenn dies nicht der Fall ist, antwortet der empfangende Server nicht auf den ursprünglichen Server. Wenn der Schlüssel gültig ist, informiert der empfangende Server den Ursprungsserver, dass Identität und Schlüssel gültig sind und die Konversation beginnen kann.
        
        Es gibt zwei gültige Zustände für **Dialback**-Aushandlung:
        
           - **True**   : der XMPP-Server ist für die Verwendung von Dialback-Aushandlung konfiguriert, wenn eine Anforderung von einem Ursprungsserver empfangen werden soll.
        
           - **Falsch**   der XMPP-Server ist nicht für die Verwendung von Dialback-Aushandlung konfiguriert, und wenn eine Anforderung von einem Ursprungsserver empfangen werden soll, wird Sie ignoriert.

10. Klicken Sie auf **Commit** , um Ihre Änderungen an der Website-oder Benutzerrichtlinie zu speichern.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Aktualisieren von DNS-Einträgen für lync Server 2013 XMPP-Gateway

1.  Zum Konfigurieren von DNS für die XMPP-Föderation fügen Sie den folgenden SRV-Eintrag zu Ihrem\_externen DNS hinzu: XMPP-Server. \_TCP. \<Domänenname\> der SRV-Eintrag wird in den Access-Edge-FQDN des Edge-Servers mit einem Portwert von 5269 aufgelöst.

</div>

</div>

<span> </span>

</div>

</div>

</div>

