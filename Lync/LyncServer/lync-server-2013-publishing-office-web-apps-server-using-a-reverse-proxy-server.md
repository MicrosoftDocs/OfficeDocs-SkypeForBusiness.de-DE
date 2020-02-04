---
title: Veröffentlichen von Office Web Apps Server mithilfe eines Reverseproxyservers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>Veröffentlichen von Office Web Apps Server in lync Server 2013 mit einem Reverse Proxy Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Wenn Sie externe Benutzer (also Benutzer, die sich außerhalb der Firewall Ihrer Organisation anmelden) für den Zugriff auf Office Web Apps Server PowerPoint-Präsentationen verwenden möchten, müssen Sie Office Web Apps Server und einen Reverse-Proxy Server wie Microsoft Forefront verwenden. Threat Management-Gateway. Das bedeutet auch, dass Sie eine Website Veröffentlichungsregel erstellen und konfigurieren müssen. Mithilfe dieser Regel wird sichergestellt, dass Benutzer eine Verbindung mit dem Server herstellen können. Wenn Sie keinen Zugriff auf externe Benutzer bereitstellen müssen, müssen Sie keine Veröffentlichungsregel für Websites konfigurieren.

Führen Sie die folgenden Schritte aus, um eine Website Veröffentlichungsregel im Forefront Threat Management-Gateway zu konfigurieren:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Forefront TMG**, und klicken Sie dann auf **Forefront TMG-Verwaltung**.

2.  Klicken Sie in Forefront TMG mit der rechten Maustaste auf **Firewall-Richtlinie**, zeigen Sie auf **neu**, und klicken Sie dann auf **Website Veröffentlichungsregel**.

3.  Geben Sie im Assistenten für neue Webveröffentlichungsregel auf der Seite **Willkommen bei der neuen Webveröffentlichungsregel-Assistent** einen Namen für die neue Regel in das Feld **Name der Webveröffentlichungs** Regel ein (beispielsweise **Office Web Apps-Server Regel**), und klicken Sie dann auf **weiter**.

4.  Wählen Sie auf der Seite **Regelaktion angeben** die Option **zulassen** aus, und klicken Sie dann auf **weiter**.

5.  Wählen Sie auf der Seite **Veröffentlichungs** **eine einzelne Website oder ein Lastenausgleichsmodul veröffentlichen** aus, und klicken Sie dann auf **weiter**.

6.  Wählen Sie auf der Seite **Server Verbindungssicherheit** die Option SSL verwenden aus, um **eine Verbindung mit dem veröffentlichten Webserver oder der Serverfarm herzustellen** , und klicken Sie dann auf **weiter**.

7.  Geben Sie auf der Seite **interne Veröffentlichungs Details** den FQDN Ihres Office Web Apps-Servers (beispielsweise **officewebapps01.contoso.com**) in das Feld **interner Websitename** ein, und klicken Sie dann auf **weiter**. Der Name, der im Feld **interner Websitename** eingegeben wurde, muss im Feld Betreff oder im Feld Subject Alternative Name des Zertifikats angezeigt werden, das Sie Office Web Apps Server zugewiesen haben.

8.  **Geben / ** Sie auf der Seite **interne Veröffentlichungs Details** im Feld **Pfad (optional)** ein, und klicken Sie dann auf **weiter**. Mit der\* /-Syntax wird sichergestellt, dass alle Ordner und Unterordner der Website veröffentlicht werden.

9.  Wählen Sie auf der Seite Details für den **öffentlichen Namen** diesen Domänennamen aus der Dropdownliste **Accept Request for** **(Typ below)** aus, und geben Sie dann im Feld öffentlicher Name den vollqualifizierten für Ihren Office Web Apps-Server ein. Dieser Name sollte der Name sein, der für den Zugriff auf Ihre Website verwendet wird. Wenn Sie beispielsweise über die URL http://officewebapps01.contoso.com auf Ihre Website zugreifen, sollten Sie **officewebapps01.contoso.com** in das Feld **Öffentlicher Name** eingeben.

10. Klicken Sie auf **Weiter**.

11. Klicken Sie auf der Seite **Weblistener auswählen** auf **neu**.

12. Geben Sie im Assistenten für neue Weblistener-Definition einen Namen für den neuen Weblistener (beispielsweise **SSL**) in das Feld **Weblistener-Name** ein, und klicken Sie dann auf **weiter**.

13. Wählen Sie auf der Seite **Client Verbindungssicherheit** die Option **SSL-gesicherte Verbindungen mit Clients anfordern** aus, und klicken Sie dann auf **weiter**.

14. Wählen Sie auf der Seite **Weblistener-IP-Adressen** die Option **extern**aus, wählen Sie **intern**aus, und klicken Sie dann auf **weiter**.

15. Wählen Sie auf der Seite **Listener SSL-Zertifikate** die Option **einzelnes Zertifikat für diesen Weblistener verwenden** aus, und klicken Sie dann auf **Zertifikat auswählen**.

16. Wählen Sie im Dialogfeld **Zertifikat auswählen** das für diesen Weblistener zu verwendende Zertifikat aus, und klicken Sie dann auf **auswählen**.

17. Klicken Sie auf der Seite **Listener SSL-Zertifikate** auf **weiter**.

18. Wählen Sie auf der Seite **Authentifizierungseinstellungen** in der Dropdown **Liste Wählen Sie aus, wie Clients Anmeldeinformationen für Forefront TMG bereitstellen** die Option **keine Authentifizierung** aus, und klicken Sie dann auf **weiter**.

19. Klicken Sie auf der Seite **Einstellungen für einmaliges Anmelden** auf **weiter**.

20. Überprüfen Sie auf der Seite zum **abschließen des neuen Weblistener-Assistenten** die Zusammenfassung der von Ihnen vorgenommenen Konfigurationsoptionen. Wenn Sie fertig sind, klicken Sie auf **Fertig stellen**.

21. Klicken Sie auf der Seite **Weblistener auswählen** auf **weiter**.

22. Wählen Sie auf der Seite **Authentifizierungsdelegierung** die Option **keine Delegierung aus, aber der Client kann sich direkt** über die **Option wählen Sie die Methode aus, die von Forefront TMG für die Authentifizierung bei der veröffentlichten Web Server** -Dropdownliste verwendet wird, und klicken Sie dann auf **weiter**.

23. Überprüfen Sie auf der Seite **Benutzersätze** , ob die entsprechenden Benutzersätze aufgelistet sind. Standardmäßig ist dies der Benutzersatz **alle Benutzer** . Klicken Sie auf **Hinzufügen** , um andere Benutzergruppen hinzuzufügen, die Sie möglicherweise definiert haben. Wenn Sie fertig sind, klicken Sie auf **weiter**.

24. Klicken Sie auf der Seite zum **Abschließen der neuen Webveröffentlichungsregel** auf **Fertig stellen**.

Beachten Sie, dass das Klicken auf " **Fertig stellen** " nicht bedeutet, dass Sie den Vorgang abgeschlossen haben. Das bedeutet, dass dies nicht automatisch angewendet wird und die neue Regel aktiviert wird. Stattdessen müssen Sie auf die Schaltfläche "über **nehmen** " klicken, die auf der Forefront TMG-Benutzeroberfläche angezeigt wird. Wenn Sie auf über **nehmen** klicken, wird das Dialogfeld **Beschreibung der Konfigurationsänderung** angezeigt. Klicken Sie in diesem Dialogfeld auf über **nehmen** , um die neue Veröffentlichungsregel zu aktivieren.

Nachdem die neue Regel angewendet wurde, müssen Sie einige kleinere Änderungen an der Regel vornehmen, um sicherzustellen, dass die Benutzer die neuen PowerPoint-Präsentationsfunktionen verwenden können. Verwenden Sie dazu das folgende Verfahren:

1.  Klicken Sie in Forefront TMG mit der rechten Maustaste auf den Namen der neuen Veröffentlichungsregel, und klicken Sie dann auf **Eigenschaften**.

2.  Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **an** die Option **Weiterleiten des ursprünglichen Hostheaders statt des eigentlichen**aus.

3.  Klicken Sie auf der Registerkarte **Datenverkehr** auf **Filtern** , und klicken Sie dann auf **http konfigurieren**.

4.  Deaktivieren Sie im Dialogfeld **http-Richtlinie für Regel konfigurieren** das Kontrollkästchen **Normalisierung über** prüfen, und klicken Sie dann auf **OK**.

5.  Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.

6.  Klicken Sie in Forefront TMG auf über **nehmen** , um die Änderungen zu aktivieren. Wenn das Dialogfeld **Beschreibung der Konfigurationsänderung** angezeigt wird, klicken Sie auf über **nehmen**.

Nach Abschluss der Installation können Sie Ihren Office Web Apps-Server mit den Verfahren im Thema über [Prüfen der Konfiguration von Office Web Apps Server in lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)testen.

</div>

<span> </span>

</div>

</div>

</div>

