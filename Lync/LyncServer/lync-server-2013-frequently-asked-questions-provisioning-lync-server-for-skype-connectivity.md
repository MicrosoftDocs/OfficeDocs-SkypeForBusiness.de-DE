---
title: 'Häufig gestellte Fragen: lync Server für Skype-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3679999bc12f606fe338652e8bef22e455cec9ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Häufig gestellte Fragen: lync Server 2013 für Skype-Konnektivität

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2019-03-22_

Ab April 2019 werden wir die Erfassung und Aufbewahrung von Kontaktinformationen für Kunden beenden, die über die PIC.lync.com-Website für Skype Federation vorgesehen sind. Diese Änderung wird vorgenommen, um sicherzustellen, dass das PIC.lync.com-Bereitstellung System den Microsoft-Datenschutzrichtlinien entspricht. 
 
Sobald diese Änderung aktiv ist, können wir keine e-Mail-Updates mehr für ausstehende Bereitstellung Änderungen bereitstellen. PIC-prodie Änderungen werden normalerweise innerhalb von 24-48 Stunden nach der Eingabe abgeschlossen. Wenn Sie noch immer Probleme mit dem Skype-Verbund haben 48 Stunden nach dem Einreichen einer proprovisionierung, wenden Sie sich an den technischen Support von Microsoft, um weitere Informationen zu erhalten.

> [!IMPORTANT]
> Im Rahmen dieser Änderung werden alle zuvor eingegebenen Kontaktinformationen bis Ende April 2019 aus unserem System gelöscht.


**F.: welche Funktionen werden zwischen Microsoft lync und Skype unterstützt?**

**A:** Mit Skype now-Teil der Microsoft-Produktfamilie eröffnen sich neue Möglichkeiten für die Erweiterung von Unified Communications-Szenarien auf die Hunderte von Millionen Personen, die Skype verwenden. Diese Kombination ermöglicht lync-Kunden die Verbindung und Zusammenarbeit mit Lieferanten, Kunden und Partnern, die sich auf den Umfang von lync und die Reichweite von Skype verlassen.

  - Sofortnachrichten und Audio-und Videoanrufe – Verbund-Audio und Videoanrufe und Chatnachrichten zwischen lync-und Skype-Benutzern

  - Anwesenheits Freigabe – Exchange-Anwesenheitsinformationen zwischen verbundkontakten

  - Einfache Verwaltung – Einstellungen und Steuerelemente zum Konfigurieren der Verbundkommunikation gemäß den Richtlinien und Standards Ihrer Organisation

**F.: Wie kann ich mich für die Verbindung meiner lync-Bereitstellung mit Skype qualifizieren?**

**A:** Sie haben eine Lizenz für Skype-Konnektivität, wenn Sie über Folgendes verfügen:

  - Lync Server (2010 oder 2013) plus lync Server Standard-Client Zugriffs Lizenzen ("CALs"; 2010 oder 2013) für die Benutzer und/oder Geräte in Ihrer Organisation, die eine Verbindung mit Skype herstellen sollen. 

  - Lync Online (als eigenständige Lizenzen oder als Teil einer Office 365 Suite).Dieser Dienst (PIC.lync.com) ist jedoch nur für die Bereitstellung von lync Server-und Hybrid lync Server und lync Online Bereitstellungen vorgesehen.Lync Online PIC-proprovisionierung erfolgt in lync Online Systemsteuerung (LOCP).

**F.: Was müssen lync-Endbenutzer tun, um eine Verbindung mit Skype-Kontakten herzustellen?**

**A:** Nachdem eine Domäne aktiviert wurde und die Funktionen vom lync-Administrator einer Organisation aktiviert wurden, können lync-Benutzer ihren Kontaktlisten innerhalb des lync-Clients Skype-Kontakte hinzufügen.

**F.: Was müssen Skype-Endbenutzer tun, um eine Verbindung zu lync-Kontakten herzustellen?**

**A:** Alle Skype-Benutzer, die eine Verbindung mit einem lync-Benutzer herstellen möchten, müssen über ein Microsoft-Konto verfügen, das Ihren Skype-IDs zugeordnet ist, und sich mit dem Microsoft-Konto anmelden.Dies kann innerhalb des Skype-Clients aktiviert werden.

**F.: ist der Verbund mit Windows Live noch verfügbar?**

**A:** Beginnend im Oktober 2012 begann Microsoft, Windows Live Messenger (WLM)-Benutzern zu helfen, zu Skype zu wechseln, auf dem Weg zum letzten einziehen von WLM.Lync wird weiterhin den Verbund mit WLM unterstützen, solange WLM im Markt ist, aber keine zusätzlichen Windows Live-Domänen Aktivierungen werden zugelassen.Die Bewegung von WLM-Benutzern wird durch das Skype 6,0 für Mac und Windows (veröffentlicht am 25. Oktober 2012) aktiviert, mit dem Sie sich mit einem Microsoft-Konto anmelden können (d. h. die gleichen Anmeldeinformationen wie WLM). Nachdem Sie sich einfach bei Skype angemeldet haben, werden die WLM-Buddylisten automatisch in Skype eingefügt, und die Benutzer können die erweiterten Kommunikationsfunktionen von Skype nutzen, beispielsweise das Anrufen von Festnetz und Mobiltelefonen, Bildschirmfreigabe, Gruppen Videoanrufe und Unterstützung für ein breites Vielzahl von Geräten.Darüber hinaus folgen die Partner-lync-Kontakte von WLM-Benutzern dem Übergang in Skype mit den restlichen Buddy-Listen, und Chats zwischen Skype und lync für diese Kontakte werden sofort verfügbar sein. Lync-Kunden müssen nichts Unternehmen, um diese Kontinuität des Diensts zu aktivieren.

**F.: ist der Partner\! Verbund mit Yahoo oder AOL noch verfügbar?**

**A:** Nein. Partnerverbund mit Yahoo\! und AOL waren abhängig von der Unterstützung von Yahoo\! und AOL.Für Yahoo\! und AOL endete der Dienst am 30. Juni 2014. 

**F.: kann ich Skype-Konnektivität vor dem Kauf von lync testen?**

**A:** Skype-Konnektivität wird nicht Test basiert angeboten. Anstelle einer Testversion werden lync-Kunden mit berechtigten Lizenzen aufgefordert, sich einfach für den zu testenden Dienst anzumelden.

**F.: welche Informationen sind für die Einrichtung erforderlich?**

**A:** Um eine Übermittlungsanforderung unter einer qualifizierten Lizenz zu übermitteln, benötigen Sie Folgendes:

  - Microsoft-Vertragsnummer:
    
      - Microsoft Volume Licensing-Unterstützung: Microsoft Volume License Agreement-Nummer
    
      - Microsoft Partner Network: zentrale Partner-ID
    
      - Dienstanbieter-Lizenzvertrag: erste Registrierungsnummer
    
      - High Volume Services: Produkt Registrierungsnummer

  - Vollqualifizierte Domänennamen (FQDNs) für die Zugriffs-Edgedienst.
    
      - FQDN für mindestens eine Zugriffs-Edgedienst erforderlich.
    
      - Wenn Ihre Organisation über mehr als einen Server verfügt, auf dem der Zugriffs-Edgedienst ausgeführt wird, geben Sie die FQDNs für jede zusätzliche Zugriffs-Edgedienst an. Wichtig: Wenn Sie zuvor einen FQDN für den Zugriffs-Edgedienst angegeben haben und ihn ändern möchten, kann die Vorbereitung der Änderung mehrere Tage in Anspruch nehmen und zu einer Unterbrechung des Diensts führen. Zur Vermeidung von Dienstunterbrechungen wird empfohlen, den zuvor angegebenen FQDN des Zugriffs-Edgedienst beizubehalten.

  - SIP (Session Initiation Protocol)-Domäne (n). Dies ist das Domänensuffix des SIP-URI, den Benutzer derzeit für Chatnachrichten verwenden. Wenn Ihre Organisation über mehr als eine SIP-Domäne verfügt, geben Sie das Domänensuffix für jede Domäne an, die für Chatnachrichten verwendet wird. Geben Sie beispielsweise für user1@contoso.com contoso.com für die SIP-Domäne an; Geben Sie für user1@example.fabrikam.com example.fabrikam.com als SIP-Domäne an.
    
    <div>
    

    > [!NOTE]
    > Geben Sie nur das Domänensuffix für die SIP-Domäne an. Geben Sie für die SIP-Domäne keine FQDNs an, einschließlich des FQDN für die Zugriffs-Edgedienst.

    
    </div>

  - Kontaktinformationen. Geben Sie eine e-Mail-Adresse für den Administrator jeder von Ihnen angegebenen SIP-Domäne an.

**F: Wie aktiviere ich die lync-Skype-Konnektivität in einem Szenario mit geteilten Domänen?**

**A:** Wenn Sie über ein Szenario mit einer lync Online 2013 und lync Server lokalen Split-Domain (mit Benutzern sowohl online als auch lokal mit derselben SIP-Domäne) verfügen, aktivieren Sie die lync-Skype-Konnektivität, indem Sie die folgenden beiden Schritte in der folgenden Reihenfolge ausführen.

1.  Richten Sie die lokale lync-Skype-Konnektivität wie im PIC-Leitfaden zur Anleitung beschrieben ein.

2.  Warten Sie, bis die Bestätigung angezeigt wird, dass Ihre Domäne von Microsoft bereitgestellt wurde.

3.  Nachdem Sie die Bestätigung angezeigt haben, aktivieren Sie im lync Admin Center "externe Kommunikation". Weitere Informationen finden Sie unter[https://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](https://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Diese Reihenfolge ist wichtig.Sie müssen die lokale Konnektivität einrichten, bevor Sie die Kommunikation in lync Online aktivieren. Wenn die Reihenfolge umgekehrt wird, <https://pic.lync.com> werden die für die lokale Anmeldung eingegebenen Informationen nicht durchlaufen. Wenn Sie lync Online für die externe Kommunikation mit dieser Domäne bereits eingerichtet haben, müssen Sie diese deaktivieren, 24 Stunden warten und erneut starten, indem Sie zuerst Ihre lokalen Informationen eingeben <https://pic.lync.com> und dann die externe Kommunikation für lync Online aktivieren.

**F.: kann ich mehrere Zugriffs-Edgedienst FQDNs für Skype-Konnektivität anbieten?**

**A:** Sie können nur einen Zugriffs-Edge-FQDN für eine oder mehrere Domänen anbieten. Sie können mehrere Access-Edge-FQDNs bis zu 10 pro Anforderung für unterschiedliche Domänen anbieten.

**F.: kann ich eine Liste der e-Mail-Adressen von Microsoft-Konten erhalten, die für die Organisation, die die Bereitstellung anfordert, gefunden werden?**

**A:** Nein. Diese Adressen werden als personenbezogene Informationen betrachtet und nicht freigegeben.

**F: Wie füge ich einen Windows Live Messenger-Kontakt hinzu, der eine ID enthält, die eine andere Domäne als die von Windows Live unterstützten hat?**

**A:** Wenn Sie einen Windows Live Messenger-Benutzer mit einem Konto oder einer ID mit einer nicht-Windows Live-Domäne hinzufügen, geben Sie die Adresse im \<folgenden Format\>ein\<: Benutzer\>Name (Domänenname) @MSN \<. com\> , wobei Domain Name der Domänenname in der e-Mail-Adresse des Benutzers ist. Wenn Sie beispielsweise Ted@contoso.com hinzufügen wollten, verwenden Sie das folgende Format: Ted (contoso. com) @MSN. com. Eine Liste der Domänen, die von Windows Live verwaltet werden, finden Sie im Abschnitt "unterstützte Domänen" unter "bekannte Probleme, die mit öffentlichen Sofortnachrichten nach der Installation von Live Communications Server Service https://support.microsoft.com/?kbid=897567Pack 1 auftreten" unter.

**F: wie lange dauert der Bereitstellung Prozess?**

**A:** Die proprovisionierung kann bis zu 30 Tage dauern.

**F.: Woher weiß ich, wann die Einrichtung abgeschlossen ist?**

**A:** Microsoft sendet eine e-Mail-Benachrichtigung, wenn die proprovisionierung abgeschlossen ist.

**F: Wie kann ich die Konfigurations-oder Kontaktdetails aktualisieren, die ich übermittle?**

**A:** Sie können Ihre Informationen auf der gleichen Website aktualisieren, die Sie zum Anfordern der Bereitstellung verwendet haben, nachdem die Bereitstellung abgeschlossen ist. Geben Sie Ihre Vertragsnummer ein, und klicken Sie dann auf Dienst aktualisieren.

</div>

<span> </span>

</div>

</div>

</div>

