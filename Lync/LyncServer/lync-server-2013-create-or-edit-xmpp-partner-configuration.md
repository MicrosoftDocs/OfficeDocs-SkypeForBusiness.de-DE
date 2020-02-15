---
title: 'Lync Server 2013: Erstellen oder Bearbeiten der XMPP-Partnerkonfiguration'
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
ms.openlocfilehash: 4410444d1565e61fa80ef8b8db29aad63b4401de
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Erstellen oder Bearbeiten der XMPP-Partnerkonfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-09-03_

Microsoft lync Server 2013 integriert einen XMPP-Proxy (Extensible Messaging and Presence Protocol) auf der Edgeserver und ein XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool. Um Verbindungen von anderen XMPP-Bereitstellungen zuzulassen, müssen Sie XMPP im lync Server-Systemsteuerung konfigurieren. Die Einstellungen werden auf XMPP-Domänenbasis konfiguriert. Führen Sie zum Erstellen eines neuen Partnerverbunds die folgenden Schritte aus:

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>So erstellen Sie einen neuen Verbundpartner oder bearbeiten eine vorhandene Konfiguration

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund- und externer Zugriff** und dann auf **XMPP-Verbundpartner**.

4.  Klicken Sie zum Erstellen einer neuen Konfiguration auf **Neu**.

5.  Wenn Sie eine vorhandene Konfiguration bearbeiten möchten, wählen Sie die Konfiguration aus, und klicken Sie auf **Bearbeiten**.

6.  Um Konfigurationen für **XMPP-Verbundpartner** zu erstellen oder zu bearbeiten, definieren Sie die folgenden Einstellungen:

7.  **Primäre Domäne** (erforderlich). Die primäre Domäne ist die Basisdomäne des XMPP-Partners. Sie können beispielsweise **fabrikam.com** als Domänennamen für den XMPP-Partner eingeben. Dies ist ein erforderlicher Eintrag.

8.  **Beschreibung**. Die Beschreibung ist für Notizen oder für andere Identifizierungsinformationen in Bezug auf diese bestimme Konfiguration vorgesehen. Dieser Eintrag ist optional.

9.  **Zusätzliche Domänen**. Bei den weiteren Domänen handelt es sich um Domänen, die Teil der Domäne Ihres XMPP-Partners sind und in die zulässige XMPP-Kommunikation einbezogen werden sollen. Wenn die primäre Domäne z. B. **fabrikam.com** lautet, führen Sie alle anderen Domänen von "fabrikam.com" auf, mit denen Sie per XMPP kommunizieren möchten. Beispielsweise können Sie **Corp.fabrikam.com** und **IT.fabrikam.com** für die betriebliche XMPP-Domäne und die Information Technologies XMPP-Domäne unter fabrikam. com es Haupt-XMPP-Domäne eingeben.

10. **Partnertyp**. Der **Partnertyp** ist eine erforderliche Einstellung und bietet eine Auswahl von drei Optionen in einem Dropdownmenü. Wählen Sie eine der folgenden Optionen aus, um zu beschreiben und vorzugeben, welche Kontakte hinzugefügt werden können. Die Optionen lauten:
    
      - **Verbund**. Bei einem **Verbund** Partnertyp handelt es sich um eine vertrauenswürdige Verbindung zwischen einer lync Server-oder Office Communications Server 2007 R2 Partner Bereitstellung.
    
      - **Öffentlich überprüft**. Als **Überprüft öffentlich** gelten Partner, wenn Kontakte, die Teil einer Bereitstellung sind, vom Anbieter überprüft werden und der Kontaktliste Ihres Benutzer hinzugefügt werden können. Einladungen können vom lync-Benutzer gesendet werden, oder der lync-Benutzer kann Einladungen vom Partner Kontakt annehmen.
    
      - **Öffentlich nicht überprüft**. Eine Beziehung vom Typ **Nicht überprüft öffentlich** bedeutet, dass zwischen den beiden Bereitstellungen kein etablierter und überprüfbarer Status besteht. Ein lync-Benutzer muss den nicht überprüften Kontakt für diesen Kontakt einladen, um den lync-Benutzer zu seiner Kontaktliste hinzufügen zu können. Beispielsweise ist Google Gtalk kein öffentlicher überprüfter XMPP-Dienst, der sich auf lync Server bezieht. Ein GTalk-Benutzer kann den lync-Benutzer nur dann als Kontakt hinzufügen, wenn eine explizite Einladung vom lync-Benutzer gesendet wurde.

11. Anmerkungen zur Datenstromaushandlung und den Sicherheitsmethoden TLS (Transport Layer Security) und SASL (Software Authentication and Security Layer):
    
    Die **XMPP Standards Foundation** (XSF) und die **Internet Engineering Task Force** (IETF) definieren einen Satz von Regeln und Standards zum Verwenden und Verwalten von TLS-Clientzertifikaten, TLS-Serverzertifikaten und des SASL-Mechanismus. Das Verwenden von TLS und SASL ist zum Schützen des XMPP-Datenstroms erforderlich. Aus dem Dokument der XMPP Standards Foundation geht hervor, dass **XEP-0178** einen empfohlenen Protokollablauf für die Verwendung des SASL EXTERNAL-Mechanismus mit PKIX-Zertifikaten angibt, insbesondere wenn ein XMPP-Dienst TLS zur Aushandlung erfordert. PKIX bezieht sich gemäß der XSF-Dokumentation auf eine Public Key-Infrastruktur (kurz PKI).
    
    Weitere Informationen zu den XMPP-Anforderungen finden Sie im XSF-Dokument XEP-0178. Ausführliche Informationen finden Sie unter "XEP-0178: bewährte Methoden für die Verwendung von SASL extern mit Zertifikaten". <http://xmpp.org/extensions/xep-0178.html>
    
    Lesen Sie das IETF-Dokument "Extensible Messaging and Presence Protocol (XMPP): Core", Abschnitt 5,0, STARTTLS <http://tools.ietf.org/html/rfc6120>-Verhandlung.
    
      - **TLS-Aushandlung**. Definiert die TLS-Aushandlungs Regeln. Ein XMPP-Dienst kann TLS erfordern, kann TLS optional machen, oder Sie definieren, dass TLS nicht unterstützt wird. Bei Auswahl von optional wird die Anforderung für eine obligatorische Aushandlungs Entscheidung für den XMPP-Dienst erfüllt. Um alle möglichen Einstellungen und Details für SASL, TLS und Rückruf-Aushandlung – einschließlich nicht gültiger und bekannter Fehler Konfigurationen – anzuzeigen, finden Sie weitere Informationen unter [Aushandlungs Einstellungen für XMPP-Verbundpartner in lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Erforderlich**. Der XMPP-Dienst erfordert die TLS-Aushandlung.
        
          - <span></span>  
            **Optional**. Der XMPP-Dienst gibt an, dass TLS für die Aushandlung erforderlich ist.
        
          - <span></span>  
            **Nicht unterstützt**. Der XMPP-Dienst unterstützt TLS nicht.
    
      - **SASL-Aushandlung**. Definiert die SASL-Aushandlungs Regeln. Ein XMPP-Dienst kann SASL erfordern, kann SASL optional machen, oder Sie definieren, dass SASL nicht unterstützt wird. Wenn Sie die Option optional auswählen, bleibt die Anforderung bis zum Partner-XMPP-Dienst für eine obligatorische-zu-Aushandlungs Entscheidung.
        
        <div>
        

        > [!WARNING]  
        > SASL erfordert TLS. Um SASL verwenden zu können, muss TLS entweder erforderlich oder optional sein. TLS muss in jeder Konfiguration unterstützt werden, die SASL entweder als erforderlich oder optional definiert. Wenn Sie auf<STRONG>Commit ausführen</STRONG> klicken, um Ihre Änderungen zu speichern, und TLS nicht als erforderlich oder optional festgelegt haben, wird eine Warnung angezeigt. Diese besagt, dass SASL eine TLS-Unterstützung erfordert, und Ihre Änderungen werden nicht gespeichert. Legen Sie TLS auf <STRONG>Erforderlich</STRONG> oder <STRONG>Optional</STRONG> fest, um den Fehler zu beheben. Wenn die Verwendung von SASL optional und die Unterstützung der TLS-Aushandlung nicht möglich ist, müssen Sie die SASL-Aushandlung auf <STRONG>Nicht unterstützt</STRONG> festlegen. Überprüfen Sie für den XMPP-Dienst, wie die Aushandlungsdatenströme für TLS und SASL genau aussehen müssen, um eine Dienstunterbrechung zu verhindern.

        
        </div>
        
          - <span></span>  
            **Erforderlich**. Der XMPP-Dienst erfordert die SASL-Aushandlung.
        
          - <span></span>  
            **Optional**. Der XMPP-Dienst gibt an, dass SASL für die Aushandlung erforderlich ist.
        
          - <span></span>  
            **Nicht unterstützt**. Der XMPP-Dienst unterstützt SASL nicht.
    
      - **Rückruf-Aushandlung**. Rückruf-Aushandlung wird durch die XSF in Document **XEP-220: Server Rückruf** <http://xmpp.org/extensions/xep-0220.html>definiert. Der Serverrückrufprozess verwendet das Domain Name System (DNS) und einen autoritativen Server, um zu überprüfen, ob die Anforderung von einem gültigen XMPP-Partner stammt. Hierzu erstellt der Ausgangsserver eine Meldung eines bestimmten Typs mit einem generierten Rückrufschlüssel und schlägt den empfangenden Server im DNS nach. Der Ausgangsserver sendet den Schlüssel in einem XML-Datenstrom an den resultierenden DNS-Lookup, wahrscheinlich an den empfangenden Server. Wenn der Schlüssel über den XML-Datenstrom empfangen wird, antwortet der empfangende Server dem Ausgangsserver nicht, sondern sendet den Schlüssel aber an einen bekannten autoritativen Server. Der autoritative Server überprüft die Gültigkeit des Schlüssels. Wenn der Schlüssel nicht gültig ist, antwortet der empfangende Server dem Ausgangsserver nicht. Wenn der Schlüssel gültig ist, informiert der empfangende Server den Ausgangsserver, dass die Identität und der Schlüssel gültig sind und dass die Unterhaltung beginnen kann.
        
        Für die **Rückrufaushandlung** gibt es zwei gültige Statusangaben:
        
          - <span></span>  
            **True**. Der XMPP-Server ist für die Verwendung der Rückrufaushandlung konfiguriert, wenn eine Anforderung von einem Ausgangsserver eingeht.
        
          - <span></span>  
            **False**. Der XMPP-Server ist nicht für die Verwendung der Rückruf-Aushandlung konfiguriert, und wenn eine Anforderung von einem ursprünglichen Server empfangen werden soll, wird Sie ignoriert.

</div>

</div>

<span> </span>

</div>

</div>

</div>

