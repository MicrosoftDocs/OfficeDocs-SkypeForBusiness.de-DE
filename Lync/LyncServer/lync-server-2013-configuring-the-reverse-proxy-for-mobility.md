---
title: 'Lync Server 2013: Konfigurieren des Reverseproxys für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657ddf0711b0a14c9ce861a0f237977c9a2369c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a>Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-03-20_

Wenn Sie die automatische Ermittlung für Clients für mobile Geräte verwenden möchten, müssen Sie eine vorhandene oder eine neue Webveröffentlichungsregel für den Reverseproxy ändern, unabhängig davon, ob Sie die Listen Betreff alternativer Name auf den Reverse-Proxy Zertifikaten aktualisieren.

Wenn Sie sich entschließen, HTTPS für anfängliche lync Server 2013-Erkennungsdienst Anforderungen zu verwenden und die Listen Betreff Alternative Namen auf den Reverse-Proxy Zertifikaten zu aktualisieren, müssen Sie das aktualisierte öffentliche Zertifikat dem Secure Sockets Layer (SSL)-Listener auf Ihr Reverse-Proxy. Details zu den erforderlichen Einträgen für Alternativen Betreff finden Sie unter [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Anschließend müssen Sie den vorhandenen Listener für die externen Webdienste ändern oder eine neue Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL erstellen. Wenn Sie noch keine Webveröffentlichungsregel für die externe lync Server 2013-Webdienste-URL für Ihren Front-End-Pool besitzen, müssen Sie auch eine Regel dafür veröffentlichen.

<div>


> [!NOTE]  
> Die Reverse Proxy-Veröffentlichungsregel und der Listener können sowohl die externen Webdienste als auch den AutoErmittlungsdienst bedienen, solange das dem Listener zugewiesene Zertifikat den erforderlichen Namen und die alternativen Subjektnamen für beide enthält. Details zur Standardkonfiguration der Weblistener-und Veröffentlichungsregel finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A> für weitere Informationen.



</div>

Wenn Sie sich entschließen, http für anfängliche AutoErmittlungsdienst Anforderungen zu verwenden, damit Sie keine alternativen Antragstellernamen für den Reverse-Proxy aktualisieren müssen, müssen Sie eine Webveröffentlichungsregel für Port 80 erstellen oder ändern.

Die Verfahren in diesem Abschnitt beschreiben, wie Sie die Webveröffentlichungsregeln in Microsoft Forefront Threat Management Gateway 2010 für die automatische Ermittlung erstellen oder ändern.

<div>


> [!NOTE]  
> Bei diesen Verfahren wird davon ausgegangen, dass Sie die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert haben. Wenn Sie einen anderen Reverseproxy verwenden, sind die Verfahren ähnlich, müssen aber der Dokumentation des Drittanbieterprodukts zugeordnet sein.



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>So erstellen Sie eine Webveröffentlichungsregel für die externe Auto Ermittlungs-URL

1.  Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Forefront TMG**, und klicken Sie dann auf **Forefront TMG-Verwaltung**.

2.  Erweitern Sie im linken Bereich **Servername**, klicken Sie mit der rechten Maustaste auf **Firewall-Richtlinie**, zeigen Sie auf **neu**, und klicken Sie dann auf **Website Veröffentlichungsregel**.

3.  Geben Sie auf der Seite **Willkommen bei der neuen Webveröffentlichungsregel** einen Anzeigenamen für die neue Veröffentlichungsregel ein (beispielsweise LyncDiscoveryURL).

4.  Wählen Sie auf der Seite **Regelaktion auswählen** die Option **zulassen**aus.

5.  Wählen Sie **** auf der Seite Veröffentlichungs **eine einzelne Website oder ein Lastenausgleichsmodul veröffentlichen**aus.

6.  Wählen Sie auf der Seite **Server Verbindungssicherheit** die Option **SSL verwenden aus, um eine Verbindung mit dem veröffentlichten Webserver oder der Serverfarm herzustellen**.

7.  Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres Director-Pools ein (beispielsweise "lyncdir01. contoso. local"). Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie die VIP-Adresse des Hardware Load Balancer (HLB) vor dem Front-End-Pool ein.

8.  **Geben / ** Sie auf der Seite **interne Veröffentlichungs Details** unter **Pfad (optional)** den Pfad des zu veröffentlichenden Ordners ein, und wählen Sie dann **den ursprünglichen Hostheader weiterleiten**aus.

9.  Führen Sie auf der Seite " **Details zum öffentlichen Namen** " die folgenden Aktionen aus:
    
      - Wählen Sie unter **Anforderungen annehmen für** **den folgenden Domänennamen**aus.
    
      - Geben Sie in **Öffentlicher Name** **lyncdiscover.** \<sipdomain\> (die URL des externen AutoErmittlungsdiensts). Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie den FQDN für die externen Webdienste in Ihrem Front-End-Pool ein (beispielsweise lyncwebextpool01.contoso.com).
    
      - Geben **** Sie in Pfad ** / **den Text ein.

10. Wählen Sie auf der Seite Weblistener **auswählen** im Weblistener Ihren vorhandenen SSL-Listener mit dem aktualisierten öffentlichen Zertifikat aus. ****

11. Wählen Sie **** auf der Seite Authentifizierungsdelegierung **keine Delegierung aus, aber der Client kann sich direkt authentifizieren**.

12. Wählen Sie auf der Seite **Benutzer festlegen** **alle Benutzer**aus.

13. Überprüfen Sie auf der Seite zum **Abschließen der neuen Webveröffentlichungsregel** , ob die Einstellungen für die Webveröffentlichungsregel richtig sind, und klicken Sie dann auf **Fertig stellen**.

14. Doppelklicken Sie in der Liste der Forefront TMG-Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften**zu öffnen.

15. Führen Sie auf der Registerkarte **an** die folgenden Aktionen aus:
    
      - Wählen Sie **den ursprünglichen Hostheader anstelle des tatsächlichen weiterleiten**aus.
    
      - Select- **Anforderungen scheinen vom Forefront TMG-Computer zu stammen**.

16. Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:
    
      - Wählen Sie **Webserver**aus.
    
      - Wählen Sie **Anforderungen an http-Port umleiten**aus, und geben Sie **8080** für die Portnummer ein.
    
      - Wählen Sie **Anforderungen an SSL-Port umleiten**aus, und geben Sie **4443** für die Portnummer ein.

17. Klicken Sie auf **OK**.

18. Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

19. Klicken Sie auf **Regel testen** , um zu überprüfen, ob Ihre neue Regel ordnungsgemäß eingerichtet ist.

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>So ändern Sie eine vorhandene Webveröffentlichungsregel, um den externen Auto Ermittlungs-San und die URL hinzuzufügen

1.  Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Forefront TMG**, und klicken Sie dann auf **Forefront TMG-Verwaltung**.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie werden die Änderung für jede Veröffentlichungsregel und jeden Listener wiederholen, die Sie haben. In der Regel handelt es sich um eine Regel und einen Listener für die Front-End-Pools und einen für die optionalen Directors-oder Director-Pools, wenn Sie diese bereitgestellt haben.

    
    </div>

2.  Erweitern Sie im linken Bereich **Servername**, klicken Sie mit der rechten Maustaste auf **Firewall-Richtlinie**, und klicken Sie auf die entsprechende Regel. Klicken Sie auf der Registerkarte **Aufgaben** auf **ausgewählte Regel bearbeiten**.

3.  Wählen Sie auf der Registerkarte **Öffentlicher Name** in **dieser Regel gilt**für **die Option Anforderungen für die folgenden Websites**aus.

4.  Klicken Sie auf **Hinzufügen**, geben Sie den Namen der neuen Auto Ermittlungs Website ein (beispielsweise "lyncdiscover.contoso.com"), und klicken Sie dann auf **OK**.

5.  Klicken Sie **** auf der Registerkarte Listener auf **Zertifikat auswählen** , und weisen Sie dem hinzugefügten San-Eintrag für die AutoErmittlung das neue Zertifikat zu. Schließen Sie die Listener-und Webveröffentlichungseigenschaften.

6.  Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

7.  Klicken Sie auf **Regel testen** , um zu überprüfen, ob Ihre neue Regel ordnungsgemäß eingerichtet ist.

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>So erstellen Sie eine Webveröffentlichungsregel für Port 80

1.  Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Forefront TMG**, und klicken Sie dann auf **Forefront TMG-Verwaltung**.

2.  Erweitern Sie im linken Bereich **Servername**, klicken Sie mit der rechten Maustaste auf **Firewall-Richtlinie**, zeigen Sie auf **neu**, und klicken Sie dann auf **Website Veröffentlichungsregel**.

3.  Geben Sie auf der Seite **Willkommen bei der neuen Webveröffentlichungsregel** einen Anzeigenamen für die neue Veröffentlichungsregel ein (beispielsweise lync AutoErmittlung (http)).

4.  Wählen Sie auf der Seite **Regelaktion auswählen** die Option **zulassen**aus.

5.  Wählen Sie **** auf der Seite Veröffentlichungs **eine einzelne Website oder ein Lastenausgleichsmodul veröffentlichen**aus.

6.  Wählen Sie auf der Seite **Server Verbindungssicherheit** die Option **nicht gesicherte Verbindungen verwenden aus, um eine Verbindung mit dem veröffentlichten Webserver oder der Serverfarm herzustellen**.

7.  Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**die VIP-Adresse des Hardware Lastenausgleichs (Hardware Load Balancer, HLB) vor dem Front-End-Pool ein.

8.  **Geben / ** Sie auf der Seite **interne Veröffentlichungs Details** unter **Pfad (optional)** den Pfad des zu veröffentlichenden Ordners ein, und wählen Sie dann **den ursprünglichen Hostheader anstelle des im Feld Interner Websitename angegebenen weiterleiten aus. **.

9.  Führen Sie auf der Seite " **Details zum öffentlichen Namen** " die folgenden Aktionen aus:
    
      - Wählen Sie unter **Anforderungen annehmen für** **den folgenden Domänennamen**aus.
    
      - Geben Sie in **Öffentlicher Name** **lyncdiscover.** \<sipdomain\> (die URL des externen AutoErmittlungsdiensts).
    
      - Geben **** Sie in Pfad ** / **den Text ein.

10. Wählen Sie auf der Seite Weblistener **auswählen** im Weblistener einen Weblistener aus, oder verwenden Sie den Assistenten für neue Weblistener-Definition, um eine neue zu erstellen. ****

11. Wählen Sie **** auf der Seite Authentifizierungsdelegierung **keine Delegierung aus, und der Client kann sich nicht direkt authentifizieren**.

12. Wählen Sie auf der Seite **Benutzer festlegen** **alle Benutzer**aus.

13. Überprüfen Sie auf der Seite zum **Abschließen der neuen Webveröffentlichungsregel** , ob die Einstellungen für die Webveröffentlichungsregel richtig sind, und klicken Sie dann auf **Fertig stellen**.

14. Doppelklicken Sie in der Liste der Forefront TMG-Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften**zu öffnen.

15. Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:
    
      - Wählen Sie **Webserver**aus.
    
      - Wählen Sie **Anforderungen an http-Port umleiten**aus, und geben Sie **8080** für die Portnummer ein.
    
      - Vergewissern Sie sich, dass " **Anforderungen an SSL-Port umleiten** " nicht aktiviert ist.

16. Klicken Sie auf **OK**.

17. Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

18. Klicken Sie auf **Regel testen** , um zu überprüfen, ob Ihre neue Regel ordnungsgemäß eingerichtet ist.

19. Überprüfen Sie, ob die URL des externen AutoErmittlungsdiensts in einer anderen Webveröffentlichungsregel nicht definiert ist.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Einrichten von Reverseproxyservern für Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

