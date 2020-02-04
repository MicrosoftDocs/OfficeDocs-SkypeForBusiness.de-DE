---
title: 'Lync Server 2013: Erstellen oder Bearbeiten einer XMPP-Verbundpartnerkonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488665bca5cd2ad1b4d2d91a3c85a6a1ddaa3916
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Erstellen oder Bearbeiten einer XMPP-Verbundpartnerkonfiguration in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-09-03_

Microsoft lync Server 2013 integriert einen Extensible Messaging and Presence Protocol (XMPP)-Proxy auf dem Edgeserver und ein XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool. Damit Verbindungen von anderen XMPP-Bereitstellungen zugelassen werden, müssen Sie xmpp in der lync Server-Systemsteuerung konfigurieren. Sie konfigurieren die Einstellungen auf einer XMPP-Domänenbasis. Gehen Sie wie folgt vor, um eine neue Partnerzuordnung zu erstellen:

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>So erstellen Sie einen neuen Föderationspartner oder bearbeiten eine vorhandene Konfiguration

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **XMPP Federated Partners**.

4.  Wenn Sie eine neue Konfiguration erstellen möchten, klicken Sie auf **neu** .

5.  Wenn Sie eine vorhandene Konfiguration bearbeiten möchten, wählen Sie die Konfiguration aus, und klicken Sie auf **Bearbeiten** .

6.  Zum Erstellen oder Bearbeiten von Konfigurationen für **XMPP-Verbundpartner**definieren Sie die folgenden Einstellungen:

7.  **Primäre Domäne** (erforderlich). Die primäre Domäne ist die Basisdomäne des XMPP-Partners. Geben Sie beispielsweise **Fabrikam.com** für den Namen der XMPP-Partnerdomäne ein. Dies ist ein erforderlicher Eintrag.

8.  **Beschreibung**aus. Die Beschreibung ist für Notizen oder andere identifizierende Informationen für diese bestimmte Konfiguration. Dieser Eintrag ist optional.

9.  **Zusätzliche Domänen**. Zusätzliche Domänen sind Domänen, die Teil der Domäne Ihres XMPP-Partners sind und als Teil der zulässigen XMPP-Kommunikation enthalten sein sollten. Wenn es sich bei der primären Domäne beispielsweise um **Fabrikam.com**handelt, werden alle anderen Domänen aufgelistet, die unter fabrikam.com sind, mit denen Sie über XMPP kommunizieren. So können Sie beispielsweise **Corp.fabrikam.com** und **IT.fabrikam.com** für die Unternehmens-XMPP-Domäne und die XMPP-Domäne Informationstechnologien unter der Haupt-XMPP-Domäne von fabrikam. com eingeben.

10. **Partnertyp**. Der **Partnertyp** ist eine erforderliche Einstellung und bietet in einem Dropdownmenü drei Auswahlmöglichkeiten. Sie müssen eine der folgenden Optionen auswählen, um zu beschreiben und zu erzwingen, welche Kontakte hinzugefügt werden können. Sie können Folgendes auswählen:
    
      - **Federated**. Ein **Federated** -Partner-Typ ist eine vertrauenswürdige Verbindung zwischen einer lync Server-oder Office Communications Server 2007 R2-Partner Bereitstellung.
    
      - **Öffentlich verifiziert**. Ein **öffentlich überprüfter** Partner ist, wenn Kontakte, die Teil einer Bereitstellung sind, die vom Anbieter überprüft werden, der Kontaktliste des Benutzers hinzugefügt werden können. Einladungen können vom lync-Benutzer gesendet werden, oder der lync-Benutzer kann Einladungen vom Partner Kontakt akzeptieren.
    
      - **Öffentlich nicht überprüft**. Eine **öffentliche** nicht überprüfte Beziehung impliziert, dass es zwischen den beiden Bereitstellungen keinen festgelegten und überprüfbaren Status gibt. Ein lync-Benutzer muss den nicht überprüften Kontakt für diesen Kontakt einladen, um den lync-Benutzer in seine Kontaktliste aufnehmen zu können. Beispielsweise ist Google Gtalk kein öffentlicher überprüfter XMPP-Dienst, da es sich um lync Server handelt. Ein GTalk-Benutzer kann den lync-Benutzer nur dann als Kontakt hinzufügen, wenn eine explizite Einladung vom lync-Benutzer gesendet wurde.

11. Hinweise zur Datenstrom Aushandlung und den Sicherheitsmethoden Transport Layer Security (TLS) und Software Authentication and Security Layer (SASL):
    
    Die **XMPP Standards Foundation** (XSF) und die **Internet Engineering Task Force** (IETF) definieren einen Satz von Regeln und Standards für die Verwendung und Verwaltung von TLS-Clientzertifikaten, TLS-Serverzertifikaten und dem SASL-Mechanismus. Die Verwendung von TLS und SASL ist der erforderliche Prozess zum Sichern des XMPP-Streams. Aus dem XMPP-Standarddokument **XEP-0178**gibt "einen empfohlenen Protokoll Fluss für die Verwendung des SASL-externen Mechanismus mit PKIX-Zertifikaten an, insbesondere dann, wenn ein XMPP-Dienst angibt, dass TLS obligatorisch-zu-Negotiate ist." PKIX, wie in der XSF-Dokumentation angegeben, bezieht sich auf Infrastruktur öffentlicher Schlüssel, auch bekannt als PKI.
    
    Weitere Informationen zu den XMPP-Anforderungen finden Sie im XSF-Dokument XEP-0178. Einzelheiten hierzu finden Sie unter "XEP-0178: bewährte Methoden für die Verwendung von SASL External with Certificates". <http://xmpp.org/extensions/xep-0178.html>
    
    Weitere Informationen finden Sie im IETF-Dokument "Extensible Messaging and Presence Protocol (XMPP): Core", Abschnitt 5,0 <http://tools.ietf.org/html/rfc6120>, STARTTLS-Aushandlung.
    
      - **TLS-Aushandlung**. Definiert die TLS-Aushandlungs Regeln. Ein XMPP-Dienst kann TLS erfordern, kann TLS optional machen, oder Sie definieren, dass TLS nicht unterstützt wird. Wenn Sie optional auswählen, bleibt die Anforderung dem XMPP-Dienst für eine obligatorische Aushandlungs Entscheidung überlassen. Informationen zum Anzeigen aller möglichen Einstellungen und Details für SASL-, TLS-und Dialback-Aushandlung – einschließlich Ungültiger und bekannter Fehler Konfigurationen – finden Sie unter [Aushandlungs Einstellungen für XMPP-Verbundpartner in lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Erforderlich**. Der XMPP-Dienst erfordert TLS-Aushandlung.
        
          - <span></span>  
            **Optional**. Der XMPP-Dienst gibt an, dass TLS obligatorisch-zu-Negotiate ist.
        
          - <span></span>  
            **Nicht unterstützt**. Der XMPP-Dienst unterstützt keine TLS-Funktion.
    
      - **SASL-Aushandlung**. Definiert die SASL-Aushandlungs Regeln. Ein XMPP-Dienst kann SASL erfordern, kann SASL optional machen, oder Sie definieren, dass SASL nicht unterstützt wird. Wenn Sie optional auswählen, bleibt die Anforderung dem Partner XMPP-Dienst für eine obligatorische-zu-Aushandlungs Entscheidung überlassen.
        
        <div>
        

        > [!WARNING]  
        > SASL erfordert TLS. Um SASL verwenden zu können, muss TLS entweder erforderlich oder optional sein. Jede Konfiguration, die SASL als erforderlich oder optional definiert, muss über TLS-Unterstützung verfügen. Wenn Sie auf <STRONG>Commit</STRONG> klicken, um Ihre Änderungen zu speichern, wenn Sie TLS nicht auf erforderlich oder optional festgesetzt haben, werden Sie gewarnt, dass SASL über TLS-Unterstützung verfügen muss und Ihre Änderungen nicht gespeichert werden. Um den Fehler zu beheben, legen Sie TLS auf <STRONG>erforderlich</STRONG> oder <STRONG>optional</STRONG>. Wenn die Verwendung von SASL optional ist und TLS-Aushandlungs Unterstützung nicht möglich ist, müssen Sie die SASL-Aushandlung auf <STRONG>nicht unterstützt</STRONG>setzen. Bestätigen Sie mit dem XMPP-Dienst, was die richtigen Aushandlungsdaten Ströme für TLS und SASL sein müssen, oder die Dienstunterbrechung erfolgt.

        
        </div>
        
          - <span></span>  
            **Erforderlich**. Der XMPP-Dienst erfordert SASL-Aushandlung.
        
          - <span></span>  
            **Optional**. Der XMPP-Dienst gibt an, dass SASL obligatorisch-zu-Negotiate ist.
        
          - <span></span>  
            **Nicht unterstützt**. SASL wird vom XMPP-Dienst nicht unterstützt.
    
      - **Dialback-Aushandlung**. Dialback-Aushandlung wird vom XSF im Dokument **XEP-220: Server Dialback** <http://xmpp.org/extensions/xep-0220.html>definiert. Der Server Dialback-Prozess verwendet das Domain Name System (DNS) und einen autorisierenden Server, um zu überprüfen, ob die Anforderung von einem gültigen XMPP-Partner kam. Zu diesem Zweck erstellt der ursprüngliche Server eine Nachricht eines bestimmten Typs mit einem generierten Dialback-Schlüssel und schlägt den empfangenden Server in DNS nach. Der ursprüngliche Server sendet den Schlüssel in einem XML-Datenstrom an den resultierenden DNS-Lookup, vermutlich den empfangenden Server. Nach Erhalt des Schlüssels über den XML-Datenstrom antwortet der empfangende Server nicht auf den ursprünglichen Server, sondern sendet den Schlüssel an einen bekannten autorisierenden Server. Der autorisierende Server überprüft, ob der Schlüssel entweder gültig oder ungültig ist. Wenn dies nicht der Fall ist, antwortet der empfangende Server nicht auf den ursprünglichen Server. Wenn der Schlüssel gültig ist, informiert der empfangende Server den Ursprungsserver, dass Identität und Schlüssel gültig sind und die Konversation beginnen kann.
        
        Es gibt zwei gültige Zustände für **Dialback-Aushandlung**:
        
          - <span></span>  
            **True**. Der XMPP-Server ist für die Verwendung von Dialback-Aushandlung konfiguriert, wenn eine Anforderung von einem Ursprungsserver empfangen werden soll.
        
          - <span></span>  
            **False**. Der XMPP-Server ist nicht für die Verwendung von Dialback-Aushandlung konfiguriert, und wenn eine Anforderung von einem Ursprungsserver empfangen werden soll, wird Sie ignoriert.

</div>

</div>

<span> </span>

</div>

</div>

</div>

