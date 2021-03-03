---
title: Bereitstellen der Skype-Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Zusammenfassung: Erfahren Sie, wie Sie Skype for Business Server mit einem Skype Consumer verbinden. Wird auch als Skype-Konnektivität bezeichnet.'
ms.openlocfilehash: ae3982375c0693c34e204e4512481a1f9f3b6ec3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834105"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Bereitstellen der Skype-Konnektivität in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Skype for Business Server mit einem Skype Consumer verbinden. Wird auch als Skype-Konnektivität bezeichnet.
  
In diesem Artikel wird die Bereitstellung für die Skype-Konnektivität erläutert.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Übersicht über die Skype-Konnektivität für IT-Experten

Skype Connectivity bietet Skype for Business-Benutzern die Möglichkeit, nach Skype-Benutzern zu suchen und diese hinzuzufügen. Die Skype-Konnektivität ist ein Feature von Skype for Business, mit dem Sie die Verbund- und Verzeichnissuche mit Skype-Benutzern aktivieren können. Nachdem Sie die Skype-Konnektivität aktiviert haben, können Ihre Skype for Business-Benutzer nach den Benutzern von Skype suchen und diese hinzufügen.
  
## <a name="skype-directory-search"></a>Skype Directory Search

Die Funktion "Skype-Verzeichnissuche" bietet Skype for Business-Benutzern die Möglichkeit, nach Skype-Kontakten zu suchen. Mit der Suchfunktion können Benutzer wie folgt suchen:
  
- **Suche nach Anzeigename, Beispiel "John Doe"** – Dies kann viele Ergebnisse zurückgeben, sodass Sie möglicherweise nicht finden, was Sie suchen.
    
- **Suche nach Anzeigename und Standort, Beispiel "John Doe in Einer"** – Dadurch werden die Ergebnisse der Suche erheblich reduziert.
    
- **Suche per E-Mail, Beispiel "johndoe@outlook.com"** – Dies sollte in den meisten Fällen ein Ergebnis zurückgeben. die, die der angegebenen E-Mail genau entspricht. Wenn dieselbe E-Mail jedoch mehreren Konten zugeordnet ist, können mehrere Ergebnisse zurückgegeben werden.
    
- **Suche nach Telefonnummer, Beispiel "123-123-1234"** – Dies sollte in den meisten Fällen ein Ergebnis zurückgeben. das, das dem angegebenen Telefon genau entspricht. Die Telefonnummer muss den Ländercode (d. h. 1-xxx-yyy-zzzz) enthalten. Wenn dieselbe Telefonnummer mehreren Konten zugeordnet ist, können mehrere Ergebnisse zurückgegeben werden.
    
- **Suche nach Skype-Name, Beispiel "JohnDoe1456"** – Wenn eine genaue Übereinstimmung gefunden wird, wird sie als erstes Ergebnis zurückgegeben. Möglicherweise werden andere mögliche Übereinstimmungen mit "Name" zurückgegeben.
    
    > [!NOTE]
    > Die Skype-Verzeichnissuche muss mit den folgenden IP-Adressen an Port 443 kommunizieren können: 104.40.75.246, 23.101.135.34 und 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Unterstützte Bereitstellungsmatrix für die Skype-Verzeichnissuche

In der folgenden Tabelle ist die Unterstützung für die Skype-Verzeichnissuche aufgeführt.
  

||**Skype for Business Server Front End**|**Lync Server 2013 (oder älter) Front-End**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Skype for Business Server und Edge sind Voraussetzungen für die Skype-Verzeichnissuche.  <br/> |
|Skype for Business Server Edge + Lync Server 2013 Edge nebeneinander bereitgestellt  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Der Datenverkehr der Skype-Verzeichnissuche läuft über Skype for Business Server-Edgeserver. Der Verbunddatenverkehr durchgeht den vom Administrator konfigurierten Edge. Beispielsweise könnte der Administrator weiterhin Verbunddatenverkehr über Lync Server 2013-Edgeserver senden, die die Skype-Verzeichnissuche nicht unterstützen würden.  <br/> |
|Lync Server 2013-Edgeserver (oder älter)  <br/> |Nicht unterstützt  <br/> |Nicht unterstützt  <br/> ||
   
> [!NOTE]
> Der auf dem Skype for Business Server-Front-End ausgeführte Adressbuchdienst findet den Edgeserver durch das Vorhandensein des Skype-Suchports 4443 auf dem Edgeserver. 
  
> [!NOTE]
> Wenn ein Kunde über mehrere Standorte in seiner lokalen Bereitstellung verfügt und nur einen Skype for Business Server-Edgeserver/-Pool bereitgestellt hat, wird der Suchdatenverkehr von allen Standorten über den einzelnen verfügbaren Edgeserver gesendet. Der Administrator muss sicherstellen, dass die Pools von allen Standorten auf den bereitgestellten Skype for Business Server-Edgeserver/-Pool zugreifen können. 
  
> [!NOTE]
> Der Skype -Graph-Dienst drosselt Suchanforderungen von einem lokalen oder Microsoft 365- oder Office 365-Kunden, wenn die Anforderungsrate 15 Anforderungen/Sekunde überschreitet. 
  
> [!NOTE]
> Bei lokalen Großunternehmen müssen die Domänen mit dem Skype-Suchdienst in die Whitelist eingetragen werden, um höhere Anforderungsraten zu ermöglichen. 
  
> [!NOTE]
> Skype for Business Server drosselt eingehende Anforderungen, wenn zu viele ausstehende Anforderungen in der Warteschlange vorhanden sind. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Bereitstellen der Skype-Konnektivität für Skype for Business Online

Die Skype-Konnektivität ist auch ein Feature von Skype for Business Online, das Teil von Microsoft 365 und Office 365 ist. Sie können die Skype-Konnektivitätsfunktion über die Skype for Business Administration Center im Microsoft 365 Admin Center aktivieren.
  
Für Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education und Office 365 for Government: Melden Sie sich beim Microsoft 365 Admin Center an, und navigieren Sie zum Skype for Business Administration Center. Wechseln Sie zu "Externe Kommunikation". Klicken Sie unter "Öffentliche Im-Service-Anbieter" auf "Aktivieren". Wenn Sie den Zugriff einzelner Benutzer auf die Skype-Konnektivität steuern möchten, können Sie dazu die Einstellungen für die externe Kommunikation einzelner Benutzer bearbeiten.
  
For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service Settings \> Instant messaging, meetings and conferencing. Aktivieren Sie die externe Kommunikation. Der Switch "Externe Kommunikation" aktiviert sowohl die Skype-Konnektivität als auch die Kommunikation mit anderen Organisationen, die Skype for Business verwenden.
  
Weitere Informationen zur Skype for Business Online-Verwaltung finden Sie unter:
  
- [Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Was Sie ausprobieren sollten, wenn Sie keine Chats für Skype for Business oder externe Kontakte in Skype senden können](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Hinzufügen eines Kontakts in Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administratoren: Konfigurieren von Skype for Business-Einstellungen für einzelne Benutzer](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Bereitstellen der Skype-Konnektivität für Skype for Business Server

Skype for Business Server verwendet die Verbundzugriffsarchitektur, um die Konnektivität mit Skype zu unterstützen. Diese Konnektivität ermöglicht Ihren Skype for Business Server-Benutzern, Skype hinzuzufügen. Skype for Business-Benutzer können auch von Clients zu ihrer Kontaktliste hinzugefügt werden. Basierend auf den in Skype for Business Server administrativen Richtlinien können Benutzer über Chat kommunizieren, sich gegenseitig sehen und Audio- und Videoanrufe initiieren. Die Skype-Konnektivität ist auch ein Feature von Skype for Business Online und kann für Skype for Business Online-Kunden über das Skype for Business Administration Center im Microsoft 365 Admin Center aktiviert werden.
  
> [!NOTE]
> Wenn Skype for Business Server bereits für die Verbindung mit Windows Messenger mithilfe von PIC (Public Instant Messaging Connectivity) konfiguriert ist, ist Ihre Bereitstellung bereits für die Verbindung mit Skype konfiguriert. Die einzige Änderung, die Sie erwägen sollten, ist, Ihren vorhandenen Messenger -PIC-Eintrag in Skype umzubenennen. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Die Skype for Business Server-Bereitstellungswebsite für Verbindungen mit öffentlichen Chats ist nicht mehr verfügbar.

Die Website, die früher zum manuellen Bereitstellen des Verbunds zwischen lokalen Skype for Business-Bereitstellungen und Skype verwendet wurde, ist nicht mehr erforderlich und wird am 15.08.2019 beendet. Der Partnerverbund mit Skype nutzt jetzt die Ermittlung von Verbundpartnern. Dies ist der gleiche Mechanismus, der für den Partnerverbund mit Skype for Business Online erforderlich ist.

Für die Kommunikation zwischen jeder lokalen Skype for Business-Bereitstellung und den Benutzern von Skype über die vorhandene Öffentliche Chatinfrastruktur muss die lokale Edgeserverkonfiguration jetzt mit Skype for Business Online kompatibel sein.

> [!NOTE]
> Die meisten Kunden benötigen keine Aktion, einschließlich aller Bereitstellungen, die mit Skype for Business Online zusammenarbeiten.
  
Lokale Bereitstellungen sind erforderlich, um einen DNS-SRV-Verbunddatensatz für jede Domäne zu veröffentlichen, die sie hosten. Anleitungen sind in der [DNS-Planung verfügbar.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) Jede Domäne muss durch dns-SRV-Abfrage in einen Edgeserver-FQDN aufgelöst werden, der eine Suffixenteinung der obersten Ebene der Domäne erfüllt. Betrachten Sie beispielsweise die Domäne "contoso.com":

|**Gültige FQDNs**|**Kommentar**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In jedem Fall muss der genaue FQDN im SN oder im SAN des auf dem Edgeserver installierten externen Zertifikats vorhanden sein.   |
|access.contoso.com   ||
|**Ungültige FQDNs**|**Grund**|
|sip.contoso-edge.com   |Keine Suffix-Übereinstimmung.  |
|sip.it.contoso.com   |Keine Suffix-Übereinstimmung auf oberster Ebene.   |

Weitere Anleitungen zu externen Zertifikaten finden Sie in der [Zertifikatplanung.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>Häufig gestellte Fragen

**Warum wird die Bereitstellungswebsite heruntergefahren?**
Der im Jahr 2006 bereitgestellte bereitstellungsmechanismus (public im im pic) provisioning mechanism (pic.lync.com) is no longer serviceable and will be shut down on 8/15/2019. Stattdessen übernimmt der Partnerverbund für öffentliche Chats dasselbe Verbundmodell, das von Skype for Business Online verwendet wird, das auch als "Partnerermittlung" bezeichnet wird, wobei eine lokale Bereitstellung öffentlich durch die DNS-SRV-Einträge des Verbunds ermittelt werden kann.

**Bedeutet diese Änderung, dass der Verbund für öffentliche Imitation veraltet ist?**
Nein. Der Öffentliche Chatverbund wird weiterhin viele Jahre unterstützt, wahrscheinlich bis das lokale Produkt von Skype for Business das Ende des Lebenszyklus erreicht.

**Unser Unternehmen hat eine Hybridbeziehung (freigegebener Adressraum) mit Skype for Business Online, sind wir betroffen?**
Nein, da Sie bereits einen Verbund mit Skype for Business Online haben, wirkt sich diese Änderung nicht auf Sie aus.
 
**Bedeutet diese Änderung, dass unser Unternehmen den Partnerverbund mit Skype for Business Online aktivieren muss?**
Nein. Wenn Ihre Edgeserverproxyeinstellungen den Verbund mit dem Skype for Business Online-Hostinganbieter (sipfed.online.lync.com) nicht aktivieren, hat diese Änderung keine Auswirkungen darauf. Die gleichen DNS- und Zertifikatanforderungen, die für den Verbund mit Skype for Business Online gelten, gelten jetzt jedoch auch für den Partnerbetrieb mit Skype-Benutzern.
 
**Unser Unternehmen ist groß und kann seine Edgekonfiguration aus rechtlichen/Compliance-/anderen Gründen nicht ändern... Was können wir tun?**
Jede lokale Organisation, die ihre Edgeserverkonfiguration nicht wie angegeben ändern kann, sollte sich so schnell wie möglich an den Produktsupport senden.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Aktivieren des Verbunds und der Verbindung mit öffentlichen Verbindungen (PIC)

Konzentrieren Sie sich nun auf die Skype for Business Server-Umgebung und verwaltungstechnische Aufgaben, die zum Konfigurieren der Skype-Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der Administrator Skype for Business Server bereitgestellt und den externen Zugriff konfiguriert hat, der auch als Edgeserver bezeichnet wird. 
  
Es sind drei primäre Schritte erforderlich, um den Verbund und PIC zu aktivieren. Diese sind:
  
1. Konfigurieren von Verbund und PIC
    
2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Partnerbenutzer
    
3. Konfigurieren der Skype PIC-Anbietereinstellung
    
#### <a name="1-configure-federation-and-pic"></a>1. Konfigurieren von Verbund und PIC

Ein Verbund ist erforderlich, damit Die Benutzer von Skype for Business mit Skype for Business in Ihrer Organisation kommunizieren können. Pic (Public Instant Messaging Connectivity) ist eine Verbundklasse und muss so konfiguriert werden, dass Ihre Skype for Business-Benutzer mit den Benutzer von Skype for Business kommunizieren können. Verbund und PIC werden mithilfe der Skype for Business Server-Systemsteuerung konfiguriert.
  
> [!NOTE]
> Der PIC-Verbund wird von Produktversionen vor Lync Server 2010 (Live Communication Server, Office Communications Server) nicht mehr unterstützt. Zu den unterstützten Plattformen für den PIC-Verbund gehören Skype for Business Server, Lync Server 2013 und Lync Server 2010. 
  
Ein Verbund ist erforderlich, damit Die Benutzer von Skype for Business mit Skype for Business in Ihrer Organisation kommunizieren können. Pic (Public Instant Messaging Connectivity) ist eine Verbundklasse und muss so konfiguriert werden, dass Ihre Skype for Business Server-Benutzer mit Den Benutzern von Skype for Business Server kommunizieren können. Verbund und PIC werden mithilfe des Dialogfelds "Edgekonfiguration" der Skype for Business Server-Systemsteuerung konfiguriert, wie in der Abbildung dargestellt.
  
![Definieren eines neuen Edgepools](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Die Attribute "EnableSkypeIdRouting" und "EnableSkypeDirectorySearch" müssen in den Einstellungen für öffentliche Anbieter auf "true" festgelegt werden (siehe spätere Anweisungen), damit die Suche funktioniert. 
  
Damit werden die Verwaltungsaufgaben abgeschlossen, die auf dem Server ausgeführt werden müssen. Sie sind jetzt für die Skype-Konnektivität eingerichtet.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Konfigurieren Sie mindestens eine Richtlinie zur Unterstützung des Zugriffs durch Partnerbenutzer

Mithilfe der Skype for Business Server-Systemsteuerung muss ein Administrator eine oder mehrere Zugriffsrichtlinien für externe Benutzer konfigurieren, um zu steuern, ob Die Benutzer von Skype for Business Server mit internen Skype for Business Server-Benutzern zusammenarbeiten können.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Konfigurieren der Skype PIC-Anbietereinstellung

Mithilfe der Skype for Business Server-Verwaltungsshell muss ein Administrator die Skype for Business-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird. 
  
> [!NOTE]
> Benutzer der Public Instant Messaging Connectivity (PIC)-Dienstanbieter können erst an Sofortnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) zur Unterstützung der Verbindung mit öffentlichen Chatdiensten konfigurieren. 
  
Für neue Installationen können Sie die Skype-Konnektivität konfigurieren, indem Sie einen öffentlichen Skype-Anbieter über die Skype for Business Server-Systemsteuerung aktivieren, wie in der Abbildung dargestellt.
  
![SIP-Partnerverbundanbieter](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Zum Konfigurieren der Skype-Konnektivität beim Upgrade auf Skype for Business Server müssen Sie den vorhandenen öffentlichen Anbieter von Skype entfernen und erneut hinzufügen. 
  
Das Konfigurieren der Skype-Konnektivität kann auch nur mithilfe von PowerShell durchgeführt werden. So konfigurieren Sie die Skype-Konnektivität mithilfe von PowerShell:
  
1. Öffnen Sie auf einem Skype for Business Server-Front-End-Server die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie die folgenden beiden Befehle aus:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Wenn Sie noch nicht über einen ANBIETER für Pic in Ihrer Umgebung verfügen und einen neuen ANBIETER für pic erstellen, müssen Sie das cmdlet Remove-CsPublicProvider ausführen. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Was tun die weniger offensichtlichen Parameter?
    
   - ProxyFqdn: Standort des Skype-Verbund-Edgeservers (im Besitz/verwaltet von Microsoft)
    
   - IconURL: Symbol, das vom Lync &amp; Skype for Business-Client zum visuellen Identifizieren von Skype-Kontakten verwendet wird
    
   - NameDecorationRoutingDomain und NameDecorationExcludedDomainList: Wenn Sie diese Einstellungen festlegen, können Benutzer die MSAs von Skype-Benutzern eingeben, ohne sich über das "Auszieren" von Nicht-Microsoft-Domänen mit "msn.com" zu verfügen. Dadurch entfällt die Notwendigkeit, "user(contoso.com)@msn.com" für alle Domänen ein, die SICH NICHT in der ExcludedDomainList befinden. Der SfB-Client formatiert die MSA automatisch, wenn sich die Domäne NICHT in der Liste "Ausgeschlossen" befindet. Wir haben die am häufigsten verwendeten Domänen des Microsoft-Kontos zur ausgeschlossenen Liste hinzugefügt.
    
     > [!NOTE]
     > Der öffentliche Anbieter muss entfernt und neu hinzugefügt werden, wenn Änderungen vorgenommen werden. Es sind keine änderungen zulässig. 
  
     > [!NOTE]
     > Die im Lync Server 2013 CU5 &amp; -Lync-Desktopclient in Office 2013 SP1 hinzugefügten NameDecorationRoutingDomain und NameDecorationExcludedDomainList verbessern die Situation, in der Lync-Benutzer, die Skype-Kontakte hinzufügen, die zum "Auszieren" von Nicht-Microsoft-Domänen erforderlich sind, um sie zu identifizieren und an Skype weiter zu routen (format: user(contoso.com)@msn.com). Diese neuen Einstellungen ermöglichen die automatische Formatierung der Eingabe des Adressbenutzers im Dialogfeld "Skype-Kontakt hinzufügen" mit dem NameDecorationRoutingDomain (der auf msn.com festgelegt werden sollte), wenn er nicht die Domänen in der NameDecorationExcludedDomainList enthält (wir können derzeit msn.com, live.com, Hotmail.com, outlook.com unterstützen). 
  
3. Über einen Skype for Business-Client können Benutzer jetzt nach einem Skype-Benutzer suchen und diesen hinzufügen.
    
## <a name="clients-and-interoperability-matrix"></a>Clients und Interoperabilitätsmatrix

In der folgenden Tabelle ist der Status der Inaktivität zwischen der neuesten Version von Skype Consumer und der neuesten Version von Skype for Business aufgeführt.
  

|**Skype Clients**|**Hinzufügen von Kontakten, Im-, Anwesenheits-, Audio- und Videoanrufen**|**Kommentar**|
|:-----|:-----|:-----|
|Skype Windows Desktop  <br/> |7.6 oder höher, Windows XP und höher  <br/> |**NEU:** Unterstützung für Windows -Skype-Client, der unter Windows XP ausgeführt wird, und Windows Vista hinzugefügt (erfordert die neueste **Clientversion 7.26 oder höher)** <br/> |
|Skype Mobile – Android Phone und Tablet  <br/> |6.19 oder höher mit Android OS Version 4.0.3 oder höher  <br/> |Geräte mit geringer Spezifikation unterstützen möglicherweise keine Videoanrufe.  <br/> |
|Skype Mobile – iOS  <br/> |6.11 oder höher, auf IOS 7 oder höher  <br/> |Nicht unterstützt werden iPhone 4 und frühere iPod der 4. Generation und früher, iPad 1. Generation  <br/> |
|Skype Mac  <br/> |7.19 oder höher, unter Mac OS X 10.9 (Mavericks) oder höher  <br/> |Erfordert Mac OSX 10.9 oder höher  <br/> |
|Skype Universal Windows App (Windows 10) Desktop und Mobile  <br/> |Windows 10 (Redstone 1-Update oder höher)  <br/> |Die universelle Windows-App erhält ein Update im Fall 2016 und bietet Zusätzliche Interopunterstützung.  <br/> |
   
In der folgenden Tabelle ist der Status der Inaktivität zwischen der neuesten Version von Skype for Business und der neuesten Version von Skype Consumer aufgeführt. 
  
|**Client**|**Skype-Verzeichnissuche und Hinzufügen von Kontakten**|**Skype A/V, Chatinteop**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Ja  <br/> |Ja  <br/> |
|Skype for Business auf dem Mac  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2013  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Web App – online und lokal  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |
|Lync Mobile – Windows Phone  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Mobile – Android  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Mobile – iOS  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync-Raumsystem  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Ja  <br/> |Ja  <br/> |
|Lync Mac 2011  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2010  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Phone Edition  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |
|Lync Attendant  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |
   
