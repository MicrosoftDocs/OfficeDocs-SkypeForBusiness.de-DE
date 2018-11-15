---
title: Planen von hybridkonnektivität
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Planungsüberlegungen für die Implementierung von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online oder Teams.
ms.openlocfilehash: 2f702989a0d40e7bce9b0f3612d67fd374d0813c
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531653"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Plan hybridkonnektivität zwischen Skype für Business Server und Office 365

## <a name="overview"></a>Übersicht

Lesen Sie in diesem Thema erfahren, wie hybridkonnektivität zwischen Skype für Business Server und Teams oder Skype für Business Online zu planen. Einrichten von hybridkonnektivität ist der erste Schritt beim Verschieben Ihrer lokalen Umgebung in der Cloud.

Wenn Sie lokale Skype für Unternehmensbenutzer, die auch Teams (nebeneinander) verwenden verfügen, diese Benutzer müssen nicht die Möglichkeit zum interagieren mit Skype für Unternehmensbenutzer von ihrem Teams Client noch kommunizieren mit Benutzern in Partnerorganisationen, deren Teams-Client. Um diese Funktionalität in Teams zu erhalten, müssen diese Benutzer in die Cloud Die erforderlich sind, Konfigurieren von Skype für Business Hybrid-Modus von Skype für Business lokal verschoben werden. Darüber hinaus sollten die beste wünschen, diese Benutzer im Modus nur Teams sein, die gewährleistet alle eingehenden Anrufe und chats aus Flächen, die Benutzer in der Client des Benutzers Teams.

Einrichten von hybridkonnektivität und verschieben alle Benutzer in der Cloud ist auch erforderlich, bevor Sie Ihre lokale Skype für die Business-Bereitstellung außer Betrieb nehmen.  Mit hybridkonnektivität einrichten können Sie Ihre Benutzer in die Cloud basierend auf Ihren Terminen und Business Bedarf verschieben. Mit direktem Routing können Sie Ihre lokale VoIP-Infrastruktur nutzen, während und nach Abschluss die Migration zur Cloud verschoben werden.

In diesem Thema wird die Infrastruktur und Systemanforderungen, die Sie benötigen zum Konfigurieren von hybridkonnektivität zwischen den vorhandenen lokalen Skype für Business Server-Bereitstellung und Teams oder Skype für Business Online.

Nachdem Sie in diesem Thema gelesen haben und zum Konfigurieren von hybridkonnektivität bereit sind, finden Sie unter [Configure hybridkonnektivität zwischen Skype für Business Server und Office 365](configure-hybrid-connectivity.md). Die Konfigurationsthemen bieten schrittweise Anweisungen zum Einrichten von hybridkonnektivität zwischen Ihrer lokalen Bereitstellung und Teams oder Skype für Business Online.


## <a name="about-split-domain-functionality"></a>Über geteilte Domäne Funktionen
<a name="BKMK_Overview"> </a>

 Hybrid-Verbindung zwischen einer lokalen Bereitstellung von Skype für Business Server und Teams oder Skype für Business Online einrichten können Sie einige Benutzer lokal und einige Benutzer online verwaltet.

Diese Art der Konfiguration abhängig von freigegebenen SIP-Adresse Speicherplatz Funktionalität und wird manchmal als "geteilte Domäne" – Was bedeutet, dass Benutzer einer Domäne, z. B. "contoso.com", aufgeteilt sind, zwischen der Verwendung von Skype für Business Server auf lokale und Teams oder Skype für Unternehmen Online, wie im folgenden Diagramm dargestellt: 

![Skype for Business mit hybrider Konnektivität – geteilte Domäne](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Wenn freigegebenen SIP-Adressraums konfiguriert ist:

- Azure Active Directory verbinden wird verwendet, um das lokale Verzeichnis mit Office 365 synchronisieren.

- Benutzer, die lokal verwaltet werden interagieren mit lokalen Skype für Unternehmensserver. 

- Benutzer, die online verwaltet werden möglicherweise Skype für Business Online oder Teams Dienste interagieren.

- Benutzer aus beiden Umgebungen können miteinander kommunizieren. 

- Die lokale Active Directory ist autorisierend. Alle Benutzer sollten zunächst in die lokale Active Directory erstellt, und klicken Sie dann mit Azure Active Directory synchronisiert werden. Auch wenn der Benutzer online verwaltet werden soll, müssen Sie zuerst erstellen Sie den Benutzer in der lokalen Umgebung, und verschieben Sie den Benutzer in online, um sicherzustellen, dass der Benutzer von lokalen Benutzern sichtbar ist. 

Bevor ein Benutzer online verschoben werden kann, muss der Benutzer einen Skype für Business Online (Plan 2) Lizenz zugewiesen werden. Wenn der Benutzer Teams verwenden, muss der Benutzer auch Teams Lizenz zugewiesen werden (und die Skype für Business Lizenz muss aktiviert bleiben). Wenn Ihre Benutzer zusätzliche online-Funktionen wie Audiokonferenzen oder Telefonsystem, nutzen möchten, müssen Sie diese die entsprechende in Office 365-Lizenz zuweisen.


## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen
<a name="BKMK_Infrastructure"> </a>

Um hybridkonnektivität zwischen Ihrer lokalen Umgebung und Office 365 Kommunikationsdienste zu implementieren, müssen Sie die folgenden infrastrukturanforderungen erfüllen:

- Ein einzelnes lokale Bereitstellung von Skype für Business Server oder Lync Server, die in einer unterstützten Topologie bereitgestellt wird. Finden Sie in diesem Thema in der [topologieanforderungen](plan-hybrid-connectivity.md#BKMK_Topology) .

- Microsoft Office 365-Mandanten mit der Skype für Business Online aktiviert werden soll.

    > [!NOTE]
    > Sie können nur einen einzelnen Mandanten für eine Hybridkonfiguration mit Ihrer lokalen Bereitstellung verwenden.

- Azure Active Directory Connect zum Synchronisieren Ihres lokalen Verzeichnisses mit Office 365. Weitere Informationen finden Sie unter [Azure AD-Connect: Konten und Berechtigungen](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype für Business Server-Verwaltungstools.  Diese sind erforderlich, um Benutzer aus der lokalen in die Cloud zu verschieben. Diese Tools müssen auf einem Server mit Zugriff auf die lokale Bereitstellung sowie dem Internet installiert werden. 

- Online-Verwaltungstools.  Entweder der Teams und Skype für Business-Verwaltungskonsole oder Windows PowerShell können Sie um Teams und Skype für Business Online zu verwalten. Um mithilfe von PowerShell zum Verwalten von Teams oder Skype für Business Online herunter, und installieren Sie die Skype für Business Online Connector. 

- Freigegebenen SIP-Adressraums muss aktiviert sein, und die lokale Bereitstellung muss konfiguriert werden, um Office 365 als einen Hostinganbieter zu verwenden. Weitere Informationen über die erforderlichen Schritte zum Konfigurieren von hybridkonnektivität finden Sie unter [Configure hybridkonnektivität](configure-hybrid-connectivity.md).

Nach der Konfiguration hybridkonnektivität können Sie Benutzer in Teams oder Skype für Business Online verschieben. Weitere Informationen finden Sie unter [Verschieben von Benutzern aus lokalen Teams](move-users-from-on-premises-to-teams.md) und [Verschieben von Benutzern aus lokal zu Skype für Business Online](move-users-from-on-premises-to-skype-for-business-online.md).


## <a name="topology-requirements"></a>Topologieanforderungen
<a name="BKMK_Topology"> </a>

Um die für hybride Bereitstellung mit **Teams oder Skype für Business Online**konfigurieren, müssen Sie einen der folgenden unterstützten Topologien aufweisen:

- Eine Skype für die Bereitstellung mit allen Servern mit Skype für Business Server 2019 Business Server 2019. 
- Eine Skype für die Bereitstellung mit allen Servern mit Skype für Business Server 2015 Business Server 2015.
- Ein Lync Server 2013-Bereitstellung mit allen Servern mit Lync Server 2013.  Wenn VoIP hybridkonnektivität erforderlich ist, müssen Sie eine gemischte Version Topologie wie unten angegeben verwenden.
- Eine Bereitstellung mit bis zu 2 verschiedenen Serverversionen wie unten aufgeführt:
  - Skype für Business Server 2015 und Skype für Business Server 2019
  - Lync Server 2013 und Skype für Business Server 2019
  - Lync Server 2013 und Skype für Business Server 2015

*Wenn Hybrid-VoIP in jeder Topologie gewünscht wird*, muss sowohl der Edge-Server, die als der Verbund Kante als auch für den Pool zugeordneten SIP-Verbund vorgesehen ist Skype für Business 2015 oder höher ausgeführt werden. Benutzer können auf einem Lync 2013-Pool bleiben, sofern vorhanden. Weitere Informationen finden Sie unter [Telefonsystem mit PSTN-Konnektivität in Skype für Business Server planen](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

Die folgenden Topologien, die **Lync Server 2010 werden mit Skype für Business Online unterstützt** für instant messaging und Besprechungen enthalten.  Topologien, die **Lync Server 2010 werden nicht unterstützt, für Hybrid-VoIP noch Teams**enthalten.

- Eine gemischte Lync Server 2010 und Skype für die Bereitstellung von Business Server 2015
- Eine gemischte Bereitstellung von Lync Server 2010 und Lync Server 2013
-   Ein Lync Server 2010-Bereitstellung mit allen Servern mit Lync Server 2010 mit den neuesten kumulativen Updates.
Der Verbund Edge-Server und Hopserver für den nächsten aus den Edge-Server-Verbund müssen Lync Server 2010 mit den neuesten kumulativen Updates ausgeführt werden. Die Skype für Business Server 2015 oder Administrative Tools für Lync Server 2013 muss auf mindestens einem Server oder Verwaltungscomputer installiert werden.



 ## <a name="multi-forest-support"></a>Unterstützung für mehrere Gesamtstrukturen
<a name="BKMK_MultiForest"> </a>

Wenn die folgenden Anforderungen erfüllt sind, können Benutzer auf Skype for Business-Funktionen in einer anderen Gesamtstruktur zugreifen:

- Die Benutzer werden ordnungsgemäß mit der Gesamtstruktur synchronisiert, in der Skype for Business gehostet wird: In Hybridkonfigurationen bedeutet dies, dass die Benutzer als deaktivierte Benutzerobjekte synchronisiert werden müssen.

- Die Gesamtstruktur, in der Skype for Business gehostet wird, muss der Gesamtstruktur, in der sich die Benutzer befinden, vertrauen.

Ausführliche Informationen zum hybridszenarien mit mehreren Gesamtstrukturen finden Sie unter [Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für hybride Skype für Unternehmen](configure-a-multi-forest-environment-for-hybrid.md).


## <a name="federation-requirements"></a>Anforderungen an den Identitätsverbund
<a name="BKMK_Federation"> </a>

Beim Hybrid konfigurieren zu können, müssen Sie sicherstellen, dass Ihre lokalen und online-Umgebung miteinander verbinden können.  Online-Umgebung hat einen öffentlichen Verbund standardmäßig. die lokale Umgebung wurde häufig Verbund standardmäßig geschlossen.  

Die folgenden Anforderungen müssen erfüllt sein, um eine Hybridbereitstellung erfolgreich zu konfigurieren:

- Der Domänenabgleich muss für die lokale Bereitstellung und den Office 365-Mandanten identisch konfiguriert sein. Wenn die Partnerermittlung für die lokale Bereitstellung aktiviert ist, muss der öffentliche Partnerverbund für den Onlinemandaten konfiguriert sein. Wenn die Partnerermittlung nicht aktiviert ist, muss für den Onlinemandanten der geschlossene Partnerverbund konfiguriert sein.

- Die Liste der blockierten Domänen in der lokalen Bereitstellung muss genau mit der Liste der blockierten Domänen für den Onlinemandanten übereinstimmen.

- Die Liste der zugelassenen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zugelassenen Domänen für den Onlinemandanten übereinstimmen.

- Verbund muss für die externen Kommunikation für den online-Mandanten aktiviert sein.


## <a name="network-considerations"></a>Überlegungen zum Netzwerk

Die folgenden Abschnitte beschreiben Aspekte: 

- DNS-Einstellungen 
- Überlegungen zu Firewalls 


### <a name="dns-settings"></a>DNS-Einstellungen
<a name="BKMK_DNS"> </a>

Beim Erstellen von DNS-Einträgen für hybridbereitstellungen sollten alle Skype für Business externe DNS-Einträge für die lokale Infrastruktur verweisen. Informationen zu den erforderlichen DNS-Einträgen finden Sie unter [DNS-Anforderungen für Skype für Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Darüber hinaus müssen Sie sicherstellen, dass die DNS-Auflösung in der folgenden Tabelle beschriebenen in Ihrer lokalen Bereitstellung funktioniert. (Wenn Sie den Verbund für lokale bereits konfiguriert haben, müssen Sie Sie wahrscheinlich bereits diese.)

|DNS-Eintrag  <br/> |Aufzulösen durch  <br/> |DNS-Anforderung  <br/> |
|:-----|:-----|:-----|
|DNS-SRV-Eintrag für _sipfederationtls. \<sipdomain.com\> für alle unterstützten SIP-Domänen, die zum Auflösen von in externen IP(s) Zugriffs-Edgeservers  <br/> |Edgeserver  <br/> |Aktivieren Sie Partnerverbundkommunikation in einer Hybridkonfiguration. Der Edgeserver muss wissen, wohin der Datenverkehr im Partnerverbund für die zwischen lokal und online aufgeteilte SIP-Domäne geleitet werden soll.  <br/> Es muss strenge DNS-Namensübereinstimmung zwischen der Domäne im Benutzernamen und dem SRV-Eintrag verwendet werden.  <br/> |
|DNS-A-Eintrag/Einträge für den Edge-Webkonferenzdienst-FQDN, zum Beispiel „webcon.contoso.com“, aufgelöst zu der externen IP/den IPs des Webkonferenzdienst-Edgeservers  <br/> |Interne Firmennetzwerk den Computern der Benutzer verbunden  <br/> |Versetzen Sie Onlinebenutzer in die Lage, in lokal gehosteten Besprechungen Inhalte zu präsentieren oder zu betrachten. Entsprechende Inhalte sind unter anderem PowerPoint-Dateien, Whiteboards, Umfragen und freigegebene Notizen.   <br/> |

Je nachdem, wie DNS in Ihrer Organisation konfiguriert ist, müssen Sie möglicherweise der intern gehosteten DNS-Zone für die entsprechenden SIP-Domäne(n) diese Einträge hinzufügen, um die interne DNS-Auflösung dieser Datensätze zu gewährleisten. 

### <a name="firewall-considerations"></a>Überlegungen zu Firewalls
<a name="BKMK_Firewall"> </a>

Die Computer in Ihrem Netzwerk müssen Standard-Internet-DNS-Lookups ausführen können. Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.

Je nach den Speicherort des Microsoft Online Services-Rechenzentrum, müssen Sie auch Ihre Netzwerkgeräte Firewall, um Verbindungen basierend auf Platzhalter-Domänennamen akzeptieren konfigurieren (beispielsweise alle Datenverkehr von \*. outlook.com). Wenn der Firewalls der Organisation keine Platzhalter Namen Konfigurationen unterstützen, müssen Sie manuell ermitteln der IP-Adressbereiche, die Sie zulassen möchten und die angegebenen Ports.

Weitere Informationen, einschließlich Informationen zu Ports und protokollanforderungen finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://go.microsoft.com/fwlink/p/?LinkId=252942).
