---
title: 'Häufig gestellte Fragen: Bereitstellen der Skype-Konnektivität für Lync Server'
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
ms.openlocfilehash: 7204119aca18bfeb2539b0ee5eae5bb53f38efd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Häufig gestellte Fragen: Bereitstellen der Skype-Konnektivität für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2019-03-22_

Ab April 2019 werden wir die Erfassung und Speicherung von Kontaktinformationen für Kunden, die über die PIC.lync.com-Website für Skype Federation bereitgestellt werden, beenden. Diese Änderung wird vorgenommen, um sicherzustellen, dass das PIC.lync.com-Bereitstellungssystem den Microsoft-Datenschutzrichtlinien entspricht. 
 
Sobald diese Änderung in Echtzeit erfolgt, können wir keine e-Mail-Updates mehr für ausstehende Bereitstellungsänderungen bereitstellen. PIC-Bereitstellungsänderungen werden in der Regel innerhalb von 24-48 Stunden nach der Eingabe abgeschlossen. Wenn Sie nach dem Einreichen einer Bereitstellungsanfrage nach wie vor Skype Federation Issues (48) erleben, wenden Sie sich bitte an den technischen Support von Microsoft, um weitere Informationen zu erhalten.

> [!IMPORTANT]
> Im Rahmen dieser Änderung werden alle zuvor eingegebenen Kontaktinformationen bis Ende April 2019 aus unserem System gelöscht.


**F: welche Features werden zwischen Microsoft lync und Skype unterstützt?**

**A:** Da Skype nun Teil der Microsoft-Familie ist, eröffnen sich neue Möglichkeiten, um Unified Communications-Szenarien für Hunderte von Millionen von Skype-Nutzern zu erweitern. Diese Kombination ermöglicht lync-Kunden die Verbindung und Zusammenarbeit mit Lieferanten, Kunden und Partnern, die sich auf den Reichtum von lync und die Reichweite von Skype verlassen.

  - Sofortnachrichten und Audio-und Videoanrufe – Federated-Audio-und Videoanrufe und Sofortnachrichten zwischen lync-und Skype-Nutzern

  - Anwesenheits Freigabe – Exchange-Anwesenheitsinformationen zwischen verbundkontakten

  - Einfache Verwaltung – Einstellungen und Steuerelemente zum Konfigurieren der Verbundkommunikation gemäß den Richtlinien und Standards Ihrer Organisation

**F: Wie qualifiziere ich mich für die Verbindung meiner lync-Bereitstellung mit Skype?**

**A:** Sie haben eine Lizenz für Skype-Konnektivität, wenn Sie über Folgendes verfügen:

  - Lync Server (2010 oder 2013) plus lync Server-Standard Client Zugriffs Lizenzen ("CALs"; 2010 oder 2013) für die Benutzer und/oder Geräte in Ihrer Organisation, die eine Verbindung mit Skype herstellen. 

  - Lync Online (als eigenständige Lizenzen oder als Teil einer Office 365-Suite).Dieser Dienst (PIC.lync.com) ist allerdings nur für die Bereitstellung von lync Server-und Hybriden lync Server-und lync Online-Bereitstellungen vorgesehen.Die lync Online PIC-Bereitstellung erfolgt in der lync Online-Systemsteuerung (LOCP).

**F: Was müssen lync-Endbenutzer tun, um eine Verbindung mit Skype-Kontakten herzustellen?**

**A:** Nachdem eine Domäne aktiviert wurde und die Features vom lync-Administrator einer Organisation aktiviert wurden, können lync-Benutzer ihren Kontaktlisten innerhalb des lync-Clients Skype-Kontakte hinzufügen.

**F: Was müssen Skype-Endbenutzer tun, um eine Verbindung mit lync-Kontakten herzustellen?**

**A:** Alle Skype-Nutzer, die eine Verbindung mit einem lync-Nutzer herstellen möchten, müssen über ein Microsoft-Konto verfügen, das mit den Skype-IDs verbunden ist, und sich mit dem Microsoft-Konto anmelden.Dies kann im Skype-Client aktiviert werden.

**F: ist der Verbund mit Windows Live weiterhin verfügbar?**

**A:** Ab Oktober 2012 begann Microsoft, Windows Live Messenger (WLM)-Benutzern zu helfen, zu Skype zu wechseln und sich schließlich für WLM einzusetzen.Lync wird weiterhin die Föderation mit WLM unterstützen, solange WLM im Markt ist, aber keine zusätzlichen Windows Live-Domänen Aktivierungen zulässig sind.Die Bewegung von WLM-Benutzern wird durch den Skype 6,0 für Mac und Windows (veröffentlicht am 25. Oktober 2012) ermöglicht, mit dem Sie sich mit einem Microsoft-Konto anmelden können (also mit den gleichen Anmeldeinformationen wie WLM). Nachdem Sie sich einfach bei Skype angemeldet haben, werden die WLM-Kontaktlisten automatisch in Skype eingefügt, und Nutzer können die erweiterten Kommunikationsmöglichkeiten von Skype nutzen, wie Anrufe an Festnetz-und Handynummern, Bildschirmübertragung, Gruppen-Videoanrufe und Unterstützung für ein breites Vielzahl von Geräten.Darüber hinaus folgen die lync-Kontakte von WLM-Benutzern dem Übergang in Skype mit den restlichen Kontaktlisten, und Chats zwischen Skype und lync für diese Kontakte werden sofort zur Verfügung stehen. Lync-Kunden müssen nichts Unternehmen, um diese Kontinuität des Diensts zu ermöglichen.

**F: ist Föderation mit Yahoo\! oder AOL weiterhin verfügbar?**

**A:** Nein. Föderation mit Yahoo\! und AOL waren von Yahoo abhängig\! und AOL.Für Yahoo\! und AOL endete der Service am 30. Juni 2014. 

**F: kann ich Skype-Konnektivität testen, bevor ich lync kaufe?**

**A:** Skype-Konnektivität wird nicht Test basiert angeboten. Anstelle einer Testversion werden lync-Kunden mit berechtigten Lizenzen dazu ermutigt, sich einfach für den zu testenden Dienst anzumelden.

**F: welche Informationen sind für die Bereitstellung erforderlich?**

**A:** Wenn Sie eine Bereitstellungsanforderung unter einer qualifizierten Lizenz einreichen möchten, benötigen Sie Folgendes:

  - Microsoft-Vereinbarungsnummer:
    
      - Microsoft Volume Licensing-Unterstützung: Microsoft-Volumenlizenz Vereinbarungsnummer
    
      - Microsoft-Partnernetzwerk: Headquarter-Partner-ID
    
      - Dienstanbieter-Lizenzvertrag: erste Registrierungsnummer
    
      - Dienstleistungen mit großem Volumen: Produkt Registrierungsnummer

  - Vollqualifizierte Domänennamen (FQDNs) für den Access Edge-Dienst.
    
      - Der FQDN für mindestens einen Access Edge-Dienst ist erforderlich.
    
      - Wenn in Ihrer Organisation mehr als ein Server den Access-Edgedienst ausführt, geben Sie die FQDNs für jeden zusätzlichen Access Edge-Dienst an. Wichtig: Wenn Sie zuvor einen FQDN für den Access-Edgedienst angegeben haben und ihn ändern möchten, kann die Bereitstellung für die Änderung mehrere Tage dauern und zu einer Unterbrechung des Diensts führen. Um eine Dienstunterbrechung zu verhindern, empfehlen wir, den zuvor angegebenen FQDN des Access Edge-Diensts beizubehalten.

  - SIP (Session Initiation Protocol)-Domäne (n). Dies ist das Domänensuffix des SIP-URIs, den Benutzer derzeit für Chatnachrichten verwenden. Wenn Ihre Organisation über mehr als eine SIP-Domäne verfügt, geben Sie das Domänensuffix für jede Domäne an, die für Chatnachrichten verwendet wird. Geben Sie beispielsweise für user1@contoso.com contoso.com für die SIP-Domäne an; Geben Sie für user1@example.fabrikam.com example.fabrikam.com als SIP-Domäne an.
    
    <div>
    

    > [!NOTE]
    > Geben Sie nur das Domänensuffix für die SIP-Domäne an. Geben Sie für die SIP-Domäne keine FQDNs an, einschließlich des FQDN für den Access Edge-Dienst.

    
    </div>

  - Kontaktinformationen. Geben Sie eine e-Mail-Adresse für den Administrator jeder von Ihnen angegebenen SIP-Domäne an.

**F: Wie aktiviere ich die lync-Skype-Konnektivität in einem Szenario mit geteilten Domänen?**

**A:** Wenn Sie über ein Szenario mit einer lync Online 2013-und lync Server-Domäne mit getrennten Domänen (mit Benutzern sowohl online als auch lokal mit derselben SIP-Domäne) verfügen, aktivieren Sie die lync-Skype-Konnektivität, indem Sie diese beiden Schritte in der folgenden Reihenfolge ausführen.

1.  Richten Sie die lokale lync-Skype-Konnektivität ein, wie im PIC-Bereitstellungshandbuch erläutert.

2.  Warten Sie, bis Sie die Bestätigung erhalten, dass Ihre Domäne von Microsoft bereitgestellt wurde.

3.  Nachdem Sie die Bestätigung angezeigt haben, verwenden Sie das lync Admin Center, um "externe Kommunikation" zu aktivieren. Weitere Informationen finden Sie unter[http://office.microsoft.com/en-us/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/en-us/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Diese Reihenfolge ist wichtig.Sie müssen die lokale Konnektivität einrichten, bevor Sie die Kommunikation in lync Online aktivieren. Wenn die Bestellung storniert wird, <https://pic.lync.com> werden die für die lokale Eingabe eingegebenen Informationen nicht durchlaufen. Wenn Sie lync Online für die externe Kommunikation mit dieser Domäne bereits eingerichtet haben, müssen Sie es deaktivieren, 24 Stunden warten und erneut starten, indem Sie zunächst Ihre lokalen Informationen eingeben <https://pic.lync.com> und dann die externe Kommunikation für lync Online aktivieren.

**F: kann ich für die Skype-Konnektivität mehrere Access-Edge-Service-FQDNs bereitstellen?**

**A:** Sie können nur einen Access-Edge-FQDN für eine oder mehrere Domänen bereitstellen. Wenn Sie über unterschiedliche Domänen verfügen, können Sie mehrere Access-Edge-FQDNs (bis zu 10 pro Anforderung) bereitstellen.

**F: kann ich eine Liste der e-Mail-Adressen von Microsoft-Konten abrufen, die für die Organisation, die die Bereitstellung beantragt, gefunden werden?**

**A:** Nein. Diese Adressen gelten als persönlich identifizierbare Informationen und werden nicht freigegeben.

**F: Wie kann ich einen Windows Live Messenger-Kontakt hinzufügen, dessen ID eine andere Domäne als die von Windows Live unterstützten enthält?**

**A:** Wenn Sie einen Windows Live Messenger-Benutzer mit einem Konto oder einer ID mit einer nicht-Windows Live-Domäne hinzufügen, geben Sie die Adresse im \<folgenden Format\>ein\<: Benutzer\>Name (Domänenname) @MSN \<. com\> , wobei Domänenname der Domänenname in der e-Mail-Adresse des Benutzers ist. Wenn Sie beispielsweise Ted@contoso.com hinzufügen möchten, verwenden Sie das folgende Format: Ted (contoso. com) @MSN. com. Eine Liste der Domänen, die von Windows Live verwaltet werden, finden Sie im Abschnitt unterstützte Domänen unter "bekannte Probleme, die bei öffentlichen Sofortnachrichten auftreten, nachdem Sie Live Communications Server Service Pack 1 http://support.microsoft.com/?kbid=897567" unter installiert haben.

**F: wie lange dauert der Bereitstellungsprozess?**

**A:** Die Bereitstellung kann bis zu 30 Tage dauern.

**F: Wie kann ich feststellen, ob die Bereitstellung abgeschlossen ist?**

**A:** Microsoft sendet eine e-Mail-Benachrichtigung, wenn die Bereitstellung abgeschlossen ist.

**F: Wie kann ich die von mir gesendeten Konfigurations-oder Kontaktdetails aktualisieren?**

**A:** Nach Abschluss der Bereitstellung können Sie Ihre Informationen auf der Website aktualisieren, die Sie zum Anfordern der Bereitstellung verwendet haben. Geben Sie Ihre Vertragsnummer ein, und klicken Sie dann auf Dienst aktualisieren.

</div>

<span> </span>

</div>

</div>

</div>

