---
title: 'Lync Server 2013: Konfigurieren des Reverse-Proxys für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e2a84b07821601b82e0268c6f5f167105f7d55c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a>Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-03-20_

Wenn Sie die AutoErmittlung für die Clients mobiler Geräte verwenden möchten, müssen Sie eine neue Webveröffentlichungsregel für den Reverseproxy erstellen oder eine vorhandene bearbeiten, ganz gleich, ob Sie die Listen der alternativen Antragstellernamen für die Reverseproxyzertifikate aktualisieren oder nicht.

Wenn Sie HTTPS für die anfängliche lync Server 2013 AutoErmittlungs-Dienstanforderungen verwenden und die Listen alternativer Antragstellernamen in den Reverse-Proxy Zertifikaten aktualisieren, müssen Sie das aktualisierte öffentliche Zertifikat dem Secure Sockets Layer (SSL) Listener auf zuweisen. Reverse-Proxy. Ausführliche Informationen zu den erforderlichen Einträgen für alternative Antragstellernamen finden Sie unter [Technical Requirements for Mobility in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Dann müssen Sie den bestehenden Listener für die externen Webdienste bearbeiten oder eine neue Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL erstellen. Wenn Sie noch nicht über eine Webveröffentlichungsregel für die externe lync Server 2013 Webdienste-URL für Ihre Front-End-Pool verfügen, müssen Sie auch eine Regel dafür veröffentlichen.

<div>


> [!NOTE]  
> Die Veröffentlichungsregel und der Listener für Reverseproxys können sowohl für die externen Webdienste als auch für den AutoErmittlungsdienst gelten, solange das dem Listener zugewiesene Zertifikat jeweils den erforderlichen Antragstellernamen und den alternativen Antragstellernamen für beides enthält. Ausführliche Informationen zur Standardkonfiguration der Weblistener-und Veröffentlichungsregel finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A> .



</div>

Wenn Sie HTTP für die anfänglichen AutoErmittlungsdienst-Anforderungen verwenden möchten, damit die alternativen Antragstellernamen für den Reverseproxy nicht aktualisiert werden müssen, müssen Sie eine Webveröffentlichungsregel für Port 80 erstellen oder bearbeiten.

Die Vorgehensweisen in diesem Abschnitt beschreiben, wie die neuen Webveröffentlichungsregeln in Microsoft Forefront Threat Management Gateway 2010 für die automatische Ermittlung erstellt oder bearbeitet werden können.

<div>


> [!NOTE]  
> Bei diesen Vorgehensweisen wird vorausgesetzt, dass die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert ist. Wenn Sie einen anderen Reverseproxy verwenden, sind die Vorgänge ähnlich, müssen jedoch der Dokumentation für das Drittanbieterprodukt zugeordnet werden.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>So erstellen Sie eine Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL

1.  Klicken Sie auf **Start**, zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG**, und klicken Sie auf **Forefront TMG-Verwaltung**.

2.  Erweitern Sie im linken Bereich **ServerName**, klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Website-Veröffentlichungsregel**.

3.  Geben Sie auf der Seite **Willkommen** einen Anzeigenamen für die neue Veröffentlichungsregel ein (z. B. "LyncErmittlungURL").

4.  Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.

5.  Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.

6.  Klicken Sie auf der Seite **Sicherheit der Serververbindung** auf **SSL verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen**.

7.  Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Directorpool ein (beispielsweise lyncdir01. contoso. local). Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie die VIP-Adresse des Hardware Lastenausgleichs (HLB) vor dem Front-End-Pool ein.

8.  **Geben / ** Sie auf der Seite **interne Veröffentlichungs Details** im **Pfad (optional)** als Pfad zu dem zu veröffentlichenden Ordner ein, und wählen Sie dann **den ursprünglichen Hostheader weiterleiten**aus.

9.  Führen Sie auf der Seite **Details des öffentlichen Namens** folgende Schritte aus:
    
      - Wählen Sie unter **Anforderungen annehmen für:** den Eintrag**Diesen Domänennamen** aus.
    
      - Geben Sie im **öffentlichen Namen** **lyncdiscover.** \<sipdomain "\> (die externe AutoErmittlungsdienst-URL). Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie den FQDN für die externe Webdienste auf dem Front-End-Pool ein (beispielsweise lyncwebextpool01.contoso.com).
    
      - Geben **** Sie im Pfad ** / **den Namen ein.

10. Wählen Sie auf der Seite **Weblistener auswählen** im Feld **Weblistener** den vorhandenen SSL-Listener mit dem aktualisierten öffentlichen Zertifikat aus.

11. Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, aber direkte Authentifizierung des Clients**.

12. Wählen Sie auf der Seite **Benutzersatz** die Option **Alle Benutzer** aus.

13. Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel, und klicken Sie dann auf **Fertig stellen**.

14. Doppelklicken Sie in der Forefront TMG-Liste der Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften** zu öffnen.

15. Führen Sie auf der Registerkarte **An** die folgenden Schritte aus:
    
      - Wählen Sie **Ursprünglichen Hostheader anstelle des aktuellen Headers weiterleiten** aus.
    
      - Wählen Sie **Ursprung der Anforderungen scheint der Forefront TMG-Computer zu sein** aus.

16. Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:
    
      - Wählen Sie **Webserver** aus.
    
      - Wählen Sie **Anforderungen an HTTP-Port umleiten** aus, und geben Sie als Portnummer**8080** ein.
    
      - Wählen Sie **Anforderungen an SSL-Port umleiten** aus, und geben Sie als Portnummer **4443** ein.

17. Klicken Sie auf **OK**.

18. Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

19. Klicken Sie auf **Regel testen**, um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>So bearbeiten Sie eine bestehende Webveröffentlichungsregel zum Hinzufügen des externen AutoErmittlungsdienst-SAN und der -URL

1.  Klicken Sie auf **Start**, zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG**, und klicken Sie auf **Forefront TMG-Verwaltung**.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen die Bearbeitung für jede Veröffentlichungsregel und jeden Listener wiederholen. Normalerweise ist dies eine Regel und ein Listener für die Front-End-Pools und eine für die optionalen Directors-oder Director-Pools, sofern Sie sie bereitgestellt haben.

    
    </div>

2.  Erweitern Sie im linken Bereich **ServerName**, klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie**, und klicken Sie auf die entsprechende Regel. Klicken Sie auf der Registerkarte **Aufgaben** auf **Ausgewählte Regel bearbeiten**.

3.  Wählen Sie auf der Registerkarte **Öffentlicher Name** unter **Regel gilt für** den Eintrag **Anforderungen für die folgenden Websites** aus.

4.  Klicken Sie auf **Hinzufügen**, geben Sie den Namen des neuen AutoErmittlungs-Standorts ein (beispielsweise "lyncdiscover.contoso.com"), und klicken Sie auf **OK**.

5.  Klicken Sie auf der Registerkarte **Listener** auf **Zertifikat auswählen**, und weisen Sie den hinzugefügten AutoErmittlungs-SAN-Einträgen das neue Zertifikat zu. Schließen Sie die Listener- und Webveröffentlichungs-Eigenschaften.

6.  Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

7.  Klicken Sie auf **Regel testen**, um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>So erstellen Sie eine Webveröffentlichungsregel für Port 80

1.  Klicken Sie auf **Start**, zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG**, und klicken Sie auf **Forefront TMG-Verwaltung**.

2.  Erweitern Sie im linken Bereich **ServerName**, klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Website-Veröffentlichungsregel**.

3.  Geben Sie auf der Seite **Willkommen** einen Anzeigenamen für die neue Veröffentlichungsregel ein (z. B. "Lync AutoErmittlung (HTTP)").

4.  Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.

5.  Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.

6.  Wählen Sie auf der Seite **Sicherheit der Serververbindung** die Option **Nicht sichere Verbindungen verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen** aus.

7.  Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**die VIP-Adresse des Hardware Lastenausgleichs (HLB) vor dem Front-End-Pool ein.

8.  **Geben / ** Sie auf der Seite **interne Veröffentlichungs Details** im Feld **Pfad (optional)** den Pfad des zu veröffentlichenden Ordners ein, und wählen Sie dann **den ursprünglichen Hostheader anstelle des im Feld Interner Websitename angegebenen Forwards**aus.

9.  Führen Sie auf der Seite **Details des öffentlichen Namens** folgende Schritte aus:
    
      - Wählen Sie unter **Anforderungen annehmen für:** den Eintrag**Diesen Domänennamen** aus.
    
      - Geben Sie im **öffentlichen Namen** **lyncdiscover.** \<sipdomain "\> (die externe AutoErmittlungsdienst-URL).
    
      - Geben **** Sie im Pfad ** / **den Namen ein.

10. Wählen Sie auf der Seite **Weblistener auswählen** im Feld **Weblistener** einen Weblistener aus, oder erstellen Sie mit dem Assistenten für neue Weblistenerdefinition einen neuen Weblistener.

11. Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, keine direkte Authentifizierung des Clients**.

12. Wählen Sie auf der Seite **Benutzersatz** die Option **Alle Benutzer** aus.

13. Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel, und klicken Sie dann auf **Fertig stellen**.

14. Doppelklicken Sie in der Forefront TMG-Liste der Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften** zu öffnen.

15. Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:
    
      - Wählen Sie **Webserver** aus.
    
      - Wählen Sie **Anforderungen an HTTP-Port umleiten** aus, und geben Sie als Portnummer**8080** ein.
    
      - Stellen Sie sicher, dass **Anforderungen an SSL-Port umleiten** nicht ausgewählt ist.

16. Klicken Sie auf **OK**.

17. Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

18. Klicken Sie auf **Regel testen**, um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.

19. Stellen Sie sicher, dass die externe AutoErmittlungsdienst-URL für keine andere Webveröffentlichungsregel definiert ist.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Einrichten von Reverse-Proxyservern für lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[Technische Anforderungen für die Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

